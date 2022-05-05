---
title: Segmenty založené na výstupe predikcie
description: Vytvorte segmenty na základe výstupnej entity modelu predikcia.
ms.date: 03/24/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: b0b3357cdf3c049bd92f6c3f690f27433df9117b
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 04/27/2022
ms.locfileid: "8643758"
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