---
title: Začíname s firemnými obchodnými vzťahmi ako s primárnou cieľovou skupinou
description: Prečítajte si o firemných obchodných vzťahoch ako o primárnej cieľovej skupine Dynamics 365 Customer Insights.
ms.date: 10/19/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.custom: intro-internal
ms.author: wimohabb
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: fb943a91154e913c85c40fbf6077c171e9240ac5
ms.sourcegitcommit: bb1ca84bc38e81fb2ff2961c457384b7beb5b5fa
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 01/15/2022
ms.locfileid: "7977940"
---
# <a name="work-with-business-accounts-in-audience-insights"></a>Pracujte s firemnými obchodnými vzťahmi v prehľadoch cieľových skupín

Funkcia prehľadov cieľových skupín v Dynamics 365 Customer Insights umožňuje konfigurovať prostredie pre rôzne primárne cieľové skupiny: individuálnych spotrebiteľov (firma a spotrebiteľ) a firemné obchodné vzťahy (firma a firma). V scenároch „firma a spotrebiteľ“ sú údaje sústredené okolo jednotlivcov. Pri scenároch „firma a firma“ sú primárnou cieľovou skupinou obchodné vzťahy – organizácie alebo spoločnosti – a kontakty. Tento článok vám pomôže začať s prostredím pre firemné obchodné vzťahy. Uvádza rozdiely v oblastiach funkcií v prehľadoch cieľových skupín v závislosti od zamerania vášho prostredia. Ak chcete získať ďalšie informácie o rozdieloch, prečítajte si dokumenty o oblastiach funkcií. 

## <a name="create-an-environment-for-business-accounts"></a>Vytvorenie prostredia pre firemné obchodné vzťahy

Správcovia môžu [vytvoriť prostredie v existujúcej organizácii](create-environment.md). Krok v procese vytvárania nového prostredia požaduje od správcov primárnu cieľovú skupinu daného prostredia. V prípade, že ide o počiatočné nastavenie prehľadov cieľovej skupiny po zakúpení licencie, sprievodca vám pomôže s vytvorením prvého prostredia.

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

