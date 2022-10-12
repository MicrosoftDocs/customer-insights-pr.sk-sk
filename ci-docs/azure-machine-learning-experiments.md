---
title: Používajte modely založené na strojovom učení platformy Azure
description: Používajte modely založené na strojovom učení platformy Azure v službe Dynamics 365 Customer Insights.
ms.date: 09/22/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: naravill
ms.author: naravill
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 8d9c9324ea4840b585b9af1a58d505ccaea6f18e
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 09/30/2022
ms.locfileid: "9609844"
---
# <a name="use-azure-machine-learning-based-models"></a>Používajte modely založené na strojovom učení platformy Azure

Zjednotené údaje v službe Dynamics 365 Customer Insights sú zdrojom pre vytváranie modelov strojového učenia, ktoré môžu generovať ďalšie obchodné prehľady. Customer Insights sa integrujú do služby strojového učenia Azure, aby ste mohli používať svoje vlastné modely.

## <a name="prerequisites"></a>Predpoklady

- Prístup do Customer Insights
- Aktívne predplatné Azure Enterprise
- [Zjednotené profily zákazníka](data-unification.md)
- [Export entít do úložiska Azure Blob](export-azure-blob-storage.md) je nakonfigurovaný

## <a name="set-up-azure-machine-learning-workspace"></a>Nastavte pracovný priestor strojového učenia platformy Azure

1. V sekcii [Vytvorenie pracovného priestoru služby strojového učenia platformy Azure](/azure/machine-learning/concept-workspace#-create-a-workspace) nájdete rôzne možnosti na vytvorenie pracovného priestoru. S cieľom dosiahnuť čo najlepší výkon vytvorte pracovný priestor v oblasti platformy Azure, ktorá je geograficky najbližšie k vášmu prostrediu služby Customer Insights.

1. Získajte prístup do vášho pracovného priestoru prostredníctvom služby [strojového učenia platformy Azure Studio](https://ml.azure.com/). Existuje niekoľko [spôsobov interakcie](/azure/machine-learning/concept-workspace#tools-for-workspace-interaction) s vaším pracovným priestorom.

## <a name="work-with-azure-machine-learning-designer"></a>Spolupracujte s návrhárom služby strojového učenia platformy Azure

Návrhár Azure strojové učenie poskytuje vizuálne plátno, kde môžete presúvať množiny údajov a moduly. Hromadný kanál vytvorený návrhárom možno integrovať do služby Customer Insights, ak je zodpovedajúcim spôsobom nakonfigurovaný. 

## <a name="working-with-azure-machine-learning-sdk"></a>Práca so súpravou SDK služby strojového učenia platformy Azure

Dátoví vedci a vývojári umelej inteligencie používajú [súpravu SDK strojového učenia platformy Azure](/python/api/overview/azure/ml/?preserve-view=true&view=azure-ml-py) na vytváranie pracovných postupov strojového učenia. V súčasnosti nemožno modely trénované pomocou súpravy SDK integrovať priamo do služby Customer Insights. Na integráciu do služby Customer Insights je potrebný kanál hromadnej predikcie, ktorý tento model využíva.

## <a name="batch-pipeline-requirements-to-integrate-with-customer-insights"></a>Požiadavky na integráciu hromadného kanála so službou Customer Insights

### <a name="dataset-configuration"></a>Konfigurácia množiny údajov

Vytvorte množiny údajov na použitie údajov entity zo Customer Insights pre váš dávkový odvodňovací kanál. Zaregistrujte tieto množiny údajov v pracovnom priestore. Momentálne podporujeme iba [tabuľkové množiny údajov](/azure/machine-learning/how-to-create-register-datasets#tabulardataset) vo formáte .csv. Parametrizujte množiny údajov, ktoré zodpovedajú údajom entity, ako parameter kanála.

- Parametre množiny údajov v Návrhárovi

  V návrhárovi otvorte sekciu **Vybrať stĺpce v množine údajov** a vyberte položku **Nastaviť ako parameter kanála**, kde zadáte názov parametra.

  :::image type="content" source="media/intelligence-designer-dataset-parameters.png" alt-text="Parametrizácia množiny údajov v návrhárovi.":::

- Parameter množiny údajov v súprave SDK (Python)

   ```python
   HotelStayActivity_dataset = Dataset.get_by_name(ws, name='Hotel Stay Activity Data')
   HotelStayActivity_pipeline_param = PipelineParameter(name="HotelStayActivity_pipeline_param", default_value=HotelStayActivity_dataset)
   HotelStayActivity_ds_consumption = DatasetConsumptionConfig("HotelStayActivity_dataset", HotelStayActivity_pipeline_param)
   ```

### <a name="batch-inference-pipeline"></a>Kanál hromadnej predikcie
  
- V návrhárovi použite tréningový kanál na vytvorenie alebo aktualizáciu odvodeného kanála. V súčasnosti sú podporované iba kanály hromadnej predikcie.

- Pomocou súpravy SDK zverejnite kanál do koncového bodu. V súčasnosti sa služba Customer Insights integruje s predvoleným kanálom do koncového bodu hromadného kanála v pracovnom priestore na strojové učenie.

   ```python
   published_pipeline = pipeline.publish(name="ChurnInferencePipeline", description="Published Churn Inference pipeline")
   pipeline_endpoint = PipelineEndpoint.get(workspace=ws, name="ChurnPipelineEndpoint") 
   pipeline_endpoint.add_default(pipeline=published_pipeline)
   ```

### <a name="import-pipeline-data-into-customer-insights"></a>Importujte údaje o kanáli do služby Customer Insights

- Návrhár poskytuje [Modul Export údajov](/azure/machine-learning/algorithm-module-reference/export-data), ktorý umožňuje export výstupu kanála do ukladacieho priestoru Azure. V súčasnosti musí modul používať typ údajového súboru **Úložisko Azure Blob** a parametrizovať **Údajový súbor** a relatívny **Postup**. Customer Insights prepíše oba tieto parametre počas vykonávania kanála na dátový súbor a postup, ktoré sú pre produkt prístupné.

  :::image type="content" source="media/intelligence-designer-importdata.png" alt-text="Konfigurácia modulu Export údajov.":::

- Pri písaní odvodeného výstupu pomocou kódu odovzdajte výstup do cesty v rámci a *registrované dátové úložisko* v pracovnom priestore. Ak je postup a údajový súbor parametrizovaný v rámci kanála, Customer Insights bude môcť načítať a importovať výstup predikcie. V súčasnosti je podporovaný jeden tabuľkový výstup vo formáte .csv. Postup musí obsahovať adresár a názov súboru.

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


[!INCLUDE [footer-include](includes/footer-banner.md)]