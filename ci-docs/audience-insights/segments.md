---
title: Segmenty v prehľade cieľových skupín
description: Prehľad o segmentoch a o tom, ako ich vytvárať a spravovať.
ms.date: 05/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 336cab8619c0b80b7b8a38035cae99620baf2873
ms.sourcegitcommit: 0b754d194d765afef70d1008db7b347dd1f0ee40
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 06/24/2021
ms.locfileid: "6306276"
---
# <a name="segments-overview"></a><span data-ttu-id="5a720-103">Prehľad segmentov</span><span class="sxs-lookup"><span data-stu-id="5a720-103">Segments overview</span></span>

<span data-ttu-id="5a720-104">Segmenty vám umožňujú zoskupiť zákazníkov na základe demografických, transakčných alebo behaviorálnych atribútov.</span><span class="sxs-lookup"><span data-stu-id="5a720-104">Segments let you group your customers based on demographic, transactional, or behavioral attributes.</span></span> <span data-ttu-id="5a720-105">Segmenty môžete použiť na zacielenie reklamných kampaní, predajných aktivít a akcií podpory zákazníkov na dosiahnutie vašich obchodných cieľov.</span><span class="sxs-lookup"><span data-stu-id="5a720-105">You can use segments to target promotional campaigns, sales activities, and customer support actions to achieve your business goals.</span></span>

<span data-ttu-id="5a720-106">Profily zákazníkov, ktoré zodpovedajú filtrom definície segmentu, sa označujú ako *členovia* segmentu.</span><span class="sxs-lookup"><span data-stu-id="5a720-106">Customer profiles that match the filters of a segment definition are referred as *members* of a segment.</span></span> <span data-ttu-id="5a720-107">Platia niektoré [obmedzenia služby](service-limits.md).</span><span class="sxs-lookup"><span data-stu-id="5a720-107">Some [service limits](service-limits.md) apply.</span></span>

## <a name="create-a-new-segment"></a><span data-ttu-id="5a720-108">Vytvorenie nového segmentu</span><span class="sxs-lookup"><span data-stu-id="5a720-108">Create a new segment</span></span>

<span data-ttu-id="5a720-109">Existuje niekoľko spôsobov, ako vytvoriť nový segment:</span><span class="sxs-lookup"><span data-stu-id="5a720-109">There are multiple ways to create a new segment:</span></span> 

