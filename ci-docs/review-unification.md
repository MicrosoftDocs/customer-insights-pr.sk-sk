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
ms.openlocfilehash: 20728ffaef9bb705410b3ac22d19868ffd5d1243
ms.sourcegitcommit: 3c5b0b40b2b45e420015bbdd228ce0e610245e6f
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 07/12/2022
ms.locfileid: "9139603"
---
# <a name="review-data-unification"></a>Skontrolujte zjednotenie údajov

Tento posledný krok v procese zjednotenia zobrazuje súhrn krokov v procese a poskytuje možnosť vykonať zmeny pred vytvorením zjednoteného profilu.

:::image type="content" source="media/m3_review.png" alt-text="Snímka obrazovky kontroly a vytvárania zákazníckych profilov.":::

## <a name="review-the-data-unification-steps"></a>Pozrite si kroky zjednotenia údajov

1. Vyberte **Upraviť** na ktoromkoľvek z krokov zjednotenia údajov, aby ste ich mohli skontrolovať a vykonať akékoľvek zmeny.

1. Ak ste s výberom spokojní, vyberte si **Vytvorte profily zákazníkov**. The **Zjednotiť** počas vytvárania jednotného zákazníckeho profilu. Všetky dlaždice okrem **Zdrojové polia** šou **Vo fronte** alebo **Osviežujúce** postavenie.

   :::image type="content" source="media/m3_unify_refreshing.png" alt-text="Snímka obrazovky stránky Zjednotiť s dlaždicami so zobrazením v rade alebo Obnovuje sa.":::

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
