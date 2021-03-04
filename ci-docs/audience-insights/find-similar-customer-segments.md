---
title: Nájsť podobných zákazníkov pomocou AI
description: Nájdite podobné zákaznícke segmenty pomocou umelej inteligencie.
ms.date: 06/25/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: jimsonc
manager: shellyha
ms.openlocfilehash: b9b2e7fa862b595c6a364a7208e42295b4f9df83
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268889"
---
# <a name="similar-customers-preview"></a><span data-ttu-id="5b6db-103">Podobní zákazníci (ukážka)</span><span class="sxs-lookup"><span data-stu-id="5b6db-103">Similar Customers (preview)</span></span>

<span data-ttu-id="5b6db-104">Táto funkcia vám umožní nájsť podobných zákazníkov vo vašej zákazníckej základni pomocou umelej inteligencie.</span><span class="sxs-lookup"><span data-stu-id="5b6db-104">This feature lets you find similar customers in your customer base using artificial intelligence.</span></span> <span data-ttu-id="5b6db-105">Aby ste mohli používať túto funkciu, musíte mať aspoň jeden segment.</span><span class="sxs-lookup"><span data-stu-id="5b6db-105">You need to have at least one segment created to use this feature.</span></span> <span data-ttu-id="5b6db-106">Rozšírenie kritérií existujúceho segmentu pomôže nájsť zákazníkov, ktorí sú podobní tomuto segmentu.</span><span class="sxs-lookup"><span data-stu-id="5b6db-106">Expanding the criteria of an existing segment help find customers that are similar to that segment.</span></span>

> [!NOTE]
> <span data-ttu-id="5b6db-107">*Nájdite podobných zákazníkov* využíva automatizované prostriedky na vyhodnotenie údajov a vypracovanie predpovedí na základe týchto údajov, a preto má schopnosť použitia ako metódy profilovania, pretože tento pojem je vymedzený vo všeobecnom nariadení o ochrane údajov („GDPR“).</span><span class="sxs-lookup"><span data-stu-id="5b6db-107">*Find similar customers* uses automated means to evaluate data and make predictions based on that data, and therefore has the capability to be used as a method of profiling, as that term is defined by the General Data Protection Regulation (“GDPR”).</span></span> <span data-ttu-id="5b6db-108">Použitie tejto funkcie zákazníkom na spracovanie údajov môže podliehať GDPR alebo iným zákonom alebo predpisom.</span><span class="sxs-lookup"><span data-stu-id="5b6db-108">Customer’s use of this feature to process data may be subject to GDPR or other laws or regulations.</span></span> <span data-ttu-id="5b6db-109">Ste zodpovední za zabezpečenie toho, že vaše používanie služby Dynamics 365 Customer Insights vrátane predikcií bude v súlade so všetkými platnými zákonmi a nariadeniami vrátane zákonov týkajúcich sa ochrany súkromia, osobných údajov, biometrických údajov, ochrany údajov a dôvernosti komunikácií.</span><span class="sxs-lookup"><span data-stu-id="5b6db-109">You are responsible for ensuring that your use of Dynamics 365 Customer Insights, including predictions, complies with all applicable laws and regulations, including laws related to privacy, personal data, biometric data, data protection, and confidentiality of communications.</span></span>

## <a name="finding-similar-customers"></a><span data-ttu-id="5b6db-110">Hľadanie podobných zákazníkov</span><span class="sxs-lookup"><span data-stu-id="5b6db-110">Finding similar customers</span></span>

1. <span data-ttu-id="5b6db-111">V prehľadoch cieľových skupín prejdite na **Segmenty** a vyberte segment, na ktorom chcete založiť svoj nový segment.</span><span class="sxs-lookup"><span data-stu-id="5b6db-111">In audience insights, go to **Segments** and select the segment you want to base your new segment on.</span></span> <span data-ttu-id="5b6db-112">Toto je váš *zdrojový segment*.</span><span class="sxs-lookup"><span data-stu-id="5b6db-112">That's your *source segment*.</span></span>

