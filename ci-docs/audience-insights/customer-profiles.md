---
title: Zobrazenie profilov zákazníkov
description: Získajte kombinovaný pohľad na vaše zjednotené údaje o zákazníkoch.
ms.date: 09/30/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: Nils-2m
ms.author: nikeller
manager: shellyha
searchScope:
- ci-customers-page
- ci-customer-card
- ci-activities
- ci-activities-wizard
- customerInsights
ms.openlocfilehash: 3a17716508a14020c56640c7d68f300a9d721af4
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 02/25/2022
ms.locfileid: "8354909"
---
# <a name="customer-profiles"></a>Profily zákazníkov

Stránka **Zákazníci** zobrazuje kombinovaný pohľad na vaše zjednotené profily zákazníkov. Profily zákazníkov budú k dispozícii, keď [vytvoríte zjednotenú entitu Zákazník](data-unification.md). Táto stránka vám umožňuje vyhľadávať zákazníkov a definovať index pre toto vyhľadávanie.

Zákazníkmi môžu byť jednotlivci alebo organizácie. Každý profil zákazníka je reprezentovaný dlaždicou. Na získanie ďalších záznamov použite ovládacie prvky stránkovania. Karta zobrazuje polia z entity *Zákazník*, ako bolo definované v **Indexe vyhľadávania a filtrovania**. Vyberte dlaždicu, aby ste zobrazili údaje pre vybraného zákazníka na vyhradenej stránke s názvom [Stránka s podrobnosťami o zákazníkovi](customer-profiles.md#customer-details-page).

> [!div class="mx-imgBorder"] 
> ![Stránka Zákazníci, ktorá zobrazuje dlaždice s výsledkami](media/customers-page-result-tiles-B2C.png "Stránka Zákazníci, ktorá zobrazuje dlaždice s výsledkami")

> [!NOTE]
> Ak pri výbere možnosti **Zákazníci** pri navigácii nevidíte dlaždice, musí váš správca [definovať aspoň jeden atribút, ktorý je možné vyhľadávať](search-filter-index.md) v položke **Index vyhľadávania a filtrovania**.

## <a name="search-for-customers"></a>Vyhľadávanie zákazníkov

Vyhľadajte zákazníkov zadaním mena alebo iného atribútu do vyhľadávacieho poľa. Vyhľadávanie funguje iba v rámci entity _Zákazník_ vytvorenej počas procesu zjednocovania údajov.

Ako správca môžete konfigurovať vyhľadávané atribúty pomocou stránky **Index vyhľadávania a filtrovania**. Ak chcete získať ďalšie informácie, navštívte stránku [Spravovať index vyhľadávania a filtrovania](search-filter-index.md).

## <a name="filter-customers"></a>Filtrovanie zákazníkov

Zákazníkov môžete filtrovať podľa polí entity _Zákazník_. Podobne ako pri vyhľadávaní aj váš správca musí najprv definovať polia ako filtrovateľné pomocou stránky **Index vyhľadávania a filtrovania**.

1. Vyberte **Zobraziť filtre** na stránke **Zákazníci**.

1. Začiarknite políčka vedľa atribútov, podľa ktorých chcete filtrovať zákazníkov.

1. Odstráňte svoje filtre výberom položky **Vymazať filtre** na stránke **Zákazníci**.

## <a name="customer-details-page"></a>Stránka s podrobnosťami o zákazníkovi

Vyberte ktorúkoľvek z dlaždíc zákazníka a otvorte **stránku s podrobnosťami o zákazníkovi**. Toto zobrazenie obsahuje zjednotené informácie o vybranom zákazníkovi. Podrobnosti o zákazníkovi obsahujú nasledujúci obsah:

**Dlaždica profilu zákazníka**: Táto dlaždica zobrazuje hodnoty, ktoré sa líšia od entity _Zákazník_. Ak pole pre vybratý profil zákazníka nemá žiadnu hodnotu, nezobrazí sa. Dlaždica je štruktúrovaná do sekcií:  
  - Prvá sekcia zobrazuje vopred definovanú množinu polí, za ktorou nasledujú všetky polia, ktoré sú súčasťou indexu vyhľadávania a filtrovania. Ak profil obsahuje tieto polia, všetky polia súvisiace s adresou sa spoja do jedného riadka. 
  - **Kontakty na tohto zákazníka**: V prostrediach pre firemné obchodné vzťahy uvidíte všetky súvisiace kontakty na tohto zákazníka ako druhú sekciu. Každý kontakt je zobrazený s jeho poľami. Prázdne polia sú skryté.
  - **Ďalšie polia**: Zobrazuje zostávajúce polia vybratého zákazníka s výnimkou IDs. 
  - **IDs**: Uvádza všetky identifikátory pod ich zodpovedajúcim názvom entity. Polia sú identifikované ako IDs svojou sémantikou, ktorá ich ako taká kategorizuje.

**Časová os aktivity**: Zobrazuje údaje, ak máte nakonfigurované aktivity. Zobrazenie časovej osi obsahuje chronologicky zoradené aktivity vybraného zákazníka, počnúc najnovšou aktivitou. Ďalšie informácie získate v časti [Aktivity zákazníkov](activities.md).

**Prehľady**:  
  - **Miery**: Zobrazuje, či ste nakonfigurovali jednu alebo viac mier meraní atribútov zákazníka. Tie zahŕňajú vypočítané KPI v súvislosti s vašimi zákazníkmi na úrovni jednotlivých zákazníkov. Ak chcete získať ďalšie informácie, navštívte stránku [Definícia a spravovanie mier](measures.md).

  - **Potenciálne záujmy, potenciálne značky**: Zobrazí, či ste nakonfigurovali obohatenie afinity k značke alebo záujmom. Predstavuje potenciálne záujmy a afinity pre značky založené na iných zákazníkoch, ktorých profil je podobný zvolenému zákazníckemu profilu. Ak chcete získať ďalšie informácie, navštívte stránku [Obohatenie profilov zákazníkov o afinity k značke a záujmom](enrichment-microsoft.md).

Ak sa chcete vrátiť na stránku vyhľadávania zákazníkov, vyberte **Späť na stránku Zákazníci**.

## <a name="next-steps"></a>Ďalšie kroky

[Pridajte ďalšie zdroje údajov](data-sources.md), [obohaťte zjednotené profily](enrichment-hub.md) alebo [vytvárajte segmenty](segments.md) na prácu so zjednotenými profilmi zákazníkov v iných aplikáciách.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
