---
title: Slúži na vytvorenie a spravovanie segmentov
description: Vytvorenie segmentov zákazníkov na ich zoskupenie na základe rôznych atribútov.
ms.date: 10/15/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: jimsonc
manager: shellyha
ms.openlocfilehash: 6931110c2ae93cd2792d319aa5a34f0df3088552
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406942"
---
# <a name="create-and-manage-segments"></a><span data-ttu-id="c335e-103">Slúži na vytvorenie a spravovanie segmentov</span><span class="sxs-lookup"><span data-stu-id="c335e-103">Create and manage segments</span></span>

<span data-ttu-id="c335e-104">Segmenty vám umožňujú zoskupiť zákazníkov na základe demografických, transakčných alebo behaviorálnych atribútov.</span><span class="sxs-lookup"><span data-stu-id="c335e-104">Segments let you group your customers based on demographic, transactional, or behavioral attributes.</span></span> <span data-ttu-id="c335e-105">Segmenty môžete použiť na zacielenie reklamných kampaní, predajných aktivít a akcií podpory zákazníkov na dosiahnutie vašich obchodných cieľov.</span><span class="sxs-lookup"><span data-stu-id="c335e-105">You can use segments to target promotional campaigns, sales activities, and customer support actions to achieve your business goals.</span></span>

<span data-ttu-id="c335e-106">Okolo entity profilu zákazníka a jej príbuzných entít môžete definovať zložité filtre.</span><span class="sxs-lookup"><span data-stu-id="c335e-106">You can define complex filters around the Customer Profile entity and its related entities.</span></span> <span data-ttu-id="c335e-107">Každý segment po spracovaní vytvorí skupinu zákazníckych záznamov, ktoré môžete exportovať a podniknúť kroky.</span><span class="sxs-lookup"><span data-stu-id="c335e-107">Each segment, after processing, creates a set of customer records that you can export and take action on.</span></span> <span data-ttu-id="c335e-108">Platia niektoré [obmedzenia služby](service-limits.md).</span><span class="sxs-lookup"><span data-stu-id="c335e-108">Some [service limits](service-limits.md) apply.</span></span>

<span data-ttu-id="c335e-109">Pokiaľ nie je uvedené inak, všetky segmenty sú **dynamické segmenty**, ktoré sa obnovujú podľa opakujúceho sa plánu.</span><span class="sxs-lookup"><span data-stu-id="c335e-109">Unless stated otherwise, all segments are **Dynamic segments**, which are refreshed on a recurring schedule.</span></span>

<span data-ttu-id="c335e-110">Nasledujúci príklad ilustruje možnosti segmentácie.</span><span class="sxs-lookup"><span data-stu-id="c335e-110">The following example illustrates the segmentation capability.</span></span> <span data-ttu-id="c335e-111">Definovali sme segment pre zákazníkov, ktorí za posledných 90 dní objednali tovar aspoň za 500 USD *a* ktorí boli zapojení do hovoru služieb pre zákazníkov, ktorý bol eskalovaný.</span><span class="sxs-lookup"><span data-stu-id="c335e-111">We've defined a segment for customers who ordered at least $500 of goods in the last 90 days *and* who were involved in a customer service call that got escalated.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="c335e-112">![Viac skupín](media/segmentation-group1-2.png "Viac skupín")</span><span class="sxs-lookup"><span data-stu-id="c335e-112">![Multiple groups](media/segmentation-group1-2.png "Multiple groups")</span></span>

## <a name="create-a-new-segment"></a><span data-ttu-id="c335e-113">Vytvorenie nového segmentu</span><span class="sxs-lookup"><span data-stu-id="c335e-113">Create a new segment</span></span>

<span data-ttu-id="c335e-114">Segmenty sú spravované na stránke **Segmenty**.</span><span class="sxs-lookup"><span data-stu-id="c335e-114">Segments are managed on the **Segments** page.</span></span>

1. <span data-ttu-id="c335e-115">V prehľadoch cieľových skupín prejdite na stránku **Segmenty**.</span><span class="sxs-lookup"><span data-stu-id="c335e-115">In audience insights, go to the **Segments** page.</span></span>

2. <span data-ttu-id="c335e-116">Vyberte **Nový** > **Prázdny segment**.</span><span class="sxs-lookup"><span data-stu-id="c335e-116">Select **New** > **Blank segment**.</span></span>

3. <span data-ttu-id="c335e-117">Na table **Nový segment** vyberte typ segmentu a zadajte a **Názov**.</span><span class="sxs-lookup"><span data-stu-id="c335e-117">In the **New segment** pane, choose a segment type and provide a **Name**.</span></span>

   <span data-ttu-id="c335e-118">Voliteľne uveďte zobrazovaný názov a popis, ktorý pomôže identifikovať segment.</span><span class="sxs-lookup"><span data-stu-id="c335e-118">Optionally, provide a display name, and a description that helps identifying the segment.</span></span>

