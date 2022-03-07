---
title: Konektor Power Automate | Dokumentácia spoločnosti Microsoft
description: Vytvorenie postupov v Microsoft Power Automate z Dynamics 365 Customer Insights.
ms.date: 06/24/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: dc9bbe22b7f10cf92f06cae18fbece9808b87dce
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 02/16/2022
ms.locfileid: "8226733"
---
# <a name="power-automate-connector-preview"></a>Konektor Power Automate (ukážka)

[Power Automate](https://flow.microsoft.com/) umožňuje automatické spúšťanie vybratých udalostí pri zmene údajov a priame spravovanie komplexnejších postupov.

## <a name="power-automate-triggers"></a>Spúšťače Power Automate

Pomocou spúšťačov môžete vytvárať postupy v cloude a automatizovať opakujúce sa úlohy, napríklad oznámenia alebo pokročilejšie akcie. 

- Spúšťač pri zlyhaní obnovenia zdroja údajov. 
- Spúšťač pri úspešnom obnovení zdroja údajov.
- Spúšťač pri prekročení prahu v segmente. Spúšťač je obmedzený na prekročenie prahu.
- Spúšťač pri prekročení prahu vo firemnej miere. Podporované sú len podnikové opatrenia bez dimenzie. Spúšťač je obmedzený na prekročenie prahu.
- Spustí sa, keď sa dokončí úplné obnovenie (zdrojov údajov, segmentov, mier, ...).
- Spustí sa, keď sa dokončí aktualizácia procesu zjednotenia (priradenie, párovanie, zlúčenie).

[Nakonfigurujte svoje spúšťače v službe Power Automate.](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/)

## <a name="power-automate-actions"></a>Akcie Power Automate

Konektor Power Automate poskytuje iné akcie ako dostupné spúšťače. Viac informácií nájdete v dokumente [Dynamics 365 Customer Insights Connector](/connectors/customerinsights/).

## <a name="create-a-power-automate-flow"></a>Vytvorte postup Power Automate

1. V prehľadoch cieľových skupín prejdite na **Správca** > **Ciele exportu**.

1. Na dlaždici **Power Automate** vyberte **Nastaviť**.

1. Otvorí sa konektor Customer Insights (verzia Preview) v Power Automate. **Prihláste sa** do Power Automate.

1. Vyberte si jeden z dostupných spúšťačov a do nového postupu pridajte ďalšie kroky. Viac informácií nájdete v časti [Vytvorenie postupu v cloude v Power Automate](/power-automate/get-started-logic-flow).

Príklady použitia tokov: 
- Pošlite správu do kanála Microsoft Teams, ak zlyhá obnovenie zdroja údajov. 
- Po prekročení prahovej hodnoty v segmente pošlite e-mail vlastníkom údajov.



[!INCLUDE[footer-include](../includes/footer-banner.md)]
