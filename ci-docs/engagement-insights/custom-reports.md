---
title: Informácie o vlastných zostavách
description: Zistite ako si vytvoriť vlastné zostavy.
author: mochimochi016
ms.reviewer: mhart
ms.author: jefhar
ms.date: 10/01/2021
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: e8cdfc07b67b78febc1d50b3b1fd44ab94448e64
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 02/16/2022
ms.locfileid: "8232167"
---
# <a name="create-and-edit-custom-reports"></a>Vytvorenie a úprava vlastných zostáv

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Okrem predpripravených zostáv (OOB) môžete vytvoriť aj vlastnú zostavu s vizualizáciami grafov a tabuliek, ktoré vám pomôžu porozumieť správaniu používateľov. Tento článok vysvetľuje, ako vytvoriť prehľad s údajmi, ktoré potrebujete, pomocou vizualizácií tabuľky a grafu. Informácie o zostavách OOB nájdete v časti [Zobrazenie zostáv](view-reports.md).

## <a name="create-a-custom-report"></a>Vytvorenie vlastnej zostavy

1. Prejdite do **Analyzovať** > **Vlastné** a získajte prístup k zoznamu vlastných prehľadov.

1. Stlačte možnosť **Nová zostava** a začnite vytvárať vlastný prehľad.

   :::image type="content" source="media/new-custom-report.png" alt-text="Nové vlastné zostavy.":::

1. Rozhodnite o type zostavy, ktorú chcete vytvoriť:

    - Stlačte možnosť **Pridá vizuálny prvok** na paneli príkazov a vytvorte predvolenú vizualizáciu tabuľky.
    - Alebo vyberte z vizualizácie stĺpec, pruh, riadok, plochu, koláč, šišku alebo tabuľku z tably **Editor zostáv**.

1. V sekcii **Údaje** na table **Editor vizualizácie** vyberte jednu z dostupných možností (napríklad zobrazenia stránky) z rozbaľovacieho zoznamu **Metriky**. Môžete tiež pridať **Dimenzie** (napríklad krajina), ktoré sa majú zobraziť na vizualizácii. Ďalšie informácie nájdete v časti [Zobrazenie a tvorba metrík](metrics.md) a [Zobrazenie a tvorba dimenzií](dimensions.md).

   :::image type="content" source="media/page-views.png" alt-text="Vyberte metriku pre svoju zostavu.":::

1. Vyberte sekciu **Dizajn** tably **Editor vizualizácie** na pridanie **Textu nadpisu** a zapnite/vypnite **Nadpis**.  Typ vizualizácie môžete tiež zmeniť výberom iného grafu, ako napr. **koláčový graf**.

1. Ak chcete zmeniť veľkosť a polohu vizualizácie:
   - Vyberte vizualizáciu a potom potiahnutím jedného z rohov alebo okrajov upravte jeho veľkosť.
   - Vyberte vizualizáciu a presuňte ju na nové miesto. Na zmenu polohy môžete tiež použiť klávesy so šípkami.
1. Na pridanie ďalšej vizualizácie stlačte možnosť **Pridať vizuálny prvok** v príkazovom riadku.
1. Po pridaní požadovaných vizualizácií do prehľadu stlačte možnosť **Uložiť** na paneli príkazov.

1. Zadajte názov vlastného prehľadu a stlačte možnosť **Uložiť**, aby sa vytvoril.
 
## <a name="filter-a-custom-report"></a>Filtrovanie vlastnej zostavy

Môžete vybrať časový rámec alebo rozsah dátumov vo vlastnej zostave, aby ste sa zamerali na hodnotu alebo časové obdobie.

Ak chcete vybrať časový rámec, v pravom hornom rohu zobrazenia zostavy vyberte hodnotu z rozbaľovacieho zoznamu zostavy. Môžete si tiež vybrať *Pevný rozsah dátumov*.

:::image type="content" source="media/filter-time-date-range.png" alt-text="Filtrovanie podľa času alebo rozsahu dátumov.":::

Pre väčšinu zostáv vyberte **+ Pridať podmienku**, na výber dimenzie alebo segmentu na filtrovanie zostavy. Ďalšie informácie nájdete v téme [Zobrazenie a vytváranie segmentov](segments.md).

## <a name="edit-a-custom-report"></a>Úprava vlastnej zostavy

1. Prejdite do **Analyzovať** > **Vlastné** a získajte prístup k zoznamu vlastných prehľadov.

1. V zozname vlastných zostáv vyberte možnosť **Viac [...]** 

1. Vyberte **Upraviť názov** na zmenu názvu zostavy.

1. Vyberte názov zostavy a použite možnosti **+ Pridať vizuálny prvok** a **Upraviť** na pridanie, odstránenie, premiestnenie alebo zmenu veľkosti vizualizácií.

1. Ak chcete zmeniť vlastnosti vizualizácie, vyberte vizualizáciu, zvoľte **...** a potom **Upraviť vizualizáciu**.

   :::image type="content" source="media/edit-visual-control.png" alt-text="Úpravy vlastností grafu pre vlastné prehľady.":::

1. Po úprave zostavy stlačte možnosť **Uložiť**, čím svoje zmeny použijete. 

## <a name="delete-a-custom-report"></a>Odstránenie vlastnej zostavy

1. Prejdite do **Analyzovať** > **Vlastné** a získajte prístup k zoznamu vlastných prehľadov.

1. V zozname vlastných zostáv vyberte možnosť **...**

1. Stlačte možnosť **Odstrániť** a odstráňte zostavu.

1. Ak chcete prehľad natrvalo odstrániť, potvrďte odstránenie.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
