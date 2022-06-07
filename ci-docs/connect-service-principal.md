---
title: Pripojenie k účtu Azure Data Lake Storage pomocou objektu služby
description: Na pripojenie k vlastnému dátovému jazeru použite objekt služby Azure.
ms.date: 05/31/2022
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-system-security
- customerInsights
ms.openlocfilehash: b18d1f42b9510ebf23f0666322819865d132173b
ms.sourcegitcommit: f5af5613afd9c3f2f0695e2d62d225f0b504f033
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 06/01/2022
ms.locfileid: "8833416"
---
# <a name="connect-to-an-azure-data-lake-storage-account-by-using-an-azure-service-principal"></a>Pripojenie k účtu Azure Data Lake Storage pomocou objektu služby Azure

Tento článok popisuje, ako sa pripojiť Dynamics 365 Customer Insights s Azure Data Lake Storage účtu pomocou princípu služby Azure namiesto kľúčov účtov úložiska.

Automatizované nástroje, ktoré využívajú služby Azure, by mali mať vždy obmedzené povolenia. Namiesto prihlasovania aplikácií ako plne privilegovaného používateľa ponúka Azure objekty služieb. Princípy služieb môžete použiť na zabezpečenie [pridajte alebo upravte priečinok Common Data Model ako zdroj údajov](connect-common-data-model.md) alebo [vytvoriť alebo aktualizovať prostredie](create-environment.md).

> [!IMPORTANT]
>
> - Účet Data Lake Storage, ktorý bude používať principál služby, musí byť Gen2 a mať ho [hierarchický menný priestor povolený](/azure/storage/blobs/data-lake-storage-namespace). Účty úložiska Azure Data Lake Gen1 nie sú podporované.
> - Na vytvorenie principála služby potrebujete administrátorské povolenia pre nájomník platformy Azure.

## <a name="create-an-azure-service-principal-for-customer-insights"></a>Vytvorte objekt služby Azure pre Customer Insights

Pred vytvorením nového principála služby pre Customer Insights skontrolujte, či už vo vašej organizácii existuje.

### <a name="look-for-an-existing-service-principal"></a>Vyhľadajte existujúci objekt služby

