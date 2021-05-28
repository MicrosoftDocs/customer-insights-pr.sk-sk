---
title: Segmenty navrhované na základe aktivity.
description: Nechajte strojové učenie pomôcť vám nájsť nové a zaujímavé segmenty založené na aktivite zákazníkov.
ms.date: 05/11/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
manager: shellyha
ms.openlocfilehash: 14d9d4f0df6b5835f21fb63447d05853ee98a757
ms.sourcegitcommit: 8341fa964365c185b65bc4b71fc0c695ea127dc0
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 05/14/2021
ms.locfileid: "6034113"
---
# <a name="suggested-segments-based-on-activity-data-preview"></a><span data-ttu-id="ee943-103">Segmenty navrhované na základe údajov aktivity (verzia Preview).</span><span class="sxs-lookup"><span data-stu-id="ee943-103">Suggested segments based on activity data (preview)</span></span>

<span data-ttu-id="ee943-104">Objavte zaujímavé segmenty svojich zákazníkov na základe údajov o aktivite zákazníkov, ktoré sú prijaté do služby Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="ee943-104">Discover interesting segments of your customers based on customer activity data that is ingested to Customer Insights.</span></span> <span data-ttu-id="ee943-105">Príkladom údajov o činnosti sú transakcie, doba trvania hovoru, nákupy alebo vrátenia.</span><span class="sxs-lookup"><span data-stu-id="ee943-105">Examples of activity data are transactions, support call duration, purchases, or returns.</span></span> <span data-ttu-id="ee943-106">Pri navrhovaní segmentov sa údaje o činnosti analyzujú v oblasti aktuálnosti, frekvencie a peňažnej hodnoty (alebo trvania).</span><span class="sxs-lookup"><span data-stu-id="ee943-106">To suggest segments, activity data gets analyzed for recency, frequency, and monetary value (or duration).</span></span> <span data-ttu-id="ee943-107">Prípadne môžete vygenerovať [navrhované segmenty na zlepšenie miery alebo lepšie pochopenie toho, čo ovplyvňuje atribút](suggested-segments.md).</span><span class="sxs-lookup"><span data-stu-id="ee943-107">Alternatively, you can generate [suggested segments to improve a measure or better understand what influences an attribute](suggested-segments.md).</span></span>

:::image type="content" source="media/suggested-segments-tab.png" alt-text="Karta Navrhované segmenty, ktorá zobrazuje návrhy segmentov pre segmenty založené na aktivite a atribúte.":::

## <a name="categorize-customers-by-activity"></a><span data-ttu-id="ee943-109">Kategorizujte zákazníkov podľa aktivity</span><span class="sxs-lookup"><span data-stu-id="ee943-109">Categorize customers by activity</span></span>

<span data-ttu-id="ee943-110">S [údajmi o aktivite](activities.md) dostupnými v Customer Insights, môžeme generovať návrhy, ktoré zastupujú skupiny zákazníkov:</span><span class="sxs-lookup"><span data-stu-id="ee943-110">With [activity data](activities.md) available in Customer Insights, we can generate suggestions that represent customer groups:</span></span>

- <span data-ttu-id="ee943-111">najaktívnejší zákazníci</span><span class="sxs-lookup"><span data-stu-id="ee943-111">most active customers</span></span> 
- <span data-ttu-id="ee943-112">zákazníci, ktorí uskutočnili najviac nákupov</span><span class="sxs-lookup"><span data-stu-id="ee943-112">customers that have made the most purchases</span></span> 
- <span data-ttu-id="ee943-113">zákazníci, ktorí dosiahli najväčší príjem</span><span class="sxs-lookup"><span data-stu-id="ee943-113">customers that generated the most revenue</span></span> 
- <span data-ttu-id="ee943-114">zákazníci, ktorí v poslednej dobe neboli aktívni</span><span class="sxs-lookup"><span data-stu-id="ee943-114">customers who haven’t been active lately</span></span> 
- <span data-ttu-id="ee943-115">zákazníci, ktorí často interagujú s vašou firmou</span><span class="sxs-lookup"><span data-stu-id="ee943-115">customers who frequently interact with your business</span></span>  

