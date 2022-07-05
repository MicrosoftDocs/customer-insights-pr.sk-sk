---
title: Práca s firemnými obchodnými vzťahmi
description: Získajte informácie o firemných účtoch ako primárnom cieľovom publiku v Dynamics 365 Customer Insights.
ms.date: 10/19/2021
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.custom: intro-internal
ms.author: wimohabb
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-semantic-mapping
- ci-connections
- customerInsights
ms.openlocfilehash: 9bf91671b744198b2f37391edc7abf58eca3c820
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 06/29/2022
ms.locfileid: "9053132"
---
# <a name="work-with-business-accounts"></a>Práca s firemnými obchodnými vzťahmi

The Dynamics 365 Customer Insights vám umožňuje nakonfigurovať vaše prostredie pre rôzne primárne cieľové skupiny: individuálnych spotrebiteľov (B-to-C) a obchodné účty (B-to-B). V scenároch „firma a spotrebiteľ“ sú údaje sústredené okolo jednotlivcov. Pri scenároch „firma a firma“ sú primárnou cieľovou skupinou obchodné vzťahy – organizácie alebo spoločnosti – a kontakty. Tento článok vám pomôže začať s prostredím pre firemné obchodné vzťahy. Uvádza rozdiely pre oblasti funkcií v Customer Insights v závislosti od zamerania vášho prostredia. Ak chcete získať ďalšie informácie o rozdieloch, prečítajte si dokumenty o oblastiach funkcií. 

## <a name="create-an-environment-for-business-accounts"></a>Vytvorenie prostredia pre firemné obchodné vzťahy

Správcovia môžu [vytvoriť prostredie v existujúcej organizácii](create-environment.md). Krok v procese vytvárania nového prostredia požaduje od správcov primárnu cieľovú skupinu daného prostredia. V prípade, že ide o prvotné nastavenie po zakúpení licencie, s vytvorením prvého prostredia vám pomôže riadená skúsenosť.

Potom môžete [prijať údaje](data-sources.md) pre firemné obchodné vzťahy a súvisiace kontakty ako zdroje údajov zo všetkých podporovaných zdrojov.

Po zjednotení údajov [zadajte hierarchie obchodných vzťahov](relationships.md#set-up-account-hierarchies) ako súčasť konfigurácie vzťahu. Môžete tiež [konfigurovať sémantické mapovania](semantic-mappings.md) na prepojenie entít kontaktov a obchodných vzťahov. 

## <a name="switch-between-primary-target-audience"></a>Prepínanie medzi primárnou cieľovou skupinou

Ak vaša organizácia spravuje prostredia pre individuálnych zákazníkov a firemné obchodné vzťahy, pomocou prepínača na ľavej table môžete zvoliť primárnu cieľovú skupinu.

:::image type="content" source="media/switch-primary-target-audience.png" alt-text="Prepínač na zmenu primárnej cieľovej skupiny medzi jednotlivými zákazníkmi a firemnými obchodnými vzťahmi.":::

## <a name="supported-feature-areas"></a>Podporované oblasti funkcií

- [Aktivity](activities.md): Podpora pre obchodné vzťahy a súvisiace kontakty na vytváranie aktivít a ich zobrazovanie na časovej osi.
- [Vzťahy](relationships.md): Sprievodca aktivitami pomáha vytvárať vzťahy medzi entitami, aby zobrazenie obchodného vzťahu mohlo zobrazovať všetky aktivity z kontaktov. Kontakty je možné zobraziť detailnejšie a hierarchie je možné použiť na agregáciu aktivít obchodného vzťahu.
- [Miery](measures.md): Podporuje miery vytvorené z nástroja na tvorbu mier pomocou jedného výpočtu. Voliteľné nastavenie umožňuje súhrn pre vedľajšie obchodné vzťahy pri vytváraní mier.
- [Segmenty](segments.md): Podporuje segmenty, ktoré sú vytvárané úplne od začiatku pomocou nástroja na tvorbu segmentov. Noví operátori umožňujú začlenenie hierarchie obchodných vzťahov pri vytváraní segmentov.
- [Prijímanie údajov](data-sources.md): Všetky funkcie v tejto oblasti sú rovnaké pre firemné obchodné vzťahy a individuálnych zákazníkov.
- [Zjednotenie údajov](data-unification.md): Všetky funkcie v tejto oblasti sú rovnaké pre firemné obchodné vzťahy a individuálnych zákazníkov.
- [Obohatenie](enrichment-hub.md): Niektoré typy obohatenia sú k dispozícii iba pre scenáre individuálnych zákazníkov, zatiaľ čo iné sú k dispozícii výlučne pre firemné obchodné vzťahy.
- [Predikcie a vopred pripravené modely](predictions-overview.md): Predikcia úbytku transakcií obsahuje ďalšie kroky pre firemné obchodné vzťahy. Ostatné predikcie sú k dispozícii iba pre individuálnych zákazníkov.
- [Aktivácia a export](export-destinations.md): Export je dostupný pre firemné obchodné vzťahy a individuálnych zákazníkov. Niektoré exporty vyžadujú dodatočnú konfiguráciu a kontaktné informácie projektované v príslušných segmentoch, aby boli platné pre firemné obchodné vzťahy.
- [Systémové nastavenia](system.md) a [správa používateľov](permissions.md): Všetky funkcie v tejto oblasti sú rovnaké pre firemné obchodné vzťahy a individuálnych zákazníkov.

