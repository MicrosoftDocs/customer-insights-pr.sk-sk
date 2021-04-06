---
title: Konektor Power Automate | Dokumentácia spoločnosti Microsoft
description: Vytvorenie postupov v Microsoft Power Automate z Dynamics 365 Customer Insights.
ms.date: 01/20/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: e973bb11b31c9e70b695ebec8aa2700fdaa5e44f
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597944"
---
# <a name="power-automate-connector-preview"></a><span data-ttu-id="680ca-103">Konektor Power Automate (ukážka)</span><span class="sxs-lookup"><span data-stu-id="680ca-103">Power Automate connector (preview)</span></span>

<span data-ttu-id="680ca-104">[Power Automate](https://flow.microsoft.com/) umožňuje automatické spúšťanie vybratých udalostí pri zmene údajov a priame spravovanie komplexnejších postupov.</span><span class="sxs-lookup"><span data-stu-id="680ca-104">Trigger specific events to occur automatically when your data changes and manage more complex flows directly in [Power Automate](https://flow.microsoft.com/).</span></span>

## <a name="power-automate-triggers"></a><span data-ttu-id="680ca-105">Spúšťače Power Automate</span><span class="sxs-lookup"><span data-stu-id="680ca-105">Power Automate triggers</span></span>

<span data-ttu-id="680ca-106">Pomocou spúšťačov môžete vytvárať postupy v cloude a automatizovať opakujúce sa úlohy, napríklad oznámenia alebo pokročilejšie akcie.</span><span class="sxs-lookup"><span data-stu-id="680ca-106">Use triggers to create cloud flows and automate repetitive tasks, such as notifications or more advanced actions.</span></span> 

- <span data-ttu-id="680ca-107">Spúšťač pri zlyhaní obnovenia zdroja údajov.</span><span class="sxs-lookup"><span data-stu-id="680ca-107">Trigger when a data source refresh fails.</span></span> 
- <span data-ttu-id="680ca-108">Spúšťač pri úspešnom obnovení zdroja údajov.</span><span class="sxs-lookup"><span data-stu-id="680ca-108">Trigger when a data source refresh succeeds.</span></span>
- <span data-ttu-id="680ca-109">Spúšťač pri prekročení prahu v segmente.</span><span class="sxs-lookup"><span data-stu-id="680ca-109">Trigger when a threshold is crossed on a segment.</span></span> <span data-ttu-id="680ca-110">Spúšťač je obmedzený na prekročenie prahu.</span><span class="sxs-lookup"><span data-stu-id="680ca-110">The trigger is limited to crossing above the threshold.</span></span>
- <span data-ttu-id="680ca-111">Spúšťač pri prekročení prahu vo firemnej miere.</span><span class="sxs-lookup"><span data-stu-id="680ca-111">Trigger when a threshold is crossed on a business measure.</span></span> <span data-ttu-id="680ca-112">Spúšťač je obmedzený na prekročenie prahu.</span><span class="sxs-lookup"><span data-stu-id="680ca-112">The trigger is limited crossing above the threshold.</span></span>
- <span data-ttu-id="680ca-113">Spustí sa, keď sa dokončí úplné obnovenie (zdrojov údajov, segmentov, mier, ...).</span><span class="sxs-lookup"><span data-stu-id="680ca-113">Trigger when a full refresh of (data sources, segments, measures,...) is completed.</span></span>
- <span data-ttu-id="680ca-114">Spustí sa, keď sa dokončí aktualizácia procesu zjednotenia (priradenie, párovanie, zlúčenie).</span><span class="sxs-lookup"><span data-stu-id="680ca-114">Trigger when a refresh of the unification process (map, match, merge) is completed.</span></span>

<span data-ttu-id="680ca-115">[Nakonfigurujte svoje spúšťače v Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).</span><span class="sxs-lookup"><span data-stu-id="680ca-115">[Configure your triggers in Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).</span></span>

## <a name="power-automate-actions"></a><span data-ttu-id="680ca-116">Akcie Power Automate</span><span class="sxs-lookup"><span data-stu-id="680ca-116">Power Automate actions</span></span>
<span data-ttu-id="680ca-117">Konektor Power Automate poskytuje iné akcie ako dostupné spúšťače.</span><span class="sxs-lookup"><span data-stu-id="680ca-117">The Power Automate connector provides other actions than the available triggers.</span></span> <span data-ttu-id="680ca-118">Viac informácií nájdete v dokumente [Dynamics 365 Customer Insights Connector](/connectors/customerinsights/).</span><span class="sxs-lookup"><span data-stu-id="680ca-118">For more information, see the [Dynamics 365 Customer Insights Connector](/connectors/customerinsights/).</span></span>

## <a name="create-a-power-automate-flow"></a><span data-ttu-id="680ca-119">Vytvorte postup Power Automate</span><span class="sxs-lookup"><span data-stu-id="680ca-119">Create a Power Automate flow</span></span>

1. <span data-ttu-id="680ca-120">V prehľadoch cieľových skupín prejdite na **Správca** > **Ciele exportu**.</span><span class="sxs-lookup"><span data-stu-id="680ca-120">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="680ca-121">Na dlaždici **Power Automate** vyberte **Nastaviť**.</span><span class="sxs-lookup"><span data-stu-id="680ca-121">On the **Power Automate** tile, select **Set up**.</span></span>

1. <span data-ttu-id="680ca-122">Otvorí sa konektor Customer Insights (verzia Preview) v Power Automate.</span><span class="sxs-lookup"><span data-stu-id="680ca-122">The Customer Insights Connector (preview) in Power Automate opens.</span></span> <span data-ttu-id="680ca-123">**Prihláste sa** do Power Automate.</span><span class="sxs-lookup"><span data-stu-id="680ca-123">**Sign in** to Power Automate.</span></span>

1. <span data-ttu-id="680ca-124">Vyberte si jeden z dostupných spúšťačov a do nového postupu pridajte ďalšie kroky.</span><span class="sxs-lookup"><span data-stu-id="680ca-124">Choose one of the available triggers and add more steps to your new flow.</span></span> <span data-ttu-id="680ca-125">Viac informácií nájdete v časti [Vytvorenie postupu v cloude v Power Automate](/power-automate/get-started-logic-flow).</span><span class="sxs-lookup"><span data-stu-id="680ca-125">For more information, see [Create a cloud flow in Power Automate](/power-automate/get-started-logic-flow).</span></span>

<span data-ttu-id="680ca-126">Príklady použitia postupov:</span><span class="sxs-lookup"><span data-stu-id="680ca-126">Examples how to use flows:</span></span> 
- <span data-ttu-id="680ca-127">Pošlite správu do kanála Microsoft Teams, ak zlyhá obnovenie zdroja údajov.</span><span class="sxs-lookup"><span data-stu-id="680ca-127">Post a message to a Microsoft Teams channel if a data source refresh fails.</span></span> 
- <span data-ttu-id="680ca-128">Po prekročení prahovej hodnoty v segmente pošlite e-mail vlastníkom údajov.</span><span class="sxs-lookup"><span data-stu-id="680ca-128">Send an email to the data owners when a threshold on a segment is crossed.</span></span>



[!INCLUDE[footer-include](../includes/footer-banner.md)]