1. <span data-ttu-id="5b6db-113">Na paneli akcií vyberte položku **Vyhľadanie podobných zákazníkov**.</span><span class="sxs-lookup"><span data-stu-id="5b6db-113">In the action bar, select **Find similar customers**.</span></span>

1. <span data-ttu-id="5b6db-114">Skontrolujte navrhovaný názov nového segmentu a v prípade potreby ho zmeňte.</span><span class="sxs-lookup"><span data-stu-id="5b6db-114">Review the suggested name for your new segment and change it if necessary.</span></span>

1. <span data-ttu-id="5b6db-115">Skontrolujte polia, ktoré definujú váš nový segment.</span><span class="sxs-lookup"><span data-stu-id="5b6db-115">Review the fields that define your new segment.</span></span> <span data-ttu-id="5b6db-116">Tieto polia definujú základ, na ktorom sa systém pokúsi nájsť podobných zákazníkov ako váš zdrojový segment.</span><span class="sxs-lookup"><span data-stu-id="5b6db-116">These fields define the basis on which the system will try to find similar customers to your source segment.</span></span> <span data-ttu-id="5b6db-117">Systém predvolene vyberie odporúčané polia.</span><span class="sxs-lookup"><span data-stu-id="5b6db-117">The system will select recommended fields by default.</span></span>
  <span data-ttu-id="5b6db-118">Polia, ktoré môžu výrazne znížiť výkon modelu, sú automaticky vylúčené:</span><span class="sxs-lookup"><span data-stu-id="5b6db-118">Fields that can significantly reduce the model performance are automatically excluded:</span></span>
  
   - <span data-ttu-id="5b6db-119">Polia s nasledujúcimi typmi údajov: StringType, BooleanType, CharType, LongType, IntType, DoubleType, FloatType, ShortType</span><span class="sxs-lookup"><span data-stu-id="5b6db-119">Fields with the following data types: StringType, BooleanType, CharType, LongType, IntType, DoubleType, FloatType, ShortType</span></span>
   - <span data-ttu-id="5b6db-120">Polia s mohutnosťou (počet prvkov v poli) menšie ako 2 alebo viac ako 30</span><span class="sxs-lookup"><span data-stu-id="5b6db-120">Fields with a cardinality (the number of elements in a field) of less than 2 or more than 30</span></span>

1. <span data-ttu-id="5b6db-121">Vyberte, či chcete zahrnúť **Všetkých zákazníkov** alebo iba zákazníci v **Špecifickom existujúcom segmente** vo vašom novom segmente.</span><span class="sxs-lookup"><span data-stu-id="5b6db-121">Choose if you want to include **All customers** or only customers in a **Specific existing segment** in your new segment.</span></span>

1. <span data-ttu-id="5b6db-122">Vylúčte zákazníkov z vášho zdrojového segmentu výberom začiarkavacieho poľa **Vylúčiť všetkých v zdrojovom segmente**.</span><span class="sxs-lookup"><span data-stu-id="5b6db-122">Exclude customers in your source segment by selecting the **Exclude everyone in source segment** checkbox.</span></span>

1. <span data-ttu-id="5b6db-123">Systém predvolene navrhuje zahrnúť do výstupu iba 20 % cieľovej veľkosti publika.</span><span class="sxs-lookup"><span data-stu-id="5b6db-123">By default, the system suggests including only 20% of the target audience size in your output.</span></span> <span data-ttu-id="5b6db-124">Upravte tento prah podľa potreby.</span><span class="sxs-lookup"><span data-stu-id="5b6db-124">Edit this threshold as needed.</span></span> <span data-ttu-id="5b6db-125">Zvýšenie prahu zníži presnosť.</span><span class="sxs-lookup"><span data-stu-id="5b6db-125">Increasing the threshold will reduce the precision.</span></span>

