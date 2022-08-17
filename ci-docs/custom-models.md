---
title: Vlastné modely strojového učenia | Dokumentácia spoločnosti Microsoft
description: Práca s vlastnými modelmi zo strojového učenia platformy Azure v systéme Dynamics 365 Customer Insights.
ms.date: 12/01/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: tutorial
author: zacookmsft
ms.author: zacook
manager: shellyha
searchScope:
- ci-custom-models
- customerInsights
ms.openlocfilehash: 3fad8a6cba71da80d4cc34be4084275e0d0a3622
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 08/10/2022
ms.locfileid: "9245822"
---
# <a name="custom-machine-learning-models"></a>Vlastné modely strojového učenia

> [!NOTE]
> Podpora pre strojové učenie Studio (klasické) sa skončí 31. augusta 2024. Odporúčame vám prejsť na [Azure strojové učenie](/azure/machine-learning/overview-what-is-azure-machine-learning) do tohto dátumu.
>
> Od 1. decembra 2021 nebudete môcť vytvárať nové zdroje strojové učenie Studio (klasické). Do 31. augusta 2024 môžete naďalej používať existujúce zdroje strojové učenie Studio (klasické). Viac informácií nájdete v časti [Migrujte do Azure strojové učenie](/azure/machine-learning/migrate-overview).


**Inteligencia** > **Vlastné modely** umožňuje spravovať pracovné postupy založené na modeloch strojového učenia Azure. Pracovné postupy vám pomôžu vybrať údaje, z ktorých chcete generovať prehľady, a namapovať výsledky na vaše zjednotené údaje o zákazníkoch. Ďalšie informácie o vytváraní vlastných modelov ML nájdete v sekcii [Používajte modely založené na strojovom učení platformy Azure](azure-machine-learning-experiments.md).

## <a name="responsible-ai"></a>Zodpovedná AI

Predikcie ponúkajú možnosti na vytváranie lepších zákazníckych prostredí, zlepšovanie obchodných schopností a prehľadov o výnosoch. Dôrazne odporúčame, aby ste vyvážili hodnotu svojej predikcie vo vzťahu k jej vplyvu a nedostatkom, ktoré môžu vzniknúť etickým spôsobom. Zistite viac o tom, ako sa spoločnosť Microsoft [rieši zodpovednú AI](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6). Môžete sa tiež dozvedieť o [technikách a procesoch pre zodpovedné strojové učenie](/azure/machine-learning/concept-responsible-ml) špecifických pre strojové učenie platformy Azure.

## <a name="prerequisites"></a>Požiadavky

- Táto funkcia podporuje webové služby publikované prostredníctvom [Dávkové potrubia Azure strojové učenie](/azure/machine-learning/concept-ml-pipelines).

- Ak chcete používať túto funkciu, potrebujete účet ukladacieho priestoru Azure Data Lake Gen2 spojený s inštanciou platformy Azure Studio. Ďalšie informácie nájdete v časti [Vytvorenie účtu úložiska Azure Data Lake Storage Gen2](/azure/storage/blobs/data-lake-storage-quickstart-create-account).

- Pre strojové učenie pracovných priestorov Azure s kanálmi potrebujete oprávnenie vlastníka alebo správcu prístupu používateľov do pracovného priestoru strojového učenia Azure.

   > [!NOTE]
   > Údaje sa prenášajú medzi vašimi inštanciami Customer Insights a vybranými webovými službami alebo kanálmi Azure v pracovnom postupe. Pri prenose údajov do služby Azure sa ubezpečte, že služba je nakonfigurovaná tak, aby spracovávala údaje takým spôsobom a na takom mieste, ktoré sú potrebné na dodržanie súladu so všetkými právnymi alebo regulačnými požiadavkami vzťahujúcimi sa na tieto údaje a vašu organizáciu.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWRElk]

## <a name="add-a-new-workflow"></a>Pridajte nový pracovný postup

1. Prejdite do ponuky **Analýza** > **Vlastné modely** a vyberte **Nový pracovný postup**.

