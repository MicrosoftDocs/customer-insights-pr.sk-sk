---
title: Zobrazenie profilov zákazníkov
description: Zobrazte si zjednotené údaje o zákazníkoch vrátane použitia vyhľadávania a filtrovania
ms.date: 06/08/2022
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
ms.openlocfilehash: 0c8edfd8f45ce7770d568811df2b38be1b04e73a
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 08/16/2022
ms.locfileid: "9303802"
---
# <a name="view-customer-profiles"></a>Zobrazenie profilov zákazníkov

Profily zákazníkov sú k dispozícii, keď budete [vytvoriť jednotu *Zákazník* subjekt](data-unification.md). Kombinované zobrazenie vašich zjednotených zákazníckych profilov sa zobrazí na **zákazníkov** stránku. Zákazníkmi môžu byť jednotlivci alebo organizácie.

Choďte na **zákazníkov** stránku na zobrazenie vašich zákazníkov a ich profilov. Každý profil zákazníka je reprezentovaný dlaždicou. Na získanie ďalších záznamov použite ovládacie prvky stránkovania. Karta zobrazuje polia z entity *Zákazník*, ako bolo definované v **Indexe vyhľadávania a filtrovania**. Poradie polí na každej karte vyberie systém.

> [!NOTE]
> Ak pri výbere nevidíte dlaždice **zákazníkov**, váš správca potrebuje [definujte aspoň jeden vyhľadávateľný atribút](search-filter-index.md) v **Index vyhľadávania a filtrovania**.

:::image type="content" source="media/customers-page-result-tiles-B2C.png" alt-text="Stránka zákazníkov zobrazujúca dlaždice výsledkov.":::

Vyberte niektorú z nasledujúcich akcií:
- [Zobraziť podrobnosti o zákazníkovi](#view-customer-details)
- [Spravujte index vyhľadávania a filtrovania](search-filter-index.md) (iba správcovia)
- [Filtrovanie zákazníkov](#filter-customers)
- **Rozbaliť karty** alebo **Zbaliť karty** na rozbalenie alebo zbalenie informácií zobrazených na dlaždici zákazníka
- **Triediť podľa** konkrétny atribút
- [Vyhľadávanie zákazníkov](#search-for-customers)

  > [!NOTE]
  > Ak chcete použiť vyhľadávanie a filtrovanie, správca musí nakonfigurovať vyhľadávateľné atribúty a definovať filtrovateľné polia pomocou indexu vyhľadávania a filtrovania.

## <a name="search-for-customers"></a>Vyhľadávanie zákazníkov

Vyhľadajte zákazníkov zadaním mena alebo iného atribútu **Vyhľadajte zákazníkov**. Vyhľadávateľné atribúty sú definované správcom a pochádzajú z unified *Zákazník* subjekt.

> [!NOTE]
> **Reťazec** je jediný dátový typ, ktorý je zahrnutý vo vyhľadávaní. Použite ho v **Vyhľadajte zákazníkov** na stránke Zákazníci na vyhľadanie zákazníkov.

## <a name="filter-customers"></a>Filtrovanie zákazníkov

Filtrujte zákazníkov podľa *Zákazník* polia entity. Filtrovateľné polia definuje správca.

1. Na **zákazníkov** stránku, vyberte **Zobraziť filtre**. Zobrazí sa panel Filter.

1. Začiarknite políčka vedľa atribútov, podľa ktorých chcete filtrovať zákazníkov.

1. Odstrániť všetky filtre výberom **Vymazať filtre** alebo zrušte začiarknutie políčka vedľa vybratého atribútu.

1. Vyberte **Skryť filtre** zatvorte panel filtra.

1. Ak chcete uložiť výsledky filtrovania ako a [segment](segments.md), vyberte **Uložiť filtre ako segment**.
   1. Zadajte názov segmentu.
   1. Vyberte **Uložiť** na uloženie segmentu.
   1. Výberom vyberte, či chcete segment spustiť teraz **Aktivovať** alebo ho spustiť **Neskôr**.

## <a name="view-customer-details"></a>Zobraziť podrobnosti o zákazníkovi

Na **zákazníkov** vyberte dlaždicu zákazníka a zobrazte podrobnosti o vybranom zákazníkovi.

:::image type="content" source="media/customers-details-B2C.png" alt-text="Stránka s podrobnosťami o zákazníkovi.":::

Podrobnosti o zákazníkovi zahŕňajú tieto údaje:

**Dlaždica profilu zákazníka** zobrazuje odlišné hodnoty od zjednotených *Zákazník* subjekt. Ak pole nemá žiadnu hodnotu pre vybraný profil zákazníka, nezobrazí sa okrem poľa adresy. Dlaždica je štruktúrovaná do sekcií:

- Prvá sekcia zobrazuje vopred definovanú množinu polí, za ktorou nasledujú všetky polia, ktoré sú súčasťou indexu vyhľadávania a filtrovania. Všetky polia súvisiace s adresou sú spojené do jedného riadku, ktorý sa zobrazuje, aj keď profil neobsahuje žiadne informácie o adrese.
- **Kontakty na tohto zákazníka** zobrazenie v prostrediach pre obchodné účty (B-to-B). Každý kontakt je zobrazený s jeho poľami. Prázdne polia sú skryté.
- **Ďalšie polia** zobrazuje zostávajúce polia vybraného zákazníka okrem ID.
- **ID** uvádza všetky ID pod ich zodpovedajúcim názvom entity. Polia sú identifikované ako ID podľa ich sémantiky.

**Časová os aktivity** zobrazuje údaje, ak ste to nakonfigurovali [činnosti](activities.md). Zobrazenie časovej osi obsahuje chronologicky zoradené aktivity vybraného zákazníka, počnúc najnovšou aktivitou.

**Prehľady**:

- **Opatrenia** zobraziť, ak ste nakonfigurovali [merania atribútov zákazníka](measures.md). Tie zahŕňajú vypočítané KPI v súvislosti s vašimi zákazníkmi na úrovni jednotlivých zákazníkov.

- **Potenciálne záujmy, potenciálne značky** zobraziť, ak ste nakonfigurovali a [obohatenie afinity k značke alebo záujmu](enrichment-microsoft.md). Predstavuje potenciálne záujmy a afinity pre značky založené na iných zákazníkoch, ktorých profil je podobný zvolenému zákazníckemu profilu.

Ak sa chcete vrátiť k **zákazníkov** stránku, vyberte **Späť k zákazníkom**.

## <a name="next-steps"></a>Ďalšie kroky

[Pridajte ďalšie zdroje údajov](data-sources.md), [obohaťte zjednotené profily](enrichment-hub.md) alebo [vytvárajte segmenty](segments.md) na prácu so zjednotenými profilmi zákazníkov v iných aplikáciách.

[!INCLUDE [footer-include](includes/footer-banner.md)]
