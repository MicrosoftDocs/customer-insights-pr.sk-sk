---
title: Aktualizujte nastavenia zjednotenia zákazníka, účtu alebo kontaktov
description: Aktualizujte duplicitné pravidlá, pravidlá zhody alebo zjednotené polia v nastaveniach zjednotenia zákazníka alebo účtu.
ms.date: 08/26/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: Scott-Stabbert
ms.author: sstabbert
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-match
- ci-merge
- ci-relationships
- customerInsights
ms.openlocfilehash: e893e66fd7691b9703d51ed8f87cfad63880cc3b
ms.sourcegitcommit: 560c4ee16376a9c6fdd7860988ce2d2440194fa5
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 09/01/2022
ms.locfileid: "9392490"
---
# <a name="update-unification-settings"></a>Aktualizujte nastavenia zjednotenia

Ak chcete po vytvorení jednotného profilu skontrolovať alebo zmeniť nastavenia zjednotenia, vykonajte nasledujúce kroky.

1. Ísť do **Údaje** > **Zjednotiť**.

   Pre individuálnych zákazníkov (B-to-C) je **Zjednotiť** zobrazuje počet zjednotených zákazníckych profilov a dlaždíc pre každý z krokov zjednotenia.

   :::image type="content" source="media/m3_unified.png" alt-text="Snímka obrazovky stránky Zjednotenie údajov po zjednotení údajov." lightbox="media/m3_unified.png":::

   Pre podnikateľské účty (B-to-B) **Zjednotiť** zobrazuje počet zjednotených profilov účtov a dlaždíc pre každý z krokov zjednotenia účtov. Ak boli kontakty zjednotené, zobrazí sa počet zjednotených profilov kontaktov a dlaždíc pre každý z krokov zjednotenia kontaktov. Vyberte si vhodnú dlaždicu pod **Zjednotiť účty** alebo **Zjednotiť kontakty (ukážka)** v závislosti od toho, čo chcete aktualizovať.

   :::image type="content" source="media/b2b_unified.png" alt-text="Snímka obrazovky stránky Zjednotenie údajov po zjednotení údajov účtu a kontaktov." lightbox="media/b2b_unified.png":::

   > [!TIP]
   > The **Zodpovedajúce podmienky** dlaždice sa zobrazia iba vtedy, ak bolo vybratých viacero entít.

