---
title: Skontrolujte zjednotenie údajov
description: Skontrolujte kroky zjednotenia údajov, vytvorte jednotné profily zákazníkov a skontrolujte výsledky
ms.date: 06/02/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: v-wendysmith
ms.author: adkuppa
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-match
- ci-merge
- ci-relationships
- customerInsights
ms.openlocfilehash: 0f7b2e9af65796c4d304dbd9893a21617e847620
ms.sourcegitcommit: 760fbac397c738407c7dea59297d54cae19b6f57
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 06/03/2022
ms.locfileid: "8844105"
---
# <a name="review-data-unification"></a>Skontrolujte zjednotenie údajov

[!INCLUDE [m3-prod-trial-note](includes/m3-prod-trial-note.md)]

Tento posledný krok v procese zjednotenia zobrazuje súhrn krokov v procese a poskytuje možnosť vykonať zmeny pred vytvorením zjednoteného profilu.

:::image type="content" source="media/m3_review.png" alt-text="Snímka obrazovky kontroly a vytvárania zákazníckych profilov.":::

## <a name="review-the-data-unification-steps"></a>Pozrite si kroky zjednotenia údajov

1. Vyberte **Upraviť** na ktoromkoľvek z krokov zjednotenia údajov, aby ste ich mohli skontrolovať a vykonať akékoľvek zmeny.

1. Ak ste s výberom spokojní, vyberte si **Vytvorte profily zákazníkov**. The **Zjednotiť** stránka sa zobrazí počas vytvárania jednotného zákazníckeho profilu. Všetky dlaždice okrem **Zdrojové polia** šou **Vo fronte** alebo **Osviežujúce** postavenie.

   :::image type="content" source="media/m3_unify_refreshing.png" alt-text="Snímka obrazovky stránky Zjednotiť s dlaždicami so zobrazením Zaradené do poradia alebo Obnovovanie.":::

   [!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

Dokončenie algoritmu zjednotenia nejaký čas trvá a konfiguráciu nemôžete zmeniť, kým sa nedokončí. Po dokončení procesu zjednotenia zavolá entita jednotného profilu zákazníka *Zákazník*, je uvedený na **entity** stránke v **Profily** oddiele. Prvý úspešný beh zjednotenia vytvorí zjednotené *Zákazník* subjekt. Všetky nasledujúce behy rozširujú túto entitu.

## <a name="review-the-results-of-data-unification"></a>Skontrolujte výsledky zjednotenia údajov

Po zjednotení, **Údaje** > **Zjednotiť** zobrazuje počet zjednotených zákazníckych profilov. Výsledky každého kroku v procese zjednotenia sa zobrazia na každej dlaždici. Napríklad, **Zdrojové polia** zobrazuje počet mapovaných atribútov (polí) a **Duplicitné záznamy** zobrazuje počet nájdených duplicitných záznamov.

:::image type="content" source="media/m3_unified.png" alt-text="Snímka obrazovky stránky Zjednotenie údajov po zjednotení údajov.":::

> [!TIP]
> The **Zodpovedajúce podmienky** dlaždice sa zobrazia iba vtedy, ak bolo vybratých viacero entít.

Odporúčame vám, aby ste si prezreli výsledky, najmä ich kvalitu [pravidlá zápasu](data-unification-update.md#manage-match-rules) a v prípade potreby ich upravte.

Keď treba, [vykonajte zmeny v nastaveniach zjednotenia](data-unification-update.md) a znova spustite zjednotený profil.

## <a name="next-step"></a>Ďalší krok

Konfigurovať [činnosti](activities.md),[obohatenie](enrichment-hub.md),[vzťahy](relationships.md), alebo [Opatrenia](measures.md) získať viac informácií o svojich zákazníkoch.

[!INCLUDE[footer-include](includes/footer-banner.md)]
