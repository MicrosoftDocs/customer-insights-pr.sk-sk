---
title: Zlučovanie entít pri zjednotení údajov
description: Zlučujte entity na účely vytvorenia jednotných profilov zákazníkov.
ms.date: 04/16/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 4ad06a0baf57e612fc0e0214dfd23d28e7d2b6be
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896530"
---
# <a name="merge-entities"></a><span data-ttu-id="39325-103">Zlúčenie entít</span><span class="sxs-lookup"><span data-stu-id="39325-103">Merge entities</span></span>

<span data-ttu-id="39325-104">Fáza zlúčenia je posledná fáza v procese zjednocovania údajov.</span><span class="sxs-lookup"><span data-stu-id="39325-104">The merge phase is the last phase in the data unification process.</span></span> <span data-ttu-id="39325-105">Jeho účelom je zosúladenie protichodných údajov.</span><span class="sxs-lookup"><span data-stu-id="39325-105">Its purpose is reconciling conflicting data.</span></span> <span data-ttu-id="39325-106">Medzi príklady konfliktných údajov môže patriť meno zákazníka, ktoré sa nachádza v dvoch vašich množinách údajov, ale v každom sa zobrazuje trochu inak („Grant Marshall“ verzus „Grant Marshal“), alebo telefónne číslo, ktoré sa líši vo formáte (617-803-091X verzus 617803091X).</span><span class="sxs-lookup"><span data-stu-id="39325-106">Examples of conflicting data could include a customer name found in two of your datasets but that shows up a little differently in each ("Grant Marshall" versus "Grant Marshal"), or a phone number that differs in format (617-803-091X versus 617803091X).</span></span> <span data-ttu-id="39325-107">Zlúčenie týchto kolidujúcich údajových bodov sa vykonáva na základe atribútov.</span><span class="sxs-lookup"><span data-stu-id="39325-107">Merging those conflicting data points is done on an attribute-by-attribute basis.</span></span>

<span data-ttu-id="39325-108">Po dokončení [porovnávacej fázy](match-entities.md) môžete začať fázu zlúčenia výberom dlaždice **Zlúčiť** na stránke **Zjednotiť**.</span><span class="sxs-lookup"><span data-stu-id="39325-108">After completing the [match phase](match-entities.md), you start the merge phase by selecting the **Merge** tile on the **Unify** page.</span></span>

## <a name="review-system-recommendations"></a><span data-ttu-id="39325-109">Kontrola systémových odporúčaní</span><span class="sxs-lookup"><span data-stu-id="39325-109">Review system recommendations</span></span>

<span data-ttu-id="39325-110">Na stránke **Zlúčiť** môžete vybrať a vylúčiť atribúty, ktoré sa majú zlúčiť v rámci jednotnej entity profilu zákazníka (výsledok procesu konfigurácie).</span><span class="sxs-lookup"><span data-stu-id="39325-110">On the **Merge** page, you choose and exclude attributes to merge within your unified customer profile entity (the result of the configuration process).</span></span> <span data-ttu-id="39325-111">Niektoré atribúty sú zlúčené systémom automaticky.</span><span class="sxs-lookup"><span data-stu-id="39325-111">Some attributes are automatically merged by the system.</span></span>

### <a name="view-merged-attributes"></a><span data-ttu-id="39325-112">Zobrazenie zlúčených atribútov</span><span class="sxs-lookup"><span data-stu-id="39325-112">View merged attributes</span></span>

<span data-ttu-id="39325-113">Ak chcete zobraziť atribúty, ktoré sú súčasťou jedného z automaticky zlúčených atribútov, vyberte tento zlúčený atribút.</span><span class="sxs-lookup"><span data-stu-id="39325-113">To view the attributes that are included in one of your automatically merged attributes, select that merged attribute.</span></span> <span data-ttu-id="39325-114">Dva atribúty, ktoré tvoria zlúčený atribút, sa zobrazia v dvoch nových riadkoch pod zlúčeným atribútom.</span><span class="sxs-lookup"><span data-stu-id="39325-114">The two attributes that compose that merged attribute display in two new rows beneath the merged attribute.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="39325-115">![Výber zlúčeného atribútu](media/configure-data-merge-profile-attributes.png "Výber zlúčeného atribútu")</span><span class="sxs-lookup"><span data-stu-id="39325-115">![Select merged attribute](media/configure-data-merge-profile-attributes.png "Select merged attribute")</span></span>

### <a name="separate-merged-attributes"></a><span data-ttu-id="39325-116">Oddelenie zlúčených atribútov</span><span class="sxs-lookup"><span data-stu-id="39325-116">Separate merged attributes</span></span>

<span data-ttu-id="39325-117">Ak chcete oddeliť alebo zrušiť zlúčenie všetkých automaticky zlúčených atribútov, vyhľadajte tento atribút v tabuľke **Atribúty profilu**.</span><span class="sxs-lookup"><span data-stu-id="39325-117">To separate or unmerge any of the automatically merged attributes, find the attribute in the **Profile attributes** table.</span></span>

