---
title: Vyhľadávanie a filtrovanie profilov zákazníkov
description: Rýchlo vyhľadajte informácie o zjednotených profiloch zákazníkov a filtrujte konkrétne atribúty.
ms.date: 11/01/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: e17d745974958b73683f1f9406c5ae95f2cbcb3c
ms.sourcegitcommit: 834651b933b1e50e7557d44f926a3fb757c1f83a
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 11/02/2021
ms.locfileid: "7732053"
---
# <a name="customer-profiles-search--filter-index"></a>Profily zákazníkov: Index vyhľadávania a filtrovania

Výsledkom zjednocovanie vašich zákazníckych údajov je entita profilu zákazníka, ktorá poskytuje zjednotený pohľad na celkovú zákaznícku základňu. Ak chcete [rýchlo vyhľadať informácie o konkrétnom zákazníkovi alebo skupine zákazníkov](customer-profiles.md), môžete nakonfigurovať možnosti **vyhľadávania** a **filtrovania** na stránke **zákazníci**. Čítajte ďalej a dozviete sa, ako môžu správcovia upravovať atribúty na stránke **indexu vyhľadávania a filtrovania**, ktoré sú k dispozícii používateľom na vyhľadávanie a filtrovanie.

   :::image type="content" source="media/search-filter.png" alt-text="Filter vyhľadávania":::

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

## <a name="add-fields-and-specify-attributes"></a>Pridanie polí a zadanie atribútov

Ak definujete atribúty s možnosťou vyhľadávania ako správca po prvý raz, musíte najprv definovať indexované polia. Odporúčame, aby ste si vybrali všetky atribúty, podľa ktorých môžu používatelia vyhľadávať a filtrovať zákazníkov na stránke **Zákazníci**. Môžete zadať iba atribúty, ktoré existujú v entite profilu zákazníka, ktorý ste vytvorili počas procesu zjednotenia údajov.

1. Otvorte stránku **Zákazníci** a vyberte **Index vyhľadávania a filtrovania**.

2. Vyberte **+ pridať** a zadajte indexované polia.

3. Vyberte atribúty v zozname, ktoré chcete pridať ako indexované polia. Vždy môžete pridať ďalšie atribúty výberom položky **Pridať**. Vybrané atribúty môžete tiež odstrániť výberom symbolu **Odstrániť**.

## <a name="explore-the-indexed-customer-fields-table"></a>Preskúmanie tabuľky Indexované polia zákazníkov

V tabuľke sú uvedené nasledujúce informácie.

- **Názov**: Predstavuje názov atribútu, ako sa zobrazuje v entite profilu zákazníka.
- **Typ údajov**: Určuje, či je typ údajov reťazec, číslo alebo dátum.
- **Zahrnuté do vyhľadávania**: Určuje, či sa tento atribút môže použiť na vyhľadávanie zákazníkov na stránke **Zákazníci** pomocou **vyhľadávacieho** poľa.
- **Pridať filter**: Ovládací prvok na definovanie spôsobu, akým sa tento atribút môže použiť na filtrovanie na stránke **Zákazníci**.

## <a name="editing-filtering-options-for-a-given-attribute"></a>Úprava možností filtrovania pre daný atribút

Ponuka **Filter** na stránke **Zákazníci** môže obsahovať rôzny počet úrovní atribútov (napríklad rôzne vekové skupiny na filtrovanie zákazníkov).

1. Vyberte **Pridať filter** pre daný atribút na stránke **Index vyhľadávania a filtrovania**. Môžete definovať počet výsledkov a poradie, v ktorom budú usporiadané. V závislosti od typu údajov atribútu sa zobrazí jedna z nasledujúcich tabiel.

- Atribúty typu Reťazec: Zadajte počet požadovaných výsledkov na table **Možnosti filtrovania reťazcov** a pravidlá poradia, podľa ktorých budú usporiadané.

- Atribúty typu Číselný: Zadajte počet intervalov obsiahnutých na table **Možnosti filtrovania čísiel** a pravidlá poradia, podľa ktorých budú usporiadané.

- Atribúty typu Údaje: Zadajte počet intervalov obsiahnutých na table **Možnosti filtrovania údajov** a pravidlá poradia, podľa ktorých budú usporiadané.

2. Zmeny vykonajte výberom položky **Uložiť**.

3. Vyberte položku **Spustiť**, keď budete pripravení použiť svoje nastavenia. Po spracovaní zmien ich nájdete na [zákazníckych kartách na stránke Zákazník](customer-profiles.md). 

## <a name="next-steps"></a>Ďalšie kroky

Prezrite si [stránku zjednotených profilov](customer-profiles.md) na vyhľadávanie profilov alebo používanie indexovaných polí na zobrazenie podmnožiny všetkých zjednotených profilov.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
