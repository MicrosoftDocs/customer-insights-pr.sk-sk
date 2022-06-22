---
title: Začíname pracovať so systémom Dynamics 365 Customer Insights
description: Prehľad Customer Insights pomáha zdrojom rýchlo začať.
ms.reviewer: v-wendysmith
ms.author: mhart
author: m-hartmann
ms.date: 04/12/2022
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.custom: intro-internal
searchScope:
- ci-home
- customerInsights
ms.openlocfilehash: 1c925110f40319df77940d1c32f24a99504d6ec6
ms.sourcegitcommit: 5e26cbb6d2258074471505af2da515818327cf2c
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 06/14/2022
ms.locfileid: "9011998"
---
# <a name="get-started-with-dynamics-365-customer-insights"></a>Začíname pracovať so systémom Dynamics 365 Customer Insights

Customer Insights vám môže pomôcť lepšie porozumieť vašim zákazníkom. Prepojte údaje z rôznych transakčných, behaviorálnych a observačných zdrojov a vytvorte 360-stupňový pohľad na zákazníka. Tieto informácie použite na získanie skúseností a procesov zameraných na zákazníka. Zjednoťte a pochopte údaje zákazníkov a využite ich na získavanie inteligentných prehľadov a akcií.

## <a name="step-1-create-an-environment"></a>Krok 1: Vytvorenie prostredia

Najprv vytvorte prostredie na prácu. Ak si už vaša organizácia kúpila licenciu, pozrite si časť [Vytvorenie prostredia](create-environment.md). Ak chcete spustiť skúšobnú verziu Customer Insights, pozrite si časť [Nastavte skúšobné prostredie](trial-signup.md).

## <a name="step-2-explore-customer-insights"></a>Krok 2: Preskúmajte štatistiky zákazníka

Pri prvom prihlásení do Customer Insights nakonfigurujte nastavenia a preskúmajte produkt.

1. [prihláste sa do Customer Insights](https://home.ci.ai.dynamics.com) pomocou vášho Microsoft Azure Active Directory (AAD) používateľský účet.

1. Zmeňte prostredie, aby ste videli demo údaje a [preskúmať Customer Insights](home.md).

## <a name="step-3-ingest-unify-and-set-up-relationships-for-your-data"></a>Krok 3: Prijímajte, zjednoťte a nastavte vzťahy pre svoje údaje

Zjednotené profily sú základom na získanie prehľadov a vykonávanie akcií týkajúcich sa údajov. Dajte dokopy údaje z rôznych zdrojov a zjednocovanie údajov, aby ste nakombinovali zjednotené profily. Zadajte vzťahy medzi prijatými entitami a použite funkcie obohatenia na pridanie informácií do profilov.

1. Prijímajte údaje vytváraním zdrojov údajov z viacerých možností. Vyberte si medzi [Azure Data Lake Storage vrátane spoločného dátového modelu](connect-common-data-model.md),[Azure Synapse Analytics](connect-synapse.md),[Microsoft Dataverse](connect-dataverse-managed-lake.md), alebo [Power Query konektory](connect-power-query.md).

1. Spustite [proces zjednotenia údajov](data-unification.md) identifikáciou [zdrojové polia](map-entities.md), odstránenie [duplikáty](remove-duplicates.md),[zodpovedajúce podmienky](match-entities.md) a [zjednocujúce polia](merge-entities.md).

1. Zoznámte sa s [entitami, ktoré systém vytvára](entities.md) a vytvorte [vzťahy medzi prijatými entitami ](relationships.md).

## <a name="step-4-enhance-unified-profiles-with-predictions-activities-and-measures"></a>Krok 4: Vylepšite zjednotené profily predpoveďami, aktivitami a opatreniami

S nastavením zjednotených profilov vylepšite svoje údaje a ďalej rozšírte informácie, ktoré poskytujú.

1. Vyberte si zo zväčšujúcej sa knižnice poskytovateľov obohatenia a[ obohaťte údaje o svojich zákazníkoch ](enrichment-hub.md).

1. Použite[ hotové modely](predictions-overview.md) na predpovedanie pravdepodobnosti odchodu predplatiteľov alebo očakávaných výnosov.

1. [Nakonfigurujte aktivity](activities.md) podľa prijatých údajov a vizualizujte interakcie so svojimi zákazníkmi chronologicky na časovej osi.

1. [Vytvorte opatrenia](measures.md) na meranie vašich obchodných cieľov a KPI.

## <a name="step-5-create-segments-and-activate-data-through-various-export-options"></a>Krok 5: Vytvárajte segmenty a aktivujte údaje rôznymi možnosťami exportu

Teraz, keď sú vaše údaje úplné a obsahujú širokú škálu informácií o vašich zákazníkoch, hľadajte spôsoby, ako s týmito údajmi podniknúť kroky.

1. [Vytvárajte segmenty](segments.md), podmnožiny vašej zákazníckej základne, aby ste zaistili, že je vaša činnosť relevantná pre cieľových zákazníkov.

1. Prezrite si rozširujúci sa katalóg[ možností exportu](export-destinations.md) kde môžete využiť informácie o zákazníkoch. Informácie môžete napríklad použiť na správu propagačných materiálov a na kontakt s digitálnym marketingom.

1. Pozrite si možnosti integrácie, napríklad do iných aplikácií Dynamics 365 s [Doplnok Zákazníckej karty](customer-card-add-in.md).  


[!INCLUDE [footer-include](includes/footer-banner.md)]