1. <span data-ttu-id="5b6db-126">Vyberte **Spustiť** v dolnej časti stránky na spustenie úlohy binárnej klasifikácie (metóda strojového učenia), ktorá analyzuje množinu údajov.</span><span class="sxs-lookup"><span data-stu-id="5b6db-126">Select **Run** at the bottom of the page to start a binary classification task (a method of machine learning) which analyzes the dataset.</span></span>

## <a name="view-the-similar-segment"></a><span data-ttu-id="5b6db-127">Zobraziť podobný segment</span><span class="sxs-lookup"><span data-stu-id="5b6db-127">View the similar segment</span></span>

<span data-ttu-id="5b6db-128">Po spracovaní podobného segmentu nájdete nový segment uvedený na stránke **Segmenty**.</span><span class="sxs-lookup"><span data-stu-id="5b6db-128">After processing the similar segment, you'll find the new segment listed on the **Segments** page.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="5b6db-129">![Segment podobných zákazníkov](media/expanded-segment.png "Segment podobných zákazníkov")</span><span class="sxs-lookup"><span data-stu-id="5b6db-129">![Similar customers segment](media/expanded-segment.png "Similar customers segment")</span></span>

<span data-ttu-id="5b6db-130">Vyberte **Zobraziť** na paneli akcií na otvorenie podrobností o segmente.</span><span class="sxs-lookup"><span data-stu-id="5b6db-130">Select **View** in the action bar to open the segment detail.</span></span> <span data-ttu-id="5b6db-131">Toto zobrazenie obsahuje informácie o distribúcii výsledkov naprieč [skóre podobnosti](#about-similarity-scores).</span><span class="sxs-lookup"><span data-stu-id="5b6db-131">This view contains information about the result distribution across [similarity scores](#about-similarity-scores).</span></span> <span data-ttu-id="5b6db-132">Hodnoty skóre podobnosti nájdete aj v **Ukážke členov segmentu**.</span><span class="sxs-lookup"><span data-stu-id="5b6db-132">You'll also find the similarity score values in the **Segment members preview**.</span></span>

## <a name="use-the-output-of-a-similar-segment"></a><span data-ttu-id="5b6db-133">Použite výstup podobného segmentu</span><span class="sxs-lookup"><span data-stu-id="5b6db-133">Use the output of a similar segment</span></span>

<span data-ttu-id="5b6db-134">Môžete [pracovať s výstupom podobného segmentu](segments.md) rovnako ako v prípade iných segmentov.</span><span class="sxs-lookup"><span data-stu-id="5b6db-134">You can [work with the output of a similar segment](segments.md) as you do with other segments.</span></span> <span data-ttu-id="5b6db-135">Napríklad exportujte segment alebo vytvorte mieru.</span><span class="sxs-lookup"><span data-stu-id="5b6db-135">For example, export the segment or build a measure.</span></span>

## <a name="refresh-and-edit-a-similar-segment"></a><span data-ttu-id="5b6db-136">Obnovte a upravte podobný segment</span><span class="sxs-lookup"><span data-stu-id="5b6db-136">Refresh and edit a similar segment</span></span>

<span data-ttu-id="5b6db-137">Ak chcete obnoviť podobný segment, vyberte ho na stránke **Segmenty** a vyberte **Obnoviť** na paneli akcií.</span><span class="sxs-lookup"><span data-stu-id="5b6db-137">To refresh a similar segment, select it on the **Segments** page and select **Refresh** in the action bar.</span></span>

<span data-ttu-id="5b6db-138">Úpravou podobného segmentu sa znova spracujú vaše údaje.</span><span class="sxs-lookup"><span data-stu-id="5b6db-138">Editing a similar segment will reprocess your data.</span></span> <span data-ttu-id="5b6db-139">Predtým vytvorený segment sa aktualizuje aktualizovanými údajmi.</span><span class="sxs-lookup"><span data-stu-id="5b6db-139">The previously created segment gets updated with refreshed data.</span></span>    
<span data-ttu-id="5b6db-140">Ak chcete upraviť podobný segment, vyberte ho na stránke **Segmenty** a vyberte **Upraviť** na paneli akcií.</span><span class="sxs-lookup"><span data-stu-id="5b6db-140">To edit a similar segment, select it on the **Segments** page and select **Edit** in the action bar.</span></span> <span data-ttu-id="5b6db-141">Vykonajte zmeny a vyberte položku **Spustiť** na spustenie spracovania.</span><span class="sxs-lookup"><span data-stu-id="5b6db-141">Apply your changes and select **Run** to start the processing.</span></span>

## <a name="delete-a-similar-segment"></a><span data-ttu-id="5b6db-142">Odstráňte podobný segment</span><span class="sxs-lookup"><span data-stu-id="5b6db-142">Delete a similar segment</span></span>

<span data-ttu-id="5b6db-143">Vyberte segment na stránke **Segmenty** a vyberte **Odstrániť** na paneli akcií.</span><span class="sxs-lookup"><span data-stu-id="5b6db-143">Select the segment on the **Segments** page and select **Delete** in the action bar.</span></span> <span data-ttu-id="5b6db-144">Potom potvrďte odstránenie.</span><span class="sxs-lookup"><span data-stu-id="5b6db-144">Then, confirm your deletion.</span></span>

## <a name="about-similarity-scores"></a><span data-ttu-id="5b6db-145">O skóre podobnosti</span><span class="sxs-lookup"><span data-stu-id="5b6db-145">About similarity scores</span></span>

<span data-ttu-id="5b6db-146">Model binárnej klasifikácie strojového učenia priraďuje skóre zákazníkom v podobnom segmente.</span><span class="sxs-lookup"><span data-stu-id="5b6db-146">The binary classification machine learning model assigns a score to customers in the similar segment.</span></span> <span data-ttu-id="5b6db-147">Skóre je založené na podobnosti so zákazníkmi v segmente zdrojov.</span><span class="sxs-lookup"><span data-stu-id="5b6db-147">The score is based on the similarity to customers in the source segment.</span></span>

- <span data-ttu-id="5b6db-148">Skóre podobnosti pod 0,55 sú zákazníci klasifikovaní systémom ako *nie podobní* zákazníkom v zdrojovom segmente</span><span class="sxs-lookup"><span data-stu-id="5b6db-148">Similarity scores below 0.55 are customers the system classified as *not similar* to customers in the source segment</span></span>
- <span data-ttu-id="5b6db-149">Skóre podobnosti medzi 0,55 – 0,7 sa klasifikuje ako *trochu podobní*</span><span class="sxs-lookup"><span data-stu-id="5b6db-149">Similarity scores between 0.55 – 0.7 are classified as *somewhat similar*</span></span>
- <span data-ttu-id="5b6db-150">Skóre podobnosti medzi 0,7 – 0,85 sa klasifikuje ako *podobní*</span><span class="sxs-lookup"><span data-stu-id="5b6db-150">Similarity scores between 0.7 – 0.85 are classified as *similar*</span></span>
- <span data-ttu-id="5b6db-151">Skóre podobnosti medzi 0,85 – 1 sú zákazníci klasifikovaní ako *veľmi podobní*</span><span class="sxs-lookup"><span data-stu-id="5b6db-151">Similarity scores between 0.85 – 1 are customers the system classified as *very similar*</span></span>

<span data-ttu-id="5b6db-152">Zákazníci so skóre podobnosti pod 0,4 nie sú zahrnutí do výstupu modelu.</span><span class="sxs-lookup"><span data-stu-id="5b6db-152">Customers with similarity scores below 0.4 aren't included in the model output.</span></span> <span data-ttu-id="5b6db-153">Systém ich nepovažuje za dosť podobných zdrojovému segmentu.</span><span class="sxs-lookup"><span data-stu-id="5b6db-153">The system doesn't consider them similar enough to the source segment.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]