4. <span data-ttu-id="c335e-119">Vyberte **Ďalšie** a prejdite na stránku **Tvorca segmentov**, kde definujete skupinu.</span><span class="sxs-lookup"><span data-stu-id="c335e-119">Select **Next** to get to the **Segment builder** page where you define a group.</span></span> <span data-ttu-id="c335e-120">Skupina je množina zákazníkov.</span><span class="sxs-lookup"><span data-stu-id="c335e-120">A group is a set of customers.</span></span>

5. <span data-ttu-id="c335e-121">Vyberte entity, ktorá obsahuje atribút, podľa ktorého chcete segmentovať.</span><span class="sxs-lookup"><span data-stu-id="c335e-121">Choose the entity that includes the attribute you want to segment by.</span></span>

6. <span data-ttu-id="c335e-122">Vyberte atribút pre segment podľa.</span><span class="sxs-lookup"><span data-stu-id="c335e-122">Choose the attribute to segment by.</span></span> <span data-ttu-id="c335e-123">Tento atribút môže mať jeden zo štyroch typov hodnôt: číselný, reťazec, dátum alebo logický.</span><span class="sxs-lookup"><span data-stu-id="c335e-123">This attribute can have one of four value types: numerical, string, date, or Boolean.</span></span>

7. <span data-ttu-id="c335e-124">Vyberte operátora a hodnotu pre vybraného atribútu.</span><span class="sxs-lookup"><span data-stu-id="c335e-124">Choose an operator and a value for the selected attribute.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c335e-125">![Filter vlastnej skupiny](media/customer-group-numbers.png "Filter skupiny zákazníkov")</span><span class="sxs-lookup"><span data-stu-id="c335e-125">![Custom group filter](media/customer-group-numbers.png "Customer group filter")</span></span>

   |<span data-ttu-id="c335e-126">Číslo</span><span class="sxs-lookup"><span data-stu-id="c335e-126">Number</span></span> |<span data-ttu-id="c335e-127">Definícia</span><span class="sxs-lookup"><span data-stu-id="c335e-127">Definition</span></span>  |
   |---------|---------|
   |<span data-ttu-id="c335e-128">1</span><span class="sxs-lookup"><span data-stu-id="c335e-128">1</span></span>     |<span data-ttu-id="c335e-129">Entity</span><span class="sxs-lookup"><span data-stu-id="c335e-129">Entity</span></span>          |
   |<span data-ttu-id="c335e-130">2</span><span class="sxs-lookup"><span data-stu-id="c335e-130">2</span></span>     |<span data-ttu-id="c335e-131">Atribút</span><span class="sxs-lookup"><span data-stu-id="c335e-131">Attribute</span></span>          |
   |<span data-ttu-id="c335e-132">3</span><span class="sxs-lookup"><span data-stu-id="c335e-132">3</span></span>    |<span data-ttu-id="c335e-133">Operátor</span><span class="sxs-lookup"><span data-stu-id="c335e-133">Operator</span></span>         |
   |<span data-ttu-id="c335e-134">4</span><span class="sxs-lookup"><span data-stu-id="c335e-134">4</span></span>    |<span data-ttu-id="c335e-135">Hodnota</span><span class="sxs-lookup"><span data-stu-id="c335e-135">Value</span></span>         |

8. <span data-ttu-id="c335e-136">Ak je entita prepojená so zjednotenou entitou zákazníka prostredníctvom [vzťahov](relationships.md), musíte definovať cestu vzťahov, aby ste vytvorili platný segment.</span><span class="sxs-lookup"><span data-stu-id="c335e-136">If the entity is connected to the unified customer entity through [relationships](relationships.md), you need to define the relationship path to create a valid segment.</span></span> <span data-ttu-id="c335e-137">Pridajte entity z cesty vzťahov, kým si nevyberiete entitu **Zákazník: CustomerInsights** z rozbaľovacej ponuky.</span><span class="sxs-lookup"><span data-stu-id="c335e-137">Add the entities from the relationship path until you can select the **Customer:CustomerInsights** entity from the dropdown.</span></span> <span data-ttu-id="c335e-138">Potom vyberte **Všetky záznamy** pre každú podmienku.</span><span class="sxs-lookup"><span data-stu-id="c335e-138">Then, choose **All records** for each condition.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c335e-139">![Cesta vzťahov pri vytváraní segmentov](media/segments-multiple-relationships.png "Cesta vzťahov pri vytváraní segmentov")</span><span class="sxs-lookup"><span data-stu-id="c335e-139">![Relationship path during segment creation](media/segments-multiple-relationships.png "Relationship path during segment creation")</span></span>

9. <span data-ttu-id="c335e-140">Segment uložte výberom položky **Uložiť**.</span><span class="sxs-lookup"><span data-stu-id="c335e-140">Select **Save** to save your segment.</span></span> <span data-ttu-id="c335e-141">Váš segment bude uložený a spracovaný, ak budú splnené všetky požiadavky.</span><span class="sxs-lookup"><span data-stu-id="c335e-141">Your segment will be saved and processed if all requirements are validated.</span></span> <span data-ttu-id="c335e-142">V opačnom prípade sa uloží ako koncept.</span><span class="sxs-lookup"><span data-stu-id="c335e-142">Otherwise, it will be saved as a draft.</span></span>

