---
title: Aktualizujte nastavenia zjednotenia
description: Aktualizujte duplicitné pravidlá, pravidlá zhody alebo zjednotené polia v nastaveniach zjednotenia.
ms.date: 05/04/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: v-wendysmith
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-match
- ci-merge
- ci-relationships
- customerInsights
ms.openlocfilehash: be399da9b98d8803d7d1a90f44a40e0d638a8d47
ms.sourcegitcommit: 4ae316c856b8de0f08a4605f73e75a8c2cf51c4e
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 05/13/2022
ms.locfileid: "8755609"
---
# <a name="update-the-unification-settings"></a>Aktualizujte nastavenia zjednotenia

[!INCLUDE [m3-prod-trial-note](includes/m3-prod-trial-note.md)]

Ak chcete po vytvorení jednotného profilu skontrolovať alebo zmeniť nastavenia zjednotenia, vykonajte nasledujúce kroky.

1. Ísť do **Údaje** > **Zjednotiť**.

   :::image type="content" source="media/m3_unified.png" alt-text="Snímka obrazovky stránky Zjednotenie údajov po zjednotení údajov.":::

   > [!TIP]
   > The **Zodpovedajúce podmienky** dlaždice sa zobrazia iba vtedy, ak bolo vybratých viacero entít.

