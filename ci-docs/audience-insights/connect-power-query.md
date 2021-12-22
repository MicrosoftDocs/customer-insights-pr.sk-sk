---
title: Prijímanie údajov cez konektor Power Query (video)
description: Konektory pre zdroje údajov založené na Power Query.
ms.date: 12/06/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.openlocfilehash: 38c447d80a25feca087ca9f110278b8401423018
ms.sourcegitcommit: 12910882ca990ec0e890ed4deaf3dac7e01621e5
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 12/10/2021
ms.locfileid: "7903859"
---
# <a name="connect-to-a-power-query-data-source"></a>Pripojenie k zdroju údajov Power Query

Power Query ponúka širokú škálu konektorov na prijímanie údajov. Väčšinu z týchto konektorov podporuje Dynamics 365 Customer Insights. 

Pridávanie zdrojov údajov na základe Power Query konektorov sa vo všeobecnosti riadi krokmi uvedenými v tejto časti. V závislosti od použitého konektora sú však potrebné rôzne informácie. Ak sa chcete dozvedieť viac, pozrite si dokumentáciu o jednotlivých konektoroch v [Power Query odkaz na konektor](/power-query/connectors/).

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWN6EK]

## <a name="create-a-new-data-source"></a>Vytvorenie nového zdroja údajov

1. V prehľadoch cieľových skupín prejdite na **Údaje** > **Zdroje údajov**.

1. Vyberte položku **Pridať zdroj údajov**.

1. Vyberte **Microsoft Power Query** a potom vyberte **Ďalšie**.

1. Zadajte **Názov** pre zdroj údajov a vyberte **Ďalej** na vytvorenie zdroja údajov.

1. Vyberte jeden z [dostupných konektorov](#available-power-query-data-sources). V tomto príklade vyberieme **Text/CSV** konektor.

1. Zadajte požadované údaje v časti **Nastavenia spojenia** pre vybraný konektor a vyberte **Ďalej** na zobrazenie ukážky údajov.

1. Vyberte **Zmena údajov**. V tomto kroku pridáte entity do zdroja údajov. Entity sú súbory údajov. Ak máte databázu, ktorá obsahuje viacero množín údajov, každá množina údajov je jej vlastná entita.

1. Dialógové okno **Power Query – úprava dopytov** umožňuje skontrolovať a spresniť údaje. Entity, ktoré systémy identifikovali vo vybratých zdrojoch údajov, sa zobrazia na ľavej table.

   > [!div class="mx-imgBorder"]
   > ![Úprava dialógového okna dotazov.](media/data-manager-configure-edit-queries.png "Úprava dialógového okna dotazov")

1. Údaje môžete aj transformovať. Vyberte entitu, ktorú chcete upraviť alebo transformovať. Použite možnosti v okne Power Query na použitie transformácií. Každá transformácia bude uvedená v zozname **Použité kroky**. Power Query poskytuje množstvo vopred pripravených možností transformácie. Ďalšie informácie nájdete v téme [Transformácie Power Query](/power-query/power-query-what-is-power-query#transformations).

1. Do zdroja údajov môžete pridať ďalšie entity výberom položky **Získať údaje** v dialógovom okne **Upraviť dotazy**.

   Odporúčame vám použiť nasledujúce transformácie:

   - Ak prijímate údaje zo súboru CSV, prvý riadok často obsahuje hlavičky. Prejdite do časti **Transformovať tabuľku** a vyberte **Ako prvý riadok použiť hlavičky**.
   - Zaistite, aby bol dátový typ nastavený správne.

1. Výberom tlačidla **Uložiť** v spodnej časti okna Power Query uložte transformácie. Po uložení nájdete zdroj údajov v časti **Údaje** > **Zdroje údajov**.

1. Na stránke **Zdroje údajov** si všimnete, že je tu nový zdroj údajov v stave **Obnovuje sa**.

## <a name="available-power-query-data-sources"></a>Dostupné zdroje údajov pre Power Query

Pozrite si [Power Query odkaz na konektor](/power-query/connectors/) nájdete zoznam konektorov, ktoré môžete použiť na import údajov do Customer Insights. 

Konektory so značkou začiarknutia v stĺpci **Customer Insights (toky údajov)** sú k dispozícii na vytvorenie nových zdrojov údajov na základe Power Query. V dokumentácii konkrétneho konektora sa dozviete viac o jeho požiadavkách, obmedzeniach a ďalších podrobnostiach.

## <a name="edit-power-query-data-sources"></a>Úprava zdrojov údajov pre Power Query

> [!NOTE]
> Nemusí byť možné vykonať zmeny zdrojov údajov, ktoré sa momentálne používajú v niektorom z procesov aplikácie (napríklad *segmentácia*, *zosúladenie* alebo *zlúčenie*). 
>
> V **nastavenie** môžete sledovať priebeh každého z aktívnych procesov. Po dokončení procesu sa môžete vrátiť na stránku **Zdroje údajov** a vykonať zmeny.

1. V prehľadoch cieľových skupín prejdite na **Údaje** > **Zdroje údajov**.

2. Vyberte zvislé tri bodky vedľa zdroja údajov, ktorý chcete zmeniť, a z rozbaľovacieho zoznamu vyberte položku **Upraviť**.

   > [!div class="mx-imgBorder"]
   > ![Úprava možnosti.](media/edit-option-data-sources.png "Úprava možnosti")

   [!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]
   
3. Použite svoje zmeny a transformácie v dialógovom okne **Power Query – Upraviť dotazy**, ako je opísané v časti [Vytvorenie nového zdroja údajov](#create-a-new-data-source).

4. Vyberte **Uložiť** v Power Query po dokončení úprav a uložte zmeny.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
