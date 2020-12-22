---
title: Vlastné modely strojového učenia | Dokumentácia spoločnosti Microsoft
description: Práca s vlastnými modelmi zo strojového učenia platformy Azure v systéme Dynamics 365 Customer Insights.
ms.date: 11/19/2020
ms.reviewer: zacook
ms.service: dynamics-365-ai
ms.topic: article
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: ef248086b30b870359970529a7bfb37792be62d5
ms.sourcegitcommit: a9b2cf598f256d07a48bba8617347ee90024a1dd
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 12/03/2020
ms.locfileid: "4668922"
---
# <a name="custom-machine-learning-models"></a><span data-ttu-id="87266-103">Vlastné modely strojového učenia</span><span class="sxs-lookup"><span data-stu-id="87266-103">Custom machine learning models</span></span>

<span data-ttu-id="87266-104">**Inteligencia** > **Vlastné modely** umožňuje spravovať pracovné postupy založené na modeloch strojového učenia Azure.</span><span class="sxs-lookup"><span data-stu-id="87266-104">**Intelligence** > **Custom models** lets you manage workflows based on Azure Machine Learning models.</span></span> <span data-ttu-id="87266-105">Pracovné postupy vám pomôžu vybrať údaje, z ktorých chcete generovať prehľady, a namapovať výsledky na vaše zjednotené údaje o zákazníkoch.</span><span class="sxs-lookup"><span data-stu-id="87266-105">Workflows help you choose the data you want to generate insights from and map the results to your unified customer data.</span></span> <span data-ttu-id="87266-106">Ďalšie informácie o vytváraní vlastných modelov ML nájdete v sekcii [Používajte modely založené na strojovom učení platformy Azure](azure-machine-learning-experiments.md).</span><span class="sxs-lookup"><span data-stu-id="87266-106">For more information about building custom ML models, see [Use Azure Machine Learning-based models](azure-machine-learning-experiments.md).</span></span>

## <a name="responsible-ai"></a><span data-ttu-id="87266-107">Zodpovedná AI</span><span class="sxs-lookup"><span data-stu-id="87266-107">Responsible AI</span></span>

