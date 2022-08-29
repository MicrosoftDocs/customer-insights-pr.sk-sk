---
title: Skontrolujte zjednotenie údajov
description: Skontrolujte kroky zjednotenia údajov, vytvorte jednotné profily zákazníkov a skontrolujte výsledky
ms.date: 08/12/2022
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
ms.openlocfilehash: b4d77effc347e40fecde625a1a42a24900456471
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 08/16/2022
ms.locfileid: "9303986"
---
# <a name="review-data-unification"></a>Skontrolujte zjednotenie údajov

Skontrolujte súhrn zmien, vytvorte jednotný profil a skontrolujte výsledky.

## <a name="review-and-create-customer-profiles"></a>Kontrola a vytváranie profilov zákazníkov

Tento posledný krok v procese zjednotenia zobrazuje súhrn krokov v procese a poskytuje možnosť vykonať zmeny pred vytvorením zjednoteného profilu.

[!INCLUDE [m3-first-run-note](includes/m3-first-run-note.md)]

:::image type="content" source="media/m3_review.png" alt-text="Snímka obrazovky kontroly a vytvárania profilov zákazníkov.":::

1. Vyberte **Upraviť** na ktoromkoľvek z krokov zjednotenia údajov, aby ste ich mohli skontrolovať a vykonať akékoľvek zmeny.

1. Ak ste s výberom spokojní, vyberte si **Vytvorte profily zákazníkov** (alebo **Vytvorte profily účtov** pre B-to-B). The **Zjednotiť** počas vytvárania jednotného zákazníckeho profilu.

   :::image type="content" source="media/m3_unify_refreshing.png" alt-text="Snímka obrazovky stránky Zjednotiť s dlaždicami so zobrazením v rade alebo Obnovuje sa.":::

   [!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

Dokončenie algoritmu zjednotenia nejaký čas trvá a konfiguráciu nemôžete zmeniť, kým sa nedokončí.

## <a name="view-the-results-of-data-unification"></a>Pozrite si výsledky zjednotenia údajov

Po zjednotení, **Údaje** > **Zjednotiť** zobrazuje počet zjednotených zákazníckych profilov (alebo profilov účtov pre B-to-B). Výsledky každého kroku v procese zjednotenia sa zobrazia na každej dlaždici. Napríklad, **Zdrojové polia** zobrazuje počet mapovaných atribútov (polí) a **Duplicitné záznamy** zobrazuje počet nájdených duplicitných záznamov.

:::image type="content" source="media/m3_unified.png" alt-text="Snímka obrazovky stránky Zjednotenie údajov po zjednotení údajov.":::

> [!TIP]
> The **Zodpovedajúce podmienky** dlaždice sa zobrazia iba vtedy, ak bolo vybratých viacero entít.

Odporúčame vám, aby ste si prezreli výsledky, najmä ich kvalitu [pravidlá zápasu](data-unification-update.md#manage-match-rules) a v prípade potreby ich upravte.

Keď treba, [vykonajte zmeny v nastaveniach zjednotenia](data-unification-update.md) a znova spustite zjednotený profil.

### <a name="verify-output-entities-from-data-unification"></a>Overte výstupné entity zo zjednotenia údajov

Ísť do **Údaje** > **entity** na overenie výstupných entít.

Entita jednotného profilu zákazníka, tzv *Zákazník*, zobrazí sa v **Profily** oddiele. Prvý úspešný beh zjednotenia vytvorí zjednotené *Zákazník* subjekt. Všetky nasledujúce behy rozširujú túto entitu.

Deduplikácia a konfigurácia entity sa vytvárajú a zobrazujú v **Systém** oddiele. Vytvorí sa deduplikovaná entita pre každú zo zdrojových entít s názvom **Deduplication_DataSource_Entity**. The **ConflationMatchPairs** entity obsahuje informácie o zhodách medzi entitami.

Entita deduplikovaného výstupu obsahuje nasledujúce informácie:
- ID/kľúče
  - Polia Primárny kľúč a Alternatívne ID. Pole Alternatívne ID pozostáva zo všetkých alternatívnych ID identifikovaných pre záznam.
  - Pole Deduplication_GroupId zobrazuje skupinu alebo klaster identifikovaný v rámci entity, ktorá zoskupuje všetky podobné záznamy na základe zadaných deduplikačných polí. Používa sa na účely spracovania systému. Ak nie sú zadané žiadne pravidlá manuálnej deduplikácie a uplatňujú sa pravidlá systému definované pre deduplikáciu, toto pole v entite výstupu deduplikácie nenájdete.
  - Deduplication_WinnerId: Toto pole obsahuje ID víťaza z identifikovaných skupín alebo klastrov. Ak je hodnota Deduplication_WinnerId rovnaká ako hodnota primárneho kľúča pre záznam, znamená to, že záznam je víťazným záznamom.
- Polia používané na definovanie pravidiel deduplikácie.
- Polia Pravidlo a Skóre označujú, ktoré z pravidiel deduplikácie sa použili a skóre vrátené algoritmom párovania.

## <a name="next-step"></a>Ďalší krok

- Pre B-to-B voliteľne vykonať [zjednotenie kontaktov](data-unification-contacts.md).

- Pre B-to-C nakonfigurujte [činnosti](activities.md),[obohatenia](enrichment-hub.md),[vzťahy](relationships.md), alebo [Opatrenia](measures.md) získať viac informácií o svojich zákazníkoch.

[!INCLUDE[footer-include](includes/footer-banner.md)]
