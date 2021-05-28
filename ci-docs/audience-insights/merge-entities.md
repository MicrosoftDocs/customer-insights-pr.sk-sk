---
title: Zlučovanie entít pri zjednotení údajov
description: Zlučujte entity na účely vytvorenia jednotných profilov zákazníkov.
ms.date: 05/10/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 2cab702509596dd87c0c9b9769d1af8ba8387f9d
ms.sourcegitcommit: fcc94f55dc2dce84eae188d582801dc47696c9cc
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 05/20/2021
ms.locfileid: "6085595"
---
# <a name="merge-entities"></a><span data-ttu-id="adcf1-103">Zlúčenie entít</span><span class="sxs-lookup"><span data-stu-id="adcf1-103">Merge entities</span></span>

<span data-ttu-id="adcf1-104">Fáza zlúčenia je posledná fáza v procese zjednocovania údajov.</span><span class="sxs-lookup"><span data-stu-id="adcf1-104">The merge phase is the last phase in the data unification process.</span></span> <span data-ttu-id="adcf1-105">Jeho účelom je zosúladenie protichodných údajov.</span><span class="sxs-lookup"><span data-stu-id="adcf1-105">Its purpose is reconciling conflicting data.</span></span> <span data-ttu-id="adcf1-106">Medzi príklady konfliktných údajov môže patriť meno zákazníka, ktoré sa nachádza v dvoch vašich množinách údajov, ale v každom sa zobrazuje trochu inak („Grant Marshall“ verzus „Grant Marshal“), alebo telefónne číslo, ktoré sa líši vo formáte (617-803-091X verzus 617803091X).</span><span class="sxs-lookup"><span data-stu-id="adcf1-106">Examples of conflicting data could include a customer name found in two of your datasets but that shows up a little differently in each ("Grant Marshall" versus "Grant Marshal"), or a phone number that differs in format (617-803-091X versus 617803091X).</span></span> <span data-ttu-id="adcf1-107">Zlúčenie týchto kolidujúcich údajových bodov sa vykonáva na základe atribútov.</span><span class="sxs-lookup"><span data-stu-id="adcf1-107">Merging those conflicting data points is done on an attribute-by-attribute basis.</span></span>

:::image type="content" source="media/merge-fields-page.png" alt-text="Stránka zlúčenia v procese zjednotenia údajov zobrazujúca tabuľku so zlúčenými poľami, ktoré definujú zjednotený profil zákazníka.":::

<span data-ttu-id="adcf1-109">Po dokončení [porovnávacej fázy](match-entities.md) môžete začať fázu zlúčenia výberom dlaždice **Zlúčiť** na stránke **Zjednotiť**.</span><span class="sxs-lookup"><span data-stu-id="adcf1-109">After completing the [match phase](match-entities.md), you start the merge phase by selecting the **Merge** tile on the **Unify** page.</span></span>

## <a name="review-system-recommendations"></a><span data-ttu-id="adcf1-110">Kontrola systémových odporúčaní</span><span class="sxs-lookup"><span data-stu-id="adcf1-110">Review system recommendations</span></span>

<span data-ttu-id="adcf1-111">V časti **Údaje** > **Zjednotiť** > **Zlúčiť** vyberáte a vylučujete atribúty, ktoré sa majú zlúčiť v rámci vašej entity zjednoteného profilu zákazníka.</span><span class="sxs-lookup"><span data-stu-id="adcf1-111">On **Data** > **Unify** > **Merge**, you choose and exclude attributes to merge within your unified customer profile entity.</span></span> <span data-ttu-id="adcf1-112">Zjednotený profil zákazníka je výsledkom procesu zjednotenia údajov.</span><span class="sxs-lookup"><span data-stu-id="adcf1-112">The unified customer profile is the result of the data unification process.</span></span> <span data-ttu-id="adcf1-113">Niektoré atribúty sú zlúčené systémom automaticky.</span><span class="sxs-lookup"><span data-stu-id="adcf1-113">Some attributes are automatically merged by the system.</span></span>