<span data-ttu-id="ee943-116">Ak podnikáte v maloobchode, môžete zistiť, ktorí zákazníci vygenerovali najväčší obrat, a odmeniť ich kupónom.</span><span class="sxs-lookup"><span data-stu-id="ee943-116">If you have a retail business, you could find out which customers generate the most revenue and reward them with a coupon.</span></span> <span data-ttu-id="ee943-117">Alebo môžete identifikovať príležitostných zákazníkov a ponúknuť im účasť v programe odmien, aby navštevovali vašu firmu častejšie.</span><span class="sxs-lookup"><span data-stu-id="ee943-117">Or you can identify occasional customers and offer them to join a rewards program so they visit your business more often.</span></span>
<span data-ttu-id="ee943-118">Ak podnikáte v zdravotníctve a poskytujete verejnú zdravotnú starostlivosť, vaším cieľom je minimalizovať náklady na jednotlivých pacientov.</span><span class="sxs-lookup"><span data-stu-id="ee943-118">If you're in the healthcare business providing public healthcare and your goal is to minimize the expenses for individual patients.</span></span> <span data-ttu-id="ee943-119">Spôsobom, ako to urobiť, môže byť zníženie opakujúcich sa návštev poskytovaním najlepšej možnej starostlivosti pri čo najmenšom počte návštev.</span><span class="sxs-lookup"><span data-stu-id="ee943-119">A way to do so could be to reduce recurring visits by providing best possible care in as few visits as possible.</span></span> <span data-ttu-id="ee943-120">V takom prípade je vaším cieľom udržiavať nízku frekvenciu návštev a minimalizovať opakujúce sa náklady na pacientov.</span><span class="sxs-lookup"><span data-stu-id="ee943-120">In this case, your goal is to keep the visit frequency low and minimize recurring cost for the patients.</span></span> <span data-ttu-id="ee943-121">Alebo môžete identifikovať segmenty pacientov, ktorí majú časté plánované činnosti a vysoké opakujúce sa náklady, a analyzovať tieto prípady s cieľom zlepšiť liečbu jednotlivca.</span><span class="sxs-lookup"><span data-stu-id="ee943-121">Or you can identify segments of patients who have frequent appointments and high recurring costs and analyze these cases to improve the treatment of the individual.</span></span> 

## <a name="required-data"></a><span data-ttu-id="ee943-122">Požadované údaje</span><span class="sxs-lookup"><span data-stu-id="ee943-122">Required data</span></span>

<span data-ttu-id="ee943-123">Návrhy sa generujú na základe vybratých vstupných údajov.</span><span class="sxs-lookup"><span data-stu-id="ee943-123">Suggestions are generated based on the selected input data.</span></span> 

- <span data-ttu-id="ee943-124">Profily zákazníkov: Všetci zákazníci alebo členovia konkrétneho segmentu.</span><span class="sxs-lookup"><span data-stu-id="ee943-124">Customer profiles: All customers or members of a specific segment.</span></span> 

- <span data-ttu-id="ee943-125">Časové obdobie: minulý mesiac, minulý rok alebo ľubovoľný vlastný časový rámec.</span><span class="sxs-lookup"><span data-stu-id="ee943-125">Time period: Last month, last year, or any custom time frame.</span></span>

- <span data-ttu-id="ee943-126">Typ aktivity: nákupy, maloobchodné transakcie, online transakcie, prípady podpory zákazníkov, predplatné atď.</span><span class="sxs-lookup"><span data-stu-id="ee943-126">Activity type: purchases, retail transactions, online transactions, customer support cases, subscriptions, and so on.</span></span>  

- <span data-ttu-id="ee943-127">Entita v Customer Insights, ktorá obsahuje údaje o aktivite: entita UnifiedActivity alebo entita pre konkrétnu aktivitu.</span><span class="sxs-lookup"><span data-stu-id="ee943-127">Entity in Customer Insights that contains the activity data: The UnifiedActivity entity or the entity for a specific activity.</span></span> 

- <span data-ttu-id="ee943-128">Zahrnuté dimenzie: Aktuálnosť, frekvencia alebo peňažná dimenzia v závislosti od vašich obchodných požiadaviek.</span><span class="sxs-lookup"><span data-stu-id="ee943-128">Dimensions to include: Recency, frequency, or monetary dimension, depending on your business requirements.</span></span>

## <a name="generate-suggested-segments"></a><span data-ttu-id="ee943-129">Generovanie navrhovaných segmentov</span><span class="sxs-lookup"><span data-stu-id="ee943-129">Generate suggested segments</span></span>

1. <span data-ttu-id="ee943-130">Prejdite na **Segmenty**.</span><span class="sxs-lookup"><span data-stu-id="ee943-130">Go to **Segments**.</span></span>

