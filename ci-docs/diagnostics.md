---
title: Audit Dynamics 365 Customer Insights s Azure Monitor
description: Zistite, ako odosielať denníky na Microsoft Azure Monitor.
ms.date: 12/14/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: article
author: brndkfr
ms.author: bkief
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: 15ae772617efa4c64cf79d0bac10a0c3cb28ca30
ms.sourcegitcommit: a92bf5985263240fd07bad98d8e119b88cf2c9d9
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 05/26/2022
ms.locfileid: "8807600"
---
# <a name="log-forwarding-in-dynamics-365-customer-insights-with-azure-monitor-preview"></a>Prihláste sa preposielanie Dynamics 365 Customer Insights s Azure Monitor (ukážka)

Dynamics 365 Customer Insights poskytuje priamu integráciu s Azure Monitor. Protokoly prostriedkov Azure Monitor vám umožňujú monitorovať a odosielať protokoly [Azure Storage](https://azure.microsoft.com/services/storage/),[Azure Log Analytics](/azure/azure-monitor/logs/log-analytics-overview) alebo ich streamujte na [Azure Event Hubs](https://azure.microsoft.com/services/event-hubs/).

Customer Insights odosiela nasledujúce protokoly udalostí:

- **Udalosti auditu**
  - **APIEvent** - umožňuje sledovanie zmien pomocou Dynamics 365 Customer Insights UI.
- **Prevádzkové udalosti**
  - **WorkflowEvent** - Pracovný postup vám umožňuje nastaviť [Zdroje dát](data-sources.md),[zjednotiť](data-unification.md),[obohatiť](enrichment-hub.md), a nakoniec [export](export-destinations.md) údaje do iných systémov. Všetky tieto kroky je možné vykonať jednotlivo (napríklad spustiť jeden export). Môže tiež bežať organizovane (napríklad obnova údajov zo zdrojov údajov, ktorá spustí proces zjednotenia, ktorý zavedie obohatenia a po dokončení exportuje údaje do iného systému). Viac informácií nájdete na [WorkflowEvent Schema](#workflow-event-schema).
  - **APIEvent** - všetky volania API do inštancie zákazníkov Dynamics 365 Customer Insights. Viac informácií nájdete na [Schéma APIEvent](#api-event-schema).

## <a name="set-up-the-diagnostic-settings"></a>Nastavte diagnostické nastavenia

### <a name="prerequisites"></a>Požiadavky

Ak chcete nakonfigurovať diagnostiku v Customer Insights, musia byť splnené tieto predpoklady:

- Máte aktívny [Azure predplatné](https://azure.microsoft.com/pricing/purchase-options/pay-as-you-go/).
- Máš [správca](permissions.md#admin) povolenia v Customer Insights.
- Máte **Prispievateľ** a **Administrátor prístupu používateľov** rolu na cieľovom prostriedku v Azure. Zdrojom môže byť Azure Data Lake Storage účet, centrum udalostí Azure alebo pracovný priestor Azure Log Analytics. Ďalšie informácie nájdete v časti [Pridajte alebo odstráňte priradenia rolí Azure pomocou portálu Azure](/azure/role-based-access-control/role-assignments-portal). Toto povolenie je potrebné pri konfigurácii diagnostických nastavení v Customer Insights, po úspešnom nastavení ho možno zmeniť.
- [Požiadavky na destináciu](/azure/azure-monitor/platform/diagnostic-settings#destination-requirements) pre Azure Storage, Azure Event Hub alebo Azure Log Analytics splnené.
- Máte aspoň ten **Čitateľ** rolu v skupine prostriedkov, do ktorej prostriedok patrí.

### <a name="set-up-diagnostics-with-azure-monitor"></a>Nastavte diagnostiku pomocou Azure Monitor

1. V Customer Insights vyberte **systém** > **Diagnostika** aby ste videli diagnostické ciele nakonfigurované pre túto inštanciu.

1. Vyberte **Pridať cieľ**.

   > [!div class="mx-imgBorder"]
   > ![Diagnostické pripojenie](media/diagnostics-pane.png "Diagnostické pripojenie")

1. Zadajte meno v **Názov cieľa diagnostiky** lúka.

1. Vyber **Nájomca** predplatného Azure s cieľovým prostriedkom a vyberte **Prihlásiť sa**.

1. Vyberte **Typ zdroja** (Účet úložiska, centrum udalostí alebo analýza denníkov).

1. Vyberte **Predplatné** pre cieľový zdroj.

1. Vyberte **Skupina zdrojov** pre cieľový zdroj.

1. Vyberte **Zdroj**.

1. Potvrďte **Ochrana osobných údajov a dodržiavanie predpisov** vyhlásenie.

1. Vyberte **Pripojte sa k systému** na pripojenie k cieľovému zdroju. Protokoly sa začnú objavovať v cieli po 15 minútach, ak sa používa API a generuje udalosti.

### <a name="remove-a-destination"></a>Odstráňte cieľ

1. Ísť do **systém** > **Diagnostika**.

1. V zozname vyberte cieľ diagnostiky.

1. V **Akcie** vyberte stĺpec **Odstrániť** ikonu.

1. Ak chcete zastaviť preposielanie denníka, potvrďte vymazanie. Prostriedok v predplatnom Azure sa neodstráni. Môžete si vybrať odkaz v **Akcie** otvorte Azure Portal pre vybratý prostriedok a odstráňte ho tam.

## <a name="log-categories-and-event-schemas"></a>Kategórie denníkov a schémy udalostí

V súčasnosti [Udalosti API](apis.md) a udalosti pracovného toku sú podporované a platia nasledujúce kategórie a schémy.
Logová schéma nasleduje [Bežná schéma Azure Monitor](/azure/azure-monitor/platform/resource-logs-schema#top-level-common-schema).

### <a name="categories"></a>Kategórie

Customer Insights poskytuje dve kategórie:

- **Audit udalostí** :[Udalosti API](#api-event-schema) sledovať zmeny konfigurácie v službe. `POST|PUT|DELETE|PATCH` operácie patria do tejto kategórie.
- **Prevádzkové udalosti** :[Udalosti API](#api-event-schema) alebo [udalosti pracovného toku](#workflow-event-schema) generované počas používania služby.  Napríklad,`GET` požiadavky alebo udalosti vykonávania pracovného toku.

## <a name="configuration-on-the-destination-resource"></a>Konfigurácia na cieľovom zdroji

Na základe vášho výberu typu zdroja sa automaticky použijú nasledujúce kroky:

### <a name="storage-account"></a>Storage account

Riaditeľ služby Customer Insights dostane **Prispievateľ účtu úložiska** povolenie na vybratý zdroj a vytvorí dva kontajnery pod vybratým priestorom názvov:

- `insight-logs-audit` obsahujúce **auditové udalosti**
- `insight-logs-operational` obsahujúce **prevádzkové udalosti**

### <a name="event-hub"></a>Centrum udalostí

Riaditeľ služby Customer Insights dostane **Vlastník údajov Azure Event Hubs** povolenie na zdroj a vytvorí dva Event Hubs pod vybratým menným priestorom:

- `insight-logs-audit` obsahujúce **auditové udalosti**
- `insight-logs-operational` obsahujúce **prevádzkové udalosti**

### <a name="log-analytics"></a>Log Analytics

Riaditeľ služby Customer Insights dostane **Log Analytics Contributor** povolenie na zdroj. Záznamy budú dostupné pod **Denníky** > **Tabuľky** > **Správa denníkov** vo vybranom pracovnom priestore Log Analytics. Rozbaľte **Správa denníkov** riešenie a nájdite`CIEventsAudit` a`CIEventsOperational` tabuľky.

- `CIEventsAudit` obsahujúce **auditové udalosti**
- `CIEventsOperational` obsahujúce **prevádzkové udalosti**

Pod **Dotazy** okno, rozbaľte **Audit** riešenie a nájdite príklady dotazov poskytnutých vyhľadávaním `CIEvents`.

## <a name="event-schemas"></a>Schémy udalostí

Udalosti API a udalosti workflow majú spoločnú štruktúru a detaily, kde sa líšia, viď [Schéma udalosti API](#api-event-schema) alebo [schéma udalosti pracovného toku](#workflow-event-schema).

### <a name="api-event-schema"></a>Schéma udalosti API

| Pole             | Dátový typ  | Povinné/voliteľné | Description       | Príklad        |
| ----------------- | --------- | ----------------- | --------------------- | ------------------------ |
| `time`            | Časová pečiatka | Požaduje sa          | Časová pečiatka udalosti (UTC)       | `2020-09-08T09:48:14.8050869Z`         |
| `resourceId`      | String    | Požaduje sa          | ResourceId inštancie, ktorá vyvolala udalosť         | `/SUBSCRIPTIONS/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX/RESOURCEGROUPS/<RESOURCEGROUPNAME>/`<br>`PROVIDERS/MICROSOFT.D365CUSTOMERINSIGHTS/`<br>`INSTANCES/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX`  |
| `operationName`   | String    | Požaduje sa          | Názov operácie reprezentovanej touto udalosťou.                                                                                                                | `Workflows.GetWorkFlowStatusAsync`                                                                                                                                       |
| `category`        | String    | Požaduje sa          | Kategória denníka udalosti. Zdroj môže byť buď `Operational`, alebo `Audit`. Všetky POST/PUT/PATCH/DELETE HTTP požiadavky sú označené`Audit`, všetko ostatné s`Operational` | `2020-09-08T09:48:14.8050869Z`                                                                                                                                           |
| `resultType`      | String    | Požaduje sa          | Stav udalosti. `Success`,`ClientError`,`Failure`                                                                                                        |                                                                                                                                                                          |
| `resultSignature` | String    | Voliteľné          | Stav výsledku udalosti. Ak operácia zodpovedá volaniu Rozhranie REST API, je to stavový kód HTTP.        | `200`             |
| `durationMs`      | Long      | Voliteľné          | Trvanie operácie v milisekundách.     | `133`     |
| `callerIpAddress` | String    | Voliteľné          | IP adresa volajúceho, ak operácia zodpovedá volaniu API, ktoré prichádza z verejne dostupnej IP adresy.                                                 | `144.318.99.233`         |
| `identity`        | String    | Voliteľné          | Objekt JSON popisujúci identitu používateľa alebo aplikácie, ktorá vykonala operáciu.       | Pozri [identita](#identity-schema) oddiele.     |  
| `properties`      | String    | Voliteľné          | Objekt JSON s viacerými vlastnosťami pre konkrétnu kategóriu udalostí.      | Pozri [Vlastnosti](#api-properties-schema) oddiele.    |
| `level`           | String    | Požaduje sa          | Úroveň závažnosti udalosti.    | `Informational`,`Warning`,`Error`, alebo `Critical`.           |
| `uri`             | String    | Voliteľné          | Absolútny identifikátor URI požiadavky.    |               |

#### <a name="identity-schema"></a>Schéma identity

The`identity` Objekt JSON má nasledujúcu štruktúru

```json
{
  "Authorization" : {
    "UserRole": "Admin",
    "RequiredRoles": [
      "Contributor",
      "Viewer"
      ]
    },
  "Claims" {
    "claimNameX" : "claimValueX",
    "claimNameY" : "claimValueY"
   }
}  
```

| Pole                         | Description                                                                                                                          |
| ----------------------------- | ------------------------------------------------------------------------------------------------------------------------------------ |
| `Authorization.UserRole`      | Priradená rola používateľovi alebo aplikácii. Ďalšie informácie nájdete v časti [používateľské oprávnenia](permissions.md).                                     |
| `Authorization.RequiredRoles` | Požadované roly na vykonanie operácie. `Admin` rola môže vykonávať všetky operácie.                                                    |
| `Claims`                      | Nároky používateľa alebo aplikácie webový token JSON (JWT). Vlastnosti nároku sa líšia v závislosti od organizácie a organizácie Azure Active Directory konfigurácia. |

#### <a name="api-properties-schema"></a>Schéma vlastností API

[Udalosti API](apis.md) majú nasledujúce vlastnosti.

| Pole                        | Description                                                                                                            |
| ---------------------------- | ---------------------------------------------------------------------------------------------------------------------- |
| `properties.eventType`       | Vždy`ApiEvent`, pričom udalosť protokolu sa označí ako udalosť API.                                                                 |
| `properties.userAgent`       | Agent prehliadača odosielajúci požiadavku resp `unknown`.                                                                        |
| `properties.method`          | HTTP metóda:`GET/POST/PUT/PATCH/HEAD`.                                                                                |
| `properties.path`            | Relatívna cesta žiadosti.                                                                                          |
| `properties.origin`          | URI označujúce, odkiaľ pochádza načítanie alebo `unknown`.                                                                  |
| `properties.operationStatus` | `Success` pre stavový kód HTTP < 400 <br> `ClientError` pre stavový kód HTTP < 500 <br> `Error` pre stav HTTP >= 500 |
| `properties.tenantId`        | Identifikátor organizácie                                                                                                        |
| `properties.tenantName`      | Názov organizácie.                                                                                              |
| `properties.callerObjectId`  | Azure Active Directory ObjectId volajúceho.                                                                         |
| `properties.instanceId`      | Customer Insights`instanceId`                                                                                         |

### <a name="workflow-event-schema"></a>Schéma udalosti pracovného toku

Pracovný postup obsahuje viacero krokov. [Zdroje údajov príjmu](data-sources.md),[zjednotiť](data-unification.md),[obohatiť](enrichment-hub.md) a [export](export-destinations.md) údajov. Všetky tieto kroky môžu prebiehať jednotlivo alebo organizovane s nasledujúcimi procesmi.

#### <a name="operation-types"></a>Typy operácií

| Typ operácie     | Zoskupiť                                     |
| ----------------- | ----------------------------------------- |
| Požitie         | [Zdroje dát](data-sources.md)           |
| DataPreparation   | [Zdroje dát](data-sources.md)           |
| Priradenie               | [Zjednotenie údajov](data-unification.md)   |
| Match             | [Zjednotenie údajov](data-unification.md)   |
| Zlúčenie             | [Zjednotenie údajov](data-unification.md)   |
| ProfileStore      | [Profily zákazníkov](customer-profiles.md) |
| Vyhľadávať            | [Profily zákazníkov](customer-profiles.md) |
| Aktivita          | [Aktivity](activities.md)                  |
| AttributeMeasures | [Segmenty a miery](segments.md)      |
| EntityMeasures    | [Segmenty a miery](segments.md)      |
| Miery          | [Segmenty a miery](segments.md)      |
| Segmentácia      | [Segmenty a miery](segments.md)      |
| Obohatenie        | [Obohatenie](enrichment-hub.md)                                          |
| Inteligencia      | [Predikcie](predictions-overview.md)                                          |
| AiBuilder         | [Predikcie](predictions-overview.md)                                          |
| Prehľady          | [Predikcie](predictions-overview.md)                                          |
| Export            | [Exporty](export-destinations.md)                                          |
| ModelManagement   | [Predikcie](custom-models.md)                                           |
| Vzťah      | [Zjednotenie údajov](relationships.md)                                           |

#### <a name="field-description"></a>Popis poľa

| Pole           | Dátový typ  | Povinné/voliteľné | Description                                                                                                                                                   | Príklad                                                                                                                                                                  |
| --------------- | --------- | ----------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `time`          | Časová pečiatka | Požaduje sa          | Časová pečiatka udalosti (UTC).                                                                                                                                 | `2020-09-08T09:48:14.8050869Z`                                                                                                                                           |
| `resourceId`    | String    | Požaduje sa          | ResourceId inštancie, ktorá vyvolala udalosť.                                                                                                            | `/SUBSCRIPTIONS/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX/RESOURCEGROUPS/<RESOURCEGROUPNAME>/`<br>`PROVIDERS/MICROSOFT.D365CUSTOMERINSIGHTS/`<br>`INSTANCES/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX` |
| `operationName` | String    | Požaduje sa          | Názov operácie reprezentovanej touto udalosťou. `{OperationType}.[WorkFlow|Task][Started|Completed]`. Pozri [Typy operácií](#operation-types) pre referenciu. | `Segmentation.WorkflowStarted`,<br> `Segmentation.TaskStarted`, <br> `Segmentation.TaskCompleted`, <br> `Segmentation.WorkflowCompleted`                                 |
| `category`      | String    | Požaduje sa          | Kategória denníka udalosti. Vždy`Operational` pre udalosti pracovného toku                                                                                           | `Operational`                                                                                                                                                            |
| `resultType`    | String    | Požaduje sa          | Stav udalosti. `Running`,`Skipped`,`Successful`,`Failure`                                                                                            |                                                                                                                                                                          |
| `durationMs`    | Long      | Voliteľné          | Trvanie operácie v milisekundách.                                                                                                                    | `133`                                                                                                                                                                    |
| `properties`    | String    | Voliteľné          | Objekt JSON s viacerými vlastnosťami pre konkrétnu kategóriu udalostí.                                                                                        | Pozri podsekciu [Vlastnosti pracovného postupu](#workflow-properties-schema)                                                                                                       |
| `level`         | String    | Požaduje sa          | Úroveň závažnosti udalosti.                                                                                                                                  | `Informational`, `Warning` alebo `Error`                                                                                                                                   |
|                 |

#### <a name="workflow-properties-schema"></a>Schéma vlastností pracovného toku

Udalosti pracovného toku majú nasledujúce vlastnosti.

| Pole              | Workflow | Úloha | Description            |
| ------------------------------- | -------- | ---- | ----------- |
| `properties.eventType`                       | Áno      | Áno  | Vždy`WorkflowEvent`, čím sa udalosť označí ako udalosť pracovného toku.                                                                                                                                                                                                |
| `properties.workflowJobId`                   | Áno      | Áno  | Identifikátor behu pracovného toku. Všetky udalosti pracovného toku a úloh v rámci vykonávania pracovného toku majú rovnaké `workflowJobId`.                                                                                                                                   |
| `properties.operationType`                   | Áno      | Áno  | Identifikátor prevádzky, viď [Typy operácií](#operation-types).                                                                                                                                                                               |
| `properties.tasksCount`                      | Áno      | No   | Iba pracovný postup. Počet úloh, ktoré pracovný tok spúšťa.                                                                                                                                                                                                       |
| `properties.submittedBy`                     | Áno      | No   | Voliteľné. Iba udalosti pracovného toku. The Azure Active Directory [objectId používateľa](/azure/marketplace/find-tenant-object-id#find-user-object-id) kto spustil pracovný tok, pozri tiež `properties.workflowSubmissionKind`.                                   |
| `properties.workflowType`                    | Áno      | No   | `full` alebo`incremental` Obnoviť.                                                                                                                                                                                                                            |
| `properties.workflowSubmissionKind`          | Áno      | No   | `OnDemand` alebo `Scheduled`.                                                                                                                                                                                                                                  |
| `properties.workflowStatus`                  | Áno      | No   | `Running` alebo `Successful`.                                                                                                                                                                                                                                 |
| `properties.startTimestamp`                  | Áno      | Áno  | Časová pečiatka UTC`yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.endTimestamp`                    | Áno      | Áno  | Časová pečiatka UTC`yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.submittedTimestamp`              | Áno      | Áno  | Časová pečiatka UTC`yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.instanceId`                      | Áno      | Áno  | Customer Insights`instanceId`                                                                                                                                                                                                                              |  
| `properties.identifier`                      | No       | Áno  | - Pre typ operácie =`Export`, identifikátor je vodítkom pre konfiguráciu exportu. <br> - Pre typ operácie =`Enrichment`, je to vodca obohatenia <br> - Pre typ operácie`Measures` a`Segmentation`, identifikátorom je názov entity. |
| `properties.friendlyName`                    | No       | Áno  | Užívateľsky prívetivý názov exportu alebo entity, ktorá sa spracováva.                                                                                                                                                                                           |
| `properties.error`                           | No       | Áno  | Voliteľné. Chybová správa s ďalšími podrobnosťami.                                                                                                                                                                                                                  |
| `properties.additionalInfo.Kind`             | No       | Áno  | Voliteľné. Pre typ operácie`Export` iba. Identifikuje typ exportu. Ďalšie informácie nájdete v časti [prehľad exportných destinácií](export-destinations.md).                                                                                          |
| `properties.additionalInfo.AffectedEntities` | No       | Áno  | Voliteľné. Pre typ operácie`Export` iba. Obsahuje zoznam nakonfigurovaných entít v exporte.                                                                                                                                                            |
| `properties.additionalInfo.MessageCode`      | No       | Áno  | Voliteľné. Pre typ operácie`Export` iba. Podrobná správa pre export.                                                                                                                                                                                 |
| `properties.additionalInfo.entityCount`      | No       | Áno  | Voliteľné. Pre typ operácie`Segmentation` iba. Označuje celkový počet členov segmentu.                                                                                                                                                    |
