---
title: Začíname pracovať so systémom Dynamics 365 Customer Insights
description: Prehľad zdrojov Customer Insights pomáha rýchlo začať.
ms.reviewer: mhart
ms.author: mhart
author: m-hartmann
ms.date: 08/31/2021
ms.subservice: audience-insights
ms.topic: conceptual
ms.manager: shellyha
ms.custom: intro-internal
searchScope:
- ci-home
- customerInsights
ms.openlocfilehash: 6d23552687530fddf42418b924571dddc0209e69
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 04/27/2022
ms.locfileid: "8643229"
---
# <a name="get-started-with-dynamics-365-customer-insights"></a>Začíname pracovať so systémom Dynamics 365 Customer Insights

Customer Insights vám môže pomôcť lepšie porozumieť vašim zákazníkom. Prepojte údaje z rôznych transakčných, behaviorálnych a observačných zdrojov a vytvorte 360-stupňový pohľad na zákazníka. Tieto informácie použite na získanie skúseností a procesov zameraných na zákazníka. Zjednoťte a pochopte údaje zákazníkov a využite ich na získavanie inteligentných prehľadov a akcií.

## <a name="step-1-create-an-environment"></a>Krok 1: Vytvorenie prostredia

Začnite vytvorením prostredia, kde budete pracovať. Ak si už vaša organizácia kúpila licenciu, pozrite si časť [Vytvorenie prostredia](create-environment.md). Ak chcete spustiť skúšobnú verziu Customer Insights, pozrite si časť [Nastavte skúšobné prostredie](trial-signup.md). 

## <a name="step-2-explore-customer-insights"></a>Krok 2: Preskúmajte štatistiky zákazníka

Pri prvom prihlásení do Customer Insights môžete nakonfigurovať nastavenia a preskúmať produkt.

1. [prihláste sa do Customer Insights](https://home.ci.ai.dynamics.com) pomocou vášho Microsoft Azure Active Directory (AAD) používateľský účet.

1. [Zmeňte prostredie](manage-environments.md#switch-environments) zobraziť ukážkové údaje a [preskúmať Customer Insights](home.md).

##  <a name="step-3-ingest-unify-and-set-up-relationships-for-your-data"></a>Krok 3: Prijímajte, zjednoťte a nastavte vzťahy pre svoje údaje

Zjednotené profily sú základom na získanie prehľadov a vykonávanie akcií týkajúcich sa údajov. Dajte dokopy údaje z rôznych zdrojov a zjednocovanie údajov, aby ste nakombinovali zjednotené profily. Určte vzťahy medzi prijatými entitami a použite funkcie obohatenia, aby ste informácie pridali do profilov. 

1. Prijímajte údaje vytváraním zdrojov údajov z viacerých možností. Vyberte si medzi [Power Query konektory](connect-power-query.md), a [Priečinok Common Data Model](connect-common-data-model.md), alebo [Microsoft Dataverse](connect-dataverse-managed-lake.md). 

1. Spustite [ proces zjednocovania údajov](data-unification.md) tak, že prejdete fázami [ mapovania](map-entities.md),[ zhody](match-entities.md) a[ zlúčenia](merge-entities.md).

1. Zoznámte sa s [entitami, ktoré systém vytvára](entities.md) a vytvorte [vzťahy medzi prijatými entitami ](relationships.md).
    
## <a name="step-4-enhance-unified-profiles-with-predictions-activities-and-measures"></a>Krok 4: Vylepšite zjednotené profily predpoveďami, aktivitami a opatreniami

Vďaka nastaveniu zjednotených profilov môžete vylepšiť svoje údaje a ďalej zvýšiť informácie, ktoré poskytujú.

1. Vyberte si zo zväčšujúcej sa knižnice poskytovateľov obohatenia a[ obohaťte údaje o svojich zákazníkoch ](enrichment-hub.md).

1. Použite[ hotové modely](predictions-overview.md) na predpovedanie pravdepodobnosti odchodu predplatiteľov alebo očakávaných výnosov.

1. [Nakonfigurujte aktivity](activities.md) podľa prijatých údajov a vizualizujte interakcie so svojimi zákazníkmi chronologicky na časovej osi. 

1. [Vytvorte opatrenia](measures.md) na meranie vašich obchodných cieľov a KPI.
 
## <a name="step-5-create-segments-and-activate-data-through-various-export-options"></a>Krok 5: Vytvárajte segmenty a aktivujte údaje rôznymi možnosťami exportu

Keď sú teraz vaše údaje kompletné a obsahujú široký rozsah informácií o vašich zákazníkoch, je čas hľadať spôsoby, ako podľa týchto údajov konať. 

1. [Vytvárajte segmenty](segments.md), podmnožiny vašej zákazníckej základne, aby ste zaistili, že je vaša činnosť relevantná pre cieľových zákazníkov.

1. Prezrite si rozširujúci sa katalóg[ možností exportu](export-destinations.md) kde môžete využiť informácie o zákazníkoch. Informácie môžete napríklad použiť na správu propagačných materiálov a na kontakt s digitálnym marketingom.

1. Pozrite si možnosti integrácie, napríklad do iných aplikácií Dynamics 365 s [Doplnok Zákazníckej karty](customer-card-add-in.md).  


[!INCLUDE [footer-include](includes/footer-banner.md)]