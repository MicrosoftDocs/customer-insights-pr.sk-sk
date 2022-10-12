---
title: Pripojte sa k a Power Query zdroj údajov (obsahuje video)
description: Spracovanie údajov prostredníctvom a Power Query konektor (obsahuje video).
ms.date: 09/29/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-data-sources
- ci-create-data-source
- customerInsights
ms.openlocfilehash: 4cc7e57dfb0f8d050e91adc441c24e849882f5d8
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 09/30/2022
ms.locfileid: "9609915"
---
# <a name="connect-to-a-power-query-data-source"></a>Pripojte sa k a Power Query zdroj údajov

Power Query ponúka širokú škálu konektorov na prijímanie údajov. Väčšinu z týchto konektorov podporuje Dynamics 365 Customer Insights.

Pridávanie zdrojov údajov na základe Power Query konektory sa vo všeobecnosti riadia krokmi uvedenými v tejto časti. V závislosti od použitého konektora sú však potrebné rôzne informácie. Ak sa chcete dozvedieť viac, pozrite si dokumentáciu o jednotlivých konektoroch v [Power Query odkaz na konektor](/power-query/connectors/).

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWN6EK]

## <a name="create-a-new-data-source"></a>Vytvorenie nového zdroja údajov

1. Prejdite do **Údaje** > **Zdroje údajov**.

1. Vyberte položku **Pridať zdroj údajov**.

1. Vybrať **Microsoft Power Query**.

1. Poskytnúť **názov** a voliteľné **Popis** pre zdroj údajov a vyberte **Ďalšie**.

