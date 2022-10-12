---
title: Vlastné modely strojového učenia | Dokumentácia spoločnosti Microsoft
description: Práca s vlastnými modelmi zo strojového učenia platformy Azure v systéme Dynamics 365 Customer Insights.
ms.date: 09/19/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: tutorial
author: zacookmsft
ms.author: zacook
manager: shellyha
searchScope:
- ci-custom-models
- customerInsights
ms.openlocfilehash: 89553b511d249fd586e36a1c4944a977513b0643
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 09/30/2022
ms.locfileid: "9609765"
---
# <a name="custom-machine-learning-models"></a>Vlastné modely strojového učenia

> [!NOTE]
> Podpora pre strojové učenie Studio (klasické) sa skončí 31. augusta 2024. Odporúčame vám prejsť na [Azure strojové učenie](/azure/machine-learning/overview-what-is-azure-machine-learning) do tohto dátumu.
>
> Od 1. decembra 2021 nebudete môcť vytvárať nové zdroje strojové učenie Studio (klasické). Do 31. augusta 2024 môžete naďalej používať existujúce zdroje strojové učenie Studio (klasické). Ďalšie informácie nájdete v časti [Migrujte do Azure strojové učenie](/azure/machine-learning/migrate-overview).

Vlastné modely vám umožňujú spravovať pracovné postupy založené na modeloch Azure strojové učenie. Pracovné postupy vám pomôžu vybrať údaje, z ktorých chcete generovať prehľady, a namapovať výsledky na vaše zjednotené údaje o zákazníkoch. Ďalšie informácie o vytváraní vlastných modelov ML nájdete v sekcii [Používajte modely založené na strojovom učení platformy Azure](azure-machine-learning-experiments.md).

## <a name="prerequisites"></a>Požiadavky

- Webové služby publikované prostredníctvom [Dávkové potrubia Azure strojové učenie](/azure/machine-learning/concept-ml-pipelines).
- Potrubie musí byť zverejnené pod a [koncový bod potrubia](/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run).
- An [Účet úložiska Azure Data Lake Gen2](/azure/storage/blobs/data-lake-storage-quickstart-create-account) priradené k vašej inštancii Azure Studio.
- Pre strojové učenie pracovné priestory Azure s kanálmi majú povolenia vlastníka alebo správcu prístupu k pracovnému priestoru Azure strojové učenie.

  > [!NOTE]
  > Údaje sa prenášajú medzi vašimi inštanciami Customer Insights a vybranými webovými službami alebo kanálmi Azure v pracovnom postupe. Pri prenose údajov do služby Azure sa ubezpečte, že služba je nakonfigurovaná tak, aby spracovávala údaje takým spôsobom a na takom mieste, ktoré sú potrebné na dodržanie súladu so všetkými právnymi alebo regulačnými požiadavkami vzťahujúcimi sa na tieto údaje a vašu organizáciu.

## <a name="add-a-new-workflow"></a>Pridajte nový pracovný postup

1. Prejdite do ponuky **Analýza** > **Vlastné modely** a vyberte **Nový pracovný postup**.

1. Poskytnite rozpoznateľný **názov**.

   :::image type="content" source="media/new-workflowv2.png" alt-text="Snímka obrazovky tably Nový pracovný postup.":::

1. V ponuke **Nájomník, ktorý obsahuje vašu webovú službu**, vyberte organizáciu, ktorá obsahuje webovú službu.

1. Ak je vaše predplatné strojového učenia platformy Azure u iného nájomníka ako Customer Insights, vyberte položku **Prihlásiť sa** s vašimi povereniami pre vybratú organizáciu.

1. Vyberte **Pracovné priestory** spojené s vašou webovou službou.

1. Vyberte si potrubie strojové učenie Azure v **Webová služba, ktorá obsahuje váš model** rozbaľovacia ponuka. Potom vyberte položku **Ďalej**.
   Zistite viac o [publikovaní kanálu v strojovom učení platformy Azure pomocou návrhára](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) alebo [súpravy SDK](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk).

