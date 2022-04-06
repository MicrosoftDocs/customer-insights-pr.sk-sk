---
title: Prehľad podporovaných scenárov predikcie
description: Scenáre predikcie a možnosti, ktoré pokrýva aplikácia Dynamics 365 Customer Insights.
ms.date: 03/24/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: overview
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 11b0efeecf8bea893272e67d29b1c6622771110c
ms.sourcegitcommit: a5e4503cf9ce0cea562bab9389748d8ca1451f9d
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 03/25/2022
ms.locfileid: "8487554"
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

> [!TIP]
> Odporúčame vám pravidelne obnovovať predvolené modely s aktualizovanými údajmi, aby ste zaistili, že budú presne informovať o vašom firemnom použití. Údaje sa obnovujú ad-hoc, keď systém prijíma nové alebo aktualizované zdroje údajov. Modely však v tomto prípade len prehodnotia a budú naďalej využívať existujúce tréningové dáta.
> 
> Môžete nakonfigurovať **Aktualizovať plán** nastavením plánu preškolenia modelu v prostredí konfigurácie. Model sa preškolí a prehodnotí podľa tohto rozvrhu, ktorý môžete kedykoľvek zmeniť.


## <a name="azure-machine-learning-integration"></a>Integrácia strojového učenia platformy Azure

Ak organizácia už používa scenáre strojového učenia založené na experimentoch strojového učenia Azure, funkcia vlastných modelov v Customer Insights pomôže tieto body spojiť. Vytvorte pracovné postupy, ktoré vám pomôžu vybrať údaje, z ktorých chcete generovať štatistiky, a výsledky namapovať do svojich zjednotených profilov zákazníkov. Viac informácií nájdete v časti [Vlastné modely strojového učenia](custom-models.md).

## <a name="ai-builder-prediction"></a>AI Builder predikcia

Množiny údajov niekedy nie sú úplné a niektoré hodnoty chýbajú. Customer Insights môže pomôcť predikovať chýbajúce hodnoty pre entitu a segmenty zákazníka. Viac informácií nájdete v časti [Doplňte svoje čiastkové údaje o predikcie](predictions.md).