<span data-ttu-id="adcf1-114">Ak chcete zobraziť atribúty, ktoré sú obsiahnuté v jednom z vašich automaticky zlúčených atribútov, vyberte tento zlúčený atribút na karte **Zákaznícke polia** tabuľky.</span><span class="sxs-lookup"><span data-stu-id="adcf1-114">To view the attributes that are included in one of your automatically merged attributes, select that merged attribute in the **Customer fields** tab of the table.</span></span> <span data-ttu-id="adcf1-115">Dva atribúty, ktoré tvoria zlúčený atribút, sa zobrazia v dvoch nových riadkoch pod zlúčeným atribútom.</span><span class="sxs-lookup"><span data-stu-id="adcf1-115">The attributes that compose that merged attribute display in two new rows beneath the merged attribute.</span></span>

## <a name="separate-rename-exclude-and-edit-merged-fields"></a><span data-ttu-id="adcf1-116">Zlúčené polia môžete oddeľovať, premenovávať, vylučovať a upravovať</span><span class="sxs-lookup"><span data-stu-id="adcf1-116">Separate, rename, exclude, and edit merged fields</span></span>

<span data-ttu-id="adcf1-117">Môžete zmeniť spôsob, akým systém spracováva zlúčené atribúty, aby sa vytvoril jednotný profil zákazníka.</span><span class="sxs-lookup"><span data-stu-id="adcf1-117">You can change how the system processes merged attributes to generate the unified customer profile.</span></span> <span data-ttu-id="adcf1-118">Stlačte možnosť **Zobraziť viac** a vyberte, čo chcete zmeniť.</span><span class="sxs-lookup"><span data-stu-id="adcf1-118">Select **Show more** and choose what you want to change.</span></span>

:::image type="content" source="media/manage-merged-attributes.png" alt-text="Možnosti v rozbaľovacej ponuke Zobraziť viac na správu zlúčených atribútov.":::

<span data-ttu-id="adcf1-120">Ďalšie informácie nájdete v nasledovných sekciách.</span><span class="sxs-lookup"><span data-stu-id="adcf1-120">For more information, see the following sections.</span></span>

## <a name="separate-merged-fields"></a><span data-ttu-id="adcf1-121">Oddelenie zlúčených polí</span><span class="sxs-lookup"><span data-stu-id="adcf1-121">Separate merged fields</span></span>

<span data-ttu-id="adcf1-122">Ak chcete oddeliť zlúčené polia, vyhľadajte atribút v tabuľke.</span><span class="sxs-lookup"><span data-stu-id="adcf1-122">To separate merged fields, find the attribute in the table.</span></span> <span data-ttu-id="adcf1-123">Oddelené polia sa zobrazujú ako jednotlivé údajové body v zjednotenom profile zákazníka.</span><span class="sxs-lookup"><span data-stu-id="adcf1-123">Separated fields show as individual data points on the unified customer profile.</span></span> 

1. <span data-ttu-id="adcf1-124">Vybrať zlúčené polia.</span><span class="sxs-lookup"><span data-stu-id="adcf1-124">Select the merged field.</span></span>
  
1. <span data-ttu-id="adcf1-125">Stlačte možnosť **Zobraziť viac** a stlačte možnosť **Oddeliť polia**.</span><span class="sxs-lookup"><span data-stu-id="adcf1-125">Select **Show more** and choose **Separate fields**.</span></span>
 
1. <span data-ttu-id="adcf1-126">Potvrďte oddelenie.</span><span class="sxs-lookup"><span data-stu-id="adcf1-126">Confirm the separation.</span></span>

1. <span data-ttu-id="adcf1-127">Stlačte možnosť **Uložiť** a **Spustiť** na spracovanie zmien.</span><span class="sxs-lookup"><span data-stu-id="adcf1-127">Select **Save** and **Run** to process the changes.</span></span>

## <a name="rename-merged-fields"></a><span data-ttu-id="adcf1-128">Premenovať zlúčené polia</span><span class="sxs-lookup"><span data-stu-id="adcf1-128">Rename merged fields</span></span>

<span data-ttu-id="adcf1-129">Zmeňte zobrazovaný názov zlúčených atribútov.</span><span class="sxs-lookup"><span data-stu-id="adcf1-129">Change the display name of merged attributes.</span></span> <span data-ttu-id="adcf1-130">Názov výstupnej entity nemožno zmeniť.</span><span class="sxs-lookup"><span data-stu-id="adcf1-130">You can't change the name of the output entity.</span></span>