1. Pre každý **Vstup webovej služby** vyberte zhodnú položku **Entita** v rámci Customer Insights. Potom vyberte položku **Ďalej**.
   > [!NOTE]
   > Pracovný postup vlastného modelu použije heuristiku na mapovanie vstupných polí webovej služby na atribúty entít na základe názvu a dátového typu poľa. Ak pole webovej služby nemožno priradiť k entite, zobrazí sa chyba.

   :::image type="content" source="media/intelligence-screen2-updated.png" alt-text="Konfigurácia pracovného postupu.":::

1. Pre **Výstupné parametre modelu**, nastavte nasledujúce vlastnosti:
   - **Názov entity** pre výsledky výstupu potrubia
   - **Výstup ukladací priestor údajov názov parametra** vášho dávkového potrubia
   - **Názov parametra výstupnej cesty** vášho dávkového potrubia

   :::image type="content" source="media/intelligence-screen3-outputparameters.png" alt-text="Tabla parametrov modelového výstupu.":::

1. Vyberte zodpovedajúci atribút z **ID zákazníka vo výsledkoch** ktorý identifikuje zákazníkov a vyberie **Uložiť**.

   :::image type="content" source="media/intelligence-screen4-relatetocustomer.png" alt-text="Spárovanie výsledkov s tablou údajov o zákazníkoch.":::

   The **Pracovný postup bol uložený** obrazovka zobrazuje podrobnosti o pracovnom postupe. Ak ste nakonfigurovali pracovný tok pre kanál Azure strojové učenie, Customer Insights sa pripojí k pracovnému priestoru, ktorý obsahuje kanál. Customer Insights získajú a **Prispievateľ** rolu na pracovnom priestore Azure.

1. Vyberte položku **Hotovo**. The **Vlastné modely** zobrazí stránka.

1. Vyberte zvislú elipsu (&vellip;) pre pracovný postup a vyberte **Bežať**. Váš pracovný postup tiež beží automaticky s každým [plánované obnovenie](schedule-refresh.md).

## <a name="manage-an-existing-workflow"></a>Spravujte existujúci pracovný postup

Ísť do **Inteligencia** > **Vlastné modely** na zobrazenie pracovných postupov, ktoré ste vytvorili.

Ak chcete zobraziť dostupné akcie, vyberte pracovný postup.

