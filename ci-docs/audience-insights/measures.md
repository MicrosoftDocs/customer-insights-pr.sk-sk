---
title: Vytváranie a spravovanie mier
description: Definujte miery na analýzu a zobrazovanie výkonnosti vášho podnikania.
ms.date: 02/02/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: wameng
manager: shellyha
ms.openlocfilehash: 5bcee3b4c51880740715575b18fd7a4dbf87e6d0
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269947"
---
# <a name="define-and-manage-measures"></a><span data-ttu-id="d905e-103">Definovanie a spravovanie mier</span><span class="sxs-lookup"><span data-stu-id="d905e-103">Define and manage measures</span></span>

<span data-ttu-id="d905e-104">Miery vám pomôžu lepšie pochopiť správanie zákazníkov a výkonnosť podnikania načítaním relevantných hodnôt zo [zjednotených profilov](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="d905e-104">Measures help you to better understand customer behaviors and business performance by retrieving relevant values from [unified profiles](data-unification.md).</span></span> <span data-ttu-id="d905e-105">Napríklad firma chce vidieť *celkové výdavky na zákazníka* a pochopiť tak históriu nákupu jednotlivých zákazníkov.</span><span class="sxs-lookup"><span data-stu-id="d905e-105">For example, a business wants to see the *total spend per customer* to understand individual customer’s purchase history.</span></span> <span data-ttu-id="d905e-106">Alebo zmerať *celkový predaj spoločnosti* a porozumieť agregovaným výnosom v celom podnikaní.</span><span class="sxs-lookup"><span data-stu-id="d905e-106">Or measure *total sales of the company* to understand the aggregate-level revenue in the whole business.</span></span>  

<span data-ttu-id="d905e-107">Miery sa vytvárajú pomocou nástroja na tvorbu mier, platformy na dotazovanie údajov s rôznymi operátormi a jednoduchými možnosťami mapovania.</span><span class="sxs-lookup"><span data-stu-id="d905e-107">Measures are created using the measure builder, a data query platform with various operators and simple mapping options.</span></span> <span data-ttu-id="d905e-108">Umožňujú vám filtrovať údaje, zoskupovať výsledky, zisťovať [cesty vzťahov medzi entitami](relationships.md) a zobrazovať ukážku výstupu.</span><span class="sxs-lookup"><span data-stu-id="d905e-108">It lets you filter the data, group results, detect [entity relationship paths](relationships.md), and preview the output.</span></span>

<span data-ttu-id="d905e-109">Použite nástroj na tvorbu mier na plánovanie obchodných aktivít dotazovaním na údaje o zákazníkoch a získavaním prehľadov.</span><span class="sxs-lookup"><span data-stu-id="d905e-109">Use the measure builder to plan business activities by querying customer data and extract insights.</span></span> <span data-ttu-id="d905e-110">Napríklad vytvorenie miery *celkové výdavky na zákazníka* a *celková návratnosť na zákazníka* pomáha identifikovať skupinu zákazníkov s vysokými výdavkami, ale s vysokou návratnosťou.</span><span class="sxs-lookup"><span data-stu-id="d905e-110">For example, creating a measure of *total spend per customer* and *total return per customer* helps identify a group of customers with high spend yet high return.</span></span> <span data-ttu-id="d905e-111">Môžete [vytvoriť segment](segments.md) na podporu ďalších najvhodnejších akcií.</span><span class="sxs-lookup"><span data-stu-id="d905e-111">You can [create a segment](segments.md) to drive next best actions.</span></span> 

## <a name="create-a-measure"></a><span data-ttu-id="d905e-112">Vytvorenie miery</span><span class="sxs-lookup"><span data-stu-id="d905e-112">Create a measure</span></span>

<span data-ttu-id="d905e-113">Táto sekcia vás prevedie vytvorením novej miery od nuly.</span><span class="sxs-lookup"><span data-stu-id="d905e-113">This section walks you through creating a new measure from scratch.</span></span> <span data-ttu-id="d905e-114">Môžete vytvoriť mieru s atribútmi údajov z údajových entít, ktoré majú nastavený vzťah na spojenie s entitou Zákazník.</span><span class="sxs-lookup"><span data-stu-id="d905e-114">You can build a measure with data attributes from data entities that have a relationship set up to connect with the Customer entity.</span></span> 

1. <span data-ttu-id="d905e-115">V prehľadoch cieľových skupín prejdite na **Miery**.</span><span class="sxs-lookup"><span data-stu-id="d905e-115">In audience insights, go to **Measures**.</span></span>

1. <span data-ttu-id="d905e-116">Vyberte **Nové**.</span><span class="sxs-lookup"><span data-stu-id="d905e-116">Select **New**.</span></span>

1. <span data-ttu-id="d905e-117">Vyberte **Upraviť názov** a zadajte **Názov** miery.</span><span class="sxs-lookup"><span data-stu-id="d905e-117">Select **Edit name** and provide a **Name** for the measure.</span></span> 
   > [!NOTE]
   > <span data-ttu-id="d905e-118">Ak má vaša nová konfigurácia mier iba dve polia, napríklad CustomerID a jeden výpočet, výstup sa pridá ako nový stĺpec do systémovo generovanej entity s názvom Customer_Measure.</span><span class="sxs-lookup"><span data-stu-id="d905e-118">If your new measure configuration has only two fields, for exmample, CustomerID and one calculation, the output will be added as a new column to the system generated entity called Customer_Measure.</span></span> <span data-ttu-id="d905e-119">Hodnotu miery uvidíte v zjednotenom profile zákazníka.</span><span class="sxs-lookup"><span data-stu-id="d905e-119">And you will be able to see the measure’s value in the unified customer profile.</span></span> <span data-ttu-id="d905e-120">Ostatné miery vytvoria svoje vlastné entity.</span><span class="sxs-lookup"><span data-stu-id="d905e-120">Other measures will generate their own entities.</span></span>

1. <span data-ttu-id="d905e-121">V konfiguračnej oblasti vyberte agregačnú funkciu z rozbaľovacej ponuky **Vyberte funkciu**.</span><span class="sxs-lookup"><span data-stu-id="d905e-121">In the configuration area, choose the aggregation function from the **Select Function** drop-down menu.</span></span> <span data-ttu-id="d905e-122">Medzi agregačné funkcie patria:</span><span class="sxs-lookup"><span data-stu-id="d905e-122">Aggregation functions include:</span></span> 
   - <span data-ttu-id="d905e-123">**Sum**</span><span class="sxs-lookup"><span data-stu-id="d905e-123">**Sum**</span></span>
   - <span data-ttu-id="d905e-124">**Priemer**</span><span class="sxs-lookup"><span data-stu-id="d905e-124">**Average**</span></span>
   - <span data-ttu-id="d905e-125">**Obchodný vzťah**</span><span class="sxs-lookup"><span data-stu-id="d905e-125">**Count**</span></span>
   - <span data-ttu-id="d905e-126">**Počet jedinečných**</span><span class="sxs-lookup"><span data-stu-id="d905e-126">**Count Unique**</span></span>
   - <span data-ttu-id="d905e-127">**Max**</span><span class="sxs-lookup"><span data-stu-id="d905e-127">**Max**</span></span>
   - <span data-ttu-id="d905e-128">**Minimum**</span><span class="sxs-lookup"><span data-stu-id="d905e-128">**Min**</span></span>
   - <span data-ttu-id="d905e-129">**Prvé**: berie prvú hodnotu dátového záznamu</span><span class="sxs-lookup"><span data-stu-id="d905e-129">**First**: takes the first value of the data record</span></span>
   - <span data-ttu-id="d905e-130">**Posledné**: berie poslednú hodnotu, ktorá bola pridaná do dátového záznamu</span><span class="sxs-lookup"><span data-stu-id="d905e-130">**Last**: takes the last value that was added to the data record</span></span>

   :::image type="content" source="media/measure-operators.png" alt-text="Operátory výpočtov miery.":::

1. <span data-ttu-id="d905e-132">Vyberte **Pridať atribút** a vyberte údaje, ktoré potrebujete na vytvorenie tejto miery.</span><span class="sxs-lookup"><span data-stu-id="d905e-132">Select **Add attribute** to select the data you need to create this measure.</span></span>
   
   1. <span data-ttu-id="d905e-133">Vyberte karty **Atribúty**.</span><span class="sxs-lookup"><span data-stu-id="d905e-133">Select the **Attributes** tab.</span></span> 
   1. <span data-ttu-id="d905e-134">Dátová entita: Vyberte entitu, ktorá obsahuje atribút, ktorý chcete merať.</span><span class="sxs-lookup"><span data-stu-id="d905e-134">Data entity: Choose the entity that includes the attribute you want to measure.</span></span> 
   1. <span data-ttu-id="d905e-135">Atribút údajov: Vyberte atribút, ktorý chcete použiť vo funkcii agregácie na výpočet miery.</span><span class="sxs-lookup"><span data-stu-id="d905e-135">Data attribute: Choose the attribute you want to use in the aggregation function to calculate the measure.</span></span> <span data-ttu-id="d905e-136">Môžete vybrať iba jeden atribút naraz.</span><span class="sxs-lookup"><span data-stu-id="d905e-136">You can only select one attribute at a time.</span></span>
   1. <span data-ttu-id="d905e-137">Atribút údajov môžete vybrať aj z existujúcej miery výberom karty **Miery**. Alebo môžete vyhľadať názov entity alebo miery.</span><span class="sxs-lookup"><span data-stu-id="d905e-137">You can also select a data attribute from an existing measure by selecting the **Measures** tab. Or, you can search for an entity or measure name.</span></span> 
   1. <span data-ttu-id="d905e-138">Vyberte **Pridať** na pridanie vybraného atribútu k miere.</span><span class="sxs-lookup"><span data-stu-id="d905e-138">Select **Add** to add the selected attribute to the measure.</span></span>

   :::image type="content" source="media/measure-attribute-selection.png" alt-text="Vyberte atribút, ktorý sa má použiť pri výpočtoch.":::

1. <span data-ttu-id="d905e-140">Ak chcete vytvoriť zložitejšie miery, môžete pridať ďalšie atribúty alebo použiť matematické operátory svojej funkcie miery.</span><span class="sxs-lookup"><span data-stu-id="d905e-140">To build more complex measures, you can add more attributes or use math operators on your measure function.</span></span>

   :::image type="content" source="media/measure-math-operators.png" alt-text="Vytvorte komplexné miery s matematickými operátormi.":::

1. <span data-ttu-id="d905e-142">Ak chcete pridať filtre, vyberte **Filtrovať** v konfiguračnej oblasti.</span><span class="sxs-lookup"><span data-stu-id="d905e-142">To add filters, select the **Filter** in the configuration area.</span></span> 
  
   1. <span data-ttu-id="d905e-143">V sekcii **Pridať atribút** tably **Filtre** vyberte atribút, ktorý chcete použiť na vytvorenie filtrov.</span><span class="sxs-lookup"><span data-stu-id="d905e-143">In **Add attribute** section of the **Filters** pane, select the attribute you want to use to create filters.</span></span>
   1. <span data-ttu-id="d905e-144">Nastavte operátory filtra tak, aby definovali filter pre každý vybraný atribút.</span><span class="sxs-lookup"><span data-stu-id="d905e-144">Set the filter operators to define the filter for every selected attribute.</span></span>
   1. <span data-ttu-id="d905e-145">Vyberte **Použiť** na pridanie filtrov k miere.</span><span class="sxs-lookup"><span data-stu-id="d905e-145">Select **Apply** to add the filters to the measure.</span></span>

1. <span data-ttu-id="d905e-146">Ak chcete pridať dimenzie, vyberte **Dimenzie** v konfiguračnej oblasti.</span><span class="sxs-lookup"><span data-stu-id="d905e-146">To add dimensions, select **Dimension** in the configuration area.</span></span> <span data-ttu-id="d905e-147">Dimenzie sa zobrazia ako stĺpce v entite výstupu miery.</span><span class="sxs-lookup"><span data-stu-id="d905e-147">Dimensions will show as columns in the measure output entity.</span></span>
   1. <span data-ttu-id="d905e-148">Vyberte **Upraviť dimenzie**, ak chcete pridať atribúty údajov, podľa ktorých chcete zoskupiť namerané hodnoty.</span><span class="sxs-lookup"><span data-stu-id="d905e-148">Select **Edit dimensions** to add data attributes you want to group the measure values by.</span></span> <span data-ttu-id="d905e-149">Napríklad mesto alebo pohlavie.</span><span class="sxs-lookup"><span data-stu-id="d905e-149">For example, city or gender.</span></span> <span data-ttu-id="d905e-150">V predvolenom nastavení je vybraná dimenzia *CustomerID* na vytvorenie *mier na úrovni zákazníka*.</span><span class="sxs-lookup"><span data-stu-id="d905e-150">By default, the *CustomerID* dimension is selected to create *customer-level measures*.</span></span> <span data-ttu-id="d905e-151">Ak chcete vytvoriť *miery na úrovni podniku*, môžete odstrániť predvolenú dimenziu.</span><span class="sxs-lookup"><span data-stu-id="d905e-151">You can remove the default dimension if you want to create *business-level measures*.</span></span>
   1. <span data-ttu-id="d905e-152">Vyberte **Hotovo** na pridanie dimenzie k miere.</span><span class="sxs-lookup"><span data-stu-id="d905e-152">Select **Done** to add the dimensions to the measure.</span></span>

1. <span data-ttu-id="d905e-153">Ak existuje viac postupov medzi dátovou entitou, ktorú ste mapovali, a entitou zákazníka, musíte zvoliť jednu z identifikovaných [postupov vzťahov medzi entitami](relationships.md).</span><span class="sxs-lookup"><span data-stu-id="d905e-153">If there are multiple paths between the data entity you mapped and the Customer entity, you have to choose one of the identified [entity relationship paths](relationships.md).</span></span> <span data-ttu-id="d905e-154">Výsledky mier sa môžu líšiť v závislosti od zvoleného postupu.</span><span class="sxs-lookup"><span data-stu-id="d905e-154">Measure results can vary depending on the selected path.</span></span>
   1. <span data-ttu-id="d905e-155">Vyberte **Predvoľby údajov** a vyberte postup entity, ktorý by sa mal použiť na identifikáciu vašej miery.</span><span class="sxs-lookup"><span data-stu-id="d905e-155">Select **Data preferences** and choose the entity path that should be used to identify your measure.</span></span>
   1. <span data-ttu-id="d905e-156">Výberom možnosti **Hotovo** použite svoj výber.</span><span class="sxs-lookup"><span data-stu-id="d905e-156">Select **Done** to apply your selection.</span></span> 

   :::image type="content" source="media/measures-data-preferences.png" alt-text="Vyberte postup entity pre mieru.":::

1. <span data-ttu-id="d905e-158">Ak chcete pridať ďalšie výpočty miery, vyberte položku **Nový výpočet**.</span><span class="sxs-lookup"><span data-stu-id="d905e-158">To add more calculations for the measure, select **New calculation**.</span></span> <span data-ttu-id="d905e-159">Na nové výpočty môžete použiť iba entity v tom istom postupe entity.</span><span class="sxs-lookup"><span data-stu-id="d905e-159">You can only use entities on the same entity path for new calculations.</span></span> <span data-ttu-id="d905e-160">Ďalšie výpočty sa zobrazia ako nové stĺpce v entite výstupu miery.</span><span class="sxs-lookup"><span data-stu-id="d905e-160">More calculations will show as new columns in the measure output entity.</span></span>

1. <span data-ttu-id="d905e-161">Vyberte **...** vo výpočte na **Duplikovanie**, **Premenovanie** alebo **Odstránenie** výpočtu z miery.</span><span class="sxs-lookup"><span data-stu-id="d905e-161">Select **...** on the calculation to **Duplicate**, **Rename**, or **Remove** a calculation from a measure.</span></span>

1. <span data-ttu-id="d905e-162">V oblasti **Ukážka** uvidíte dátovú schému entity výstupu miery vrátane filtrov a dimenzií.</span><span class="sxs-lookup"><span data-stu-id="d905e-162">In the **Preview** area, you'll see the data schema of the measure output entity, including filters and dimensions.</span></span> <span data-ttu-id="d905e-163">Ukážka dynamicky reaguje na zmeny v konfigurácii.</span><span class="sxs-lookup"><span data-stu-id="d905e-163">The preview reacts dynamically to changes in the configuration.</span></span>

1. <span data-ttu-id="d905e-164">Vyberte **Spustiť** na výpočet výsledkov pre nakonfigurovanú mieru.</span><span class="sxs-lookup"><span data-stu-id="d905e-164">Select **Run** to calculate results for the configured measure.</span></span> <span data-ttu-id="d905e-165">Vyberte **Uložiť a zavrieť**, ak si chcete ponechať aktuálnu konfiguráciu a mieru spustiť neskôr.</span><span class="sxs-lookup"><span data-stu-id="d905e-165">Select **Save and close** if you want to keep the current configuration and run the measure later.</span></span>

1. <span data-ttu-id="d905e-166">Prechodom na možnosť **Miery** zobrazíte novovytvorenú mieru v zozname.</span><span class="sxs-lookup"><span data-stu-id="d905e-166">Go to **Measures** to see the newly created measure in the list.</span></span>

## <a name="manage-your-measures"></a><span data-ttu-id="d905e-167">Spravovanie mier</span><span class="sxs-lookup"><span data-stu-id="d905e-167">Manage your measures</span></span>

<span data-ttu-id="d905e-168">Po [vytvorení miery](#create-a-measure) sa zobrazí zoznam mier na stránke **Miery**.</span><span class="sxs-lookup"><span data-stu-id="d905e-168">After [creating a measure](#create-a-measure), you see a list of measures on the **Measures** page.</span></span>

<span data-ttu-id="d905e-169">Nájdete informácie o type miery, jej tvorcovi, dátume vytvorenia, statuse a stave.</span><span class="sxs-lookup"><span data-stu-id="d905e-169">You'll find information about the measure type, the creator, creation date, status, and state.</span></span> <span data-ttu-id="d905e-170">Keď vyberiete mieru zo zoznamu, môžete si pozrieť ukážku výstupu a stiahnuť súbor .CSV.</span><span class="sxs-lookup"><span data-stu-id="d905e-170">When you select a measure from the list, you can preview the output and download a .CSV file.</span></span>

<span data-ttu-id="d905e-171">Ak chcete obnoviť všetky svoje miery naraz, vyberte položku **Obnoviť všetko** bez výberu konkrétnej miery.</span><span class="sxs-lookup"><span data-stu-id="d905e-171">To refresh all of your measures at the same time, select **Refresh all** without selecting a specific measure.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="d905e-172">![Akcie na spravovanie jednotlivých mier](media/measure-actions.png "Akcie na spravovanie jednotlivých mier")</span><span class="sxs-lookup"><span data-stu-id="d905e-172">![Actions to manage single measures](media/measure-actions.png "Actions to manage single measures")</span></span>

<span data-ttu-id="d905e-173">Vyberte mieru zo zoznamu a zobrazte nasledujúce možnosti:</span><span class="sxs-lookup"><span data-stu-id="d905e-173">Select a measure from the list for the following options:</span></span>

- <span data-ttu-id="d905e-174">Kliknutím na názov miery zobrazíte podrobnosti.</span><span class="sxs-lookup"><span data-stu-id="d905e-174">Select the measure name to see its details.</span></span>
- <span data-ttu-id="d905e-175">**Upravte** konfiguráciu miery.</span><span class="sxs-lookup"><span data-stu-id="d905e-175">**Edit** the configuration of the measure.</span></span>
- <span data-ttu-id="d905e-176">**Obnovte** mieru na základe najnovších údajov.</span><span class="sxs-lookup"><span data-stu-id="d905e-176">**Refresh** the measure based on the latest data.</span></span>
- <span data-ttu-id="d905e-177">**Premenujte** mieru.</span><span class="sxs-lookup"><span data-stu-id="d905e-177">**Rename** the measure.</span></span>
- <span data-ttu-id="d905e-178">**Odstráňte** mieru.</span><span class="sxs-lookup"><span data-stu-id="d905e-178">**Delete** the measure.</span></span>
- <span data-ttu-id="d905e-179">**Aktivujte** alebo **Deaktivujte**.</span><span class="sxs-lookup"><span data-stu-id="d905e-179">**Activate** or **Deactivate**.</span></span> <span data-ttu-id="d905e-180">Neaktívne miery sa počas [plánovaného obnovenia](system.md#schedule-tab) neobnovujú.</span><span class="sxs-lookup"><span data-stu-id="d905e-180">Inactive measures won't get refreshed during a [scheduled refresh](system.md#schedule-tab).</span></span>

> [!TIP]
> <span data-ttu-id="d905e-181">Existuje [šesť druhov stavov](system.md#status-types) pre úlohy/procesy.</span><span class="sxs-lookup"><span data-stu-id="d905e-181">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="d905e-182">Okrem toho väčšina procesov [závisí na ďalších nadväzujúcich procesoch](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="d905e-182">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="d905e-183">Môžete si vybrať stav procesu a zobraziť podrobnosti o priebehu celej úlohy.</span><span class="sxs-lookup"><span data-stu-id="d905e-183">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="d905e-184">Po výbere **Pozrieť detaily** pre jednu z úloh úlohy nájdete ďalšie informácie: čas spracovania, posledný dátum spracovania a všetky chyby a varovania spojené s úlohou.</span><span class="sxs-lookup"><span data-stu-id="d905e-184">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="d905e-185">Nasledujúci krok</span><span class="sxs-lookup"><span data-stu-id="d905e-185">Next step</span></span>

<span data-ttu-id="d905e-186">Môžete použiť existujúce miery na vytvorenie [vlastného segmentu](segments.md).</span><span class="sxs-lookup"><span data-stu-id="d905e-186">You cam use existing measures to create [a customer segment](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]