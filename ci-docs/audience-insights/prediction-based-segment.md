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
# <a name="create-a-segment-based-on-a-prediction-model-preview"></a><span data-ttu-id="24305-103">Vytvorte segment na základe modelu predikcie (verzie Preview)</span><span class="sxs-lookup"><span data-stu-id="24305-103">Create a segment based on a prediction model (preview)</span></span>

<span data-ttu-id="24305-104">Výsledky predpovedí sa niekedy vzťahujú iba na podmnožinu vašich zákazníkov.</span><span class="sxs-lookup"><span data-stu-id="24305-104">The results of predictions sometimes only apply to a subset of your customers.</span></span> <span data-ttu-id="24305-105">Zvýšte prispôsobenie odporúčaní vytvorením segmentov z výsledkov modelov predikcie.</span><span class="sxs-lookup"><span data-stu-id="24305-105">Increase the personalization of recommendations by creating segments from results of prediction models.</span></span> <span data-ttu-id="24305-106">Môžete napríklad chcieť dať konkrétne odporúčania zákazníkom, ktorí uprednostňujú určitý typ služby.</span><span class="sxs-lookup"><span data-stu-id="24305-106">For example, you may want to give specific recommendations to customers that prefer a certain type of service.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="24305-107">Predpoklady</span><span class="sxs-lookup"><span data-stu-id="24305-107">Prerequisites</span></span>

- <span data-ttu-id="24305-108">Minimálne [povolenia prispievateľa](permissions.md) v Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="24305-108">At least [Contributor permissions](permissions.md) in Customer Insights.</span></span>

- <span data-ttu-id="24305-109">Odporúčanie produktu, zmena transakcie, zmena predplatného alebo model životnej hodnoty zákazníka nakonfigurovaný v nástroji Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="24305-109">A product recommendation, transactional churn, subscription churn, or customer lifetime value model configured in Customer Insights.</span></span> <span data-ttu-id="24305-110">Skontrolujte požiadavky na nastavenie rôznych modelov:</span><span class="sxs-lookup"><span data-stu-id="24305-110">Review the requirements to set up the different models:</span></span>

  - [<span data-ttu-id="24305-111">Model odporúčaní produktov</span><span class="sxs-lookup"><span data-stu-id="24305-111">Product recommendation model</span></span>](predict-product-recommendation.md)
  - [<span data-ttu-id="24305-112">Model odchodu predplatiteľov</span><span class="sxs-lookup"><span data-stu-id="24305-112">Subscription churn model</span></span>](predict-subscription-churn.md)
  - [<span data-ttu-id="24305-113">Transakčný model churn</span><span class="sxs-lookup"><span data-stu-id="24305-113">Transactional churn model</span></span>](predict-transactional-churn.md)
  - [<span data-ttu-id="24305-114">Model celoživotnej hodnoty zákazníka</span><span class="sxs-lookup"><span data-stu-id="24305-114">Customer lifetime value model</span></span>](predict-customer-lifetime-value.md)

## <a name="create-a-customer-segment-based-on-predictions"></a><span data-ttu-id="24305-115">Vytvorte segment zákazníka na základe predikcií</span><span class="sxs-lookup"><span data-stu-id="24305-115">Create a customer segment based on predictions</span></span>

1. <span data-ttu-id="24305-116">Prejdite do ponuky **Analýza** > **Predikcie** a vyberte kartu **Moje predikcie**.</span><span class="sxs-lookup"><span data-stu-id="24305-116">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="24305-117">Vyberte zvislé elipsy vedľa modelu, ktorý chcete skontrolovať, a stlačte **Zobraziť**.</span><span class="sxs-lookup"><span data-stu-id="24305-117">Select the vertical ellipses next to the model you want to review and select **View**.</span></span>

1. <span data-ttu-id="24305-118">Na stránke s výsledkami vyberte možnosť **Vytvoriť segment**.</span><span class="sxs-lookup"><span data-stu-id="24305-118">On the results page, select **Create segment**.</span></span> <span data-ttu-id="24305-119">Ďalšie informácie o stránke s výsledkami nájdete v článku o modeli.</span><span class="sxs-lookup"><span data-stu-id="24305-119">For more information about the results page, review the article about the model.</span></span>

   :::image type="content" source="media/prediction-create-segment.png" alt-text="Snímka obrazovky predikcia stránky s výsledkami so zvýraznením akcie Vytvoriť segment.":::

1. <span data-ttu-id="24305-121">Vytvorte nový segment na základe entity výstupu vybratého modelu.</span><span class="sxs-lookup"><span data-stu-id="24305-121">Create a new segment based on the output entity of the selected model.</span></span> <span data-ttu-id="24305-122">Ďalšie informácie nájdete v téme [Tvorba a správa segmentov](segments.md).</span><span class="sxs-lookup"><span data-stu-id="24305-122">For more information, see [Create and manage segments](segments.md).</span></span>