1. <span data-ttu-id="adcf1-131">Vybrať zlúčené polia.</span><span class="sxs-lookup"><span data-stu-id="adcf1-131">Select the merged field.</span></span>
  
1. <span data-ttu-id="adcf1-132">Stlačte možnosť **Zobraziť viac** a stlačte možnosť **Premenovať**.</span><span class="sxs-lookup"><span data-stu-id="adcf1-132">Select **Show more** and choose **Rename**.</span></span>

1. <span data-ttu-id="adcf1-133">Potvrďte zmenený zobrazovaný názov.</span><span class="sxs-lookup"><span data-stu-id="adcf1-133">Confirm the changed display name.</span></span> 

1. <span data-ttu-id="adcf1-134">Stlačte možnosť **Uložiť** a **Spustiť** na spracovanie zmien.</span><span class="sxs-lookup"><span data-stu-id="adcf1-134">Select **Save** and **Run** to process the changes.</span></span>

## <a name="exclude-merged-fields"></a><span data-ttu-id="adcf1-135">Vylúčiť zlúčené polia</span><span class="sxs-lookup"><span data-stu-id="adcf1-135">Exclude merged fields</span></span>

<span data-ttu-id="adcf1-136">Vylúčte atribút z jednotného profilu zákazníka.</span><span class="sxs-lookup"><span data-stu-id="adcf1-136">Exclude an attribute from the unified customer profile.</span></span> <span data-ttu-id="adcf1-137">Ak sa pole používa v iných procesoch, napríklad v segmente, pred vylúčením z profilu zákazníka ho z týchto procesov odstráňte.</span><span class="sxs-lookup"><span data-stu-id="adcf1-137">If the field is used in other processes, for example in a segment, remove it from these processes before excluding it from the customer profile.</span></span> 

1. <span data-ttu-id="adcf1-138">Vybrať zlúčené polia.</span><span class="sxs-lookup"><span data-stu-id="adcf1-138">Select the merged field.</span></span>
  
1. <span data-ttu-id="adcf1-139">Stlačte možnosť **Zobraziť viac** a stlačte možnosť **Vylúčiť**.</span><span class="sxs-lookup"><span data-stu-id="adcf1-139">Select **Show more** and choose **Exclude**.</span></span>

1. <span data-ttu-id="adcf1-140">Potvrďte vylúčenie.</span><span class="sxs-lookup"><span data-stu-id="adcf1-140">Confirm the exclusion.</span></span>

1. <span data-ttu-id="adcf1-141">Stlačte možnosť **Uložiť** a **Spustiť** na spracovanie zmien.</span><span class="sxs-lookup"><span data-stu-id="adcf1-141">Select **Save** and **Run** to process the changes.</span></span> 

<span data-ttu-id="adcf1-142">Na stránke **Zlúčiť** zvoľte možnosť **Vylúčené polia** a zobrazte si zoznam všetkých vylúčených polí.</span><span class="sxs-lookup"><span data-stu-id="adcf1-142">On the **Merge** page, select **Excluded fields** to see the list of all excluded fields.</span></span> <span data-ttu-id="adcf1-143">Táto tabla vám umožňuje pridať vylúčené polia späť.</span><span class="sxs-lookup"><span data-stu-id="adcf1-143">This pane lets you add excluded fields back.</span></span>

## <a name="manually-combine-fields"></a><span data-ttu-id="adcf1-144">Ručne spojené polia</span><span class="sxs-lookup"><span data-stu-id="adcf1-144">Manually combine fields</span></span>

<span data-ttu-id="adcf1-145">Zadajte zlúčený atribút manuálne.</span><span class="sxs-lookup"><span data-stu-id="adcf1-145">Specify a merged attribute manually.</span></span> 

1. <span data-ttu-id="adcf1-146">Na stránke **Zlúčiť** stlačte možnosť **Kombinovať polia**.</span><span class="sxs-lookup"><span data-stu-id="adcf1-146">On the **Merge** page, select **Combine fields**.</span></span>