10. <span data-ttu-id="c335e-143">Ak sa chcete vrátiť späť na stránku **Segmenty**, vyberte **Späť na segmenty**.</span><span class="sxs-lookup"><span data-stu-id="c335e-143">Select **Back to segments** to go back to the **Segments** page.</span></span>

## <a name="manage-existing-segments"></a><span data-ttu-id="c335e-144">Spravovanie existujúcich segmentov</span><span class="sxs-lookup"><span data-stu-id="c335e-144">Manage existing segments</span></span>

<span data-ttu-id="c335e-145">Na stránke **Segmenty** môžete zobraziť všetky uložené segmenty a spravovať ich.</span><span class="sxs-lookup"><span data-stu-id="c335e-145">On the **Segments** page, you can view all your saved segments and manage them.</span></span>

<span data-ttu-id="c335e-146">Každý segment je reprezentovaný radom, ktorý obsahuje ďalšie informácie o segmente.</span><span class="sxs-lookup"><span data-stu-id="c335e-146">Each segment is represented by a row that includes additional information about the segment.</span></span>

<span data-ttu-id="c335e-147">Segmenty v stĺpci môžete zoradiť výberom záhlavia stĺpca.</span><span class="sxs-lookup"><span data-stu-id="c335e-147">You can sort the segments in a column by selecting the column heading.</span></span>

<span data-ttu-id="c335e-148">Použite pole **Vyhľadávanie** v pravom hornom rohu na filtrovanie segmentov.</span><span class="sxs-lookup"><span data-stu-id="c335e-148">Use the **Search** box in the top-right corner to filter the segments.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="c335e-149">![Možnosti správy existujúceho segmentu](media/segments-selected-segment.png "Možnosti správy existujúceho segmentu")</span><span class="sxs-lookup"><span data-stu-id="c335e-149">![Options to manage an existing segment](media/segments-selected-segment.png "Options to manage an existing segment")</span></span>

<span data-ttu-id="c335e-150">Po výbere segmentu sú k dispozícii nasledujúce akcie:</span><span class="sxs-lookup"><span data-stu-id="c335e-150">The following action are available when you select a segment:</span></span>

- <span data-ttu-id="c335e-151">**Zobrazenie** podrobností o segmente vrátane trendu počtu členov a ukážky členov segmentu.</span><span class="sxs-lookup"><span data-stu-id="c335e-151">**View** the segment details, including member count trend a preview of segment members.</span></span>
- <span data-ttu-id="c335e-152">**Úprava** segmentu na zmenu jeho vlastností.</span><span class="sxs-lookup"><span data-stu-id="c335e-152">**Edit** the segment to change its properties.</span></span>
- <span data-ttu-id="c335e-153">**Obnova** segmentu, ktorý obsahuje najnovšie údaje.</span><span class="sxs-lookup"><span data-stu-id="c335e-153">**Refresh** the segment to include the latest data.</span></span>
- <span data-ttu-id="c335e-154">**Aktivácia** alebo **deaktivácia** segmentu.</span><span class="sxs-lookup"><span data-stu-id="c335e-154">**Activate** or **Deactivate** the segment.</span></span> <span data-ttu-id="c335e-155">Segmenty majú dva možné stavy – aktívny alebo neaktívny.</span><span class="sxs-lookup"><span data-stu-id="c335e-155">Segments have two possible states - active or inactive.</span></span> <span data-ttu-id="c335e-156">Tieto stavy sa hodia pri úprave segmentu.</span><span class="sxs-lookup"><span data-stu-id="c335e-156">These states come in handy when editing a segment.</span></span> <span data-ttu-id="c335e-157">Pre neaktívne segmenty existuje definícia segmentu, zatiaľ však neobsahuje žiadnych zákazníkov.</span><span class="sxs-lookup"><span data-stu-id="c335e-157">For inactive segments, the segment definition exists but it doesn't contain any customers yet.</span></span> <span data-ttu-id="c335e-158">Keď aktivujete segment, jeho stav sa zmení z „neaktívneho“ na „aktívny“ a začne hľadať zákazníkov, ktorí zodpovedajú definícii segmentu.</span><span class="sxs-lookup"><span data-stu-id="c335e-158">When you activate a segment, its state changes from 'inactive' to 'active" and it starts looking for customers that match the segment definition.</span></span> <span data-ttu-id="c335e-159">Ak je [plánované obnovenie](system.md#schedule-tab) nakonfigurované, neaktívne segmenty majú **Postavenie** uvedené ako **Preskočené**, čo naznačuje, že k obnoveniu ani nedošlo.</span><span class="sxs-lookup"><span data-stu-id="c335e-159">If a [scheduled refresh](system.md#schedule-tab) is configured, inactive segments have the **Status** listed as **Skipped**, indicating that a refresh wasn't even attempted.</span></span> <span data-ttu-id="c335e-160">Keď je neaktívny segment aktivovaný, obnoví sa a bude zahrnutý do plánovaných aktualizácií.</span><span class="sxs-lookup"><span data-stu-id="c335e-160">When an inactive segment is activated, it will refresh and will be included in scheduled refreshes.</span></span>
  <span data-ttu-id="c335e-161">Prípadne môžete použiť funkciu **Naplánovať neskôr** v rozbaľovacej ponuke **Aktivácia/Deaktivácia** na určenie budúceho dátumu a času aktivácie a deaktivácie konkrétneho segmentu.</span><span class="sxs-lookup"><span data-stu-id="c335e-161">Alternatively, you can use the **Schedule later** functionality in the **Activate/Deactivate** dropdown to specify a future date and time for activation and deactivation of a particular segment.</span></span>
