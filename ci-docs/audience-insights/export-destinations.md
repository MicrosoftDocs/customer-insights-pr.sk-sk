---
title: Ciele exportu
description: Exportujte údaje a spravujte ciele exportu.
ms.date: 07/21/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 9032d99357db86e66588eda544211a5f8eb2f23b
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643882"
---
# <a name="export-destinations-preview"></a><span data-ttu-id="7f7ac-103">Ciele exportu (Preview)</span><span class="sxs-lookup"><span data-stu-id="7f7ac-103">Export destinations (preview)</span></span>

<span data-ttu-id="7f7ac-104">Stránka **Ciele exportu** zobrazuje všetky lokality, ktoré ste nastavili na export údajov.</span><span class="sxs-lookup"><span data-stu-id="7f7ac-104">The **Export destinations** page shows you all locations you've set up to export data to.</span></span> <span data-ttu-id="7f7ac-105">Môžete tiež pridať nové ciele na export.</span><span class="sxs-lookup"><span data-stu-id="7f7ac-105">You can also add new destinations for export.</span></span> <span data-ttu-id="7f7ac-106">Ďalej sa zobrazujú možnosti exportu, ktoré sú v súčasnosti k dispozícii.</span><span class="sxs-lookup"><span data-stu-id="7f7ac-106">Additionally, it shows export currently available options.</span></span> <span data-ttu-id="7f7ac-107">Získajte rýchly prehľad, popis a zistite, čo môžete robiť s každou možnosťou rozšírenia.</span><span class="sxs-lookup"><span data-stu-id="7f7ac-107">Get a quick overview, description, and find out what you can do with each extensibility option.</span></span> <span data-ttu-id="7f7ac-108">Exportujte zjednotené profily, miery a segmenty do podporovaných aplikácií relevantných pre vaše podnikanie.</span><span class="sxs-lookup"><span data-stu-id="7f7ac-108">Export unified profiles, measures, and segments to supported apps relevant for your business.</span></span>

<span data-ttu-id="7f7ac-109">Prejdite do ponuky **Správca** > **Ciele exportu** a nájdite nasledujúce možnosti rozšírenia:</span><span class="sxs-lookup"><span data-stu-id="7f7ac-109">Go to **Admin** > **Export destinations** to find the following extensibility options:</span></span>

- [<span data-ttu-id="7f7ac-110">Doplnok Karta Dynamics 365 Customer</span><span class="sxs-lookup"><span data-stu-id="7f7ac-110">Dynamics 365 Customer Card Add-in</span></span>](customer-card-add-in.md)
- [<span data-ttu-id="7f7ac-111">Konektor správcu reklám Facebook</span><span class="sxs-lookup"><span data-stu-id="7f7ac-111">Facebook Ads Manager connector</span></span>](export-facebook.md)
- [<span data-ttu-id="7f7ac-112">Konektor Power Automate</span><span class="sxs-lookup"><span data-stu-id="7f7ac-112">Power Automate connector</span></span>](export-power-automate.md)
- [<span data-ttu-id="7f7ac-113">Konektor Power Apps</span><span class="sxs-lookup"><span data-stu-id="7f7ac-113">Power Apps connector</span></span>](export-power-apps.md)
- [<span data-ttu-id="7f7ac-114">Konektor Power BI</span><span class="sxs-lookup"><span data-stu-id="7f7ac-114">Power BI connector</span></span>](export-power-bi.md)
- [<span data-ttu-id="7f7ac-115">DotDigital</span><span class="sxs-lookup"><span data-stu-id="7f7ac-115">DotDigital</span></span>](export-dotdigital.md)
- [<span data-ttu-id="7f7ac-116">Dynamics 365 for Sales</span><span class="sxs-lookup"><span data-stu-id="7f7ac-116">Dynamics 365 Sales</span></span>](export-dynamics365-sales.md)
- [<span data-ttu-id="7f7ac-117">Dynamics 365 Marketing</span><span class="sxs-lookup"><span data-stu-id="7f7ac-117">Dynamics 365 Marketing</span></span>](export-dynamics365-marketing.md)
- [<span data-ttu-id="7f7ac-118">Ukladací priestor objektu BLOB platformy Azure</span><span class="sxs-lookup"><span data-stu-id="7f7ac-118">Azure Blob Storage</span></span>](export-azure-blob-storage.md)
- [<span data-ttu-id="7f7ac-119">Konektor LiveRamp&reg;</span><span class="sxs-lookup"><span data-stu-id="7f7ac-119">LiveRamp&reg; connector</span></span>](export-liveramp.md)
- [<span data-ttu-id="7f7ac-120">Bot pre Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="7f7ac-120">Bot for Microsoft Teams</span></span>](export-teams-bot.md)
- [<span data-ttu-id="7f7ac-121">Mailchimp</span><span class="sxs-lookup"><span data-stu-id="7f7ac-121">Mailchimp</span></span>](export-mailchimp.md)
- [<span data-ttu-id="7f7ac-122">Customer Insights API</span><span class="sxs-lookup"><span data-stu-id="7f7ac-122">Customer Insights API</span></span>](apis.md)

