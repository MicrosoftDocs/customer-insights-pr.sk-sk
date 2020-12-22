---
title: Konektor Power Automate | Dokumentácia spoločnosti Microsoft
description: Vytvárajte toky v Microsoft Power Automate z Dynamics 365 Customer Insights.
ms.date: 08/03/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: philk
manager: shellyha
ms.openlocfilehash: ffe92414365b0b777691a4a2d585100e4fbea591
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406890"
---
# <a name="power-automate-connector-preview"></a><span data-ttu-id="ebc06-103">Konektor Power Automate (ukážka)</span><span class="sxs-lookup"><span data-stu-id="ebc06-103">Power Automate connector (preview)</span></span>

<span data-ttu-id="ebc06-104">[Power Automate](https://flow.microsoft.com/) umožňuje automatické spúšťanie vybratých udalostí pri zmene údajov a priame spravovanie komplexnejších postupov.</span><span class="sxs-lookup"><span data-stu-id="ebc06-104">Trigger specific events to occur automatically when your data changes and manage more complex flows directly in [Power Automate](https://flow.microsoft.com/).</span></span>

## <a name="power-automate-triggers"></a><span data-ttu-id="ebc06-105">Spúšťače Power Automate</span><span class="sxs-lookup"><span data-stu-id="ebc06-105">Power Automate triggers</span></span>

<span data-ttu-id="ebc06-106">Môžete použiť rôzne spúšťače, ktoré vám umožňujú vytvárať toky na automatizáciu opakujúcich sa úloh, ako sú upozornenia alebo pokročilejšie akcie.</span><span class="sxs-lookup"><span data-stu-id="ebc06-106">You can use a variety of triggers that allow you to create flows to automate repetitive tasks, such as notifications or more advanced actions.</span></span> 

- <span data-ttu-id="ebc06-107">Spúšťač pri zlyhaní obnovenia zdroja údajov.</span><span class="sxs-lookup"><span data-stu-id="ebc06-107">Trigger when a data source refresh fails.</span></span> 
- <span data-ttu-id="ebc06-108">Spúšťač pri úspešnom obnovení zdroja údajov.</span><span class="sxs-lookup"><span data-stu-id="ebc06-108">Trigger when a data source refresh succeeds.</span></span>
- <span data-ttu-id="ebc06-109">Spúšťač pri prekročení prahu v segmente.</span><span class="sxs-lookup"><span data-stu-id="ebc06-109">Trigger when a threshold is crossed on a segment.</span></span> <span data-ttu-id="ebc06-110">Spúšťač je obmedzený na prekročenie prahu.</span><span class="sxs-lookup"><span data-stu-id="ebc06-110">The trigger is limited to crossing above the threshold.</span></span>
- <span data-ttu-id="ebc06-111">Spúšťač pri prekročení prahu vo firemnej miere.</span><span class="sxs-lookup"><span data-stu-id="ebc06-111">Trigger when a threshold is crossed on a business measure.</span></span> <span data-ttu-id="ebc06-112">Spúšťač je obmedzený na prekročenie prahu.</span><span class="sxs-lookup"><span data-stu-id="ebc06-112">The trigger is limited crossing above the threshold.</span></span>
- <span data-ttu-id="ebc06-113">Spustí sa, keď sa dokončí úplné obnovenie (zdrojov údajov, segmentov, mier, ...).</span><span class="sxs-lookup"><span data-stu-id="ebc06-113">Trigger when a full refresh of (data sources, segments, measures,...) is completed.</span></span>
- <span data-ttu-id="ebc06-114">Spustí sa, keď sa dokončí aktualizácia procesu zjednotenia (priradenie, párovanie, zlúčenie).</span><span class="sxs-lookup"><span data-stu-id="ebc06-114">Trigger when a refresh of the unification process (map, match, merge) is completed.</span></span>

<span data-ttu-id="ebc06-115">[Nakonfigurujte svoje spúšťače v Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).</span><span class="sxs-lookup"><span data-stu-id="ebc06-115">[Configure your triggers in Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).</span></span>

## <a name="power-automate-actions"></a><span data-ttu-id="ebc06-116">Akcie Power Automate</span><span class="sxs-lookup"><span data-stu-id="ebc06-116">Power Automate actions</span></span>
<span data-ttu-id="ebc06-117">Konektor Power Automate poskytuje iné akcie ako dostupné spúšťače.</span><span class="sxs-lookup"><span data-stu-id="ebc06-117">The Power Automate connector provides other actions than the available triggers.</span></span> <span data-ttu-id="ebc06-118">Viac informácií nájdete v dokumente [Dynamics 365 Customer Insights Connector](https://docs.microsoft.com/connectors/customerinsights/).</span><span class="sxs-lookup"><span data-stu-id="ebc06-118">For more information, see the [Dynamics 365 Customer Insights Connector](https://docs.microsoft.com/connectors/customerinsights/).</span></span>

## <a name="create-a-power-automate-flow-in-audience-insights"></a><span data-ttu-id="ebc06-119">Vytvorenie postupu služby Power Automate v prehľadoch cieľových skupín</span><span class="sxs-lookup"><span data-stu-id="ebc06-119">Create a Power Automate flow in audience insights</span></span>

1. <span data-ttu-id="ebc06-120">V prehľadoch cieľových skupín prejdite na **Správca** > **Systém**.</span><span class="sxs-lookup"><span data-stu-id="ebc06-120">In audience insights, go to **Admin** > **System**.</span></span>

1. <span data-ttu-id="ebc06-121">Na stránke **Systém** vyberte kartu **Stav**.</span><span class="sxs-lookup"><span data-stu-id="ebc06-121">On the **System** page, select the **Status** tab.</span></span>

1. <span data-ttu-id="ebc06-122">V sekcii **Zdroje údajov** vyberte **Postupy** a vyberte **Vytvoriť postup** z rozbaľovacieho zoznamu.</span><span class="sxs-lookup"><span data-stu-id="ebc06-122">In the **Data Sources** section, select **Flows** and select **Create a flow** from the dropdown list.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="ebc06-123">![Konektor Power Automate zobrazujúci akciu Vytvorenie toku](media/power-automate-connector-create-flow.png "Konektor Power Automate zobrazujúci akciu Vytvorenie toku")</span><span class="sxs-lookup"><span data-stu-id="ebc06-123">![Power Automate connector showing Create a Flow action](media/power-automate-connector-create-flow.png "Power Automate connector showing Create a Flow action")</span></span>

1. <span data-ttu-id="ebc06-124">V Power Automate vyberte jeden z dostupných spúšťačov a vytvorte požadovaný postup.</span><span class="sxs-lookup"><span data-stu-id="ebc06-124">In Power Automate, select one of the available triggers to create your preferred flow.</span></span> <span data-ttu-id="ebc06-125">Ak vytvárate svoj prvý tok, musíte sa najprv autentifikovať pomocou konektora Power Automate.</span><span class="sxs-lookup"><span data-stu-id="ebc06-125">If you're creating your first flow, you'll need to authenticate with the Power Automate connector first.</span></span>