1. <span data-ttu-id="ee943-131">Vyberte kartu **Návrhy (ukážka)**.</span><span class="sxs-lookup"><span data-stu-id="ee943-131">Select the **Suggestions (preview)** tab.</span></span>

1. <span data-ttu-id="ee943-132">Stlačte možnosť **Vyhľadanie nových návrhov** a stlačte **Zobrazenie alebo predvídanie správania zákazníkov**.</span><span class="sxs-lookup"><span data-stu-id="ee943-132">Select **Find new suggestions** and choose **See or anticipate customer behavior**.</span></span> <span data-ttu-id="ee943-133">Stlačte **Spustiť** na spustenie riadenej používateľskej skúsenosti.</span><span class="sxs-lookup"><span data-stu-id="ee943-133">Select **Start** to run the guided experience.</span></span>

   :::image type="content" source="media/suggested-segments-activity-wizard.png" alt-text="Prvý krok sprievodcu konfiguráciou pre navrhovaný segment na základe aktivity.":::

1. <span data-ttu-id="ee943-135">Zadajte požadované vstupné údaje a pokračujte stlačením možnosti **Ďalej**.</span><span class="sxs-lookup"><span data-stu-id="ee943-135">Provide the required input data and select **Next** proceed.</span></span>

   - <span data-ttu-id="ee943-136">Vyberte zákazníkov: Zahrňte všetkých zákazníkov alebo konkrétny segment.</span><span class="sxs-lookup"><span data-stu-id="ee943-136">Choose customers: Include all customers or a specific segment.</span></span>
   - <span data-ttu-id="ee943-137">Vyberte aktivitu: Vyberte typ aktivity a entity, ktoré aktivitu popisujú.</span><span class="sxs-lookup"><span data-stu-id="ee943-137">Choose activity: Select the activity type and the entities that describe the activity.</span></span>
   - <span data-ttu-id="ee943-138">Predvoľby: Nastavte časové obdobie, ktoré je potrebné vziať do úvahy, faktory pre návrhy a mapujte atribúty.</span><span class="sxs-lookup"><span data-stu-id="ee943-138">Preferences: Set the time period to consider, the factors for suggestions, and map the attributes.</span></span>

1. <span data-ttu-id="ee943-139">Skontrolujte svoje zadanie a stlačte možnosť **Spustiť** na spustenie modelu a generácie návrhov.</span><span class="sxs-lookup"><span data-stu-id="ee943-139">Review your input and select **Run** to run the model and generate suggestions.</span></span>

1. <span data-ttu-id="ee943-140">V závislosti od počtu profilov zákazníkov a vybraných aktivít môže dokončenie trvať niekoľko minút.</span><span class="sxs-lookup"><span data-stu-id="ee943-140">Depending on the number of customer profiles and selected activities, it can take a few minutes to complete.</span></span> 

<span data-ttu-id="ee943-141">Po vygenerovaní návrhov ich môžete filtrovať podľa dimenzie alebo hodnoty, ktorá vás zaujíma najviac.</span><span class="sxs-lookup"><span data-stu-id="ee943-141">After generating the suggestions, you can filter them by the dimension or value you're most interested in.</span></span> 

## <a name="view-details-of-a-suggested-segment"></a><span data-ttu-id="ee943-142">Zobrazenie podrobností o navrhovanom segmente</span><span class="sxs-lookup"><span data-stu-id="ee943-142">View details of a suggested segment</span></span>

<span data-ttu-id="ee943-143">Po vygenerovaní návrhov ich nájdete na zozname **Segmenty** > **Návrhy (verzia Preview)** v časti **Návrhy založené na aktivite**.</span><span class="sxs-lookup"><span data-stu-id="ee943-143">Once the suggestions are generated, you'll find them listed on **Segments** > **Suggestions (preview)** in the **Activity-based suggestions** section.</span></span>

:::image type="content" source="media/suggested-segments-details.png" alt-text="Rozšírená bočná tabla zobrazujúca podrobné údaje o navrhovanom segmente.":::

