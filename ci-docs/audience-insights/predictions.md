---
title: Doplnenie čiastkových údajov pomocou predikcií
description: Použite predikcie na vyplnenie neúplných údajov o zákazníkoch.
ms.date: 05/05/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 3342328b9eead9bdcb8b41f119a1d0a5823001c8
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 03/15/2021
ms.locfileid: "5595920"
---
# <a name="complete-your-partial-data-with-predictions"></a><span data-ttu-id="7c74c-103">Doplňte svoje predbežné údaje o predikcie</span><span class="sxs-lookup"><span data-stu-id="7c74c-103">Complete your partial data with predictions</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="7c74c-104">Predikcie vám umožňujú ľahko vytvárať predikované hodnoty, ktoré môžu zlepšiť vaše pochopenie zákazníka.</span><span class="sxs-lookup"><span data-stu-id="7c74c-104">Predictions lets you easily create predicted values that can enhance your understanding of a customer.</span></span> <span data-ttu-id="7c74c-105">Na stránke **Analýza** > **Predikcie** môžete vybrať **Moje predikcie** a zobraziť predikcie, ktoré ste nakonfigurovali v iných častiach štatistík o cieľovej skupine, a môžete ich ďalej prispôsobovať.</span><span class="sxs-lookup"><span data-stu-id="7c74c-105">On the **Intelligence** > **Predictions** page, you can select **My predictions** to see predictions that you've configured in other parts of audience insights, and allow you to further customize them.</span></span>

> [!NOTE]
> <span data-ttu-id="7c74c-106">Túto funkciu nemôžete použiť, ak vaše prostredie používa úložisko Azure Data Lake Gen 2.</span><span class="sxs-lookup"><span data-stu-id="7c74c-106">You can't use this feature if your environment uses Azure Data Lake Gen 2 storage.</span></span>
>
> <span data-ttu-id="7c74c-107">Funkcia predikcii využíva automatizované prostriedky na vyhodnotenie údajov a predikcie na základe týchto údajov, a preto sa dá použiť ako metóda profilovania, pretože tento pojem je definovaný všeobecným nariadením o ochrane údajov („GDPR“).</span><span class="sxs-lookup"><span data-stu-id="7c74c-107">The predictions feature uses automated means to evaluate data and make predictions based on that data, and therefore has the capability to be used as a method of profiling, as that term is defined by the General Data Protection Regulation ("GDPR").</span></span> <span data-ttu-id="7c74c-108">Použitie tejto funkcie zákazníkom na spracovanie údajov môže podliehať GDPR alebo iným zákonom alebo predpisom.</span><span class="sxs-lookup"><span data-stu-id="7c74c-108">Customer's use of this feature to process data may be subject to GDPR or other laws or regulations.</span></span> <span data-ttu-id="7c74c-109">Ste zodpovední za zabezpečenie toho, že vaše používanie služby Dynamics 365 Customer Insights vrátane predikcií bude v súlade so všetkými platnými zákonmi a nariadeniami vrátane zákonov týkajúcich sa ochrany súkromia, osobných údajov, biometrických údajov, ochrany údajov a dôvernosti komunikácií.</span><span class="sxs-lookup"><span data-stu-id="7c74c-109">You are responsible for ensuring that your use of Dynamics 365 Customer Insights, including predictions, complies with all applicable laws and regulations, including laws related to privacy, personal data, biometric data, data protection, and confidentiality of communications.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="7c74c-110">Predpoklady</span><span class="sxs-lookup"><span data-stu-id="7c74c-110">Prerequisites</span></span>

<span data-ttu-id="7c74c-111">Predtým ako bude vaša organizácia môcť používať funkciu predikcií, skontrolujte, či sú splnené nasledujúce predpoklady:</span><span class="sxs-lookup"><span data-stu-id="7c74c-111">Before your organization can use the predictions feature, the following prerequisites must be met:</span></span>

