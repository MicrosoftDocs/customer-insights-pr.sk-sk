---
title: Prehľady segmentov (ukážka)
description: Získajte prehľady o existujúcich segmentoch, aby ste videli rozdiely a spoločné črty.
ms.date: 06/10/2020
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-segment-insights
- customerInsights
ms.openlocfilehash: ccb33594a3a92e87d307f3300c77772ef8b4a82f
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 07/18/2022
ms.locfileid: "9171022"
---
# <a name="segment-insights-preview"></a>Prehľady segmentov (ukážka)

Objavte ďalšie informácie a prehľady o svojich existujúcich segmentoch. Zistite, čo odlišuje dva segmenty alebo čo majú spoločné.

## <a name="segment-overlap"></a>Prekrytie segmentu

Analýza prekrývania segmentov ukazuje, koľkí a ktorí zákazníci sú spoloční pre dva alebo viac segmentov. Napríklad, ako sa segment častých zákazníkov prekrýva so segmentom, ktorý obsahuje zákazníkov, ktorí sú spokojní s vašou službou alebo produktom.
Môžete tiež analyzovať, ako sa prekrývanie mení pre konkrétne atribúty.

### <a name="run-an-overlap-analysis"></a>Spustenie analýzy prekrývania

1. Prejdite na **Segmenty** a vyberte kartu **Štatistiky (ukážka)**.

1. Vyberte **Nový** a vyberte možnosť **Prekrytie** na table **Vyberte typ štatistík**.

1. Vyberte segmenty záujmu a zvoľte **Ďalšie**.

1. Ak chcete analyzovať prekrytia pre každú možnú hodnotu poľa, vyberte jedno alebo viac polí záujmu a vyberte **Ďalšie**.

1. Uveďte názov prekrývajúcej sa analýzy, voliteľný zobrazovaný názov a popis.

1. Vyberte **Uložiť** na spustenie analýzy. Analýza prekrývania je pripravená, keď sa stav zmení z Obnovuje sa na Úspešné.

### <a name="view-and-optimize-an-overlap-analysis"></a>Zobrazenie a optimalizácia analýzy prekrývania

1. Po dokončení analýzy vyhľadajte podrobnosti o tomto prehľade v časti **Segmenty** > **Prehľady (ukážka)**.

   :::image type="content" source="media/segment-overlap.png" alt-text="Podrobnosti prehľadu prekrývania segmentov.":::

1. Ak chcete zobraziť výsledky analýzy, vyberte prehľad:

   - Počet členov prekrývajúcich segmenty vybrané na analýzu.
   - Počet členov zahrnutých v jednom zo segmentov, ale nie v ostatných segmentoch.
   - Ak ste pri konfigurácii analýzy prekrývania vybrali polia, nájdete ich na príslušných kartách. Pomocou rozbaľovacej ponuky filtra si môžete vybrať ľubovoľnú úroveň atribútu, ktorá vás zaujíma, pričom tabuľka v dolnej časti obsahuje príslušné údaje.

## <a name="segment-differentiators"></a>Diferenciátory segmentov

Diferenciátory segmentov vám pomôžu zistiť, čo odlišuje segment od ostatných zákazníkov alebo od iného segmentu. Vyberte segment a systém identifikuje atribúty profilu a miery, ktoré odlišujú vybraný segment.

### <a name="run-a-differentiator-analysis"></a>Spustenie analýzy diferenciátora

1. Prejdite na **Segmenty** a vyberte kartu **Štatistiky (ukážka)**.

1. Vyberte **Nový** a vyberte si **Diferenciátory** možnosť v **Vyberte Typ štatistiky** tabuľka.

1. Vyberte segment, ktorý chcete analyzovať ako **Primárny segment** a vyberte **Ďalšie**.

1. Vyberte **Všetci zákazníci** alebo **Sekundárny segment** na porovnanie vášho primárneho segmentu a vyberte **Ďalšie**.

1. Prípadne vyberte jednu alebo viac oblastí záujmu, aby sa analýza zamerala na konkrétne atribúty, a vyberte **Ďalšie**.

1. Zadajte názov pre analýzu diferenciátora, voliteľný zobrazovaný názov a popis.

1. Vyberte **Uložiť** na spustenie analýzy. Analýza diferenciátora je pripravená, keď sa stav zmení z Obnovuje sa na Úspešné.

### <a name="view-and-optimize-a-differentiators-analysis"></a>Prezrite si a optimalizujte analýzu diferenciátorov

1. Po dokončení analýzy prejdite na **Segmenty** > **Štatistiky (ukážka)**.

   :::image type="content" source="media/segment-differentiators.png" alt-text="Podrobnosti prehľadu diferenciátora segmentov.":::

1. Ak chcete zobraziť výsledky analýzy, vyberte prehľad. Analýza diferenciátora obsahuje dve karty. Karta **Atribúty** uvádza atribúty profilu, ktoré sa považujú za diferenciátory. Karta **Miery** zobrazuje diferenciátory. Každá karta obsahuje nasledujúce podrobnosti:

   - Hodnotený zoznam diferenciátorov zoradený podľa skóre rozdielu.
   - **Skóre rozdielu** pre každého diferenciátora. Skóre rozdielu predstavuje stupeň rozdielu atribútu medzi dvoma segmentmi. Čím vyššie je skóre rozdielu, tým viac atribútov sa medzi týmito dvoma segmentmi líši. Vyberte skóre, a otvorte tablu **Skóre rozdielu** s rozdelením hodnôt pre tento atribút.

## <a name="manage-segment-insights"></a>Spravovanie prehľadov o segmentoch

Ísť do **Segmenty** > **Štatistiky (ukážka)** zobraziť štatistiky segmentov a spravovať ich. Ak chcete zobraziť dostupné akcie, vyberte štatistiku segmentu.

- **vyhliadka** analýza vhľadu
- **Upraviť** vhľad zmeniť jeho vlastnosti
- **Obnoviť** prehľad na opätovné spustenie analýzy
- **Premenovať** prehľad
- **Odstrániť** prehľad

[!INCLUDE [footer-include](includes/footer-banner.md)]
