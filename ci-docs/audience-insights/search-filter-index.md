---
title: Vyhľadávanie a filtrovanie profilov zákazníkov
description: Rýchlo vyhľadajte informácie o zjednotených profiloch zákazníkov a filtrujte konkrétne atribúty.
ms.date: 01/19/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: a6131d4dddce48b0fba153bcefe5631e0d22d808
ms.sourcegitcommit: dab2cbf818fafc9436e685376df94c5e44e4b144
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 07/13/2021
ms.locfileid: "6554040"
---
# <a name="customer-profiles-search--filter-index"></a>Profily zákazníkov: Index vyhľadávania a filtrovania

Výsledkom zjednocovanie vašich zákazníckych údajov je entita profilu zákazníka, ktorá poskytuje zjednotený pohľad na celkovú zákaznícku základňu. Ak chcete [rýchlo vyhľadať informácie o konkrétnom zákazníkovi alebo skupine zákazníkov](customer-profiles.md), môžete nakonfigurovať možnosti **vyhľadávania** a **filtrovania** na stránke **zákazníci**. Čítajte ďalej a dozviete sa, ako môžu správcovia upravovať atribúty na stránke **indexu vyhľadávania a filtrovania**, ktoré sú k dispozícii používateľom na vyhľadávanie a filtrovanie.

> [!div class="mx-imgBorder"]
> ![Filter vyhľadávania.](media/search-filter.png "Filter vyhľadávania")

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

3. Vyberte položku **Spustiť**, keď budete pripravení použiť svoje nastavenia.

## <a name="next-steps"></a>Ďalšie kroky

Choďte na stránku **Zákazníci** a vyhľadajte profily zákazníkov alebo pomocou indexovaných polí zobrazte podmnožinu všetkých profilov zákazníkov.


[!INCLUDE[footer-include](../includes/footer-banner.md)]