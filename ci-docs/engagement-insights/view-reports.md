---
title: Zobrazenie výkazov údajov
description: Použite dostupné zostavy na zobrazenie aktivity na vašej lokalite v reálnom čase.
author: darrinw-docs
ms.reviewer: mhart
ms.author: darrinw
ms.date: 06/18/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: cb6d9ab75b95a5f677d2267f5412a55327930987b2fc3a1a21958633a8116bd2
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036667"
---
# <a name="view-reports"></a>Zobraziť zostavy

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Zostava je súborom vizualizácií údajov, ktoré využívajú údaje zhromaždené prostredníctvom súpravy SDK, ktoré vám pomôžu merať a porozumieť správaniu používateľov. Prehľady interakcií Dynamics 365 Customer Insights zahŕňajú vopred pripravené (OOB) zostavy pre webové a mobilné projekty.  

## <a name="web-reports"></a>Webové zostavy

Prístup k webovým zostavám môžete získať v sekcii **Objavovať** na ľavej navigačnej table.

:::image type="content" source="media/report-menu.png" alt-text="Navigácia zobrazujúca zoznam dostupných správ.":::

### <a name="real-time-usage-report"></a>Zostava o používaní v reálnom čase

Zostava **Využitie v reálnom čase** poskytuje prehľad o aktuálnej aktivite na vašej lokalite, ktorý sa automaticky obnovuje každú minútu. Využitie v reálnom čase môžete využiť na sledovanie vplyvu marketingových kampaní, tlačových udalostí a ďalších scenárov na prenos na vašej lokalite.

### <a name="key-metrics-reports"></a>Zostavy hlavných metrík

- **Zobrazenia stránok** obsahuje zoznam zobrazení jednotlivých stránok spolu s celkovým počtom zobrazení stránok vo vybranom časovom rámci.

- **Návštevy** ukazujú informácie o počte návštev a trvaní návštevy.

- **Návštevníci** informujú o nových a vracajúcich sa jedinečných návštevníkoch vašej lokality.

### <a name="content-reports"></a>Výkazy o obsahu

- **Odkazy** ukazujú informácie o počte a type kliknutí.

- **Koncové stránky** obsahujú zoznam odkazov, na ktoré návštevníci klikli, aby opustili vašu lokalitu.

### <a name="traffic-sources-reports"></a>Výkazy o zdrojoch prenosu

- **Sprostredkovatelia** obsahujú zoznam domén a adries URL, ktoré odkázali návštevníkov na vašu lokalitu.

- **Sledovacie kódy** uvádzajú podrobnosti o sledovacích kódoch v odkazoch, ktoré priviedli návštevníkov na vašu lokalitu.

### <a name="visitor-profiles-reports"></a>Zostavy profilov návštevníkov

- **Zariadenia** uvádzajú zoznam fyzických zariadení, ktoré boli použité na prístup na vašu lokalitu.

- **OS a prehliadače** poskytujú informácie o operačných systémoch a prehľadávačoch, ktoré boli spustené pri prístupe na vašu lokalitu.

- **Umiestnenia** ukazujú informácie o návštevníkoch podľa štátu, regiónu a mesta.

- **Jazyky** obsahujú zoznam zobrazení stránok podľa preferovaných jazykov návštevníka.

## <a name="mobile-reports"></a>Mobilné zostavy

Mobilné zostavy sú zoskupené do kategórií podľa použitia v reálnom čase, aplikácií a používateľov. Prístup k mobilným zostavám môžete získať v sekcii **Objavovať** na ľavej navigačnej table.   

:::image type="content" source="media/mobile-reports.png" alt-text="Používateľské rozhranie prehľadov interakcií, ktoré ukazuje prehľad používania v reálnom čase, ktorý vykresľuje údaje v grafoch a zoznamoch.":::   

### <a name="real-time-usage"></a>Používanie v reálnom čase

**Využitie v reálnom čase** poskytuje prehľad o aktuálnej aktivite vo vašej mobilnej aplikácii, ktorá sa automaticky obnovuje každú minútu. Pomocou použitia v reálnom čase môžete monitorovať počet používateľov a relácií, ktoré sú momentálne aktívne vo vašej aplikácii, ako aj najvyššieho počtu zobrazení na obrazovke.

### <a name="app-reports"></a>Zostavy aplikácií

- **Zobrazenia na obrazovke** obsahujú zoznam zobrazení na jednotlivých obrazovkách v aplikácii a celkový počet zobrazení na obrazovke vo vybranom časovom rámci. Zobrazenia na obrazovke si môžete zobraziť podľa názvu obrazovky alebo podľa titulu obrazovky.

- **Relácie** ukazujú informácie o počte relácií a trvaní relácie.

- **Frekvencia návratu** zoskupuje počet relácií podľa počtu dní od poslednej relácie.

- **Používatelia** ukazujú nových a vracajúcich sa používateľov vo vašej mobilnej aplikácii.

- **Udalosti** obsahujú zoznam všetkých udalostí získaných z vašej aplikácie a tiež celkový počet jednotlivých udalostí.

### <a name="user-reports"></a>Zostavy používateľov

- **Verzie aplikácie** obsahujú zoznam verzií mobilnej aplikácie, ktoré používa vaša používateľská základňa.

- **Zariadenia a verzie OS** poskytujú prehľady o tom, na ktorých zariadeniach a operačných systémoch je spustená vaša mobilná aplikácia.

- **Umiestnenia** ukazujú informácie o používateľoch aplikácie podľa štátu, regiónu a mesta.

## <a name="filter-by-time-or-value"></a>Filtrovať podľa času alebo hodnoty

Môžete zvoliť časový rámec alebo hodnotu vo webovej alebo mobilnej zostave, aby ste sa zamerali na hodnotu alebo časové obdobie. 

- Ak chcete zvoliť časový rámec, vyberte možnosť **Viac [...]** z rozbaľovacieho zoznamu zostavy. Pre prehľad používania v reálnom čase je výber časového rozsahu zakázaný; časový rozsah pre prehľad používania v reálnom čase je „teraz“.

- Vo väčšine prehľadov vyberte hodnotu v grafe alebo zozname, aby sa prehľad filtroval pre vybratú hodnotu.

[!INCLUDE[footer-include](../includes/footer-banner.md)]