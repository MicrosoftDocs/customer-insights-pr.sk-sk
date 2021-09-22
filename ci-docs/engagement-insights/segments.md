---
title: Zobrazenie a vytváranie segmentov
description: Ako vytvárať, upravovať a mazať segmenty a kde ich používať.
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 06/09/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: cedcd58373428dd35ba29ce8fdd00007257f8fa59b0d25bc584b4e832df13604
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036167"
---
# <a name="view-and-create-segments"></a>Zobrazenie a vytváranie segmentov

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Segmenty vám umožňujú identifikovať podmnožiny návštevníkov na základe charakteristík alebo interakcií webových stránok. Segmenty vám umožňujú použiť filtre a analyzovať tieto podmnožiny. Analýza môže pomôcť preskúmať a reagovať na trendy vo vašom podnikaní. 

:::image type="content" source="media/segments-page.png" alt-text="Snímka obrazovky z aplikácie prehľadov interakcií, ktorá zobrazuje zoznam existujúcich segmentov v pracovnom priestore.":::

## <a name="view-segments"></a>Zobrazenie segmentov

1. Na ľavej navigačnej table prejdite na **Údaje**. 

1. Vyberte kartu **Segmenty** na zobrazenie zoznamu všetkých segmentov v pracovnom priestore. 

## <a name="create-a-segment"></a>Vytvoriť segment

Segmenty pozostávajú z pravidiel a podmienok, ktoré sú spojené s logickými operátormi. Podmienky použijú filtre na vybratú dimenziu. Každý segment môže používať až päť dimenzií.

Nasledujúci príklad ukazuje segment s dvoma podmienkami v jednom pravidle. Filtruje všetky udalosti webových stránok, v ktorých je prehľadávač Chrome a operačné systémy sú iOS alebo Android.

:::image type="content" source="media/segment-sample.png" alt-text="Príklad segmentov s dvoma podmienkami v pravidle na filtrovanie udalostí webu.":::

Táto časť popisuje, ako vytvoriť *prázdny segment* od začiatku.

1. Prejdite na **Údaje** > **Segmenty**.

1. Vyberte **Nový segment**.

1. V možnosti **Knižnica zdrojov** vyberte atribút, podľa ktorého chcete filtrovať. V súčasnosti môžete segmenty vytvárať iba na základe dimenzií.

1. Vyberte operátora a hodnotu pre vybraného atribútu. Nasledujúce operácie nie sú podporované.
   - **je**: vyžaduje presnú zhodu na zahrnutie hodnôt. Používa **rovná sa** pre jednu hodnotu alebo **ktorýkoľvek z** na zahrnutie viac hodnôt.
   - **nie je**: vyžaduje presnú zhodu na vylúčenie hodnôt. Používa **rovná sa** pre jednu hodnotu alebo **ktorýkoľvek z** na zahrnutie viac hodnôt.
   - **začína s**: reťazec, ktorým zodpovedajúce hodnoty začínajú.
   - **končí sa na**: reťazec, ktorým zodpovedajúce hodnoty končia.
   - **obsahuje**: reťazec obsiahnutý v zodpovedajúcich hodnotách.

1. Na pridanie ďalších podmienok do skupiny môžete použiť dva logické operátory. Pri použití množinových operátorov sa zohľadňujú projektované atribúty.
   - Operátor **A**: Obe podmienky musia byť splnené ako súčasť procesu segmentácie. Táto voľba je najužitočnejšia, keď definujete podmienky pre rôzne entity.
   - Operátor **ALEBO**: V rámci procesu segmentácie musí byť splnená jedna z podmienok. Táto voľba je najužitočnejšia, keď definujete viac podmienok pre jednu entitu.

1. Vyberte **Uložiť** a pomenujte segment. 

Segment bude uvedený na stránke Segmenty a môžete ho použiť na všetky zostavy a lieviky v pracovnom priestore.

## <a name="use-a-segment-in-a-report-or-funnel"></a>Použitie segmentu v zostave alebo lieviku

Môžete použiť segmenty na výkaz alebo lievik a filtrovať ich na základe podmienok v segmente. Segmenty však nemôžete použiť na zostavu používania v reálnom čase.

:::image type="content" source="media/segment-reports-filter.png" alt-text="Zostava zobrazení stránky s rozšíreným rozbaľovacím zoznamom, v ktorom môžete zvoliť, ktoré segmenty sa majú použiť.":::

Ak chcete použiť segment, otvorte zostavy alebo lievik. Vyberte **Pridať podmienku** a následne **Filtrovať podľa segmentu**. Zo zoznamu vyberte segment, ktorý chcete použiť. Segment sa použije na zostavu. Ak graf nepodporuje segment, zobrazí sa chyba.
 
Môžete použiť *až do troch segmentov* na zostavu alebo lievik.

## <a name="edit-a-segment"></a>Úprava segmentu

1. Prejdite na **Údaje** > **Segmenty**.
1. Vyberte segment v zozname a otvorte ho. 
1. Podľa potreby zmeňte alebo pridajte hodnoty.
1. Zmeny vykonajte výberom položky **Uložiť**.

## <a name="change-the-name-of-a-segment"></a>Zmena názvu segmentu

1. Prejdite na **Údaje** > **Segmenty**.
1. V zozname segmentov vyberte **Viac [...]**. 
1. Z rozbaľovacieho zoznamu si vyberte možnosť **Upraviť názov**.
1. Zadajte nový názov a vyberte možnosť **Premenovať**.

## <a name="delete-a-segment"></a>Odstránenie segmentu

1. Prejdite na **Údaje** > **Segmenty**.
1. V zozname segmentov vyberte **Viac [...]**. 
1. Z rozbaľovacieho zoznamu si vyberte možnosť **Odstrániť**.
1. Na potvrdenie vyberte položku **Odstrániť**.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
