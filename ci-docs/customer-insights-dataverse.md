---
title: Práca s údajmi Customer Insights v Microsoft Dataverse
description: Zistite, ako prepojiť Customer Insights a Microsoft Dataverse a pochopiť výstupné entity, ktoré sa exportujú do Dataverse.
ms.date: 05/30/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: 3848e143bc7cb2f345bc698a274b92148ef00669
ms.sourcegitcommit: f5af5613afd9c3f2f0695e2d62d225f0b504f033
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 06/01/2022
ms.locfileid: "8833695"
---
# <a name="work-with-customer-insights-data-in-microsoft-dataverse"></a>Práca s údajmi Customer Insights v Microsoft Dataverse

Customer Insights poskytuje možnosť sprístupniť výstupné entity ako [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro). Táto integrácia umožňuje jednoduché zdieľanie údajov a vlastný vývoj prostredníctvom prístupu s nízkym kódom/bez kódu. The [výstupné entity](#output-entities) sú dostupné ako tabuľky v a Dataverse životné prostredie. Údaje môžete použiť pre akúkoľvek inú aplikáciu založenú na Dataverse tabuľky. Tieto tabuľky umožňujú scenáre, ako sú automatizované pracovné postupy Power Automate alebo vytváranie aplikácií pomocou Power Apps.

Pripája sa k vášmu Dataverse prostredie vám to tiež umožňuje [prijímať údaje zo zdrojov údajov lokálny pomocou Power Platform dátové toky a brány](data-sources.md#add-data-from-on-premises-data-sources).

## <a name="prerequisites"></a>Požiadavky

- Štatistiky zákazníkov a Dataverse prostredia musia byť hosťované v rovnakej oblasti.
- Musíte mať rolu globálneho správcu v Dataverse životné prostredie. Overte si, či toto [Dataverse prostredie je spojené](/power-platform/admin/control-user-access#associate-a-security-group-with-a-dataverse-environment) do určitých skupín zabezpečenia a uistite sa, že ste do týchto skupín zabezpečenia pridaný.
- Žiadne iné prostredie Customer Insights už nie je priradené k Dataverse prostredie, ktoré chcete pripojiť. Naučiť sa ako [odstrániť existujúce pripojenie k a Dataverse životné prostredie](#remove-an-existing-connection-to-a-dataverse-environment).
- A Microsoft Dataverse prostredie sa môže pripojiť iba k jednému účtu úložiska. Platí to iba vtedy, ak nakonfigurujete prostredie [použi svoj Azure Data Lake Storage](own-data-lake-storage.md).

## <a name="connect-a-dataverse-environment-to-customer-insights"></a>Pripojte a Dataverse prostredia na Customer Insights

The **Microsoft Dataverse** krok vám umožní prepojiť Customer Insights s vaším Dataverse prostredia kým [vytvorenie prostredia Customer Insights](create-environment.md).

:::image type="content" source="media/dataverse-provisioning.png" alt-text="zdieľanie údajov s Microsoft Dataverse automaticky povolené pre nové sieťové prostredia.":::

Správcovia môžu nakonfigurovať Customer Insights na pripojenie existujúceho Dataverse životné prostredie. Poskytnutím adresy URL na Dataverse prostredie, pripája sa k ich novému prostrediu Customer Insights.

Ak nechcete použiť existujúci Dataverse prostredie, systém vytvorí nové prostredie pre údaje Customer Insights vo vašom nájomníkovi. [Power Platform správcovia môžu kontrolovať, kto môže vytvárať prostredia](/power-platform/admin/control-environment-creation). Keď nastavujete nové prostredie Customer Insights a správca zakázal vytváranie Dataverse prostrediach pre všetkých okrem správcov, možno nebudete môcť vytvoriť nové prostredie.

**Povoliť zdieľanie údajov** s Dataverse začiarknutím políčka zdieľania údajov.

Ak používate svoj vlastný účet Data Lake Storage, potrebujete aj **Identifikátor povolení**. Ďalšie informácie o tom, ako získať identifikátor povolenia, nájdete v nasledujúcej časti.

## <a name="enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview"></a>Povoliť zdieľanie údajov s Dataverse z vlastného Azure Data Lake Storage (Náhľad)

Povolenie zdieľania údajov s Microsoft Dataverse keď vaše prostredie [používa svoje vlastné Azure Data Lake Storage účtu](own-data-lake-storage.md) potrebuje nejakú extra konfiguráciu. Používateľ, ktorý nastavuje prostredie Customer Insights, musí mať min **Storage Blob Data Reader** povolenia na *CustomerInsights* kontajner v Azure Data Lake Storage účtu.

1. Vytvorte dve skupiny zabezpečenia vo svojom predplatnom Azure – jednu **Čitateľ** bezpečnostná skupina a jedna **Prispievateľ** bezpečnostnú skupinu a nastavte Microsoft Dataverse ako vlastník pre obe bezpečnostné skupiny.
2. Spravujte zoznam riadenia prístupu (ACL) v kontajneri CustomerInsights vo svojom účte úložiska prostredníctvom týchto skupín zabezpečenia. Pridajte Microsoft Dataverse servis a akékoľvek Dataverse podnikových aplikácií, ako je Dynamics 365 Marketing **Čitateľ** bezpečnostná skupina s **iba na čítanie** povolenia. Pridať *iba* aplikáciu Customers Insights na **Prispievateľ** bezpečnostná skupina udeliť oboje **čítaj a píš** povolenia na písanie profilov a prehľadov.

### <a name="limitations"></a>Obmedzenia

Pri používaní existujú dve obmedzenia Dataverse so svojimi vlastnými Azure Data Lake Storage účet:

- Existuje mapovanie jedna ku jednej medzi a Dataverse organizácia a an Azure Data Lake Storage účtu. Raz Dataverse organizácia je pripojená k účtu úložiska, nemôže sa pripojiť k inému účtu úložiska. Toto obmedzenie bráni tomu, aby a Dataverse nezapĺňa viacero účtov úložiska.
- Zdieľanie údajov nebude fungovať, ak je na prístup k účtu úložiska Azure Data Lake potrebné nastavenie Azure Private Link, pretože je za bránou firewall. Dataverse momentálne nepodporuje pripojenie k súkromným koncovým bodom cez Private Link.

### <a name="set-up-powershell"></a>Nastavte PowerShell

Ak chcete spustiť skripty PowerShell, musíte najskôr zodpovedajúcim spôsobom nastaviť PowerShell.

1. Nainštalujte najnovšiu verziu [Azure Active Directory PowerShell pre Graph](/powershell/azure/active-directory/install-adv2).
   1. Na počítači stlačte kláves Windows a nájdite **Windows PowerShell** a vyberte **Spustiť ako správca**.
   1. Do okna PowerShell, ktoré sa otvorí, zadajte výraz `Install-Module AzureAD`.
2. Importujte tri moduly.
    1. V okne PowerShell zadajte`Install-Module -Name Az.Accounts` a postupujte podľa krokov.
    1. Opakujte pre`Install-Module -Name Az.Resources` a `Install-Module -Name Az.Storage`.

### <a name="configuration-steps"></a>Kroky konfigurácie

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
        - Po úspešnom spustení skriptu skopírujte výstupný reťazec. Výstupný reťazec vyzerá takto:`https://DVBYODLDemo/customerinsights?rg=285f5727-a2ae-4afd-9549-64343a0gbabc&cg=720d2dae-4ac8-59f8-9e96-2fa675dbdabc`

2. Zadajte výstupný reťazec skopírovaný zhora do **Identifikátor povolení** poľa kroku konfigurácie prostredia pre Microsoft Dataverse.

:::image type="content" source="media/dataverse-enable-datasharing-BYODL.png" alt-text="Možnosti konfigurácie umožňujúce zdieľanie údajov z vašich vlastných Azure Data Lake Storage s Microsoft Dataverse .":::

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

Ak odstránenie pripojenia zlyhá kvôli závislostiam, musíte odstrániť aj závislosti. Ďalšie informácie nájdete v časti [Odstránenie závislostí](/power-platform/alm/removing-dependencies).

## <a name="output-entities"></a>Výstupné entity

Niektoré výstupné entity z Customer Insights sú dostupné ako tabuľky v Dataverse. Nasledujúce časti popisujú očakávanú schému týchto tabuliek.

- [CustomerProfile](#customerprofile)
- [AlternateKey](#alternatekey)
- [UnifiedActivity](#unifiedactivity)
- [CustomerMeasure](#customermeasure)
- [Obohatenie](#enrichment)
- [Predikcia](#prediction)
- [Členstvo v segmente](#segment-membership)

### <a name="customerprofile"></a>CustomerProfile

Táto tabuľka obsahuje zjednotený profil zákazníka z nástroja Customer Insights. Schéma pre zjednotený zákaznícky profil závisí od entít a atribútov použitých v procese zjednotenia údajov. Schéma profilu zákazníka zvyčajne obsahuje podmnožinu atribútov z [Definícia Common Data Model pre CustomerProfile ](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customerprofile).

### <a name="alternatekey"></a>AlternateKey

Tabuľka AlternateKey obsahuje kľúče entít, ktoré sa zúčastnili procesu zjednotenia.

|Column  |Zadať  |Popis  |
|---------|---------|---------|
|DataSourceName    |String         | Názov zdroja údajov. Napríklad: `datasource5`        |
|EntityName        | String        | Názov entity v Customer Insights. Napríklad: `contact1`        |
|AlternateValue    |String         |Alternatívne ID, ktoré je namapované na ID zákazníka. Príklad: `cntid_1078`         |
|KeyRing           | Viacriadkový text        | Hodnota JSON  </br> Ukážka: [{"dataSourceName":" datasource5 ",</br>"entityName":" contact1",</br>"preferredKey":" cntid_1078",</br>"keys":[" cntid_1078"]}]       |
|ID zákazníka         | String        | ID zjednoteného profilu zákazníka.         |
|AlternateKeyId     | GUID         |  AlternateKey deterministický založený GUID na msdynci_identifier       |
|msdynci_identifier |   String      |   `DataSourceName|EntityName|AlternateValue`  </br> Ukážka: `testdatasource|contact1|cntid_1078`    |

### <a name="unifiedactivity"></a>UnifiedActivity

Táto tabuľka obsahuje aktivity používateľov, ktoré sú k dispozícii v Customer Insights.

| Column            | Zadať        | Popis                                                                              |
|-------------------|-------------|------------------------------------------------------------------------------------------|
| ID zákazníka        | String      | ID profilu zákazníka                                                                      |
| ActivityId        | String      | Interné ID aktivity zákazníka (primárny kľúč)                                       |
| SourceEntityName  | String      | Názov zdrojovej entity                                                                |
| SourceActivityId  | String      | Primárny kľúč zo zdrojovej entity                                                       |
| ActivityType      | String      | Typ sémantickej aktivity alebo názov vlastnej aktivity                                        |
| ActivityTimeStamp | DATETIME    | Časová pečiatka aktivity                                                                      |
| Nadpis             | String      | Titul alebo názov aktivity                                                               |
| Popis       | String      | Opis aktivity                                                                     |
| Adresa URL               | String      | Odkaz na externú adresu URL špecifickú pre danú aktivitu                                         |
| SemanticData      | Reťazec JSON | Zahŕňa zoznam párov kľúč/hodnota pre polia sémantického mapovania špecifické pre typ aktivity |
| RangeIndex        | String      | Unixová časová pečiatka používaná na triedenie časovej osi aktivity a dotazov na efektívny rozsah |
| mydynci_unifiedactivityid   | GUID | Interné ID aktivity zákazníka (ActivityId) |

### <a name="customermeasure"></a>CustomerMeasure

Táto tabuľka obsahuje výstupné údaje mier založených na atribútoch zákazníka.

| Column             | Zadať             | Popis                 |
|--------------------|------------------|-----------------------------|
| ID zákazníka         | String           | ID profilu zákazníka        |
| Miery           | Reťazec JSON      | Zahŕňa zoznam párov kľúčových hodnôt pre názov miery a hodnoty pre daného zákazníka | 
| msdynci_identifier | String           | `Customer_Measure|CustomerId` |
| msdynci_customermeasureid | GUID      | ID profilu zákazníka |


### <a name="enrichment"></a>Obohatenie

Táto tabuľka obsahuje výstup z procesu obohacovania.

| Column               | Zadať             |  Popis                                          |
|----------------------|------------------|------------------------------------------------------|
| ID zákazníka           | String           | ID profilu zákazníka                                 |
| EnrichmentProvider   | String           | Názov poskytovateľa pre obohatenie                                  |
| EnrichmentType       | String           | Typ obohatenia                                      |
| Hodnoty               | Reťazec JSON      | Zoznam atribútov získaných procesom obohacovania |
| msdynci_enrichmentid | GUID             | Deterministický GUID vygenerovaný z msdynci_identifier |
| msdynci_identifier   | String           | `EnrichmentProvider|EnrichmentType|CustomerId`         |

### <a name="prediction"></a>Predikcia

Táto tabuľka obsahuje výstup predikcií modelu.

| Column               | Zadať        | Popis                                          |
|----------------------|-------------|------------------------------------------------------|
| ID zákazníka           | String      | ID profilu zákazníka                                  |
| ModelProvider        | String      | Názov poskytovateľa modelu                                      |
| Model                | String      | Názov modelu                                                |
| Hodnoty               | Reťazec JSON | Zoznam atribútov získaných modelom |
| msdynci_predictionid | GUID        | Deterministický GUID vygenerovaný z msdynci_identifier | 
| msdynci_identifier   | String      |  `Model|ModelProvider|CustomerId`                      |

### <a name="segment-membership"></a>Členstvo v segmente

Táto tabuľka obsahuje informácie o členstve v segmentoch profilov zákazníkov.

| Column        | Type | Description                        |
|--------------------|--------------|-----------------------------|
| ID zákazníka        | String       | ID profilu zákazníka        |
| SegmentProvider      | String       | Aplikácia, ktorá zverejňuje segmenty.      |
| Typ členstva v segmente | String       | Typ záznamu členstva v tomto segmente zákazníka. Podporuje viacero typov, ako napríklad Zákazník, Kontakt alebo Účet. Predvolené: Zákazník  |
| Segmenty       | Reťazec JSON  | Zoznam jedinečných segmentov, ktorých členom je profil zákazníka      |
| msdynci_identifier  | String   | Jedinečný identifikátor záznamu členstva v segmente. `CustomerId|SegmentProvider|SegmentMembershipType|Name`  |
| msdynci_segmentmembershipid | GUID      | Deterministický GUID generovaný z`msdynci_identifier`          |

<!--
## FAQ: Update existing environments to use Microsoft Dataverse

Between mid-May 2022 and June 13, 2022, administrators can update the environment settings with a Dataverse environment that Customer Insights can use. On June 13, 2022, your environment will be updated automatically and we'll create a Dataverse environment on your tenant for you.

1. My environment uses my own Azure Data Lake Storage account. Do I still need to update?

   If there's already a Dataverse environment configured in your environment, the update isn't required. If no Dataverse is environment configured, the **Update now** button will create a Dataverse environment and update from the Customer Insights database to a Dataverse database.

1. Will we get extra Dataverse capacity, or will the update use my existing Dataverse capacity?

   - If there's already a Dataverse environment configured in your Customer Insights environment, or connected with other Dynamics 365 or Power Apps applications, the capacity remains unchanged.
   - If the Dataverse environment is new, it will add new storage and database capacity. The capacity added varies per environment and entitlements. You'll get 3 GB for trial and sandbox environment. Production environments get 15 GB.

1. I proceeded with the update and it seems like nothing happened. Is the update complete?

   If the notification in Customer Insights doesn't show anymore, the update is complete. You can check the status of the update by reviewing your environment settings.

1. Why do I still see the banner after completing the update steps?

   It can happen due to an upgrade or refresh failure. Contact support.

1. I received a "Failed to provision Dataverse environment" error after starting the update. What happened?

   It can happen due to an upgrade or refresh failure. Contact support.
   Common causes:
    - Insufficient capacity. There's no more capacity to create more environments. For more information, see [Manage capacity action](/power-platform/admin/capacity-storage#actions-to-take-for-a-storage-capacity-deficit).
    - Region mismatch between tenant region and Customer Insights environment region in the Australia and India regions.
    - Insufficient privileges to provision Dataverse. The users starting the update needs a Dynamics 365 admin role.
    - -->
