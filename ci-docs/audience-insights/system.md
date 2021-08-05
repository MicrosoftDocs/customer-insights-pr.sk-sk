---
title: Konfigurácia systému v prehľadoch cieľových skupín
description: Prečítajte si viac informácií o systémových nastaveniach vo funkcii prehľadov o cieľových skupinách v Dynamics 365 Customer Insights.
ms.date: 02/12/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 32bb89b02947350c056c8ce8adbe37500d2099a1
ms.sourcegitcommit: dab2cbf818fafc9436e685376df94c5e44e4b144
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 07/13/2021
ms.locfileid: "6556097"
---
# <a name="system-configuration"></a>Konfigurácia systému

Stránka **Systém** obsahuje nasledujúce karty:
- [Status](#status-tab)
- [Plánovanie](#schedule-tab)
- [Využitie rozhrania API](#api-usage-tab)
- [Informácie](#about-tab)
- [Všeobecné](#general-tab)

> [!div class="mx-imgBorder"]
> ![Systémová stránka.](media/system-tabs.png "Systémová stránka")

## <a name="status-tab"></a>Karta stavu

**Karta Stav** vám umožňuje sledovať postup prijímania údajov, exportu údajov a niekoľko ďalších dôležitých procesov produktu. Skontrolujte informácie na tejto karte a zaistite úplnosť aktívnych procesov.

Táto karta obsahuje tabuľky so stavom a informáciami o spracovaní pre rôzne procesy. Každá tabuľka sleduje **Názov** úlohy a jej zodpovedajúcej entity, **Stav** jej posledného spustenia a kedy bola **Naposledy aktualizovaná**.

Pozrite si podrobnosti o posledných niekoľkých spusteniach úloh výberom názvu.

### <a name="status-types"></a>Typy stavov

Existuje šesť druhov stavov pre úlohy. Nasledujúce typy stavov sa tiež zobrazujú na stránkach *Spárovať*, *Zlúčiť*, *Zdroje údajov*, *Segmenty*, *Miery*, *Obohatenie*, *Aktivity* a *Predikcie*:

- **Spracovanie:** Úloha práve prebieha. Stav sa môže zmeniť na Úspešné alebo Zlyhanie.
- **Úspešný:** Úloha bola úspešne dokončená.
- **Vynechané:** Úloha bola vynechaná. Jeden alebo viac následných procesov, od ktorých závisí táto úloha, zlyháva alebo sú preskočené.
- **Zlyhanie:** Spracovanie úlohy zlyhalo.
- **Zrušené:** Spracovanie bolo zrušené používateľom pred jeho dokončením.
- **Vo fronte:** Spracovanie je vo fronte a začne sa po dokončení všetkých predchádzajúcich úloh. Ďalšie informácie získate v článku [Politiky obnovenia](#refresh-policies).

### <a name="refresh-policies"></a>Politiky obnovenia

Tento zoznam zobrazuje zásady obnovovania pre každý z hlavných procesov:

- **Zdroje dát:** Beží podľa [nakonfigurovaného harmonogramu](#schedule-tab). Nezávisí od žiadneho iného procesu. Zhoda závisí od úspešného ukončenia tohto procesu.
- **Zhoda:** Beží podľa [nakonfigurovaného harmonogramu](#schedule-tab). Závisí od spracovania zdrojov údajov použitých v definícii zhody. Zlúčenie závisí od úspešného ukončenia tohto procesu.
- **Zlúčenie:** Beží podľa [nakonfigurovaného harmonogramu](#schedule-tab). Závisí od úspešného ukončenia procesu zhody. Segmenty, miery, obohatenie, vyhľadávanie, aktivity, predikcie a príprava dát závisia od úspešného ukončenia tohto procesu.
- **Segmenty**: Spustí sa manuálne (jednorazové obnovenie) a podľa [nakonfigurovaného harmonogramu](#schedule-tab). Závisí od zlúčenia. Štatistiky závisia od spracovania.
- **Miery**: Spustí sa manuálne (jednorazové obnovenie) a podľa [nakonfigurovaného harmonogramu](#schedule-tab). Závisí od zlúčenia.
- **Aktivity**: Spustí sa manuálne (jednorazové obnovenie) a podľa [nakonfigurovaného harmonogramu](#schedule-tab). Závisí od zlúčenia.
- **Obohatenie**: Spustí sa manuálne (jednorazové obnovenie) a podľa [nakonfigurovaného harmonogramu](#schedule-tab). Závisí od zlúčenia.
- **Vyhľadávanie**: Spustí sa manuálne (jednorazové obnovenie) a podľa [nakonfigurovaného harmonogramu](#schedule-tab). Závisí od zlúčenia.
- **Príprava dát:** Beží podľa [nakonfigurovaného harmonogramu](#schedule-tab). Závisí od zlúčenia.
- **Analýzy**: Spustí sa manuálne (jednorazové obnovenie) a podľa [nakonfigurovaného harmonogramu](#schedule-tab). Závisí od segmentov.

Vyberte stav úlohy, ak chcete zobraziť podrobnosti o priebehu celej úlohy, v ktorej bol. Vyššie uvedené pravidlá obnovenia vám môžu pomôcť pochopiť, čo môžete urobiť, aby ste vyriešili úlohu **Vynechané** alebo **Vo fronte**.

## <a name="schedule-tab"></a>Karta Plán

Použite kartu **Plán** na naplánovanie automatického obnovenie všetkých vašich [prijatých zdrojov údajov](data-sources.md). Automatické obnovovanie pomáha zaistiť, aby sa aktualizácie z vašich zdrojov údajov prejavili vo vašich zjednotených profiloch zákazníkov.

1. V prehľadoch cieľových skupín prejdite na **Správca** > **Systém** a vyberte kartu **Plán**.

2. Predvolený stav plánovanej obnovy je **Vyp.** Ak chcete povoliť naplánované obnovovanie, zmeňte prepínač v hornej časti obrazovky na **Zap.**

3. Vyberte si medzi **Týždenné** (predvolené) a **Denné** obnovenie. Ak chcete naplánovať týždenné obnovovanie, vyberte jeden alebo viac dní, v ktorých chcete obnovenie spustiť.

4. Nastavte si **Časové pásmo**, potom použite rozbaľovaciu ponuku **Čas** a nastavte časovanie obnovenia. Po dokončení vyberte **Nastaviť**. Ak chcete naplánovať viac aktualizácií za jeden deň, vyberte položku **Pridať ďalší čas**.

5. Zmeny vykonajte výberom položky **Uložiť**.

## <a name="about-tab"></a>Karta Informácie o systéme

Karta **Informácie** obsahuje **Zobrazovaný názov** vašej organizácie, aktívne **ID prostredia**, **Región** a vaše **ID relácie**. Ak máte viac ako jedno pracovné prostredie, mali by ste každému dať ľahko identifikovateľný zobrazovaný názov.

## <a name="general-tab"></a>Karta Všeobecné

Na karte **Všeobecné**, **Jazyk** a **Formát krajiny/regiónu** existujú dve možnosti.

Aplikácia [podporuje rad jazykov](supported-languages.md). Ak chcete zmeniť preferovaný jazyk, vyberte z rozbaľovacej ponuky **Jazyk**.

Ak chcete zmeniť preferované formátovanie pre dátumy, čas a čísla, použite rozbaľovaciu ponuku **Formát krajiny alebo oblasti**. Pod týmto poľom sa zobrazí ukážka formátovania. Keď zvolíte nový jazyk, systém automaticky navrhne výber.

Zmeny potvrďte výberom položky **Uložiť**.

## <a name="api-usage-tab"></a>Karta použitia rozhrania API

Nájdite podrobnosti o použití API v reálnom čase a uvidíte, ktoré udalosti sa stali v danom časovom rámci. Časový rámec si zvolíte z položky rozbaľovacieho zoznamu **Vyberte časový rámec**. 

**Využitie API** obsahuje tri časti: 
- **Volania API** – graf, ktorý vizualizuje agregovaný počet volaní API vo vybranom časovom rámci.

- **Prenos údajov** – graf, ktorý zobrazuje množstvo dát, ktoré boli prenesené cez API vo vybranom časovom rámci.

-  **Operácie** – tabuľka s riadkami pre každú dostupnú operáciu API a podrobnosťami o použití týchto operácií. Môžete zvoliť názov operácie, a prejsť na [referenčnú príručku rozhrania API](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances).

   Operácie, ktoré využívajú [príjem údajov v reálnom čase](real-time-data-ingestion.md) obsahujú tlačidlo so symbolom ďalekohľadu na zobrazenie použitia API v reálnom čase. Výberom tohto tlačidla otvoríte bočnú tablu obsahujúcu podrobnosti o použití rozhrania API v reálnom čase v aktuálnom prostredí.   
   Použite políčko **Zoskupiť podľa** na table **Využitie API v reálnom čase** a vyberte, ako najlepšie prezentovať svoje interakcie v reálnom čase. Údaje môžete zoskupiť podľa metódy API, kvalifikovaného názvu entity (prijatá entita), spôsobu vytvorenia (zdroj udalosti), výsledku (úspech alebo zlyhanie) alebo chybových kódov. Dáta sú k dispozícii ako graf histórie a ako tabuľka.


[!INCLUDE[footer-include](../includes/footer-banner.md)]