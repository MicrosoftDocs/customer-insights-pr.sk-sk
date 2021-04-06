---
title: Prehľady segmentov pre existujúce segmenty
description: Získajte prehľady o existujúcich segmentoch, aby ste videli rozdiely a spoločné črty.
ms.date: 06/10/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 90ebcaab896c628b04e751ad9857e924749895e7
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 03/15/2021
ms.locfileid: "5595353"
---
# <a name="segment-insights-preview"></a><span data-ttu-id="f5f89-103">Prehľady segmentov (ukážka)</span><span class="sxs-lookup"><span data-stu-id="f5f89-103">Segment insights (preview)</span></span>

<span data-ttu-id="f5f89-104">Objavte ďalšie informácie a prehľady o svojich existujúcich segmentoch.</span><span class="sxs-lookup"><span data-stu-id="f5f89-104">Discover additional information and insights around your existing segments.</span></span> <span data-ttu-id="f5f89-105">Zistite, čo odlišuje dva segmenty alebo čo majú spoločné.</span><span class="sxs-lookup"><span data-stu-id="f5f89-105">Find out what differentiates two segments or what they have in common.</span></span>

## <a name="segment-overlap"></a><span data-ttu-id="f5f89-106">Prekrytie segmentu</span><span class="sxs-lookup"><span data-stu-id="f5f89-106">Segment overlap</span></span>

<span data-ttu-id="f5f89-107">Analýza prekrývania segmentov ukazuje, koľkí a ktorí zákazníci sú spoloční pre dva alebo viac segmentov.</span><span class="sxs-lookup"><span data-stu-id="f5f89-107">Segment overlap analysis shows how many and which customers are common to two or more segments.</span></span> <span data-ttu-id="f5f89-108">Napríklad, ako sa segment častých zákazníkov prekrýva so segmentom, ktorý obsahuje zákazníkov, ktorí sú spokojní s vašou službou alebo produktom.</span><span class="sxs-lookup"><span data-stu-id="f5f89-108">For example, how a segment of frequent customers overlaps with a segment that contains customers that are satisfied with your service or product.</span></span>
<span data-ttu-id="f5f89-109">Môžete tiež analyzovať, ako sa prekrývanie mení pre konkrétne atribúty.</span><span class="sxs-lookup"><span data-stu-id="f5f89-109">You can also analyze how the overlap changes for specific attributes.</span></span>

### <a name="run-an-overlap-analysis"></a><span data-ttu-id="f5f89-110">Spustenie analýzy prekrývania</span><span class="sxs-lookup"><span data-stu-id="f5f89-110">Run an overlap analysis</span></span>

1. <span data-ttu-id="f5f89-111">Prejdite na **Segmenty** a vyberte kartu **Štatistiky (ukážka)**.</span><span class="sxs-lookup"><span data-stu-id="f5f89-111">Go to **Segments** and select the **Insights (preview)** tab.</span></span>

1. <span data-ttu-id="f5f89-112">Vyberte **Nový** a vyberte možnosť **Prekrytie** na table **Vyberte typ štatistík**.</span><span class="sxs-lookup"><span data-stu-id="f5f89-112">Select **New** and choose the **Overlap** option in the **Choose Insight Type** pane.</span></span>

1. <span data-ttu-id="f5f89-113">Vyberte segmenty záujmu a zvoľte **Ďalšie**.</span><span class="sxs-lookup"><span data-stu-id="f5f89-113">Choose the segments of interest and select **Next**.</span></span>

1. <span data-ttu-id="f5f89-114">Ak chcete analyzovať prekrytia pre každú možnú hodnotu poľa, vyberte jedno alebo viac polí záujmu a vyberte **Ďalšie**.</span><span class="sxs-lookup"><span data-stu-id="f5f89-114">Optionally, choose one or more fields of interest to analyze overlaps for every possible field value and select **Next**.</span></span>

1. <span data-ttu-id="f5f89-115">Uveďte názov prekrývajúcej sa analýzy, voliteľný zobrazovaný názov a popis.</span><span class="sxs-lookup"><span data-stu-id="f5f89-115">Provide a name for you overlap analysis, an optional display name, and a description.</span></span>

1. <span data-ttu-id="f5f89-116">Vyberte **Uložiť** na spustenie analýzy.</span><span class="sxs-lookup"><span data-stu-id="f5f89-116">Select **Save** to start the analysis.</span></span> <span data-ttu-id="f5f89-117">Analýza prekrývania je pripravená, keď sa stav zmení z Obnovuje sa na Úspešné.</span><span class="sxs-lookup"><span data-stu-id="f5f89-117">The overlap analysis is ready when the status changes from Refreshing to Successful.</span></span>

### <a name="view-and-optimize-an-overlap-analysis"></a><span data-ttu-id="f5f89-118">Zobrazenie a optimalizácia analýzy prekrývania</span><span class="sxs-lookup"><span data-stu-id="f5f89-118">View and optimize an overlap analysis</span></span>