- <span data-ttu-id="5a720-110">Komplexný segment s nástrojom na tvorbu segmentov: [Prázdny segment](segment-builder.md#create-a-new-segment)</span><span class="sxs-lookup"><span data-stu-id="5a720-110">Complex segment with segment builder: [Blank segment](segment-builder.md#create-a-new-segment)</span></span>
- <span data-ttu-id="5a720-111">Jednoduché segmenty s jedným operátorom: [Rýchly segment](segment-builder.md#quick-segments)</span><span class="sxs-lookup"><span data-stu-id="5a720-111">Simple segments with one operator: [Quick segment](segment-builder.md#quick-segments)</span></span>
- <span data-ttu-id="5a720-112">Spôsob hľadania podobných zákazníkov pomocou technológie AI: [Podobní zákazníci](find-similar-customer-segments.md)</span><span class="sxs-lookup"><span data-stu-id="5a720-112">AI-powered way to find similar customers: [Similar Customers](find-similar-customer-segments.md)</span></span>
- <span data-ttu-id="5a720-113">Návrhy založené na AI založené na opatreniach alebo atribútoch: [Navrhované segmenty na zlepšenie opatrení](suggested-segments.md)</span><span class="sxs-lookup"><span data-stu-id="5a720-113">AI-powered suggestions based on measures or attributes: [Suggested segments to improve measures](suggested-segments.md)</span></span>
- <span data-ttu-id="5a720-114">Návrhy založené na činnostiach: [Navrhované segmenty na základe aktivity zákazníka](suggested-segments-activity.md)</span><span class="sxs-lookup"><span data-stu-id="5a720-114">Suggestions based on activities: [Suggested segments based on customer activity](suggested-segments-activity.md)</span></span>

## <a name="manage-existing-segments"></a><span data-ttu-id="5a720-115">Spravovanie existujúcich segmentov</span><span class="sxs-lookup"><span data-stu-id="5a720-115">Manage existing segments</span></span>

<span data-ttu-id="5a720-116">Choďte na stránku **Segmenty** a zobrazte si všetky svoje uložené segmenty a spravujte ich.</span><span class="sxs-lookup"><span data-stu-id="5a720-116">Go to the **Segments** page, to view all your saved segments and manage them.</span></span>

<span data-ttu-id="5a720-117">Každý segment je reprezentovaný radom, ktorý obsahuje ďalšie informácie o segmente.</span><span class="sxs-lookup"><span data-stu-id="5a720-117">Each segment is represented by a row that includes additional information about the segment.</span></span>

:::image type="content" source="media/segments-selected-segment.png" alt-text="Vybratý segment s rozbaľovacím zoznamom možností a dostupnými možnosťami.":::

<span data-ttu-id="5a720-119">Po výbere segmentu sú k dispozícii nasledujúce akcie:</span><span class="sxs-lookup"><span data-stu-id="5a720-119">The following action are available when you select a segment:</span></span>

- <span data-ttu-id="5a720-120">**Zobrazenie** podrobností o segmente vrátane trendu počtu členov a ukážky členov segmentu.</span><span class="sxs-lookup"><span data-stu-id="5a720-120">**View** the segment details, including member count trend a preview of segment members.</span></span>
- <span data-ttu-id="5a720-121">**Úprava** segmentu na zmenu jeho vlastností.</span><span class="sxs-lookup"><span data-stu-id="5a720-121">**Edit** the segment to change its properties.</span></span>
- <span data-ttu-id="5a720-122">**Vytvorte duplikát** segmentu.</span><span class="sxs-lookup"><span data-stu-id="5a720-122">**Create duplicate** of a segment.</span></span> <span data-ttu-id="5a720-123">Môžete sa rozhodnúť okamžite upraviť jeho vlastnosti alebo duplikát jednoducho uložiť.</span><span class="sxs-lookup"><span data-stu-id="5a720-123">You can choose to edit its properties right away or simply save the duplicate.</span></span>
- <span data-ttu-id="5a720-124">**Obnova** segmentu, ktorý obsahuje najnovšie údaje.</span><span class="sxs-lookup"><span data-stu-id="5a720-124">**Refresh** the segment to include the latest data.</span></span>
- <span data-ttu-id="5a720-125">**Aktivácia** alebo **deaktivácia** segmentu.</span><span class="sxs-lookup"><span data-stu-id="5a720-125">**Activate** or **Deactivate** the segment.</span></span> <span data-ttu-id="5a720-126">Segmenty majú dva možné stavy – aktívny alebo neaktívny.</span><span class="sxs-lookup"><span data-stu-id="5a720-126">Segments have two possible states - active or inactive.</span></span> <span data-ttu-id="5a720-127">Tieto stavy sa hodia pri úprave segmentu.</span><span class="sxs-lookup"><span data-stu-id="5a720-127">These states come in handy when editing a segment.</span></span> <span data-ttu-id="5a720-128">Pre neaktívne segmenty existuje definícia segmentu, zatiaľ však neobsahuje žiadnych zákazníkov.</span><span class="sxs-lookup"><span data-stu-id="5a720-128">For inactive segments, the segment definition exists but it doesn't contain any customers yet.</span></span> <span data-ttu-id="5a720-129">Keď aktivujete segment, jeho stav sa zmení z „neaktívneho“ na „aktívny“ a začne hľadať zákazníkov, ktorí zodpovedajú definícii segmentu.</span><span class="sxs-lookup"><span data-stu-id="5a720-129">When you activate a segment, its state changes from 'inactive' to 'active" and it starts looking for customers that match the segment definition.</span></span> <span data-ttu-id="5a720-130">Ak je [plánované obnovenie](system.md#schedule-tab) nakonfigurované, neaktívne segmenty majú **Postavenie** uvedené ako **Preskočené**, čo naznačuje, že k obnoveniu ani nedošlo.</span><span class="sxs-lookup"><span data-stu-id="5a720-130">If a [scheduled refresh](system.md#schedule-tab) is configured, inactive segments have the **Status** listed as **Skipped**, indicating that a refresh wasn't even attempted.</span></span> <span data-ttu-id="5a720-131">Keď je neaktívny segment aktivovaný, obnoví sa a bude zahrnutý do plánovaných aktualizácií.</span><span class="sxs-lookup"><span data-stu-id="5a720-131">When an inactive segment is activated, it will refresh and will be included in scheduled refreshes.</span></span>
  <span data-ttu-id="5a720-132">Prípadne môžete použiť funkciu **Naplánovať neskôr** v rozbaľovacej ponuke **Aktivácia/Deaktivácia** na určenie budúceho dátumu a času aktivácie a deaktivácie konkrétneho segmentu.</span><span class="sxs-lookup"><span data-stu-id="5a720-132">Alternatively, you can use the **Schedule later** functionality in the **Activate/Deactivate** dropdown to specify a future date and time for activation and deactivation of a particular segment.</span></span>
- <span data-ttu-id="5a720-133">**Premenovanie** segmentu.</span><span class="sxs-lookup"><span data-stu-id="5a720-133">**Rename** the segment.</span></span>
- <span data-ttu-id="5a720-134">**Stiahnutie** zoznam členov ako súbor .CSV.</span><span class="sxs-lookup"><span data-stu-id="5a720-134">**Download** the list of members as a .CSV file.</span></span>
- <span data-ttu-id="5a720-135">**Spravujte exporty**, ak chcete zobraziť segmenty súvisiace s exportom a spravovať ich.</span><span class="sxs-lookup"><span data-stu-id="5a720-135">**Manage exports** to see exports related segment and manage them.</span></span> [<span data-ttu-id="5a720-136">Ďalšie informácie o exportoch.</span><span class="sxs-lookup"><span data-stu-id="5a720-136">Learn more about exports.</span></span>](export-destinations.md)
- <span data-ttu-id="5a720-137">**Odstránenie** segmentu.</span><span class="sxs-lookup"><span data-stu-id="5a720-137">**Delete** the segment.</span></span>

## <a name="refresh-segments"></a><span data-ttu-id="5a720-138">Obnovenie segmentov</span><span class="sxs-lookup"><span data-stu-id="5a720-138">Refresh segments</span></span>

<span data-ttu-id="5a720-139">Výberom možnosti **Obnoviť všetko** na stránke **Segmenty** môžete obnoviť všetky segmenty naraz alebo môžete jeden alebo viac segmentov, keď ich vyberiete a následne vyberiete **Obnoviť** z možností.</span><span class="sxs-lookup"><span data-stu-id="5a720-139">You can refresh all segments at once by selecting **Refresh all** on the **Segments** page or you can refresh one or multiple segments when you select them and choose **Refresh** in from the options.</span></span> <span data-ttu-id="5a720-140">Prípadne môžete nakonfigurovať opakujúce sa obnovovanie v ponuke **Správca** > **Systém** > **Plán**.</span><span class="sxs-lookup"><span data-stu-id="5a720-140">Alternatively, you can configure a recurring refresh on **Admin** > **System** > **Schedule**.</span></span>

> [!TIP]
> <span data-ttu-id="5a720-141">Existuje [šesť druhov stavov](system.md#status-types) pre úlohy/procesy.</span><span class="sxs-lookup"><span data-stu-id="5a720-141">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="5a720-142">Okrem toho väčšina procesov [závisí na ďalších nadväzujúcich procesoch](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="5a720-142">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="5a720-143">Môžete si vybrať stav procesu a zobraziť podrobnosti o priebehu celej úlohy.</span><span class="sxs-lookup"><span data-stu-id="5a720-143">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="5a720-144">Po výbere **Pozrieť detaily** pre jednu z úloh úlohy nájdete ďalšie informácie: čas spracovania, posledný dátum spracovania a všetky chyby a varovania spojené s úlohou.</span><span class="sxs-lookup"><span data-stu-id="5a720-144">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="export-segments"></a><span data-ttu-id="5a720-145">Segmenty exportu</span><span class="sxs-lookup"><span data-stu-id="5a720-145">Export segments</span></span>

<span data-ttu-id="5a720-146">Segment môžete exportovať zo stránky so segmentmi alebo zo [stránky s exportom](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="5a720-146">You can export a segment from the segments page or the [exports page](export-destinations.md).</span></span> 

1. <span data-ttu-id="5a720-147">Prejdite na stránku **Segmenty**.</span><span class="sxs-lookup"><span data-stu-id="5a720-147">Go to the **Segments** page.</span></span>

1. <span data-ttu-id="5a720-148">Vyberte **Zobraziť viac [...]** pre segment, ktorý chcete exportovať.</span><span class="sxs-lookup"><span data-stu-id="5a720-148">Select **Show more [...]** for the segment you want to export.</span></span>

1. <span data-ttu-id="5a720-149">Z rozbaľovacieho zoznamu akcií si vyberte možnosť **Spravovať exporty**.</span><span class="sxs-lookup"><span data-stu-id="5a720-149">Select **Manage exports** from the actions dropdown list.</span></span>

1. <span data-ttu-id="5a720-150">Otvorí sa stránka **Exporty (verzia Preview) pre segment**.</span><span class="sxs-lookup"><span data-stu-id="5a720-150">The page **Exports (preview) for segment** opens.</span></span> <span data-ttu-id="5a720-151">Všetky nakonfigurované exporty môžete vidieť zoskupené podľa exportov, ktoré obsahujú aktuálny segment alebo ho neobsahujú.</span><span class="sxs-lookup"><span data-stu-id="5a720-151">You can see all configured exports grouped by by exports that contain the current segment or don't contain it.</span></span>

   1. <span data-ttu-id="5a720-152">Ak chcete pridať vybratý segment do exportu, vyberte export v zozname a zvoľte **Pridať segment**.</span><span class="sxs-lookup"><span data-stu-id="5a720-152">To add the selected segment to an export, select the export in the list and select **Add segment**.</span></span>

   1. <span data-ttu-id="5a720-153">Ak chcete vytvoriť nový export s vybraným segmentom, vyberte **Pridať export**.</span><span class="sxs-lookup"><span data-stu-id="5a720-153">To create a new export with the selected segment, select **Add export**.</span></span> <span data-ttu-id="5a720-154">Ďalšie informácie o vytváraní exportu nájdete v článku [Nastavenie nového exportu](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="5a720-154">For more information about creating exports, see [Set up a new export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="5a720-155">Vyberte **Späť** na návrat na hlavnú stránku pre segmenty.</span><span class="sxs-lookup"><span data-stu-id="5a720-155">Select **Back** to return to the main page for segments.</span></span>

## <a name="view-processing-history-and-segment-members"></a><span data-ttu-id="5a720-156">Zobrazenie histórie spracovania a členov segmentu</span><span class="sxs-lookup"><span data-stu-id="5a720-156">View processing history and segment members</span></span>

<span data-ttu-id="5a720-157">Ak chcete zobraziť konsolidované údaje o segmente, prečítajte si podrobnosti.</span><span class="sxs-lookup"><span data-stu-id="5a720-157">You can see consolidated data about a segment by reviewing its details.</span></span>

<span data-ttu-id="5a720-158">Na stránke **Segmenty** vyberte segment, ktorý chcete skontrolovať.</span><span class="sxs-lookup"><span data-stu-id="5a720-158">On the **Segments** page, select the segment you want to review.</span></span>

<span data-ttu-id="5a720-159">Horná časť stránky obsahuje graf trendov, ktorý vizualizuje zmeny v počte členov.</span><span class="sxs-lookup"><span data-stu-id="5a720-159">The upper part of the page includes a trend graph that visualizes changes in member count.</span></span> <span data-ttu-id="5a720-160">Ak umiestnite kurzor myši nad údajové body, zobrazí sa počet členov k určitému dátumu.</span><span class="sxs-lookup"><span data-stu-id="5a720-160">Hover over data points to see the member count on a specific date.</span></span>

<span data-ttu-id="5a720-161">Môžete aktualizovať časový rámec vizualizácie.</span><span class="sxs-lookup"><span data-stu-id="5a720-161">You can update the time frame of the visualization.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="5a720-162">![Časový rozsah segmentu](media/segment-time-range.png "Časový rozsah segmentu")</span><span class="sxs-lookup"><span data-stu-id="5a720-162">![Segment time range](media/segment-time-range.png "Segment time range")</span></span>

<span data-ttu-id="5a720-163">Spodná časť obsahuje zoznam členov segmentu.</span><span class="sxs-lookup"><span data-stu-id="5a720-163">The lower part contains a list of the segment members.</span></span>

> [!NOTE]
> <span data-ttu-id="5a720-164">Polia, ktoré sa nachádzajú v tomto zozname, sú založené na atribútoch entít vášho segmentu.</span><span class="sxs-lookup"><span data-stu-id="5a720-164">Fields that appear in this list are based on the attributes of your segment's entities.</span></span>
>
><span data-ttu-id="5a720-165">Zoznam predstavuje ukážku zodpovedajúcich členov segmentu a zobrazuje prvých 100 záznamov segmentu, aby ste ho mohli rýchlo vyhodnotiť a podľa potreby skontrolovať jeho definície.</span><span class="sxs-lookup"><span data-stu-id="5a720-165">The list is a preview of the matching segment members and shows the first 100 records of your segment so that you can quickly evaluate it and review its definitions if needed.</span></span> <span data-ttu-id="5a720-166">Ak chcete zobraziť všetky zodpovedajúce záznamy, musíte [exportovať segment](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="5a720-166">To see all matching records, you need to [export the segment](export-destinations.md).</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)] 
