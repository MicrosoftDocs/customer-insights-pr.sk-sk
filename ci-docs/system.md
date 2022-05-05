---
title: Konfigurácia systému v Customer Insights
description: Ďalšie informácie o systémových nastaveniach nájdete v Dynamics 365 Customer Insights.
ms.date: 04/21/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-system-status
- ci-system-schedule
- ci-system-about
- ci-system-general
- ci-system-api-usage
- customerInsights
ms.openlocfilehash: 3aa4c6529d705698e612adad86587e3c3a4db35b
ms.sourcegitcommit: cf74b8c20d88eb96e1ac86e18cd44fe27aad5ab9
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 04/28/2022
ms.locfileid: "8653635"
---
# <a name="system-configuration"></a>Konfigurácia systému

Ak chcete získať prístup ku konfiguráciám systému, prejdite na **Admin** > **systém** na zobrazenie zoznamu systémových úloh a procesov.

Stránka **Systém** obsahuje nasledujúce karty:
- [Status](#status-tab)
- [Plánovanie](#schedule-tab)
- [Využitie rozhrania API](#api-usage-tab)
- [Informácie](#about-tab)
- [Všeobecné](#general-tab)

:::image type="content" source="media/system-tabs.png" alt-text="Karty nastavení na systémovej stránke.":::

## <a name="status-tab"></a>Karta stavu

The **Karta Stav** umožňuje sledovať priebeh úloh, príjem údajov, export údajov a niekoľko ďalších dôležitých procesov produktu. Skontrolujte informácie na tejto karte, aby ste sa uistili, že vaše aktívne úlohy a procesy sú úplné.

Táto karta obsahuje tabuľky so stavom a informáciami o spracovaní pre rôzne procesy. Každá tabuľka sleduje **Názov** úlohy a jej zodpovedajúcej entity, **Stav** jej posledného spustenia a kedy bola **Naposledy aktualizovaná**. Výberom názvu úlohy alebo procesu môžete zobraziť podrobnosti o niekoľkých posledných spusteniach. 

Vyberte stav vedľa úlohy alebo procesu v **Postavenie** stĺpec na otvorenie **Podrobnosti o pokroku** tabuľka.

   :::image type="content" source="media/system-progress-details.png" alt-text="Panel s podrobnosťami o priebehu systému":::

### <a name="status-definitions"></a>Definície stavu

Systém používa pre úlohy a procesy nasledujúce stavy:

|Status  |Definícia  |
|---------|---------|
|Zrušená |Spracovanie bolo pred dokončením používateľom zrušené.   |
|Zlyhalo   |Pri prijímaní údajov nastali chyby.         |
|Zlyhanie  |Spracovanie zlyhalo.  |
|Nespustené   |Zdroj údajov zatiaľ nemá žiadne prijaté údaje alebo je stále v režime konceptu.         |
|Spracováva sa  |Úloha alebo proces prebieha.  |
|Obnovuje sa    |Prebieha prijímanie údajov. Túto operáciu môžete zrušiť tak, že v stĺpci **Akcie** vyberiete **Zastaviť obnovovanie**. Zastavenie obnovovania zdroja údajov sa obnoví do posledného stavu obnovenia.       |
|Vynechané  |Úloha alebo proces boli preskočené. Jeden alebo viac následných procesov, od ktorých závisí táto úloha, zlyháva alebo sú preskočené.|
|Úspešné  |Úloha alebo proces úspešne dokončený. V prípade zdrojov údajov označuje, že údaje boli úspešne prijaté, ak je v položke uvedený čas **Osviežené** stĺpec.|
|Vo fronte | Spracovanie je zaradené do frontu a začne sa po dokončení všetkých nadradených úloh a procesov. Ďalšie informácie nájdete v časti [Obnoviť procesy](#refresh-processes).|

### <a name="refresh-processes"></a>Obnoviť procesy

Obnovenie úloh a procesov prebieha podľa [nakonfigurovaný rozvrh](#schedule-tab). 

|Spracovať  |Description  |
|---------|---------|
|Aktivita  |Spúšťa sa manuálne (jednorazové obnovenie). Závisí od procesu spájania. Štatistiky závisia od spracovania.|
|Prepojenie analýzy |Spúšťa sa manuálne (jednorazové obnovenie). Závisí od segmentov.  |
|Príprava analýzy |Spúšťa sa manuálne (jednorazové obnovenie). Závisí od segmentov.  |
|Príprava údajov   |Na spustenie potrebuje entitu. Zdroj údajov entity závisia od príjmu. Obohatené entity závisia od obohatenia. Subjekt Zákazník závisí od zlúčenia.  |
|Zdroje údajov   |Nezávisí od žiadneho iného procesu. Zhoda závisí od úspešného ukončenia tohto procesu.  |
|Obohatenia   |Spúšťa sa manuálne (jednorazové obnovenie). Závisí od procesu spájania. |
|Vývozné destinácie |Spúšťa sa manuálne (jednorazové obnovenie). Závisí od segmentov.  |
|Prehľady |Spúšťa sa manuálne (jednorazové obnovenie). Závisí od segmentov.  |
|Inteligencia   |Závisí od zlúčenia.   |
|Match |Závisí od spracovania zdrojov údajov použitých v definícii zhody.      |
|Miery  |Spúšťa sa manuálne (jednorazové obnovenie). Závisí od procesu spájania.  |
|Zlúčenie   |Závisí od úspešného ukončenia procesu zhody. Segmenty, miery, obohatenie, vyhľadávanie, aktivity, predikcie a príprava dát závisia od úspešného ukončenia tohto procesu.   |
|Profily   |Spúšťa sa manuálne (jednorazové obnovenie). Závisí od procesu spájania. |
|Vyhľadávať   |Spúšťa sa manuálne (jednorazové obnovenie). Závisí od procesu spájania. |
|Segmenty  |Spúšťa sa manuálne (jednorazové obnovenie). Závisí od procesu spájania. Štatistiky závisia od spracovania.|
|Systémové   |Závisí od úspešného ukončenia procesu zhody. Segmenty, miery, obohatenie, vyhľadávanie, aktivity, predikcie a príprava dát závisia od úspešného ukončenia tohto procesu.   |
|User  |Spúšťa sa manuálne (jednorazové obnovenie). Závisí od subjektov.  |

Výberom stavu procesu zobrazíte podrobnosti o priebehu celej úlohy, v ktorej sa nachádzal. Vyššie uvedené procesy obnovenia vám môžu pomôcť pochopiť, čo môžete urobiť, aby ste vyriešili problém a **Preskočené** alebo **Vo fronte** úloha alebo proces.

## <a name="schedule-tab"></a>Karta Plán

Použite kartu **Plán** na naplánovanie automatického obnovenie všetkých vašich [prijatých zdrojov údajov](data-sources.md). Automatické obnovovanie pomáha zaistiť, aby sa aktualizácie z vašich zdrojov údajov prejavili vo vašich zjednotených profiloch zákazníkov.

> [!NOTE]
> Vami spravované zdroje údajov sa obnovujú podľa vlastných plánov. Ak chcete naplánovať obnovenie vami spravovaných zdrojov údajov, nakonfigurujte nastavenia obnovenia na tomto konkrétnom zdroj údajov z **Zdroje dát** stránku.
> :::image type="content" source="media/PPDF-edit-refresh.png" alt-text="Power Platform Nastavenia obnovenia toku údajov.":::

1. Ísť do **Admin** > **systém** a vyberte **Rozvrh** tab.

2. Predvolený stav plánovanej obnovy je **Vyp.** Ak chcete povoliť naplánované obnovovanie, zmeňte prepínač v hornej časti obrazovky na **Zap.**

3. Vyberte si medzi **Týždenné** (predvolené) a **Denné** obnovenie. Ak chcete naplánovať týždenné obnovovanie, vyberte jeden alebo viac dní, v ktorých chcete obnovenie spustiť.

4. Nastavte si **Časové pásmo**, potom použite rozbaľovaciu ponuku **Čas** a nastavte časovanie obnovenia. Po dokončení vyberte **Nastaviť**. Ak chcete naplánovať viac aktualizácií za jeden deň, vyberte položku **Pridať ďalší čas**.

5. Zmeny vykonajte výberom položky **Uložiť**.

## <a name="about-tab"></a>Karta Informácie o systéme

Karta **Informácie** obsahuje **Zobrazovaný názov** vašej organizácie, aktívne **ID prostredia**, **Región** a vaše **ID relácie**. Ak máte viac ako jedno pracovné prostredie, mali by ste každému dať ľahko identifikovateľný zobrazovaný názov.

## <a name="general-tab"></a>Karta Všeobecné

Jazyk a formát krajiny/regiónu môžete zmeniť na karte **Všeobecné**.

Customer Insights [podporuje mnoho jazykov](/dynamics365/get-started/availability). Aplikácia použije vaše jazykové preferencie na zobrazenie prvkov, ako sú ponuka, text štítkov a systémové správy vo vašom preferovanom jazyku.

Importované údaje a informácie, ktoré ste zadali manuálne, sa neprekladajú.

### <a name="update-the-settings"></a>Aktualizácia nastavení

Ak chcete zmeniť preferovaný jazyk, vyberte z rozbaľovacej ponuky **Jazyk**.

Ak chcete zmeniť preferované formátovanie pre dátumy, čas a čísla, použite rozbaľovaciu ponuku **Formát krajiny alebo oblasti**. Pod týmto poľom sa zobrazí ukážka formátovania. Keď zvolíte nový jazyk, systém automaticky navrhne výber.

Zmeny potvrďte výberom položky **Uložiť**.

## <a name="api-usage-tab"></a>Karta použitia rozhrania API

Nájdite podrobnosti o použití API v reálnom čase a uvidíte, ktoré udalosti sa stali v danom časovom rámci. Časový rámec si zvolíte z položky rozbaľovacieho zoznamu **Vyberte časový rámec**. 

**Využitie API** obsahuje tri časti: 
- **Volania API** – graf, ktorý vizualizuje agregovaný počet volaní API vo vybranom časovom rámci.

- **Prenos údajov** – graf, ktorý zobrazuje množstvo dát, ktoré boli prenesené cez API vo vybranom časovom rámci.

-  **Operácie** – tabuľka s riadkami pre každú dostupnú operáciu API a podrobnosťami o použití týchto operácií. Môžete zvoliť názov operácie, a prejsť na [referenčnú príručku rozhrania API](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances).

   Operácie, ktoré využívajú [prijímanie údajov v reálnom čase](real-time-data-ingestion.md) obsahujú tlačidlo s binokulárnym symbolom na zobrazenie využitia API v reálnom čase. Výberom tohto tlačidla otvoríte bočnú tablu obsahujúcu podrobnosti o použití rozhrania API v reálnom čase v aktuálnom prostredí.   
   Použite políčko **Zoskupiť podľa** na table **Využitie API v reálnom čase** a vyberte, ako najlepšie prezentovať svoje interakcie v reálnom čase. Údaje môžete zoskupiť podľa metódy API, kvalifikovaného názvu entity (prijatá entita), spôsobu vytvorenia (zdroj udalosti), výsledku (úspech alebo zlyhanie) alebo chybových kódov. Dáta sú k dispozícii ako graf histórie a ako tabuľka.


[!INCLUDE [footer-include](includes/footer-banner.md)]
