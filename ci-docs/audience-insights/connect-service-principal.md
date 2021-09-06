---
title: Pripojenie k účtu Azure Data Lake Storage pomocou objektu služby
description: Na pripojenie k vlastnému dátovému jazeru použite objekt služby Azure.
ms.date: 07/23/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 845d1f55eb99f2adf9b437124addec4f6d016fec
ms.sourcegitcommit: 1c396394470df8e68c2fafe3106567536ff87194
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 08/30/2021
ms.locfileid: "7461167"
---
# <a name="connect-to-an-azure-data-lake-storage-account-by-using-an-azure-service-principal"></a>Pripojenie k účtu Azure Data Lake Storage pomocou objektu služby Azure
<!--note from editor: The Cloud Style Guide would have us just use "Azure Data Lake Storage" to mean the current version, unless the old version (Gen1) is mentioned. I've followed this guidance, even though it seems that our docs and Azure docs are all over the map on this.-->
Automatizované nástroje, ktoré využívajú služby Azure, by mali mať vždy obmedzené povolenia. Namiesto prihlasovania aplikácií ako plne privilegovaného používateľa ponúka Azure objekty služieb. Pokračujte v čítaní, aby ste sa dozvedeli, ako prepojiť Dynamics 365 Customer Insights s Azure Data Lake Storage pomocou objektu služby Azure namiesto kľúčov účtu úložiska. 

Objekt služby môžete použiť na bezpečné [pridanie alebo úpravu priečinka Common Data Model ako zdroja údajov](connect-common-data-model.md) alebo [na vytvorenie alebo aktualizáciu prostredia](get-started-paid.md).<!--note from editor: Suggested. Or it could be ", or create a new environment or update an existing one". I think "new" is implied with "create". The comma is necessary.-->

> [!IMPORTANT]
> - Účet Data Lake Storage, ktorý sa bude používať<!--note from editor: Suggested. Or perhaps it could be "The Data Lake Storage account to which you want to give access to the service principal..."--> objekt služby musí mať [povolený hierarchický priestor názvov](/azure/storage/blobs/data-lake-storage-namespace).
> - Na vytvorenie objektu služby potrebujete povolenia správcu predplatného Azure.

## <a name="create-an-azure-service-principal-for-customer-insights"></a>Vytvorte objekt služby Azure pre Customer Insights

Pred vytvorením nového objektu služby pre prehľady cieľovej skupiny alebo prehľady interakcií skontrolujte, či už vo vašej organizácii existuje.

### <a name="look-for-an-existing-service-principal"></a>Vyhľadajte existujúci objekt služby

