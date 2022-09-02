---
title: Príklady dotazov OData pre rozhrania API Customer Insights
description: Bežne používané príklady protokolu Open Data Protocol (OData) na dopytovanie rozhraní API Customer Insights na kontrolu údajov.
ms.date: 08/30/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 26e56a3bab01ba55284a52e72efbcbfbaadaad6f
ms.sourcegitcommit: 624b27bb65a0de1970dc1ac436643b493f0a31cf
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 08/31/2022
ms.locfileid: "9387221"
---
# <a name="odata-query-examples-for-customer-insights-apis"></a>Príklady dotazov OData pre rozhrania API Customer Insights

Open Data Protocol (OData) je protokol pre prístup k údajom založený na základných protokoloch, ako je HTTP. Používa bežne akceptované metodológie ako REST pre web. Existujú rôzne druhy knižníc a nástrojov, ktoré možno použiť na používanie služieb OData.

Aby sme vám pomohli vytvoriť si vlastné implementácie založené na [Rozhrania API Customer Insights](apis.md) , skontrolujte niektoré často požadované príklady dopytov.

Upravte vzorky dotazov, aby fungovali v cieľových prostrediach:

- {serviceRoot}:`https://api.ci.ai.dynamics.com/v1/instances/{instanceId}/data` kde{instanceId} je GUID prostredia Customer Insights, na ktoré sa chcete dotazovať. The [Operácia ListAllInstances](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances) vám umožní nájsť{InstanceId} máte prístup k.
- {CID}: GUID jednotného zákazníckeho záznamu. Príklad: `ce759201f786d590bf2134bff576c369`.
- {AlternateKey}: Identifikátor primárneho kľúča záznamu zákazníka v zdroj údajov. Príklad: `CNTID_1002`
- {DSname}: Reťazec s názvom entity zdroj údajov, ktorý sa prijíma do Customer Insights. Príklad: `Website_contacts`.
- {SegmentName}: Reťazec s názvom výstupnej entity segmentu v Customer Insights. Príklad: `Male_under_40`.

## <a name="customer"></a>zákazník

Vzorové otázky pre *Zákazník* subjekt.

|Typ dotazu |Príklad  | Poznámka  |
|---------|---------|---------|
|Identifikačné číslo jedného zákazníka     | `{serviceRoot}/Customer?$filter=CustomerId eq '{CID}'`          |  |
|alternatívny kľúč    | `{serviceRoot}/Customer?$filter={DSname_EntityName_PrimaryKeyColumnName} eq '{AlternateKey}'`         |  Alternatívne kľúče pretrvávajú v jednotnej entite zákazníka       |
|Vyberte   | `{serviceRoot}/Customer?$select=CustomerId,FullName&$filter=customerid eq '1'`        |         |
|O    | `{serviceRoot}/Customer?$filter=CustomerId in ('{CID1}',’{CID2}’)`        |         |
|alternatívny kľúč + In   | `{serviceRoot}/Customer?$filter={DSname_EntityName_PrimaryKeyColumnName} in ('{AlternateKey}','{AlternateKey}')`         |         |
|Vyhľadávať  | `{serviceRoot}/Customer?$top=10&$skip=0&$search="string"`        |   Vráti 10 najlepších výsledkov pre hľadaný reťazec      |
|Členstvo v segmente  | `{serviceRoot}/Customer?select=*&$filter=IsMemberOfSegment('{SegmentName}')&$top=10`     | Vráti prednastavený počet riadkov z entity segmentácie.      |
|Členstvo v segmente pre zákazníka | `{serviceRoot}/Customer?$filter=CustomerId eq '{CID}'&IsMemberOfSegment('{SegmentName}')`     | Vráti profil zákazníka, ak je členom daného segmentu     |

## <a name="unified-activity"></a>Jednotná činnosť

Vzorové otázky pre *UnifiedActivity* subjekt.

|Typ dotazu |Príklad  | Poznámka  |
|---------|---------|---------|
|Činnosť CID     | `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq '{CID}'`          | Uvádza aktivity konkrétneho profilu zákazníka |
|Časový rámec činnosti    | `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq '{CID}' and ActivityTime gt 2017-01-01T00:00:00.000Z and ActivityTime lt 2020-01-01T00:00:00.000Z`     |  Aktivity zákazníckeho profilu v časovom rámci       |
|Typ aktivity    |   `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq '{CID}' and ActivityType eq '{ActivityName}'`        |         |
|Aktivita podľa zobrazovaného mena     | `{serviceRoot}/UnifiedActivity$filter=CustomerId eq ‘{CID}’ and ActivityTypeDisplay eq ‘{ActivityDisplayName}’`        | |
|Triedenie aktivít    | `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq ‘{CID}’ & $orderby=ActivityTime asc`     |  Zoraďte aktivity vzostupne alebo zostupne       |
|Aktivita sa rozšírila z členstva v segmente  |   `{serviceRoot}/Customer?$expand=UnifiedActivity,Customer_Measure&$filter=CustomerId eq '{CID}'`     |         |

## <a name="other-examples"></a>Ďalšie príklady

Vzorové dopyty pre iné subjekty.

|Typ dotazu |Príklad  | Poznámka  |
|---------|---------|---------|
|Opatrenia CID    | `{serviceRoot}/Customer_Measure?$filter=CustomerId eq '{CID}'`          |  |
|Obohatené značky CID    | `{serviceRoot}/BrandShareOfVoiceFromMicrosoft?$filter=CustomerId eq '{CID}'`  |       |
|Obohatené záujmy CID    |   `{serviceRoot}/InterestShareOfVoiceFromMicrosoft?$filter=CustomerId eq '{CID}'`       |         |
|In-Clause + Expand     | `{serviceRoot}/Customer?$expand=UnifiedActivity,Customer_Measure&$filter=CustomerId in ('{CID}', '{CID}')`         | |

## <a name="not-supported-odata-queries"></a>Nepodporované dotazy OData

Customer Insights nepodporuje nasledujúce dotazy:

- `$filter` na prehltnutých zdrojových entitách. Dotazy $filter môžete spúšťať iba na systémové entity, ktoré vytvorí Customer Insights.
- `$expand` od a`$search` dopyt. Príklad: `Customer?$expand=UnifiedActivity$top=10&$skip=0&$search="corey"`
- `$expand` od`$select` ak je vybratá iba podmnožina atribútov. Príklad: `Customer?$select=CustomerId,FullName&$expand=UnifiedActivity&$filter=CustomerId eq '{CID}'`
- `$expand` obohatené značky alebo záujmové afinity pre daného zákazníka. Príklad: `Customer?$expand=BrandShareOfVoiceFromMicrosoft&$filter=CustomerId eq '518291faaa12f6d853c417835d40eb10'`
- Dopyt predikcia modeluje výstupné entity cez alternatívny kľúč. Príklad: `OOBModelOutputEntity?$filter=HotelCustomerID eq '{AK}'`
