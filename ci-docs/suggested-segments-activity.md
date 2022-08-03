---
title: Navrhované segmenty na základe aktivity (ukážka)
description: Nechajte strojové učenie pomôcť vám nájsť nové a zaujímavé segmenty založené na aktivite zákazníkov.
ms.date: 05/11/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
manager: shellyha
searchScope:
- ci-segment-suggestions
- customerInsights
ms.openlocfilehash: df4f5f4b5c9a3ad66d57a6b349e18a0d714aff62
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 07/18/2022
ms.locfileid: "9170608"
---
# <a name="suggested-segments-based-on-activity-preview"></a>Navrhované segmenty na základe aktivity (ukážka)

Objavte zaujímavé segmenty svojich zákazníkov na základe údajov o aktivite zákazníkov, ktoré sú prijaté do služby Customer Insights. Príkladom údajov o činnosti sú transakcie, doba trvania hovoru, nákupy alebo vrátenia. Pri navrhovaní segmentov sa údaje o činnosti analyzujú v oblasti aktuálnosti, frekvencie a peňažnej hodnoty (alebo trvania). Prípadne môžete vygenerovať [navrhované segmenty na zlepšenie miery alebo lepšie pochopenie toho, čo ovplyvňuje atribút](suggested-segments.md).

:::image type="content" source="media/suggested-segments-tab.png" alt-text="Karta Navrhované segmenty, ktorá zobrazuje návrhy segmentov pre segmenty založené na aktivite a atribúte.":::

## <a name="categorize-customers-by-activity"></a>Kategorizujte zákazníkov podľa aktivity

S [údajmi o aktivite](activities.md) dostupnými v Customer Insights, môžeme generovať návrhy, ktoré zastupujú skupiny zákazníkov:

- najaktívnejší zákazníci 
- zákazníci, ktorí uskutočnili najviac nákupov 
- zákazníci, ktorí dosiahli najväčší príjem 
- zákazníci, ktorí v poslednej dobe neboli aktívni 
- zákazníci, ktorí často interagujú s vašou firmou  

Ak podnikáte v maloobchode, môžete zistiť, ktorí zákazníci vygenerovali najväčší obrat, a odmeniť ich kupónom. Alebo môžete identifikovať príležitostných zákazníkov a ponúknuť im účasť v programe odmien, aby navštevovali vašu firmu častejšie.
Ak poskytujete verejnú zdravotnú starostlivosť a vaším cieľom je minimalizovať výdavky pre jednotlivých pacientov, môžete sa pokúsiť obmedziť opakované návštevy poskytnutím čo najlepšej starostlivosti za čo najmenej návštev. V takom prípade je vaším cieľom udržiavať nízku frekvenciu návštev a minimalizovať opakujúce sa náklady na pacientov. Alebo môžete identifikovať segmenty pacientov, ktorí majú časté plánované činnosti a vysoké opakujúce sa náklady, a analyzovať tieto prípady s cieľom zlepšiť liečbu jednotlivca.

## <a name="required-data"></a>Požadované údaje

Návrhy sa generujú na základe vybratých vstupných údajov.

- Profily zákazníkov: Všetci zákazníci alebo členovia konkrétneho segmentu.

- Časové obdobie: minulý mesiac, minulý rok alebo ľubovoľný vlastný časový rámec.

- Typ aktivity: nákupy, maloobchodné transakcie, online transakcie, prípady podpory zákazníkov, predplatné atď.  

- Entita v Customer Insights, ktorá obsahuje údaje o aktivite: entita UnifiedActivity alebo entita pre konkrétnu aktivitu.

- Zahrnuté dimenzie: Aktuálnosť, frekvencia alebo peňažná dimenzia v závislosti od vašich obchodných požiadaviek.

## <a name="generate-suggested-segments"></a>Generovanie navrhovaných segmentov

1. Ísť do **Segmenty** a vyberte **Návrhy (ukážka)** tab.

1. Stlačte možnosť **Vyhľadanie nových návrhov** a stlačte **Zobrazenie alebo predvídanie správania zákazníkov**. Vyberte **Štart**.

   :::image type="content" source="media/suggested-segments-activity-wizard.png" alt-text="Prvý krok sprievodcu konfiguráciou pre navrhovaný segment na základe aktivity.":::

1. Zadajte požadované vstupné údaje a vyberte **Ďalšie**.

   - Vyberte zákazníkov: Zahrňte všetkých zákazníkov alebo konkrétny segment.
   - Vyberte aktivitu: Vyberte typ aktivity a entity, ktoré aktivitu popisujú.
   - Predvoľby: Nastavte časové obdobie, ktoré je potrebné vziať do úvahy, faktory pre návrhy a mapujte atribúty.

1. Skontrolujte svoje zadanie a stlačte možnosť **Spustiť** na spustenie modelu a generácie návrhov.

V závislosti od počtu profilov zákazníkov a vybraných aktivít môže dokončenie trvať niekoľko minút.

Po vygenerovaní návrhov ich môžete filtrovať podľa dimenzie alebo hodnoty, ktorá vás zaujíma najviac.

## <a name="manage-suggested-segments"></a>Spravujte navrhované segmenty

Ísť do **Segmenty** a vyberte **Návrhy (ukážka)** tab. V **Návrhy založené na aktivitách** vyberte navrhovaný segment na zobrazenie dostupných akcií.

- **Pozri návrh** zobraziť podrobnosti o tomto segmente, ako je rozsah každej dimenzie v porovnaní s cieľovou skupinou. Zdôrazňuje tiež počet potenciálnych členov v segmente a zodpovedajúce percento z celkového počtu zákazníkov.
- **Vytvorte segment** uložiť navrhovanú položku ako segment. Zobrazuje sa na **Všetky segmenty** kartu a môže byť [obnovené alebo odstránené](segments.md). Nemôžete upraviť podrobnosti segmentu. Môžete však zmeniť vstupné kritériá pre návrhy a vygenerovať rôzne návrhy.
- **Upraviť návrhy** na úpravu nakonfigurovaných atribútov, ktoré nahradia aktuálne návrhy.
- **Obnoviť návrhy** na obnovenie návrhov pri zachovaní nakonfigurovaných atribútov.

[!INCLUDE [footer-include](includes/footer-banner.md)]
