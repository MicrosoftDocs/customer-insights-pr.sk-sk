---
title: Údaje Customer Insights v Microsoft Dataverse
description: Použite entity Customer Insights ako tabuľky v Microsoft Dataverse.
ms.date: 11/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: 6f74559b34a95ed976a4e353c2dbabe59e1a8839
ms.sourcegitcommit: 9558ff772ee6c944fcb8db4bfc8cda13b38a1bff
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 11/29/2021
ms.locfileid: "7866953"
---
# <a name="work-with-customer-insights-data-in-microsoft-dataverse"></a>Pracujte s údajmi Customer Insights v Microsoft Dataverse

Customer Insights poskytuje možnosť sprístupniť výstupné entity v [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro.md). Táto integrácia umožňuje ľahké zdieľanie údajov a vlastný vývoj prostredníctvom prístupu založeného na nízkom alebo žiadnom kóde. Výstupné entity budú dostupné ako tabuľky v Dataverse. Tieto tabuľky umožňujú scenáre ako napr [automatizované pracovné postupy prostredníctvom Power Automate](/power-automate/getting-started),[modelom riadené aplikácie](/powerapps/maker/model-driven-apps/) a [aplikácie na plátne](/powerapps/maker/canvas-apps/) cez Power Apps. Údaje môžete použiť pre akúkoľvek inú aplikáciu, ktorá je založená na Dataverse tabuľkách. Aktuálna implementácia podporuje hlavne vyhľadávania, kde je možné pre dané ID zákazníka načítať údaje z dostupných štatistík publika.

## <a name="attach-a-dataverse-environment-to-customer-insights"></a>Pripojte Dataverse prostredie k Customer Insights

**Organizácie s existujúcimi prostrediami Dataverse**

Organizácie, ktoré už používajú Dataverse, môžu [použite jedno z ich existujúcich Dataverse prostredí](create-environment.md) keď správca nastaví štatistiky publika. Poskytnutím adresy URL do prostredia Dataverse sa pripojí k ich novému prostrediu štatistík publika. Na zabezpečenie čo najlepšieho výkonu musia byť prostredia Customer Insights a Dataverse hosťované v rovnakej oblasti.

**Nová organizácia**

Ak pri nastavovaní Customer Insights vytvoríte novú organizáciu, automaticky získate nové Dataverse prostredie.

> [!NOTE]
> Ak vaše organizácie už používajú Dataverse vo svojom nájomníkovi, je dôležité si uvedomiť, že [Dataverse vytváranie prostredia je riadené správcom](/power-platform/admin/control-environment-creation.md) . Ak napríklad pomocou účtu organizácie nastavujete nové prostredie štatistík publika a správca zakázal vytváranie Dataverse skúšobných prostredí pre všetkých okrem správcov, nemôžete vytvoriť nové skúšobné prostredie.
> 
> Dataverse skúšobné prostredia vytvorené v Customer Insights majú 3 GB úložného priestoru, ktorý sa nezapočítava do celkovej kapacity oprávnenej nájomcom. Platené odbery získavajú Dataverse nárok na 15 GB pre databázu a 20 GB pre ukladanie súborov.

## <a name="output-entities"></a>Výstupné entity

Niektoré výstupné entity zo štatistík publika sú dostupné ako tabuľky v Dataverse. Nasledujúce časti popisujú očakávanú schému týchto tabuliek.

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

| Column        | Type | Description                        |
|--------------------|--------------|-----------------------------|
| ID zákazníka        | String       | ID profilu zákazníka        |
| SegmentProvider      | String       | Aplikácia, ktorá zverejňuje segmenty. Predvolené: Štatistiky publika         |
| Typ členstva v segmente | String       | Typ záznamu členstva v tomto segmente zákazníka. Podporuje viacero typov, ako napríklad Zákazník, Kontakt alebo Účet. Predvolené: Zákazník  |
| Segmenty       | Reťazec JSON  | Zoznam jedinečných segmentov, ktorých členom je profil zákazníka      |
| msdynci_identifier  | String   | Jedinečný identifikátor záznamu členstva v segmente. `CustomerId|SegmentProvider|SegmentMembershipType|Name`  |
| msdynci_segmentmembershipid | GUID      | Deterministický GUID generovaný z`msdynci_identifier`          |
