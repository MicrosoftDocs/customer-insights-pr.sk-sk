---
title: Segmenty navrhované na základe aktivity.
description: Nechajte strojové učenie pomôcť vám nájsť nové a zaujímavé segmenty založené na aktivite zákazníkov.
ms.date: 05/11/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
manager: shellyha
ms.openlocfilehash: 14d9d4f0df6b5835f21fb63447d05853ee98a757
ms.sourcegitcommit: 8341fa964365c185b65bc4b71fc0c695ea127dc0
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 05/14/2021
ms.locfileid: "6034113"
---
# <a name="suggested-segments-based-on-activity-data-preview"></a>Segmenty navrhované na základe údajov aktivity (verzia Preview).

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
Ak podnikáte v zdravotníctve a poskytujete verejnú zdravotnú starostlivosť, vaším cieľom je minimalizovať náklady na jednotlivých pacientov. Spôsobom, ako to urobiť, môže byť zníženie opakujúcich sa návštev poskytovaním najlepšej možnej starostlivosti pri čo najmenšom počte návštev. V takom prípade je vaším cieľom udržiavať nízku frekvenciu návštev a minimalizovať opakujúce sa náklady na pacientov. Alebo môžete identifikovať segmenty pacientov, ktorí majú časté plánované činnosti a vysoké opakujúce sa náklady, a analyzovať tieto prípady s cieľom zlepšiť liečbu jednotlivca. 

## <a name="required-data"></a>Požadované údaje

Návrhy sa generujú na základe vybratých vstupných údajov. 

- Profily zákazníkov: Všetci zákazníci alebo členovia konkrétneho segmentu. 

- Časové obdobie: minulý mesiac, minulý rok alebo ľubovoľný vlastný časový rámec.

- Typ aktivity: nákupy, maloobchodné transakcie, online transakcie, prípady podpory zákazníkov, predplatné atď.  

- Entita v Customer Insights, ktorá obsahuje údaje o aktivite: entita UnifiedActivity alebo entita pre konkrétnu aktivitu. 

- Zahrnuté dimenzie: Aktuálnosť, frekvencia alebo peňažná dimenzia v závislosti od vašich obchodných požiadaviek.

## <a name="generate-suggested-segments"></a>Generovanie navrhovaných segmentov

1. Prejdite na **Segmenty**.

1. Vyberte kartu **Návrhy (ukážka)**.

1. Stlačte možnosť **Vyhľadanie nových návrhov** a stlačte **Zobrazenie alebo predvídanie správania zákazníkov**. Stlačte **Spustiť** na spustenie riadenej používateľskej skúsenosti.

   :::image type="content" source="media/suggested-segments-activity-wizard.png" alt-text="Prvý krok sprievodcu konfiguráciou pre navrhovaný segment na základe aktivity.":::

1. Zadajte požadované vstupné údaje a pokračujte stlačením možnosti **Ďalej**.

   - Vyberte zákazníkov: Zahrňte všetkých zákazníkov alebo konkrétny segment.
   - Vyberte aktivitu: Vyberte typ aktivity a entity, ktoré aktivitu popisujú.
   - Predvoľby: Nastavte časové obdobie, ktoré je potrebné vziať do úvahy, faktory pre návrhy a mapujte atribúty.

1. Skontrolujte svoje zadanie a stlačte možnosť **Spustiť** na spustenie modelu a generácie návrhov.

1. V závislosti od počtu profilov zákazníkov a vybraných aktivít môže dokončenie trvať niekoľko minút. 

Po vygenerovaní návrhov ich môžete filtrovať podľa dimenzie alebo hodnoty, ktorá vás zaujíma najviac. 

## <a name="view-details-of-a-suggested-segment"></a>Zobrazenie podrobností o navrhovanom segmente

Po vygenerovaní návrhov ich nájdete na zozname **Segmenty** > **Návrhy (verzia Preview)** v časti **Návrhy založené na aktivite**.

:::image type="content" source="media/suggested-segments-details.png" alt-text="Rozšírená bočná tabla zobrazujúca podrobné údaje o navrhovanom segmente.":::

Stlačte možnosť **Zobraziť návrh** na navrhovanom segmente pre zobrazenie podrobností o danom segmente. Bočná tabla poskytuje podrobnosti, ako je rozsah každej dimenzie v porovnaní s cieľovou skupinou. Zdôrazňuje tiež počet potenciálnych členov v segmente a zodpovedajúce percento z celkového počtu zákazníkov. Ak si chcete ponechať návrh ako segment, stlačte možnosť **Vytvoriť segment**.    

## <a name="save-a-suggestion-as-a-segment"></a>Uloženie návrhu ako segmentu

1. Prejdite na **Segmenty** > **Návrhy (ukážka)**.

1. Vyberte segment, ktorý chcete uložiť. 

1. Na bočnom paneli stlačte možnosť **Vytvoriť segment**. 

1. Po uložení sa segment zobrazí v zozname segmentov na karte **Všetky segmenty**. Teraz ho možno [ obnoviť alebo odstrániť ako každý iný segment](segments.md). Nemôžete upraviť podrobnosti segmentu. Môžete však zmeniť vstupné kritériá pre návrhy a vygenerovať rôzne návrhy.

## <a name="refresh-or-edit-a-set-of-suggestions"></a>Obnovenie alebo úprava skupiny návrhov

1. Prejdite do **Segmenty** > **Návrhy (verzia Preview)** a vyhľadajte segment v sekcii **Návrhy založené na aktivite**.

1. Vyberte **Obnoviť návrhy** na obnovenie návrhov pri zachovaní nakonfigurovaných atribútov. Alebo stlačte možnosť **Upraviť návrhy** a upravte nakonfigurované atribúty. Systém znova spustí proces, vygeneruje návrhy segmentov na základe najnovších údajov a nahradí súčasné návrhy.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
