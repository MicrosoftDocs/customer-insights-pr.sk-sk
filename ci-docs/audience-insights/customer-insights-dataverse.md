---
title: Údaje riešenia Customer Insights v Microsoft Dataverse
description: Entity Customer Insights použite ako tabuľky v Microsoft Dataverse.
ms.date: 04/05/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: bbbbf2a7f5edb81ee75f6e33988cd4721134b6e7
ms.sourcegitcommit: 0363559a1af7ae16da2a96b09d6a4a8a53a8cbb8
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 04/05/2022
ms.locfileid: "8547645"
---
# <a name="work-with-customer-insights-data-in-microsoft-dataverse"></a>Práca s údajmi Customer Insights v Microsoft Dataverse

Customer Insights poskytuje možnosť sprístupniť výstupné entity dostupné v [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro). Táto integrácia umožňuje jednoduché zdieľanie údajov a vlastný vývoj prostredníctvom prístupu s nízkym kódom/bez kódu. The [výstupné entity](#output-entities) sú dostupné ako tabuľky v a Dataverse životné prostredie. Údaje môžete použiť pre akúkoľvek inú aplikáciu založenú na Dataverse tabuľky. Tieto tabuľky umožňujú scenáre, ako sú automatizované pracovné postupy Power Automate alebo vytváranie aplikácií pomocou Power Apps. Aktuálna implementácia podporuje hlavne vyhľadávania, kde je možné získať údaje z dostupných entít Customer Insights pre dané ID zákazníka.

## <a name="attach-a-dataverse-environment-to-customer-insights"></a>Pripojenie prostredia Dataverse do Customer Insights

**Existujúca organizácia**

Správcovia môžu nakonfigurovať Customer Insights na [použiť existujúci Dataverse životné prostredie](create-environment.md) keď vytvoria prostredie Customer Insights. Poskytnutím adresy URL do prostredia Dataverse sa pripája k ich novému prostrediu prehľadov cieľovej skupiny. Štatistiky zákazníkov a Dataverse prostredia musia byť hosťované v rovnakej oblasti. 

Ak nechcete použiť existujúci Dataverse prostredie, systém vytvorí nové prostredie pre údaje Customer Insights vo vašom nájomníkovi. 

> [!NOTE]
> Ak už vaše organizácie používajú Dataverse v ich nájomníkovi, je dôležité si zapamätať, že [vytvorenie prostredia Dataverse riadi správca](/power-platform/admin/control-environment-creation). Napríklad ak vo svojom účte organizácie nastavujete nové prostredie prehľadov cieľovej skupiny a správca zakázal vytváranie skúšobných prostredí Dataverse pre všetkých okrem správcov, nemôžete vytvoriť nové skúšobné prostredie.
> 
> Skúšobné prostredia Dataverse vytvorené v Customer Insights majú 3 GB úložného priestoru, ktorý sa nezapočítava do celkovej kapacity, na ktorú má nájomník nárok. Platené predplatné získa oprávnenie Dataverse na 15 GB na databázu a 20 GB na ukladanie súborov.

**Nová organizácia**

Ak pri nastavovaní Customer Insights vytvoríte novú organizáciu, systém automaticky vytvorí novú Dataverse prostredie vo vašej organizácii pre vás.

## <a name="output-entities"></a>Výstupné entity

Niektoré výstupné entity z prehľadov cieľovej skupiny sú k dispozícii ako tabuľky v Dataverse. Nasledujúce časti popisujú očakávanú schému týchto tabuliek.

- [CustomerProfile](#customerprofile)
- [AlternateKey](#alternatekey)
- [UnifiedActivity](#unifiedactivity)
- [CustomerMeasure](#customermeasure)
- [Obohatenie](#enrichment)
- [Predikcia](#prediction)
- [Členstvo v segmente](#segment-membership)


### <a name="customerprofile"></a>CustomerProfile

Táto tabuľka obsahuje zjednotený profil zákazníka z nástroja Customer Insights. Schéma pre zjednotený profil zákazníka závisí od entít a atribútov použitých v procese zlučovania. Schéma profilu zákazníka zvyčajne obsahuje podmnožinu atribútov z [Definícia Common Data Model pre CustomerProfile ](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customerprofile).

### <a name="alternatekey"></a>AlternateKey

Tabuľka AlternateKey obsahuje kľúče entít, ktoré sa zúčastnili procesu zjednotenia.

|Column  |Zadať  |Popis  |
|---------|---------|---------|
|DataSourceName    |String         | Názov zdroja údajov. Napríklad: `datasource5`        |
|EntityName        | String        | Názov entity v prehľadoch cieľovej skupiny. Napríklad: `contact1`        |
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

| Column        | Type | Description                        |
|--------------------|--------------|-----------------------------|
| ID zákazníka        | String       | ID profilu zákazníka        |
| SegmentProvider      | String       | Aplikácia, ktorá zverejňuje segmenty. Predvolené: Štatistiky publika         |
| Typ členstva v segmente | String       | Typ záznamu členstva v tomto segmente zákazníka. Podporuje viacero typov, ako napríklad Zákazník, Kontakt alebo Účet. Predvolené: Zákazník  |
| Segmenty       | Reťazec JSON  | Zoznam jedinečných segmentov, ktorých členom je profil zákazníka      |
| msdynci_identifier  | String   | Jedinečný identifikátor záznamu členstva v segmente. `CustomerId|SegmentProvider|SegmentMembershipType|Name`  |
| msdynci_segmentmembershipid | GUID      | Deterministický GUID generovaný z`msdynci_identifier`          |
