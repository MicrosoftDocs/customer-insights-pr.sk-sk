---
title: Skontrolujte zjednotenie údajov
description: Skontrolujte kroky zjednotenia údajov, vytvorte jednotné profily zákazníkov a skontrolujte výsledky
ms.date: 05/04/2022
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
ms.openlocfilehash: 4c709dfb55bf079dd2fe99e41adb4c77c2bece4b
ms.sourcegitcommit: 6a5f4312a2bb808c40830863f26620daf65b921d
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 05/11/2022
ms.locfileid: "8743030"
---
# <a name="review-data-unification"></a>Skontrolujte zjednotenie údajov

[!INCLUDE [m3-prod-trial-note](includes/m3-prod-trial-note.md)]

Tento posledný krok v procese zjednotenia zobrazuje súhrn krokov v procese a poskytuje možnosť vykonať zmeny pred vytvorením zjednoteného profilu.

:::image type="content" source="media/m3_review.png" alt-text="Snímka obrazovky kontroly a vytvárania zákazníckych profilov.":::

## <a name="review-the-data-unification-steps"></a>Pozrite si kroky zjednotenia údajov

1. Vyberte **Upraviť** na ktoromkoľvek z krokov zjednotenia údajov, aby ste ich mohli skontrolovať a vykonať akékoľvek zmeny.

1. Ak ste s výberom spokojní, vyberte si **Vytvorte profily zákazníkov**. The **Zjednotiť** stránka sa zobrazí počas vytvárania jednotného profilu zákazníka. Dokončenie algoritmu zjednotenia nejaký čas trvá a konfiguráciu nemôžete zmeniť, kým sa nedokončí.

   [!INCLUDE [m3-task-details-include](includes/m3-task-details.md)]

Po dokončení procesu zjednotenia zavolá entita jednotného profilu zákazníka *Zákazník*, je uvedený na **entity** stránke v **Profily** oddiele. Prvý úspešný beh zjednotenia vytvorí zjednotené *Zákazník* subjekt. Všetky nasledujúce behy rozširujú túto entitu.

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