- **Upraviť** pracovný postup
- **Bežať** pracovný postup
- [**Odstrániť**](#delete-a-workflow) pracovný postup

### <a name="edit-a-workflow"></a>Upraviť pracovný postup

1. Ísť do **Inteligencia** > **Vlastné modely**.

1. Vedľa pracovného postupu, ktorý chcete aktualizovať, vyberte zvislú elipsu (&vellip;) a vyberte **Upraviť**.

1. Zmeniť **Zobraziť meno** v prípade potreby a vyberte **Ďalšie**.

1. Pre každý **Vstup webovej služby**, aktualizujte párovanie **Entita** v prípade potreby zo služby Customer Insights. Potom vyberte položku **Ďalej**.

1. Pre **Výstupné parametre modelu**, zmeňte niektorú z nasledujúcich možností:
   - **Názov entity** pre výsledky výstupu potrubia
   - **Výstup ukladací priestor údajov názov parametra** vášho dávkového potrubia
   - **Názov parametra výstupnej cesty** vášho dávkového potrubia

1. Zmeňte zodpovedajúci atribút z **ID zákazníka vo výsledkoch** na identifikáciu zákazníkov. Zvoľte si atribút z výstupu predikcie s hodnotami podobnými ako v stĺpci ID zákazníka v rámci entity Zákazník. Ak takýto stĺpec v množine údajov nemáte, vyberte atribút, ktorý jedinečne identifikuje riadok.

1. Stlačte možnosť **Uložiť**

### <a name="delete-a-workflow"></a>Odstrániť pracovný postup

1. Ísť do **Inteligencia** > **Vlastné modely**.

1. Vedľa pracovného postupu, ktorý chcete odstrániť, vyberte zvislú elipsu (&vellip;) a vyberte **Odstrániť**.

1. Potvrďte odstránenie.

Váš pracovný postup bude odstránený. The [subjekt](entities.md) ktorý bol vytvorený pri vytváraní pracovného toku pretrváva a možno ho zobraziť z **Údaje** > **entity** stránku.

## <a name="view-the-results"></a>Pozrite si výsledky

Výsledky z pracovného toku sú uložené v názve entity definovanej pre **Výstupné parametre modelu**. K týmto údajom pristupujte z [**Údaje** > **entity** stránku](entities.md) alebo s [API prístup](apis.md).

### <a name="api-access"></a>Prístup API

Pre konkrétny dopyt OData na získanie údajov z entity vlastného modelu použite nasledujúci formát:

`https://api.ci.ai.dynamics.com/v1/instances/<your instance id>/data/<custom model output entity name>%3Ffilter%3DCustomerId%20eq%20'<guid value>'`

1. Nahradiť`<your instance id>` s ID vášho prostredia Customer Insights, ktoré sa zobrazuje v paneli s adresou vášho prehliadača pri prístupe k Customer Insights.

1. Nahradiť`<custom model output entity>` s názvom entity, ktorý ste poskytli pre **Výstupné parametre modelu**.

1. Nahradiť`<guid value>` s ID zákazníka zákazníka, ku ktorému chcete získať prístup. Toto ID sa zobrazí na [stránka profilov zákazníkov](customer-profiles.md) v poli CustomerID.

## <a name="frequently-asked-questions"></a>Najčastejšie otázky

- Prečo nevidím svoj kanál pri nastavovaní pracovného postupu vlastného modelu?
  Tento problém je často spôsobený problémom s konfiguráciou v kanáli. Zaistite [konfiguráciu vstupného parametra](azure-machine-learning-experiments.md#dataset-configuration) a konfiguráciu [výstupných parametrov dátového úložiska a cesty](azure-machine-learning-experiments.md#import-pipeline-data-into-customer-insights).

- Čo znamená chyba „Nemôžem uložiť pracovný postup analýzy“? 
  Používateľom sa toto chybové hlásenie zvyčajne zobrazí, ak v pracovnom priestore nemajú oprávnenie vlastníka alebo správcu prístupu používateľov. Používateľ potrebuje vyššiu úroveň povolení, aby umožnil Customer Insights spracovať pracovný postup ako službu, a nie používať prihlasovacie údaje používateľa na ďalšie spustenia pracovného postupu.

- Je podporovaný súkromný koncový bod/súkromné prepojenie pre môj pracovný postup vlastného modelu?
  Customer Insights v súčasnosti nepodporuje súkromný koncový bod pre vlastné modely, ale je k dispozícii manuálne riešenie. Podrobnosti vám poskytne podpora.

## <a name="responsible-ai"></a>Zodpovedná AI

Predikcie ponúkajú možnosti na vytváranie lepších zákazníckych prostredí, zlepšovanie obchodných schopností a prehľadov o výnosoch. Dôrazne odporúčame, aby ste vyvážili hodnotu svojej predikcie vo vzťahu k jej vplyvu a nedostatkom, ktoré môžu vzniknúť etickým spôsobom. Zistite viac o tom, ako sa spoločnosť Microsoft [rieši zodpovednú AI](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6). Môžete sa tiež dozvedieť o [technikách a procesoch pre zodpovedné strojové učenie](/azure/machine-learning/concept-responsible-ml) špecifických pre strojové učenie platformy Azure.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWRElk]

[!INCLUDE [footer-include](includes/footer-banner.md)]
