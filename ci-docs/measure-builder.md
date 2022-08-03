---
title: Vytvorte opatrenia pomocou nástroja na tvorbu opatrení
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
ms.openlocfilehash: fac00b8a1b4ca6e09dd29abe46dfe240adcc029e
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 07/18/2022
ms.locfileid: "9170884"
---
# <a name="create-measures-with-measure-builder"></a>Vytvorte opatrenia pomocou nástroja na tvorbu opatrení

Nástroj Measure Builder vám umožňuje definovať výpočty pomocou matematických operátorov, agregačných funkcií a filtrov. Definujte miery pomocou atribútov z entít, ktoré súvisia s jednotným *Zákazník* subjekt.

Vytváranie mier v prostrediach B-to-C a B-to-B funguje rovnakým spôsobom. Ak však vaše prostredie B-to-B [používa účty s hierarchiami](relationships.md#set-up-account-hierarchies), vyberte, či chcete agregovať mieru medzi súvisiacimi podúčtami.

# <a name="individual-consumers-b-to-c"></a>[Jednotliví spotrebitelia (firma a spotrebiteľ)](#tab/b2c)

Vytvorte opatrenia na úrovni jednotlivých zákazníkov (atribút zákazníka, opatrenie zákazníka) alebo na úrovni podniku/organizácie (podnikateľské opatrenie). Atribút zákazníka a meranie zákazníka vám umožňujú sledovať výkon na zákazníka. Napríklad celkové výdavky každého zákazníka. Podnik meria výkonnosť jednotlivých podnikov. Napríklad celkový príjem spoločnosti.

- Atribút zákazníka: Vygeneruje výstup ako nový atribút, ktorý sa uloží ako nový stĺpec v entite vygenerovanej systémom s názvom *Customer_Measure*. Pri obnovovaní atribútu zákazníka sa všetky ostatné atribúty zákazníka v *Customer_Measure* obnovenie entity súčasne. Okrem toho sú atribúty zákazníka zobrazené na karte profilu zákazníka. Po spustení alebo uložení už nemôžete zmeniť atribút zákazníka na mieru zákazníka.

- Zákaznícke meranie: Generuje výstup ako vlastnú entitu a po spustení alebo uložení ho nemôžete zmeniť na atribút zákazníka. Merania zákazníka sa nezobrazujú na karte profilu zákazníka.

- Obchodné meranie: Generuje výstup ako vlastnú entitu a zobrazuje sa na domovskej stránke vášho prostredia Customer Insights.

1. Ísť do **Opatrenia**.

1. Vyberte položku **Nový** > **Vytvorte si vlastný**.

   :::image type="content" source="media/measure-b2c.png" alt-text="Prázdna konfiguračná obrazovka pre meranie B-to-C." lightbox="media/measure-b2c.png":::

1. Vyberte **Upraviť podrobnosti** vedľa Bez názvu. Zadajte názov opatrenia. Prípadne pridajte [značky](work-with-tags-columns.md#manage-tags) na mieru.

   :::image type="content" source="media/measures_edit_details.png" alt-text="Dialógové okno Upraviť podrobnosti.":::

1. Vyberte položku **Hotovo**.

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

1. Vyberte **Pridať atribút** vyberte údaje na vytvorenie tejto miery.

   1. Vyberte karty **Atribúty**.
   1. Dátová entita: Vyberte entitu, ktorá obsahuje atribút, ktorý chcete merať.
   1. Atribút údajov: Vyberte atribút, ktorý chcete použiť vo funkcii agregácie na výpočet miery. Môžete vybrať iba jeden atribút naraz.
   1. Voliteľne vyberte atribút údajov z existujúcej miery výberom položky **Opatrenia** alebo vyhľadajte názov entity alebo miery.
   1. Stlačte možnosť **Pridať**.

1. Ak chcete vytvoriť zložitejšie miery, pridajte ďalšie atribúty alebo použite matematické operátory vo svojej funkcii merania.

1. Ak chcete pridať filtre, vyberte **Filtrovať** v konfiguračnej oblasti. Pri použití filtrov sa na výpočet miery použijú iba záznamy, ktoré zodpovedajú filtrom.
  
   1. V sekcii **Pridať atribút** na table **Filtre** vyberte atribút, ktorý chcete použiť na vytvorenie filtrov.
   1. Nastavte operátory filtra tak, aby definovali filter pre každý vybraný atribút.
   1. Vyberte **Použiť**.

1. Vyberte **Rozmer** vyberte viac polí, ktoré sa majú pridať ako stĺpce do entity výstupu merania.

   1. Vyberte **Upraviť dimenzie**, ak chcete pridať atribúty údajov, podľa ktorých chcete zoskupiť namerané hodnoty. Napríklad mesto alebo pohlavie.
      > [!TIP]
      > Ak ste vybrali **Zákaznícka úroveň** ako **Typ merania** na *CustomerId* atribút je už pridaný. Ak atribút odstránite, **Typ merania** prepne na **Obchodná úroveň**.
   1. Vyberte položku **Hotovo**.

1. Ak sú vo vašich údajoch hodnoty, ktoré je potrebné nahradiť celým číslom, vyberte **pravidlá**. Nakonfigurujte pravidlo a uistite sa, že ste ako náhradu vybrali iba celé čísla. Napríklad nahraďte *null* s *0*.

1. Ak existuje viacero ciest medzi dátovou entitou, ktorú ste mapovali, a *Zákazník* subjekt, vyberte jeden z identifikovaných [cesty vzťahu entít](relationships.md). Výsledky mier sa môžu líšiť v závislosti od zvoleného postupu.

   1. Vyberte **Cesta vyjadrujúca vzťah** a vyberte cestu entity, ktorá by mala byť použitá na identifikáciu vašej miery. Ak existuje iba jedna cesta k entite *Zákazník*, tento ovládací prvok sa nezobrazí.
   1. Vyberte položku **Hotovo**.

1. Ak chcete pridať ďalšie výpočty miery, vyberte položku **Nový výpočet**. Na nové výpočty používajte iba entity na rovnakej ceste entity. Ďalšie výpočty sa zobrazia ako nové stĺpce v entite výstupu miery. Voliteľne vyberte **Upraviť meno** na vytvorenie názvu pre výpočet.

1. Vyberte zvislú elipsu (&vellip;) o výpočte na **Duplicitné** alebo **Odstrániť** výpočet z opatrenia.

1. V oblasti **Ukážka** uvidíte dátovú schému entity výstupu miery vrátane filtrov a dimenzií. Ukážka dynamicky reaguje na zmeny v konfigurácii.

1. Vyberte **Spustiť** na výpočet výsledkov pre nakonfigurovanú mieru. Vyberte **Uložiť a zavrieť**, ak si chcete ponechať aktuálnu konfiguráciu a mieru spustiť neskôr. The **Opatrenia** zobrazí stránka.

# <a name="business-accounts-b-to-b"></a>[Firemné obchodné vzťahy (firma a firma)](#tab/b2b)

Vytvárajte opatrenia na úrovni jednotlivých účtov (zákaznícke opatrenie) alebo na úrovni všetkých účtov (obchodné opatrenie).

- Zákaznícke meranie: Vytvára výstup ako vlastný subjekt. Merania zákazníka sa nezobrazujú na karte profilu zákazníka.

- Obchodné meranie: Generuje výstup ako vlastnú entitu a zobrazuje sa na domovskej stránke vášho prostredia Customer Insights.

1. Ísť do **Opatrenia**.

1. Vyberte **Nové**.

   :::image type="content" source="media/measure-b2b.png" alt-text="Prázdna konfiguračná obrazovka pre meranie B-to-B.":::

1. Vyberte **Upraviť podrobnosti** vedľa Bez názvu. Zadajte názov opatrenia. Prípadne pridajte [značky](work-with-tags-columns.md#manage-tags) na mieru. 
   :::image type="content" source="media/measures_edit_details.png" alt-text="Dialógové okno Upraviť podrobnosti.":::

1. Vyberte položku **Hotovo**.

1. V oblasti konfigurácie vyberte funkciu agregácie z **Vyberte funkciu** rozbaľovacia ponuka. Medzi agregačné funkcie patria:
   - **Sum**
   - **Priemer**
   - **Obchodný vzťah**
   - **Počet jedinečných**
   - **Max**
   - **Minimum**
   - **Prvé**: berie prvú hodnotu dátového záznamu
   - **Posledné**: berie poslednú hodnotu, ktorá bola pridaná do dátového záznamu

1. Vyberte **Pridať atribút** vyberte údaje na vytvorenie tejto miery.

   1. Vyberte karty **Atribúty**.
   1. Dátová entita: Vyberte entitu, ktorá obsahuje atribút, ktorý chcete merať.
   1. Atribút údajov: Vyberte atribút, ktorý chcete použiť vo funkcii agregácie na výpočet miery. Môžete vybrať iba jeden atribút naraz.
   1. Voliteľne vyberte atribút údajov z existujúcej miery výberom položky **Opatrenia** alebo vyhľadajte názov entity alebo miery.
   1. Vyberte **Pridať** na pridanie vybraného atribútu k miere.

1. Ak chcete vytvoriť zložitejšie miery, pridajte ďalšie atribúty alebo použite matematické operátory vo svojej funkcii merania.

1. Ak chcete pridať filtre, vyberte **Filtrovať** v konfiguračnej oblasti. Pri použití filtrov sa na výpočet miery použijú iba záznamy, ktoré zodpovedajú filtrom.
  
   1. V sekcii **Pridať atribút** na table **Filtre** vyberte atribút, ktorý chcete použiť na vytvorenie filtrov.
   1. Nastavte operátory filtra tak, aby definovali filter pre každý vybraný atribút.
   1. Vyberte **Použiť** na pridanie filtrov k miere.

1. Vyberte **Rozmer** vyberte viac polí, ktoré sa majú pridať ako stĺpce do entity výstupu merania.

   1. Vyberte **Upraviť dimenzie**, ak chcete pridať atribúty údajov, podľa ktorých chcete zoskupiť namerané hodnoty. Napríklad mesto alebo pohlavie.
      > [!TIP]
      > The *CustomerId* atribút je už pridaný, čo znamená, že ide o typ merania na úrovni zákazníka. Ak atribút odstránite, typ miery sa zmení na obchodnú úroveň.
   1. Vyberte **Hotovo** na pridanie dimenzie k miere.

1. Ak sú vo vašich údajoch hodnoty, ktoré je potrebné nahradiť celým číslom, vyberte **pravidlá**. Nakonfigurujte pravidlo a uistite sa, že ste ako náhradu vybrali iba celé čísla. Napríklad nahraďte *null* s *0*.

1. Ak ty [používať účty s hierarchiou](relationships.md#set-up-account-hierarchies), preskúmanie **Zrolovať podúčty**.
   - Ak je nastavené na **Vyp.** miera sa vypočíta pre každý obchodný vzťah. Každý účet dostane svoj vlastný výsledok.
   - Ak je nastavený na **Zap.**, vyberte **Upraviť** a zvoľte hierarchiu účtov podľa prijatých hierarchií. Meranie prinesie iba jeden výsledok, pretože je agregované s podúčtami.

1. Ak existuje viacero ciest medzi dátovou entitou, ktorú ste mapovali, a *Zákazník* subjekt, vyberte jeden z identifikovaných [cesty vzťahu entít](relationships.md). Výsledky mier sa môžu líšiť v závislosti od zvoleného postupu.

   1. Vyberte **Cesta vyjadrujúca vzťah** a vyberte cestu entity, ktorá by mala byť použitá na identifikáciu vašej miery. Ak existuje iba jedna cesta k entite *Zákazník*, tento ovládací prvok sa nezobrazí.
   1. Výberom možnosti **Hotovo** použite svoj výber.

1. Vyberte zvislú elipsu (&vellip;) o výpočte na **Duplicitné** alebo **Odstrániť** výpočet z opatrenia.

1. V oblasti **Ukážka** uvidíte dátovú schému entity výstupu miery vrátane filtrov a dimenzií. Ukážka dynamicky reaguje na zmeny v konfigurácii.

1. Vyberte **Spustiť** na výpočet výsledkov pre nakonfigurovanú mieru. Vyberte **Uložiť a zavrieť**, ak si chcete ponechať aktuálnu konfiguráciu a mieru spustiť neskôr. The **Opatrenia** zobrazí stránka.

---

## <a name="next-step"></a>Ďalší krok

Na vytvorenie použite existujúce opatrenia [zákaznícky segment](segments.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