<span data-ttu-id="f5f89-119">Po dokončení analýzy vyhľadajte podrobnosti o tomto prehľade v časti **Segmenty** > **Prehľady (ukážka)**.</span><span class="sxs-lookup"><span data-stu-id="f5f89-119">After completing the analysis, find details on this insight on **Segments** > **Insights (preview)**.</span></span>

> [!div class="mx-imgBorder"]
> :::image type="content" source="media/segment-overlap.png" alt-text="Podrobnosti prehľadu prekrývania segmentov":::

<span data-ttu-id="f5f89-121">Ak chcete zobraziť výsledky analýzy, vyberte prehľad:</span><span class="sxs-lookup"><span data-stu-id="f5f89-121">Select an insight to see the analysis results:</span></span>

- <span data-ttu-id="f5f89-122">Počet členov prekrývajúcich segmenty vybrané na analýzu.</span><span class="sxs-lookup"><span data-stu-id="f5f89-122">The number of members overlapping the segments selected for analysis.</span></span>
- <span data-ttu-id="f5f89-123">Počet členov zahrnutých v jednom zo segmentov, ale nie v ostatných segmentoch.</span><span class="sxs-lookup"><span data-stu-id="f5f89-123">The number of members included in one of the segments but not in the rest of the segments.</span></span>
- <span data-ttu-id="f5f89-124">Ak ste pri konfigurácii analýzy prekrývania vybrali polia, nájdete ich na príslušných kartách.</span><span class="sxs-lookup"><span data-stu-id="f5f89-124">If you selected fields while configuring the overlap analysis, you'll find them in the corresponding tabs.</span></span> <span data-ttu-id="f5f89-125">Pomocou rozbaľovacej ponuky filtra môžete vybrať ľubovoľnú požadovanú úroveň atribútu a tabuľka dole zobrazuje príslušné údaje.</span><span class="sxs-lookup"><span data-stu-id="f5f89-125">You can use the filter drop-down to select any attribute level of interest and the table at the bottom will show the corresponding data.</span></span>

## <a name="segment-differentiators"></a><span data-ttu-id="f5f89-126">Diferenciátory segmentov</span><span class="sxs-lookup"><span data-stu-id="f5f89-126">Segment differentiators</span></span>

<span data-ttu-id="f5f89-127">Diferenciátory segmentov vám pomôžu zistiť, čo odlišuje segment od ostatných zákazníkov alebo od iného segmentu.</span><span class="sxs-lookup"><span data-stu-id="f5f89-127">Segment differentiators help you find out what differentiates a segment from the rest of your customers or from another segment.</span></span> <span data-ttu-id="f5f89-128">Musíte iba vybrať segment a systém identifikuje atribúty profilu a miery, ktoré odlišujú vybraný segment.</span><span class="sxs-lookup"><span data-stu-id="f5f89-128">You just have to select a segment and the system will identify profile attributes and measures that distinguish the selected segment.</span></span>

### <a name="run-a-differentiator-analysis"></a><span data-ttu-id="f5f89-129">Spustenie analýzy diferenciátora</span><span class="sxs-lookup"><span data-stu-id="f5f89-129">Run a differentiator analysis</span></span>

1. <span data-ttu-id="f5f89-130">Prejdite na **Segmenty** a vyberte kartu **Štatistiky (ukážka)**.</span><span class="sxs-lookup"><span data-stu-id="f5f89-130">Go to **Segments** and select the **Insights (preview)** tab.</span></span>

1. <span data-ttu-id="f5f89-131">Vyberte **Nový** a vyberte možnosť **Prekrytie** na table **Vyberte typ štatistík**.</span><span class="sxs-lookup"><span data-stu-id="f5f89-131">Select **New** and choose the **Overlap** option in the **Choose Insight Type** pane.</span></span>

1. <span data-ttu-id="f5f89-132">Vyberte segment, ktorý chcete analyzovať ako **Primárny segment** a vyberte **Ďalšie**.</span><span class="sxs-lookup"><span data-stu-id="f5f89-132">Choose the segment you want to analyze as **Primary segment** and select **Next**.</span></span>

1. <span data-ttu-id="f5f89-133">Vyberte **Všetci zákazníci** alebo **Sekundárny segment** na porovnanie vášho primárneho segmentu a vyberte **Ďalšie**.</span><span class="sxs-lookup"><span data-stu-id="f5f89-133">Choose **All customers** or a **Secondary segment** to compare your primary segment with and select **Next**.</span></span>

1. <span data-ttu-id="f5f89-134">Prípadne vyberte jednu alebo viac oblastí záujmu, aby sa analýza zamerala na konkrétne atribúty, a vyberte **Ďalšie**.</span><span class="sxs-lookup"><span data-stu-id="f5f89-134">Optionally, choose one or more fields of interest to focus the analysis on specific attributes and select **Next**.</span></span>

1. <span data-ttu-id="f5f89-135">Uveďte názov prekrývajúcej sa analýzy, voliteľný zobrazovaný názov a popis.</span><span class="sxs-lookup"><span data-stu-id="f5f89-135">Provide a name for you overlap analysis, an optional display name, and a description.</span></span>