1. <span data-ttu-id="39325-118">Stlačte tlačidlo troch bodiek (...).</span><span class="sxs-lookup"><span data-stu-id="39325-118">Select the ellipsis (...) button.</span></span>
  
2. <span data-ttu-id="39325-119">V rozbaľovacej ponuke vyberte položku **Oddeliť polia**.</span><span class="sxs-lookup"><span data-stu-id="39325-119">In the dropdown list, select **Separate fields**.</span></span>

### <a name="remove-merged-attributes"></a><span data-ttu-id="39325-120">Odstránenie zlúčených atribútov</span><span class="sxs-lookup"><span data-stu-id="39325-120">Remove merged attributes</span></span>

<span data-ttu-id="39325-121">Ak chcete vylúčiť atribút z entity profilu konečného zákazníka, nájdite ho v tabuľke **Atribúty profilu**.</span><span class="sxs-lookup"><span data-stu-id="39325-121">To exclude an attribute from the final customer profile entity, find it in the **Profile attributes** table.</span></span>

1. <span data-ttu-id="39325-122">Stlačte tlačidlo troch bodiek (...).</span><span class="sxs-lookup"><span data-stu-id="39325-122">Select the ellipsis (...) button.</span></span>
  
2. <span data-ttu-id="39325-123">V rozbaľovacom zozname vyberte položku **Nezlúčiť**.</span><span class="sxs-lookup"><span data-stu-id="39325-123">In the dropdown list, select **Don't merge**.</span></span>

   <span data-ttu-id="39325-124">Atribút sa presunie do sekcie **Odstránené zo záznamu zákazníka**.</span><span class="sxs-lookup"><span data-stu-id="39325-124">The attribute is moved to the **Removed from customer record** section.</span></span>

## <a name="manually-add-a-merged-attribute"></a><span data-ttu-id="39325-125">Ručné pridanie zlúčeného atribútu</span><span class="sxs-lookup"><span data-stu-id="39325-125">Manually add a merged attribute</span></span>

<span data-ttu-id="39325-126">Ak chcete pridať zlúčený atribút, prejdite na stránku **Zlúčiť**.</span><span class="sxs-lookup"><span data-stu-id="39325-126">To add a merged attribute, go to the **Merge** page.</span></span>

1. <span data-ttu-id="39325-127">Vyberte **Pridať zlúčený atribút**.</span><span class="sxs-lookup"><span data-stu-id="39325-127">Select **Add merged attribute**.</span></span>

2. <span data-ttu-id="39325-128">Zadajte **Názov** jeho neskoršiu identifikáciu na stránke **Zlúčiť**.</span><span class="sxs-lookup"><span data-stu-id="39325-128">Provide a **Name** to identify it on the **Merge** page later.</span></span>

3. <span data-ttu-id="39325-129">Voliteľne uveďte **Zobrazované meno**, ktoré sa objaví v zjednotenej entite Profil zákazníka.</span><span class="sxs-lookup"><span data-stu-id="39325-129">Optionally, provide a **Display name** to appear in the unified Customer Profile entity.</span></span>

4. <span data-ttu-id="39325-130">Nakonfigurujte **Výber duplicitných atribútov** na výber atribútov, ktoré chcete zlúčiť zo zosúladených entít.</span><span class="sxs-lookup"><span data-stu-id="39325-130">Configure **Select duplicate attributes** to select the attributes that you want to merge from the matched entities.</span></span> <span data-ttu-id="39325-131">Môžete tiež hľadať atribúty.</span><span class="sxs-lookup"><span data-stu-id="39325-131">You can also search for attributes.</span></span>

5. <span data-ttu-id="39325-132">Nastavte **Zoradiť podľa dôležitosti** na uprednostnenie jedného atribútu pred ostatnými.</span><span class="sxs-lookup"><span data-stu-id="39325-132">Set the **Rank by importance** to prioritize one attribute above the others.</span></span> <span data-ttu-id="39325-133">Napríklad, ak entita *WebAccountCSV* obsahuje najpresnejšie údaje o atribúte *Celé mená*, mali by ste uprednostniť túto entitu pred *ContactCSV* výberom *WebAccountCSV*.</span><span class="sxs-lookup"><span data-stu-id="39325-133">For example, if the *WebAccountCSV* entity includes the most accurate data about the *Full Names* attribute, you could prioritize this entity over *ContactCSV* by selecting *WebAccountCSV*.</span></span> <span data-ttu-id="39325-134">Ako výsledok, *WebAccountCSV* prejde na prvú prioritu, zatiaľ čo *ContactCSV* prejde na druhú prioritu pri posúvaní hodnôt pre atribút *Celé meno*.</span><span class="sxs-lookup"><span data-stu-id="39325-134">As a result, *WebAccountCSV* moves to first priority, while *ContactCSV* moves to second priority when pulling values for the *Full Name* attribute.</span></span>

## <a name="run-your-merge"></a><span data-ttu-id="39325-135">Spustenie zlúčenia</span><span class="sxs-lookup"><span data-stu-id="39325-135">Run your merge</span></span>

