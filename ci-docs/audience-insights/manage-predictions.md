---
title: Zdieľané úlohy pre scenáre predikcia
description: Naučte sa, ako spravovať, riešiť problémy a vylepšovať predikcie.
ms.date: 05/17/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: diegogranados117
ms.author: digranad
manager: shellyha
ms.openlocfilehash: dccb8dcca8f65f64973e46fed9d83034d58282e2
ms.sourcegitcommit: bcc47d15d4f0eacf008e4dbc09baac7f062b3ca8
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 06/29/2021
ms.locfileid: "6315897"
---
# <a name="manage-predictions"></a>Spravovanie predikcií

Tento článok píše o úlohách, ktoré zdieľa väčšina scenárov predikcií.

## <a name="troubleshoot-a-failed-prediction"></a>Riešenie problémov so zlyhaním predikcie

1. Prejdite do ponuky **Analýza** > **Predikcie** a vyberte kartu **Moje predikcie**.

1. Vyberte zvislé tri bodky vedľa predikcie, pre ktorú chcete zobraziť protokoly chýb.

1. Vyberte **Záznamy**.

1. Skontrolujte všetky chyby. Môže sa vyskytnúť niekoľko typov chýb, ktoré popisujú, ktorý stav chybu spôsobil. Napríklad chyba, že nie je dostatok údajov na presnú predikciu, sa zvyčajne vyrieši načítaním ďalších údajov do Customer Insights.

## <a name="input-data-usability-report"></a>Zostava použiteľnosti vstupných údajov

Zostava o použiteľnosti vstupných údajov poskytuje konsolidovaný prehľad o chybách a varovaniach, ktoré môžu generovať vaše vopred pripravené predikcie. Poskytuje tiež odporúčania, ako zlepšiť výkon modelu.

Zostava je k dispozícii po dokončení tréningového procesu modelu. Je vytvorená pre každý model zvlášť, bez ohľadu na to, či bol úspešne dokončený alebo nie.

### <a name="view-the-input-data-usability-report"></a>Prezeranie zostavy použiteľnosti vstupných údajov

Keď vopred pripravený model dokončil krok výuky, pozrite si zostavu:
- Vyberte tri bodky vedľa názvu modelu a zvoľte **Zostava použiteľnosti vstupných údajov**.
- Vyberte stav modelu a **Pozrite si zostavu použiteľnosti vstupných údajov** na bočnej table.
- Vyberte jeden z modelov v zozname a vyberte **Zostava použiteľnosti vstupných údajov** na paneli príkazov.
- Otvorte stránku s výsledkami modelu a vyberte **Zostava použiteľnosti vstupných údajov** na paneli príkazov.

### <a name="information-in-the-input-data-usability-report"></a>Informácie v zostave o použiteľnosti vstupných údajov

Nasledujúce stĺpce v zostave obsahujú užitočné informácie na vylepšenie údajov pre model.

:::image type="content" source="media/input-data-usability-report.png" alt-text="Príklad správy o použiteľnosti vstupných údajov, ktorá zobrazuje tabuľku s chybami, varovaniami a odporúčaniami.":::

- Názov: Popisný názov chyby, varovania alebo odporúčania.
- Krok: Fáza, trénovanie alebo skóre modelu, ktorého sa informácie sa týkajú.
- Stav: Závažnosť informácií (chyba, varovanie, odporúčanie).
- Názov stĺpca: Stĺpec v entite, ktorý je potrebné upraviť, aby sa zlepšil výkon modelu.
- Názov entity: Názov entity, ktorú je potrebné upraviť, aby sa zlepšil výkon modelu.
- Podrobnosti: Podrobnosti o chybe, varovaní alebo odporúčaní.

## <a name="refresh-a-prediction"></a>Obnovenie predikcie

Predikcie sa automaticky obnovujú v rovnakom [harmonogram, ako vaše údaje](system.md#schedule-tab), ako je nakonfigurované v nastaveniach. Môžete ich tiež obnoviť ručne.

1. Prejdite do ponuky **Analýza** > **Predikcie** a vyberte kartu **Moje predikcie**.

1. Vyberte zvislé tri bodky vedľa predikcie, ktorú chcete obnoviť.

1. Vyberte **Obnoviť**.

## <a name="delete-a-prediction"></a>Odstránenie predikcie

Odstránenie predikcie tiež odstráni jeho výstupnú entitu.

1. Prejdite do ponuky **Analýza** > **Predikcie** a vyberte kartu **Moje predikcie**.

1. Vyberte zvislé tri bodky vedľa predikcie, ktorú chcete odstrániť.

1. Vyberte **Odstrániť**.
