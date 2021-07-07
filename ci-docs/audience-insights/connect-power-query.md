---
title: Príjem údajov prostredníctvom konektora Power Query
description: Konektory pre zdroje údajov založené na Power Query.
ms.date: 09/29/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.openlocfilehash: 50c231070ff9930c1ea82971bf4f8541a89d5027
ms.sourcegitcommit: 0b754d194d765afef70d1008db7b347dd1f0ee40
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305910"
---
# <a name="connect-to-a-power-query-data-source"></a><span data-ttu-id="c8dc2-103">Pripojenie k zdroju údajov Power Query</span><span class="sxs-lookup"><span data-stu-id="c8dc2-103">Connect to a Power Query data source</span></span>

<span data-ttu-id="c8dc2-104">Power Query ponúka širokú škálu konektorov na prijímanie údajov.</span><span class="sxs-lookup"><span data-stu-id="c8dc2-104">Power Query offers a broad set of connectors to ingest data.</span></span> <span data-ttu-id="c8dc2-105">Väčšinu z týchto konektorov podporuje Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="c8dc2-105">Most of these connectors are supported by Dynamics 365 Customer Insights.</span></span> <span data-ttu-id="c8dc2-106">Pri pridávaní zdrojov údajov na základe konektorov Power Query sa všeobecne postupuje podľa krokov uvedených v nasledujúcej časti.</span><span class="sxs-lookup"><span data-stu-id="c8dc2-106">Adding data sources based on Power Query connectors generally follows the steps outlined in the next section.</span></span> <span data-ttu-id="c8dc2-107">V závislosti od použitého konektora sú však potrebné rôzne informácie.</span><span class="sxs-lookup"><span data-stu-id="c8dc2-107">However, depending on the connector you use, different information is required.</span></span> <span data-ttu-id="c8dc2-108">Ďalšie informácie nájdete v dokumentácii o jednotlivých konektoroch v časti [Referencia na konektor Power Query](/power-query/connectors/).</span><span class="sxs-lookup"><span data-stu-id="c8dc2-108">For more information, see the documentation about individual connectors in the [Power Query connector reference](/power-query/connectors/).</span></span>

## <a name="create-a-new-data-source"></a><span data-ttu-id="c8dc2-109">Vytvorenie nového zdroja údajov</span><span class="sxs-lookup"><span data-stu-id="c8dc2-109">Create a new data source</span></span>

1. <span data-ttu-id="c8dc2-110">V prehľadoch cieľových skupín prejdite na **Údaje** > **Zdroje údajov**.</span><span class="sxs-lookup"><span data-stu-id="c8dc2-110">In audience insights, go to **Data** > **Data sources**.</span></span>

1. <span data-ttu-id="c8dc2-111">Vyberte položku **Pridať zdroj údajov**.</span><span class="sxs-lookup"><span data-stu-id="c8dc2-111">Select **Add data source**.</span></span>

1. <span data-ttu-id="c8dc2-112">Vyberte metódu **Import údajov** a **Ďalej**.</span><span class="sxs-lookup"><span data-stu-id="c8dc2-112">Choose the **Import data** method and select **Next**.</span></span>

1. <span data-ttu-id="c8dc2-113">Zadajte **Názov** pre zdroj údajov a vyberte **Ďalej** na vytvorenie zdroja údajov.</span><span class="sxs-lookup"><span data-stu-id="c8dc2-113">Provide a **Name** for the data source, and select **Next** to create the data source.</span></span> <span data-ttu-id="c8dc2-114">Pokyny týkajúce sa pomenovania:</span><span class="sxs-lookup"><span data-stu-id="c8dc2-114">Name guidelines:</span></span> 
   - <span data-ttu-id="c8dc2-115">Začnite písmenom.</span><span class="sxs-lookup"><span data-stu-id="c8dc2-115">Start with a letter.</span></span>
   - <span data-ttu-id="c8dc2-116">Používajte iba písmená a číslice.</span><span class="sxs-lookup"><span data-stu-id="c8dc2-116">Use letters and numbers only.</span></span> <span data-ttu-id="c8dc2-117">Nie je povolené zadávanie špeciálnych znakov a medzier.</span><span class="sxs-lookup"><span data-stu-id="c8dc2-117">Special characters and spaces are not allowed.</span></span>
   - <span data-ttu-id="c8dc2-118">Použite 3 až 64 znakov.</span><span class="sxs-lookup"><span data-stu-id="c8dc2-118">Use between 3 and 64 characters.</span></span>

