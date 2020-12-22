---
title: Konektor Power Automate | Dokumentácia spoločnosti Microsoft
description: Vytvárajte toky v Microsoft Power Automate z Dynamics 365 Customer Insights.
ms.date: 08/03/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: philk
manager: shellyha
ms.openlocfilehash: ffe92414365b0b777691a4a2d585100e4fbea591
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406890"
---
# <a name="power-automate-connector-preview"></a>Konektor Power Automate (ukážka)

[Power Automate](https://flow.microsoft.com/) umožňuje automatické spúšťanie vybratých udalostí pri zmene údajov a priame spravovanie komplexnejších postupov.

## <a name="power-automate-triggers"></a>Spúšťače Power Automate

Môžete použiť rôzne spúšťače, ktoré vám umožňujú vytvárať toky na automatizáciu opakujúcich sa úloh, ako sú upozornenia alebo pokročilejšie akcie. 

- Spúšťač pri zlyhaní obnovenia zdroja údajov. 
- Spúšťač pri úspešnom obnovení zdroja údajov.
- Spúšťač pri prekročení prahu v segmente. Spúšťač je obmedzený na prekročenie prahu.
- Spúšťač pri prekročení prahu vo firemnej miere. Spúšťač je obmedzený na prekročenie prahu.
- Spustí sa, keď sa dokončí úplné obnovenie (zdrojov údajov, segmentov, mier, ...).
- Spustí sa, keď sa dokončí aktualizácia procesu zjednotenia (priradenie, párovanie, zlúčenie).

[Nakonfigurujte svoje spúšťače v Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).

## <a name="power-automate-actions"></a>Akcie Power Automate
Konektor Power Automate poskytuje iné akcie ako dostupné spúšťače. Viac informácií nájdete v dokumente [Dynamics 365 Customer Insights Connector](https://docs.microsoft.com/connectors/customerinsights/).

## <a name="create-a-power-automate-flow-in-audience-insights"></a>Vytvorenie postupu služby Power Automate v prehľadoch cieľových skupín

1. V prehľadoch cieľových skupín prejdite na **Správca** > **Systém**.

1. Na stránke **Systém** vyberte kartu **Stav**.

1. V sekcii **Zdroje údajov** vyberte **Postupy** a vyberte **Vytvoriť postup** z rozbaľovacieho zoznamu.
   > [!div class="mx-imgBorder"]
   > ![Konektor Power Automate zobrazujúci akciu Vytvorenie toku](media/power-automate-connector-create-flow.png "Konektor Power Automate zobrazujúci akciu Vytvorenie toku")

1. V Power Automate vyberte jeden z dostupných spúšťačov a vytvorte požadovaný postup. Ak vytvárate svoj prvý tok, musíte sa najprv autentifikovať pomocou konektora Power Automate.
