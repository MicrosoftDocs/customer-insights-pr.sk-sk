---
title: Prehľad podporovaných scenárov predikcie
description: Scenáre predikcie a možnosti, ktoré pokrýva aplikácia Dynamics 365 Customer Insights.
ms.date: 09/06/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: get-started
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: be452e4f1515f637f6edbc3ae3aaf6a3d3471489
ms.sourcegitcommit: 23c8973a726b15050e368cc6e0aab78b266a89f6
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 10/08/2021
ms.locfileid: "7618862"
---
# <a name="predictions-overview"></a>Prehľad predikcií

Dynamics 365 Customer Insights prichádza s rôznymi možnosťami, ktoré využívajú AI a strojové učenie na predikciu údajov. 

## <a name="out-of-box-models"></a>Pripravené modely

Najjednoduchší spôsob, ako začať s predikovaním údajov, sú preddefinované modely, ktoré sa často označujú ako vopred pripravené modely. Vyžadujú iba určité údaje a štruktúru na rýchle získanie štatistík. V súčasnosti sú k dispozícii nasledujúce modely: 

# <a name="individual-customers-b2c"></a>[Individuálni zákazníci (B2C)](#tab/b2c)

- [Hodnota životnosti zákazníka](predict-customer-lifetime-value.md): Predikuje potenciálne príjmy zákazníka počas celej interakcie s podnikom.
- [Odporúčanie produktu](predict-product-recommendation.md): Navrhuje množiny prediktívnych odporúčaní produktov na základe nákupného správania a zákazníkov s podobnými nákupnými vzormi.
- [Odchod predplatiteľov](predict-subscription-churn.md): Predikuje, či hrozí odchod zákazníka, pretože už nebude používať predplatené produkty alebo služby vašej spoločnosti.
- [Odchod transakcií](predict-transactional-churn.md): Predikujte, či si zákazník už v určitom časovom rámci viac nebude kupovať vaše produkty alebo služby.

# <a name="business-accounts-b2b"></a>[Firemné obchodné vzťahy (B2B)](#tab/b2b)

- [Odchod transakcií](predict-transactional-churn.md): Predikujte, či si zákazník už v určitom časovom rámci viac nebude kupovať vaše produkty alebo služby.

---


## <a name="azure-machine-learning-integration"></a>Integrácia strojového učenia platformy Azure

Ak organizácia už používa scenáre strojového učenia založené na experimentoch strojového učenia Azure, funkcia vlastných modelov v Customer Insights pomôže tieto body spojiť. Vytvorte pracovné postupy, ktoré vám pomôžu vybrať údaje, z ktorých chcete generovať štatistiky, a výsledky namapovať do svojich zjednotených profilov zákazníkov. Viac informácií nájdete v časti [Vlastné modely strojového učenia](custom-models.md).

## <a name="ai-builder-prediction"></a>Predikcia nástroja AI Builder

Množiny údajov niekedy nie sú úplné a niektoré hodnoty chýbajú. Customer Insights môže pomôcť predikovať chýbajúce hodnoty pre entitu a segmenty zákazníka. Viac informácií nájdete v časti [Doplňte svoje čiastkové údaje o predikcie](predictions.md).
