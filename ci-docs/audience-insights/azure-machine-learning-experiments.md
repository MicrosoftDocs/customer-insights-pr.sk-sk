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
ms.openlocfilehash: 4c04a1d08aba152ce91d452ae2300c1ce0fc79e5d6980ac506dc40d9914c9fca
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 08/10/2021
ms.locfileid: "7033191"
---
# <a name="use-azure-machine-learning-based-models"></a>Používajte modely založené na strojovom učení platformy Azure

Zjednotené údaje v službe Dynamics 365 Customer Insights sú zdrojom pre vytváranie modelov strojového učenia, ktoré môžu generovať ďalšie obchodné prehľady. Customer Insights sa integruje do služby strojového učenia Studio (klasickej) a do služby strojového učenia platformy Azure, aby ste mohli používať svoje vlastné modely. V sekcii [Pokusy so službou strojového učenia Studio (klasickou)](machine-learning-studio-experiments.md) nájdete príklady pokusov postavených na službe strojového učenia Studio (klasickej). 

## <a name="prerequisites"></a>Predpoklady

- Prístup do Customer Insights
- Aktívne predplatné Azure Enterprise
- [Zjednotené profily zákazníka](data-unification.md)
- [Export entít do úložiska Azure Blob](export-azure-blob-storage.md) je nakonfigurovaný

## <a name="set-up-azure-machine-learning-workspace"></a>Nastavte pracovný priestor strojového učenia platformy Azure

1. V sekcii [Vytvorenie pracovného priestoru služby strojového učenia platformy Azure](/azure/machine-learning/concept-workspace#-create-a-workspace) nájdete rôzne možnosti na vytvorenie pracovného priestoru. S cieľom dosiahnuť čo najlepší výkon vytvorte pracovný priestor v oblasti platformy Azure, ktorá je geograficky najbližšie k vášmu prostrediu služby Customer Insights.

1. Získajte prístup do vášho pracovného priestoru prostredníctvom služby [strojového učenia platformy Azure Studio](https://ml.azure.com/). Existuje niekoľko [spôsobov interakcie](/azure/machine-learning/concept-workspace#tools-for-workspace-interaction) s vaším pracovným priestorom.

## <a name="work-with-azure-machine-learning-designer"></a>Spolupracujte s návrhárom služby strojového učenia platformy Azure

Návrhár služby strojového učenia platformy Azure poskytne vizuálne plátno, do ktorého môžete presúvať množiny údajov a moduly, podobne ako pri službe strojového učenia Studio (klasickú). Hromadný kanál vytvorený návrhárom možno integrovať do služby Customer Insights, ak je zodpovedajúcim spôsobom nakonfigurovaný. 
   
## <a name="working-with-azure-machine-learning-sdk"></a>Práca so súpravou SDK služby strojového učenia platformy Azure

Dátoví vedci a vývojári umelej inteligencie používajú [súpravu SDK strojového učenia platformy Azure](/python/api/overview/azure/ml/?preserve-view=true&view=azure-ml-py) na vytváranie pracovných postupov strojového učenia. V súčasnosti nemožno modely trénované pomocou súpravy SDK integrovať priamo do služby Customer Insights. Na integráciu do služby Customer Insights je potrebný kanál hromadnej predikcie, ktorý tento model využíva.

## <a name="batch-pipeline-requirements-to-integrate-with-customer-insights"></a>Požiadavky na integráciu hromadného kanála so službou Customer Insights

### <a name="dataset-configuration"></a>Konfigurácia množín údajov

Musíte vytvoriť množiny údajov, aby ste mohli používať údaje entít zo služby Customer Insights vo vašom kanáli pre hromadnú predikciu. Tieto množiny údajov je potrebné zaregistrovať v pracovnom priestore. Momentálne podporujeme iba [tabuľkové množiny údajov](/azure/machine-learning/how-to-create-register-datasets#tabulardataset) vo formáte .csv. Množiny údajov, ktoré zodpovedajú údajom entity, je potrebné parametrizovať ako parameter kanála.
   
* Parametre množiny údajov v Návrhárovi
   
     V návrhárovi otvorte sekciu **Vybrať stĺpce v množine údajov** a vyberte položku **Nastaviť ako parameter kanála**, kde zadáte názov parametra.

     > [!div class="mx-imgBorder"]
     > ![Parametrizácia množiny údajov v návrhárovi.](media/intelligence-designer-dataset-parameters.png "Parametrizácia množiny údajov v návrhárovi")
   
* Parameter množiny údajov v súprave SDK (Python)
   
   ```python
   HotelStayActivity_dataset = Dataset.get_by_name(ws, name='Hotel Stay Activity Data')
   HotelStayActivity_pipeline_param = PipelineParameter(name="HotelStayActivity_pipeline_param", default_value=HotelStayActivity_dataset)
   HotelStayActivity_ds_consumption = DatasetConsumptionConfig("HotelStayActivity_dataset", HotelStayActivity_pipeline_param)
   ```

### <a name="batch-inference-pipeline"></a>Kanál hromadnej predikcie
  
* V návrhárovi sa dá tréningový kanál použiť na vytvorenie alebo aktualizáciu kanálu predikcie. V súčasnosti sú podporované iba kanály hromadnej predikcie.

* Pomocou súpravy SDK môžete kanál publikovať do koncového bodu. V súčasnosti sa služba Customer Insights integruje s predvoleným kanálom do koncového bodu hromadného kanála v pracovnom priestore na strojové učenie.
   
   ```python
   published_pipeline = pipeline.publish(name="ChurnInferencePipeline", description="Published Churn Inference pipeline")
   pipeline_endpoint = PipelineEndpoint.get(workspace=ws, name="ChurnPipelineEndpoint") 
   pipeline_endpoint.add_default(pipeline=published_pipeline)
   ```

### <a name="import-pipeline-data-into-customer-insights"></a>Importujte údaje o kanáli do služby Customer Insights

* Návrhár poskytuje [Modul Export údajov](/azure/machine-learning/algorithm-module-reference/export-data), ktorý umožňuje export výstupu kanála do ukladacieho priestoru Azure. V súčasnosti musí modul používať typ údajového súboru **Úložisko Azure Blob** a parametrizovať **Údajový súbor** a relatívny **Postup**. Customer Insights prepíše oba tieto parametre počas vykonávania kanála na dátový súbor a postup, ktoré sú pre produkt prístupné.
   > [!div class="mx-imgBorder"]
   > ![Konfigurácia modulu Export údajov.](media/intelligence-designer-importdata.png "Konfigurácia modulu Export údajov")
   
* Pri zápise predikcie pomocou kódu môžete nahrať výstup do postupu v rámci *registrovaného údajového súboru* v pracovnom priestore. Ak je postup a údajový súbor parametrizovaný v rámci kanála, Customer Insights bude môcť načítať a importovať výstup predikcie. V súčasnosti je podporovaný jeden tabuľkový výstup vo formáte .csv. Postup musí obsahovať adresár a názov súboru.

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