<span data-ttu-id="39325-136">Či už atribúty zlúčite ručne alebo necháte, aby ich zlúčil systém, môžete zlúčenie kedykoľvek spustiť.</span><span class="sxs-lookup"><span data-stu-id="39325-136">Whether you manually merge attributes or let the system merge them, you can always run your merge.</span></span> <span data-ttu-id="39325-137">Vyberte **Spustiť** na stránke **Zlúčiť** a začnite s procesom.</span><span class="sxs-lookup"><span data-stu-id="39325-137">Select **Run** on the **Merge** page to start the process.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="39325-138">![Uloženie a spustenie zlúčenia údajov](media/configure-data-merge-save-run.png "Uloženie a spustenie zlúčenia údajov")</span><span class="sxs-lookup"><span data-stu-id="39325-138">![Data merge Save and Run](media/configure-data-merge-save-run.png "Data merge Save and Run")</span></span>

<span data-ttu-id="39325-139">Ak chcete vykonať ďalšie zmeny a zopakovať krok, môžete zrušiť prebiehajúcu zlúčenie.</span><span class="sxs-lookup"><span data-stu-id="39325-139">To make additional changes and rerun the step, you can cancel an in-progress merge.</span></span> <span data-ttu-id="39325-140">Vyberte **Obnovuje sa…** a vyberte **Zrušiť úlohu** na zobrazenej bočnej table.</span><span class="sxs-lookup"><span data-stu-id="39325-140">Select **Refreshing ...** and select **Cancel job**  in the side pane that appears.</span></span>

<span data-ttu-id="39325-141">Keď sa text **Obnovuje sa…** zmení na **Úspešný**, zlúčenie bolo dokončené a vyriešilo rozpory vo vašich údajoch podľa pravidiel, ktoré ste definovali.</span><span class="sxs-lookup"><span data-stu-id="39325-141">After the **Refreshing ...** text changes to **Successful**, merge has completed and resolved contradictions in your data according to the policies you defined.</span></span> <span data-ttu-id="39325-142">Zlúčené a nezlúčené atribúty sú zahrnuté v entite zjednoteného profilu.</span><span class="sxs-lookup"><span data-stu-id="39325-142">Merged and unmerged attributes are included in the unified profile entity.</span></span> <span data-ttu-id="39325-143">Vylúčené atribúty nie sú zahrnuté v entite zjednoteného profilu.</span><span class="sxs-lookup"><span data-stu-id="39325-143">Excluded attributes aren't included in the unified profile entity.</span></span>

<span data-ttu-id="39325-144">Ak to nebolo prvýkrát, keď ste úspešne vykonali zlúčenie, všetky následné procesy vrátane obohatenia, segmentácie a mier, sa automaticky znovu spustia.</span><span class="sxs-lookup"><span data-stu-id="39325-144">If it wasn't the first time you ran a merge successfully, all downstream processes, including enrichment, segmentation, and measures will rerun automatically.</span></span> <span data-ttu-id="39325-145">Po opätovnom spustení všetkých následných procesov profily zákazníkov odrážajú všetky zmeny, ktoré ste vykonali.</span><span class="sxs-lookup"><span data-stu-id="39325-145">After all downstream processes have been rerun, the customer profiles reflect any changes you made.</span></span>

> [!TIP]
> <span data-ttu-id="39325-146">Existuje [šesť druhov stavov](system.md#status-types) pre úlohy/procesy.</span><span class="sxs-lookup"><span data-stu-id="39325-146">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="39325-147">Okrem toho väčšina procesov [závisí na ďalších nadväzujúcich procesoch](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="39325-147">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="39325-148">Môžete si vybrať stav procesu a zobraziť podrobnosti o priebehu celej úlohy.</span><span class="sxs-lookup"><span data-stu-id="39325-148">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="39325-149">Po výbere **Pozrieť detaily** pre jednu z úloh úlohy nájdete ďalšie informácie: čas spracovania, posledný dátum spracovania a všetky chyby a varovania spojené s úlohou.</span><span class="sxs-lookup"><span data-stu-id="39325-149">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="39325-150">Nasledujúci krok</span><span class="sxs-lookup"><span data-stu-id="39325-150">Next Step</span></span>

<span data-ttu-id="39325-151">Konfigurujte [Aktivity](activities.md), [Obohatenie](enrichment-hub.md) alebo [Vzťahy](relationships.md) a získajte viac informácií o svojich zákazníkoch.</span><span class="sxs-lookup"><span data-stu-id="39325-151">Configure [activities](activities.md), [enrichment](enrichment-hub.md), or [relationships](relationships.md) to gain more insights about your customers.</span></span>

<span data-ttu-id="39325-152">Ak ste už nakonfigurovali činnosti, obohatenie alebo vzťahy alebo ak ste zadefinovali segmenty, automaticky sa spracujú, aby sa použili najnovšie údaje o zákazníkoch.</span><span class="sxs-lookup"><span data-stu-id="39325-152">If you already configured activities, enrichment, or relationships, or if you defined segments, they'll be processed automatically to use the latest customer data.</span></span>




[!INCLUDE[footer-include](../includes/footer-banner.md)]