---
title: Pripojenie k účtu Azure Data Lake Storage pomocou objektu služby Azure
description: Na pripojenie k vlastnému dátovému jazeru použite objekt služby Azure.
ms.date: 08/12/2022
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-system-security
- customerInsights
ms.openlocfilehash: eba10068c48db5c147100c25a397bcc13b014784
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304216"
---
# <a name="connect-to-an-azure-data-lake-storage-account-by-using-an-azure-service-principal"></a>Pripojenie k účtu Azure Data Lake Storage pomocou objektu služby Azure

Dynamics 365 Customer Insights poskytuje možnosť pripojenia k Azure Data Lake Storage účtu pomocou princípu služby Azure namiesto kľúčov účtov úložiska.

Automatizované nástroje, ktoré používajú služby Azure, musia mať obmedzené povolenia. Namiesto prihlasovania aplikácií ako plne privilegovaného používateľa ponúka Azure objekty služieb. Na zabezpečenie použite princípy služieb [pridajte alebo upravte priečinok Common Data Model ako zdroj údajov](connect-common-data-model.md) alebo [vytvoriť alebo aktualizovať prostredie](create-environment.md).

## <a name="prerequisites"></a>Požiadavky

- Účet Data Lake Storage, ktorý bude používať principál služby, musí byť Gen2. Účty úložiska Azure Data Lake Gen1 nie sú podporované.
- Účet Data Lake Storage má [povolený hierarchický menný priestor](/azure/storage/blobs/data-lake-storage-namespace).
- Povolenia správcu pre nájomník platformy Azure, ak musíte vytvoriť nový principál služby.

## <a name="create-an-azure-service-principal-for-customer-insights"></a>Vytvorte objekt služby Azure pre Customer Insights

Pred vytvorením nového principála služby pre Customer Insights skontrolujte, či už vo vašej organizácii existuje. Vo väčšine prípadov už existuje.

### <a name="look-for-an-existing-service-principal"></a>Vyhľadajte existujúci objekt služby

