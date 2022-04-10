---
title: Použite segmenty prehľadov cieľovej skupiny na filtrovanie správa o prehľadoch cieľovej skupiny
description: Segmenty prehľadov cieľovej skupiny použite v interaktívnych analýzach údajov o správaní zachytených prehľadmi interakcií na webových stránkach zákazníka.
ms.date: 07/27/2021
ms.topic: conceptual
author: mkisel
ms.author: mkisel
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 9c8c7a1a9216e04ebee100c548afbc745af396ec
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 02/16/2022
ms.locfileid: "8230505"
---
# <a name="use-audience-insights-segments-to-filter-engagement-insights-reports"></a>Použite segmenty prehľadov cieľovej skupiny na filtrovanie správa o prehľadoch cieľovej skupiny

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Vďaka prehľadom interakcií môžete segmenty prehľadov cieľovej skupiny používať v interaktívnych analýzach údajov o správaní zachytených pomocou prehľadov interakcií na vašich webových stránkach.

## <a name="prerequisite"></a>Predpoklady

- Prostredie prehľadov interakcií, v ktorom máte údaje o segmentoch prehľadov cieľových skupín prepojené s prostredím prehľadov cieľovej skupiny, kde sú vytvárané segmenty a profily zákazníkov. Ďalšie informácie: [Vytvorte prepojenie medzi prehľadmi cieľových skupín a prehľadmi interakcií](integrate-audience-insights-engagement-insights.md)

## <a name="create-audience-insights-segments"></a>Vytvorte segmenty prehľadov cieľovej skupiny 

> [!IMPORTANT]
> Aby sa segmenty prehľadov cieľovej skupiny zobrazovali v prehľadoch interakcií, musíte najskôr [spustiť procesy zlúčenia a nadväzujúce procesy](../audience-insights/merge-entities.md). Následné procesy sú dôležité, pretože generujú jedinečnú tabuľku, ktorá pripravuje segmenty prehľadov cieľovej skupiny na zdieľanie s prehľadmi interakcií. (Ak je naplánovaná aktualizácia systému, bude automaticky zahŕňať následné procesy.)

Segmenty prehľadov cieľovej skupiny môžete použiť v interaktívnych prehľadoch interakcií alebo vo vlastných prehľadoch, ktoré ste vytvorili. Ak chcete získať ďalšie informácie, navštívte stránku [Pripravené správy o profile](profile-reports.md) a [Vytvárajte a upravujte vlastné správy](custom-reports.md).

**Použitie segmentov prehľadov cieľocej skupiny v správach o prehľadoch interakcií**

1. Na stránke **Pracovný priestor** vyberte **Údaje** a potom vyberte kartu **Segmenty**.

    :::image type="content" source="media/integrate-audience-insights-segments1.png" alt-text="Vyberte kartu Segmenty.":::

   >[!NOTE]
   > Výber segmentu prehľadov cieľovej skupiny vás presmeruje na prehľady cieľovej skupiny, kde môžete zistiť, ako bol tento segment vytvorený z hľadiska pravidiel a logiky. Ak chcete získať ďalšie informácie o segmentoch prehľadov cieľovej skupiny, prejdite na položku [Zobraziť a vytvárať segmenty](../audience-insights/segments.md).

2. Vyberte pripravenú zostavu alebo [vytvorte vlastnú správu](custom-reports.md), a potom vyberte **Pridajte podmienku**. (V tomto prípade sme vybrali správu **Zobrazenia stránky**.)

    :::image type="content" source="media/integrate-audience-insights-segments2.png" alt-text="Pridá podmienku.":::

3. Vyberte **Filtrovať podľa segmentov**, rozbaľte zoznam **Typ segmentu** a potom vyberte položku **Demografické**.

    :::image type="content" source="media/integrate-audience-insights-segments3.png" alt-text="Vyberte typ demografického segmentu.":::

4. Rozbaľte zoznam **Názov segmentu** a potom vyberte segment prehľadov cieľovej skupiny.

    :::image type="content" source="media/integrate-audience-insights-segments4.png" alt-text="Vyberte segment.":::

5. Môžete použiť jeden alebo viac segmentov vrátane segmentov správania (prehľady interakcií) a demografických údajov (prehľady cieľovej skupiny). 

    :::image type="content" source="media/integrate-audience-insights-segments6.png" alt-text="Prehľad zobrazení stránok je obmedzený na zákazníkov z USA a segmenty domovskej stránky.":::

Na predchádzajúcom obrázku sú vybrané segmenty **Zákazníci z USA** a **Domovská stránka**, čím sa obmedzuje správa **Zobrazenia stránky** iba na zobrazenie týchto dvoch segmentov. 


>[!NOTE]
> Segmenty prehľadov cieľovej skupiny môžete použiť na filtrovanie okamžitých prehľadov, vlastných prehľadov a zúžení v prehľadoch interakcií. 


[!INCLUDE[footer-include](../includes/footer-banner.md)]