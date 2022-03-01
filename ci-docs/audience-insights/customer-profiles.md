---
title: Zobrazenie profilov zákazníkov
description: Získajte kombinovaný pohľad na vaše zjednotené údaje o zákazníkoch.
ms.date: 12/01/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: 433e6ceda0ec7827bd672cff40f895d7719561df
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896346"
---
# <a name="customer-profiles"></a>Profily zákazníkov

Na stránke **Zákazníci** je uvedený kombinovaný pohľad na vašich zákazníkov na základe údajov z profilu získaných z [všetkých zdrojov údajov](data-sources.md). Profily zákazníkov sú k dispozícii, keď [vytvoríte zjednotenú entitu Zákazník](data-unification.md). Uistite sa, že ste dokončili proces zjednotenia údajov, aby ste získali bohatší prehľad o svojich zákazníkoch. Táto stránka tiež umožňuje vyhľadávať zákazníkov.

Zákazníkmi môžu byť jednotlivci alebo organizácie (ukážka). Každý profil zákazníka alebo organizácie je reprezentovaný dlaždicou. Vyberte dlaždicu a zobrazte ďalšie informácie o konkrétnom zákazníkovi alebo organizácii. Ak chcete zobraziť ďalšie záznamy, použite ovládacie prvky stránkovania v dolnej časti stránky.

> [!div class="mx-imgBorder"] 
> ![Profily zákazníka B2C](media/profiles-customers.png "Profily zákazníka B2C")

Organizácie (ukážka)
> [!div class="mx-imgBorder"] 
> ![Profily zákazníka B2B](media/profile-customers-b2b.png "Profily zákazníka B2B")

> [!NOTE]
> Ak nevidíte dlaždice, keď vyberiete **Zákazníci** v navigácii, musí váš správca [definovať aspoň jeden prehľadávateľný atribút](search-filter-index.md) na stránke **Index vyhľadávania a filtrovania**.

## <a name="search-for-customers"></a>Vyhľadávanie zákazníkov

Vyhľadajte zákazníkov zadaním mena alebo iného atribútu do vyhľadávacieho poľa. Vyhľadávanie funguje iba v rámci entity Profil zákazníka vytvorenej počas procesu zjednotenia údajov.

Ako správca môžete konfigurovať vyhľadávané atribúty pomocou stránky **Index vyhľadávania a filtrovania**. Viac informácií nájdete v článku [Spravujte index vyhľadávania a filtrovania](search-filter-index.md).

## <a name="filter-customers"></a>Filtrovanie zákazníkov

Zákazníkov môžete filtrovať podľa polí entity Profil zákazníka. Podobne ako pri vyhľadávaní aj váš správca musí najprv definovať polia ako filtrovateľné pomocou stránky **Index vyhľadávania a filtrovania**.

1. Vyberte položku **Filtrovať** na stránke **Zákazníci**.

2. Začiarknite políčka vedľa atribútov, podľa ktorých chcete filtrovať zákazníkov.

   > [!div class="mx-imgBorder"] 
   > ![Profily zákazníkov](media/profiles-customers3.png "Profily zákazníkov")

3. Odstráňte svoje filtre výberom položky **Vymazať filtre** na stránke **Zákazníci**.

##  <a name="customer-details-page"></a>Stránka s podrobnosťami o zákazníkovi

Vyberte ktorúkoľvek z dlaždíc zákazníka a otvorte **stránku s podrobnosťami o zákazníkovi**. Toto zobrazenie obsahuje zjednotené informácie o vybranom zákazníkovi.

Podrobnosti o zákazníkovi zahŕňajú tieto údaje:

-   **Dlaždica profilu zákazníka:** Táto dlaždica ukazuje rôzne hodnoty z entity zjednoteného profilu zákazníka. Tieto podrobnosti môžu zahŕňať e-mailovú adresu, meno, mesto atď. 

-   **Potenciálne záujmy, potenciálne značky:** Ukazuje, či ste nakonfigurovali obohatenie prvej strany. Predstavuje potenciálne záujmy a príbuznosti značiek, ktoré môže mať zákazník s podobným profilom ako tento zákazník. Ďalšie informácie nájdete v sekcii [Obohatenie profilov zákazníkov o značky a záujmy](enrichment-microsoft.md).

-   **Miery:** Ukazuje, či ste nakonfigurovali jednu alebo viac mier konkrétneho typu: miery atribútov zákazníka. Tie zahŕňajú vypočítané KPI v súvislosti s vašimi zákazníkmi na úrovni jednotlivých zákazníkov. Ďalšie informácie nájdete v sekcii [Definovanie a správa mier](measures.md).

-   **Časová os aktivít:** Zobrazuje, či máte nakonfigurované aktivity. Zobrazenie na časovej osi obsahuje chronologicky zoradené aktivity tohto zákazníka, počnúc najnovšou aktivitou. Ďalšie informácie nájdete v článku [Aktivity zákazníka](activities.md).

Výberom položky **Späť k zákazníkom** sa vrátite na stránku vyhľadávania zákazníkov.

## <a name="next-steps"></a>Ďalšie kroky

[Pridanie ďalších zdrojov údajov](data-sources.md) alebo [vytváranie zákazníckych segmentov](segments.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]