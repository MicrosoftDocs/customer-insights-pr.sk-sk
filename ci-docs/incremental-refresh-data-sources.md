---
title: Prírastkové obnovenie pre Power Query a zdroje údajov Azure Data Lake
description: Obnovte nové a aktualizované údaje pre veľké zdroje údajov na základe Power Query alebo zdroje údajov Azure Data Lake.
ms.date: 05/30/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-system-schedule
- customerInsights
ms.openlocfilehash: de39743eb8728fac34e417724c5f73bf44309c89
ms.sourcegitcommit: 5807b7d8c822925b727b099713a74ce2cb7897ba
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 07/28/2022
ms.locfileid: "9207156"
---
# <a name="incremental-refresh-for-power-query-and-azure-data-lake-data-sources"></a>Prírastkové obnovenie pre Power Query a zdroje údajov Azure Data Lake

Prírastkové obnovenie pre zdroje údajov založené na Power Query alebo Azure Data Lake poskytuje nasledujúce výhody:

- **Rýchlejšie obnovenie** – Obnovia sa iba údaje, ktoré sa zmenili. Môžete napríklad obnoviť iba posledných päť dní historického súboru údajov.
- **Zvýšená spoľahlivosť** – Pri menších aktualizáciách nemusíte udržiavať pripojenia k systémom pohyblivých zdrojov tak dlho, aby ste znížili riziko problémov s pripojením.
- **Znížená spotreba zdrojov** – Obnovenie iba podskupiny vašich celkových údajov vedie k efektívnejšiemu využívaniu výpočtových zdrojov a znižuje environmentálnu stopu.

## <a name="configure-incremental-refresh-for-data-sources-based-on-power-query"></a>Nakonfigurujte prírastkové obnovenie pre zdroje údajov na základe Power Query

Customer Insights umožňuje prírastkové obnovenie pre zdroje údajov importované cez Power Query ktoré podporujú prírastkové požitie. Napríklad databázy Azure SQL s poliami dátum a čas, ktoré označujú, kedy boli záznamy údajov naposledy aktualizované.

1. [Vytvorte nový zdroj údajov založený na Power Query](connect-power-query.md).

1. Vyberte zdroj údajov, ktorý podporuje prírastkové obnovenie, ako napr [SQL databáza Azure](/power-query/connectors/azuresqldatabase).

1. Vyberte entity alebo tabuľky, ktoré chcete prijať.

1. Dokončite kroky transformácie a vyberte položku **Ďalej**.

1. V dialógovom okne **Nastaviť prírastkové obnovovanie** zvoľte možnosť **Nastaviť**, čím sa otvorí **Nastavenia prírastkového obnovovania**. Ak zvolíte možnosť **Preskočiť**, zdroj údajov obnoví celú množinu údajov.
   > [!TIP]
   > Prírastkové obnovenie môžete použiť aj neskôr úpravou existujúceho zdroja údajov.

1. V časti **Nastavenia prírastkového obnovovania** nakonfigurujete prírastkové obnovovanie pre všetky entity, ktoré ste si vybrali pri vytváraní zdroja údajov.

   :::image type="content" source="media/incremental-refresh-settings.png" alt-text="Nakonfigurujte nastavenia prírastkového obnovovania.":::

1. Vyberte entitu a zadajte nasledujúce podrobnosti:

   - **Definujte primárny kľúč**: Vyberte primárny kľúč pre entitu alebo tabuľku.
   - **Definujte pole Naposledy aktualizované**: Toto pole zobrazí iba atribúty typu dátum alebo čas. Vyberte atribút, ktorý označuje, kedy boli záznamy naposledy aktualizované. Bude sa používať na identifikáciu záznamov, ktoré spadajú do časového rámca prírastkovej obnovy.
   - **Vyhľadávať aktualizácie s frekvenciou**: Zadajte, ako dlho chcete, aby bol časový rámec prírastkového obnovovania.

1. Stlačte možnosť **Uložiť** na dokončenie vytvorenia zdroja údajov. Počiatočná obnova dát bude úplne obnovená. Potom sa prírastkové obnovenie údajov uskutoční tak, ako bolo nakonfigurované v predchádzajúcom kroku.

## <a name="configure-incremental-refresh-for-azure-data-lake-data-sources"></a>Nakonfigurujte prírastkové obnovenie pre zdroje údajov Azure Data Lake

Customer Insights umožňuje prírastkové obnovenie pre pripojené zdroje údajov Azure Data Lake Storage. Ak chcete použiť prírastkové prijímanie a obnovenie pre entitu, nakonfigurujte túto entitu pri pridávaní Azure Data Lake zdroj údajov alebo neskôr pri úprave zdroj údajov. Priečinok s údajmi entity musí obsahovať nasledujúce priečinky:

- **Úplné údaje** : Priečinok s dátovými súbormi obsahujúcimi počiatočné záznamy
- **IncrementalData** : Priečinok s priečinkami s hierarchiou dátumu a času **rrrr/mm/dd/hh** formát obsahujúci prírastkové aktualizácie. **hh** predstavuje hodinu UTC aktualizácií a obsahuje **Upserts** a **Vymaže** priečinky. **Upserts** obsahuje dátové súbory s aktualizáciami existujúcich záznamov alebo nových záznamov. **Vymaže** obsahuje dátové súbory so záznamami, ktoré sa majú odstrániť.

1. Pri pridávaní alebo úprave zdroj údajov prejdite na **Atribúty** panel pre entitu.

1. Skontrolujte atribúty. Uistite sa, že atribút dátumu vytvorenia alebo poslednej aktualizácie je nastavený na a *Dátum Čas* **Formát údajov** a a *Kalendár.Dátum* **Sémantický typ**. V prípade potreby upravte atribút a vyberte **hotový**.

1. Z **Vyberte položku Entity** panel, upravte entitu. The **Postupné požitie** je začiarknuté políčko.

   :::image type="content" source="media/ADLS_inc_refresh.png" alt-text="Nakonfigurujte entity v zdroj údajov na prírastkové obnovovanie.":::

   1. Prejdite do koreňového priečinka, ktorý obsahuje súbory .csv alebo .parquet, kde nájdete úplné údaje, prírastkové aktualizácie údajov a prírastkové vymazania údajov.
   1. Zadajte príponu úplných údajov a oboch prírastkových súborov (\. csv alebo\. parkety).
   1. V prípade súborov .csv vyberte oddeľovač stĺpcov a ak chcete, aby sa ako hlavička stĺpca použil prvý riadok súboru.
   1. Vyberte **Uložiť**.

1. Pre **Naposledy aktualizovaný**, vyberte atribút dátum a časová pečiatka.

1. Ak **Primárny kľúč** nie je vybratý, vyberte primárny kľúč. Primárny kľúč je atribút jedinečný pre entitu. Ak má byť atribút platným primárnym kľúčom, nemal by obsahovať duplicitné hodnoty, chýbajúce hodnoty ani nulové hodnoty. Ako primárne kľúče sú podporované atribúty typu reťazec, celé číslo a GUID.

1. Vyberte **Zavrieť** uložte a zatvorte tablu.

1. Pokračujte pridávaním alebo upravovaním zdroj údajov.

[!INCLUDE [footer-include](includes/footer-banner.md)]