1. Vyberte jeden z [dostupných konektorov](#available-power-query-data-sources). V tomto príklade vyberieme **Text/CSV** konektor.

1. Zadajte požadované údaje v časti **Nastavenia spojenia** pre vybraný konektor a vyberte **Ďalej** na zobrazenie ukážky údajov.

1. Vyberte **Zmena údajov**.

1. Skontrolujte a upravte svoje údaje v **Power Query - Upraviť otázky** stránku. Entity, ktoré systémy identifikovali vo vybratých zdrojoch údajov, sa zobrazia na ľavej table.

   :::image type="content" source="media/data-manager-configure-edit-queries.png" alt-text="Úprava dialógového okna dotazov":::

1. Transformujte svoje údaje. Vyberte entitu, ktorú chcete upraviť alebo transformovať. Použite možnosti v Power Query okno na použitie transformácií. Každá transformácia je uvedená pod **Aplikované kroky**. Power Query poskytuje množstvo [vopred postavená transformácia](/power-query/power-query-what-is-power-query#transformations) možnosti.

   > [!IMPORTANT]
   > Odporúčame vám použiť nasledujúce transformácie:
   >
   > - Ak prijímate údaje zo súboru CSV, prvý riadok často obsahuje hlavičky. Ísť do **Transformovať** a vyberte **Použite prvý riadok ako hlavičky**.
   > - Uistite sa, že typ údajov je nastavený správne a zodpovedá údajom. Napríklad pre polia dátumu vyberte typ dátumu.

1. Ak chcete pridať ďalšie entity do zdroj údajov v **Upraviť dopyty** dialóg, prejdite na **Domov** a vyberte **Získajte údaje**. Opakujte kroky 5-10, kým nepridáte všetky entity pre toto zdroj údajov. Ak máte databázu, ktorá obsahuje viacero množín údajov, každá množina údajov je jej vlastná entita.

1. Vyberte **Uložiť**. The **Zdroje dát** otvorí sa stránka s novým zdroj údajov v **Osviežujúce** postavenie.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

Načítanie údajov môže chvíľu trvať. Po úspešnom obnovení môžu byť prijaté údaje skontrolované z [**entity**](entities.md) stránku.

> [!CAUTION]
>
> - Zdroj údajov na základe Power Query vytvára a [dátový tok v Dataverse](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365). Nemeňte názov toku údajov v Power Platform centrum spravovania, ktoré sa používa v Customer Insights. Premenovanie toku údajov spôsobuje problémy s referenciami medzi Customer Insights zdroj údajov a Dataverse dátový tok.
> - Súbežné hodnotenia pre Power Query zdroje údajov v Customer Insights majú to isté [obnovovacie limity ako Dataflows v PowerBI.com](/power-query/power-query-online-limits#refresh-limits). Ak obnova údajov zlyhá, pretože dosiahla limit hodnotenia, odporúčame vám upraviť plán obnovy pre každý tok údajov, aby ste zabezpečili, že zdroje údajov nebudú spracované v rovnakom čase.

### <a name="available-power-query-data-sources"></a>Dostupné Power Query zdroje dát

Pozrite si [Power Query odkaz na konektor](/power-query/connectors/) nájdete zoznam konektorov, ktoré môžete použiť na import údajov do Customer Insights.

Konektory so začiarknutím v **Customer Insights (toky údajov)** na vytvorenie nových zdrojov údajov na základe Power Query. Pozrite si dokumentáciu konkrétneho konektora, aby ste sa dozvedeli viac o jeho predpokladoch, [obmedzenia dopytov](/power-query/power-query-online-limits) a ďalšie podrobnosti.

## <a name="add-data-from-on-premises-data-sources"></a>Pridajte údaje z lokálny zdrojov údajov

Príjem údajov zo zdrojov údajov lokálny je podporovaný na základe Microsoft Power Platform dátové toky (PPDF). V Customer Insights môžete povoliť toky údajov pomocou [poskytovanie Microsoft Dataverse URL prostredia](create-environment.md) pri nastavovaní prostredia.

Zdroje údajov, ktoré sa vytvoria po priradení a Dataverse prostredie s využitím Customer Insights [Power Platform dátové toky](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) predvolene. Dátové toky podporujú lokálne pripojenie pomocou brány údajov. Môžete odstrániť a znovu vytvoriť zdroje údajov, ktoré existovali pred a Dataverse prostredie bolo spojené [pomocou dátových brán lokálny](/data-integration/gateway/service-gateway-app).

Dátové brány z existujúcich Power BI alebo Power Apps prostredie bude viditeľné a môžete ich znova použiť v Customer Insights, ak sa brána údajov a prostredie Customer Insights nachádzajú v rovnakej oblasti Azure. Na stránke zdrojov údajov sú zobrazené odkazy smerujúce do prostredia Microsoft Power Platform, v ktorom si môžete prezerať a konfigurovať lokálne brány údajov.

> [!IMPORTANT]
> Uistite sa, že sú vaše brány aktualizované na najnovšiu verziu. Aktualizáciu a prekonfigurovanie brány môžete nainštalovať priamo z výzvy zobrazenej na obrazovke brány alebo [stiahnite si najnovšiu verziu](https://powerapps.microsoft.com/downloads/). Ak nepoužívate najnovšiu verziu brány, obnovenie toku údajov zlyhá s chybovými hláseniami, ako napr **Kľúčové slovo nie je podporované: konfiguračné vlastnosti. Názov parametra: kľúčové slovo**.
>
> Chyby lokálny dátových brán v Customer Insights sú často spôsobené problémami s konfiguráciou. Ďalšie informácie o riešení problémov s dátovými bránami nájdete v časti [Riešenie problémov s dátovou bránou lokálny](/data-integration/gateway/service-gateway-tshoot).

## <a name="edit-power-query-data-sources"></a>Upraviť Power Query zdroje dát

> [!NOTE]
> Možno nebude možné vykonať zmeny v zdrojoch údajov, ktoré sa momentálne používajú v niektorom z procesov aplikácie (napríklad segmentácia alebo zjednotenie údajov).
>
> V **nastavenie** môžete sledovať priebeh každého z aktívnych procesov. Po dokončení procesu sa môžete vrátiť na stránku **Zdroje údajov** a vykonať zmeny.

1. Prejdite do **Údaje** > **Zdroje údajov**.

1. Vedľa zdroj údajov, ktorý chcete aktualizovať, vyberte **Upraviť**.

1. Aplikujte svoje zmeny a transformácie v **Power Query - Upraviť otázky** dialóg, ako je popísané v [Vytvorte nový zdroj údajov](#create-a-new-data-source) oddiele.

1. Vyberte **Uložiť** aplikujte zmeny a vráťte sa do **Zdroje dát** stránku.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="common-reasons-for-ingestion-errors-or-corrupt-data"></a>Bežné dôvody chýb príjmu alebo poškodených údajov

### <a name="data-type-does-not-match-data"></a>Typ údajov sa nezhoduje s údajmi

Najbežnejšia nezhoda typu údajov sa vyskytuje, keď pole dátumu nie je nastavené na správny formát dátumu.

Údaje je možné opraviť v zdroji a znova ich spracovať. Alebo opravte transformáciu v rámci Customer Insights. Ak chcete opraviť transformáciu:

1. Prejdite do **Údaje** > **Zdroje údajov**.

1. Vedľa zdroj údajov s poškodenými údajmi vyberte **Upraviť**.

1. Vyberte **Ďalej**.

1. Vyberte každý z dotazov a vyhľadajte transformácie použité v časti „Použité kroky“, ktoré sú nesprávne, alebo stĺpce dátumu, ktoré neboli transformované pomocou formátu dátumu.

   :::image type="content" source="media/PQ_corruped_date.png" alt-text="Power Query- Úprava zobrazujúca nesprávny formát dátumu":::

1. Zmeňte typ údajov tak, aby sa správne zhodovali s údajmi.

1. Vyberte **Uložiť**. To zdroj údajov je obnovené.

## <a name="troubleshoot-ppdf-power-query-based-data-source-refresh-issues"></a>Riešenie problémov s PPDF Power Query -založené zdroj údajov problémy s obnovením

Ak sú údaje zastarané alebo sa po obnovení zdroj údajov zobrazujú chyby, vykonajte tieto kroky:

1. Prejdite na [Power Platform](https://make.powerapps.com).

1. Vyberte **Životné prostredie** pre vašu inštanciu Customer Insights.

1. Prejdite na **Dátové toky**.

1. Pre tok údajov, ktorý zodpovedá zdroj údajov v Customer Insights, vyberte zvislú elipsu (&vellip;) a potom vyberte **Zobraziť históriu obnovenia**.

1. Ak **Postavenie** dátového toku je **Úspech**, vlastníctvom Power Query -založené zdroj údajov sa mohlo zmeniť:

   1. Skontrolujte plán obnovenia z histórie obnovenia.
   1. Nastavte plán nového vlastníka a uložte nastavenia.

1. Ak **Postavenie** dátového toku je **Nepodarilo sa**:

   1. Stiahnite si súbor histórie obnovenia.
   1. V stiahnutom súbore skontrolujte príčinu zlyhania.
   1. Ak sa chyba nedá vyriešiť, vyberte **?** Na otvorenie lístka podpory. Zahrňte stiahnutý súbor histórie obnovenia.


[!INCLUDE [footer-include](includes/footer-banner.md)]
