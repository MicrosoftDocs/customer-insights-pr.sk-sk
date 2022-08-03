---
title: Schémy entít v modeli Common Data Model
description: Pracujte s entitami vo formáte Common Data Model.
ms.date: 08/13/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: cc65314f1b083694b60ac0a2625bea906be7272b
ms.sourcegitcommit: ad74ace653db9a25fce4343adef7db1c9b0d8904
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 07/21/2022
ms.locfileid: "9183512"
---
# <a name="entity-schemas-in-common-data-model"></a>Schémy entít v modeli Common Data Model

Model [Common Data Model](/common-data-model/) je deklaratívna špecifikácia a definícia štandardných entít, ktoré predstavujú bežne používané koncepcie a aktivity v rôznych podnikových a produkčných aplikáciách. Tento model sa rozširuje aj na pozorovacie a analytické údaje. Model Common Data Model poskytuje jasne definované, modulárne a rozšíriteľné obchodné entity, ako napríklad Obchodný vzťah, Obchodná jednotka, Prípad, Kontakt, Potenciálny zákazník, Príležitosť a Produkt, ako aj interakcie s dodávateľmi, pracovníkmi a klientami, ako napríklad aktivity a zmluvy o úrovni služieb. Ktokoľvek môže budovať a rozširovať definície formátu Common Data Model s cieľom zaznamenávať ďalšie konkrétne obchodné nápady.

Toto je zdieľaný dátový model, ktorý umožňuje aplikáciám a integrátorom údajom ľahšiu spoluprácu vďaka tomu, že poskytuje jednotnú definíciu údajov. Model Common Data Model obsahuje bohatý systém metaúdajov so štandardnými entitami, vzťahmi, hierarchiami, vlastnosťami a ďalšími. Pochádza z aplikácií systému Dynamics 365 a má otvorený zdroj na serveri GitHub s viac ako 260 štandardnými entitami. Veľký systém interných a externých partnerov prispieva modelu Common Data Model priemyselnými konceptmi.

Common Data Model dnes implementuje viacero systémov a platforiem vrátane tokov údajov v službe Power BI a dátových služieb Azure. Je to už podporované v službe Microsoft Dataverse, Dynamics 365,Power Apps,Power BI a v nadchádzajúcich dátových službách Azure, s priamym získavaním hodnôt smerom k dátovému modelu [Open Data Initiative ](https://dynamics.microsoft.com/en-us/open-data-initiative/).

## <a name="customer-insights-entity-schemas"></a>Schémy entít pre Customer Insights

Aby sme získali 360-stupňový pohľad na zákazníka a sprístupnili modely Customer Insights v modeli Common Data Model na rozšírenie, zverejnili sme nasledujúce schémy entít:

| Entita | Opis |
|---------|---------|
|[CustomerActivity](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customeractivity) | Činnosť vykonávaná používateľom, ktorá má pre firmu pozorovaciu hodnotu. |
|[CustomerProfile](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customerprofile) | Osoba alebo organizácia, ktorá buď vykonáva obchodné aktivity, alebo má potenciál sa do nich zapojiť. |
|[MeasureDefinition](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/measuredefinition) | Definícia kľúčových ukazovateľov výkonu rozdelených podľa nulových alebo viacerých dimenzií (ako napr. Mesačný počet aktívnych používateľov, Celková útrata zákazníka či Priemerné náklady na získanie zákazníka) |
|[Segment](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/segment) | Definuje skupinu členov so spoločnými črtami. |
|[SegmentMembership](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/segmentmembership) | Členovia, ktorí sa podieľajú na danom segmente. |

Ďalšie informácie nájdete v dokumentácii o časti [Schémy entít pre Customer Insights v modeli Common Data Model](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/overview).

## <a name="view-entities-using-the-common-data-model-entity-navigator"></a>Zobrazte entít pomocou Navigátora entít formátu Common Data Model

Zobraziť entity v [Common Data Model Entity Navigator](https://microsoft.github.io/CDM/). Vyberte entitu v sekcii Aplikácia Insights, aby ste získali zoznam entít Customer Insights a ich definície.

:::image type="content" source="media/CDM-entity-navigator.png" alt-text="Navigátor entít CDM zobrazuje entitu CustomerActivity.":::

[!INCLUDE [footer-include](includes/footer-banner.md)]