1. Do poľa **Názov** zadajte rozpoznateľný názov vlastného modelu.

   > [!div class="mx-imgBorder"]
   > ![Snímka obrazovky tably Nový pracovný postup.](media/new-workflowv2.png "Snímka obrazovky tably Nový pracovný postup")

1. V ponuke **Nájomník, ktorý obsahuje vašu webovú službu**, vyberte organizáciu, ktorá obsahuje webovú službu.

1. Ak je vaše predplatné strojového učenia platformy Azure u iného nájomníka ako Customer Insights, vyberte položku **Prihlásiť sa** s vašimi povereniami pre vybratú organizáciu.

1. Vyberte **Pracovné priestory** spojené s vašou webovou službou. 

1. Vyberte si potrubie strojové učenie Azure v **Webová služba, ktorá obsahuje váš model** rozbaľovacia ponuka. Potom vyberte položku **Ďalej**.    
   Zistite viac o [publikovaní kanálu v strojovom učení platformy Azure pomocou návrhára](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) alebo [súpravy SDK](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk). Váš kanál musí byť zverejnený pod [koncovým bodom kanála](/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run).

1. Pre každý **Vstup webovej služby** vyberte zhodnú položku **Entita** v rámci Customer Insights a následne vyberte položku **Ďalej**.
   > [!NOTE]
   > Pracovný postup vlastného modelu použije heuristiku na mapovanie vstupných polí webovej služby na atribúty entít na základe názvu a dátového typu poľa. Ak pole webovej služby nemožno priradiť k entite, zobrazí sa chyba.

   > [!div class="mx-imgBorder"]
   > ![Konfigurácia pracovného postupu.](media/intelligence-screen2-updated.png "Konfigurácia pracovného postupu")

1. V rámci kroku **Parametre modelového výstupu** nastavte nasledujúce vlastnosti:
      1. Zadajte **Názov entity** výstupu, do ktorého majú prúdiť výsledky výstupu kanálov.
      1. Vyberte **Názov parametra ukladacieho priestoru výstupných údajov** vášho hromadného kanála z rozbaľovacej ponuky.
      1. Vyberte **Názov parametra postupu výstupných údajov** vášho hromadného kanála z rozbaľovacej ponuky.

      > [!div class="mx-imgBorder"]
      > ![Tabla parametrov modelového výstupu.](media/intelligence-screen3-outputparameters.png "Tabla parametrov modelového výstupu")

1. Vyberte zodpovedajúci atribút z rozbaľovacieho zoznamu **ID zákazníka vo výsledkoch**, ktorý identifikuje zákazníkov, a vyberte možnosť **Uložiť**.

   > [!div class="mx-imgBorder"]
   > ![Spárovanie výsledkov s tablou údajov o zákazníkoch.](media/intelligence-screen4-relatetocustomer.png "Spárovanie výsledkov s tablou údajov o zákazníkoch")

1. Zobrazí sa obrazovka **Pracovný postup bol uložený** s podrobnosťami o pracovnom postupe.    
   Ak ste nakonfigurovali pracovný tok pre kanál strojové učenie Azure, Customer Insights sa pripojí k pracovnému priestoru, ktorý obsahuje kanál. Customer Insights získajú a **Prispievateľ** rolu na pracovnom priestore Azure.

1. Vyberte **Hotovo**.

1. Teraz môžete spustiť pracovný postup zo stránky **Vlastné modely**.

## <a name="edit-a-workflow"></a>Upraviť pracovný postup

1. Na **Vlastné modely** stránku, vyberte zvislú elipsu (&vellip;) v **Akcie** vedľa pracovného postupu, ktorý ste predtým vytvorili, a vyberte ho **Upraviť**.

1. Rozpoznateľný názov svojho pracovného postupu môžete aktualizovať v poli **Zobrazovaný názov**, ale nakonfigurovanú webovú službu alebo kanál nemôžete zmeniť. Vyberte **Ďalej**.

1. Pre každý **Vstup webovej služby**, môžete aktualizovať priraďovanie **Entita** z Customer Insights. Potom vyberte položku **Ďalej**.