1. <span data-ttu-id="7c74c-112">Vaša organizácia má nastavenú inštanciu [v Common Data Service](/ai-builder/build-model#prerequisites) a nachádza sa v rovnakej organizácii ako Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="7c74c-112">Your organization has an instance [set up in the Common Data Service](/ai-builder/build-model#prerequisites) and it's in the same organization as Customer Insights.</span></span>

2. <span data-ttu-id="7c74c-113">Vaše prostredie je spojené s vašou inštanciou Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="7c74c-113">Your environment is attached to your Common Data Service instance.</span></span>

<span data-ttu-id="7c74c-114">Keď [vytvárate nové prostredie](manage-environments.md), nakonfigurujte ho v dialógovom okne **Vytvorenie prostredia** a vyberte možnosť **Pokročilé**.</span><span class="sxs-lookup"><span data-stu-id="7c74c-114">If you're [creating a new environment](manage-environments.md), configure it in the **Create an environment** dialog and select **Advanced**.</span></span> <span data-ttu-id="7c74c-115">Ak ste už vytvorili prostredie, prejdite na jeho nastavenia a vyberte položku **Pokročilé**.</span><span class="sxs-lookup"><span data-stu-id="7c74c-115">If you've already created an environment, go to its settings and select **Advanced**.</span></span> <span data-ttu-id="7c74c-116">V každom prípade v sekcii **Používať predikcie** zadajte adresu URL inštancie Common Data Service, ku ktorej chcete pripojiť svoje prostredie.</span><span class="sxs-lookup"><span data-stu-id="7c74c-116">Either way, in the **Use predictions** section, enter the Common Data Service instance URL to which you want to attach your environment.</span></span>

## <a name="create-a-prediction-in-the-customer-entity"></a><span data-ttu-id="7c74c-117">Vytvorenie predikcie v entite Zákazník</span><span class="sxs-lookup"><span data-stu-id="7c74c-117">Create a prediction in the Customer entity</span></span>

1. <span data-ttu-id="7c74c-118">V prehľadoch cieľových skupín prejdite na **Údaje** > **Entity**.</span><span class="sxs-lookup"><span data-stu-id="7c74c-118">In audience insights, go to **Data** > **Entities**.</span></span>

2. <span data-ttu-id="7c74c-119">Vyberte entitu **Zákazník**.</span><span class="sxs-lookup"><span data-stu-id="7c74c-119">Select the **Customer** entity.</span></span>

3. <span data-ttu-id="7c74c-120">V entite **Zákazník: Customer Insights** vyberte kartu **Polia**.</span><span class="sxs-lookup"><span data-stu-id="7c74c-120">In the **Customer:CustomerInsights** entity, select on the **Fields** tab.</span></span>

4. <span data-ttu-id="7c74c-121">Nájdite názov atribútu, pre ktorý chcete predpovedať hodnoty, a potom vyberte ikonu **Prehľad** v stĺpci **Zhrnutie**.</span><span class="sxs-lookup"><span data-stu-id="7c74c-121">Find the attribute name you wish to predict values for, then select the **Overview** icon in the **Summary** column.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="7c74c-122">![Ikona prehľadu](media/intelligence-overviewicon.png "Ikona prehľadu")</span><span class="sxs-lookup"><span data-stu-id="7c74c-122">![Overview icon](media/intelligence-overviewicon.png "Overview icon")</span></span>

5. <span data-ttu-id="7c74c-123">Ak existuje vysoký počet chýbajúcich hodnôt pre váš atribút, vyberte položku **Predpovedať chýbajúce hodnoty** a pokračujte v predikcii.</span><span class="sxs-lookup"><span data-stu-id="7c74c-123">If there's a high rate of missing values for your attribute, select **Predict missing values** to continue with your prediction.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="7c74c-124">![Stav prehľadu so zobrazeným tlačidlom predikcie chýbajúcich hodnôt](media/intelligence-overviewpredictmissingvalues.png "Stav prehľadu so zobrazeným tlačidlom predikcie chýbajúcich hodnôt")</span><span class="sxs-lookup"><span data-stu-id="7c74c-124">![Overview status with predict missing values button shown](media/intelligence-overviewpredictmissingvalues.png "Overview status with predict missing values button shown")</span></span>

6. <span data-ttu-id="7c74c-125">Uveďte **Zobrazované meno** a **Názov výstupnej entity** pre výsledky predikcie.</span><span class="sxs-lookup"><span data-stu-id="7c74c-125">Provide a **Display name** and an **Output entity name** for the results of the prediction.</span></span>

7. <span data-ttu-id="7c74c-126">Zobrazí sa predvyplnený zoznam možností, kde môžete namapovať hodnoty na predikovanú kategóriu.</span><span class="sxs-lookup"><span data-stu-id="7c74c-126">A pre-populated list of options will show where you can map the values to a predicted category.</span></span> <span data-ttu-id="7c74c-127">V takom prípade budú vašou jedinou možnosťou kategórie 0 alebo 1, pretože mapujú na pravdivú/nepravdivú alebo binárnu povahu predikcie.</span><span class="sxs-lookup"><span data-stu-id="7c74c-127">In this case, your only category options will be 0 or 1, as they map to the true/false or binary nature of the prediction.</span></span> <span data-ttu-id="7c74c-128">V stĺpci Kategória, priraďte hodnoty polí, ktoré chcete nechať klasifikovať ako „0“ v konečnej predikcii, na „0“ a položky, ktoré by ste chceli klasifikovať ako „1“ v konečnej predikcii na „1“.</span><span class="sxs-lookup"><span data-stu-id="7c74c-128">In the Category column, map the field values you'd like to be classified as "0" in the final prediction to "0", and the items you'd like to be classified as "1" in the final prediction to "1".</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="7c74c-129">![Príklad, ktorý zobrazuje hodnoty mapovaných hodnôt polí do kategórií](media/intelligence-categorymapping.png "Príklad, ktorý zobrazuje hodnoty mapovaných hodnôt polí do kategórií")</span><span class="sxs-lookup"><span data-stu-id="7c74c-129">![Example showing mapped field values to categories](media/intelligence-categorymapping.png "Example showing mapped field values to categories")</span></span>

8. <span data-ttu-id="7c74c-130">Vyberte **Hotovo** a predikcia sa spracuje.</span><span class="sxs-lookup"><span data-stu-id="7c74c-130">Select **Done** and the prediction will be processed.</span></span> <span data-ttu-id="7c74c-131">Spracovanie bude nejaký čas trvať, v závislosti od veľkosti a zložitosti údajov.</span><span class="sxs-lookup"><span data-stu-id="7c74c-131">The processing will take some time, depending on the size and complexity of data.</span></span> <span data-ttu-id="7c74c-132">Výsledky budú k dispozícii v novej entite založenej na predikcii **Názve výstupnej entity**, ktorú ste vytvorili.</span><span class="sxs-lookup"><span data-stu-id="7c74c-132">Results will be available in a new entity based on the **Output entity name** of the prediction you created.</span></span>

## <a name="create-a-prediction-while-creating-a-segment"></a><span data-ttu-id="7c74c-133">Vytvorenie predikcie pri vytváraní segmentu</span><span class="sxs-lookup"><span data-stu-id="7c74c-133">Create a prediction while creating a segment</span></span>

<span data-ttu-id="7c74c-134">Pri vytváraní segmentu je tiež možné predikovať chýbajúce hodnoty pre konkrétny zvolený atribút.</span><span class="sxs-lookup"><span data-stu-id="7c74c-134">Predicting missing values for a specific attribute of choice is also possible when creating a segment.</span></span> <span data-ttu-id="7c74c-135">Konkrétne, keď rýchlo vytvoríte segment založený na zjednotenej entite Zákazník alebo entite Miera_zákazníka.</span><span class="sxs-lookup"><span data-stu-id="7c74c-135">Specifically, when you quickly create a segment based on either your unified Customer entity or Customer_Measure entity.</span></span>

<span data-ttu-id="7c74c-136">V rámci tohto toku vyberiete konkrétny atribút, ktorý bude základom vášho segmentu, napríklad Spokojnosť zákazníka alebo Suma nákupu.</span><span class="sxs-lookup"><span data-stu-id="7c74c-136">As part of this flow, you'll choose a specific attribute to base your segment on, such as Customer Satisfaction or Purchase Amount.</span></span> <span data-ttu-id="7c74c-137">Po vytvorení segmentu systém navrhne metódu predpovedania akýchkoľvek chýbajúcich hodnôt pre tento atribút.</span><span class="sxs-lookup"><span data-stu-id="7c74c-137">Upon segment creation, the system will suggest a method for predicting any missing values for this attribute.</span></span>

1. <span data-ttu-id="7c74c-138">V prehľadoch cieľových skupín prejdite na **Segmenty** a vyberte dlaždicu **Profily**.</span><span class="sxs-lookup"><span data-stu-id="7c74c-138">In audience insights, go to **Segments** and select the **Profiles** tile.</span></span>

2. <span data-ttu-id="7c74c-139">Vyberte **Pole** na vytvorenie segmentu a vyberte **Operátor** a potom **Skontrolovať**.</span><span class="sxs-lookup"><span data-stu-id="7c74c-139">Choose a **Field** to create a segment on and select an **Operator**, then select **Review**.</span></span>

3. <span data-ttu-id="7c74c-140">Uveďte **Názov** a **Zobrazovaný názov** pre segment.</span><span class="sxs-lookup"><span data-stu-id="7c74c-140">Provide a **Name** and a **Display name** for the segment.</span></span>

4. <span data-ttu-id="7c74c-141">Vyberte položku **Uložiť**.</span><span class="sxs-lookup"><span data-stu-id="7c74c-141">Select **Save**.</span></span>

5. <span data-ttu-id="7c74c-142">Ak segment, ktorý ste vytvorili, obsahuje neúplné údaje v zdrojovom poli, môžete predikovať chýbajúce hodnoty.</span><span class="sxs-lookup"><span data-stu-id="7c74c-142">If the segment you created has incomplete data in the source field, you can choose to predict the missing values.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="7c74c-143">![Tlačidlo predikcie](media/segments-predictoption.png "Tlačidlo predikcie")</span><span class="sxs-lookup"><span data-stu-id="7c74c-143">![Prediction button](media/segments-predictoption.png "Prediction button")</span></span>

6. <span data-ttu-id="7c74c-144">Uveďte **Zobrazované meno** a **Názov výstupnej entity** pre výsledky predikcie.</span><span class="sxs-lookup"><span data-stu-id="7c74c-144">Provide a **Display name** and an **Output entity name** for the results of the prediction.</span></span>

7. <span data-ttu-id="7c74c-145">Vyberte **Hotovo**.</span><span class="sxs-lookup"><span data-stu-id="7c74c-145">Select **Done**.</span></span> <span data-ttu-id="7c74c-146">Vaša predikcia bude vygenerovaná čoskoro v novej entite s názvom, ktorý ste zadali pre **Názov výstupnej entity**.</span><span class="sxs-lookup"><span data-stu-id="7c74c-146">Your prediction will be generated shortly in a new entity with the name you provided for the **Output entity name**.</span></span>

## <a name="view-a-prediction"></a><span data-ttu-id="7c74c-147">Zobrazenie predikcie</span><span class="sxs-lookup"><span data-stu-id="7c74c-147">View a prediction</span></span>

1. <span data-ttu-id="7c74c-148">V prehľadoch cieľových skupín prejdite na **Analýza** > **Predikcie** > **Moje predikcie**.</span><span class="sxs-lookup"><span data-stu-id="7c74c-148">In audience insights, go to **Intelligence** > **Predictions** > **My predictions**.</span></span>

2. <span data-ttu-id="7c74c-149">Vyberte predikciu, ktorú chcete skontrolovať.</span><span class="sxs-lookup"><span data-stu-id="7c74c-149">Select the prediction you want to review.</span></span>

3. <span data-ttu-id="7c74c-150">Vyberte tri bodky v stĺpci **Akcie** a vyberte **Zobraziť**.</span><span class="sxs-lookup"><span data-stu-id="7c74c-150">Select the ellipsis in the **Actions** column and choose **View**.</span></span>

4. <span data-ttu-id="7c74c-151">V zobrazení predikcie sa zobrazí niekoľko údajových bodov.</span><span class="sxs-lookup"><span data-stu-id="7c74c-151">You'll see a number of data points in the view of your prediction.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="7c74c-152">![Stránka predikcie](media/intelligence-predictionsviewpage.png "Stránka predikcie")</span><span class="sxs-lookup"><span data-stu-id="7c74c-152">![Predictions page](media/intelligence-predictionsviewpage.png "Predictions page")</span></span>

   - <span data-ttu-id="7c74c-153">**Hodnoty predikcie** zobrazujú mapovanie, ktoré ste vytvorili počas fázy mapovania hodnoty poľa do kategórie.</span><span class="sxs-lookup"><span data-stu-id="7c74c-153">**Predicted values** shows the mapping you created during the Field value to Category mapping phase.</span></span> <span data-ttu-id="7c74c-154">Toto sú hodnoty vo vašom súbore údajov, ktoré boli mapované do konkrétnej kategórie.</span><span class="sxs-lookup"><span data-stu-id="7c74c-154">These are the values in your dataset that have been mapped to a specific category.</span></span>
   <span data-ttu-id="7c74c-155">-**Top vplyvné osoby** sú faktory v rámci vášho súboru údajov, ktoré najpravdepodobnejšie ovplyvnili dôveru v predikciu, že hodnota vášho poľa bude mapovaná na konkrétnu kategóriu.</span><span class="sxs-lookup"><span data-stu-id="7c74c-155">-**Top influencers** are the factors within your dataset that were most likely to influence the prediction's confidence of your Field value being mapped to a specific category.</span></span>
   - <span data-ttu-id="7c74c-156">**Výkon** označuje, ako sa darí predikciám.</span><span class="sxs-lookup"><span data-stu-id="7c74c-156">**Performance** indicates how the predictions are doing.</span></span> <span data-ttu-id="7c74c-157">Ak chcete získať viac informácií, kliknite na odkaz.</span><span class="sxs-lookup"><span data-stu-id="7c74c-157">Select the link to learn more.</span></span>
   - <span data-ttu-id="7c74c-158">**Náhľad** zobrazuje ukážky súboru výstupných údajov z vašej predikcie a pravdepodobnosť alebo spoľahlivosť predikovanej hodnoty, kde 0 je neistota a 1 je istota.</span><span class="sxs-lookup"><span data-stu-id="7c74c-158">**Preview** shows samples of the output dataset from your prediction and the likelihood, or our confidence, of the predicted value where 0 is uncertain, and 1 is certain.</span></span>

## <a name="update-a-prediction"></a><span data-ttu-id="7c74c-159">Aktualizácia predikcie</span><span class="sxs-lookup"><span data-stu-id="7c74c-159">Update a prediction</span></span>

1. <span data-ttu-id="7c74c-160">V prehľadoch cieľových skupín prejdite na **Analýza** > **Predikcie** > **Moje predikcie**.</span><span class="sxs-lookup"><span data-stu-id="7c74c-160">In audience insights, go to **Intelligence** > **Predictions** > **My predictions**.</span></span>

2. <span data-ttu-id="7c74c-161">Vyberte predikciu, ktorú chcete aktualizovať, a vyberte ikonu **Aktualizovať**.</span><span class="sxs-lookup"><span data-stu-id="7c74c-161">Select the prediction you want to update and select the **Update** icon.</span></span>

3. <span data-ttu-id="7c74c-162">Predikcia bude naplánovaná na spracovanie.</span><span class="sxs-lookup"><span data-stu-id="7c74c-162">The prediction will be scheduled for processing.</span></span> <span data-ttu-id="7c74c-163">Čas poslednej aktualizácie sa zobrazuje v stĺpci **Aktualizované** stránky **Predikcie**.</span><span class="sxs-lookup"><span data-stu-id="7c74c-163">You can see the time it was last updated in the **Updated** column of the **Predictions** page.</span></span>

## <a name="edit-a-prediction"></a><span data-ttu-id="7c74c-164">Úprava predikcie</span><span class="sxs-lookup"><span data-stu-id="7c74c-164">Edit a prediction</span></span>

<span data-ttu-id="7c74c-165">Po vytvorení predikcie môžete model v nástroji AI Builder prispôsobiť tak, aby sa zvýšila jeho účinnosť.</span><span class="sxs-lookup"><span data-stu-id="7c74c-165">After you've created a prediction, you can customize the model in the AI Builder to increase the effectiveness of your model.</span></span>  

1. <span data-ttu-id="7c74c-166">V prehľadoch cieľových skupín prejdite na **Analýza** > **Predikcie** > **Moje predikcie**.</span><span class="sxs-lookup"><span data-stu-id="7c74c-166">In audience insights, go to **Intelligence** > **Predictions** > **My predictions**.</span></span>

2. <span data-ttu-id="7c74c-167">Vyberte predikciu, ktorú chcete upraviť.</span><span class="sxs-lookup"><span data-stu-id="7c74c-167">Select the prediction you want to edit.</span></span>

3. <span data-ttu-id="7c74c-168">Vyberte tri bodky v stĺpci **Akcie** a vyberte **Zobraziť**.</span><span class="sxs-lookup"><span data-stu-id="7c74c-168">Select the ellipsis in the **Actions** column and choose **View**.</span></span>

4. <span data-ttu-id="7c74c-169">Vyberte **Prispôsobiť v nástroji AI Builder**.</span><span class="sxs-lookup"><span data-stu-id="7c74c-169">Select **Customize in AI Builder**.</span></span>

5. <span data-ttu-id="7c74c-170">Aktualizujte svoj model v nástroji AI Builder.</span><span class="sxs-lookup"><span data-stu-id="7c74c-170">Update your model in the AI Builder.</span></span> <span data-ttu-id="7c74c-171">[Prečítajte si viac informácií o správe modelov v nástroji AI Builder](/ai-builder/manage-model#retrain-and-republish-existing-models).</span><span class="sxs-lookup"><span data-stu-id="7c74c-171">[Learn more about managing models in the AI builder](/ai-builder/manage-model#retrain-and-republish-existing-models).</span></span>

<span data-ttu-id="7c74c-172">Pri ďalšom spustení predikcie sa použije aktualizovaný model, ktorý ste vytvorili.</span><span class="sxs-lookup"><span data-stu-id="7c74c-172">The next run of your prediction will use the updated model you've created.</span></span>

> [!NOTE]
> <span data-ttu-id="7c74c-173">Nové modely vytvorené v aplikácii AI Builder sa nebudú zobrazovať v štatistikách publika, pokiaľ nebol model vytvorený z vyššie uvedených prostredí.</span><span class="sxs-lookup"><span data-stu-id="7c74c-173">New models created in AI Builder will not be displayed in audience insights unless the model was created from the experiences listed above.</span></span>

## <a name="remove-a-prediction"></a><span data-ttu-id="7c74c-174">Odstránenie predikcie</span><span class="sxs-lookup"><span data-stu-id="7c74c-174">Remove a prediction</span></span>

1. <span data-ttu-id="7c74c-175">V prehľadoch cieľových skupín prejdite na **Analýza** > **Predikcie** > **Moje predikcie**.</span><span class="sxs-lookup"><span data-stu-id="7c74c-175">In audience insights, go to **Intelligence** > **Predictions** > **My predictions**.</span></span>

2. <span data-ttu-id="7c74c-176">Vyberte predikciu, ktorú chcete odstrániť.</span><span class="sxs-lookup"><span data-stu-id="7c74c-176">Select the prediction you want to delete.</span></span>

3. <span data-ttu-id="7c74c-177">Vyberte tri bodky v stĺpci **Akcie** a vyberte **Odstrániť**.</span><span class="sxs-lookup"><span data-stu-id="7c74c-177">Select the ellipsis in the **Actions** column and choose **Delete**.</span></span>

4. <span data-ttu-id="7c74c-178">Potvrďte vymazanie.</span><span class="sxs-lookup"><span data-stu-id="7c74c-178">Confirm the deletion.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="7c74c-179">Riešenie problémov</span><span class="sxs-lookup"><span data-stu-id="7c74c-179">Troubleshooting</span></span>

<span data-ttu-id="7c74c-180">Ak nemôžete dokončiť proces pripojenia Common Data Service kvôli chybe, môžete skúsiť dokončiť proces ručne.</span><span class="sxs-lookup"><span data-stu-id="7c74c-180">If you can't complete the attach Common Data Service process due to an error, you can try to complete the process manually.</span></span> <span data-ttu-id="7c74c-181">V procese pripájania sa môžu vyskytnúť dva známe problémy:</span><span class="sxs-lookup"><span data-stu-id="7c74c-181">There are two known issues that can occur in the attach process:</span></span>

- <span data-ttu-id="7c74c-182">Nie je nainštalované riešenie doplnku Karta zákazníka.</span><span class="sxs-lookup"><span data-stu-id="7c74c-182">The Customer Card Add-in solution is not installed.</span></span>
    1. <span data-ttu-id="7c74c-183">Vykonajte pokyny podľa pokynov [nainštalujte a nakonfigurujte riešenie](customer-card-add-in.md).</span><span class="sxs-lookup"><span data-stu-id="7c74c-183">Complete the instructions to [install and configure the solution](customer-card-add-in.md).</span></span>

- <span data-ttu-id="7c74c-184">Povolenia aplikácií nie sú udelené.</span><span class="sxs-lookup"><span data-stu-id="7c74c-184">App permissions aren't granted.</span></span>
    1. <span data-ttu-id="7c74c-185">Prejdite do systému [https://admin.powerplatform.microsoft.com](https://admin.powerplatform.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="7c74c-185">Go to [https://admin.powerplatform.microsoft.com](https://admin.powerplatform.microsoft.com).</span></span>
    1. <span data-ttu-id="7c74c-186">Vyberte položku **Prostredia**.</span><span class="sxs-lookup"><span data-stu-id="7c74c-186">Select **Environments**.</span></span>
    1. <span data-ttu-id="7c74c-187">Vyberte tri bodky vedľa prostredia, do ktorého chcete pridať povolenie, a vyberte **Nastavenia**.</span><span class="sxs-lookup"><span data-stu-id="7c74c-187">Select the ellipsis next to the environment you want to add the permission to and select **Settings**.</span></span>
    1. <span data-ttu-id="7c74c-188">Rozbaľte **Používatelia + povolenia** a vyberte **Používatelia**.</span><span class="sxs-lookup"><span data-stu-id="7c74c-188">Expand **Users + permissions** and select **Users**.</span></span>
    1. <span data-ttu-id="7c74c-189">Vyberte možnosť **+ Nové** a zvoľte možnosť **Používateľ**.</span><span class="sxs-lookup"><span data-stu-id="7c74c-189">Select **+ New** and select **User**.</span></span>
    1. <span data-ttu-id="7c74c-190">Vyberte **Používateľ aplikácie**, ak ešte nie je vybraté, zadajte nasledujúce informácie:</span><span class="sxs-lookup"><span data-stu-id="7c74c-190">Select **Application User** if it's not already selected and enter the following information:</span></span>
        - <span data-ttu-id="7c74c-191">**Meno používateľa:** cihelp@microsoft.com</span><span class="sxs-lookup"><span data-stu-id="7c74c-191">**User Name:** cihelp@microsoft.com</span></span>
        - <span data-ttu-id="7c74c-192">**ID aplikácie:** 38c77d00-5fcb-4cce-9d93-af4738258e3c</span><span class="sxs-lookup"><span data-stu-id="7c74c-192">**Application ID:** 38c77d00-5fcb-4cce-9d93-af4738258e3c</span></span>
        - <span data-ttu-id="7c74c-193">**Krstné meno:** Zákazník</span><span class="sxs-lookup"><span data-stu-id="7c74c-193">**First Name:** Customer</span></span>
        - <span data-ttu-id="7c74c-194">**Priezvisko:** Insights</span><span class="sxs-lookup"><span data-stu-id="7c74c-194">**Last Name:** Insights</span></span>
        - <span data-ttu-id="7c74c-195">**Hlavný e-mail:** cihelp@microsoft.com</span><span class="sxs-lookup"><span data-stu-id="7c74c-195">**Primary Email:** cihelp@microsoft.com</span></span>
    1. <span data-ttu-id="7c74c-196">Vyberte položku **Uložiť a zavrieť**.</span><span class="sxs-lookup"><span data-stu-id="7c74c-196">Select **Save & Close**.</span></span>
    1. <span data-ttu-id="7c74c-197">Vyberte používateľa, ktorého ste práve vytvorili.</span><span class="sxs-lookup"><span data-stu-id="7c74c-197">Select the user you just created.</span></span>
    1. <span data-ttu-id="7c74c-198">V hornej ponuke vyberte možnosť **Spravovať roly**.</span><span class="sxs-lookup"><span data-stu-id="7c74c-198">Select **Manage Roles** in the top menu bar.</span></span>
    1. <span data-ttu-id="7c74c-199">Vyberte **Správca systému** a potom **OK**.</span><span class="sxs-lookup"><span data-stu-id="7c74c-199">Select **System Administrator**, then select **OK**.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]