1. Vyberte, čo chcete aktualizovať:
   - [Zdrojové polia](#edit-source-fields) pridať atribúty alebo entity alebo zmeniť typy atribútov. Ak chcete odstrániť atribút, pozrite si časť [Odstráňte zjednotené pole](#remove-a-unified-field). Ak chcete odstrániť entitu, pozrite si časť [Odstráňte zjednotenú entitu](#remove-a-unified-entity).
   - [Duplicitné záznamy](#manage-deduplication-rules) spravovať pravidlá deduplikácie alebo preferencie zlúčenia.
   - [Zodpovedajúce podmienky](#manage-match-rules) aktualizovať pravidlá zhody v dvoch alebo viacerých entitách.
   - [Zjednotené zákaznícke polia](#manage-unified-fields) na kombináciu alebo vylúčenie polí. Môžete tiež zoskupiť súvisiace profily do klastrov.
   - [Sémantické polia](#manage-semantic-fields-for-unified-contacts) na správu sémantických typov pre jednotné kontaktné polia.
   - [Vzťahy](#manage-contact-and-account-relationships) spravovať vzťah medzi kontaktom a účtom.

1. Po vykonaní zmien vyberte ďalšiu možnosť:

   - [Spustite zodpovedajúce podmienky](#run-matching-conditions) na rýchle vyhodnotenie kvality vašich podmienok zhody (deduplikácia a pravidlá zhody) bez aktualizácie zjednoteného profilu. The **Spustite iba zodpovedajúce podmienky** možnosť sa nezobrazuje pre jednu entitu.
   - [Zjednotiť profily](#run-updates-to-the-unified-profile) spustiť zodpovedajúce podmienky a aktualizovať entitu jednotného profilu bez ovplyvnenia závislostí (ako sú obohatenia, segmenty alebo miery). Závislé procesy nie sú spustené, ale budú obnovené ako [definované v pláne obnovy](schedule-refresh.md).
   - [Zjednotiť profily a závislosti](#run-updates-to-the-unified-profile) na spustenie zodpovedajúcich podmienok, aktualizujte entitu jednotného profilu a aktualizujte všetky závislosti (ako sú obohatenia, segmenty alebo miery). Všetky procesy sa automaticky znova spustia. V B-to-B prebieha zjednotenie na účte aj kontaktných subjektoch, ktoré aktualizujú zjednotené profily.

## <a name="edit-source-fields"></a>Upravte zdrojové polia

1. Vyberte **Upraviť** na **Zdrojové polia** dlaždica.

   :::image type="content" source="media/m3_source_edit.png" alt-text="Snímka obrazovky stránky zdrojových polí zobrazujúca počet primárnych kľúčov, mapovaných a nemapovaných polí":::

   Zobrazí sa počet zmapovaných a nezmapovaných polí.

1. Ak chcete pridať ďalšie atribúty alebo entity, vyberte **Vyberte entity a polia**.

1. Voliteľne môžete zmeniť primárny kľúč entity, typy atribútov a prepínač **Inteligentné mapovanie** zapnuté alebo vypnuté. Ďalšie informácie nájdete v časti [Vyberte zdrojové polia](map-entities.md).

1. Vyberte **Ďalšie** ak chcete vykonať zmeny pravidiel deduplikácie, alebo vyberte **Uložiť a zavrieť** a vrátiť sa do [Aktualizujte nastavenia zjednotenia](#update-unification-settings).

### <a name="remove-a-unified-field"></a>Odstráňte zjednotené pole

Ak chcete odstrániť pole, ktoré bolo zjednotené, pole musí byť odstránené zo všetkých závislostí, ako sú segmenty, miery, obohatenia alebo vzťahy.

1. Po odstránení všetkých závislostí pre pole prejdite na **Údaje** > **Zjednotiť**.

1. Vyberte **Upraviť** na **Zjednotené zákaznícke polia** dlaždica.

1. Vyberte všetky výskyty poľa a potom vyberte **Vylúčiť**.

   :::image type="content" source="media/m3_remove_attribute1.png" alt-text="Snímka obrazovky stránky Zjednotené polia zobrazujúca vybraté polia a tlačidlo Vylúčiť":::

1. Vyberte **hotový** potvrďte a potom vyberte **Uložiť a zavrieť**.

   > [!TIP]
   > Ak sa zobrazí správa „Nepodarilo sa uložiť zjednotenie. Zadaný prostriedok nemožno upraviť alebo odstrániť z dôvodu závislostí v smere toku", potom sa pole stále používa v závislosti v smere toku.

1. Ak sa pole používa v pravidle pre duplicitné záznamy alebo podmienky zhody, vykonajte nasledujúce kroky. V opačnom prípade prejdite na ďalší krok.
   1. Vyberte **Upraviť** na **Duplicitné záznamy** dlaždica.
   1. Odstráňte pole zo všetkých pravidiel, v ktorých sa používa, ak nejaké existujú, a potom vyberte **Ďalšie**.
   1. Na **Zodpovedajúce podmienky** odstráňte pole zo všetkých pravidiel, v ktorých sa používa, ak nejaké existujú, a potom vyberte **Uložiť a zavrieť**.
   1. Vyberte **Zjednotiť** > **Zjednotiť profily a závislosti zákazníkov**. Pred prechodom na ďalší krok počkajte na dokončenie zjednotenia.

1. Vyberte **Upraviť** na **Zdrojové polia** dlaždica.

1. Vyberte **Vyberte entity a polia** a zrušte začiarknutie políčka vedľa každého výskytu poľa.

   :::image type="content" source="media/m3_remove_attribute2.png" alt-text="Snímka obrazovky dialógového okna Vybrať entity a polia so začiarknutými políčkami":::

1. Vyberte **Použiť**.

1. Vyberte položku **Uložiť a zavrieť**.

1. Vyberte **Zjednotiť** > **Zjednotiť profily a závislosti zákazníkov** aktualizovať jednotný profil.

### <a name="remove-a-unified-entity"></a>Odstráňte zjednotenú entitu

Ak chcete odstrániť entitu, ktorá bola zjednotená, entita musí byť odstránená zo všetkých závislostí, ako sú segmenty, miery, obohatenia alebo vzťahy.

1. Po odstránení všetkých závislostí entity prejdite na **Údaje** > **Zjednotiť**.

1. Vyberte **Upraviť** na **Zjednotené zákaznícke polia** dlaždica.

1. Vyberte všetky polia entity a potom vyberte **Vylúčiť**.

   :::image type="content" source="media/m3_remove_entity1.png" alt-text="Snímka obrazovky zjednotených polí so všetkými vybratými poľami entity a tlačidlom Vylúčiť":::

1. Vyberte **hotový** potvrďte a potom vyberte **Uložiť a zavrieť**.

   > [!TIP]
   > Ak sa zobrazí správa „Nepodarilo sa uložiť zjednotenie. Zadaný zdroj nie je možné upraviť alebo odstrániť z dôvodu downstreamových závislostí“, potom sa entita stále používa v downstreamovej závislosti.

1. Vyberte **Upraviť** na **Duplicitné záznamy** dlaždica.

1. Odstráňte všetky pravidlá z entity, ak nejaké existujú, a potom vyberte **Ďalšie**.

1. Na **Zodpovedajúce podmienky** stránku, vyberte entitu a potom vyberte **Odstrániť**.

   :::image type="content" source="media/m3_remove_entity2.png" alt-text="Snímka obrazovky s podmienkami zhody s vybratou entitou a tlačidlom Odstrániť":::

1. Vyberte položku **Uložiť a zavrieť**.

1. Vyberte **Upraviť** na **Zdrojové polia** dlaždica.

1. Vyberte **Vyberte entity a polia** a zrušte začiarknutie políčka vedľa entity.

   :::image type="content" source="media/m3_remove_entity3.png" alt-text="Snímka obrazovky dialógového okna Výber entít a polí so zrušeným začiarknutím políčka entity":::

1. Vyberte **Použiť**.

1. Vyberte položku **Uložiť a zavrieť**.

1. Vyberte **Zjednotiť** > **Zjednotiť profily a závislosti zákazníkov** aktualizovať jednotný profil.

## <a name="manage-deduplication-rules"></a>Spravujte pravidlá deduplikácie

1. Vyberte **Upraviť** na **Duplicitné záznamy** dlaždica.

   :::image type="content" source="media/m3_duplicates_edit.png" alt-text="Snímka obrazovky stránky duplicitných záznamov zobrazujúca počet duplicitných záznamov" lightbox="media/m3_duplicates_edit.png":::

   Počet nájdených duplicitných záznamov sa zobrazuje pod **Duplikáty**. The **Záznamy boli deduplikované** stĺpec zobrazuje, ktoré entity mali duplicitné záznamy a percento duplicitných záznamov.

1. Ak chcete použiť obohatenú entitu, vyberte **Použite obohatené entity**. Viac informácií nájdete v časti [Obohatenie pre zdroje údajov](data-sources-enrichment.md).

1. Ak chcete spravovať pravidlá deduplikácie, vyberte niektorú z nasledujúcich možností:
   - **Vytvorte nové pravidlo** : Vyberte **Pridať pravidlo** pod príslušným subjektom. Viac informácií nájdete v časti [Definujte pravidlá deduplikácie](remove-duplicates.md#define-deduplication-rules).
   - **Zmeňte podmienky pravidiel** : Vyberte pravidlo a potom **Upraviť**. Zmeňte polia, pridajte alebo odstráňte podmienky alebo pridajte alebo odstráňte výnimky.
   - **Náhľad** : Vyberte pravidlo a potom **Náhľad** zobrazíte výsledky posledného spustenia pre toto pravidlo.
   - **Deaktivujte pravidlo** : Vyberte pravidlo a potom **Deaktivovať** zachovať pravidlo deduplikácie a zároveň ho vylúčiť z procesu priraďovania.
   - **Duplikovať pravidlo** : Vyberte pravidlo a potom **Duplicitné** vytvoriť podobné pravidlo s úpravami.
   - **Odstráňte pravidlo** : Vyberte pravidlo a potom **Odstrániť**.

1. Ak chcete zmeniť predvoľby zlúčenia, vyberte entitu. Predvoľby môžete zmeniť iba vtedy, ak je vytvorené pravidlo.
   1. Vyberte **Upravte predvoľby zlúčenia** a zmeniť **Záznam na uchovanie** možnosť.
   1. Ak chcete zmeniť preferencie zlúčenia pre jednotlivé atribúty entity, vyberte **Pokročilé** a vykonať potrebné zmeny.

   1. Vyberte položku **Hotovo**.

1. Vyberte **Ďalšie** ak chcete vykonať zmeny zodpovedajúcich podmienok, alebo vyberte **Uložiť a zavrieť** a vrátiť sa do [Aktualizujte nastavenia zjednotenia](#update-unification-settings).

## <a name="manage-match-rules"></a>Spravovať pravidlá spárovania

Väčšinu parametrov zhody môžete prekonfigurovať a doladiť. Nemôžete pridávať ani odstraňovať entity. Pravidlá zhody sa nevzťahujú na jednu entitu.

1. Vyberte **Upraviť** na **Zodpovedajúce podmienky** dlaždica.

   :::image type="content" source="media/m3_match_edit.png" alt-text="Snímka obrazovky stránky pravidiel a podmienok zápasu so štatistikami." lightbox="media/m3_match_edit.png":::

   Stránka zobrazuje poradie zápasov a definované pravidlá a nasledujúce štatistiky:
   - **Jedinečné zdrojové záznamy** zobraziť počet jednotlivých zdrojových záznamov, ktoré boli spracované v poslednom behu zápasu.
   - **Zhodné a nezhodné záznamy** zvýraznite, koľko jedinečných záznamov zostáva po spracovaní pravidiel zápasu.
   - **Iba zhodné záznamy** zobraziť počet zápasov vo všetkých vašich pároch zápasov.

1. Ak chcete zobraziť výsledky všetkých pravidiel a ich skóre, vyberte **Zobraziť posledné spustenie**. Zobrazia sa výsledky vrátane alternatívnych ID kontaktu. Výsledky si môžete stiahnuť.

1. Ak chcete zobraziť výsledky a skóre konkrétneho pravidla, vyberte pravidlo a potom **Náhľad**. Zobrazia sa výsledky. Výsledky si môžete stiahnuť.

1. Ak chcete zobraziť výsledky konkrétnej podmienky v pravidle, vyberte pravidlo a potom **Upraviť**. Na table Upraviť vyberte **Náhľad** pod podmienkou. Výsledky si môžete stiahnuť.

   :::image type="content" source="media/m3_match_condition_preview.png" alt-text="Grafické znázornenie nespárovaných a spárovaných záznamov vrátane zoznamu údajov.":::

1. Ak ste pridali obohatenú entitu, vyberte **Použite obohatené entity**. Viac informácií nájdete v časti [Obohatenie pre zdroje údajov](data-sources-enrichment.md).

1. Ak chcete spravovať pravidlá, vyberte niektorú z nasledujúcich možností:
   - **Vytvorte nové pravidlo** : Vyberte **Pridať pravidlo** pod príslušným subjektom. Viac informácií nájdete v časti [Definujte pravidlá pre zápasové dvojice](match-entities.md#define-rules-for-match-pairs).
   - **Zmeňte poradie svojich pravidiel** ak ste definovali viacero pravidiel: Presuňte pravidlá do požadovaného poradia. Viac informácií nájdete v časti [Zadajte poradie zhody](match-entities.md#specify-the-match-order).
   - **Zmeňte podmienky pravidiel** : Vyberte pravidlo a potom **Upraviť**. Zmeňte polia, pridajte alebo odstráňte podmienky alebo pridajte alebo odstráňte výnimky.
   - **Deaktivujte pravidlo** : Vyberte pravidlo a potom **Deaktivovať** zachovať pravidlo zhody a zároveň ho vylúčiť z procesu priraďovania.
   - **Duplikovať pravidlo** : Vyberte pravidlo a potom **Duplicitné** vytvoriť podobné pravidlo s úpravami.
   - **Odstráňte pravidlo** : Vyberte pravidlo a potom **Odstrániť**.

1. Vyberte **Ďalšie** ak chcete vykonať zmeny v zjednotených poliach, alebo vyberte **Uložiť a zavrieť** a vrátiť sa do [Aktualizujte nastavenia zjednotenia](#update-unification-settings).

## <a name="manage-unified-fields"></a>Spravujte zjednotené polia

1. Vyberte **Upraviť** na **Zjednotené zákaznícke polia** dlaždica.

    :::image type="content" source="media/m3_merge_edit.png" alt-text="Snímka obrazovky zjednotených zákazníckych polí":::

1. Skontrolujte kombinované a vylúčené polia a vykonajte potrebné zmeny. Pridajte alebo upravte kľúč CustomerID alebo skupinové profily do klastrov. Viac informácií nájdete v časti [Zjednotiť zákaznícke polia](merge-entities.md).

1. Pre zákazníkov alebo účty vyberte **Ďalšie** preskúmať a [aktualizovať jednotný profil a závislosti](#run-updates-to-the-unified-profile). Alebo vyberte **Uložiť a zavrieť** a vrátiť sa do [Aktualizujte nastavenia zjednotenia](#update-unification-settings) vykonať ďalšie zmeny.

   Pre kontakty vyberte **Ďalšie** spravovať sémantické polia. Alebo vyberte **Uložiť a zavrieť** a vrátiť sa do [Aktualizujte nastavenia zjednotenia](#update-unification-settings) vykonať ďalšie zmeny.

## <a name="manage-semantic-fields-for-unified-contacts"></a>Spravujte sémantické polia pre jednotné kontakty

1. Vyberte **Upraviť** na **Sémantické polia** dlaždica.

1. Ak chcete zmeniť sémantický typ zjednoteného poľa, vyberte nový typ. Viac informácií nájdete v časti [Definujte sémantické polia pre jednotné kontakty](data-unification-contacts.md#define-the-semantic-fields-for-unified-contacts).

1. Vyberte **Ďalšie** spravovať vzťah účtu a kontaktu alebo vyberte **Uložiť a zavrieť** a vrátiť sa do [Aktualizujte nastavenia zjednotenia](#update-unification-settings) vykonať ďalšie zmeny.

## <a name="manage-contact-and-account-relationships"></a>Spravujte vzťahy s kontaktmi a účtami

1. Vyberte **Upraviť** na **Vzťahy** dlaždica.

1. Ak chcete zmeniť vzťah kontaktu a účtu, zmeňte ktorúkoľvek z nasledujúcich informácií:

   - **Cudzí kľúč od kontaktnej entity** : Vyberte atribút, ktorý spája vašu kontaktnú entitu s účtom.
   - **Do účtovnej jednotky** : Vyberte entitu účtu priradenú ku kontaktu.

1. Vyberte **Ďalšie** skontrolujte nastavenia zjednotenia a [aktualizovať jednotný profil a závislosti](#run-updates-to-the-unified-profile) alebo vyberte **Uložiť a zavrieť** a vrátiť sa do [Aktualizujte nastavenia zjednotenia](#update-unification-settings) vykonať ďalšie zmeny.

## <a name="run-matching-conditions"></a>Spustite zodpovedajúce podmienky

Spustiť podmienky zhody spustí iba deduplikáciu a pravidlá zhody a aktualizuje *Deduplikácia_* * a *ConflationMatchPair* subjektov.

1. Z **Údaje** > **Zjednotiť** stránku, vyberte **Spustite iba zodpovedajúce podmienky**.

   The **Duplicitné záznamy** a **Zodpovedajúce podmienky** dlaždice ukazujú **Vo fronte** alebo **Osviežujúce** postavenie.

   [!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

1. Po dokončení procesu priraďovania vyberte **Upraviť** na **Zodpovedajúce podmienky** dlaždica.

   :::image type="content" source="media/match-KPIs.png" alt-text="Orezaná snímka obrazovky s kľúčovými metrikami na stránke Zhoda s číslami a podrobnosťami.":::

1. Ak chcete vykonať zmeny, pozri [Spravujte pravidlá deduplikácie](#manage-deduplication-rules) alebo [Spravujte pravidlá zápasu](#manage-match-rules).

1. Spustite proces zápasu znova alebo [spustiť aktualizácie profilu](#run-updates-to-the-unified-profile).

## <a name="run-updates-to-the-unified-profile"></a>Spustite aktualizácie jednotného profilu

- Ak chcete spustiť zodpovedajúce podmienky a aktualizovať entitu jednotného profilu *bez* ovplyvňujúce závislosti (ako sú zákaznícke karty, obohatenia, segmenty alebo opatrenia), vyberte **Zjednotiť profily zákazníkov**. Pre účty vyberte **Zjednotiť účty** > **Zjednotiť profily**. Pre kontakty vyberte **Zjednotiť kontakty (ukážka)** > **Zjednotiť profily**. Závislé procesy nie sú spustené, ale budú obnovené ako [definované v pláne obnovy](schedule-refresh.md).
- Ak chcete spustiť zodpovedajúce podmienky, aktualizovať zjednotený profil a spustiť všetky závislosti, vyberte **Zjednotiť profily a závislosti zákazníkov**. Všetky procesy sa automaticky znova spustia. Pre účty a kontakty vyberte **Zjednotiť účty** > **Zjednotiť profily a závislosti**. Podmienky zhody sú spustené pre oba účty a kontakty, ktoré aktualizujú zjednotené profily a všetky ostatné závislosti sú spustené.

Všetky dlaždice okrem **Zdrojové polia** šou **Vo fronte** alebo **Osviežujúce**.

[!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

Výsledky úspešného behu sa zobrazia na **Zjednotiť** stránka zobrazujúca počet zjednotených profilov.