1. <span data-ttu-id="f5f89-136">Vyberte **Uložiť** na spustenie analýzy.</span><span class="sxs-lookup"><span data-stu-id="f5f89-136">Select **Save** to start the analysis.</span></span> <span data-ttu-id="f5f89-137">Analýza prekrývania je pripravená, keď sa stav zmení z Obnovuje sa na Úspešné.</span><span class="sxs-lookup"><span data-stu-id="f5f89-137">The overlap analysis is ready when the status changes from Refreshing to Successful.</span></span>

### <a name="view-and-optimize-a-differentiators-analysis"></a><span data-ttu-id="f5f89-138">Prezrite si a optimalizujte analýzu diferenciátorov</span><span class="sxs-lookup"><span data-stu-id="f5f89-138">View and optimize a differentiators analysis</span></span>

<span data-ttu-id="f5f89-139">Po dokončení analýzy vyhľadajte podrobnosti o tomto prehľade v časti **Segmenty** > **Prehľady (ukážka)**.</span><span class="sxs-lookup"><span data-stu-id="f5f89-139">After completing the analysis, find details on this insight on **Segments** > **Insights (preview)**.</span></span>

> [!div class="mx-imgBorder"]
> :::image type="content" source="media/segment-differentiators.png" alt-text="Podrobnosti prehľadu diferenciátora segmentov":::

<span data-ttu-id="f5f89-141">Ak chcete zobraziť výsledky analýzy, vyberte prehľad.</span><span class="sxs-lookup"><span data-stu-id="f5f89-141">Select an insight to see the analysis results.</span></span> <span data-ttu-id="f5f89-142">Analýza diferenciátora obsahuje dve karty.</span><span class="sxs-lookup"><span data-stu-id="f5f89-142">A differentiator analysis includes two tabs.</span></span> <span data-ttu-id="f5f89-143">Karta **Atribúty** uvádza atribúty profilu, ktoré sa považujú za diferenciátory.</span><span class="sxs-lookup"><span data-stu-id="f5f89-143">The **Attributes** tab lists profile attributes considered as differentiators.</span></span> <span data-ttu-id="f5f89-144">Karta **Miery** zobrazuje diferenciátory.</span><span class="sxs-lookup"><span data-stu-id="f5f89-144">The **Measures** tab lists differentiators.</span></span> <span data-ttu-id="f5f89-145">Každá karta obsahuje nasledujúce podrobnosti:</span><span class="sxs-lookup"><span data-stu-id="f5f89-145">Each tab includes the following details:</span></span>

- <span data-ttu-id="f5f89-146">Hodnotený zoznam diferenciátorov zoradený podľa skóre rozdielu.</span><span class="sxs-lookup"><span data-stu-id="f5f89-146">Ranked list of differentiators, sorted by difference score.</span></span>
- <span data-ttu-id="f5f89-147">**Skóre rozdielu** pre každého diferenciátora.</span><span class="sxs-lookup"><span data-stu-id="f5f89-147">The **Difference score** for each differentiator.</span></span> <span data-ttu-id="f5f89-148">Skóre rozdielu predstavuje stupeň rozdielu atribútu medzi dvoma segmentmi.</span><span class="sxs-lookup"><span data-stu-id="f5f89-148">The difference score represents the degree of difference of an attribute between two segments.</span></span> <span data-ttu-id="f5f89-149">Čím vyššie je skóre rozdielu, tým viac atribútov sa medzi týmito dvoma segmentmi líši.</span><span class="sxs-lookup"><span data-stu-id="f5f89-149">The higher the difference score, the more the attributes differ between the two segments.</span></span> <span data-ttu-id="f5f89-150">Vyberte skóre, a otvorte tablu **Skóre rozdielu** s rozdelením hodnôt pre tento atribút.</span><span class="sxs-lookup"><span data-stu-id="f5f89-150">Select a score to open the **Difference score** pane with the distributions of values for that attribute.</span></span>

## <a name="manage-segment-insights"></a><span data-ttu-id="f5f89-151">Spravovanie prehľadov o segmentoch</span><span class="sxs-lookup"><span data-stu-id="f5f89-151">Manage segment insights</span></span>

<span data-ttu-id="f5f89-152">V štatistikách na paneli príkazov môžete použiť nasledujúce možnosti:</span><span class="sxs-lookup"><span data-stu-id="f5f89-152">You can use the following options on your insights from the command bar:</span></span>

- <span data-ttu-id="f5f89-153">**Späť** na vrátenie zoznamu prehľadov</span><span class="sxs-lookup"><span data-stu-id="f5f89-153">**Back** to return the list of insights</span></span>
- <span data-ttu-id="f5f89-154">**Obnoviť** na opätovné spustenie analýzy</span><span class="sxs-lookup"><span data-stu-id="f5f89-154">**Refresh** to run the analysis again</span></span>
- <span data-ttu-id="f5f89-155">**Odstrániť** na odstránenie prehľadu</span><span class="sxs-lookup"><span data-stu-id="f5f89-155">**Delete** to remove this insight</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]