1. Prejdite do [portálu spravovania služby Azure](https://portal.azure.com) a prihláste sa do svojej organizácie.

2. V časti **Služby Azure** vyberte možnosť **Azure Active Directory**.

3. V časti **Spravovať** vyberte **Podnikové aplikácie**.

4. Vyhľadajte Microsoft<!--note from editor: Via Microsoft Writing Style Guide.--> ID aplikácie:
   - Prehľady cieľových skupín: `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` s názvom `Dynamics 365 AI for Customer Insights`
   - Prehľady interakcií: `ffa7d2fe-fc04-4599-9f6d-7ca06dd0c4fd` s názvom `Dynamics 365 AI for Customer Insights engagement insights`

5. Ak nájdete zodpovedajúci záznam, znamená to, že objekt služby už existuje. 
   
   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="Snímka obrazovky zobrazujúca existujúci objekt služby.":::
   
6. Ak sa nevrátia žiadne výsledky, vytvorte nový objekt služby.

>[!NOTE]
>Aby ste využili všetky možnosti Dynamics 365 Customer Insights, odporúčame vám pridať obe aplikácie k objektu služby.<!--note from editor: Using the note format is suggested, just so this doesn't get lost by being tucked up in the step.-->

### <a name="create-a-new-service-principal"></a>Vytvorte nový objekt služby
<!--note from editor: Some general formatting notes: The MWSG wants bold for text the user enters (in addition to UI strings and the settings users select), but there's plenty of precedent for using code format for entering text in PowerShell so I didn't change that. Note that italic should be used for placeholders, but not much else.-->
1. Nainštalovať najnovšiu verziu Azure Active Directory PowerShell for Graph. Ak chcete získať ďalšie informácie, prejdite na [Inštalácia Azure Active Directory PowerShell for Graph](/powershell/azure/active-directory/install-adv2).

   1. Na počítači stlačte kláves Windows a nájdite **Windows PowerShell** a vyberte **Spustiť ako správca**.<!--note from editor: Or should this be something like "search for **Windows PowerShell** and, if asked, select **Run as administrator**."?-->
   
   1. Do okna PowerShell, ktoré sa otvorí, zadajte výraz `Install-Module AzureAD`.

2. Vytvorte objekt služby pre Customer Insights pomocou modulu Azure AD PowerShell.

   1. Do okna PowerShell zadajte výraz `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure`. Nahraďte *„[ID vášho nájomníka]”*<!--note from editor: Edit okay? Or should the quotation marks stay in the command line, in which case it would be "Replace *[your tenant ID]* --> aktuálnym ID vášho nájomníka, kde chcete vytvoriť objekt služby. Parameter názvu prostredia, `AzureEnvironmentName`, je voliteľný.
  
   1. Zadajte `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`. Tento príkaz vytvorí objekt služby pre prehľady cieľových skupín vo vybranom nájomníkovi. 

   1. Zadajte `New-AzureADServicePrincipal -AppId "ffa7d2fe-fc04-4599-9f6d-7ca06dd0c4fd" -DisplayName "Dynamics 365 AI for Customer Insights engagement insights"`. Tento príkaz vytvorí objekt služby pre prehľady interakcií<!--note from editor: Edit okay?--> na vybranom nájomníkovi.

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a>Udeľte povolenia pre objekt služby na prístup k účtu úložiska

Prejdite na portál Azure a udeľte objektu služby povolenia pre účet úložiska, ktorý chcete použiť v prehľadoch cieľových skupín.

1. Prejdite do [portálu spravovania služby Azure](https://portal.azure.com) a prihláste sa do svojej organizácie.

1. Otvorte účet úložiska, ku ktorému má mať prístup objekt služby pre prehľady cieľových skupín.

1. Na ľavej table vyberte **Kontrola prístupu (IAM)** a potom vyberte **Pridať** > **Pridať priradenie roly**.

   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text="Snímka obrazovky zobrazujúca portál Azure pri pridávaní priradenia roly.":::

1. Na table **Pridať priradenie roly** nastavte nasledujúce vlastnosti:
   - Rola: **Prispievateľ údajov do objektu BLOB úložiska**
   - Priradiť prístup k: **Používateľovi, skupine alebo objektu služby**
   - Vyberte: **Dynamics 365 AI for Customer Insights** a **prehľady interakcií Dynamics 365 AI for Customer Insights** (dva [objekty služieb](#create-a-new-service-principal), ktoré ste vytvorili skôr v tomto postupe)

1.  Vyberte položku **Uložiť**.

Vyplnenie zmien môže byť dokončené až o 15 minút.

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-audience-insights"></a>Zadajte ID zdroja Azure alebo podrobnosti o predplatnom služby Azure v prílohe účtu úložiska k prehľadom cieľovej skupiny

Môžete<!--note from editor: Edit suggested only if this section is optional.--> pripojiť účet Data Lake Storage v prehľadoch cieľovej skupiny na [uloženie výstupných údajov](manage-environments.md) alebo [ich použite ako zdroj údajov](connect-common-data-service-lake.md). Táto možnosť vám umožňuje vybrať si z prístupu založeného na zdroji alebo na predplatnom. V závislosti od zvoleného prístupu postupujte podľa postupu v jednej z nasledujúcich sekcií.<!--note from editor: Suggested.-->

### <a name="resource-based-storage-account-connection"></a>Pripojenie účtu úložiska na základe zdrojov

1. Prejdite na [portál spravovania služby Azure](https://portal.azure.com), prihláste sa do predplatného a otvorte účet úložiska.

1. Na ľavej table prejdite na **Nastavenia** > **Vlastnosti**.

1. Skopírujte hodnotu ID zdroja účtu úložiska.

   :::image type="content" source="media/ADLS-SP-ResourceId.png" alt-text="Skopírujte ID zdroja účtu úložiska.":::

1. Do prehľadov cieľovej skupiny zadajte ID zdroja do poľa zdroja zobrazeného na obrazovke pripojenia k účtu úložiska.

   :::image type="content" source="media/ADLS-SP-ResourceIdConnection.png" alt-text="Zadajte informácie o ID zdroja účtu úložiska.":::   

1. Pokračujte zvyšnými krokmi v prehľadoch cieľových skupín a pripojte účet úložiska.

### <a name="subscription-based-storage-account-connection"></a>Pripojenie účtu úložiska na základe predplatného

1. Prejdite na [portál spravovania služby Azure](https://portal.azure.com), prihláste sa do predplatného a otvorte účet úložiska.

1. Na ľavej table prejdite na **Nastavenia** > **Vlastnosti**.

1. Skontrolujte **Predplatné**, **Skupinu zdrojov** a **Názov** účtu úložiska, aby ste v prehľadoch cieľových skupín vybrali správne hodnoty.

1. V prehľadoch cieľovej skupiny vyberte pri pripájaní účtu úložiska hodnoty pre zodpovedajúce polia.

1. Pokračujte zvyšnými krokmi v prehľadoch cieľových skupín a pripojte účet úložiska.


[!INCLUDE[footer-include](../includes/footer-banner.md)]