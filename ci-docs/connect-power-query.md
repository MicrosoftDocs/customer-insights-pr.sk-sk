---
title: Spracovanie údajov prostredníctvom a Power Query konektor (obsahuje video)
description: Konektory pre zdroje údajov založené na Power Query.
ms.date: 12/06/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
searchScope:
- ci-data-sources
- ci-create-data-source
- customerInsights
ms.openlocfilehash: 50258365c3134c588aa79ec72c66d0de329e0ff1
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 04/27/2022
ms.locfileid: "8643358"
---
# <a name="connect-to-a-power-query-data-source"></a>Pripojte sa k a Power Query zdroj údajov

Power Query ponúka širokú škálu konektorov na prijímanie údajov. Väčšinu z týchto konektorov podporuje Dynamics 365 Customer Insights. 

Pridávanie zdrojov údajov na základe Power Query konektory sa vo všeobecnosti riadia krokmi uvedenými v tejto časti. V závislosti od použitého konektora sú však potrebné rôzne informácie. Ak sa chcete dozvedieť viac, pozrite si dokumentáciu o jednotlivých konektoroch v [Power Query odkaz na konektor](/power-query/connectors/).

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWN6EK]

## <a name="create-a-new-data-source"></a>Vytvorenie nového zdroja údajov

1. Prejdite do **Údaje** > **Zdroje údajov**.

1. Vyberte položku **Pridať zdroj údajov**.

1. Vybrať **Microsoft Power Query**.

1. Zadajte **Názov** pre zdroj údajov a vyberte **Ďalej** na vytvorenie zdroja údajov.

1. Vyberte jeden z [dostupných konektorov](#available-power-query-data-sources). V tomto príklade vyberieme **Text/CSV** konektor.

1. Zadajte požadované údaje v časti **Nastavenia spojenia** pre vybraný konektor a vyberte **Ďalej** na zobrazenie ukážky údajov.

1. Vyberte **Zmena údajov**. V tomto kroku pridáte entity do zdroja údajov. Entity sú súbory údajov. Ak máte databázu, ktorá obsahuje viacero množín údajov, každá množina údajov je jej vlastná entita.

1. The **Power Query - Upraviť otázky** dialógové okno vám umožňuje kontrolovať a upravovať údaje. Entity, ktoré systémy identifikovali vo vybratých zdrojoch údajov, sa zobrazia na ľavej table.

   > [!div class="mx-imgBorder"]
   > ![Úprava dialógového okna dotazov.](media/data-manager-configure-edit-queries.png "Úprava dialógového okna dotazov")

1. Údaje môžete aj transformovať. Vyberte entitu, ktorú chcete upraviť alebo transformovať. Použite možnosti v Power Query okno na použitie transformácií. Každá transformácia bude uvedená v zozname **Použité kroky**. Power Query poskytuje množstvo vopred pripravených možností transformácie. Viac informácií nájdete v časti [Power Query Premeny](/power-query/power-query-what-is-power-query#transformations).

   Odporúčame vám použiť nasledujúce transformácie:

   - Ak prijímate údaje zo súboru CSV, prvý riadok často obsahuje hlavičky. Ísť do **Transformovať** a vyberte **Použite prvý riadok ako hlavičky**.
   - Zaistite, aby bol dátový typ nastavený správne. Napríklad pre polia dátumu vyberte typ dátumu.

1. Ak chcete pridať ďalšie entity do zdroj údajov v **Upraviť dopyty** dialóg, prejdite na **Domov** a vyberte **Získajte údaje**.

1. Vyberte **Uložiť** v spodnej časti Power Query okno na uloženie transformácií. Po uložení nájdete zdroj údajov v časti **Údaje** > **Zdroje údajov**.

1. Na stránke **Zdroje údajov** si všimnete, že je tu nový zdroj údajov v stave **Obnovuje sa**.

## <a name="available-power-query-data-sources"></a>Dostupné Power Query zdroje dát

Pozrite si [Power Query odkaz na konektor](/power-query/connectors/) nájdete zoznam konektorov, ktoré môžete použiť na import údajov do Customer Insights. 

Konektory so začiarknutím v **Customer Insights (údajové toky)** sú k dispozícii na vytvorenie nových zdrojov údajov na základe Power Query. V dokumentácii konkrétneho konektora sa dozviete viac o jeho požiadavkách, obmedzeniach a ďalších podrobnostiach.

## <a name="edit-power-query-data-sources"></a>Upraviť Power Query zdroje dát

> [!NOTE]
> Nemusí byť možné vykonať zmeny zdrojov údajov, ktoré sa momentálne používajú v niektorom z procesov aplikácie (napríklad *segmentácia*, *zosúladenie* alebo *zlúčenie*). 
>
> V **nastavenie** môžete sledovať priebeh každého z aktívnych procesov. Po dokončení procesu sa môžete vrátiť na stránku **Zdroje údajov** a vykonať zmeny.

1. Prejdite do **Údaje** > **Zdroje údajov**.

2. Vyberte zvislé tri bodky vedľa zdroja údajov, ktorý chcete zmeniť, a z rozbaľovacieho zoznamu vyberte položku **Upraviť**.

   > [!div class="mx-imgBorder"]
   > ![Úprava možnosti.](media/edit-option-data-sources.png "Úprava možnosti")

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]
   
3. Aplikujte svoje zmeny a transformácie v **Power Query - Upraviť otázky** dialóg, ako je popísané v [Vytvorte nový zdroj údajov](#create-a-new-data-source) oddiele.

4. Vyberte **Uložiť** v Power Query po dokončení úprav uložte zmeny.


[!INCLUDE [footer-include](includes/footer-banner.md)]