1. <span data-ttu-id="adcf1-147">Zadajte **Názov** a **Názov výstupného poľa**.</span><span class="sxs-lookup"><span data-stu-id="adcf1-147">Provide a **Name** and an **Output field name**.</span></span>

1. <span data-ttu-id="adcf1-148">Zvoľte si pole na pridanie.</span><span class="sxs-lookup"><span data-stu-id="adcf1-148">Choose a field to add.</span></span> <span data-ttu-id="adcf1-149">Stlačte možnosť **Pridať polia** a skombinujte ďalšie polia.</span><span class="sxs-lookup"><span data-stu-id="adcf1-149">Select **Add fields** to combine more fields.</span></span>

1. <span data-ttu-id="adcf1-150">Potvrďte vylúčenie.</span><span class="sxs-lookup"><span data-stu-id="adcf1-150">Confirm the exclusion.</span></span>

1. <span data-ttu-id="adcf1-151">Stlačte možnosť **Uložiť** a **Spustiť** na spracovanie zmien.</span><span class="sxs-lookup"><span data-stu-id="adcf1-151">Select **Save** and **Run** to process the changes.</span></span> 

## <a name="change-the-order-of-fields"></a><span data-ttu-id="adcf1-152">Zmena poradia polí</span><span class="sxs-lookup"><span data-stu-id="adcf1-152">Change the order of fields</span></span>

<span data-ttu-id="adcf1-153">Niektoré entity obsahujú viac podrobností ako iné.</span><span class="sxs-lookup"><span data-stu-id="adcf1-153">Some entities contain more details than others.</span></span> <span data-ttu-id="adcf1-154">Ak entita obsahuje najnovšie údaje o poli, môžete ju pri zlučovaní hodnôt uprednostniť pred inými entitami.</span><span class="sxs-lookup"><span data-stu-id="adcf1-154">If an entity includes the latest data about a field, you can prioritize it over other entities when merging values.</span></span>

1. <span data-ttu-id="adcf1-155">Vybrať zlúčené polia.</span><span class="sxs-lookup"><span data-stu-id="adcf1-155">Select the merged field.</span></span>
  
1. <span data-ttu-id="adcf1-156">Stlačte možnosť **Zobraziť viac** a stlačte možnosť **Upraviť**.</span><span class="sxs-lookup"><span data-stu-id="adcf1-156">Select **Show more** and choose **Edit**.</span></span>

1. <span data-ttu-id="adcf1-157">Na table **Kombinovať polia** stlačte možnosť **Premiestniť nahor/nadol** a nastavte poradie alebo ich presuňte na požadované miesto.</span><span class="sxs-lookup"><span data-stu-id="adcf1-157">In the **Combine fields** pane, select **Move up/down** to set the order or drag and drop them in the desired position.</span></span>

1. <span data-ttu-id="adcf1-158">Potvrďte zmenu.</span><span class="sxs-lookup"><span data-stu-id="adcf1-158">Confirm the change.</span></span>

1. <span data-ttu-id="adcf1-159">Stlačte možnosť **Uložiť** a **Spustiť** na spracovanie zmien.</span><span class="sxs-lookup"><span data-stu-id="adcf1-159">Select **Save** and **Run** to process the changes.</span></span>

## <a name="run-your-merge"></a><span data-ttu-id="adcf1-160">Spustenie zlúčenia</span><span class="sxs-lookup"><span data-stu-id="adcf1-160">Run your merge</span></span>

<span data-ttu-id="adcf1-161">Či už atribúty zlúčite ručne alebo necháte, aby ich zlúčil systém, môžete zlúčenie kedykoľvek spustiť.</span><span class="sxs-lookup"><span data-stu-id="adcf1-161">Whether you manually merge attributes or let the system merge them, you can always run your merge.</span></span> <span data-ttu-id="adcf1-162">Vyberte **Spustiť** na stránke **Zlúčiť** a začnite s procesom.</span><span class="sxs-lookup"><span data-stu-id="adcf1-162">Select **Run** on the **Merge** page to start the process.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="adcf1-163">![Uloženie a spustenie zlúčenia údajov](media/configure-data-merge-save-run.png "Uloženie a spustenie zlúčenia údajov")</span><span class="sxs-lookup"><span data-stu-id="adcf1-163">![Data merge Save and Run](media/configure-data-merge-save-run.png "Data merge Save and Run")</span></span>