- <span data-ttu-id="c335e-162">**Premenovanie** segmentu.</span><span class="sxs-lookup"><span data-stu-id="c335e-162">**Rename** the segment.</span></span>
- <span data-ttu-id="c335e-163">**Stiahnutie** zoznam členov ako súbor .CSV.</span><span class="sxs-lookup"><span data-stu-id="c335e-163">**Download** the list of members as a .CSV file.</span></span>
- <span data-ttu-id="c335e-164">Možnosť **Pridať do** odošle zoznam ID zákazníkov v segmente na spracovanie v inej aplikácii.</span><span class="sxs-lookup"><span data-stu-id="c335e-164">**Add to** option sends the list of customer IDs in the segment for processing in another application.</span></span>
- <span data-ttu-id="c335e-165">**Odstránenie** segmentu.</span><span class="sxs-lookup"><span data-stu-id="c335e-165">**Delete** the segment.</span></span>

## <a name="refresh-segments"></a><span data-ttu-id="c335e-166">Obnovenie segmentov</span><span class="sxs-lookup"><span data-stu-id="c335e-166">Refresh segments</span></span>

<span data-ttu-id="c335e-167">Výberom možnosti **Obnoviť všetko** na stránke **Segmenty** môžete obnoviť všetky segmenty naraz alebo môžete jeden alebo viac segmentov, keď ich vyberiete a následne vyberiete **Obnoviť** z možností.</span><span class="sxs-lookup"><span data-stu-id="c335e-167">You can refresh all segments at once by selecting **Refresh all** on the **Segments** page or you can refresh one or multiple segments when you select them and choose **Refresh** in from the options.</span></span> <span data-ttu-id="c335e-168">Prípadne môžete nakonfigurovať opakujúce sa obnovovanie v ponuke **Správca** > **Systém** > **Plán**.</span><span class="sxs-lookup"><span data-stu-id="c335e-168">Alternatively, you can configure a recurring refresh on **Admin** > **System** > **Schedule**.</span></span>