## <a name="add-a-new-export-destination"></a><span data-ttu-id="7f7ac-123">Pridanie nového cieľa exportu</span><span class="sxs-lookup"><span data-stu-id="7f7ac-123">Add a new export destination</span></span>

<span data-ttu-id="7f7ac-124">Ak chcete pridať ciele exportu, máte na to [povolenia správcu](permissions.md).</span><span class="sxs-lookup"><span data-stu-id="7f7ac-124">To add export destinations, you have [administrator permissions](permissions.md).</span></span> <span data-ttu-id="7f7ac-125">Ak exportujete do služieb Microsoft, predpokladáme, že obidve služby sú v rovnakej organizácii.</span><span class="sxs-lookup"><span data-stu-id="7f7ac-125">If you export to Microsoft services, we assume both services are in the same organization.</span></span>

1. <span data-ttu-id="7f7ac-126">Prejdite do ponuky **Správca** > **Ciele exportu**.</span><span class="sxs-lookup"><span data-stu-id="7f7ac-126">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="7f7ac-127">Prepnite na kartu **Moje ciele exportu**.</span><span class="sxs-lookup"><span data-stu-id="7f7ac-127">Switch to the **My export destinations** tab.</span></span>

1. <span data-ttu-id="7f7ac-128">Vyberte **Pridať cieľ** a vytvorte si nový cieľ exportu.</span><span class="sxs-lookup"><span data-stu-id="7f7ac-128">Select **Add destination** to create a new export destination.</span></span>

1. <span data-ttu-id="7f7ac-129">V table **Pridať cieľ** zvoľte **Typ** exportu v rozbaľovacej ponuke cieľa exportu.</span><span class="sxs-lookup"><span data-stu-id="7f7ac-129">In the **Add destination** pane, select the **Type** of export destination in the drop-down.</span></span>

1. <span data-ttu-id="7f7ac-130">Zadajte požadované podrobnosti a vyberte položku **Ďalej** na vytvorenie cieľa exportu.</span><span class="sxs-lookup"><span data-stu-id="7f7ac-130">Provide the required details and select **Next** to create the export destination.</span></span>

<span data-ttu-id="7f7ac-131">Môžete tiež vybrať **Nastaviť** na dlaždici na karte **Objavovať**.</span><span class="sxs-lookup"><span data-stu-id="7f7ac-131">You can also select **Set up** on a tile on the **Discover** tab.</span></span>

## <a name="view-export-destinations"></a><span data-ttu-id="7f7ac-132">Zobrazenie cieľov exportu</span><span class="sxs-lookup"><span data-stu-id="7f7ac-132">View Export destinations</span></span>

<span data-ttu-id="7f7ac-133">Po vytvorení cieľov exportu ich nájdete v tabuľke na karte **Moje ciele exportu** Táto tabuľka má tri stĺpce:</span><span class="sxs-lookup"><span data-stu-id="7f7ac-133">After creating export destinations, you'll find them in a table on the **My export destinations** tab. This table has three columns:</span></span>

- <span data-ttu-id="7f7ac-134">**Zobrazovaný názov**: Názov, ktorý ste zadali pri vytváraní cieľa.</span><span class="sxs-lookup"><span data-stu-id="7f7ac-134">**Display name**: The name you entered when creating the destination.</span></span>
- <span data-ttu-id="7f7ac-135">**Typ**: Typ cieľa exportu, ktorý ste nastavili pri vytváraní cieľa.</span><span class="sxs-lookup"><span data-stu-id="7f7ac-135">**Type**: The export destination type you set when creating the destination.</span></span>
- <span data-ttu-id="7f7ac-136">**Vytvorené**: Dátum vytvorenia cieľa.</span><span class="sxs-lookup"><span data-stu-id="7f7ac-136">**Created**: The date you created the destination.</span></span>

## <a name="edit-an-export-destination"></a><span data-ttu-id="7f7ac-137">Úprava cieľa exportu</span><span class="sxs-lookup"><span data-stu-id="7f7ac-137">Edit an export destination</span></span>

