---
title: Slúži na vytvorenie a spravovanie prostredí
description: Zistite, ako sa môžete zaregistrovať do služby a spravovať prostredia.
ms.date: 03/28/2022
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: adkuppa
ms.author: adkuppa
manager: shellyha
searchScope:
- ci-system-about
- customerInsights
ms.openlocfilehash: ba29bcd173e615e544bd10e69043f310c009eb47
ms.sourcegitcommit: ae02ac950810242e2505d7d371b80210dc8a0777
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 03/29/2022
ms.locfileid: "8492023"
---
# <a name="manage-environments"></a>Správa prostredí

## <a name="switch-environments"></a>Prepnutie prostredí

Ak chcete zmeniť prostredie, vyberte ovládací prvok **prostredia** v pravom hornom rohu stránky.

:::image type="content" source="media/home-page-environment-switcher.png" alt-text="Snímka obrazovky ovládacieho prvku na prepínanie prostredí.":::

Správcovia môžu [vytvárať](create-environment.md) a spravovať prostredia.

## <a name="edit-an-existing-environment"></a>Úprava existujúceho prostredia

Môžete upraviť niektoré podrobnosti o existujúcich prostrediach.

1.  Vyberte nástroj na výber **Prostredia** v hlavičke aplikácie.

2.  Vyberte ikonu **Upraviť**.

3. V poli **Upraviť prostredie** môžete aktualizovať nastavenia prostredia.

Ďalšie informácie o nastaveniach prostredia nájdete v článku [Vytvorenie nového prostredia](create-environment.md).

## <a name="connect-to-microsoft-dataverse"></a>Pripojiť k systému Microsoft Dataverse
   
Krok **Microsoft Dataverse** vám umožní prepojiť Customer Insights s vašim prostredím Dataverse. 

Poskytnite svoje vlastné Microsoft Dataverse prostredie na zdieľanie údajov (profilov a prehľadov) s obchodnými aplikáciami založenými na Dataverse, ako je Dynamics 365 Marketing alebo modelom riadené aplikácie v Power Apps.