1. V rámci kroku **Parametre modelového výstupu** nastavte nasledujúce vlastnosti:
      1. Zadajte **Názov entity** výstupu, do ktorého majú prúdiť výsledky výstupu kanálov.
      1. Vyberte položku **Názov parametra ukladacieho priestoru výstupných údajov** pre váš testovací kanál.
      1. Vyberte položku **Názov parametra ukladacieho priestoru postupu** pre váš testovací kanál.

1. Vyberte zodpovedajúci atribút z rozbaľovacieho zoznamu **ID zákazníka vo výsledkoch**, ktorý identifikuje zákazníkov, a vyberte možnosť **Uložiť**.
   Zvoľte si atribút z výstupu predikcie s hodnotami podobnými ako v stĺpci ID zákazníka v rámci entity Zákazník. Ak takýto stĺpec vo svojej množine údajov nemáte, vyberte atribút, ktorý jednoznačne identifikuje daný riadok.

## <a name="run-a-workflow"></a>Spustenie pracovného postupu

1. Na **Vlastné modely** stránku, vyberte zvislú elipsu (&vellip;) v **Akcie** vedľa pracovného postupu, ktorý ste predtým vytvorili.

1. Vyberte položku **Spustiť**.

Váš pracovný postup sa tiež spustí automaticky pri každej plánovanej aktualizácii. Zistite viac o [nastavovaní naplánovaného obnovovania](schedule-refresh.md).

## <a name="delete-a-workflow"></a>Odstrániť pracovný postup

1. Na **Vlastné modely** stránku, vyberte zvislú elipsu (&vellip;) v **Akcie** vedľa pracovného postupu, ktorý ste predtým vytvorili.

1. Vyberte možnosť **Odstrániť** a odstránenie potvrďte.

Váš pracovný postup bude odstránený. [Entita](entities.md), ktorá bola vytvorená pri vytvorení pracovného postupu, sa uchová a bude sa dať zobraziť na stránke **Entity**.

## <a name="results"></a>Výsledky

Výsledky z pracovného postupu sú uložené v entite nakonfigurovanej počas fázy parametra výstupného modelu. K týmto údajom môžete získať prístup zo [stránky entít](entities.md) alebo pomocou [prístupu API](apis.md).

### <a name="api-access"></a>Prístup API

Pre konkrétny dopyt OData na získanie údajov z entity vlastného modelu použite nasledujúci formát:

`https://api.ci.ai.dynamics.com/v1/instances/<your instance id>/data/<custom model output entity name>%3Ffilter%3DCustomerId%20eq%20'<guid value>'`

1. Vymeňte `<your instance id>` za ID vášho prostredia Customer Insights, ktoré nájdete v paneli s adresou prehliadača pri prístupe k Customer Insights.

1. Vymeňte `<custom model output entity>` za názvom entity, ktorý ste zadali počas kroku parametrov výstupných parametrov konfigurácie vlastného modelu.

1. Vymeňte `<guid value>` za ID zákazníka, pre ktorého chcete získať prístup k záznamu. Spravidla nájdete toto ID na [stránke s profilmi zákazníkov](customer-profiles.md) v poli CustomerID.

## <a name="frequently-asked-questions"></a>Najčastejšie otázky

- Prečo nevidím svoj kanál pri nastavovaní pracovného postupu vlastného modelu?    
  Tento problém je často spôsobený problémom s konfiguráciou v kanáli. Zaistite [konfiguráciu vstupného parametra](azure-machine-learning-experiments.md#dataset-configuration) a konfiguráciu [výstupných parametrov dátového úložiska a cesty](azure-machine-learning-experiments.md#import-pipeline-data-into-customer-insights).

- Čo znamená chyba „Nemôžem uložiť pracovný postup analýzy“?    
  Používateľom sa toto chybové hlásenie zvyčajne zobrazí, ak v pracovnom priestore nemajú oprávnenie vlastníka alebo správcu prístupu používateľov. Používateľ potrebuje vyššiu úroveň povolení, aby umožnil Customer Insights spracovať pracovný postup ako službu, a nie používať prihlasovacie údaje používateľa na ďalšie spustenia pracovného postupu.

[!INCLUDE [footer-include](includes/footer-banner.md)]