1. <span data-ttu-id="7f7ac-138">Vyberte zvislé tri bodky pri cieli exportu, ktorý chcete upraviť.</span><span class="sxs-lookup"><span data-stu-id="7f7ac-138">Select the vertical ellipsis for the Export destination you want to edit.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="7f7ac-139">![Zvislé tri bodky](media/export-destinations-page-ellipsis.png "Zvislé tri bodky")</span><span class="sxs-lookup"><span data-stu-id="7f7ac-139">![Vertical ellipsis](media/export-destinations-page-ellipsis.png "Vertical ellipsis")</span></span>

1. <span data-ttu-id="7f7ac-140">V rozbaľovacej ponuke vyberte položku **Upraviť**.</span><span class="sxs-lookup"><span data-stu-id="7f7ac-140">Select **Edit** from the dropdown menu.</span></span>

1. <span data-ttu-id="7f7ac-141">Zmeňte hodnoty, ktoré si vyžadujú aktualizáciu, a vyberte **Uložiť**.</span><span class="sxs-lookup"><span data-stu-id="7f7ac-141">Change the values that require update and select **Save**.</span></span>

## <a name="export-data-on-demand"></a><span data-ttu-id="7f7ac-142">Export údajov na vyžiadanie</span><span class="sxs-lookup"><span data-stu-id="7f7ac-142">Export data on demand</span></span>

<span data-ttu-id="7f7ac-143">Po nakonfigurovaní konektora pre cieľ exportu sa export spustí pri každej [plánovanej obnove](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="7f7ac-143">After configuring a connector for an export destination, exports will run with every [scheduled refresh](system.md#schedule-tab).</span></span>

<span data-ttu-id="7f7ac-144">Ak chcete exportovať údaje bez čakania na plánovanú obnovu, prejdite na kartu **Moje ciele exportu** v časti **Správca** > **Ciele exportu**.</span><span class="sxs-lookup"><span data-stu-id="7f7ac-144">To export data without waiting for a scheduled refresh, go the **My export destinations** tab on **Admin** > **Export destinations**.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="7f7ac-145">![Zvislé tri bodky](media/export-destinations-page-ellipsis.png "Zvislé tri bodky")</span><span class="sxs-lookup"><span data-stu-id="7f7ac-145">![Vertical ellipsis](media/export-destinations-page-ellipsis.png "Vertical ellipsis")</span></span>

- <span data-ttu-id="7f7ac-146">Vyberte **Exportovať** nad zoznamom na spustenie exportu do všetkých cieľov exportu súčasne.</span><span class="sxs-lookup"><span data-stu-id="7f7ac-146">Select **Export** above the list to run the export to all export destinations simultaneously.</span></span>
- <span data-ttu-id="7f7ac-147">Vyberte tri bodky (…) za položkou zoznamu a potom vyberte možnosť **Exportovať** na spustenie exportu pre jeden cieľ exportu.</span><span class="sxs-lookup"><span data-stu-id="7f7ac-147">Select the ellipsis (...) after a list item and then choose the **Export** option to run the export for a single export destination.</span></span>

## <a name="remove-an-export-destination"></a><span data-ttu-id="7f7ac-148">Odstránenie cieľa exportu</span><span class="sxs-lookup"><span data-stu-id="7f7ac-148">Remove an Export destination</span></span>

<span data-ttu-id="7f7ac-149">Ak chcete odstrániť cieľ exportu, začnite na hlavnej stránke **Ciele exportu**.</span><span class="sxs-lookup"><span data-stu-id="7f7ac-149">To remove an Export destination, start from the main **Export destinations** page.</span></span>

1. <span data-ttu-id="7f7ac-150">Vyberte zvislé tri bodky pri cieli exportu, ktorý chcete odstrániť.</span><span class="sxs-lookup"><span data-stu-id="7f7ac-150">Select the vertical ellipsis for the Export destination you want to remove.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="7f7ac-151">![Zvislé tri bodky](media/export-destinations-page-ellipsis.png "Zvislé tri bodky")</span><span class="sxs-lookup"><span data-stu-id="7f7ac-151">![Vertical ellipsis](media/export-destinations-page-ellipsis.png "Vertical ellipsis")</span></span>

2. <span data-ttu-id="7f7ac-152">Vyberte položku **Odstrániť** z rozbaľovacej ponuky.</span><span class="sxs-lookup"><span data-stu-id="7f7ac-152">Select **Remove** from the dropdown menu.</span></span>

3. <span data-ttu-id="7f7ac-153">Odstránenie potvrďte výberom položky **Odstrániť** na obrazovke s potvrdením.</span><span class="sxs-lookup"><span data-stu-id="7f7ac-153">Confirm the removal by selecting **Remove** on the confirmation screen.</span></span>