1. Vyberte, čo chcete aktualizovať:
   - [Zdrojové polia](#edit-source-fields) pridať entity alebo atribúty alebo zmeniť typy atribútov.
   - [Duplicitné záznamy](#manage-deduplication-rules) spravovať pravidlá deduplikácie alebo preferencie zlúčenia.
   - [Zodpovedajúce podmienky](#manage-match-rules) aktualizovať pravidlá zhody v dvoch alebo viacerých entitách.
   - [Zjednotené zákaznícke polia](#manage-unified-fields) na kombináciu alebo vylúčenie polí. Môžete tiež zoskupiť súvisiace profily do klastrov.

1. Po vykonaní zmien vyberte ďalšiu možnosť:

   :::image type="content" source="media/m3_run_match_merge.png" alt-text="Snímka obrazovky stránky Data Unify so zvýraznenými možnosťami Unify.":::

   - Ak chcete aktualizovať zjednotený zákaznícky profil (so závislosťami alebo bez nich), pozri [Spustite aktualizácie profilu zákazníka](#run-updates-to-the-unified-customer-profile).
   - Ak chcete vyhodnotiť kvalitu vašich zodpovedajúcich podmienok bez aktualizácie zjednoteného profilu, pozrite si [Spustite zodpovedajúce podmienky](#run-matching-conditions). The **Spustite iba zodpovedajúce podmienky** možnosť sa nezobrazuje pre jednu entitu.

## <a name="edit-source-fields"></a>Upravte zdrojové polia

Nemôžete odstrániť atribút alebo entitu, ak už boli zjednotené.

1. Vyberte **Upraviť** na **Zdrojové polia** dlaždica.

   :::image type="content" source="media/m3_source_edit.png" alt-text="Snímka obrazovky stránky zdrojových polí zobrazujúca počet primárnych kľúčov, namapovaných a nezmapovaných polí":::

   Zobrazí sa počet zmapovaných a nezmapovaných polí.

1. Vyberte **Vyberte entity a polia** pridať ďalšie atribúty alebo entity. Pomocou vyhľadávania alebo posúvania nájdite a vyberte atribúty a entity, ktoré vás zaujímajú. Vyberte **Použiť**.

1. Voliteľne môžete zmeniť primárny kľúč entity, typy atribútov a prepínač **Inteligentné mapovanie** zapnuté alebo vypnuté. Ďalšie informácie nájdete v časti [Vyberte primárny kľúč a sémantický typ atribútov](map-entities.md#select-primary-key-and-semantic-type-for-attributes).

1. Vyberte **Ďalšie** ak chcete vykonať zmeny pravidiel deduplikácie, alebo vyberte **Uložiť a zavrieť** a vrátiť sa do [Aktualizujte nastavenia zjednotenia](#update-the-unification-settings).

## <a name="manage-deduplication-rules"></a>Spravujte pravidlá deduplikácie

1. Vyberte **Upraviť** na **Duplicitné záznamy** dlaždica.

   :::image type="content" source="media/m3_duplicates_edit.png" alt-text="Snímka obrazovky stránky duplicitných záznamov zobrazujúca počet duplicitných záznamov" lightbox="media/m3_duplicates_edit.png":::

   Počet nájdených duplicitných záznamov sa zobrazuje pod **Duplikáty**. The **Záznamy boli deduplikované** stĺpec zobrazuje, ktoré entity mali duplicitné záznamy a percento duplicitných záznamov.

1. Ak ste pridali obohatenú entitu, vyberte **Použite obohatené entity**. Ďalšie informácie nájdete v časti [Obohatenie pre zdroje údajov](data-sources-enrichment.md).

1. Ak chcete spravovať pravidlá deduplikácie, vyberte niektorú z nasledujúcich možností:
   - **Vytvorte nové pravidlo** : Vyberte **Pridať pravidlo** pod príslušným subjektom. Ďalšie informácie nájdete v časti [Definujte pravidlá deduplikácie](remove-duplicates.md#define-deduplication-rules).
   - **Zmeňte podmienky pravidiel** : Vyberte pravidlo a potom **Upraviť**. Zmeňte polia, pridajte alebo odstráňte podmienky alebo pridajte alebo odstráňte výnimky.
   - **Náhľad** : Vyberte pravidlo a potom **Náhľad** zobrazíte výsledky posledného spustenia tohto pravidla.
   - **Deaktivujte pravidlo** : Vyberte pravidlo a potom **Deaktivovať** zachovať pravidlo deduplikácie a zároveň ho vylúčiť z procesu priraďovania.
   - **Duplikovať pravidlo** : Vyberte pravidlo a potom **Duplicitné** vytvoriť podobné pravidlo s úpravami.
   - **Odstráňte pravidlo** : Vyberte pravidlo a potom **Odstrániť**.

1. Ak chcete zmeniť preferencie zlúčenia, vyberte entitu. Predvoľby môžete zmeniť, iba ak je vytvorené pravidlo.
   1. Vyberte **Upravte predvoľby zlúčenia** a zmeniť **Záznam na uchovanie** možnosť.
   1. Ak chcete zmeniť preferencie zlúčenia pre jednotlivé atribúty entity, vyberte **Pokročilé** a vykonať potrebné zmeny.

      :::image type="content" source="media/m3_adv_merge.png" alt-text="Snímka obrazovky rozšírených predvolieb zlúčenia zobrazujúca najnovší e-mail a najúplnejšiu adresu":::

   1. Vyberte položku **Hotovo**.

1. Vyberte **Ďalšie** ak chcete vykonať zmeny zodpovedajúcich podmienok, alebo vyberte **Uložiť a zavrieť** a vrátiť sa do [Aktualizujte nastavenia zjednotenia](#update-the-unification-settings).

## <a name="manage-match-rules"></a>Spravovať pravidlá spárovania

Väčšinu parametrov zhody môžete prekonfigurovať a doladiť. Nemôžete pridávať ani odstraňovať entity. Pravidlá zhody sa nevzťahujú na jeden subjekt.

1. Vyberte **Upraviť** na **Zodpovedajúce podmienky** dlaždica.

   :::image type="content" source="media/m3_match_edit.png" alt-text="Snímka obrazovky stránky pravidiel a podmienok zápasu so štatistikami." lightbox="media/m3_match_edit.png":::

   Stránka zobrazuje poradie zápasov a definované pravidlá a nasledujúce štatistiky:
   - **Jedinečné zdrojové záznamy** zobrazuje počet jednotlivých zdrojových záznamov, ktoré boli spracované v poslednom spustení priraďovania.
   - **Spárované a nespárované záznamy** zdôrazňuje, koľko jedinečných záznamov zostáva po spracovaní pravidiel zhody.
   - **Iba zodpovedajúce záznamy** zobrazuje počet spárovaní vo všetkých vašich pároch.

1. Ak chcete zobraziť výsledky všetkých pravidiel a ich skóre, vyberte **Zobraziť posledné spustenie**. Zobrazia sa výsledky vrátane alternatívnych ID kontaktu. Výsledky si môžete stiahnuť.

1. Ak chcete zobraziť výsledky a skóre konkrétneho pravidla, vyberte pravidlo a potom **Náhľad**. Zobrazia sa výsledky. Výsledky si môžete stiahnuť.

1. Ak chcete zobraziť výsledky konkrétnej podmienky v pravidle, vyberte pravidlo a potom **Upraviť**. Na table Upraviť vyberte **Náhľad** pod podmienkou. Výsledky si môžete stiahnuť.

   :::image type="content" source="media/m3_match_condition_preview.png" alt-text="Grafické znázornenie nespárovaných a spárovaných záznamov vrátane zoznamu údajov.":::

1. Ak ste pridali obohatenú entitu, vyberte **Použite obohatené entity**. Ďalšie informácie nájdete v časti [Obohatenie pre zdroje údajov](data-sources-enrichment.md).

1. Ak chcete spravovať pravidlá, vyberte niektorú z nasledujúcich možností:
   - **Vytvorte nové pravidlo** : Vyberte **Pridať pravidlo** pod príslušným subjektom. Ďalšie informácie nájdete v časti [Definujte pravidlá pre zápasové dvojice](match-entities.md#define-rules-for-match-pairs).
   - **Zmeňte poradie svojich pravidiel** ak ste definovali viacero pravidiel: Presuňte pravidlá do požadovaného poradia. Ďalšie informácie nájdete v časti [Zadajte poradie zhody](match-entities.md#specify-the-match-order).
   - **Zmeňte podmienky pravidiel** : Vyberte pravidlo a potom **Upraviť**. Zmeňte polia, pridajte alebo odstráňte podmienky alebo pridajte alebo odstráňte výnimky.
   - **Deaktivujte pravidlo** : Vyberte pravidlo a potom **Deaktivovať** zachovať pravidlo zhody a zároveň ho vylúčiť z procesu priraďovania.
   - **Duplikovať pravidlo** : Vyberte pravidlo a potom **Duplicitné** vytvoriť podobné pravidlo s úpravami.
   - **Odstráňte pravidlo** : Vyberte pravidlo a potom **Odstrániť**.

1. Vyberte **Ďalšie** ak chcete vykonať zmeny v zjednotených poliach, alebo vyberte **Uložiť a zavrieť** a vrátiť sa do [Aktualizujte nastavenia zjednotenia](#update-the-unification-settings).

## <a name="manage-unified-fields"></a>Spravujte zjednotené polia

1. Vyberte **Upraviť** na **Zjednotené zákaznícke polia** dlaždica.

    :::image type="content" source="media/m3_merge_edit.png" alt-text="Snímka obrazovky zjednotených zákazníckych polí":::

1. Skontrolujte kombinované a vylúčené polia a vykonajte potrebné zmeny. Pridajte alebo upravte kľúč CustomerID alebo skupinové profily do klastrov. Ďalšie informácie nájdete v časti [Zjednotiť zákaznícke polia](merge-entities.md).

1. Vyberte **Ďalšie** skontrolujte nastavenia zjednotenia a [aktualizovať jednotný profil a závislosti](#run-updates-to-the-unified-customer-profile) alebo vyberte **Uložiť a zavrieť** a vrátiť sa do [Aktualizujte nastavenia zjednotenia](#update-the-unification-settings) vykonať ďalšie zmeny.

## <a name="run-matching-conditions"></a>Spustite zodpovedajúce podmienky

1. Od **Údaje** > **Zjednotiť** stránku, vyberte **Spustite iba zodpovedajúce podmienky**.

   The **Duplicitné záznamy** a **Zodpovedajúce podmienky** dlaždice ukazujú **Vo fronte** alebo **Osviežujúce**.

   [!INCLUDE [m3-task-details-include](includes/m3-task-details.md)]

1. Po dokončení procesu priraďovania vyberte **Upraviť** na **Zodpovedajúce podmienky** dlaždica.

   :::image type="content" source="media/match-KPIs.png" alt-text="Orezaná snímka obrazovky s kľúčovými metrikami na stránke Zhoda s číslami a podrobnosťami.":::

1. Ak chcete vykonať zmeny, pozri [Spravujte pravidlá deduplikácie](#manage-deduplication-rules) alebo [Spravujte pravidlá zápasu](#manage-match-rules).

1. Spustite proces zápasu znova alebo [spustiť aktualizácie profilu zákazníka](#run-updates-to-the-unified-customer-profile).

## <a name="run-updates-to-the-unified-customer-profile"></a>Spustite aktualizácie jednotného profilu zákazníka

1. Od **Údaje** > **Zjednotiť** stránka, vyberte:

   - **Zjednotiť profily zákazníkov** : Aktualizuje entitu jednotného profilu zákazníka bez ovplyvnenia závislostí (ako sú obohatenia, segmenty alebo opatrenia). Závislé procesy nie sú spustené, ale budú obnovené ako [definované v pláne obnovy](system.md#schedule-tab).

   - **Zjednotiť profily a závislosti zákazníkov** : Aktualizuje jednotný profil a všetky závislosti. Všetky procesy sa automaticky znova spustia. Po dokončení všetkých nadväzujúcich procesov sa v profile zákazníka zohľadnia aktualizované údaje.

   The **Duplicitné záznamy**, **podmienky** a **Zjednotené zákaznícke polia** dlaždice ukazujú **Vo fronte** alebo **Osviežujúce**.

   [!INCLUDE [m3-task-details-include](includes/m3-task-details.md)]
