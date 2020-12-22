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
# <a name="custom-machine-learning-models"></a>Vlastné modely strojového učenia

**Inteligencia** > **Vlastné modely** umožňuje spravovať pracovné postupy založené na modeloch strojového učenia Azure. Pracovné postupy vám pomôžu vybrať údaje, z ktorých chcete generovať prehľady, a namapovať výsledky na vaše zjednotené údaje o zákazníkoch. Ďalšie informácie o vytváraní vlastných modelov ML nájdete v sekcii [Používajte modely založené na strojovom učení platformy Azure](azure-machine-learning-experiments.md).

## <a name="responsible-ai"></a>Zodpovedná AI

Predikcie ponúkajú možnosti na vytváranie lepších zákazníckych prostredí, zlepšovanie obchodných schopností a prehľadov o výnosoch. Dôrazne odporúčame, aby ste vyvážili hodnotu svojej predikcie vo vzťahu k jej vplyvu a nedostatkom, ktoré môžu vzniknúť etickým spôsobom. Zistite viac o tom, ako sa spoločnosť Microsoft [rieši zodpovednú AI](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6). Môžete sa tiež dozvedieť o [technikách a procesoch pre zodpovedné strojové učenie](https://docs.microsoft.com/azure/machine-learning/concept-responsible-ml) špecifických pre strojové učenie platformy Azure.

## <a name="prerequisites"></a>Predpoklady

- Táto funkcia v súčasnosti podporuje webové služby publikované cez [strojové učenie Studio (klasické)](https://studio.azureml.net) a [hromadné kanály strojového učenia platformy Azure](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines).

- Ak chcete používať túto funkciu, potrebujete účet ukladacieho priestoru Azure Data Lake Gen2 spojený s inštanciou platformy Azure Studio. Ďalšie informácie nájdete v časti [Vytvorenie účtu úložiska Azure Data Lake Storage Gen2](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-quickstart-create-account)

## <a name="add-a-new-workflow"></a>Pridajte nový pracovný postup

1. Prejdite do ponuky **Analýza** > **Vlastné modely** a vyberte **Nový pracovný postup**.

1. Do poľa **Názov** zadajte rozpoznateľný názov vlastného modelu.

   > [!div class="mx-imgBorder"]
   > ![Snímka obrazovky tably Nový pracovný postup](media/new-workflowv2.png "Snímka obrazovky tably Nový pracovný postup")

1. V ponuke **Nájomník, ktorý obsahuje vašu webovú službu**, vyberte organizáciu, ktorá obsahuje webovú službu.

1. Ak je vaše predplatné strojového učenia platformy Azure u iného nájomníka ako Customer Insights, vyberte položku **Prihlásiť sa** s vašimi povereniami pre vybratú organizáciu.

1. Vyberte **Pracovné priestory** spojené s vašou webovou službou. Uvedené sú dve sekcie, jedna pre strojové učenie platformy Azure v1 (strojové učenie Studio (klasická)) a jedna pre strojové učenie platformy Azure v2 (strojové učenie platformy Azure). Ak si nie ste istí, ktorý pracovný priestor je ten pravý pre vašu webovú službu strojového učenia Studio (klasického), vyberte položku **Ľubovoľné**.

1. Vyberte webovú službu strojového učenia Studio (klasického) alebo kanál strojového učenia platformy Azure v rozbaľovacej ponuke **Webová služba, ktorá obsahuje váš model**. Potom vyberte položku **Ďalej**.
   - Zistite viac o [publikovaní webovej služby v strojovom učení Studio (klasickom)](https://docs.microsoft.com/azure/machine-learning/studio/deploy-a-machine-learning-web-service#deploy-it-as-a-new-web-service)
   - Zistite viac o [publikovaní kanálu v strojovom učení platformy Azure pomocou návrhára](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) alebo [súpravy SDK](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk). 
     > [!NOTE]
     > Váš kanál musí byť zverejnený pod [koncovým bodom kanála](https://docs.microsoft.com/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run).

1. Pre každý **Vstup webovej služby** vyberte zhodnú položku **Entita** v rámci prehľadov cieľových skupín a vyberte položku **Ďalej**.

   > [!div class="mx-imgBorder"]
   > ![Konfigurácia pracovného postupu](media/intelligence-screen2-updated.png "Konfigurácia pracovného postupu")

1. V rámci kroku **Parametre modelového výstupu** nastavte nasledujúce vlastnosti:
   - Strojové učenie Studio (klasické)
      1. Zadajte **Názov entity** výstupu, do ktorého majú prúdiť výsledky výstupu webových služieb.
   - Strojové učenie platformy Azure
      1. Zadajte **Názov entity** výstupu, do ktorého majú prúdiť výsledky výstupu kanálov.
      1. Vyberte **Názov parametra ukladacieho priestoru výstupných údajov** vášho hromadného kanála z rozbaľovacej ponuky.
      1. Vyberte **Názov parametra postupu výstupných údajov** vášho hromadného kanála z rozbaľovacej ponuky.
      
      > [!div class="mx-imgBorder"]
      > ![Tabla parametrov modelového výstupu](media/intelligence-screen3-outputparameters.png "Tabla parametrov modelového výstupu")

1. Vyberte zodpovedajúci atribút z rozbaľovacieho zoznamu **ID zákazníka vo výsledkoch**, ktorý identifikuje zákazníkov, a vyberte položku **Uložiť**.
   
   > [!div class="mx-imgBorder"]
   > ![Spárovanie výsledkov s tablou údajov o zákazníkoch](media/intelligence-screen4-relatetocustomer.png "Spárovanie výsledkov s tablou údajov o zákazníkoch")

1. Zobrazí sa obrazovka **Pracovný postup bol uložený** s podrobnosťami o pracovnom postupe.    
   Ak ste nakonfigurovali pracovný postup pre kanál strojového učenia platformy Azure, prehľady cieľových skupín sa pripoja k pracovnému priestoru, ktorý obsahuje kanál. Prehľady cieľových skupín získajú rolu **Prispievateľ** v pracovnom priestore platformy Azure.

1. Vyberte **Hotovo**.

1. Teraz môžete spustiť pracovný postup zo stránky **Vlastné modely**.

## <a name="edit-a-workflow"></a>Upraviť pracovný postup

1. Na stránke **Vlastné modely** vyberte zvislé tri bodky v stĺpci **Akcie** vedľa pracovného postupu, ktorý ste predtým vytvorili, a vyberte **Upraviť**.

1. Rozpoznateľný názov svojho pracovného postupu môžete aktualizovať v poli **Zobrazovaný názov**, ale nakonfigurovanú webovú službu alebo kanál nemôžete zmeniť. Vyberte **Ďalej**.

1. Pre každý **Vstup webovej služby** môžete aktualizovať zhodnú položku **Entita** v rámci prehľadov cieľových skupín. Potom vyberte položku **Ďalej**.

1. V rámci kroku **Parametre modelového výstupu** nastavte nasledujúce vlastnosti:
   - Strojové učenie Studio (klasické)
      1. Zadajte **Názov entity** výstupu, do ktorého majú prúdiť výsledky výstupu webových služieb.
   - Strojové učenie platformy Azure
      1. Zadajte **Názov entity** výstupu, do ktorého majú prúdiť výsledky výstupu kanálov.
      1. Vyberte položku **Názov parametra ukladacieho priestoru výstupných údajov** pre váš testovací kanál.
      1. Vyberte položku **Názov parametra ukladacieho priestoru postupu** pre váš testovací kanál.

1. Vyberte zodpovedajúci atribút z rozbaľovacieho zoznamu **ID zákazníka vo výsledkoch**, ktorý identifikuje zákazníkov, a vyberte položku **Uložiť**.
   Musíte si zvoliť atribút z výstupu predikcie s hodnotami podobnými ako v stĺpci ID zákazníka v rámci entity Zákazník. Ak takýto stĺpec vo svojej množine údajov nemáte, vyberte atribút, ktorý jednoznačne identifikuje daný riadok.

## <a name="run-a-workflow"></a>Spustenie pracovného postupu

1. Na stránke **Vlastné modely** vyberte zvislé tri bodky v stĺpci **Akcie** vedľa pracovného postupu, ktorý ste predtým vytvorili.

1. Vyberte položku **Spustiť**.

Váš pracovný postup sa tiež spustí automaticky pri každej plánovanej aktualizácii. Zistite viac o [nastavovaní naplánovaného obnovovania](system.md#schedule-tab).

## <a name="delete-a-workflow"></a>Odstrániť pracovný postup

1. Na stránke **Vlastné modely** vyberte zvislé tri bodky v stĺpci **Akcie** vedľa pracovného postupu, ktorý ste predtým vytvorili.

1. Vyberte možnosť **Odstrániť** a odstránenie potvrďte.

Váš pracovný postup bude odstránený. [Entita](entities.md), ktorá bola vytvorená pri vytvorení pracovného postupu, sa uchová a bude sa dať zobraziť na stránke **Entity**.