1. Prejdite do [portálu spravovania služby Azure](https://portal.azure.com) a prihláste sa do svojej organizácie.

2. V časti **Služby Azure** vyberte možnosť **Azure Active Directory**.

3. Pod **Spravovať**, vyberte **Aplikácia Microsoft**.

4. Pridajte filter pre **ID aplikácie začína na**`0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` alebo vyhľadajte meno `Dynamics 365 AI for Customer Insights`.

5. Ak nájdete zodpovedajúci záznam, znamená to, že objekt služby už existuje.

   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="Snímka obrazovky zobrazujúca existujúci objekt služby.":::

6. Ak sa nevrátia žiadne výsledky, môžete [vytvoriť nový príkazca služby](#create-a-new-service-principal). Vo väčšine prípadov už existuje a na prístup k účtu úložiska potrebujete iba udeliť povolenia pre principál služby.

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a>Udeľte povolenia pre objekt služby na prístup k účtu úložiska

Prejdite na portál Azure a udeľte povolenia principálovi služby pre účet úložiska, ktorý chcete použiť v Customer Insights.

1. Prejdite do [portálu spravovania služby Azure](https://portal.azure.com) a prihláste sa do svojej organizácie.

1. Otvorte účet úložiska, ku ktorému má mať prístup principál služby pre Customer Insights.

1. Na ľavej table vyberte **Kontrola prístupu (IAM)** a potom vyberte **Pridať** > **Pridať priradenie roly**.

   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text="Snímka obrazovky zobrazujúca portál Azure pri pridávaní priradenia roly.":::

1. Na table **Pridať priradenie roly** nastavte nasledujúce vlastnosti:
   - Rola: **Prispievateľ údajov do objektu BLOB úložiska**
   - Priradiť prístup k: **Používateľovi, skupine alebo objektu služby**
   - Vyberte členov: **Dynamics 365 AI pre Customer Insights** (ten [príkazca služby](#create-a-new-service-principal) vyhľadali ste skôr v tomto postupe)

1. Vyberte **Preskúmať + priradiť**.

Vyplnenie zmien môže byť dokončené až o 15 minút.

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-customer-insights"></a>Zadajte ID prostriedku Azure alebo podrobnosti o predplatnom Azure v prílohe účtu úložiska k Customer Insights

V Customer Insights môžete pripojiť účet Data Lake Storage [uložiť výstupné dáta](manage-environments.md) alebo [použite ho ako zdroj údajov](connect-dataverse-managed-lake.md). Táto možnosť vám umožňuje vybrať si z prístupu založeného na zdroji alebo na predplatnom. V závislosti od zvoleného prístupu postupujte podľa postupu v jednej z nasledujúcich sekcií.

### <a name="resource-based-storage-account-connection"></a>Pripojenie účtu úložiska na základe zdrojov

1. Prejdite na [portál spravovania služby Azure](https://portal.azure.com), prihláste sa do predplatného a otvorte účet úložiska.

1. Na ľavej table prejdite na **nastavenie** > **Koncové body**.

1. Skopírujte hodnotu ID zdroja účtu úložiska.

   :::image type="content" source="media/ADLS-SP-ResourceId.png" alt-text="Skopírujte ID zdroja účtu úložiska.":::

1. V Customer Insights vložte ID prostriedku do poľa prostriedku zobrazeného na obrazovke pripojenia účtu úložiska.

   :::image type="content" source="media/ADLS-SP-ResourceIdConnection.png" alt-text="Zadajte informácie o ID zdroja účtu úložiska.":::   

1. Pokračujte zvyšnými krokmi v Customer Insights a pripojte účet úložiska.

### <a name="subscription-based-storage-account-connection"></a>Pripojenie účtu úložiska na základe predplatného

1. Prejdite na [portál spravovania služby Azure](https://portal.azure.com), prihláste sa do predplatného a otvorte účet úložiska.

1. Na ľavej table prejdite na **Nastavenia** > **Vlastnosti**.

1. Skontrolujte **Predplatné**, **zdrojov**, a **názov** účtu úložiska, aby ste sa uistili, že v Customer Insights vyberiete správne hodnoty.

1. V Customer Insights vyberte hodnoty pre zodpovedajúce polia pri pripájaní účtu úložiska.

1. Pokračujte zvyšnými krokmi v Customer Insights a pripojte účet úložiska.

### <a name="create-a-new-service-principal"></a>Vytvorte nový objekt služby

1. Nainštalovať najnovšiu verziu Azure Active Directory PowerShell for Graph. Ak chcete získať ďalšie informácie, prejdite na [Inštalácia Azure Active Directory PowerShell for Graph](/powershell/azure/active-directory/install-adv2).

   1. Na počítači stlačte kláves Windows na klávesnici a vyhľadajte **Windows PowerShell** a vyberte **Spustiť ako správca**.

   1. Do okna PowerShell, ktoré sa otvorí, zadajte výraz `Install-Module AzureAD`.

2. Vytvorte objekt služby pre Customer Insights pomocou modulu Azure AD PowerShell.

   1. Do okna PowerShell zadajte výraz `Connect-AzureAD -TenantId "[your Directory ID]" -AzureEnvironmentName Azure`. Vymeňte *[ID vášho adresára]* so skutočným ID adresára vášho predplatného Azure, kde chcete vytvoriť principál služby. Parameter názvu prostredia, `AzureEnvironmentName`, je voliteľný.
  
   1. Zadajte `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`. Tento príkaz vytvorí objekt služby pre Customer Insights vo vybratom predplatnom Azure.

[!INCLUDE [footer-include](includes/footer-banner.md)]