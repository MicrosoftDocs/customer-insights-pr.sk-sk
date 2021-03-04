---
title: Konektor Power Automate | Dokumentácia spoločnosti Microsoft
description: Vytvárajte toky v Microsoft Power Automate z Dynamics 365 Customer Insights.
ms.date: 01/20/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
ms.reviewer: philk
manager: shellyha
ms.openlocfilehash: fb1df4e9ab1f78300b8ec1f8dfdfbfbac0e71447
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268843"
---
# <a name="power-automate-connector-preview"></a>Konektor Power Automate (ukážka)

[Power Automate](https://flow.microsoft.com/) umožňuje automatické spúšťanie vybratých udalostí pri zmene údajov a priame spravovanie komplexnejších postupov.

## <a name="power-automate-triggers"></a>Spúšťače Power Automate

Pomocou spúšťačov môžete vytvárať postupy v cloude a automatizovať opakujúce sa úlohy, napríklad oznámenia alebo pokročilejšie akcie. 

- Spúšťač pri zlyhaní obnovenia zdroja údajov. 
- Spúšťač pri úspešnom obnovení zdroja údajov.
- Spúšťač pri prekročení prahu v segmente. Spúšťač je obmedzený na prekročenie prahu.
- Spúšťač pri prekročení prahu vo firemnej miere. Spúšťač je obmedzený na prekročenie prahu.
- Spustí sa, keď sa dokončí úplné obnovenie (zdrojov údajov, segmentov, mier, ...).
- Spustí sa, keď sa dokončí aktualizácia procesu zjednotenia (priradenie, párovanie, zlúčenie).

[Nakonfigurujte svoje spúšťače v Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).

## <a name="power-automate-actions"></a>Akcie Power Automate
Konektor Power Automate poskytuje iné akcie ako dostupné spúšťače. Viac informácií nájdete v dokumente [Dynamics 365 Customer Insights Connector](https://docs.microsoft.com/connectors/customerinsights/).

## <a name="create-a-power-automate-flow"></a>Vytvorte postup Power Automate

1. V prehľadoch cieľových skupín prejdite na **Správca** > **Ciele exportu**.

1. Na dlaždici **Power Automate** vyberte **Nastaviť**.

1. Otvorí sa konektor Customer Insights (verzia Preview) v Power Automate. **Prihláste sa** do Power Automate.

1. Vyberte si jeden z dostupných spúšťačov a do nového postupu pridajte ďalšie kroky. Viac informácií nájdete v časti [Vytvorenie postupu v cloude v Power Automate](https://docs.microsoft.com/power-automate/get-started-logic-flow).

Príklady použitia postupov: 
- Pošlite správu do kanála Microsoft Teams, ak zlyhá obnovenie zdroja údajov. 
- Po prekročení prahovej hodnoty v segmente pošlite e-mail vlastníkom údajov.



[!INCLUDE[footer-include](../includes/footer-banner.md)]