1. Prejdite do [portálu spravovania služby Azure](https://portal.azure.com) a prihláste sa do svojej organizácie.

2. V časti **Služby Azure** vyberte možnosť **Azure Active Directory**.

3. Pod **Spravovať**, vyberte **Aplikácia Microsoft**.

4. Pridajte filter pre **ID aplikácie začína na**`0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` alebo vyhľadajte meno `Dynamics 365 AI for Customer Insights`.

5. Ak nájdete zodpovedajúci záznam, znamená to, že objekt služby už existuje. [Udeliť povolenia](#grant-permissions-to-the-service-principal-to-access-the-storage-account) aby mal príkazca služby prístup k účtu úložiska.

   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="Snímka obrazovky zobrazujúca existujúci objekt služby.":::

6. Ak sa nevrátia žiadne výsledky, [vytvoriť nový príkazca služby](#create-a-new-service-principal).

### <a name="create-a-new-service-principal"></a>Vytvorte nový objekt služby

1. Nainštalovať najnovšiu verziu Azure Active Directory PowerShell for Graph. Ak chcete získať ďalšie informácie, prejdite na [Inštalácia Azure Active Directory PowerShell for Graph](/powershell/azure/active-directory/install-adv2).

   1. Na počítači stlačte kláves Windows na klávesnici a vyhľadajte **Windows PowerShell** a vyberte **Spustiť ako správca**.

   1. Do okna PowerShell, ktoré sa otvorí, zadajte výraz `Install-Module AzureAD`.

2. Vytvorte objekt služby pre Customer Insights pomocou modulu Azure AD PowerShell.

   1. Do okna PowerShell zadajte výraz `Connect-AzureAD -TenantId "[your Directory ID]" -AzureEnvironmentName Azure`. Nahradiť *[ID vášho adresára]* so skutočným ID adresára vášho predplatného Azure, kde chcete vytvoriť principál služby. Parameter názvu prostredia, `AzureEnvironmentName`, je voliteľný.
  
   1. Zadajte `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`. Tento príkaz vytvorí objekt služby pre Customer Insights vo vybratom predplatnom Azure.

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a>Udeľte povolenia pre objekt služby na prístup k účtu úložiska

Ak chcete udeliť povolenia principálovi služby pre účet úložiska, ktorý chcete použiť v Customer Insights, k účtu úložiska alebo kontajneru musí byť priradená jedna z nasledujúcich rolí:

|Poverenie|Požiadavky|
|----------|------------|
|Aktuálne prihlásený používateľ|**Role** : Čítačka dát objektu Storage Blob, prispievateľ objektu Storage Blob alebo vlastník objektu Storage Blob.<br>**úroveň** : Povolenia udelené pre účet úložiska alebo kontajner.</br>|
|Riaditeľ služby Customer Insights –<br>Použitím Azure Data Lake Storage ako zdroj údajov</br>|Možnosť č. 1<ul><li>**Role** : Čítačka údajov objektu Storage Blob, prispievateľ údajov objektu Storage Blob alebo vlastník údajov objektu Storage Blob.</li><li>**úroveň** : Povolenia udelené pre účet úložiska.</li></ul>Možnosť 2 *(bez zdieľania prístupu Principal Service k účtu úložiska)*<ul><li>**Úloha 1** : Čítačka údajov objektu Storage Blob, prispievateľ údajov objektu Storage Blob alebo vlastník údajov objektu Storage Blob.</li><li>**úroveň** : Povolenia udelené na kontajneri.</li><li>**Úloha 2** : Storage Blob Data Delegator.</li><li>**úroveň** : Povolenia udelené pre účet úložiska.</li></ul>|
|Riaditeľ služby Customer Insights – <br>Použitím Azure Data Lake Storage ako výstup alebo cieľ</br>|Možnosť č. 1<ul><li>**Role** : Prispievateľ údajov objektu Storage Blob alebo Vlastník objektu Storage Blob.</li><li>**úroveň** : Povolenia udelené pre účet úložiska.</li></ul>Možnosť 2 *(bez zdieľania prístupu Principal Service k účtu úložiska)*<ul><li>**Role** : Prispievateľ údajov objektu Storage Blob alebo Vlastník objektu Storage Blob.</li><li>**úroveň** : Povolenia udelené na kontajneri.</li><li>**Úloha 2** : Storage Blob Delegator.</li><li>**úroveň** : Povolenia udelené pre účet úložiska.</li></ul>|

1. Prejdite do [portálu spravovania služby Azure](https://portal.azure.com) a prihláste sa do svojej organizácie.

1. Otvorte konto úložiska, ku ktorému má mať principál služby pre Customer Insights prístup.

1. Na ľavej table vyberte **Kontrola prístupu (IAM)** a potom vyberte **Pridať** > **Pridať priradenie roly**.

   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text="Snímka obrazovky zobrazujúca portál Azure pri pridávaní priradenia roly.":::

1. Na table **Pridať priradenie roly** nastavte nasledujúce vlastnosti:
   - **Role** : Čítačka dát objektu Storage Blob, prispievateľ objektu Storage Blob alebo vlastník objektu Storage Blob na základe poverení uvedených vyššie.
   - **Prideliť prístup k** :**Používateľ, skupina alebo principál služby**
   - **Vyberte** členovia: **Dynamics 365 AI for Customer Insights** (ten [objednávateľ služby](#create-a-new-service-principal) vyhľadali ste skôr v tomto postupe)

1. Vyberte **Preskúmať + priradiť**.

Vyplnenie zmien môže byť dokončené až o 15 minút.

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-customer-insights"></a>Zadajte ID prostriedku Azure alebo podrobnosti o predplatnom Azure v prílohe účtu úložiska k Customer Insights

Pripojte účet Data Lake Storage v Customer Insights k [uložiť výstupné dáta](manage-environments.md) alebo [použite ho ako zdroj údajov](connect-dataverse-managed-lake.md). Vyberte si medzi a [založené na zdrojoch](#resource-based-storage-account-connection) alebo a [na základe predplatného](#subscription-based-storage-account-connection) pristúpte a postupujte podľa týchto krokov.

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

[!INCLUDE [footer-include](includes/footer-banner.md)]
