---
title: Spravujte index vyhľadávania a filtrovania pre profily zákazníkov
description: Rýchlo vyhľadajte informácie o zjednotených profiloch zákazníkov a filtrujte konkrétne atribúty.
ms.date: 07/22/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
searchScope:
- ci-search-filter
- customerInsights
ms.openlocfilehash: dfbfcbff3ffb3e4483252377e591229631d38556
ms.sourcegitcommit: c45c3e044034bf866b0662f80a59166cee4ababe
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 07/22/2022
ms.locfileid: "9187928"
---
# <a name="manage-the-search--filter-index-for-customer-profiles"></a>Spravujte index vyhľadávania a filtrovania pre profily zákazníkov

Výsledkom zjednotenia vašich zákazníckych údajov je a *Zákazník* subjekt, ktorý poskytuje jednotný pohľad na vašu celkovú zákaznícku základňu. Pre používateľov rýchlo [nájsť informácie o konkrétnom zákazníkovi alebo skupine zákazníkov](customer-profiles.md), správca musí nakonfigurovať **Vyhľadávanie** a **Filter** schopnosti pre **zákazníkov** stránku.

   :::image type="content" source="media/search-filter.png" alt-text="Filter vyhľadávania":::

## <a name="define-searchable-attributes-and-indexed-fields"></a>Definujte vyhľadávateľné atribúty a indexované polia

Ak ako správca definujete vyhľadávateľné atribúty prvýkrát, najskôr definujte indexované polia. Odporúčame, aby ste si vybrali všetky atribúty, podľa ktorých môžu používatelia vyhľadávať a filtrovať zákazníkov na stránke **Zákazníci**. Iba atribúty, ktoré existujú v *Zákazník* možno špecifikovať entitu vytvorenú počas procesu zjednocovania údajov.

1. Ísť do **zákazníkov** a vyberte **Index vyhľadávania a filtrovania**.

1. Vyberte **+ Pridať**.

1. Vyberte atribúty v zozname, ktoré chcete pridať ako indexované polia, a kliknite **Použiť**.

1. Ak chcete pridať ďalšie atribúty, vyberte **Pridať**. Ak chcete odstrániť vybratý atribút, vyberte atribút a potom **Odstrániť**.

   :::image type="content" source="media/search-filter-index.png" alt-text="Indexová stránka vyhľadávania a filtrovania.":::

1. Vyberte **Bežať** keď budete pripravení použiť nastavenia vyhľadávania a filtra. Po spracovaní zmien ich zobrazte v [zákaznícke karty na Zákazníckej stránke](customer-profiles.md).

## <a name="define-filtering-options-for-a-given-attribute"></a>Definujte možnosti filtrovania pre daný atribút

Nastavte polia, ktoré možno použiť na filtrovanie zákazníkov na **zákazníkov** stránku.

1. Ísť do **zákazníkov** a vyberte **Index vyhľadávania a filtrovania**.

1. Vyberte atribút a **Pridať filter**. Definujte počet výsledkov a poradie, v ktorom budú usporiadané. V závislosti od typu údajov atribútu sa zobrazí jeden z nasledujúcich panelov.

   - Atribúty typu reťazca: Zadajte počet požadovaných výsledkov na **Reťazcový filter** tabla a pravidlá objednávok, podľa ktorých budú usporiadané.

   - Atribúty numerického typu: Zadajte intervaly zahrnuté na **Filter čísel** tabla a pravidlá objednávok, podľa ktorých budú usporiadané.

   - Atribúty typu dátumu: Zadajte intervaly zahrnuté na **Dátumový filter** tabla a pravidlá objednávok, podľa ktorých budú usporiadané.

1. Vyberte položku **OK**. Opakujte pre všetky atribúty, podľa ktorých chcete filtrovať.

1. Vyberte **Bežať** keď budete pripravení použiť nastavenia vyhľadávania a filtra. Po spracovaní zmien ich zobrazte v [zákaznícke karty na Zákazníckej stránke](customer-profiles.md).

## <a name="view-indexed-customer-fields"></a>Zobraziť indexované polia zákazníkov

The **Index vyhľadávania a filtrovania** stránka zobrazuje nasledujúce informácie:

- **názov** : Predstavuje názov atribútu tak, ako sa objavuje v *Zákazník* subjekt.
- **Typ údajov**: Určuje, či je typ údajov reťazec, číslo alebo dátum.
- **Zahrnuté do vyhľadávania**: Určuje, či sa tento atribút môže použiť na vyhľadávanie zákazníkov na stránke **Zákazníci** pomocou **vyhľadávacieho** poľa.
- **Pridať filter**: Ovládací prvok na definovanie spôsobu, akým sa tento atribút môže použiť na filtrovanie na stránke **Zákazníci**.

## <a name="next-steps"></a>Ďalšie kroky

Prezrite si [stránku zjednotených profilov](customer-profiles.md) na vyhľadávanie profilov alebo používanie indexovaných polí na zobrazenie podmnožiny všetkých zjednotených profilov.

[!INCLUDE [footer-include](includes/footer-banner.md)]
