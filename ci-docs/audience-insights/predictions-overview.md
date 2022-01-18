---
title: Prehľad podporovaných scenárov predikcie
description: Scenáre predikcie a možnosti, ktoré pokrýva aplikácia Dynamics 365 Customer Insights.
ms.date: 12/21/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: overview
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 5972d5b191ded7db14e2ebe9a4a26570a8ea60ba
ms.sourcegitcommit: bb1ca84bc38e81fb2ff2961c457384b7beb5b5fa
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 01/15/2022
ms.locfileid: "7978032"
---
# <a name="predictions-overview"></a>Prehľad predikcií

Dynamics 365 Customer Insights prichádza s rôznymi možnosťami, ktoré využívajú AI a strojové učenie na predikciu údajov. 

## <a name="out-of-box-models"></a>Pripravené modely

Najjednoduchší spôsob, ako začať s predikovaním údajov, sú preddefinované modely, ktoré sa často označujú ako vopred pripravené modely. Vyžadujú iba určité údaje a štruktúru na rýchle získanie štatistík. V súčasnosti sú k dispozícii nasledujúce modely: 

# <a name="individual-consumers-b-to-c"></a>[Jednotliví spotrebitelia (firma a spotrebiteľ)](#tab/b2c)

- [Hodnota životnosti zákazníka](predict-customer-lifetime-value.md): Predikuje potenciálne príjmy zákazníka počas celej interakcie s podnikom.
- [Odporúčanie produktu](predict-product-recommendation.md): Navrhuje množiny prediktívnych odporúčaní produktov na základe nákupného správania a zákazníkov s podobnými nákupnými vzormi.
- [Odchod predplatiteľov](predict-subscription-churn.md): Predikuje, či hrozí odchod zákazníka, pretože už nebude používať predplatené produkty alebo služby vašej spoločnosti.
- [Odchod transakcií](predict-transactional-churn.md): Predikujte, či si zákazník už v určitom časovom rámci viac nebude kupovať vaše produkty alebo služby.
- [Analýza sentimentu](sentiment-analysis.md) : Analyzujte pocity spätnej väzby od zákazníkov a identifikujte obchodné aspekty, ktoré sa často spomínajú.

# <a name="business-accounts-b-to-b"></a>[Firemné obchodné vzťahy (firma a firma)](#tab/b2b)

- [Odchod transakcií](predict-transactional-churn.md): Predikujte, či si zákazník už v určitom časovom rámci viac nebude kupovať vaše produkty alebo služby.

---


## <a name="azure-machine-learning-integration"></a>Integrácia strojového učenia platformy Azure

Ak organizácia už používa scenáre strojového učenia založené na experimentoch strojového učenia Azure, funkcia vlastných modelov v Customer Insights pomôže tieto body spojiť. Vytvorte pracovné postupy, ktoré vám pomôžu vybrať údaje, z ktorých chcete generovať štatistiky, a výsledky namapovať do svojich zjednotených profilov zákazníkov. Viac informácií nájdete v časti [Vlastné modely strojového učenia](custom-models.md).

## <a name="ai-builder-prediction"></a>AI Builder predikcia

Množiny údajov niekedy nie sú úplné a niektoré hodnoty chýbajú. Customer Insights môže pomôcť predikovať chýbajúce hodnoty pre entitu a segmenty zákazníka. Viac informácií nájdete v časti [Doplňte svoje čiastkové údaje o predikcie](predictions.md).
