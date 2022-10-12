---
title: Vytvorte segment na základe predikcia modelu
description: Vytvorte segmenty na základe výstupnej entity modelu predikcia.
ms.date: 09/19/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: ed9c6247a1f9148628dc9b5217484e98a576224e
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610439"
---
# <a name="create-a-segment-based-on-a-prediction-model-preview"></a>Vytvorte segment na základe modelu predikcie (verzie Preview)

Výsledky predpovedí sa niekedy vzťahujú iba na podmnožinu vašich zákazníkov. Zvýšte prispôsobenie odporúčaní vytvorením segmentov z výsledkov modelov predikcie. Môžete napríklad chcieť dať konkrétne odporúčania zákazníkom, ktorí uprednostňujú určitý typ služby.

## <a name="prerequisites"></a>Predpoklady

- Minimálne [povolenia prispievateľa](permissions.md) v Customer Insights.

- Odporúčanie produktu, zmena transakcie, zmena predplatného alebo model životnej hodnoty zákazníka nakonfigurovaný v nástroji Customer Insights. Skontrolujte požiadavky na nastavenie rôznych modelov:

  - [Model odporúčaní produktov](predict-product-recommendation.md)
  - [Model odchodu predplatiteľov](predict-subscription-churn.md)
  - [Transakčný model churn](predict-transactional-churn.md)
  - [Model celoživotnej hodnoty zákazníka](predict-customer-lifetime-value.md)

## <a name="create-a-customer-segment-based-on-predictions"></a>Vytvorte segment zákazníka na základe predikcií

1. Prejdite do ponuky **Analýza** > **Predikcie** a vyberte kartu **Moje predikcie**.

1. Vyberte model, ktorý chcete skontrolovať, a vyberte ho **Vyhliadka**.

1. Na stránke s výsledkami vyberte možnosť **Vytvoriť segment**. Ďalšie informácie o stránke s výsledkami nájdete v článku o modeli.

   :::image type="content" source="media/prediction-create-segment.png" alt-text="Snímka obrazovky predikcia stránky s výsledkami so zvýraznením akcie Vytvoriť segment.":::

1. Vytvorte nový segment pomocou atribútov z výstupnej entity vybraného modelu. Ďalšie informácie nájdete v téme [Tvorba a správa segmentov](segments.md).

> [!TIP]
> Môžete tiež vytvoriť segment pre model predikcia z **Segmenty** stránku výberom **Nový** a výberom **Vytvoriť z** > **Inteligencia**. Ďalšie informácie nájdete v časti [Vytvorte nový segment s rýchlymi segmentmi](segment-quick.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
