---
title: Pokusy so službou strojového učenia platformy Azure
description: Používajte modely založené na strojovom učení platformy Azure v službe Dynamics 365 Customer Insights.
ms.date: 11/30/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: naravill
ms.author: naravill
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: edd2cf488b52cef87b09b90336e48fdc7f470a68
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597438"
---
# <a name="use-azure-machine-learning-based-models"></a><span data-ttu-id="a0c03-103">Používajte modely založené na strojovom učení platformy Azure</span><span class="sxs-lookup"><span data-stu-id="a0c03-103">Use Azure Machine Learning-based models</span></span>

<span data-ttu-id="a0c03-104">Zjednotené údaje v službe Dynamics 365 Customer Insights sú zdrojom pre vytváranie modelov strojového učenia, ktoré môžu generovať ďalšie obchodné prehľady.</span><span class="sxs-lookup"><span data-stu-id="a0c03-104">The unified data in Dynamics 365 Customer Insights is a source for building machine learning models that can generate additional business insights.</span></span> <span data-ttu-id="a0c03-105">Customer Insights sa integruje do služby strojového učenia Studio (klasickej) a do služby strojového učenia platformy Azure, aby ste mohli používať svoje vlastné modely.</span><span class="sxs-lookup"><span data-stu-id="a0c03-105">Customer Insights integrates with Machine Learning Studio (classic) and Azure Machine Learning to use your own custom models.</span></span> <span data-ttu-id="a0c03-106">V sekcii [Pokusy so službou strojového učenia Studio (klasickou)](machine-learning-studio-experiments.md) nájdete príklady pokusov postavených na službe strojového učenia Studio (klasickej).</span><span class="sxs-lookup"><span data-stu-id="a0c03-106">Refer to [Machine Learning Studio (classic) experiments](machine-learning-studio-experiments.md) for examples of experiments built on Machine Learning Studio (classic).</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="a0c03-107">Predpoklady</span><span class="sxs-lookup"><span data-stu-id="a0c03-107">Prerequisites</span></span>

- <span data-ttu-id="a0c03-108">Prístup do Customer Insights</span><span class="sxs-lookup"><span data-stu-id="a0c03-108">Access to Customer Insights</span></span>
- <span data-ttu-id="a0c03-109">Aktívne predplatné Azure Enterprise</span><span class="sxs-lookup"><span data-stu-id="a0c03-109">Active Azure Enterprise subscription</span></span>
- [<span data-ttu-id="a0c03-110">Zjednotené profily zákazníka</span><span class="sxs-lookup"><span data-stu-id="a0c03-110">Unified customer profiles</span></span>](data-unification.md)
- <span data-ttu-id="a0c03-111">[Export entít do úložiska Azure Blob](export-azure-blob-storage.md) je nakonfigurovaný</span><span class="sxs-lookup"><span data-stu-id="a0c03-111">[Entity export to Azure Blob storage](export-azure-blob-storage.md) configured</span></span>

## <a name="set-up-azure-machine-learning-workspace"></a><span data-ttu-id="a0c03-112">Nastavte pracovný priestor strojového učenia platformy Azure</span><span class="sxs-lookup"><span data-stu-id="a0c03-112">Set up Azure Machine Learning workspace</span></span>