<span data-ttu-id="adcf1-164">Stlačte možnosť **Zlúčiť položky určené len na spustenie** ak chcete iba vidieť výstup odrážajúci sa v jednotnej entite zákazníka.</span><span class="sxs-lookup"><span data-stu-id="adcf1-164">Choose **Run only Merge** if you only want to see the output reflected in the unified customer entity.</span></span> <span data-ttu-id="adcf1-165">Následné procesy sa obnovia ako [definované v rozvrhu obnovy](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="adcf1-165">Downstream processes will be refreshed as [defined in the refresh schedule](system.md#schedule-tab).</span></span>

<span data-ttu-id="adcf1-166">Stlačte možnosť **Spustiť procesy zlučovania a tie, ktoré prebiehajú zo servera ku klientovi**, aby ste obnovili systém svojimi zmenami.</span><span class="sxs-lookup"><span data-stu-id="adcf1-166">Choose **Run Merge and downstream processes** to refresh the system with your changes.</span></span> <span data-ttu-id="adcf1-167">Všetky procesy vrátane obohatenia, segmentov a opatrení sa znova spustia automaticky.</span><span class="sxs-lookup"><span data-stu-id="adcf1-167">All processes, including enrichment, segments, and measures will rerun automatically.</span></span> <span data-ttu-id="adcf1-168">Po dokončení všetkých následných procesov budú profily zákazníkov odrážať všetky vykonané zmeny.</span><span class="sxs-lookup"><span data-stu-id="adcf1-168">After all downstream processes have completed, the customer profiles reflect any changes you made.</span></span>

<span data-ttu-id="adcf1-169">Ak chcete vykonať ďalšie zmeny a znova krok zopakovať, môžete zrušiť prebiehajúce zlúčenie.</span><span class="sxs-lookup"><span data-stu-id="adcf1-169">To make more changes and rerun the step, you can cancel an in-progress merge.</span></span> <span data-ttu-id="adcf1-170">Vyberte **Obnovuje sa…** a vyberte **Zrušiť úlohu** na zobrazenej bočnej table.</span><span class="sxs-lookup"><span data-stu-id="adcf1-170">Select **Refreshing ...** and select **Cancel job**  in the side pane that appears.</span></span>

> [!TIP]
> <span data-ttu-id="adcf1-171">Existuje [šesť druhov stavov](system.md#status-types) pre úlohy/procesy.</span><span class="sxs-lookup"><span data-stu-id="adcf1-171">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="adcf1-172">Okrem toho väčšina procesov [závisí na ďalších nadväzujúcich procesoch](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="adcf1-172">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="adcf1-173">Môžete si vybrať stav procesu a zobraziť podrobnosti o priebehu celej úlohy.</span><span class="sxs-lookup"><span data-stu-id="adcf1-173">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="adcf1-174">Po výbere **Pozrieť detaily** pre jednu z úloh úlohy nájdete ďalšie informácie: čas spracovania, posledný dátum spracovania a všetky chyby a varovania spojené s úlohou.</span><span class="sxs-lookup"><span data-stu-id="adcf1-174">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="adcf1-175">Nasledujúci krok</span><span class="sxs-lookup"><span data-stu-id="adcf1-175">Next Step</span></span>

<span data-ttu-id="adcf1-176">Konfigurujte [Aktivity](activities.md), [Obohatenie](enrichment-hub.md) alebo [Vzťahy](relationships.md) a získajte viac informácií o svojich zákazníkoch.</span><span class="sxs-lookup"><span data-stu-id="adcf1-176">Configure [activities](activities.md), [enrichment](enrichment-hub.md), or [relationships](relationships.md) to gain more insights about your customers.</span></span>

<span data-ttu-id="adcf1-177">Ak ste už nakonfigurovali aktivity, obohatenie alebo segmenty, budú automaticky spracované, aby sa použili najnovšie údaje o zákazníkoch.</span><span class="sxs-lookup"><span data-stu-id="adcf1-177">If you already configured activities, enrichment, or segments, they'll be processed automatically to use the latest customer data.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
