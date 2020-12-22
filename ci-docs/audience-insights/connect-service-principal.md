---
title: Pripojenie k účtu Azure Data Lake Storage Gen2 pomocou objektu služby
description: Použite objekt služby Azure pre prehľady cieľových skupín na pripojenie vlastného dátového jazera, keď ho pripájate k prehľadom cieľových skupín.
ms.date: 11/24/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: c2fae278d34fa02b9168ac70dfa8dd351653245e
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 11/25/2020
ms.locfileid: "4644107"
---
# <a name="connect-to-an-azure-data-lake-storage-gen2-account-with-an-azure-service-principal-for-audience-insights"></a>Pripojenie k účtu Azure Data Lake Storage Gen2 pomocou objektu služby Azure pre prehľady cieľových skupín

Automatizované nástroje, ktoré využívajú služby Azure, by mali mať vždy obmedzené povolenia. Namiesto prihlasovania aplikácií ako plne privilegovaného používateľa ponúka Azure objekty služieb. Čítajte ďalej a dozviete sa, ako prepojiť prehľady cieľových skupín s účtom Azure Data Lake Storage Gen2, ktorý používa objekt služby Azure namiesto kľúčov účtu ukladacieho priestoru. 

Objekt služby môžete použiť na bezpečné [pridanie alebo úpravu priečinka Common Data Model ako zdroj údajov](connect-common-data-model.md) alebo [vytvorenie nového či aktualizáciu existujúceho prostredia](manage-environments.md#create-an-environment-in-an-existing-organization).

Na vytvorenie objektu služby potrebujete povolenia správcu predplatného Azure.

## <a name="create-azure-service-principal-for-audience-insights"></a>Vytvorte objekt služby Azure pre prehľady cieľových skupín

Pred vytvorením nového objektu služby pre prehľady cieľových skupín skontrolujte, či už vo vašej organizácii existuje.

### <a name="look-for-an-existing-service-principal"></a>Vyhľadajte existujúci objekt služby

1. Prejdite do [portálu spravovania služby Azure](https://portal.azure.com) a prihláste sa do svojej organizácie.

2. Vyberte položku **Azure Active Directory** zo služieb Azure.

3. V časti **Spravovať** vyberte **Podnikové aplikácie**.

4. Vyhľadajte ID aplikácie prvej strany s prehľadmi cieľových skupín `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` alebo názov `Dynamics 365 AI for Customer Insights`.

5. Ak nájdete zodpovedajúci záznam, znamená to, že objekt služby pre prehľady cieľových skupín existuje. Nemusíte nič znova vytvárať.
   
   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="Snímka obrazovky, ktorá ukazuje existujúci objekt služby.":::
   
6. Ak sa nevrátia žiadne výsledky, vytvorte nový objekt služby.

### <a name="create-a-new-service-principal"></a>Vytvorte nový objekt služby

1. Nainštalujte si najnovšiu verziu **Azure Active Directory PowerShell pre Graph**. Ďalšie informácie nájdete v sekcii [Inštalovať Azure Active Directory PowerShell pre Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2).
   - Na počítači vyberte kláves Windows na klávesnici a vyhľadajte výraz **Windows PowerShell** a **Spustiť ako správca**.
   
   - Do okna PowerShell, ktoré sa otvorí, zadajte výraz `Install-Module AzureAD`.

2. Vytvorte objekt služby pre prehľady cieľových skupín pomocou modulu Azure AD PowerShell.
   - Do okna PowerShell zadajte výraz `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure`. Nahraďte „ID vášho nájomníka“ skutočným ID vášho nájomníka, v ktorom chcete vytvoriť objekt služby. Parameter názvu prostredia `AzureEnvironmentName` je voliteľný.
  
   - Zadajte `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`. Tento príkaz vytvorí objekt služby pre prehľady cieľových skupín vo vybranom nájomníkovi.  

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a>Udeľte povolenia pre objekt služby na prístup k účtu úložiska

Prejdite na portál Azure a udeľte objektu služby povolenia pre účet úložiska, ktorý chcete použiť v prehľadoch cieľových skupín.

1. Prejdite do [portálu spravovania služby Azure](https://portal.azure.com) a prihláste sa do svojej organizácie.

1. Otvorte účet úložiska, ku ktorému má mať prístup objekt služby pre prehľady cieľových skupín.

1. Vyberte položku **Riadenie prístupu (IAM)** na navigačnej table a vyberte položku **Pridať** > **Pridajte priradenie roly**.
   
   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text="Snímka obrazovky, ktorá ukazuje portál Azure pri pridávaní priradenia roly.":::
   
1. Na table **Pridať priradenie roly** nastavte nasledujúce vlastnosti:
   - Rola: *Prispievateľ údajov do objektu BLOB úložiska*
   - Priradiť prístup k: *Používateľovi, skupine alebo objektu služby*
   - Vyberte: *Dynamics 365 AI for Customer Insights* ([objekt služby, ktorý ste vytvorili](#create-a-new-service-principal))

1.  Vyberte položku **Uložiť**.

Vyplnenie zmien môže byť dokončené až o 15 minút.

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-audience-insights"></a>Zadajte ID zdroja Azure alebo podrobnosti o predplatnom služby Azure v prílohe účtu úložiska k Audience Insights.

Pripojte účet úložiska Azure Data Lake v prehľadoch cieľových skupín na [ukladanie výstupných údajov](manage-environments.md) alebo [jeho použitie ako zdroja údajov](connect-common-data-service-lake.md). Výber možnosti Azure Data Lake vám umožní vybrať si medzi prístupom založeným na zdrojoch alebo na predplatnom.

Podľa nasledujúcich pokynov uveďte požadované informácie o vybranom prístupe.

### <a name="resounce-based-storage-account-connection"></a>Pripojenie účtu úložiska na základe zdrojov

1. Prejdite na [portál spravovania služby Azure](https://portal.azure.com), prihláste sa do predplatného a otvorte účet úložiska.

1. Prejdite na časť **Nastavenia** > **Vlastnosti** na navigačnej table.

1. Skopírujte hodnotu ID zdroja účtu úložiska.

   :::image type="content" source="media/ADLS-SP-ResourceId.png" alt-text="Skopírujte ID zdroja účtu úložiska.":::

1. V prehľadoch cieľových skupín vložte ID zdroja do poľa zdroja zobrazeného na obrazovke pripojenia účtu úložiska.

   :::image type="content" source="media/ADLS-SP-ResourceIdConnection.png" alt-text="Zadajte informácie o ID zdroja účtu úložiska.":::   
   
1. Pokračujte zvyšnými krokmi v prehľadoch cieľových skupín a pripojte účet úložiska.

### <a name="subscription-based-storage-account-connection"></a>Pripojenie účtu úložiska na základe predplatného

1. Prejdite na [portál spravovania služby Azure](https://portal.azure.com), prihláste sa do predplatného a otvorte účet úložiska.

1. Prejdite na časť **Nastavenia** > **Vlastnosti** na navigačnej table.

1. Skontrolujte **Predplatné**, **Skupinu zdrojov** a **Názov** účtu úložiska, aby ste v prehľadoch cieľových skupín vybrali správne hodnoty.

1. Pri pripájaní účtu úložiska vyberte v prehľadoch cieľových skupín hodnoty alebo príslušné polia.

   :::image type="content" source="media/ADLS-SP-SubscriptionConnection.png" alt-text="Zadajte informácie o ID zdroja účtu úložiska.":::
   
1. Pokračujte zvyšnými krokmi v prehľadoch cieľových skupín a pripojte účet úložiska.