1. <span data-ttu-id="a0c03-113">V sekcii [Vytvorenie pracovného priestoru služby strojového učenia platformy Azure](/azure/machine-learning/concept-workspace#-create-a-workspace) nájdete rôzne možnosti na vytvorenie pracovného priestoru.</span><span class="sxs-lookup"><span data-stu-id="a0c03-113">See [create a Azure Machine Learning workspace](/azure/machine-learning/concept-workspace#-create-a-workspace) for different options to create the workspace.</span></span> <span data-ttu-id="a0c03-114">S cieľom dosiahnuť čo najlepší výkon vytvorte pracovný priestor v oblasti platformy Azure, ktorá je geograficky najbližšie k vášmu prostrediu služby Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="a0c03-114">For best performance, create the workspace in an Azure region that is geographically closest to your Customer Insights environment.</span></span>

1. <span data-ttu-id="a0c03-115">Získajte prístup do vášho pracovného priestoru prostredníctvom služby [strojového učenia platformy Azure Studio](https://ml.azure.com/).</span><span class="sxs-lookup"><span data-stu-id="a0c03-115">Access your workspace through the [Azure Machine Learning Studio](https://ml.azure.com/).</span></span> <span data-ttu-id="a0c03-116">Existuje niekoľko [spôsobov interakcie](/azure/machine-learning/concept-workspace#tools-for-workspace-interaction) s vaším pracovným priestorom.</span><span class="sxs-lookup"><span data-stu-id="a0c03-116">There are several [ways to interact](/azure/machine-learning/concept-workspace#tools-for-workspace-interaction) with your workspace.</span></span>

## <a name="work-with-azure-machine-learning-designer"></a><span data-ttu-id="a0c03-117">Spolupracujte s návrhárom služby strojového učenia platformy Azure</span><span class="sxs-lookup"><span data-stu-id="a0c03-117">Work with Azure Machine Learning designer</span></span>

<span data-ttu-id="a0c03-118">Návrhár služby strojového učenia platformy Azure poskytne vizuálne plátno, do ktorého môžete presúvať množiny údajov a moduly, podobne ako pri službe strojového učenia Studio (klasickú).</span><span class="sxs-lookup"><span data-stu-id="a0c03-118">Azure Machine Learning designer provides a visual canvas where you can drag and drop datasets and modules, similar to Machine Learning Studio (classic).</span></span> <span data-ttu-id="a0c03-119">Hromadný kanál vytvorený návrhárom možno integrovať do služby Customer Insights, ak je zodpovedajúcim spôsobom nakonfigurovaný.</span><span class="sxs-lookup"><span data-stu-id="a0c03-119">A batch pipeline created from the designer can be integrated into Customer Insights if they are configured accordingly.</span></span> 
   
## <a name="working-with-azure-machine-learning-sdk"></a><span data-ttu-id="a0c03-120">Práca so súpravou SDK služby strojového učenia platformy Azure</span><span class="sxs-lookup"><span data-stu-id="a0c03-120">Working with Azure Machine Learning SDK</span></span>

<span data-ttu-id="a0c03-121">Dátoví vedci a vývojári umelej inteligencie používajú [súpravu SDK strojového učenia platformy Azure](/python/api/overview/azure/ml/?preserve-view=true&view=azure-ml-py) na vytváranie pracovných postupov strojového učenia.</span><span class="sxs-lookup"><span data-stu-id="a0c03-121">Data scientists and AI developers use the [Azure Machine Learning SDK](/python/api/overview/azure/ml/?preserve-view=true&view=azure-ml-py) to build machine learning workflows.</span></span> <span data-ttu-id="a0c03-122">V súčasnosti nemožno modely trénované pomocou súpravy SDK integrovať priamo do služby Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="a0c03-122">Currently, models trained using the SDK can't be integrated directly with Customer Insights.</span></span> <span data-ttu-id="a0c03-123">Na integráciu do služby Customer Insights je potrebný kanál hromadnej predikcie, ktorý tento model využíva.</span><span class="sxs-lookup"><span data-stu-id="a0c03-123">A batch inference pipeline that consumes that model is required for integration with Customer Insights.</span></span>

## <a name="batch-pipeline-requirements-to-integrate-with-customer-insights"></a><span data-ttu-id="a0c03-124">Požiadavky na integráciu hromadného kanála so službou Customer Insights</span><span class="sxs-lookup"><span data-stu-id="a0c03-124">Batch pipeline requirements to integrate with Customer Insights</span></span>

### <a name="dataset-configuration"></a><span data-ttu-id="a0c03-125">Konfigurácia množín údajov</span><span class="sxs-lookup"><span data-stu-id="a0c03-125">Dataset Configuration</span></span>

<span data-ttu-id="a0c03-126">Musíte vytvoriť množiny údajov, aby ste mohli používať údaje entít zo služby Customer Insights vo vašom kanáli pre hromadnú predikciu.</span><span class="sxs-lookup"><span data-stu-id="a0c03-126">You need to create datasets to use entity data from Customer Insights to your batch inference pipeline.</span></span> <span data-ttu-id="a0c03-127">Tieto množiny údajov je potrebné zaregistrovať v pracovnom priestore.</span><span class="sxs-lookup"><span data-stu-id="a0c03-127">These datasets need to be registered in the workspace.</span></span> <span data-ttu-id="a0c03-128">Momentálne podporujeme iba [tabuľkové množiny údajov](/azure/machine-learning/how-to-create-register-datasets#tabulardataset) vo formáte .csv.</span><span class="sxs-lookup"><span data-stu-id="a0c03-128">Currently, we only support [tabular datasets](/azure/machine-learning/how-to-create-register-datasets#tabulardataset) in .csv format.</span></span> <span data-ttu-id="a0c03-129">Množiny údajov, ktoré zodpovedajú údajom entity, je potrebné parametrizovať ako parameter kanála.</span><span class="sxs-lookup"><span data-stu-id="a0c03-129">The datasets that correspond to entity data need to be parameterized as a pipeline parameter.</span></span>
   
* <span data-ttu-id="a0c03-130">Parametre množiny údajov v Návrhárovi</span><span class="sxs-lookup"><span data-stu-id="a0c03-130">Dataset parameters in Designer</span></span>
   
     <span data-ttu-id="a0c03-131">V návrhárovi otvorte sekciu **Vybrať stĺpce v množine údajov** a vyberte položku **Nastaviť ako parameter kanála**, kde zadáte názov parametra.</span><span class="sxs-lookup"><span data-stu-id="a0c03-131">In the designer, open **Select Columns in Dataset** and select **Set as pipeline parameter** where you provide a name for the parameter.</span></span>

     > [!div class="mx-imgBorder"]
     > <span data-ttu-id="a0c03-132">![Parametrizácia množiny údajov v návrhárovi](media/intelligence-designer-dataset-parameters.png "Parametrizácia množiny údajov v návrhárovi")</span><span class="sxs-lookup"><span data-stu-id="a0c03-132">![Dataset parameterization in designer](media/intelligence-designer-dataset-parameters.png "Dataset parameterization in designer")</span></span>
   
* <span data-ttu-id="a0c03-133">Parameter množiny údajov v súprave SDK (Python)</span><span class="sxs-lookup"><span data-stu-id="a0c03-133">Dataset parameter in SDK (Python)</span></span>
   
   ```python
   HotelStayActivity_dataset = Dataset.get_by_name(ws, name='Hotel Stay Activity Data')
   HotelStayActivity_pipeline_param = PipelineParameter(name="HotelStayActivity_pipeline_param", default_value=HotelStayActivity_dataset)
   HotelStayActivity_ds_consumption = DatasetConsumptionConfig("HotelStayActivity_dataset", HotelStayActivity_pipeline_param)
   ```

### <a name="batch-inference-pipeline"></a><span data-ttu-id="a0c03-134">Kanál hromadnej predikcie</span><span class="sxs-lookup"><span data-stu-id="a0c03-134">Batch inference pipeline</span></span>
  
* <span data-ttu-id="a0c03-135">V návrhárovi sa dá tréningový kanál použiť na vytvorenie alebo aktualizáciu kanálu predikcie.</span><span class="sxs-lookup"><span data-stu-id="a0c03-135">In the designer, a training pipeline can be used to create or update an inference pipeline.</span></span> <span data-ttu-id="a0c03-136">V súčasnosti sú podporované iba kanály hromadnej predikcie.</span><span class="sxs-lookup"><span data-stu-id="a0c03-136">Currently, only batch inference pipelines are supported.</span></span>

* <span data-ttu-id="a0c03-137">Pomocou súpravy SDK môžete kanál publikovať do koncového bodu.</span><span class="sxs-lookup"><span data-stu-id="a0c03-137">Using the SDK, you can publish the pipeline to an endpoint.</span></span> <span data-ttu-id="a0c03-138">V súčasnosti sa služba Customer Insights integruje s predvoleným kanálom do koncového bodu hromadného kanála v pracovnom priestore na strojové učenie.</span><span class="sxs-lookup"><span data-stu-id="a0c03-138">Currently, Customer Insights integrates with the default pipeline in a batch pipeline endpoint in the Machine Learning workspace.</span></span>
   
   ```python
   published_pipeline = pipeline.publish(name="ChurnInferencePipeline", description="Published Churn Inference pipeline")
   pipeline_endpoint = PipelineEndpoint.get(workspace=ws, name="ChurnPipelineEndpoint") 
   pipeline_endpoint.add_default(pipeline=published_pipeline)
   ```

### <a name="import-pipeline-data-into-customer-insights"></a><span data-ttu-id="a0c03-139">Importujte údaje o kanáli do služby Customer Insights</span><span class="sxs-lookup"><span data-stu-id="a0c03-139">Import pipeline data into Customer Insights</span></span>

* <span data-ttu-id="a0c03-140">Návrhár poskytuje [Modul Export údajov](/azure/machine-learning/algorithm-module-reference/export-data), ktorý umožňuje export výstupu kanála do ukladacieho priestoru Azure.</span><span class="sxs-lookup"><span data-stu-id="a0c03-140">The designer provides the [Export Data module](/azure/machine-learning/algorithm-module-reference/export-data) that allows the output of a pipeline to be exported to Azure storage.</span></span> <span data-ttu-id="a0c03-141">V súčasnosti musí modul používať typ údajového súboru **Úložisko Azure Blob** a parametrizovať **Údajový súbor** a relatívny **Postup**.</span><span class="sxs-lookup"><span data-stu-id="a0c03-141">Currently, the module must use the datastore type **Azure Blob Storage** and parameterize the **Datastore** and relative **Path**.</span></span> <span data-ttu-id="a0c03-142">Customer Insights prepíše oba tieto parametre počas vykonávania kanála na dátový súbor a postup, ktoré sú pre produkt prístupné.</span><span class="sxs-lookup"><span data-stu-id="a0c03-142">Customer Insights overrides both these parameters during pipeline execution with a datastore and path that is accessible to the product.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="a0c03-143">![Konfigurácia modulu Export údajov](media/intelligence-designer-importdata.png "Konfigurácia modulu Export údajov")</span><span class="sxs-lookup"><span data-stu-id="a0c03-143">![Export Data Module Configuration](media/intelligence-designer-importdata.png "Export Data Module Configuration")</span></span>
   
* <span data-ttu-id="a0c03-144">Pri zápise predikcie pomocou kódu môžete nahrať výstup do postupu v rámci *registrovaného údajového súboru* v pracovnom priestore.</span><span class="sxs-lookup"><span data-stu-id="a0c03-144">When writing the inference output using code, you can upload the output to the a path within a *registered datastore* in the workspace.</span></span> <span data-ttu-id="a0c03-145">Ak je postup a údajový súbor parametrizovaný v rámci kanála, Customer Insights bude môcť načítať a importovať výstup predikcie.</span><span class="sxs-lookup"><span data-stu-id="a0c03-145">If the path and datastore are parameterized in the pipeline, Customer insights will be able to read and import the inference output.</span></span> <span data-ttu-id="a0c03-146">V súčasnosti je podporovaný jeden tabuľkový výstup vo formáte .csv.</span><span class="sxs-lookup"><span data-stu-id="a0c03-146">Currently, a single tabular output in csv format is supported.</span></span> <span data-ttu-id="a0c03-147">Postup musí obsahovať adresár a názov súboru.</span><span class="sxs-lookup"><span data-stu-id="a0c03-147">The path must include the directory and filename.</span></span>

   ```python
   # In Pipeline setup script
      OutputPathParameter = PipelineParameter(name="output_path", default_value="HotelChurnOutput/HotelChurnOutput.csv")
      OutputDatastoreParameter = PipelineParameter(name="output_datastore", default_value="workspaceblobstore")
   ...
   # In pipeline execution script
      run = Run.get_context()
      ws = run.experiment.workspace
      datastore = Datastore.get(ws, output_datastore) # output_datastore is parameterized
      directory_name =  os.path.dirname(output_path)  # output_path is parameterized.
      
      # Datastore.upload() or Dataset.File.upload_directory() are supported methods to uplaod the data
      # datastore.upload(src_dir=<<working directory>>, target_path=directory_name, overwrite=False, show_progress=True)
      output_dataset = Dataset.File.upload_directory(src_dir=<<working directory>>, target = (datastore, directory_name)) # Remove trailing "/" from directory_name
   ```


[!INCLUDE[footer-include](../includes/footer-banner.md)]