---
title: Príjem údajov prostredníctvom konektora Power Query
description: Konektory pre zdroje údajov založené na Power Query.
ms.date: 09/29/2020
ms.reviewer: adkuppa
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 8a170cc5b64b4b383501021232c83948e838a0e2
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406914"
---
# <a name="connect-to-a-power-query-data-source"></a><span data-ttu-id="6d06d-103">Pripojenie k zdroju údajov Power Query</span><span class="sxs-lookup"><span data-stu-id="6d06d-103">Connect to a Power Query data source</span></span>

<span data-ttu-id="6d06d-104">Power Query ponúka širokú škálu konektorov na prijímanie údajov.</span><span class="sxs-lookup"><span data-stu-id="6d06d-104">Power Query offers a broad set of connectors to ingest data.</span></span> <span data-ttu-id="6d06d-105">Väčšinu z týchto konektorov podporuje Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="6d06d-105">Most of these connectors are supported by Dynamics 365 Customer Insights.</span></span> <span data-ttu-id="6d06d-106">Pri pridávaní zdrojov údajov na základe konektorov Power Query sa všeobecne postupuje podľa krokov uvedených v nasledujúcej časti.</span><span class="sxs-lookup"><span data-stu-id="6d06d-106">Adding data sources based on Power Query connectors generally follows the steps outlined in the next section.</span></span> <span data-ttu-id="6d06d-107">V závislosti od použitého konektora sú však potrebné rôzne informácie.</span><span class="sxs-lookup"><span data-stu-id="6d06d-107">However, depending on the connector you use, different information is required.</span></span> <span data-ttu-id="6d06d-108">Ďalšie informácie nájdete v dokumentácii o jednotlivých konektoroch v časti [Referencia na konektor Power Query](https://docs.microsoft.com/power-query/connectors/).</span><span class="sxs-lookup"><span data-stu-id="6d06d-108">For more information, see the documentation about individual connectors in the [Power Query connector reference](https://docs.microsoft.com/power-query/connectors/).</span></span>

## <a name="create-a-new-data-source"></a><span data-ttu-id="6d06d-109">Vytvorenie nového zdroja údajov</span><span class="sxs-lookup"><span data-stu-id="6d06d-109">Create a new data source</span></span>

1. <span data-ttu-id="6d06d-110">V prehľadoch cieľových skupín prejdite na **Údaje** > **Zdroje údajov**.</span><span class="sxs-lookup"><span data-stu-id="6d06d-110">In audience insights, go to **Data** > **Data sources**.</span></span>

1. <span data-ttu-id="6d06d-111">Vyberte položku **Pridať zdroj údajov**.</span><span class="sxs-lookup"><span data-stu-id="6d06d-111">Select **Add data source**.</span></span>

1. <span data-ttu-id="6d06d-112">Vyberte metódu **Import údajov** a **Ďalej**.</span><span class="sxs-lookup"><span data-stu-id="6d06d-112">Choose the **Import data** method and select **Next**.</span></span>

1. <span data-ttu-id="6d06d-113">Zadajte **Názov** pre zdroj údajov a vyberte **Ďalej** na vytvorenie zdroja údajov.</span><span class="sxs-lookup"><span data-stu-id="6d06d-113">Provide a **Name** for the data source, and select **Next** to create the data source.</span></span>

1. <span data-ttu-id="6d06d-114">Vyberte jeden z [dostupných konektorov](#available-power-query-data-sources).</span><span class="sxs-lookup"><span data-stu-id="6d06d-114">Choose one of the [available connectors](#available-power-query-data-sources).</span></span> <span data-ttu-id="6d06d-115">Pre tento príklad vyberieme konektor **Text/CSV**.</span><span class="sxs-lookup"><span data-stu-id="6d06d-115">For this example, we select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="6d06d-116">Zadajte požadované údaje v časti **Nastavenia spojenia** pre vybraný konektor a vyberte **Ďalej** na zobrazenie ukážky údajov.</span><span class="sxs-lookup"><span data-stu-id="6d06d-116">Enter the required details in the **Connection settings** for the selected connector and select **Next** to see a preview of the data.</span></span>

1. <span data-ttu-id="6d06d-117">Vyberte **Zmena údajov**.</span><span class="sxs-lookup"><span data-stu-id="6d06d-117">Select **Transform data**.</span></span> <span data-ttu-id="6d06d-118">V tomto kroku pridáte entity do zdroja údajov.</span><span class="sxs-lookup"><span data-stu-id="6d06d-118">In this step, you'll add entities to your data source.</span></span> <span data-ttu-id="6d06d-119">Entity sú súbory údajov.</span><span class="sxs-lookup"><span data-stu-id="6d06d-119">Entities are datasets.</span></span> <span data-ttu-id="6d06d-120">Ak máte databázu, ktorá obsahuje viacero množín údajov, každá množina údajov je jej vlastná entita.</span><span class="sxs-lookup"><span data-stu-id="6d06d-120">If you have a database that includes multiple datasets, each dataset is its own entity.</span></span>

1. <span data-ttu-id="6d06d-121">Dialógové okno **Power Query – úprava dopytov** umožňuje skontrolovať a spresniť údaje.</span><span class="sxs-lookup"><span data-stu-id="6d06d-121">The **Power Query - Edit queries** dialog lets you review and refine the data.</span></span> <span data-ttu-id="6d06d-122">Entity, ktoré systémy identifikovali vo vybratých zdrojoch údajov, sa zobrazia na ľavej table.</span><span class="sxs-lookup"><span data-stu-id="6d06d-122">The entities that the systems identified in your selected data source appear in the left pane.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="6d06d-123">![Úprava dialógového okna dotazov](media/data-manager-configure-edit-queries.png "Úprava dialógového okna dotazov")</span><span class="sxs-lookup"><span data-stu-id="6d06d-123">![Edit queries dialog](media/data-manager-configure-edit-queries.png "Edit queries dialog")</span></span>

1. <span data-ttu-id="6d06d-124">Údaje môžete aj transformovať.</span><span class="sxs-lookup"><span data-stu-id="6d06d-124">You can also transform your data.</span></span> <span data-ttu-id="6d06d-125">Vyberte entitu, ktorú chcete upraviť alebo transformovať.</span><span class="sxs-lookup"><span data-stu-id="6d06d-125">Select an entity to edit or transform.</span></span> <span data-ttu-id="6d06d-126">Použite možnosti v okne Power Query na použitie transformácií.</span><span class="sxs-lookup"><span data-stu-id="6d06d-126">Use the options in the Power Query window to apply transformations.</span></span> <span data-ttu-id="6d06d-127">Každá transformácia bude uvedená v zozname **Použité kroky**.</span><span class="sxs-lookup"><span data-stu-id="6d06d-127">Each transformation gets listed under **Applied steps**.</span></span> <span data-ttu-id="6d06d-128">Power Query poskytuje množstvo vopred pripravených možností transformácie.</span><span class="sxs-lookup"><span data-stu-id="6d06d-128">Power Query provides numerous pre-built transformation options.</span></span> <span data-ttu-id="6d06d-129">Ďalšie informácie nájdete v téme [Transformácie Power Query](https://docs.microsoft.com/power-query/power-query-what-is-power-query#transformations).</span><span class="sxs-lookup"><span data-stu-id="6d06d-129">For more information, see [Power Query Transformations](https://docs.microsoft.com/power-query/power-query-what-is-power-query#transformations).</span></span>

1. <span data-ttu-id="6d06d-130">Do zdroja údajov môžete pridať ďalšie entity výberom položky **Získať údaje** v dialógovom okne **Upraviť dotazy**.</span><span class="sxs-lookup"><span data-stu-id="6d06d-130">You can add additional entities to your data source by selecting **Get data** in the **Edit queries** dialog.</span></span>

   <span data-ttu-id="6d06d-131">Tieto transformácie sú vysoko odporúčané:</span><span class="sxs-lookup"><span data-stu-id="6d06d-131">These transformations are highly recommended:</span></span>

   - <span data-ttu-id="6d06d-132">Ak prijímate údaje zo súboru CSV, prvý riadok často obsahuje hlavičky.</span><span class="sxs-lookup"><span data-stu-id="6d06d-132">If you're ingesting data from a CSV file, the first row often contains headers.</span></span> <span data-ttu-id="6d06d-133">Prejdite do časti **Transformovať tabuľku** a vyberte **Ako prvý riadok použiť hlavičky**.</span><span class="sxs-lookup"><span data-stu-id="6d06d-133">Go to **Transform table** and select **Use headers as first row**.</span></span>
   - <span data-ttu-id="6d06d-134">Zaistite, aby bol dátový typ nastavený správne.</span><span class="sxs-lookup"><span data-stu-id="6d06d-134">Ensure the data type is set appropriately.</span></span>

1. <span data-ttu-id="6d06d-135">Výberom tlačidla **Uložiť** v spodnej časti okna Power Query uložte transformácie.</span><span class="sxs-lookup"><span data-stu-id="6d06d-135">Select **Save** at the bottom of the Power Query window to save the transformations.</span></span> <span data-ttu-id="6d06d-136">Po uložení nájdete zdroj údajov v časti **Údaje** > **Zdroje údajov**.</span><span class="sxs-lookup"><span data-stu-id="6d06d-136">After saving, you'll find your data source on **Data** > **Data sources**.</span></span>

1. <span data-ttu-id="6d06d-137">Na stránke **Zdroje údajov** si všimnete, že je tu nový zdroj údajov v stave **Obnovuje sa**.</span><span class="sxs-lookup"><span data-stu-id="6d06d-137">On the **Data sources** page, you'll notice the new data source is in **Refreshing** status.</span></span>

## <a name="available-power-query-data-sources"></a><span data-ttu-id="6d06d-138">Dostupné zdroje údajov pre Power Query</span><span class="sxs-lookup"><span data-stu-id="6d06d-138">Available Power Query data sources</span></span>

<span data-ttu-id="6d06d-139">V časti [Referencia na konektor Power Query](https://docs.microsoft.com/power-query/connectors/) si môžete pozrieť aktuálny zoznam konektorov, ktoré môžete zvoliť na import údajov do Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="6d06d-139">See the [Power Query connector reference](https://docs.microsoft.com/power-query/connectors/) for an up-to-date list of connectors that you can select to import data to Customer Insights.</span></span> 

<span data-ttu-id="6d06d-140">Konektory so značkou začiarknutia v stĺpci **Customer Insights (toky údajov)** sú k dispozícii na vytvorenie nových zdrojov údajov na základe Power Query.</span><span class="sxs-lookup"><span data-stu-id="6d06d-140">Connectors with a checkmark in the **Customer Insights (Dataflows)** column are available to create new data sources based on Power Query.</span></span> <span data-ttu-id="6d06d-141">V dokumentácii konkrétneho konektora sa dozviete viac o jeho požiadavkách, obmedzeniach a ďalších podrobnostiach.</span><span class="sxs-lookup"><span data-stu-id="6d06d-141">Review the documentation of a specific connector to learn more about its prerequisites, limitations, and other details.</span></span>

## <a name="edit-power-query-data-sources"></a><span data-ttu-id="6d06d-142">Úprava zdrojov údajov pre Power Query</span><span class="sxs-lookup"><span data-stu-id="6d06d-142">Edit Power Query data sources</span></span>

> [!NOTE]
> <span data-ttu-id="6d06d-143">Nemusí byť možné vykonať zmeny zdrojov údajov, ktoré sa momentálne používajú v niektorom z procesov aplikácie (napríklad *segmentácia*, *zosúladenie* alebo *zlúčenie*).</span><span class="sxs-lookup"><span data-stu-id="6d06d-143">It might not be possible to make changes to data sources that are currently being used in one of the app's processes (*segmentation*, *match*, or *merge*, for example).</span></span> 
>
> <span data-ttu-id="6d06d-144">Pomocou stránky **Nastavenia** môžete sledovať priebeh každého aktívneho procesu.</span><span class="sxs-lookup"><span data-stu-id="6d06d-144">Using the **Settings** page, you can track the progress of each of the active processes.</span></span> <span data-ttu-id="6d06d-145">Po dokončení procesu sa môžete vrátiť na stránku **Zdroje údajov** a vykonať zmeny.</span><span class="sxs-lookup"><span data-stu-id="6d06d-145">When a process completes, you can return to the **Data Sources** page and make your changes.</span></span>

1. <span data-ttu-id="6d06d-146">V prehľadoch cieľových skupín prejdite na **Údaje** > **Zdroje údajov**.</span><span class="sxs-lookup"><span data-stu-id="6d06d-146">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="6d06d-147">Vyberte zvislé tri bodky vedľa zdroja údajov, ktorý chcete zmeniť, a vyberte **Upraviť** z rozbaľovacej ponuky.</span><span class="sxs-lookup"><span data-stu-id="6d06d-147">Select the vertical ellipsis next to the data source you want to change and select **Edit** from the drop-down menu.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="6d06d-148">![Úprava možnosti](media/edit-option-data-sources.png "Úprava možnosti")</span><span class="sxs-lookup"><span data-stu-id="6d06d-148">![Edit option](media/edit-option-data-sources.png "Edit option")</span></span>

3. <span data-ttu-id="6d06d-149">Použite svoje zmeny a transformácie v dialógovom okne **Power Query – Upraviť dotazy**, ako je opísané v časti [Vytvorenie nového zdroja údajov](#create-a-new-data-source).</span><span class="sxs-lookup"><span data-stu-id="6d06d-149">Apply your changes and transformations in the **Power Query - Edit queries** dialog as described in the [Create a new data source](#create-a-new-data-source) section.</span></span>

4. <span data-ttu-id="6d06d-150">Vyberte **Uložiť** v Power Query po dokončení úprav a uložte zmeny.</span><span class="sxs-lookup"><span data-stu-id="6d06d-150">Select **Save** in Power Query after completing your edits to save your changes.</span></span>