1. <span data-ttu-id="c8dc2-119">Vyberte jeden z [dostupných konektorov](#available-power-query-data-sources).</span><span class="sxs-lookup"><span data-stu-id="c8dc2-119">Choose one of the [available connectors](#available-power-query-data-sources).</span></span> <span data-ttu-id="c8dc2-120">Pre tento príklad vyberieme konektor **Text/CSV**.</span><span class="sxs-lookup"><span data-stu-id="c8dc2-120">For this example, we select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="c8dc2-121">Zadajte požadované údaje v časti **Nastavenia spojenia** pre vybraný konektor a vyberte **Ďalej** na zobrazenie ukážky údajov.</span><span class="sxs-lookup"><span data-stu-id="c8dc2-121">Enter the required details in the **Connection settings** for the selected connector and select **Next** to see a preview of the data.</span></span>

1. <span data-ttu-id="c8dc2-122">Vyberte **Zmena údajov**.</span><span class="sxs-lookup"><span data-stu-id="c8dc2-122">Select **Transform data**.</span></span> <span data-ttu-id="c8dc2-123">V tomto kroku pridáte entity do zdroja údajov.</span><span class="sxs-lookup"><span data-stu-id="c8dc2-123">In this step, you'll add entities to your data source.</span></span> <span data-ttu-id="c8dc2-124">Entity sú súbory údajov.</span><span class="sxs-lookup"><span data-stu-id="c8dc2-124">Entities are datasets.</span></span> <span data-ttu-id="c8dc2-125">Ak máte databázu, ktorá obsahuje viacero množín údajov, každá množina údajov je jej vlastná entita.</span><span class="sxs-lookup"><span data-stu-id="c8dc2-125">If you have a database that includes multiple datasets, each dataset is its own entity.</span></span>

1. <span data-ttu-id="c8dc2-126">Dialógové okno **Power Query – úprava dopytov** umožňuje skontrolovať a spresniť údaje.</span><span class="sxs-lookup"><span data-stu-id="c8dc2-126">The **Power Query - Edit queries** dialog lets you review and refine the data.</span></span> <span data-ttu-id="c8dc2-127">Entity, ktoré systémy identifikovali vo vybratých zdrojoch údajov, sa zobrazia na ľavej table.</span><span class="sxs-lookup"><span data-stu-id="c8dc2-127">The entities that the systems identified in your selected data source appear in the left pane.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c8dc2-128">![Úprava dialógového okna dotazov](media/data-manager-configure-edit-queries.png "Úprava dialógového okna dotazov")</span><span class="sxs-lookup"><span data-stu-id="c8dc2-128">![Edit queries dialog](media/data-manager-configure-edit-queries.png "Edit queries dialog")</span></span>

1. <span data-ttu-id="c8dc2-129">Údaje môžete aj transformovať.</span><span class="sxs-lookup"><span data-stu-id="c8dc2-129">You can also transform your data.</span></span> <span data-ttu-id="c8dc2-130">Vyberte entitu, ktorú chcete upraviť alebo transformovať.</span><span class="sxs-lookup"><span data-stu-id="c8dc2-130">Select an entity to edit or transform.</span></span> <span data-ttu-id="c8dc2-131">Použite možnosti v okne Power Query na použitie transformácií.</span><span class="sxs-lookup"><span data-stu-id="c8dc2-131">Use the options in the Power Query window to apply transformations.</span></span> <span data-ttu-id="c8dc2-132">Každá transformácia bude uvedená v zozname **Použité kroky**.</span><span class="sxs-lookup"><span data-stu-id="c8dc2-132">Each transformation gets listed under **Applied steps**.</span></span> <span data-ttu-id="c8dc2-133">Power Query poskytuje množstvo vopred pripravených možností transformácie.</span><span class="sxs-lookup"><span data-stu-id="c8dc2-133">Power Query provides numerous pre-built transformation options.</span></span> <span data-ttu-id="c8dc2-134">Ďalšie informácie nájdete v téme [Transformácie Power Query](/power-query/power-query-what-is-power-query#transformations).</span><span class="sxs-lookup"><span data-stu-id="c8dc2-134">For more information, see [Power Query Transformations](/power-query/power-query-what-is-power-query#transformations).</span></span>

1. <span data-ttu-id="c8dc2-135">Do zdroja údajov môžete pridať ďalšie entity výberom položky **Získať údaje** v dialógovom okne **Upraviť dotazy**.</span><span class="sxs-lookup"><span data-stu-id="c8dc2-135">You can add additional entities to your data source by selecting **Get data** in the **Edit queries** dialog.</span></span>

   <span data-ttu-id="c8dc2-136">Tieto transformácie sú vysoko odporúčané:</span><span class="sxs-lookup"><span data-stu-id="c8dc2-136">These transformations are highly recommended:</span></span>

   - <span data-ttu-id="c8dc2-137">Ak prijímate údaje zo súboru CSV, prvý riadok často obsahuje hlavičky.</span><span class="sxs-lookup"><span data-stu-id="c8dc2-137">If you're ingesting data from a CSV file, the first row often contains headers.</span></span> <span data-ttu-id="c8dc2-138">Prejdite do časti **Transformovať tabuľku** a vyberte **Ako prvý riadok použiť hlavičky**.</span><span class="sxs-lookup"><span data-stu-id="c8dc2-138">Go to **Transform table** and select **Use headers as first row**.</span></span>
   - <span data-ttu-id="c8dc2-139">Zaistite, aby bol dátový typ nastavený správne.</span><span class="sxs-lookup"><span data-stu-id="c8dc2-139">Ensure the data type is set appropriately.</span></span>

1. <span data-ttu-id="c8dc2-140">Výberom tlačidla **Uložiť** v spodnej časti okna Power Query uložte transformácie.</span><span class="sxs-lookup"><span data-stu-id="c8dc2-140">Select **Save** at the bottom of the Power Query window to save the transformations.</span></span> <span data-ttu-id="c8dc2-141">Po uložení nájdete zdroj údajov v časti **Údaje** > **Zdroje údajov**.</span><span class="sxs-lookup"><span data-stu-id="c8dc2-141">After saving, you'll find your data source on **Data** > **Data sources**.</span></span>

1. <span data-ttu-id="c8dc2-142">Na stránke **Zdroje údajov** si všimnete, že je tu nový zdroj údajov v stave **Obnovuje sa**.</span><span class="sxs-lookup"><span data-stu-id="c8dc2-142">On the **Data sources** page, you'll notice the new data source is in **Refreshing** status.</span></span>

## <a name="available-power-query-data-sources"></a><span data-ttu-id="c8dc2-143">Dostupné zdroje údajov pre Power Query</span><span class="sxs-lookup"><span data-stu-id="c8dc2-143">Available Power Query data sources</span></span>

<span data-ttu-id="c8dc2-144">V časti [Referencia na konektor Power Query](/power-query/connectors/) si môžete pozrieť aktuálny zoznam konektorov, ktoré môžete zvoliť na import údajov do Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="c8dc2-144">See the [Power Query connector reference](/power-query/connectors/) for an up-to-date list of connectors that you can select to import data to Customer Insights.</span></span> 

<span data-ttu-id="c8dc2-145">Konektory so značkou začiarknutia v stĺpci **Customer Insights (toky údajov)** sú k dispozícii na vytvorenie nových zdrojov údajov na základe Power Query.</span><span class="sxs-lookup"><span data-stu-id="c8dc2-145">Connectors with a checkmark in the **Customer Insights (Dataflows)** column are available to create new data sources based on Power Query.</span></span> <span data-ttu-id="c8dc2-146">V dokumentácii konkrétneho konektora sa dozviete viac o jeho požiadavkách, obmedzeniach a ďalších podrobnostiach.</span><span class="sxs-lookup"><span data-stu-id="c8dc2-146">Review the documentation of a specific connector to learn more about its prerequisites, limitations, and other details.</span></span>

## <a name="edit-power-query-data-sources"></a><span data-ttu-id="c8dc2-147">Úprava zdrojov údajov pre Power Query</span><span class="sxs-lookup"><span data-stu-id="c8dc2-147">Edit Power Query data sources</span></span>

> [!NOTE]
> <span data-ttu-id="c8dc2-148">Nemusí byť možné vykonať zmeny zdrojov údajov, ktoré sa momentálne používajú v niektorom z procesov aplikácie (napríklad *segmentácia*, *zosúladenie* alebo *zlúčenie*).</span><span class="sxs-lookup"><span data-stu-id="c8dc2-148">It might not be possible to make changes to data sources that are currently being used in one of the app's processes (*segmentation*, *match*, or *merge*, for example).</span></span> 
>
> <span data-ttu-id="c8dc2-149">Pomocou stránky **Nastavenia** môžete sledovať priebeh každého aktívneho procesu.</span><span class="sxs-lookup"><span data-stu-id="c8dc2-149">Using the **Settings** page, you can track the progress of each of the active processes.</span></span> <span data-ttu-id="c8dc2-150">Po dokončení procesu sa môžete vrátiť na stránku **Zdroje údajov** a vykonať zmeny.</span><span class="sxs-lookup"><span data-stu-id="c8dc2-150">When a process completes, you can return to the **Data Sources** page and make your changes.</span></span>

1. <span data-ttu-id="c8dc2-151">V prehľadoch cieľových skupín prejdite na **Údaje** > **Zdroje údajov**.</span><span class="sxs-lookup"><span data-stu-id="c8dc2-151">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="c8dc2-152">Vyberte zvislé tri bodky vedľa zdroja údajov, ktorý chcete zmeniť, a z rozbaľovacieho zoznamu vyberte položku **Upraviť**.</span><span class="sxs-lookup"><span data-stu-id="c8dc2-152">Select the vertical ellipsis next to the data source you want to change and select **Edit** from the dropdown menu.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c8dc2-153">![Úprava možnosti](media/edit-option-data-sources.png "Úprava možnosti")</span><span class="sxs-lookup"><span data-stu-id="c8dc2-153">![Edit option](media/edit-option-data-sources.png "Edit option")</span></span>

3. <span data-ttu-id="c8dc2-154">Použite svoje zmeny a transformácie v dialógovom okne **Power Query – Upraviť dotazy**, ako je opísané v časti [Vytvorenie nového zdroja údajov](#create-a-new-data-source).</span><span class="sxs-lookup"><span data-stu-id="c8dc2-154">Apply your changes and transformations in the **Power Query - Edit queries** dialog as described in the [Create a new data source](#create-a-new-data-source) section.</span></span>

4. <span data-ttu-id="c8dc2-155">Vyberte **Uložiť** v Power Query po dokončení úprav a uložte zmeny.</span><span class="sxs-lookup"><span data-stu-id="c8dc2-155">Select **Save** in Power Query after completing your edits to save your changes.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]