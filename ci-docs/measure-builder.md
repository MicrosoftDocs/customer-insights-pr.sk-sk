---
title: Vytvorte nové opatrenia pomocou nástroja na tvorbu opatrení
description: Vytvárajte opatrenia od začiatku a analyzujte kľúčové metriky o svojom podnikaní.
ms.date: 03/25/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: v-wendysmith
ms.author: wameng
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-measure-builder
- customerInsights
ms.openlocfilehash: d003d054145343cc2feeefeeee413810df43185a
ms.sourcegitcommit: b515120bebd2638f2639004422cee3cff42fbdf7
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 05/24/2022
ms.locfileid: "8800345"
---
# <a name="use-measure-builder-to-create-measures-from-scratch"></a>Použite nástroj na tvorbu opatrení na vytvorenie opatrení od začiatku

Tento článok vysvetľuje, ako vytvoriť nový [opatrenie](measures.md) od nuly. Nástroj na tvorbu opatrení vám umožňuje definovať výpočty pomocou matematických operátorov, agregačných funkcií a filtrov. Môžete vytvoriť mieru s atribútmi z entít, ktoré súvisia s jednotným *Zákazník* subjekt.

Vytváranie mier v prostrediach B-to-C a B-to-B funguje rovnakým spôsobom. Avšak, ak ste B-to-B prostredie [používa účty s hierarchiami](relationships.md#set-up-account-hierarchies), môžete sa rozhodnúť agregovať mieru medzi súvisiacimi podúčtami.

Mieru môžete tiež rýchlo vytvoriť výberom zo súboru bežne používaných a preddefinovaných mier. Ďalšie informácie nájdete v časti [Na vytvorenie miery použite šablónu](measure-templates.md).

# <a name="individual-consumers-b-to-c"></a>[Jednotliví spotrebitelia (firma a spotrebiteľ)](#tab/b2c)

Môžete vytvárať miery na úrovni jednotlivých zákazníkov (atribút zákazníka, miera zákazníka) alebo na úrovni podniku/organizácie (obchodné opatrenie). Atribút zákazníka a miera zákazníka sú dva typy, ktoré vám umožňujú sledovať výkonnosť na zákazníka. Napríklad celkové výdavky každého zákazníka. Obchodné opatrenia vám umožňujú sledovať výkonnosť jednotlivých podnikov. Napríklad celkový príjem spoločnosti.

- Atribút zákazníka: Vygeneruje výstup ako nový atribút, ktorý sa uloží ako nový stĺpec v entite vygenerovanej systémom s názvom *Customer_Measure*. Pri obnovovaní atribútu zákazníka sa všetky ostatné atribúty zákazníka v *Customer_Measure* obnovenie entity súčasne. Okrem toho sú atribúty zákazníka zobrazené na karte profilu zákazníka. Po spustení alebo uložení atribútu zákazníka ho nemôžete zmeniť na mieru zákazníka.

- Zákaznícke meranie: Generuje výstup ako svoju vlastnú entitu a po spustení alebo uložení ho nemôžete zmeniť na atribút zákazníka. Zákaznícke miery sa nezobrazujú na karte profilu zákazníka.

- Obchodné meranie: Generuje výstup ako vlastnú entitu a zobrazuje sa na domovskej stránke vášho prostredia Customer Insights.

1. Ísť do **Opatrenia**.

1. Vyberte **Nový** a stlačte **Vytvorte si vlastnú**.

   :::image type="content" source="media/measure-b2c.png" alt-text="Prázdna konfiguračná obrazovka pre meranie B-to-C." lightbox="media/measure-b2c.png":::

1. Ak chcete sledovať výkonnosť na úrovni podniku, prepnite **Typ merania** do **Obchodná úroveň**. **Zákaznícka úroveň** je predvolene vybratá. **Zákaznícka úroveň** automaticky pridá *CustomerId* priradiť k dimenziám while **Obchodná úroveň** automaticky ho odstráni.

1. V oblasti konfigurácie vyberte funkciu agregácie z **Vyberte funkciu** rozbaľovacia ponuka. Medzi agregačné funkcie patria:
   - **Sum**
   - **Priemer**
   - **Obchodný vzťah**
   - **Počet jedinečných**
   - **Max**
   - **Minimum**
   - **Prvé**: berie prvú hodnotu dátového záznamu
   - **Posledné**: berie poslednú hodnotu, ktorá bola pridaná do dátového záznamu
   - **ArgMax** : nájde dátový záznam poskytujúci maximálnu hodnotu z cieľovej funkcie
   - **ArgMin** : nájde dátový záznam s minimálnou hodnotou z cieľovej funkcie

1. Vyberte **Pridať atribút** a vyberte údaje, ktoré potrebujete na vytvorenie tejto miery.

   1. Vyberte karty **Atribúty**.
   1. Dátová entita: Vyberte entitu, ktorá obsahuje atribút, ktorý chcete merať.
   1. Atribút údajov: Vyberte atribút, ktorý chcete použiť vo funkcii agregácie na výpočet miery. Môžete vybrať iba jeden atribút naraz.
   1. Atribút údajov môžete vybrať aj z existujúcej miery výberom karty **Miery**. Alebo môžete vyhľadať názov entity alebo miery.
   1. Vyberte **Pridať** na pridanie vybraného atribútu k miere.

1. Ak chcete vytvoriť zložitejšie miery, môžete pridať ďalšie atribúty alebo použiť matematické operátory svojej funkcie miery.

1. Ak chcete pridať filtre, vyberte **Filtrovať** v konfiguračnej oblasti. Pri použití filtrov sa na výpočet miery použijú iba záznamy, ktoré zodpovedajú filtrom.
  
   1. V sekcii **Pridať atribút** na table **Filtre** vyberte atribút, ktorý chcete použiť na vytvorenie filtrov.
   1. Nastavte operátory filtra tak, aby definovali filter pre každý vybraný atribút.
   1. Vyberte **Použiť** na pridanie filtrov k miere.

1. Vyberte **Rozmer** vyberte viac polí, ktoré sa pridajú ako stĺpce do entity výstupu merania.

   1. Vyberte **Upraviť dimenzie**, ak chcete pridať atribúty údajov, podľa ktorých chcete zoskupiť namerané hodnoty. Napríklad mesto alebo pohlavie.
   > [!TIP]
   > Ak ste vybrali **Zákaznícka úroveň** ako **Typ merania** a *CustomerId* atribút je už pridaný. Ak odstránite atribút, **Typ merania** prepne na **Obchodná úroveň**.
   1. Vyberte **Hotovo** na pridanie dimenzie k miere.

1. Ak vo vašich údajoch existujú hodnoty, ktoré je potrebné nahradiť celým číslom, vyberte položku **Pravidlá**. Nakonfigurujte pravidlo a uistite sa, že ste ako náhradu vybrali iba celé čísla. Napríklad nahraďte *null* s *0*.

1. Ak existuje viac postupov medzi dátovou entitou, ktorú ste mapovali, a entitou *zákazníka*, musíte zvoliť jednu z identifikovaných [postupov vzťahov medzi entitami](relationships.md). Výsledky mier sa môžu líšiť v závislosti od zvoleného postupu.

   1. Vyberte **Cesta vyjadrujúca vzťah** a vyberte cestu entity, ktorá by mala byť použitá na identifikáciu vašej miery. Ak existuje iba jedna cesta k entite *Zákazník*, tento ovládací prvok sa nezobrazí.
   1. Výberom možnosti **Hotovo** použite svoj výber.

1. Ak chcete pridať ďalšie výpočty miery, vyberte položku **Nový výpočet**. Na nové výpočty môžete použiť iba entity v tom istom postupe entity. Ďalšie výpočty sa zobrazia ako nové stĺpce v entite výstupu miery.

1. Vyberte zvislú elipsu (&vellip;) o výpočte na **Duplicitné**, **·**, alebo **Odstrániť** výpočet z opatrenia.

1. V oblasti **Ukážka** uvidíte dátovú schému entity výstupu miery vrátane filtrov a dimenzií. Ukážka dynamicky reaguje na zmeny v konfigurácii.

1. Vyberte **Upraviť podrobnosti** vedľa Bez názvu. Zadajte názov opatrenia. Prípadne pridajte [značky](work-with-tags-columns.md#manage-tags) na mieru.

   :::image type="content" source="media/measures_edit_details.png" alt-text="Dialógové okno Upraviť podrobnosti.":::

1. Vyberte **Spustiť** na výpočet výsledkov pre nakonfigurovanú mieru. Vyberte **Uložiť a zavrieť**, ak si chcete ponechať aktuálnu konfiguráciu a mieru spustiť neskôr.

1. Prechodom na možnosť **Miery** zobrazíte novovytvorenú mieru v zozname.

# <a name="business-accounts-b-to-b"></a>[Firemné obchodné vzťahy (firma a firma)](#tab/b2b)

Opatrenia môžete vytvárať na úrovni jednotlivých účtov (zákaznícke opatrenie) alebo na úrovni všetkých účtov (obchodné opatrenie).

- Zákaznícke meranie: Vytvára výstup ako vlastný subjekt. Zákaznícke miery sa nezobrazujú na karte profilu zákazníka.

- Obchodné meranie: Generuje výstup ako vlastnú entitu a zobrazuje sa na domovskej stránke vášho prostredia Customer Insights.

1. Ísť do **Opatrenia**.

1. Vyberte **Nové**.

   :::image type="content" source="media/measure-b2b.png" alt-text="Prázdna konfiguračná obrazovka pre meranie B-to-B.":::

1. V oblasti konfigurácie vyberte funkciu agregácie z **Vyberte funkciu** rozbaľovacia ponuka. Medzi agregačné funkcie patria:
   - **Sum**
   - **Priemer**
   - **Obchodný vzťah**
   - **Počet jedinečných**
   - **Max**
   - **Minimum**
   - **Prvé**: berie prvú hodnotu dátového záznamu
   - **Posledné**: berie poslednú hodnotu, ktorá bola pridaná do dátového záznamu

1. Vyberte **Pridať atribút** a vyberte údaje, ktoré potrebujete na vytvorenie tejto miery.

   1. Vyberte karty **Atribúty**.
   1. Dátová entita: Vyberte entitu, ktorá obsahuje atribút, ktorý chcete merať.
   1. Atribút údajov: Vyberte atribút, ktorý chcete použiť vo funkcii agregácie na výpočet miery. Môžete vybrať iba jeden atribút naraz.
   1. Atribút údajov môžete vybrať aj z existujúcej miery výberom karty **Miery**. Alebo môžete vyhľadať názov entity alebo miery.
   1. Vyberte **Pridať** na pridanie vybraného atribútu k miere.

1. Ak chcete vytvoriť zložitejšie miery, môžete pridať ďalšie atribúty alebo použiť matematické operátory svojej funkcie miery.

1. Ak chcete pridať filtre, vyberte **Filtrovať** v konfiguračnej oblasti. Pri použití filtrov sa na výpočet miery použijú iba záznamy, ktoré zodpovedajú filtrom.
  
   1. V sekcii **Pridať atribút** na table **Filtre** vyberte atribút, ktorý chcete použiť na vytvorenie filtrov.
   1. Nastavte operátory filtra tak, aby definovali filter pre každý vybraný atribút.
   1. Vyberte **Použiť** na pridanie filtrov k miere.

1. Vyberte **Rozmer** vyberte viac polí, ktoré sa pridajú ako stĺpce do entity výstupu merania.

   1. Vyberte **Upraviť dimenzie**, ak chcete pridať atribúty údajov, podľa ktorých chcete zoskupiť namerané hodnoty. Napríklad mesto alebo pohlavie.
      > [!TIP]
      > Ak ste vybrali **Zákaznícka úroveň** ako **Typ merania** a *CustomerId* atribút je už pridaný. Ak odstránite atribút, **Typ merania** prepne na **Obchodná úroveň**.
   1. Vyberte **Hotovo** na pridanie dimenzie k miere.

1. Ak vo vašich údajoch existujú hodnoty, ktoré je potrebné nahradiť celým číslom, vyberte položku **Pravidlá**. Nakonfigurujte pravidlo a uistite sa, že ste ako náhradu vybrali iba celé čísla. Napríklad nahraďte *null* s *0*.

1. Môžete použiť prepínač **Zahrnúť podradené obchodné vzťahy**, ak [používate obchodné vzťahy s hierarchiami](relationships.md#set-up-account-hierarchies).
   - Ak je nastavené na **Vyp.** miera sa vypočíta pre každý obchodný vzťah. Každý obchodný vzťah má svoj vlastný výsledok.
   - Ak je nastavený na **Zap.**, vyberte **Upraviť** a zvoľte hierarchiu účtov podľa prijatých hierarchií. Miera prinesie iba jeden výsledok, pretože je agregovaná s podradenými obchodnými vzťahmi.

1. Ak existuje viac postupov medzi dátovou entitou, ktorú ste mapovali, a entitou *zákazníka*, musíte zvoliť jednu z identifikovaných [postupov vzťahov medzi entitami](relationships.md). Výsledky mier sa môžu líšiť v závislosti od zvoleného postupu.

   1. Vyberte **Cesta vyjadrujúca vzťah** a vyberte cestu entity, ktorá by mala byť použitá na identifikáciu vašej miery. Ak existuje iba jedna cesta k entite *Zákazník*, tento ovládací prvok sa nezobrazí.
   1. Výberom možnosti **Hotovo** použite svoj výber.

1. Vyberte zvislú elipsu (&vellip;) o výpočte na **Duplicitné**, **·**, alebo **Odstrániť** výpočet z opatrenia.

1. V oblasti **Ukážka** uvidíte dátovú schému entity výstupu miery vrátane filtrov a dimenzií. Ukážka dynamicky reaguje na zmeny v konfigurácii.

1. Vyberte **Upraviť podrobnosti** vedľa Bez názvu. Zadajte názov opatrenia. Prípadne pridajte [značky](work-with-tags-columns.md#manage-tags) na mieru.

   :::image type="content" source="media/measures_edit_details.png" alt-text="Dialógové okno Upraviť podrobnosti.":::

1. Vyberte **Spustiť** na výpočet výsledkov pre nakonfigurovanú mieru. Vyberte **Uložiť a zavrieť**, ak si chcete ponechať aktuálnu konfiguráciu a mieru spustiť neskôr.

1. Prechodom na možnosť **Miery** zobrazíte novovytvorenú mieru v zozname.