<span data-ttu-id="ee943-145">Stlačte možnosť **Zobraziť návrh** na navrhovanom segmente pre zobrazenie podrobností o danom segmente.</span><span class="sxs-lookup"><span data-stu-id="ee943-145">Select **See suggestion** on a suggested segment to view the details of that segment.</span></span> <span data-ttu-id="ee943-146">Bočná tabla poskytuje podrobnosti, ako je rozsah každej dimenzie v porovnaní s cieľovou skupinou.</span><span class="sxs-lookup"><span data-stu-id="ee943-146">The side pane provides details like the extent of each dimension in comparison to the target group.</span></span> <span data-ttu-id="ee943-147">Zdôrazňuje tiež počet potenciálnych členov v segmente a zodpovedajúce percento z celkového počtu zákazníkov.</span><span class="sxs-lookup"><span data-stu-id="ee943-147">It also highlights the number of potential members in the segment and the corresponding percentage of the total customers.</span></span> <span data-ttu-id="ee943-148">Ak si chcete ponechať návrh ako segment, stlačte možnosť **Vytvoriť segment**.</span><span class="sxs-lookup"><span data-stu-id="ee943-148">If you want to keep the suggestion as a segment, select **Create segment**.</span></span>    

## <a name="save-a-suggestion-as-a-segment"></a><span data-ttu-id="ee943-149">Uloženie návrhu ako segmentu</span><span class="sxs-lookup"><span data-stu-id="ee943-149">Save a suggestion as a segment</span></span>

1. <span data-ttu-id="ee943-150">Prejdite na **Segmenty** > **Návrhy (ukážka)**.</span><span class="sxs-lookup"><span data-stu-id="ee943-150">Go to **Segments** > **Suggestions (preview)**.</span></span>

1. <span data-ttu-id="ee943-151">Vyberte segment, ktorý chcete uložiť.</span><span class="sxs-lookup"><span data-stu-id="ee943-151">Select the segment you want to save.</span></span> 

1. <span data-ttu-id="ee943-152">Na bočnom paneli stlačte možnosť **Vytvoriť segment**.</span><span class="sxs-lookup"><span data-stu-id="ee943-152">In the side pane, select **Create segment**.</span></span> 

1. <span data-ttu-id="ee943-153">Po uložení sa segment zobrazí v zozname segmentov na karte **Všetky segmenty**. Teraz ho možno [ obnoviť alebo odstrániť ako každý iný segment](segments.md).</span><span class="sxs-lookup"><span data-stu-id="ee943-153">After saving the segment, it will show in the list of segments on the **All segments** tab. It can now be [refreshed or deleted like any other segment](segments.md).</span></span> <span data-ttu-id="ee943-154">Nemôžete upraviť podrobnosti segmentu.</span><span class="sxs-lookup"><span data-stu-id="ee943-154">You can't edit the segment details.</span></span> <span data-ttu-id="ee943-155">Môžete však zmeniť vstupné kritériá pre návrhy a vygenerovať rôzne návrhy.</span><span class="sxs-lookup"><span data-stu-id="ee943-155">However, you can change the input criteria for the suggestions and generate different suggestions.</span></span>

## <a name="refresh-or-edit-a-set-of-suggestions"></a><span data-ttu-id="ee943-156">Obnovenie alebo úprava skupiny návrhov</span><span class="sxs-lookup"><span data-stu-id="ee943-156">Refresh or edit a set of suggestions</span></span>

1. <span data-ttu-id="ee943-157">Prejdite do **Segmenty** > **Návrhy (verzia Preview)** a vyhľadajte segment v sekcii **Návrhy založené na aktivite**.</span><span class="sxs-lookup"><span data-stu-id="ee943-157">Go to **Segments** > **Suggestions (preview)** and look for the segment in the **Activity-based suggestions** section.</span></span>

1. <span data-ttu-id="ee943-158">Vyberte **Obnoviť návrhy** na obnovenie návrhov pri zachovaní nakonfigurovaných atribútov.</span><span class="sxs-lookup"><span data-stu-id="ee943-158">Select **Refresh suggestions** to refresh the suggestions while keeping configured attributes.</span></span> <span data-ttu-id="ee943-159">Alebo stlačte možnosť **Upraviť návrhy** a upravte nakonfigurované atribúty.</span><span class="sxs-lookup"><span data-stu-id="ee943-159">Or select **Edit suggestions** to modify the configured attributes.</span></span> <span data-ttu-id="ee943-160">Systém znova spustí proces, vygeneruje návrhy segmentov na základe najnovších údajov a nahradí súčasné návrhy.</span><span class="sxs-lookup"><span data-stu-id="ee943-160">The system will rerun the process, generate segment suggestions based on the latest data, and replace the current suggestions.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
