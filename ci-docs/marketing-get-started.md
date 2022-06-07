---
title: Používajte jednotné profily v Dynamics 365 Marketing
description: Zistite, ako integrovať zjednotené profily a segmenty s Dynamics 365 Marketing.
ms.date: 04/20/2022
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 4cc3cbde97d0f9da198652e86c0843476393b646
ms.sourcegitcommit: f5af5613afd9c3f2f0695e2d62d225f0b504f033
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 06/01/2022
ms.locfileid: "8833327"
---
# <a name="work-with-unified-customer-profiles-in-dynamics-365-marketing"></a>Pracujte so zjednotenými profilmi zákazníkov v Dynamics 365 Marketing

[Dynamics 365 Marketing](/dynamics365/marketing/overview) zlepšuje skúsenosti zákazníkov a umožňuje vám organizovať prispôsobené cesty naprieč všetkými kontaktnými bodmi s cieľom posilniť vzťahy a získať lojalitu. Aplikácia Dynamics 365 Marketing bezproblémovo spolupracuje s Dynamics 365 Sales,Dynamics 365 Customer Insights,Microsoft Teams, a ďalšie produkty a umožňuje vám robiť rýchlejšie a lepšie rozhodnutia s využitím sily dát a AI.

Prepojením údajov Customer Insights s marketingom môžete:

- Zacieľte na jednotné zákaznícke profily a segmenty. To vám umožní zapojiť každého zákazníka bez ohľadu na umiestnenie údajov zákazníka.
- Dynamický obsah (ako sú prispôsobené tokeny) v e-mailoch, SMS a upozorneniach push založte na opatreniach, ako je stav vernosti, dátum obnovenia predplatného, nadradený obchodný vzťah alebo akékoľvek iné opatrenie, ktoré ste zachytili v zjednotenom profile Customer Insights.
- Načítajte údaje z Marketingu do Customer Insights a kombinujte ich s údajmi o zákazníkoch z iných zdrojov.
- Použite nástroje Customer Insights na čistenie, obohatenie a fuzzy párovanie údajov.

## <a name="use-rich-customer-profiles-in-real-time-marketing"></a>Používajte bohaté profily zákazníkov v marketingu v reálnom čase

Marketing v reálnom čase vám umožňuje tvoriť [vlastné spúšťače](/dynamics365/marketing/real-time-marketing-custom-triggers) ktoré spúšťajú cesty zákazníkov na základe akejkoľvek akcie zákazníka. Čím sú vaše údaje personalizovanejšie, tým relevantnejšie a prispôsobenejšie budú vaše cesty. To je dôvod, prečo je spojenie marketingu a zákazníckych štatistík také silné. Môžeš [zjednotiť údaje](data-unification.md) z akéhokoľvek zdroja a potom ho použite na podporu hyper-personalizovaných ciest zákazníkov.

Uč sa viac: [Používajte profily a segmenty Customer Insights v marketingu v reálnom čase](/dynamics365/marketing/real-time-marketing-ci-profile)

## <a name="use-unified-segments-with-outbound-customer-journeys"></a>Používajte zjednotené segmenty s cestami odchádzajúcich zákazníkov

Customer Insights vám umožňuje spresniť údaje z mnohých zdrojov a spojiť ich do agregovaných segmentov zákazníkov. Autor: [prepojenie Customer Insights s outbound marketingom](export-dynamics365-marketing.md), tieto segmenty sa objavia automaticky *a* automaticky obnovovať v činnosť zákazníka návrhárovi.

Uč sa viac: [Použiť segmenty z Dynamics 365 Customer Insights s Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments)

## <a name="pull-data-from-your-own-azure-data-lake-storage"></a>Vytiahnite údaje zo svojich vlastných Azure Data Lake Storage

Ak chcete s marketingom používať údaje Customer Insights, nie ste obmedzený na cloudové úložisko. Ak už máte vlastný Azure Data Lake Storage nastaviť, môžete sa pripojiť k Customer Insights a potom zdieľať údaje s aplikáciou Marketing rovnako ako v prípade cloudového nastavenia.

Uč sa viac: [Povoliť zdieľanie údajov s Dataverse z vlastného Azure Data Lake Storage](customer-insights-dataverse.md#enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview)