Ak chcete použiť [pripravené modely predikcie](predictions-overview.md#out-of-box-models), nakonfigurujte zdieľanie údajov s Dataverse. Alebo môžete povoliť príjem údajov z lokálnych zdrojov údajov poskytnutím adresy URL prostredia Microsoft Dataverse, ktoré spravuje vaša organizácia.

Povolenie zdieľania údajov s Microsoft Dataverse začiarknutím políčka zdieľania údajov spustíte jednorazové úplné obnovenie vašich zdrojov údajov a všetkých ostatných procesov.

> [!IMPORTANT]
> 1. Štatistiky zákazníkov a Dataverse musia byť v rovnakej oblasti, aby bolo možné zdieľať údaje.
> 1. Musíte mať rolu globálneho správcu v Dataverse životné prostredie. Overte si, či toto [Dataverse prostredie je spojené](/power-platform/admin/control-user-access#associate-a-security-group-with-a-dataverse-environment) do určitých bezpečnostných skupín a uistite sa, že ste boli pridaní do týchto bezpečnostných skupín.
> 1. Nie je s tým už spojené žiadne existujúce prostredie Customer Insights Dataverse životné prostredie. Naučiť sa ako [odstrániť existujúce pripojenie k a Dataverse životné prostredie](#remove-an-existing-connection-to-a-dataverse-environment).

:::image type="content" source="media/dataverse-enable-datasharing.png" alt-text="Možnosti konfigurácie, ktoré umožnia zdieľanie údajov s Microsoft Dataverse.":::

### <a name="enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview"></a>Povoliť zdieľanie údajov s Dataverse z vlastného Azure Data Lake Storage (Náhľad)

Ak je vaše prostredie nakonfigurované na používanie vášho vlastného Azure Data Lake Storage na ukladanie údajov Customer Insights, čo umožňuje zdieľanie údajov s Microsoft Dataverse potrebuje nejakú extra konfiguráciu.

1. Vytvorte dve skupiny zabezpečenia vo svojom predplatnom Azure – jednu **Čitateľ** bezpečnostná skupina a jedna **Prispievateľ** bezpečnostnú skupinu a nastavte Microsoft Dataverse ako vlastník pre obe bezpečnostné skupiny.
2. Spravujte zoznam riadenia prístupu (ACL) v kontajneri CustomerInsights vo svojom účte úložiska prostredníctvom týchto skupín zabezpečenia. Pridajte Microsoft Dataverse servis a akékoľvek Dataverse podnikových aplikácií, ako je Dynamics 365 Marketing **Čitateľ** bezpečnostná skupina s **iba na čítanie** povolenia. Pridať *iba* aplikáciu Customers Insights na **Prispievateľ** bezpečnostná skupina udeliť oboje **čítaj a píš** povolenia na písanie profilov a prehľadov.
   
#### <a name="prerequisites"></a>Požiadavky

Ak chcete spustiť skripty PowerShell, musíte mať importované nasledujúce tri moduly. 

1. Nainštalujte najnovšiu verziu [Azure Active Directory PowerShell pre Graph](/powershell/azure/active-directory/install-adv2).
   1. Na počítači stlačte kláves Windows a nájdite **Windows PowerShell** a vyberte **Spustiť ako správca**.
   1. Do okna PowerShell, ktoré sa otvorí, zadajte výraz `Install-Module AzureAD`.
2. Importujte tri moduly.
    1. V okne PowerShell zadajte`Install-Module -Name Az.Accounts` a postupujte podľa krokov. 
    1. Opakujte pre`Install-Module -Name Az.Resources` a `Install-Module -Name Az.Storage`.

#### <a name="configuration-steps"></a>Kroky konfigurácie

1. Stiahnite si dva skripty PowerShell, ktoré potrebujete na spustenie, z nášho inžiniera [Úložisko GitHub](https://github.com/trin-msft/byol).
    1. `CreateSecurityGroups.ps1`
       - Potrebuješ *správca nájomcu* povolenia na spustenie tohto skriptu PowerShell. 
       - Tento skript PowerShell vytvorí dve skupiny zabezpečenia vo vašom predplatnom Azure. Jeden pre skupinu Reader a druhý pre skupinu Contributor and will make Microsoft Dataverse ako vlastník pre obe tieto bezpečnostné skupiny.
       - Spustite tento skript PowerShell v prostredí Windows PowerShell zadaním ID predplatného Azure, ktoré obsahuje vaše Azure Data Lake Storage. Otvorte skript PowerShell v editore a pozrite si ďalšie informácie a implementovanú logiku.
       - Uložte obe hodnoty ID bezpečnostnej skupiny vygenerované týmto skriptom, pretože ich použijeme v`ByolSetup.ps1` skript.
       
        > [!NOTE]
        > Vytváranie bezpečnostnej skupiny je možné vo vašom nájomníkovi zakázať. V takom prípade by bolo potrebné manuálne nastavenie a vaše Azure AD admin by musel [povoliť vytvorenie bezpečnostnej skupiny](/azure/active-directory/enterprise-users/groups-self-service-management).

    2. `ByolSetup.ps1`
        - Potrebuješ *Vlastník údajov objektu Storage Blob* oprávnenia na úrovni účtu úložiska/kontajnera na spustenie tohto skriptu alebo tento skript vytvorí jeden za vás. Po úspešnom spustení skriptu je možné priradenie vašej role manuálne odstrániť.
        - Tento skript PowerShell pridáva požadované riadenie prístupu na základe tole (RBAC) pre Microsoft Dataverse servis a akékoľvek Dataverse podnikové aplikácie. Aktualizuje tiež zoznam riadenia prístupu (ACL) v kontajneri CustomerInsights pre skupiny zabezpečenia vytvorené pomocou`CreateSecurityGroups.ps1` skript. Skupina prispievateľov bude mať *rwx* a skupina čitateľov bude mať *rx* iba povolenie.
        - Spustite tento skript PowerShell v prostredí Windows PowerShell zadaním ID predplatného Azure, ktoré obsahuje vaše Azure Data Lake Storage, názov účtu úložiska, názov skupiny prostriedkov a hodnoty ID bezpečnostnej skupiny Reader a Contributor. Otvorte skript PowerShell v editore a pozrite si ďalšie informácie a implementovanú logiku.
        - Po úspešnom spustení skriptu skopírujte výstupný reťazec. Výstupný reťazec vyzerá takto:`https: //DVBYODLDemo/customerinsights?rg=285f5727-a2ae-4afd-9549-64343a0gbabc&cg=720d2dae-4ac8-59f8-9e96-2fa675dbdabc`
        
2. Zadajte výstupný reťazec skopírovaný zhora do **Identifikátor povolení** poľa kroku konfigurácie prostredia pre Microsoft Dataverse.

:::image type="content" source="media/dataverse-enable-datasharing-BYODL.png" alt-text="Možnosti konfigurácie umožňujúce zdieľanie údajov z vašich vlastných Azure Data Lake Storage s Microsoft Dataverse .":::

Customer Insights nepodporuje nasledujúce scenáre zdieľania údajov:
- Ak povolíte zdieľanie údajov pomocou Dataverse, nebudete môcť [vytvárať predikované ani chýbajúce hodnoty v entite](predictions.md).
- Ak povolíte zdieľanie údajov s Dataverse, nebudete môcť zobraziť žiadne voliteľné zostavy PowerBI Embedded v prostredí Customer Insights.

### <a name="remove-an-existing-connection-to-a-dataverse-environment"></a>Odstráňte existujúce pripojenie k a Dataverse životné prostredie

Pri pripájaní k a Dataverse prostredia, chybové hlásenie **Táto organizácia CDS je už pripojená k inej inštancii Customer Insights** znamená, že Dataverse sa už používa v prostredí Customer Insights. Existujúce pripojenie môžete odstrániť ako globálny správca na Dataverse životné prostredie. Vyplnenie zmien môže trvať niekoľko hodín.

1. Prejdite do systému [Power Apps](https://make.powerapps.com).
1. Vyberte prostredie z výberu prostredia.
1. Ísť do **Riešenia**
1. Odinštalujte alebo odstráňte pomenované riešenie **Dynamics 365 Customer Insights Doplnok zákazníckej karty (ukážka)**.

OR 

1. Otvor tvoj Dataverse životné prostredie.
1. Ísť do **Pokročilé nastavenia** > **Riešenia**.
1. Odinštalujte **CustomerInsightsCustomerCard** Riešenie.

## <a name="copy-the-environment-configuration"></a>Skopírovať konfiguráciu prostredia

Ako správca sa môžete rozhodnúť skopírovať konfiguráciu z existujúceho prostredia, keď vytvoríte nové. 

:::image type="content" source="media/environment-settings-dialog.png" alt-text="Snímka obrazovky s možnosťami nastavení v nastaveniach prostredia.":::

Zobrazí sa zoznam všetkých dostupných prostredí vo vašej organizácii, z ktorých môžete kopírovať údaje.

Skopírujú sa nasledujúce konfiguračné nastavenia:

- Prijaté/importované zdroje údajov
- Zjednotenie údajov (Mapovanie, Zosúladenie, Zlúčenie)
- Segmenty
- Miery
- Vzťahy
- Aktivity
- Index vyhľadávania a filtrovania
- Ciele exportu
- Plánovaná obnova
- Obohatenia
- Spravovanie modelov
- Priradenia roly

## <a name="set-up-a-copied-environment"></a>Nastavte skopírované prostredie

Pri kopírovaní konfigurácie prostredia sú nasledujúce údaje *nie* skopírované:

- Profily zákazníkov.
- Poverenia zdroja údajov. Budete musieť poskytnúť poverenia pre každý zdroj údajov a ručne obnoviť zdroje údajov.
- Zdroje údajov z priečinka Common Data Model a dátového jazera spravovaného v Dataverse. Tieto zdroje údajov budete musieť vytvoriť ručne s rovnakým názvom ako v zdrojovom prostredí.
- Tajomstvá pripojenia, ktoré sa používajú na exporty a obohatenia. Musíte znova overiť pripojenia a potom znova aktivovať obohatenia a exporty. 

Po skopírovaní prostredia sa zobrazí potvrdzovacia správa o vytvorení nového prostredia. Stlačte možnosť **Prejsť na zdroje údajov**, čím si zobrazíte zoznam zdrojov údajov.

Všetky zdroje údajov sa zobrazia so stavom **Vyžadované poverenia**. Upravte zdroje údajov a zadaním poverení ich obnovte.

:::image type="content" source="media/data-sources-copied.png" alt-text="Zoznam zdrojov údajov, ktoré boli skopírované a vyžadujú autentifikáciu.":::

Po obnovení zdrojov údajov prejdite na stránku **Údaje** > **Zjednotiť**. Tu nájdete nastavenia zo zdrojového prostredia. Upravte ich podľa potreby alebo stlačte možnosť **Spustiť**, čím začnete proces zjednotenia údajov a vytvoríte jednotnú entitu zákazníka.

Po dokončení zjednotenia údajov prejdite na stránku **Opatrenia** a **Segmenty**, čím ich tiež obnovíte.

Pred opätovnou aktiváciou exportov a obohatení prejdite na stránku **Admin** > **Spojenia** na opätovné overenie pripojení vo vašom novom prostredí.

## <a name="change-the-owner-of-an-environment"></a>Zmeňte vlastníka prostredia

Aj keď v Customer Insights môže mať niekoľko používateľov povolenia správcu, vlastníkom prostredia je iba jeden používateľ. V predvolenom nastavení je to správca, ktorý na začiatku vytvára prostredie. Ako správca prostredia môžete prideliť vlastníctvo inému používateľovi s oprávneniami správcu.

1. Vyberte nástroj na výber **Prostredia** v hlavičke aplikácie.

1. Vyberte ikonu **Upraviť**.

1. V **Upraviť prostredie** box, prejdite na **Základné informácie** krok.

1. V **Zmeniť vlastníka prostredia** poľa, vybrať nového vlastníka prostredia.  

1. Vyberte **Skontrolujte a dokončite**, potom **Aktualizovať** aplikujte zmeny. 

## <a name="claim-ownership-of-an-environment"></a>Nárokujte si vlastníctvo prostredia

Ak vlastník prostredia opustí organizáciu alebo sa odstráni jeho používateľský účet, prostredie nebude mať vlastníka. Používateľ s oprávneniami správcu si môže nárokovať vlastníctvo a stať sa novým vlastníkom. Môžu naďalej vlastniť životné prostredie resp [zmeniť vlastníctvo na iného správcu](#change-the-owner-of-an-environment). 

Ak si chcete nárokovať vlastníctvo, vyberte **Prevziať vlastníctvo** tlačidlo, ktoré sa zobrazuje v hornej časti každej stránky v Customer Insights, keď pôvodný vlastník opustil organizáciu.

## <a name="reset-an-existing-environment"></a>Reset existujúceho prostredia

Ako vlastník prostredia môžete resetovať prostredie do prázdneho stavu, ak chcete vymazať všetky konfigurácie a odstrániť prijaté údaje.

1.  Vyberte nástroj na výber **Prostredia** v hlavičke aplikácie. 

2.  Vyberte prostredie, ktoré chcete resetovať, a vyberte tri bodky (**...**). 

3. Vyberte možnosť **Resetovať**. 

4.  Ak chcete potvrdiť odstránenie, zadajte názov prostredia a vyberte položku **Resetovať**.

## <a name="delete-an-existing-environment"></a>Odstránenie existujúceho prostredia

Ako vlastník prostredia môžete odstrániť prostredie, ktoré spravujete.

1.  Vyberte nástroj na výber **Prostredia** v hlavičke aplikácie.

2.  Vyberte prostredie, ktoré chcete resetovať, a vyberte tri bodky (**...**). 

3. Vyberte možnosť **Odstrániť**. 

4.  Odstránenie potvrdíte zadaním názvu prostredia a výberom položky **Odstrániť**.

> [!NOTE]
> Vymazaním prostredia sa neodstráni priradenie k a Dataverse prostredia.Naučte sa, ako na to [odstrániť existujúce pripojenie k a Dataverse životné prostredie](#remove-an-existing-connection-to-a-dataverse-environment).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
