---
title: Prehľad podporovaných scenárov predikcie
description: Scenáre predikcie a možnosti, ktoré pokrýva aplikácia Dynamics 365 Customer Insights.
ms.date: 05/18/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: get-started
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 69ae945b22819521db217508c6fc232876346747
ms.sourcegitcommit: 6b07c9c3102761be162e4842f3c9fbc19f948a9b
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 05/25/2021
ms.locfileid: "6095749"
---
# <a name="predictions-overview"></a><span data-ttu-id="b431e-103">Prehľad predikcií</span><span class="sxs-lookup"><span data-stu-id="b431e-103">Predictions overview</span></span>

<span data-ttu-id="b431e-104">Dynamics 365 Customer Insights prichádza s rôznymi možnosťami, ktoré využívajú AI a strojové učenie na predikciu údajov.</span><span class="sxs-lookup"><span data-stu-id="b431e-104">Dynamics 365 Customer Insights comes with a variety of options that leverage AI and machine learning to predict data.</span></span> 

## <a name="out-of-box-models"></a><span data-ttu-id="b431e-105">Pripravené modely</span><span class="sxs-lookup"><span data-stu-id="b431e-105">Out-of-box models</span></span>

<span data-ttu-id="b431e-106">Najjednoduchší spôsob, ako začať s predikovaním údajov, sú preddefinované modely, ktoré sa často označujú ako vopred pripravené modely.</span><span class="sxs-lookup"><span data-stu-id="b431e-106">The easiest way to start with predicting data are predefined models, often referred to as out-of-box models.</span></span> <span data-ttu-id="b431e-107">Vyžadujú iba určité údaje a štruktúru na rýchle získanie štatistík.</span><span class="sxs-lookup"><span data-stu-id="b431e-107">They only require certain data and structure to generate insights quickly.</span></span> <span data-ttu-id="b431e-108">V súčasnosti sú k dispozícii nasledujúce modely:</span><span class="sxs-lookup"><span data-stu-id="b431e-108">Currently, the following models are available:</span></span> 
- <span data-ttu-id="b431e-109">[Hodnota životnosti zákazníka](predict-customer-lifetime-value.md): Predikuje potenciálne príjmy zákazníka počas celej interakcie s podnikom.</span><span class="sxs-lookup"><span data-stu-id="b431e-109">[Customer lifetime value](predict-customer-lifetime-value.md): Predicts the potential revenue of a customer throughout the entire interaction with a business.</span></span> 
- <span data-ttu-id="b431e-110">[Odporúčanie produktu](predict-product-recommendation.md): Navrhuje množiny prediktívnych odporúčaní produktov na základe nákupného správania a zákazníkov s podobnými nákupnými vzormi.</span><span class="sxs-lookup"><span data-stu-id="b431e-110">[Product recommendation](predict-product-recommendation.md): Suggests sets of predictive product recommendations based on purchase behavior and customers with similar purchase patterns.</span></span>
- <span data-ttu-id="b431e-111">[Odchod predplatiteľov](predict-subscription-churn.md): Predikuje, či hrozí odchod zákazníka, pretože už nebude používať predplatené produkty alebo služby vašej spoločnosti.</span><span class="sxs-lookup"><span data-stu-id="b431e-111">[Subscription churn](predict-subscription-churn.md): Predicts whether a customer is at risk for no longer using your company’s subscription products or services.</span></span>
- <span data-ttu-id="b431e-112">[Odchod transakcií](predict-transactional-churn.md): Predikujte, či si zákazník už v určitom časovom rámci viac nebude kupovať vaše produkty alebo služby.</span><span class="sxs-lookup"><span data-stu-id="b431e-112">[Transactional churn](predict-transactional-churn.md): Predict if a customer will no longer purchase your products or services in a certain time frame.</span></span>

## <a name="azure-machine-learning-integration"></a><span data-ttu-id="b431e-113">Integrácia strojového učenia platformy Azure</span><span class="sxs-lookup"><span data-stu-id="b431e-113">Azure Machine Learning integration</span></span>

<span data-ttu-id="b431e-114">Ak organizácia už používa scenáre strojového učenia založené na experimentoch strojového učenia Azure, funkcia vlastných modelov v Customer Insights pomôže tieto body spojiť.</span><span class="sxs-lookup"><span data-stu-id="b431e-114">If an organization already uses machine learning scenarios based on Azure Machine Learning experiments, the custom models feature in Customer Insights helps to connect the dots.</span></span> <span data-ttu-id="b431e-115">Vytvorte pracovné postupy, ktoré vám pomôžu vybrať údaje, z ktorých chcete generovať štatistiky, a výsledky namapovať do svojich zjednotených profilov zákazníkov.</span><span class="sxs-lookup"><span data-stu-id="b431e-115">Create workflows that help you choose the data you want to generate insights from and map the results to your unified customer profiles.</span></span> <span data-ttu-id="b431e-116">Viac informácií nájdete v časti [Vlastné modely strojového učenia](custom-models.md).</span><span class="sxs-lookup"><span data-stu-id="b431e-116">For more information, see [Custom machine learning models](custom-models.md).</span></span>

## <a name="ai-builder-prediction"></a><span data-ttu-id="b431e-117">Predikcia nástroja AI Builder</span><span class="sxs-lookup"><span data-stu-id="b431e-117">AI Builder prediction</span></span>

<span data-ttu-id="b431e-118">Množiny údajov niekedy nie sú úplné a niektoré hodnoty chýbajú.</span><span class="sxs-lookup"><span data-stu-id="b431e-118">Sometimes, data sets are incomplete and some values are missing.</span></span> <span data-ttu-id="b431e-119">Customer Insights môže pomôcť predikovať chýbajúce hodnoty pre entitu a segmenty zákazníka.</span><span class="sxs-lookup"><span data-stu-id="b431e-119">Customer Insights can help to predict missing values for the Customer entity and segments.</span></span> <span data-ttu-id="b431e-120">Viac informácií nájdete v časti [Doplňte svoje čiastkové údaje o predikcie](predictions.md).</span><span class="sxs-lookup"><span data-stu-id="b431e-120">For more information, see [Complete your partial data with predictions](predictions.md).</span></span>
