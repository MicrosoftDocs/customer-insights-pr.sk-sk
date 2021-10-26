---
title: Príjem údajov prostredníctvom konektora Power Query
description: Konektory pre zdroje údajov založené na Power Query.
ms.date: 09/29/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.openlocfilehash: ab6edc3f33ebacb81f55c0882a78c5827b4384ed
ms.sourcegitcommit: 1565f4f7b4e131ede6ae089c5d21a79b02bba645
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 10/14/2021
ms.locfileid: "7643513"
---
# <a name="connect-to-a-power-query-data-source"></a>Pripojenie k zdroju údajov Power Query

Power Query ponúka širokú škálu konektorov na prijímanie údajov. Väčšinu z týchto konektorov podporuje Dynamics 365 Customer Insights. Pri pridávaní zdrojov údajov na základe konektorov Power Query sa všeobecne postupuje podľa krokov uvedených v nasledujúcej časti. V závislosti od použitého konektora sú však potrebné rôzne informácie. Ďalšie informácie nájdete v dokumentácii o jednotlivých konektoroch v časti [Referencia na konektor Power Query](/power-query/connectors/).

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWN6EK]

## <a name="create-a-new-data-source"></a>Vytvorenie nového zdroja údajov

1. V prehľadoch cieľových skupín prejdite na **Údaje** > **Zdroje údajov**.

1. Vyberte položku **Pridať zdroj údajov**.

1. Vyberte metódu **Import údajov** a **Ďalej**.

1. Zadajte **Názov** pre zdroj údajov a vyberte **Ďalej** na vytvorenie zdroja údajov. Pokyny týkajúce sa pomenovania: 
   - Začnite písmenom.
   - Používajte iba písmená a číslice. Nie je povolené zadávanie špeciálnych znakov a medzier.
   - Použite 3 až 64 znakov.

1. Vyberte jeden z [dostupných konektorov](#available-power-query-data-sources). Pre tento príklad vyberieme konektor **Text/CSV**.

1. Zadajte požadované údaje v časti **Nastavenia spojenia** pre vybraný konektor a vyberte **Ďalej** na zobrazenie ukážky údajov.

1. Vyberte **Zmena údajov**. V tomto kroku pridáte entity do zdroja údajov. Entity sú súbory údajov. Ak máte databázu, ktorá obsahuje viacero množín údajov, každá množina údajov je jej vlastná entita.

1. Dialógové okno **Power Query – úprava dopytov** umožňuje skontrolovať a spresniť údaje. Entity, ktoré systémy identifikovali vo vybratých zdrojoch údajov, sa zobrazia na ľavej table.

   > [!div class="mx-imgBorder"]
   > ![Úprava dialógového okna dotazov.](media/data-manager-configure-edit-queries.png "Úprava dialógového okna dotazov")

1. Údaje môžete aj transformovať. Vyberte entitu, ktorú chcete upraviť alebo transformovať. Použite možnosti v okne Power Query na použitie transformácií. Každá transformácia bude uvedená v zozname **Použité kroky**. Power Query poskytuje množstvo vopred pripravených možností transformácie. Ďalšie informácie nájdete v téme [Transformácie Power Query](/power-query/power-query-what-is-power-query#transformations).

1. Do zdroja údajov môžete pridať ďalšie entity výberom položky **Získať údaje** v dialógovom okne **Upraviť dotazy**.

   Tieto transformácie sú vysoko odporúčané:

   - Ak prijímate údaje zo súboru CSV, prvý riadok často obsahuje hlavičky. Prejdite do časti **Transformovať tabuľku** a vyberte **Ako prvý riadok použiť hlavičky**.
   - Zaistite, aby bol dátový typ nastavený správne.

1. Výberom tlačidla **Uložiť** v spodnej časti okna Power Query uložte transformácie. Po uložení nájdete zdroj údajov v časti **Údaje** > **Zdroje údajov**.

1. Na stránke **Zdroje údajov** si všimnete, že je tu nový zdroj údajov v stave **Obnovuje sa**.

## <a name="available-power-query-data-sources"></a>Dostupné zdroje údajov pre Power Query

V časti [Referencia na konektor Power Query](/power-query/connectors/) si môžete pozrieť aktuálny zoznam konektorov, ktoré môžete zvoliť na import údajov do Customer Insights. 

Konektory so značkou začiarknutia v stĺpci **Customer Insights (toky údajov)** sú k dispozícii na vytvorenie nových zdrojov údajov na základe Power Query. V dokumentácii konkrétneho konektora sa dozviete viac o jeho požiadavkách, obmedzeniach a ďalších podrobnostiach.

## <a name="edit-power-query-data-sources"></a>Úprava zdrojov údajov pre Power Query

> [!NOTE]
> Nemusí byť možné vykonať zmeny zdrojov údajov, ktoré sa momentálne používajú v niektorom z procesov aplikácie (napríklad *segmentácia*, *zosúladenie* alebo *zlúčenie*). 
>
> Pomocou stránky **Nastavenia** môžete sledovať priebeh každého aktívneho procesu. Po dokončení procesu sa môžete vrátiť na stránku **Zdroje údajov** a vykonať zmeny.

1. V prehľadoch cieľových skupín prejdite na **Údaje** > **Zdroje údajov**.

2. Vyberte zvislé tri bodky vedľa zdroja údajov, ktorý chcete zmeniť, a z rozbaľovacieho zoznamu vyberte položku **Upraviť**.

   > [!div class="mx-imgBorder"]
   > ![Úprava možnosti.](media/edit-option-data-sources.png "Úprava možnosti")

3. Použite svoje zmeny a transformácie v dialógovom okne **Power Query – Upraviť dotazy**, ako je opísané v časti [Vytvorenie nového zdroja údajov](#create-a-new-data-source).

4. Vyberte **Uložiť** v Power Query po dokončení úprav a uložte zmeny.


[!INCLUDE[footer-include](../includes/footer-banner.md)]