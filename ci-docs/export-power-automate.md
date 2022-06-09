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
ms.openlocfilehash: d22c4c785695b23a257a89f1ffa519fdc18b443e
ms.sourcegitcommit: 6a5f4312a2bb808c40830863f26620daf65b921d
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 05/11/2022
ms.locfileid: "8741198"
---
# <a name="power-automate-connector-preview"></a>Konektor Power Automate (ukážka)

[Power Automate](https://flow.microsoft.com/) umožňuje automatické spúšťanie vybratých udalostí pri zmene údajov a priame spravovanie komplexnejších postupov.

## <a name="known-limitations"></a>Známe obmedzenia

- Môžete uskutočniť maximálne 100 hovorov za 60 sekúnd. Koncový bod API môžete volať viackrát pomocou parametra $skip. [Prečítajte si viac o parametri $skip](/connectors/customerinsights/#get-items-from-an-entity).

## <a name="power-automate-triggers"></a>Spúšťače Power Automate

Pomocou spúšťačov môžete vytvárať postupy v cloude a automatizovať opakujúce sa úlohy, napríklad oznámenia alebo pokročilejšie akcie.

- Spúšťač pri zlyhaní obnovenia zdroja údajov.
- Spúšťač pri úspešnom obnovení zdroja údajov.
- Spúšťač pri prekročení prahu v segmente. Spúšťač je obmedzený na prekročenie prahu.
- Spúšťač pri prekročení prahu vo firemnej miere. Podporované sú len podnikové opatrenia bez dimenzie. Spúšťač je obmedzený na prekročenie prahu.
- Spustí sa, keď sa dokončí úplné obnovenie (zdrojov údajov, segmentov, mier, ...).
- Spustiť po dokončení obnovy procesu zjednotenia.

[Nakonfigurujte svoje spúšťače v službe Power Automate.](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/)

## <a name="power-automate-actions"></a>Akcie Power Automate

Konektor Power Automate poskytuje iné akcie ako dostupné spúšťače. Viac informácií nájdete v dokumente [Dynamics 365 Customer Insights Connector](/connectors/customerinsights/).

## <a name="create-a-power-automate-flow"></a>Vytvorte postup Power Automate

1. Prejdite do ponuky **Správca** > **Ciele exportu**.

1. Na dlaždici **Power Automate** vyberte **Nastaviť**.

1. Otvorí sa konektor Customer Insights (verzia Preview) v Power Automate. **Prihláste sa** do Power Automate.

1. Vyberte si jeden z dostupných spúšťačov a do nového postupu pridajte ďalšie kroky. Viac informácií nájdete v časti [Vytvorenie postupu v cloude v Power Automate](/power-automate/get-started-logic-flow).

Príklady použitia tokov: 
- Pošlite správu do kanála Microsoft Teams, ak zlyhá obnovenie zdroja údajov. 
- Po prekročení prahovej hodnoty v segmente pošlite e-mail vlastníkom údajov.



[!INCLUDE [footer-include](includes/footer-banner.md)]