<span data-ttu-id="87266-108">Predikcie ponúkajú možnosti na vytváranie lepších zákazníckych prostredí, zlepšovanie obchodných schopností a prehľadov o výnosoch.</span><span class="sxs-lookup"><span data-stu-id="87266-108">Predictions offer capabilities to create better customer experiences, improve business capabilities, and revenue streams.</span></span> <span data-ttu-id="87266-109">Dôrazne odporúčame, aby ste vyvážili hodnotu svojej predikcie vo vzťahu k jej vplyvu a nedostatkom, ktoré môžu vzniknúť etickým spôsobom.</span><span class="sxs-lookup"><span data-stu-id="87266-109">We strongly recommend you balance the value of your prediction against the impact it has and biases that may be introduced in an ethical manner.</span></span> <span data-ttu-id="87266-110">Zistite viac o tom, ako sa spoločnosť Microsoft [rieši zodpovednú AI](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6).</span><span class="sxs-lookup"><span data-stu-id="87266-110">Learn more about how Microsoft is [addressing Responsible AI](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6).</span></span> <span data-ttu-id="87266-111">Môžete sa tiež dozvedieť o [technikách a procesoch pre zodpovedné strojové učenie](https://docs.microsoft.com/azure/machine-learning/concept-responsible-ml) špecifických pre strojové učenie platformy Azure.</span><span class="sxs-lookup"><span data-stu-id="87266-111">You can also learn about [techniques and processes for responsible machine learning](https://docs.microsoft.com/azure/machine-learning/concept-responsible-ml) specific to Azure Machine Learning.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="87266-112">Predpoklady</span><span class="sxs-lookup"><span data-stu-id="87266-112">Prerequisites</span></span>

- <span data-ttu-id="87266-113">Táto funkcia v súčasnosti podporuje webové služby publikované cez [strojové učenie Studio (klasické)](https://studio.azureml.net) a [hromadné kanály strojového učenia platformy Azure](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines).</span><span class="sxs-lookup"><span data-stu-id="87266-113">Currently, this feature supports web services published through [Machine Learning Studio (classic)](https://studio.azureml.net) and [Azure Machine Learning batch pipelines](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines).</span></span>

- <span data-ttu-id="87266-114">Ak chcete používať túto funkciu, potrebujete účet ukladacieho priestoru Azure Data Lake Gen2 spojený s inštanciou platformy Azure Studio.</span><span class="sxs-lookup"><span data-stu-id="87266-114">You need an Azure Data Lake Gen2 storage account associated with your Azure Studio instance to use this feature.</span></span> <span data-ttu-id="87266-115">Ďalšie informácie nájdete v časti [Vytvorenie účtu úložiska Azure Data Lake Storage Gen2](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-quickstart-create-account)</span><span class="sxs-lookup"><span data-stu-id="87266-115">For more information, see [Create an Azure Data Lake Storage Gen2 storage account](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-quickstart-create-account)</span></span>

## <a name="add-a-new-workflow"></a><span data-ttu-id="87266-116">Pridajte nový pracovný postup</span><span class="sxs-lookup"><span data-stu-id="87266-116">Add a new workflow</span></span>

1. <span data-ttu-id="87266-117">Prejdite do ponuky **Analýza** > **Vlastné modely** a vyberte **Nový pracovný postup**.</span><span class="sxs-lookup"><span data-stu-id="87266-117">Go to **Intelligence** > **Custom models** and select **New workflow**.</span></span>

1. <span data-ttu-id="87266-118">Do poľa **Názov** zadajte rozpoznateľný názov vlastného modelu.</span><span class="sxs-lookup"><span data-stu-id="87266-118">Give your custom model a recognizable name in the **Name** field.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="87266-119">![Snímka obrazovky tably Nový pracovný postup](media/new-workflowv2.png "Snímka obrazovky tably Nový pracovný postup")</span><span class="sxs-lookup"><span data-stu-id="87266-119">![Screenshot of the New workflow pane](media/new-workflowv2.png "Screenshot of the New workflow pane")</span></span>

1. <span data-ttu-id="87266-120">V ponuke **Nájomník, ktorý obsahuje vašu webovú službu**, vyberte organizáciu, ktorá obsahuje webovú službu.</span><span class="sxs-lookup"><span data-stu-id="87266-120">Select the organization that contains the web service in **Tenant that contains your web service**.</span></span>

1. <span data-ttu-id="87266-121">Ak je vaše predplatné strojového učenia platformy Azure u iného nájomníka ako Customer Insights, vyberte položku **Prihlásiť sa** s vašimi povereniami pre vybratú organizáciu.</span><span class="sxs-lookup"><span data-stu-id="87266-121">If your Azure Machine Learning subscription is in a different tenant than Customer Insights, select **Sign in** with your credentials for the selected organization.</span></span>

1. <span data-ttu-id="87266-122">Vyberte **Pracovné priestory** spojené s vašou webovou službou.</span><span class="sxs-lookup"><span data-stu-id="87266-122">Select the **Workspaces** associated with your web service.</span></span> <span data-ttu-id="87266-123">Uvedené sú dve sekcie, jedna pre strojové učenie platformy Azure v1 (strojové učenie Studio (klasická)) a jedna pre strojové učenie platformy Azure v2 (strojové učenie platformy Azure).</span><span class="sxs-lookup"><span data-stu-id="87266-123">There are two sections listed, one for Azure Machine Learning v1 (Machine Learning Studio (classic)) and Azure Machine Learning v2 (Azure Machine Learning).</span></span> <span data-ttu-id="87266-124">Ak si nie ste istí, ktorý pracovný priestor je ten pravý pre vašu webovú službu strojového učenia Studio (klasického), vyberte položku **Ľubovoľné**.</span><span class="sxs-lookup"><span data-stu-id="87266-124">If you're not sure which workspace is the right one for your Machine Learning Studio (classic) web service, select **Any**.</span></span>

1. <span data-ttu-id="87266-125">Vyberte webovú službu strojového učenia Studio (klasického) alebo kanál strojového učenia platformy Azure v rozbaľovacej ponuke **Webová služba, ktorá obsahuje váš model**.</span><span class="sxs-lookup"><span data-stu-id="87266-125">Choose the Machine Learning Studio (classic) web service or Azure Machine Learning pipeline in the **Web service that contains your model** dropdown.</span></span> <span data-ttu-id="87266-126">Potom vyberte položku **Ďalej**.</span><span class="sxs-lookup"><span data-stu-id="87266-126">Then, select **Next**.</span></span>
   - <span data-ttu-id="87266-127">Zistite viac o [publikovaní webovej služby v strojovom učení Studio (klasickom)](https://docs.microsoft.com/azure/machine-learning/studio/deploy-a-machine-learning-web-service#deploy-it-as-a-new-web-service)</span><span class="sxs-lookup"><span data-stu-id="87266-127">Learn more about [publishing a web service in Machine Learning Studio (classic)](https://docs.microsoft.com/azure/machine-learning/studio/deploy-a-machine-learning-web-service#deploy-it-as-a-new-web-service)</span></span>
   - <span data-ttu-id="87266-128">Zistite viac o [publikovaní kanálu v strojovom učení platformy Azure pomocou návrhára](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) alebo [súpravy SDK](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk).</span><span class="sxs-lookup"><span data-stu-id="87266-128">Learn more about [publishing a pipeline in Azure Machine Learning using the designer](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) or [SDK](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk).</span></span> 
     > [!NOTE]
     > <span data-ttu-id="87266-129">Váš kanál musí byť zverejnený pod [koncovým bodom kanála](https://docs.microsoft.com/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run).</span><span class="sxs-lookup"><span data-stu-id="87266-129">Your pipeline must be published under a [pipeline endpoint](https://docs.microsoft.com/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run).</span></span>

1. <span data-ttu-id="87266-130">Pre každý **Vstup webovej služby** vyberte zhodnú položku **Entita** v rámci prehľadov cieľových skupín a vyberte položku **Ďalej**.</span><span class="sxs-lookup"><span data-stu-id="87266-130">For each **Web service input**, select the matching **Entity** from audience insights and select **Next**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="87266-131">![Konfigurácia pracovného postupu](media/intelligence-screen2-updated.png "Konfigurácia pracovného postupu")</span><span class="sxs-lookup"><span data-stu-id="87266-131">![Configure a workflow](media/intelligence-screen2-updated.png "Configure a workflow")</span></span>

1. <span data-ttu-id="87266-132">V rámci kroku **Parametre modelového výstupu** nastavte nasledujúce vlastnosti:</span><span class="sxs-lookup"><span data-stu-id="87266-132">In the **Model Output Parameters** step, set the following properties:</span></span>
   - <span data-ttu-id="87266-133">Strojové učenie Studio (klasické)</span><span class="sxs-lookup"><span data-stu-id="87266-133">Machine Learning Studio (classic)</span></span>
      1. <span data-ttu-id="87266-134">Zadajte **Názov entity** výstupu, do ktorého majú prúdiť výsledky výstupu webových služieb.</span><span class="sxs-lookup"><span data-stu-id="87266-134">Enter the output **Entity name** you want web service output results to flow into.</span></span>
   - <span data-ttu-id="87266-135">Strojové učenie platformy Azure</span><span class="sxs-lookup"><span data-stu-id="87266-135">Azure Machine Learning</span></span>
      1. <span data-ttu-id="87266-136">Zadajte **Názov entity** výstupu, do ktorého majú prúdiť výsledky výstupu kanálov.</span><span class="sxs-lookup"><span data-stu-id="87266-136">Enter the output **Entity name** you want pipeline output results to flow into.</span></span>
      1. <span data-ttu-id="87266-137">Vyberte **Názov parametra ukladacieho priestoru výstupných údajov** vášho hromadného kanála z rozbaľovacej ponuky.</span><span class="sxs-lookup"><span data-stu-id="87266-137">Select the **Output data store parameter name** of your batch pipeline from the dropdown.</span></span>
      1. <span data-ttu-id="87266-138">Vyberte **Názov parametra postupu výstupných údajov** vášho hromadného kanála z rozbaľovacej ponuky.</span><span class="sxs-lookup"><span data-stu-id="87266-138">Select the **Output Path parameter name** of your batch pipeline from the dropdown.</span></span>
      
      > [!div class="mx-imgBorder"]
      > <span data-ttu-id="87266-139">![Tabla parametrov modelového výstupu](media/intelligence-screen3-outputparameters.png "Tabla parametrov modelového výstupu")</span><span class="sxs-lookup"><span data-stu-id="87266-139">![Model Output Parameter Pane](media/intelligence-screen3-outputparameters.png "Model Output Parameter Pane")</span></span>

1. <span data-ttu-id="87266-140">Vyberte zodpovedajúci atribút z rozbaľovacieho zoznamu **ID zákazníka vo výsledkoch**, ktorý identifikuje zákazníkov, a vyberte položku **Uložiť**.</span><span class="sxs-lookup"><span data-stu-id="87266-140">Select the matching attribute from the **Customer ID in results** drop-down list that identifies customers and select **Save**.</span></span>
   
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="87266-141">![Spárovanie výsledkov s tablou údajov o zákazníkoch](media/intelligence-screen4-relatetocustomer.png "Spárovanie výsledkov s tablou údajov o zákazníkoch")</span><span class="sxs-lookup"><span data-stu-id="87266-141">![Relate results to Customer data pane](media/intelligence-screen4-relatetocustomer.png "Relate results to Customer data pane")</span></span>

1. <span data-ttu-id="87266-142">Zobrazí sa obrazovka **Pracovný postup bol uložený** s podrobnosťami o pracovnom postupe.</span><span class="sxs-lookup"><span data-stu-id="87266-142">You'll see the **Workflow Saved** screen with details about the workflow.</span></span>    
   <span data-ttu-id="87266-143">Ak ste nakonfigurovali pracovný postup pre kanál strojového učenia platformy Azure, prehľady cieľových skupín sa pripoja k pracovnému priestoru, ktorý obsahuje kanál.</span><span class="sxs-lookup"><span data-stu-id="87266-143">If you configured a workflow for an Azure Machine Learning pipeline, audience insights will attach to the workspace that contains the pipeline.</span></span> <span data-ttu-id="87266-144">Prehľady cieľových skupín získajú rolu **Prispievateľ** v pracovnom priestore platformy Azure.</span><span class="sxs-lookup"><span data-stu-id="87266-144">Audience insights will get a **Contributor** role on the Azure workspace.</span></span>

1. <span data-ttu-id="87266-145">Vyberte **Hotovo**.</span><span class="sxs-lookup"><span data-stu-id="87266-145">Select **Done**.</span></span>

1. <span data-ttu-id="87266-146">Teraz môžete spustiť pracovný postup zo stránky **Vlastné modely**.</span><span class="sxs-lookup"><span data-stu-id="87266-146">You can now run the workflow from the **Custom Models** page.</span></span>

## <a name="edit-a-workflow"></a><span data-ttu-id="87266-147">Upraviť pracovný postup</span><span class="sxs-lookup"><span data-stu-id="87266-147">Edit a workflow</span></span>

1. <span data-ttu-id="87266-148">Na stránke **Vlastné modely** vyberte zvislé tri bodky v stĺpci **Akcie** vedľa pracovného postupu, ktorý ste predtým vytvorili, a vyberte **Upraviť**.</span><span class="sxs-lookup"><span data-stu-id="87266-148">On the **Custom Models** page, select the vertical ellipsis in the **Actions** column next to a workflow you've previously created and select **Edit**.</span></span>

1. <span data-ttu-id="87266-149">Rozpoznateľný názov svojho pracovného postupu môžete aktualizovať v poli **Zobrazovaný názov**, ale nakonfigurovanú webovú službu alebo kanál nemôžete zmeniť.</span><span class="sxs-lookup"><span data-stu-id="87266-149">You can update your workflow's recognizable name in the **Display name** field, but you can't change the configured web service or pipeline.</span></span> <span data-ttu-id="87266-150">Vyberte **Ďalej**.</span><span class="sxs-lookup"><span data-stu-id="87266-150">Select **Next**.</span></span>

1. <span data-ttu-id="87266-151">Pre každý **Vstup webovej služby** môžete aktualizovať zhodnú položku **Entita** v rámci prehľadov cieľových skupín.</span><span class="sxs-lookup"><span data-stu-id="87266-151">For each **Web service input**, you can update the matching **Entity** from audience insights.</span></span> <span data-ttu-id="87266-152">Potom vyberte položku **Ďalej**.</span><span class="sxs-lookup"><span data-stu-id="87266-152">Then, select **Next**.</span></span>

1. <span data-ttu-id="87266-153">V rámci kroku **Parametre modelového výstupu** nastavte nasledujúce vlastnosti:</span><span class="sxs-lookup"><span data-stu-id="87266-153">In the **Model Output Parameters** step, set the following properties:</span></span>
   - <span data-ttu-id="87266-154">Strojové učenie Studio (klasické)</span><span class="sxs-lookup"><span data-stu-id="87266-154">Machine Learning Studio (classic)</span></span>
      1. <span data-ttu-id="87266-155">Zadajte **Názov entity** výstupu, do ktorého majú prúdiť výsledky výstupu webových služieb.</span><span class="sxs-lookup"><span data-stu-id="87266-155">Enter the output **Entity name** you want web service output results to flow into.</span></span>
   - <span data-ttu-id="87266-156">Strojové učenie platformy Azure</span><span class="sxs-lookup"><span data-stu-id="87266-156">Azure Machine Learning</span></span>
      1. <span data-ttu-id="87266-157">Zadajte **Názov entity** výstupu, do ktorého majú prúdiť výsledky výstupu kanálov.</span><span class="sxs-lookup"><span data-stu-id="87266-157">Enter the output **Entity name** you want pipeline output results to flow into.</span></span>
      1. <span data-ttu-id="87266-158">Vyberte položku **Názov parametra ukladacieho priestoru výstupných údajov** pre váš testovací kanál.</span><span class="sxs-lookup"><span data-stu-id="87266-158">Select the **Output data store parameter name** for your test pipeline.</span></span>
      1. <span data-ttu-id="87266-159">Vyberte položku **Názov parametra ukladacieho priestoru postupu** pre váš testovací kanál.</span><span class="sxs-lookup"><span data-stu-id="87266-159">Select the **Output Path parameter name** for your test pipeline.</span></span>

1. <span data-ttu-id="87266-160">Vyberte zodpovedajúci atribút z rozbaľovacieho zoznamu **ID zákazníka vo výsledkoch**, ktorý identifikuje zákazníkov, a vyberte položku **Uložiť**.</span><span class="sxs-lookup"><span data-stu-id="87266-160">Select the matching attribute from the **Customer ID in results** drop-down list that identifies customers and select **Save**.</span></span>
   <span data-ttu-id="87266-161">Musíte si zvoliť atribút z výstupu predikcie s hodnotami podobnými ako v stĺpci ID zákazníka v rámci entity Zákazník.</span><span class="sxs-lookup"><span data-stu-id="87266-161">You need to choose an attribute from the inference output with values similar to the Customer ID column of the Customer entity.</span></span> <span data-ttu-id="87266-162">Ak takýto stĺpec vo svojej množine údajov nemáte, vyberte atribút, ktorý jednoznačne identifikuje daný riadok.</span><span class="sxs-lookup"><span data-stu-id="87266-162">If don't have such a column in your data set, choose an attribute that uniquely identifies the row.</span></span>

## <a name="run-a-workflow"></a><span data-ttu-id="87266-163">Spustenie pracovného postupu</span><span class="sxs-lookup"><span data-stu-id="87266-163">Run a workflow</span></span>

1. <span data-ttu-id="87266-164">Na stránke **Vlastné modely** vyberte zvislé tri bodky v stĺpci **Akcie** vedľa pracovného postupu, ktorý ste predtým vytvorili.</span><span class="sxs-lookup"><span data-stu-id="87266-164">On the **Custom Models** page, select the vertical ellipsis in the **Actions** column next to a workflow you've previously created.</span></span>

1. <span data-ttu-id="87266-165">Vyberte položku **Spustiť**.</span><span class="sxs-lookup"><span data-stu-id="87266-165">Select **Run**.</span></span>

<span data-ttu-id="87266-166">Váš pracovný postup sa tiež spustí automaticky pri každej plánovanej aktualizácii.</span><span class="sxs-lookup"><span data-stu-id="87266-166">Your workflow also runs automatically with every scheduled refresh.</span></span> <span data-ttu-id="87266-167">Zistite viac o [nastavovaní naplánovaného obnovovania](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="87266-167">Learn more about [setting up scheduled refreshes](system.md#schedule-tab).</span></span>

## <a name="delete-a-workflow"></a><span data-ttu-id="87266-168">Odstrániť pracovný postup</span><span class="sxs-lookup"><span data-stu-id="87266-168">Delete a workflow</span></span>

1. <span data-ttu-id="87266-169">Na stránke **Vlastné modely** vyberte zvislé tri bodky v stĺpci **Akcie** vedľa pracovného postupu, ktorý ste predtým vytvorili.</span><span class="sxs-lookup"><span data-stu-id="87266-169">On the **Custom Models** page, select the vertical ellipsis in the **Actions** column next to a workflow you've previously created.</span></span>

1. <span data-ttu-id="87266-170">Vyberte možnosť **Odstrániť** a odstránenie potvrďte.</span><span class="sxs-lookup"><span data-stu-id="87266-170">Select **Delete** and confirm your deletion.</span></span>

<span data-ttu-id="87266-171">Váš pracovný postup bude odstránený.</span><span class="sxs-lookup"><span data-stu-id="87266-171">Your workflow will be deleted.</span></span> <span data-ttu-id="87266-172">[Entita](entities.md), ktorá bola vytvorená pri vytvorení pracovného postupu, sa uchová a bude sa dať zobraziť na stránke **Entity**.</span><span class="sxs-lookup"><span data-stu-id="87266-172">The [entity](entities.md) that was created when you created the workflow persists, and can be viewed from the **Entities** page.</span></span>
