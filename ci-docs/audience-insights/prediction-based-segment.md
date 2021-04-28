---
title: Segmenty založené na výstupe predikcie
description: Vytvorte segmenty na základe výstupnej entity modelu predikcia.
ms.date: 03/24/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 488db1af865ce600ec012716327d053bee33aff8
ms.sourcegitcommit: a95c82f46c23f625cb34fceba021ccc70d4b1df6
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 03/30/2021
ms.locfileid: "5741448"
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

1. Vyberte zvislé elipsy vedľa modelu, ktorý chcete skontrolovať, a stlačte **Zobraziť**.

1. Na stránke s výsledkami vyberte možnosť **Vytvoriť segment**. Ďalšie informácie o stránke s výsledkami nájdete v článku o modeli.

   :::image type="content" source="media/prediction-create-segment.png" alt-text="Snímka obrazovky predikcia stránky s výsledkami so zvýraznením akcie Vytvoriť segment.":::

1. Vytvorte nový segment na základe entity výstupu vybratého modelu. Ďalšie informácie nájdete v téme [Tvorba a správa segmentov](segments.md).