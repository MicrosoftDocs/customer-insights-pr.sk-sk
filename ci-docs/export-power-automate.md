---
title: Power Automate konektor (náhľad) | Dokumenty Microsoft
description: Vytvorenie postupov v Microsoft Power Automate z Dynamics 365 Customer Insights.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: f87bd6db7143294a264813f6c5c7d7963f303628
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196137"
---
# <a name="power-automate-connector-preview"></a>Konektor Power Automate (ukážka)

[Microsoft Power Automate](https://flow.microsoft.com/) umožňuje automatické spúšťanie vybratých udalostí pri zmene údajov a priame spravovanie komplexnejších postupov.

## <a name="known-limitations"></a>Známe obmedzenia

- Maximálne 100 hovorov za 60 sekúnd. Použi [$skip parameter](/connectors/customerinsights/#get-items-from-an-entity) viackrát zavolať koncový bod API.

## <a name="power-automate-triggers"></a>Spúšťače Power Automate

Pomocou spúšťačov môžete vytvárať postupy v cloude a automatizovať opakujúce sa úlohy, napríklad oznámenia alebo pokročilejšie akcie. Použite spúšťače, keď:

- Obnovenie zdroj údajov zlyhá.
- Obnovenie zdroj údajov je úspešné.
- Na segmente je prekročený prah. Spúšťač je obmedzený na prekročenie prahu.
- Pri obchodnom opatrení je prekročená hranica. Podporované sú len podnikové opatrenia bez dimenzie. Spúšťač je obmedzený na prekročenie prahu.
- Úplné naplánované obnovenie je dokončené. Tento spúšťač nefunguje pre manuálne spustené obnovy.
- Obnovenie procesu zjednotenia je dokončené.

[Nakonfigurujte svoje spúšťače v službe Power Automate.](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/)

## <a name="power-automate-actions"></a>Akcie Power Automate

Konektor Power Automate poskytuje iné akcie ako dostupné spúšťače. Viac informácií nájdete v dokumente [Dynamics 365 Customer Insights Connector](/connectors/customerinsights/).

## <a name="create-a-power-automate-flow"></a>Vytvorte postup Power Automate

1. Prejdite do časti **Správca** > **Pripojenia**.

1. Na dlaždici **Power Automate** vyberte **Nastaviť**.

1. Otvorí sa konektor Customer Insights (verzia Preview) v Power Automate. **Prihláste sa** do Power Automate.

1. Vyberte si jeden z dostupných spúšťačov a do nového postupu pridajte ďalšie kroky. Viac informácií nájdete v časti [Vytvorenie postupu v cloude v Power Automate](/power-automate/get-started-logic-flow).

Príklady použitia tokov: 
- Pošlite správu do kanála Microsoft Teams, ak zlyhá obnovenie zdroja údajov. 
- Po prekročení prahovej hodnoty v segmente pošlite e-mail vlastníkom údajov.

[!INCLUDE [footer-include](includes/footer-banner.md)]