> [!TIP]
> <span data-ttu-id="c335e-169">Existuje [šesť druhov stavov](system.md#status-types) pre úlohy/procesy.</span><span class="sxs-lookup"><span data-stu-id="c335e-169">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="c335e-170">Okrem toho väčšina procesov [závisí na ďalších nadväzujúcich procesoch](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="c335e-170">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="c335e-171">Môžete si vybrať stav procesu a zobraziť podrobnosti o priebehu celej úlohy.</span><span class="sxs-lookup"><span data-stu-id="c335e-171">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="c335e-172">Po výbere **Pozrieť detaily** pre jednu z úloh úlohy nájdete ďalšie informácie: čas spracovania, posledný dátum spracovania a všetky chyby a varovania spojené s úlohou.</span><span class="sxs-lookup"><span data-stu-id="c335e-172">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="download-and-export-segments"></a><span data-ttu-id="c335e-173">Sťahovanie a exportovanie segmentov</span><span class="sxs-lookup"><span data-stu-id="c335e-173">Download and export segments</span></span>

<span data-ttu-id="c335e-174">Svoje segmenty si môžete stiahnuť do súboru CSV alebo ich exportovať do Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="c335e-174">You can download your segments to a CSV file or export them to Dynamics 365 Sales.</span></span>

### <a name="download-segments-to-a-csv-file"></a><span data-ttu-id="c335e-175">Stiahnite segmenty do súboru CSV</span><span class="sxs-lookup"><span data-stu-id="c335e-175">Download segments to a CSV file</span></span>

1. <span data-ttu-id="c335e-176">V prehľadoch cieľových skupín prejdite na stránku **Segmenty**.</span><span class="sxs-lookup"><span data-stu-id="c335e-176">In audience insights, go to the **Segments** page.</span></span>

2. <span data-ttu-id="c335e-177">Vyberte tri bodky v dlaždici konkrétneho segmentu.</span><span class="sxs-lookup"><span data-stu-id="c335e-177">Select the ellipsis in a specific segment's tile.</span></span>

3. <span data-ttu-id="c335e-178">Vyberte **Stiahnuť ako CSV** z rozbaľovacieho zoznamu akcií.</span><span class="sxs-lookup"><span data-stu-id="c335e-178">Select **Download as CSV** from the actions drop-down list.</span></span>

### <a name="export-segments-to-dynamics-365-sales"></a><span data-ttu-id="c335e-179">Export segmentov do Dynamics 365 Sales</span><span class="sxs-lookup"><span data-stu-id="c335e-179">Export segments to Dynamics 365 Sales</span></span>

<span data-ttu-id="c335e-180">Pred exportom segmentov do Dynamics 365 Sales musí správca [vytvoriť cieľ exportu](export-destinations.md) pre Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="c335e-180">Before exporting segments to Dynamics 365 Sales, an admin needs to [create the export destination](export-destinations.md) for Dynamics 365 Sales.</span></span>

1. <span data-ttu-id="c335e-181">V prehľadoch cieľových skupín prejdite na stránku **Segmenty**.</span><span class="sxs-lookup"><span data-stu-id="c335e-181">In audience insights, go to the **Segments** page.</span></span>

2. <span data-ttu-id="c335e-182">Vyberte tri bodky v dlaždici konkrétneho segmentu.</span><span class="sxs-lookup"><span data-stu-id="c335e-182">Select the ellipsis in a specific segment's tile.</span></span>

3. <span data-ttu-id="c335e-183">Vyberte **Pridať k** z rozbaľovacieho zoznamu akcií a vyberte cieľ exportu, do ktorého chcete dáta poslať.</span><span class="sxs-lookup"><span data-stu-id="c335e-183">Select **Add to** from the actions drop-down list and select the export destination you want to send the data to.</span></span>

## <a name="draft-mode-for-segments"></a><span data-ttu-id="c335e-184">Režim konceptu pre segmenty</span><span class="sxs-lookup"><span data-stu-id="c335e-184">Draft mode for segments</span></span>

<span data-ttu-id="c335e-185">Ak nie sú splnené všetky požiadavky na spracovanie segmentu, môžete segment uložiť ako koncept a získať prístup k nemu zo stránky **Segmenty**.</span><span class="sxs-lookup"><span data-stu-id="c335e-185">If not all requirements to process a segment are met, you can save the segment as a draft and access it from the **Segments** page.</span></span>

<span data-ttu-id="c335e-186">Uloží sa ako neaktívny segment a nebude ho možné aktivovať, kým nebude platný.</span><span class="sxs-lookup"><span data-stu-id="c335e-186">It will be saved as an inactive segment, and can't be activated it until it's valid.</span></span>

## <a name="add-more-conditions-to-a-group"></a><span data-ttu-id="c335e-187">Pridanie ďalších podmienok do skupiny</span><span class="sxs-lookup"><span data-stu-id="c335e-187">Add more conditions to a group</span></span>

<span data-ttu-id="c335e-188">Na pridanie ďalších podmienok do skupiny môžete použiť dva logické operátory:</span><span class="sxs-lookup"><span data-stu-id="c335e-188">To add more conditions to a group, you can use two logical operators:</span></span>

- <span data-ttu-id="c335e-189">Operátor **A**: Obe podmienky musia byť splnené ako súčasť procesu segmentácie.</span><span class="sxs-lookup"><span data-stu-id="c335e-189">**AND** operator: Both conditions must be met as part of the segmentation process.</span></span> <span data-ttu-id="c335e-190">Táto voľba je najužitočnejšia, keď definujete podmienky pre rôzne entity.</span><span class="sxs-lookup"><span data-stu-id="c335e-190">This option is most useful when you define conditions across different entities.</span></span>

- <span data-ttu-id="c335e-191">Operátor **ALEBO**: V rámci procesu segmentácie musí byť splnená jedna z podmienok.</span><span class="sxs-lookup"><span data-stu-id="c335e-191">**OR** operator: Either one of the conditions needs to be met as part of the segmentation process.</span></span> <span data-ttu-id="c335e-192">Táto voľba je najužitočnejšia, keď definujete viac podmienok pre jednu entitu.</span><span class="sxs-lookup"><span data-stu-id="c335e-192">This option is most useful when you define multiple conditions for the same entity.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c335e-193">![Operátor ALEBO, ktorý musí splniť ktorúkoľvek z podmienok](media/segmentation-either-condition.png "Operátor ALEBO, ktorý musí splniť ktorúkoľvek z podmienok")</span><span class="sxs-lookup"><span data-stu-id="c335e-193">![OR operator where either condition needs to be met](media/segmentation-either-condition.png "OR operator where either condition needs to be met")</span></span>

<span data-ttu-id="c335e-194">V súčasnosti je možné vnoriť operátor **ALEBO** pod operátor **A**, ale nie naopak.</span><span class="sxs-lookup"><span data-stu-id="c335e-194">It's currently possible to nest an **OR** operator under an **AND** operator, but not the other way around.</span></span>

## <a name="combine-multiple-groups"></a><span data-ttu-id="c335e-195">Kombinácia viacerých skupín</span><span class="sxs-lookup"><span data-stu-id="c335e-195">Combine multiple groups</span></span>

<span data-ttu-id="c335e-196">Každá skupina produkuje špecifickú skupinu zákazníkov.</span><span class="sxs-lookup"><span data-stu-id="c335e-196">Each group produces a specific set of customers.</span></span> <span data-ttu-id="c335e-197">Tieto skupiny môžete skombinovať tak, aby zahŕňali zákazníkov požadovaných pre váš obchodný prípad.</span><span class="sxs-lookup"><span data-stu-id="c335e-197">You can combine these groups to include the customers required for your business case.</span></span>

1. <span data-ttu-id="c335e-198">V prehľadoch cieľových skupín prejdite na stránku **Segmenty** a vyberte segment.</span><span class="sxs-lookup"><span data-stu-id="c335e-198">In audience insights, go to the **Segments** page and select a segment.</span></span>

2. <span data-ttu-id="c335e-199">Vyberte **Pridať skupinu**.</span><span class="sxs-lookup"><span data-stu-id="c335e-199">Select **Add Group**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c335e-200">![Skupina zákazníkov – pridanie skupiny](media/customer-group-add-group.png "Skupina zákazníkov – pridanie skupiny")</span><span class="sxs-lookup"><span data-stu-id="c335e-200">![Customer group add group](media/customer-group-add-group.png "Customer group add group")</span></span>

3. <span data-ttu-id="c335e-201">Vyberte jednu z nasledujúcich množín operátorov: **Zjednotenie**, **Prienik** alebo **Okrem**.</span><span class="sxs-lookup"><span data-stu-id="c335e-201">Select one of the following set operators: **Union**, **Intersect**, or **Except**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c335e-202">![Skupina zákazníkov – pridanie zjednotenia](media/customer-group-union.png "Skupina zákazníkov – pridanie zjednotenia")</span><span class="sxs-lookup"><span data-stu-id="c335e-202">![Customer group add union](media/customer-group-union.png "Customer group add union")</span></span>

   <span data-ttu-id="c335e-203">Vyberte operátora množín na definovanie novej skupiny.</span><span class="sxs-lookup"><span data-stu-id="c335e-203">Select a set operator to define a new group.</span></span> <span data-ttu-id="c335e-204">Uložením rôznych skupín určíte, ktoré údaje sa budú získavať:</span><span class="sxs-lookup"><span data-stu-id="c335e-204">Save different groups to determine what data gets retained:</span></span>

   - <span data-ttu-id="c335e-205">**Zjednotenie** zjednocuje obe skupiny.</span><span class="sxs-lookup"><span data-stu-id="c335e-205">**Union** unites the two groups.</span></span>

   - <span data-ttu-id="c335e-206">**Prienik** prekrýva obe skupiny.</span><span class="sxs-lookup"><span data-stu-id="c335e-206">**Intersect** overlaps the two groups.</span></span> <span data-ttu-id="c335e-207">Iba údaje, ktoré *sú spoločné* pre obe skupiny, sa zachovávajú v zjednotenej skupine.</span><span class="sxs-lookup"><span data-stu-id="c335e-207">Only data that *is common* to both groups is retained in the unified group.</span></span>

   - <span data-ttu-id="c335e-208">Možnosť **Okrem** kombinuje dve skupiny.</span><span class="sxs-lookup"><span data-stu-id="c335e-208">**Except** combines the two groups.</span></span> <span data-ttu-id="c335e-209">Zachovajú sa iba údaje v skupine A, ktoré *nie sú spoločné* s údajmi v skupine B.</span><span class="sxs-lookup"><span data-stu-id="c335e-209">Only data in group A that *is not common* to data in group B is retained.</span></span>

## <a name="view-processing-history-and-segment-members"></a><span data-ttu-id="c335e-210">Zobrazenie histórie spracovania a členov segmentu</span><span class="sxs-lookup"><span data-stu-id="c335e-210">View processing history and segment members</span></span>

<span data-ttu-id="c335e-211">Ak chcete zobraziť konsolidované údaje o segmente, prečítajte si podrobnosti.</span><span class="sxs-lookup"><span data-stu-id="c335e-211">You can see consolidated data about a segment by reviewing its details.</span></span>

<span data-ttu-id="c335e-212">Na stránke **Segmenty** vyberte segment, ktorý chcete skontrolovať.</span><span class="sxs-lookup"><span data-stu-id="c335e-212">On the **Segments** page, select the segment you want to review.</span></span>

<span data-ttu-id="c335e-213">Horná časť stránky obsahuje graf trendov, ktorý vizualizuje zmeny v počte členov.</span><span class="sxs-lookup"><span data-stu-id="c335e-213">The upper part of the page includes a trend graph that visualizes changes in member count.</span></span> <span data-ttu-id="c335e-214">Ak umiestnite kurzor myši nad údajové body, zobrazí sa počet členov k určitému dátumu.</span><span class="sxs-lookup"><span data-stu-id="c335e-214">Hover over data points to see the member count on a specific date.</span></span>

<span data-ttu-id="c335e-215">Môžete aktualizovať časový rámec vizualizácie.</span><span class="sxs-lookup"><span data-stu-id="c335e-215">You can update the time frame of the visualization.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="c335e-216">![Časový rozsah segmentu](media/segment-time-range.png "Časový rozsah segmentu")</span><span class="sxs-lookup"><span data-stu-id="c335e-216">![Segment time range](media/segment-time-range.png "Segment time range")</span></span>

<span data-ttu-id="c335e-217">Spodná časť obsahuje zoznam členov segmentu.</span><span class="sxs-lookup"><span data-stu-id="c335e-217">The lower part contains a list of the segment members.</span></span>

> [!NOTE]
> <span data-ttu-id="c335e-218">Polia, ktoré sa nachádzajú v tomto zozname, sú založené na atribútoch entít vášho segmentu.</span><span class="sxs-lookup"><span data-stu-id="c335e-218">Fields that appear in this list are based on the attributes of your segment's entities.</span></span>
>
><span data-ttu-id="c335e-219">Zoznam predstavuje ukážku zodpovedajúcich členov segmentu a zobrazuje prvých 100 záznamov segmentu, aby ste ho mohli rýchlo vyhodnotiť a podľa potreby skontrolovať jeho definície.</span><span class="sxs-lookup"><span data-stu-id="c335e-219">The list is a preview of the matching segment members and shows the first 100 records of your segment so that you can quickly evaluate it and review its definitions if needed.</span></span> <span data-ttu-id="c335e-220">Ak chcete zobraziť všetky zodpovedajúce záznamy, musíte [exportovať segment](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="c335e-220">To see all matching records, you need to [export the segment](export-destinations.md).</span></span>

## <a name="quick-segments"></a><span data-ttu-id="c335e-221">Rýchle segmenty</span><span class="sxs-lookup"><span data-stu-id="c335e-221">Quick segments</span></span>

<span data-ttu-id="c335e-222">Okrem nástroja na tvorbu segmentov existuje ešte jedna cesta k vytváraniu segmentov.</span><span class="sxs-lookup"><span data-stu-id="c335e-222">In addition to the segment builder, there's another path for creating segments.</span></span> <span data-ttu-id="c335e-223">Rýchle segmenty vám umožňujú rýchlo a vytvárať jednoduché segmenty s jediným operátorom s okamžitým prehľadom.</span><span class="sxs-lookup"><span data-stu-id="c335e-223">Quick segments let you build simple segments with a single operator quickly and with instant insights.</span></span>

1. <span data-ttu-id="c335e-224">Na stránke **Segmenty** vyberte **Nový** > **Rýchlo vytvoriť z**.</span><span class="sxs-lookup"><span data-stu-id="c335e-224">On the **Segments** page, select **New** > **Quickly create from**.</span></span>

   - <span data-ttu-id="c335e-225">Vyberte možnosť **Profily** na vytvorenie segmentu, ktorý je založený na jednotnej entite zákazníka.</span><span class="sxs-lookup"><span data-stu-id="c335e-225">Select the **Profiles** option to build a segment that is based on the unified Customer entity.</span></span>
   - <span data-ttu-id="c335e-226">Vyberte možnosť **Opatrenia** na vybudovanie segmentu okolo každého z opatrení typu Atribút zákazníka, ktoré ste predtým vytvorili na stránke **Opatrenia**.</span><span class="sxs-lookup"><span data-stu-id="c335e-226">Select the **Measures** option to build a segment around each of the Customer Attribute type of measures you have previously created on the **Measures** page.</span></span>
   - <span data-ttu-id="c335e-227">Vyberte možnosť **Analýza** na zostavenie segmentu okolo jednej z výstupných entít, ktoré ste vygenerovali pomocou funkcií **Predpovede** alebo **Vlastné modely**.</span><span class="sxs-lookup"><span data-stu-id="c335e-227">Select the **Intelligence** option to build a segment around one of the output entities you generated using either the **Predictions** or **Custom Models** capabilities.</span></span>

2. <span data-ttu-id="c335e-228">V dialógovom okne **Nový rýchly segment** vyberte atribút z rozbaľovacej ponuky **Pole**.</span><span class="sxs-lookup"><span data-stu-id="c335e-228">In the **New quick segment** dialog box, select an attribute from the **Field** dropdown.</span></span>

3. <span data-ttu-id="c335e-229">Systém poskytne niektoré ďalšie informácie, ktoré vám pomôžu vytvoriť lepšie segmenty vašich zákazníkov.</span><span class="sxs-lookup"><span data-stu-id="c335e-229">The system will provide some additional insights that help you create better segments of your customers.</span></span>
   - <span data-ttu-id="c335e-230">Pre kategorické polia zobrazíme 10 najvyšších počtov zákazníkov.</span><span class="sxs-lookup"><span data-stu-id="c335e-230">For categorical fields, we'll show 10 top customer counts.</span></span> <span data-ttu-id="c335e-231">Vyberte **Hodnota** a potom **Skontrolovať**.</span><span class="sxs-lookup"><span data-stu-id="c335e-231">Choose a **Value** and select **Review**.</span></span>

   - <span data-ttu-id="c335e-232">Pokiaľ ide o číselný atribút, systém ukáže, ktorá hodnota atribútu spadá pod percentil každého zákazníka.</span><span class="sxs-lookup"><span data-stu-id="c335e-232">For a numerical attribute, the system will show what attribute value falls under each customer's percentile.</span></span> <span data-ttu-id="c335e-233">Vyberte **Operátor** a **Hodnota**, potom vyberte **Skontrolovať**.</span><span class="sxs-lookup"><span data-stu-id="c335e-233">Choose an **Operator** and a **Value**, then select **Review**.</span></span>

4. <span data-ttu-id="c335e-234">Systém vám poskytne **Odhadovanú veľkosť segmentu**.</span><span class="sxs-lookup"><span data-stu-id="c335e-234">The system will provide you with an **Estimated segment size**.</span></span> <span data-ttu-id="c335e-235">Môžete si vybrať, či chcete vygenerovať segment, ktorý ste definovali, alebo ho znova opraviť, aby ste získali inú veľkosť segmentu.</span><span class="sxs-lookup"><span data-stu-id="c335e-235">You can choose whether to generate the segment you've defined, or first revisit it to get a different segment size.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="c335e-236">![Názov a odhad rýchleho segmentu](media/quick-segment-name.png "Názov a odhad rýchleho segmentu")</span><span class="sxs-lookup"><span data-stu-id="c335e-236">![Name and estimation for a quick segment](media/quick-segment-name.png "Name and estimation for a quick segment")</span></span>

5. <span data-ttu-id="c335e-237">Zadajte **Názov** pre svoj segment.</span><span class="sxs-lookup"><span data-stu-id="c335e-237">Provide a **Name** for your segment.</span></span> <span data-ttu-id="c335e-238">Voliteľne zadajte **Zobrazovaný názov**.</span><span class="sxs-lookup"><span data-stu-id="c335e-238">Optionally, provide a **Display name**.</span></span>

6. <span data-ttu-id="c335e-239">Výberom položky **Uložiť** vytvorte segment.</span><span class="sxs-lookup"><span data-stu-id="c335e-239">Select **Save** to create your segment.</span></span>

7. <span data-ttu-id="c335e-240">Po dokončení spracovania môžete segment zobraziť ako akýkoľvek iný segment, ktorý ste vytvorili.</span><span class="sxs-lookup"><span data-stu-id="c335e-240">After the segment has finished processing, you can view it like any other segment you've created.</span></span>

<span data-ttu-id="c335e-241">Pre nasledujúce scenáre odporúčame radšej použiť nástroj na tvorbu segmentov než odporúčané možnosti segmentov:</span><span class="sxs-lookup"><span data-stu-id="c335e-241">For the following scenarios, we advise using the segment builder rather than the recommended segments capability:</span></span>

- <span data-ttu-id="c335e-242">Vytváranie segmentov s filtrami v kategorických poliach, v ktorých je operátor iný ako **Je**</span><span class="sxs-lookup"><span data-stu-id="c335e-242">Creating segments with filters on categorical fields where the operator is different than the **Is** operator</span></span>
- <span data-ttu-id="c335e-243">Vytváranie segmentov s filtrami v číselných poliach, v ktorých je operátor iný ako **Medzi**, **Väčší než** a **Menší než**</span><span class="sxs-lookup"><span data-stu-id="c335e-243">Creating segments with filters on numerical fields where the operator is different than the **Between**, **Greater than**, and **Less than** operators</span></span>
- <span data-ttu-id="c335e-244">Vytváranie segmentov s filtrami v poliach typu dátumu</span><span class="sxs-lookup"><span data-stu-id="c335e-244">Creating segments with filters on date type fields</span></span>

## <a name="next-steps"></a><span data-ttu-id="c335e-245">Ďalšie kroky</span><span class="sxs-lookup"><span data-stu-id="c335e-245">Next steps</span></span>

<span data-ttu-id="c335e-246">[Exportujte segment](export-destinations.md) a preskúmajte [kartu zákazníka](customer-card-add-in.md) a [konektory](export-power-bi.md), aby ste získali prehľad o úrovni zákazníka.</span><span class="sxs-lookup"><span data-stu-id="c335e-246">[Export a segment](export-destinations.md) and explore the [Customer Card](customer-card-add-in.md) and [Connectors](export-power-bi.md) to get insights on the customer level.</span></span>
