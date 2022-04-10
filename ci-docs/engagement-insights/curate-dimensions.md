---
title: Na rozdelenie údajov o správaní použite demografické dimenzie (zostavené dimenzie)
description: Zostavené dimenzie zjednoteného profilu použite na povolenie vlastností zákazníckeho profilu prehľadov cieľových skupín.
ms.date: 07/27/2021
ms.topic: conceptual
author: mkisel
ms.author: mkisel
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 95395e09bc0ba5ba93138957c62105f31c709e91
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 02/16/2022
ms.locfileid: "8233066"
---
# <a name="use-demographic-dimensions-for-splitting-behavioral-data"></a>Na rozdelenie údajov o správaní použite demografické dimenzie

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Použitím demografických dimenzií zjednoteného profilu môžu používatelia so štatistikami interakcie pristupovať k vlastnostiam profilu prehľadov cieľových skupín. Tieto vlastnosti potom môžete použiť v interaktívnych analýzach údajov o správaní vrátane údajov zachytených pomocou prehľadov cieľových skupín na vašom webe alebo v mobilnej aplikácii.

>[!NOTE]
> Prehľady interakcií zahŕňajú vopred pripravené dimenzie pre vlastnosti udalosti. Ďalšie informácie: [Zobrazenie a vytvorenie dimenzií](dimensions.md)

## <a name="prerequisite"></a>Predpoklady

- Prostredie prehľadov interakcií, v ktorom máte údaje o zákazníckych profiloch prepojené s prostredím prehľadov cieľovej skupiny, kde sú vytvárané profily zákazníkov. Ďalšie informácie: [Vytvorte prepojenie medzi prehľadmi cieľových skupín a prehľadmi interakcií](integrate-audience-insights-engagement-insights.md)

> [!NOTE]
> Keď vytvoríte prepojenie medzi prostrediami prehľadov cieľových skupín a interakcií, možno budete chcieť iba údaje špecifické pre vlastnosti profilu zákazníka, ktoré môžu byť užitočné ako dimenzie v prehľadoch interakcií. Ak chcete získať ďalšie informácie, prejdite na stránku [Povoliť atribúty a segmenty prehľadov cieľových skupín zjednotených profilov](integrate-audience-insights-engagement-insights.md#enable-audience-insights-unified-profiles-attributes-and-segments).

## <a name="create-a-new-custom-report"></a>Vytvoriť novú vlastnú zostavu

1. Na ľavom paneli vyberte **Vlastné** > **Nová správa** a potom vyberte požadovanú metriku. (V tomto prípade sme vybrali **Zobrazenia stránky za hodinu**.)

    :::image type="content" source="media/curated-dimensions1.png" alt-text="Vybrať metriku.":::

2. V editore vizualizácie vyberte **Rozmery**, a potom vyberte **Demografické** v rozbaľovacej ponuke **Typ dimenzie**.

    :::image type="content" source="media/curated-dimensions2.png" alt-text="Vyberte demografickú skupinu.":::

3. Vyberte dimenziu **Signal.Customer.*xxx***. (Tento príklad ukazuje Signal.Customer.Country.)

    :::image type="content" source="media/curated-dimensions3.png" alt-text="Vyberte dimenziu.":::
  
## <a name="limitations"></a>Obmedzenia

V súčasnosti môžete na rozdelenie údajov o správaní používať iba demografické dimenzie.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
