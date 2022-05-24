---
title: Príklady OData pre Dynamics 365 Customer Insights API
description: Bežne používané príklady protokolu Open Data Protocol (OData) na dopytovanie rozhraní API Customer Insights na kontrolu údajov.
ms.date: 05/10/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 007278e1330e1a8e64d524ded8496acaf83b874c
ms.sourcegitcommit: a50c5e70d2baf4db41a349162fd1b1f84c3e03b6
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 05/11/2022
ms.locfileid: "8740076"
---
# <a name="odata-query-examples"></a>Príklady dotazov OData

Open Data Protocol (OData) je protokol pre prístup k údajom založený na základných protokoloch, ako je HTTP. Používa bežne akceptované metodológie ako REST pre web. Existujú rôzne druhy knižníc a nástrojov, ktoré možno použiť na používanie služieb OData.

V tomto článku sú uvedené niektoré často požadované vzorové dotazy, ktoré vám pomôžu pri vytváraní vlastných implementácií na základe [Rozhrania API Customer Insights](apis.md).

Musíte upraviť vzorky dotazov, aby fungovali v cieľových prostrediach: 

- {serviceRoot}:`https://api.ci.ai.dynamics.com/v1/instances/{instanceId}` kde{instanceId} je GUID prostredia Customer Insights, na ktoré sa chcete dotazovať. The [Operácia ListAllInstances](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances) vám umožní nájsť{InstanceId} máte prístup k.
- {CID}: GUID jednotného zákazníckeho záznamu. Príklad: `ce759201f786d590bf2134bff576c369`.
- {AlternateKey}: Identifikátor primárneho kľúča záznamu zákazníka v zdroj údajov. Príklad: `CNTID_1002`
- {DSname}: Reťazec s názvom entity zdroj údajov, ktorý sa prijíma do Customer Insights. Príklad: `Website_contacts`.
- {SegmentName}: Reťazec s názvom výstupnej entity segmentu v Customer Insights. Príklad: `Male_under_40`.

## <a name="customer"></a>zákazník

Nasledujúca tabuľka obsahuje súbor vzorových dotazov pre *Zákazník* subjekt.


|Typ dotazu |Príklad  | Poznámka  |
|---------|---------|---------|
|Identifikačné číslo jedného zákazníka     | `{serviceRoot}/Customer?$filter=CustomerId eq '{CID}'`          |  |
|Alternatívny kľúč    | `{serviceRoot}/Customer?$filter={DSname_EntityName_PrimaryKeyColumnName} eq '{AlternateKey}' `         |  Alternatívne kľúče pretrvávajú v jednotnej entite zákazníka       |
|Vyberte   | `{serviceRoot}/Customer?$select=CustomerId,FullName&$filter=customerid eq '1'`        |         |
|O    | `{serviceRoot}/Customer?$filter=CustomerId in ('{CID1}',’{CID2}’)`        |         |
|Alternatívny kľúč + In   | `Customer?$filter={DSname_EntityName_PrimaryKeyColumnName} in ('{AlternateKey}','{AlternateKey}')`         |         |
|Vyhľadávať  | `{serviceRoot}/Customer?$top=10&$skip=0&$search="string"`        |   Vráti 10 najlepších výsledkov pre hľadaný reťazec      |
|Členstvo v segmente  | `{serviceRoot}/Customer?select=*&$filter=IsMemberOfSegment('{SegmentName}')&$top=10  `     | Vráti prednastavený počet riadkov z entity segmentácie.      |

## <a name="unified-activity"></a>Jednotná činnosť

Nasledujúca tabuľka obsahuje súbor vzorových dotazov pre *UnifiedActivity* subjekt.

|Typ dotazu |Príklad  | Poznámka  |
|---------|---------|---------|
|Činnosť CID     | `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq '{CID}'`          | Uvádza aktivity konkrétneho profilu zákazníka |
|Časový rámec činnosti    | `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq '{CID}' and ActivityTime gt 2017-01-01T00:00:00.000Z and ActivityTime lt 2020-01-01T00:00:00.000Z`     |  Aktivity zákazníckeho profilu v časovom rámci       |
|Typ aktivity    |   `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq '{CID}' and ActivityType eq '{ActivityName}'`        |         |
|Aktivita podľa zobrazovaného mena     | `{serviceRoot}/UnifiedActivity$filter=CustomerId eq ‘{CID}’ and ActivityTypeDisplay eq ‘{ActivityDisplayName}’ `        | |
|Triedenie činností    | `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq ‘{CID}’ & $orderby=ActivityTime asc`     |  Zoraďte aktivity vzostupne alebo zostupne       |
|Aktivita sa rozšírila z členstva v segmente  |   `{serviceRoot}/Customer?$expand=UnifiedActivity,Customer_Measure&$filter=CustomerId eq '{CID}'`     |         |

## <a name="other-examples"></a>Ďalšie príklady

Nasledujúca tabuľka obsahuje súbor vzorových dotazov pre iné entity.

|Typ dotazu |Príklad  | Poznámka  |
|---------|---------|---------|
|Opatrenia CID    | `{serviceRoot}/Customer_Measure?$filter=CustomerId eq '{CID}'`          |  |
|Obohatené značky CID    | `{serviceRoot}/BrandShareOfVoiceFromMicrosoft?$filter=CustomerId eq '{CID}'`  |       |
|Obohatené záujmy CID    |   `{serviceRoot}/InterestShareOfVoiceFromMicrosoft?$filter=CustomerId eq '{CID}'`       |         |
|In-Clause + Expand     | `{serviceRoot}/Customer?$expand=UnifiedActivity,Customer_Measure&$filter=CustomerId in ('{CID}', '{CID}')`         | |
