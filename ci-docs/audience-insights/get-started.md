---
title: Začnite funkciami prehľadov cieľovej skupiny v Dynamics 365 Customer Insights
description: Zdroje pomoci pre prehľady cieľovej skupiny pomáhajú rýchlo začať.
ms.reviewer: mhart
ms.author: mhart
author: m-hartmann
ms.date: 08/31/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: aaaf1848df175469d8af07754ac153b777781ffb
ms.sourcegitcommit: 971716c761871cee390519cacef617dac21ecd60
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 09/01/2021
ms.locfileid: "7466596"
---
# <a name="get-started-with-dynamics-365-customer-insights-audience-insights-capability"></a>Začnite funkciami prehľadov cieľovej skupiny v Dynamics 365 Customer Insights

Prehľady cieľových skupín vám môže pomôcť lepšie porozumieť vašim zákazníkom. Prepojte údaje z rôznych transakčných, behaviorálnych a observačných zdrojov a vytvorte 360-stupňový pohľad na zákazníka. Tieto informácie použite na získanie skúseností a procesov zameraných na zákazníka. Zjednoťte a pochopte údaje zákazníkov a využite ich na získavanie inteligentných prehľadov a akcií.

## <a name="step-1-create-an-environment"></a>Krok 1: Vytvorenie prostredia

Začnite vytvorením prostredia, kde budete pracovať. Ak už vaša organizácia má kúpenú licenciu, prejdite do časti [Začníname pracovať s predplatným ](get-started-paid.md). Ak chcete začať skúšobnou verziou prehľadov cieľovej skupiny, prejdite na časť [Nastavenie skúšobného prostredia](get-started-trial.md). 

## <a name="step-2-explore-audience-insights"></a>Krok 2: Preskúmajte prehľady cieľových skupín

Pri prvom prihlásení do prehľadov cieľových skupín môžete konfigurovať nastavenia a preskúmať produkt.

1. [Prihláste sa do prehľadov cieľových skupín](https://home.ci.ai.dynamics.com) pomocou svojho používateľského konta Microsoft Azure Active Directory (AAD).

1. [Zmeňte prostredie](manage-environments.md#switch-environments) a zobrazte demo údaje a[ preskúmajte prehľady cieľovej skupiny ](home.md).

##  <a name="step-3-ingest-unify-and-set-up-relationships-for-your-data"></a>Krok 3: Prijímajte, zjednoťte a nastavte vzťahy pre svoje údaje

Zjednotené profily sú základom na získanie prehľadov a vykonávanie akcií týkajúcich sa údajov. Dajte dokopy údaje z rôznych zdrojov a zjednocovanie údajov, aby ste nakombinovali zjednotené profily. Určte vzťahy medzi prijatými entitami a použite funkcie obohatenia, aby ste informácie pridali do profilov. 

1. Prijímajte údaje vytváraním zdrojov údajov z viacerých možností. Vyberte si medzi[ konektormi Power Query](connect-power-query.md), a [ priečinkom Common Data Model](connect-common-data-model.md), alebo [Microsoft Dataverse](connect-common-data-service-lake.md). 

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

1. Pozrite sa na možnosti integrácie, napríklad pomocou[ priameho spojenia s prehľadmi interakcie](../engagement-insights/integrate-audience-insights-engagement-insights.md), alebo do iných aplikácií Dynamics 365 prostredníctvom [doplnku zákazníckej karty ](customer-card-add-in.md).  


[!INCLUDE[footer-include](../includes/footer-banner.md)]
