---
title: Pozrite si konfiguráciu systému
description: Ďalšie informácie o systémových nastaveniach nájdete v Dynamics 365 Customer Insights.
ms.date: 08/09/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-system-status
- ci-system-about
- ci-system-general
- ci-system-api-usage
- customerInsights
ms.openlocfilehash: 6e60bf7c18939a29f660e06989e262deeb59a39b
ms.sourcegitcommit: d7054a900f8c316804b6751e855e0fba4364914b
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 09/02/2022
ms.locfileid: "9396020"
---
# <a name="view-system-configuration"></a>Pozrite si konfiguráciu systému

Zobrazenie systémových informácií, stavu systému a využitia API.

## <a name="view-api-usage"></a>Zobraziť využitie API

Pozrite si podrobnosti o používaní rozhrania API v reálnom čase a zistite, ktoré udalosti sa stali v danom časovom rámci.

1. Ísť do **Admin** > **Systém** a vyberte **Použitie API** tab.

1. **Vyberte časový rámec** zobraziť.

   The **Použitie API** stránka obsahuje tri časti:

   - **Volania API** – graf, ktorý vizualizuje agregovaný počet volaní API vo vybranom časovom rámci.
   - **Prenos údajov** – graf, ktorý zobrazuje množstvo dát, ktoré boli prenesené cez API vo vybranom časovom rámci.
   - **Operácie** – tabuľka s riadkami pre každú dostupnú operáciu API a podrobnosťami o použití týchto operácií. Vyberte názov operácie, na ktorú chcete prejsť [referenciu API](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances).

## <a name="view-system-information"></a>Zobrazenie systémových informácií

Zobrazte zobrazovaný názov prostredia, ID, región, typ a ID relácie.

1. Ísť do **Admin** > **Systém** a vyberte **O** tab.

1. Ak chcete zobraziť jazyk a krajinu/región, vyberte **generál** tab.

### <a name="update-preferred-language-or-countryregion"></a>Aktualizujte preferovaný jazyk alebo krajinu/región

Customer Insights [podporuje mnoho jazykov](/dynamics365/get-started/availability). Aplikácia použije vaše jazykové preferencie na zobrazenie prvkov, ako sú ponuka, text štítkov a systémové správy vo vašom preferovanom jazyku.

Importované údaje a informácie, ktoré ste zadali manuálne, sa neprekladajú.

1. Ísť do **Admin** > **Systém** a vyberte **generál** tab.

1. Ak chcete zmeniť preferovaný jazyk, vyberte z rozbaľovacej ponuky **Jazyk**.

1. Ak chcete zmeniť preferované formátovanie pre dátumy, čas a čísla, použite rozbaľovaciu ponuku **Formát krajiny alebo oblasti**. Zobrazí sa náhľad formátovania. Pri výbere nového jazyka systém automaticky navrhne výber.

1. Vyberte **Uložiť**.

## <a name="view-system-status"></a>Zobraziť stav systému

Sledujte priebeh úloh, príjem údajov, export údajov a niekoľko ďalších dôležitých procesov produktu. Skontrolujte informácie, aby ste zaistili úplnosť svojich aktívnych úloh a procesov.

1. Ísť do **Admin** > **Systém** a vyberte **Postavenie** tab.

   Zobrazenie informácií o stave a spracovaní pre rôzne procesy. Pozrite si **názov** úlohy, **Postavenie** svojho posledného spustenia a kedy to bolo **Naposledy aktualizovaný**.

1. Ak chcete zobraziť podrobnosti o niekoľkých posledných spusteniach, vyberte názov úlohy alebo procesu.

1. Ak chcete zobraziť podrobnosti o priebehu úlohy, vyberte stav. The **Podrobnosti o pokroku** panel zobrazí.

   :::image type="content" source="media/system-progress-details.png" alt-text="Panel s podrobnosťami o priebehu systému":::

1. Ak chcete zobraziť podrobnosti o priebehu všetkých úloh, vyberte **Celý pracovný postup**.

### <a name="status-definitions"></a>Definície stavu

Systém používa pre úlohy a procesy nasledujúce stavy:

|Status  |Definícia  |
|---------|---------|
|Zrušená |Úloha alebo proces boli zrušené používateľom pred dokončením.   |
|Zlyhalo   |V úlohe alebo procese sa vyskytli chyby.         |
|Zlyhanie  |Úloha alebo proces zlyhal.  |
|Nespustené   |Zdroj údajov ešte neprijali žiadne údaje alebo je úloha stále v režime konceptu.         |
|Spracováva sa  |Úloha alebo proces prebieha.  |
|Obnovuje sa    |Úloha alebo proces prebieha. Ak chcete zrušiť túto operáciu, vyberte **Osviežujúce** a **Zrušiť úlohu**. Zastavenie obnovy úlohy alebo procesu ich vráti do posledného stavu obnovenia.       |
|Vynechané  |Úloha alebo proces boli preskočené. Jeden alebo viac následných procesov, od ktorých závisí táto úloha, zlyháva alebo sú preskočené.|
|Úspešné  |Úloha alebo proces úspešne dokončený. V prípade zdrojov údajov označuje, že údaje boli úspešne prijaté, ak je v položke uvedený čas **Osviežené** stĺpec.|
|Vo fronte | Spracovanie je zaradené do frontu a začne sa po dokončení všetkých nadradených úloh a procesov. Ďalšie informácie nájdete v časti [Obnoviť procesy](#refresh-processes).|

### <a name="refresh-processes"></a>Obnoviť procesy

Obnovenie úloh a procesov prebieha podľa [nakonfigurovaný rozvrh](schedule-refresh.md).

|Spracovať  |Description  |
|---------|---------|
|Aktivita  |Spúšťa sa manuálne (jednorazové obnovenie). Závisí od procesu spájania. Štatistiky závisia od spracovania.|
|Prepojenie analýzy |Spúšťa sa manuálne (jednorazové obnovenie). Závisí od segmentov.  |
|Príprava analýzy |Spúšťa sa manuálne (jednorazové obnovenie). Závisí od segmentov.  |
|Príprava údajov   |Na spustenie potrebuje entitu. Zdroj údajov entity závisia od príjmu. Obohatené entity závisia od obohatenia. Entita Zákazník závisí od zlúčenia.  |
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

Výberom stavu procesu zobrazíte podrobnosti o priebehu celej úlohy, v ktorej sa nachádzal. Vyššie uvedené procesy obnovy vám môžu pomôcť pochopiť, čo môžete urobiť pre riešenie a **Preskočené** alebo **Vo fronte** úlohu alebo proces.


[!INCLUDE [footer-include](includes/footer-banner.md)]
