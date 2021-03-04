---
title: Konektor Power Automate | Dokumentácia spoločnosti Microsoft
description: Vytvárajte toky v Microsoft Power Automate z Dynamics 365 Customer Insights.
ms.date: 01/20/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
ms.reviewer: philk
manager: shellyha
ms.openlocfilehash: fb1df4e9ab1f78300b8ec1f8dfdfbfbac0e71447
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268843"
---
# <a name="power-automate-connector-preview"></a><span data-ttu-id="3c68f-103">Konektor Power Automate (ukážka)</span><span class="sxs-lookup"><span data-stu-id="3c68f-103">Power Automate connector (preview)</span></span>

<span data-ttu-id="3c68f-104">[Power Automate](https://flow.microsoft.com/) umožňuje automatické spúšťanie vybratých udalostí pri zmene údajov a priame spravovanie komplexnejších postupov.</span><span class="sxs-lookup"><span data-stu-id="3c68f-104">Trigger specific events to occur automatically when your data changes and manage more complex flows directly in [Power Automate](https://flow.microsoft.com/).</span></span>

## <a name="power-automate-triggers"></a><span data-ttu-id="3c68f-105">Spúšťače Power Automate</span><span class="sxs-lookup"><span data-stu-id="3c68f-105">Power Automate triggers</span></span>

<span data-ttu-id="3c68f-106">Pomocou spúšťačov môžete vytvárať postupy v cloude a automatizovať opakujúce sa úlohy, napríklad oznámenia alebo pokročilejšie akcie.</span><span class="sxs-lookup"><span data-stu-id="3c68f-106">Use triggers to create cloud flows and automate repetitive tasks, such as notifications or more advanced actions.</span></span> 

- <span data-ttu-id="3c68f-107">Spúšťač pri zlyhaní obnovenia zdroja údajov.</span><span class="sxs-lookup"><span data-stu-id="3c68f-107">Trigger when a data source refresh fails.</span></span> 
- <span data-ttu-id="3c68f-108">Spúšťač pri úspešnom obnovení zdroja údajov.</span><span class="sxs-lookup"><span data-stu-id="3c68f-108">Trigger when a data source refresh succeeds.</span></span>
- <span data-ttu-id="3c68f-109">Spúšťač pri prekročení prahu v segmente.</span><span class="sxs-lookup"><span data-stu-id="3c68f-109">Trigger when a threshold is crossed on a segment.</span></span> <span data-ttu-id="3c68f-110">Spúšťač je obmedzený na prekročenie prahu.</span><span class="sxs-lookup"><span data-stu-id="3c68f-110">The trigger is limited to crossing above the threshold.</span></span>
- <span data-ttu-id="3c68f-111">Spúšťač pri prekročení prahu vo firemnej miere.</span><span class="sxs-lookup"><span data-stu-id="3c68f-111">Trigger when a threshold is crossed on a business measure.</span></span> <span data-ttu-id="3c68f-112">Spúšťač je obmedzený na prekročenie prahu.</span><span class="sxs-lookup"><span data-stu-id="3c68f-112">The trigger is limited crossing above the threshold.</span></span>
- <span data-ttu-id="3c68f-113">Spustí sa, keď sa dokončí úplné obnovenie (zdrojov údajov, segmentov, mier, ...).</span><span class="sxs-lookup"><span data-stu-id="3c68f-113">Trigger when a full refresh of (data sources, segments, measures,...) is completed.</span></span>
- <span data-ttu-id="3c68f-114">Spustí sa, keď sa dokončí aktualizácia procesu zjednotenia (priradenie, párovanie, zlúčenie).</span><span class="sxs-lookup"><span data-stu-id="3c68f-114">Trigger when a refresh of the unification process (map, match, merge) is completed.</span></span>

<span data-ttu-id="3c68f-115">[Nakonfigurujte svoje spúšťače v Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).</span><span class="sxs-lookup"><span data-stu-id="3c68f-115">[Configure your triggers in Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).</span></span>

## <a name="power-automate-actions"></a><span data-ttu-id="3c68f-116">Akcie Power Automate</span><span class="sxs-lookup"><span data-stu-id="3c68f-116">Power Automate actions</span></span>
<span data-ttu-id="3c68f-117">Konektor Power Automate poskytuje iné akcie ako dostupné spúšťače.</span><span class="sxs-lookup"><span data-stu-id="3c68f-117">The Power Automate connector provides other actions than the available triggers.</span></span> <span data-ttu-id="3c68f-118">Viac informácií nájdete v dokumente [Dynamics 365 Customer Insights Connector](https://docs.microsoft.com/connectors/customerinsights/).</span><span class="sxs-lookup"><span data-stu-id="3c68f-118">For more information, see the [Dynamics 365 Customer Insights Connector](https://docs.microsoft.com/connectors/customerinsights/).</span></span>

## <a name="create-a-power-automate-flow"></a><span data-ttu-id="3c68f-119">Vytvorte postup Power Automate</span><span class="sxs-lookup"><span data-stu-id="3c68f-119">Create a Power Automate flow</span></span>

1. <span data-ttu-id="3c68f-120">V prehľadoch cieľových skupín prejdite na **Správca** > **Ciele exportu**.</span><span class="sxs-lookup"><span data-stu-id="3c68f-120">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="3c68f-121">Na dlaždici **Power Automate** vyberte **Nastaviť**.</span><span class="sxs-lookup"><span data-stu-id="3c68f-121">On the **Power Automate** tile, select **Set up**.</span></span>

1. <span data-ttu-id="3c68f-122">Otvorí sa konektor Customer Insights (verzia Preview) v Power Automate.</span><span class="sxs-lookup"><span data-stu-id="3c68f-122">The Customer Insights Connector (preview) in Power Automate opens.</span></span> <span data-ttu-id="3c68f-123">**Prihláste sa** do Power Automate.</span><span class="sxs-lookup"><span data-stu-id="3c68f-123">**Sign in** to Power Automate.</span></span>

1. <span data-ttu-id="3c68f-124">Vyberte si jeden z dostupných spúšťačov a do nového postupu pridajte ďalšie kroky.</span><span class="sxs-lookup"><span data-stu-id="3c68f-124">Choose one of the available triggers and add more steps to your new flow.</span></span> <span data-ttu-id="3c68f-125">Viac informácií nájdete v časti [Vytvorenie postupu v cloude v Power Automate](https://docs.microsoft.com/power-automate/get-started-logic-flow).</span><span class="sxs-lookup"><span data-stu-id="3c68f-125">For more information, see [Create a cloud flow in Power Automate](https://docs.microsoft.com/power-automate/get-started-logic-flow).</span></span>

<span data-ttu-id="3c68f-126">Príklady použitia postupov:</span><span class="sxs-lookup"><span data-stu-id="3c68f-126">Examples how to use flows:</span></span> 
- <span data-ttu-id="3c68f-127">Pošlite správu do kanála Microsoft Teams, ak zlyhá obnovenie zdroja údajov.</span><span class="sxs-lookup"><span data-stu-id="3c68f-127">Post a message to a Microsoft Teams channel if a data source refresh fails.</span></span> 
- <span data-ttu-id="3c68f-128">Po prekročení prahovej hodnoty v segmente pošlite e-mail vlastníkom údajov.</span><span class="sxs-lookup"><span data-stu-id="3c68f-128">Send an email to the data owners when a threshold on a segment is crossed.</span></span>



[!INCLUDE[footer-include](../includes/footer-banner.md)]