---
title: Prírastkové obnovenie pre zdroje údajov založené na doplnku Power Query
description: Obnovenie nových a aktualizovaných údajov pre veľké zdroje údajov na základe Power Query.
ms.date: 12/06/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.openlocfilehash: f614d701aeb06720a60b14549a7fe666f8fe0617
ms.sourcegitcommit: 11b343f6622665251ab84ae39ebcd91fa1c928ca
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 12/08/2021
ms.locfileid: "7900304"
---
# <a name="incremental-refresh-for-data-sources-based-on-power-query"></a>Prírastkové obnovenie pre zdroje údajov založené na Power Query

Tento článok popisuje, ako nakonfigurovať prírastkové obnovenie pre zdroje údajov na základe Power Query.

Prírastkové obnovenie pre zdroje údajov poskytuje nasledujúce výhody:

- **Rýchlejšie obnovenie** – Obnovia sa iba údaje, ktoré sa zmenili. Môžete napríklad obnoviť iba posledných päť dní historického súboru údajov.
- **Zvýšená spoľahlivosť** – Pri menších aktualizáciách nemusíte udržiavať pripojenia k systémom pohyblivých zdrojov tak dlho, aby ste znížili riziko problémov s pripojením.
- **Znížená spotreba zdrojov** – Obnovenie iba podskupiny vašich celkových údajov vedie k efektívnejšiemu využívaniu výpočtových zdrojov a znižuje environmentálnu stopu.

## <a name="configure-incremental-refresh"></a>Konfigurácia prírastkového obnovenia

Prehľady cieľových skupín umožňujú prírastkové obnovenie pre zdroje údajov importované prostredníctvom doplnku Power Query, ktoré podporujú prírastkové prijímanie. Napríklad databázy Azure SQL s poliami dátum a čas, ktoré označujú, kedy boli záznamy údajov naposledy aktualizované.

1. [Vytvorenie nového zdroja údajov na základe Power Query](connect-power-query.md).

1. Poskytnúť **názov** pre zdroj údajov.

1. Vyberte zdroj údajov, ktorý podporuje prírastkové obnovenie, ako napr [SQL databáza Azure](/power-query/connectors/azuresqldatabase).

1. Vyberte entity alebo tabuľky, ktoré chcete prijať.

1. Dokončite kroky transformácie a vyberte položku **Ďalej**.

1. V dialógovom okne **Nastaviť prírastkové obnovovanie** zvoľte možnosť **Nastaviť**, čím sa otvorí **Nastavenia prírastkového obnovovania**. Ak zvolíte možnosť **Preskočiť**, zdroj údajov obnoví celú množinu údajov.
   > [!TIP]
   > Prírastkové obnovenie môžete použiť aj neskôr úpravou existujúceho zdroja údajov.

1. V časti **Nastavenia prírastkového obnovovania** nakonfigurujete prírastkové obnovovanie pre všetky entity, ktoré ste si vybrali pri vytváraní zdroja údajov.

   :::image type="content" source="media/incremental-refresh-settings.png" alt-text="Nakonfigurujte entity v zdroj údajov na prírastkové obnovovanie.":::

1. Vyberte entitu a zadajte nasledujúce podrobnosti:

   - **Definujte primárny kľúč**: Vyberte primárny kľúč pre entitu alebo tabuľku.
   - **Definujte pole Naposledy aktualizované**: Toto pole zobrazí iba atribúty typu dátum alebo čas. Vyberte atribút, ktorý označuje, kedy boli záznamy naposledy aktualizované. Bude sa používať na identifikáciu záznamov, ktoré spadajú do časového rámca prírastkovej obnovy.
   - **Vyhľadávať aktualizácie s frekvenciou**: Zadajte, ako dlho chcete, aby bol časový rámec prírastkového obnovovania.

1. Stlačte možnosť **Uložiť** na dokončenie vytvorenia zdroja údajov. Počiatočná obnova dát bude úplne obnovená. Potom sa prírastkové obnovenie údajov uskutoční tak, ako bolo nakonfigurované v predchádzajúcom kroku.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
