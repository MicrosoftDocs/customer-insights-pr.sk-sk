---
title: Vytváranie a spravovanie mier
description: Definujte miery na analýzu a zobrazovanie výkonnosti vášho podnikania.
ms.date: 04/12/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wameng
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 402e5ef3515bce0e6f56788781b7bd909738aaa6
ms.sourcegitcommit: b833e333745d321edeaf96d3ed14458cbce02ff1
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 05/17/2021
ms.locfileid: "6049269"
---
# <a name="define-and-manage-measures"></a><span data-ttu-id="d9cf1-103">Definovanie a spravovanie mier</span><span class="sxs-lookup"><span data-stu-id="d9cf1-103">Define and manage measures</span></span>

<span data-ttu-id="d9cf1-104">Opatrenia vám pomôžu lepšie pochopiť správanie zákazníkov a výkonnosť podniku.</span><span class="sxs-lookup"><span data-stu-id="d9cf1-104">Measures help you to better understand customer behaviors and business performance.</span></span> <span data-ttu-id="d9cf1-105">Pozerajú sa na príslušné hodnoty zo [zjednotených profilov](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="d9cf1-105">They look at relevant values from [unified profiles](data-unification.md).</span></span> <span data-ttu-id="d9cf1-106">Napríklad firma chce vidieť *celkové výdavky na zákazníka*, aby mala prehľad o histórii alebo miere nákupu jednotlivých zákazníkov, prípadne si môžu odmerať *celkový predaj spoločnosti* a oboznámiť s s agregovaným výnosom pre celý podnik.</span><span class="sxs-lookup"><span data-stu-id="d9cf1-106">For example, a business wants to see the *total spend per customer* to understand individual customer’s purchase history or measure *total sales of the company* to understand the aggregate-level revenue in the whole business.</span></span>  

<span data-ttu-id="d9cf1-107">Miery sa vytvárajú pomocou nástroja na tvorbu mier, platformy na dotazovanie údajov s rôznymi operátormi a jednoduchými možnosťami mapovania.</span><span class="sxs-lookup"><span data-stu-id="d9cf1-107">Measures are created using the measure builder, a data query platform with various operators and simple mapping options.</span></span> <span data-ttu-id="d9cf1-108">Umožňujú vám filtrovať údaje, zoskupovať výsledky, zisťovať [cesty vzťahov medzi entitami](relationships.md) a zobrazovať ukážku výstupu.</span><span class="sxs-lookup"><span data-stu-id="d9cf1-108">It lets you filter the data, group results, detect [entity relationship paths](relationships.md), and preview the output.</span></span>

<span data-ttu-id="d9cf1-109">Použite nástroj na tvorbu mier na plánovanie obchodných aktivít dotazovaním na údaje o zákazníkoch a získavaním prehľadov.</span><span class="sxs-lookup"><span data-stu-id="d9cf1-109">Use the measure builder to plan business activities by querying customer data and extract insights.</span></span> <span data-ttu-id="d9cf1-110">Napríklad vytvorenie miery *celkové výdavky na zákazníka* a *celková návratnosť na zákazníka* pomáha identifikovať skupinu zákazníkov s vysokými výdavkami, ale s vysokou návratnosťou.</span><span class="sxs-lookup"><span data-stu-id="d9cf1-110">For example, creating a measure of *total spend per customer* and *total return per customer* helps identify a group of customers with high spend yet high return.</span></span> <span data-ttu-id="d9cf1-111">Môžete [vytvoriť segment](segments.md) na podporu ďalších najvhodnejších akcií.</span><span class="sxs-lookup"><span data-stu-id="d9cf1-111">You can [create a segment](segments.md) to drive next best actions.</span></span> 

## <a name="build-your-own-measure-from-scratch"></a><span data-ttu-id="d9cf1-112">Vytvorte si vlastné meranie úplne od začiatku</span><span class="sxs-lookup"><span data-stu-id="d9cf1-112">Build your own measure from scratch</span></span>

<span data-ttu-id="d9cf1-113">Táto sekcia vás prevedie vytvorením novej miery od nuly.</span><span class="sxs-lookup"><span data-stu-id="d9cf1-113">This section walks you through creating a new measure from scratch.</span></span> <span data-ttu-id="d9cf1-114">Môžete vytvoriť mieru s atribútmi údajov z údajových entít, ktoré majú nastavený vzťah na spojenie s entitou Zákazník.</span><span class="sxs-lookup"><span data-stu-id="d9cf1-114">You can build a measure with data attributes from data entities that have a relationship set up to connect with the Customer entity.</span></span> 

1. <span data-ttu-id="d9cf1-115">V prehľadoch cieľových skupín prejdite na **Miery**.</span><span class="sxs-lookup"><span data-stu-id="d9cf1-115">In audience insights, go to **Measures**.</span></span>

1. <span data-ttu-id="d9cf1-116">Vyberte **Nový** a stlačte **Vytvorte si vlastnú**.</span><span class="sxs-lookup"><span data-stu-id="d9cf1-116">Select **New** and choose **Build your own**.</span></span>

1. <span data-ttu-id="d9cf1-117">Vyberte **Upraviť názov** a zadajte **Názov** miery.</span><span class="sxs-lookup"><span data-stu-id="d9cf1-117">Select **Edit name** and provide a **Name** for the measure.</span></span> 
   > [!NOTE]
   > <span data-ttu-id="d9cf1-118">Ak má vaša nová konfigurácia opatrení iba dve polia, napríklad CustomerID a jeden výpočet, výstup sa pridá ako nový stĺpec do systémovo generovanej entity s názvom Customer_Measure.</span><span class="sxs-lookup"><span data-stu-id="d9cf1-118">If your new measure configuration has only two fields, for example, CustomerID and one calculation, the output will be added as a new column to the system generated entity called Customer_Measure.</span></span> <span data-ttu-id="d9cf1-119">Hodnotu miery uvidíte v zjednotenom profile zákazníka.</span><span class="sxs-lookup"><span data-stu-id="d9cf1-119">And you will be able to see the measure’s value in the unified customer profile.</span></span> <span data-ttu-id="d9cf1-120">Ostatné miery vytvoria svoje vlastné entity.</span><span class="sxs-lookup"><span data-stu-id="d9cf1-120">Other measures will generate their own entities.</span></span>

1. <span data-ttu-id="d9cf1-121">V konfiguračnej oblasti vyberte agregačnú funkciu z rozbaľovacej ponuky **Vyberte funkciu**.</span><span class="sxs-lookup"><span data-stu-id="d9cf1-121">In the configuration area, choose the aggregation function from the **Select Function** drop-down menu.</span></span> <span data-ttu-id="d9cf1-122">Medzi agregačné funkcie patria:</span><span class="sxs-lookup"><span data-stu-id="d9cf1-122">Aggregation functions include:</span></span> 
   - <span data-ttu-id="d9cf1-123">**Sum**</span><span class="sxs-lookup"><span data-stu-id="d9cf1-123">**Sum**</span></span>
   - <span data-ttu-id="d9cf1-124">**Priemer**</span><span class="sxs-lookup"><span data-stu-id="d9cf1-124">**Average**</span></span>
   - <span data-ttu-id="d9cf1-125">**Obchodný vzťah**</span><span class="sxs-lookup"><span data-stu-id="d9cf1-125">**Count**</span></span>
   - <span data-ttu-id="d9cf1-126">**Počet jedinečných**</span><span class="sxs-lookup"><span data-stu-id="d9cf1-126">**Count Unique**</span></span>
   - <span data-ttu-id="d9cf1-127">**Max**</span><span class="sxs-lookup"><span data-stu-id="d9cf1-127">**Max**</span></span>
   - <span data-ttu-id="d9cf1-128">**Minimum**</span><span class="sxs-lookup"><span data-stu-id="d9cf1-128">**Min**</span></span>
   - <span data-ttu-id="d9cf1-129">**Prvé**: berie prvú hodnotu dátového záznamu</span><span class="sxs-lookup"><span data-stu-id="d9cf1-129">**First**: takes the first value of the data record</span></span>
   - <span data-ttu-id="d9cf1-130">**Posledné**: berie poslednú hodnotu, ktorá bola pridaná do dátového záznamu</span><span class="sxs-lookup"><span data-stu-id="d9cf1-130">**Last**: takes the last value that was added to the data record</span></span>

   :::image type="content" source="media/measure-operators.png" alt-text="Operátory výpočtov miery.":::

1. <span data-ttu-id="d9cf1-132">Vyberte **Pridať atribút** a vyberte údaje, ktoré potrebujete na vytvorenie tejto miery.</span><span class="sxs-lookup"><span data-stu-id="d9cf1-132">Select **Add attribute** to select the data you need to create this measure.</span></span>
   
   1. <span data-ttu-id="d9cf1-133">Vyberte karty **Atribúty**.</span><span class="sxs-lookup"><span data-stu-id="d9cf1-133">Select the **Attributes** tab.</span></span> 
   1. <span data-ttu-id="d9cf1-134">Dátová entita: Vyberte entitu, ktorá obsahuje atribút, ktorý chcete merať.</span><span class="sxs-lookup"><span data-stu-id="d9cf1-134">Data entity: Choose the entity that includes the attribute you want to measure.</span></span> 
   1. <span data-ttu-id="d9cf1-135">Atribút údajov: Vyberte atribút, ktorý chcete použiť vo funkcii agregácie na výpočet miery.</span><span class="sxs-lookup"><span data-stu-id="d9cf1-135">Data attribute: Choose the attribute you want to use in the aggregation function to calculate the measure.</span></span> <span data-ttu-id="d9cf1-136">Môžete vybrať iba jeden atribút naraz.</span><span class="sxs-lookup"><span data-stu-id="d9cf1-136">You can only select one attribute at a time.</span></span>
   1. <span data-ttu-id="d9cf1-137">Atribút údajov môžete vybrať aj z existujúcej miery výberom karty **Miery**. Alebo môžete vyhľadať názov entity alebo miery.</span><span class="sxs-lookup"><span data-stu-id="d9cf1-137">You can also select a data attribute from an existing measure by selecting the **Measures** tab. Or, you can search for an entity or measure name.</span></span> 
   1. <span data-ttu-id="d9cf1-138">Vyberte **Pridať** na pridanie vybraného atribútu k miere.</span><span class="sxs-lookup"><span data-stu-id="d9cf1-138">Select **Add** to add the selected attribute to the measure.</span></span>

   :::image type="content" source="media/measure-attribute-selection.png" alt-text="Vyberte atribút, ktorý sa má použiť pri výpočtoch.":::

1. <span data-ttu-id="d9cf1-140">Ak chcete vytvoriť zložitejšie miery, môžete pridať ďalšie atribúty alebo použiť matematické operátory svojej funkcie miery.</span><span class="sxs-lookup"><span data-stu-id="d9cf1-140">To build more complex measures, you can add more attributes or use math operators on your measure function.</span></span>

   :::image type="content" source="media/measure-math-operators.png" alt-text="Vytvorte komplexné miery s matematickými operátormi.":::

1. <span data-ttu-id="d9cf1-142">Ak chcete pridať filtre, vyberte **Filtrovať** v konfiguračnej oblasti.</span><span class="sxs-lookup"><span data-stu-id="d9cf1-142">To add filters, select the **Filter** in the configuration area.</span></span> 
  
   1. <span data-ttu-id="d9cf1-143">V sekcii **Pridať atribút** tably **Filtre** vyberte atribút, ktorý chcete použiť na vytvorenie filtrov.</span><span class="sxs-lookup"><span data-stu-id="d9cf1-143">In **Add attribute** section of the **Filters** pane, select the attribute you want to use to create filters.</span></span>
   1. <span data-ttu-id="d9cf1-144">Nastavte operátory filtra tak, aby definovali filter pre každý vybraný atribút.</span><span class="sxs-lookup"><span data-stu-id="d9cf1-144">Set the filter operators to define the filter for every selected attribute.</span></span>
   1. <span data-ttu-id="d9cf1-145">Vyberte **Použiť** na pridanie filtrov k miere.</span><span class="sxs-lookup"><span data-stu-id="d9cf1-145">Select **Apply** to add the filters to the measure.</span></span>

1. <span data-ttu-id="d9cf1-146">Ak chcete pridať dimenzie, vyberte **Dimenzie** v konfiguračnej oblasti.</span><span class="sxs-lookup"><span data-stu-id="d9cf1-146">To add dimensions, select **Dimension** in the configuration area.</span></span> <span data-ttu-id="d9cf1-147">Dimenzie sa zobrazia ako stĺpce v entite výstupu miery.</span><span class="sxs-lookup"><span data-stu-id="d9cf1-147">Dimensions will show as columns in the measure output entity.</span></span>
   1. <span data-ttu-id="d9cf1-148">Vyberte **Upraviť dimenzie**, ak chcete pridať atribúty údajov, podľa ktorých chcete zoskupiť namerané hodnoty.</span><span class="sxs-lookup"><span data-stu-id="d9cf1-148">Select **Edit dimensions** to add data attributes you want to group the measure values by.</span></span> <span data-ttu-id="d9cf1-149">Napríklad mesto alebo pohlavie.</span><span class="sxs-lookup"><span data-stu-id="d9cf1-149">For example, city or gender.</span></span> <span data-ttu-id="d9cf1-150">V predvolenom nastavení je vybraná dimenzia *CustomerID* na vytvorenie *mier na úrovni zákazníka*.</span><span class="sxs-lookup"><span data-stu-id="d9cf1-150">By default, the *CustomerID* dimension is selected to create *customer-level measures*.</span></span> <span data-ttu-id="d9cf1-151">Ak chcete vytvoriť *miery na úrovni podniku*, môžete odstrániť predvolenú dimenziu.</span><span class="sxs-lookup"><span data-stu-id="d9cf1-151">You can remove the default dimension if you want to create *business-level measures*.</span></span>
   1. <span data-ttu-id="d9cf1-152">Vyberte **Hotovo** na pridanie dimenzie k miere.</span><span class="sxs-lookup"><span data-stu-id="d9cf1-152">Select **Done** to add the dimensions to the measure.</span></span>

1. <span data-ttu-id="d9cf1-153">Ak sú vo vašich údajoch hodnoty, ktoré musíte vymeniť napríklad celým číslom, nahraďte ich príznakom *null* s *0*, a stlačte možnosť **Pravidlá**.</span><span class="sxs-lookup"><span data-stu-id="d9cf1-153">If there are values in your data that you need to replace with an integer, for example, replace *null* with *0*, select **Rules**.</span></span> <span data-ttu-id="d9cf1-154">Nakonfigurujte pravidlo a uistite sa, že ste ako náhradu vybrali iba celé čísla.</span><span class="sxs-lookup"><span data-stu-id="d9cf1-154">Configure the rule and make sure that you choose only whole numbers as replacements.</span></span>

1. <span data-ttu-id="d9cf1-155">Ak existuje viac postupov medzi dátovou entitou, ktorú ste mapovali, a entitou *zákazníka*, musíte zvoliť jednu z identifikovaných [postupov vzťahov medzi entitami](relationships.md).</span><span class="sxs-lookup"><span data-stu-id="d9cf1-155">If there are multiple paths between the data entity you mapped and the *Customer* entity, you have to choose one of the identified [entity relationship paths](relationships.md).</span></span> <span data-ttu-id="d9cf1-156">Výsledky mier sa môžu líšiť v závislosti od zvoleného postupu.</span><span class="sxs-lookup"><span data-stu-id="d9cf1-156">Measure results can vary depending on the selected path.</span></span> 
   1. <span data-ttu-id="d9cf1-157">Vyberte **Predvoľby údajov** a vyberte postup entity, ktorý by sa mal použiť na identifikáciu vašej miery.</span><span class="sxs-lookup"><span data-stu-id="d9cf1-157">Select **Data preferences** and choose the entity path that should be used to identify your measure.</span></span> <span data-ttu-id="d9cf1-158">Ak existuje iba jedna cesta k entite *Zákazník*, tento ovládací prvok sa nezobrazí.</span><span class="sxs-lookup"><span data-stu-id="d9cf1-158">If there's only a single path to the *Customer* entity, this control won't show.</span></span>
   1. <span data-ttu-id="d9cf1-159">Výberom možnosti **Hotovo** použite svoj výber.</span><span class="sxs-lookup"><span data-stu-id="d9cf1-159">Select **Done** to apply your selection.</span></span> 

   :::image type="content" source="media/measures-data-preferences.png" alt-text="Vyberte postup entity pre mieru.":::

1. <span data-ttu-id="d9cf1-161">Ak chcete pridať ďalšie výpočty miery, vyberte položku **Nový výpočet**.</span><span class="sxs-lookup"><span data-stu-id="d9cf1-161">To add more calculations for the measure, select **New calculation**.</span></span> <span data-ttu-id="d9cf1-162">Na nové výpočty môžete použiť iba entity v tom istom postupe entity.</span><span class="sxs-lookup"><span data-stu-id="d9cf1-162">You can only use entities on the same entity path for new calculations.</span></span> <span data-ttu-id="d9cf1-163">Ďalšie výpočty sa zobrazia ako nové stĺpce v entite výstupu miery.</span><span class="sxs-lookup"><span data-stu-id="d9cf1-163">More calculations will show as new columns in the measure output entity.</span></span>

1. <span data-ttu-id="d9cf1-164">Vyberte **...** vo výpočte na **Duplikovanie**, **Premenovanie** alebo **Odstránenie** výpočtu z miery.</span><span class="sxs-lookup"><span data-stu-id="d9cf1-164">Select **...** on the calculation to **Duplicate**, **Rename**, or **Remove** a calculation from a measure.</span></span>

1. <span data-ttu-id="d9cf1-165">V oblasti **Ukážka** uvidíte dátovú schému entity výstupu miery vrátane filtrov a dimenzií.</span><span class="sxs-lookup"><span data-stu-id="d9cf1-165">In the **Preview** area, you'll see the data schema of the measure output entity, including filters and dimensions.</span></span> <span data-ttu-id="d9cf1-166">Ukážka dynamicky reaguje na zmeny v konfigurácii.</span><span class="sxs-lookup"><span data-stu-id="d9cf1-166">The preview reacts dynamically to changes in the configuration.</span></span>

1. <span data-ttu-id="d9cf1-167">Vyberte **Spustiť** na výpočet výsledkov pre nakonfigurovanú mieru.</span><span class="sxs-lookup"><span data-stu-id="d9cf1-167">Select **Run** to calculate results for the configured measure.</span></span> <span data-ttu-id="d9cf1-168">Vyberte **Uložiť a zavrieť**, ak si chcete ponechať aktuálnu konfiguráciu a mieru spustiť neskôr.</span><span class="sxs-lookup"><span data-stu-id="d9cf1-168">Select **Save and close** if you want to keep the current configuration and run the measure later.</span></span>

1. <span data-ttu-id="d9cf1-169">Prechodom na možnosť **Miery** zobrazíte novovytvorenú mieru v zozname.</span><span class="sxs-lookup"><span data-stu-id="d9cf1-169">Go to **Measures** to see the newly created measure in the list.</span></span>

## <a name="use-a-template-to-build-a-measure"></a><span data-ttu-id="d9cf1-170">Na vytvorenie miery použite šablónu</span><span class="sxs-lookup"><span data-stu-id="d9cf1-170">Use a template to build a measure</span></span>

<span data-ttu-id="d9cf1-171">Na ich vytvorenie môžete použiť preddefinované šablóny bežne používaných meraní.</span><span class="sxs-lookup"><span data-stu-id="d9cf1-171">You can use predefined templates of commonly used measures to create them.</span></span> <span data-ttu-id="d9cf1-172">Podrobné popisy šablón a sprievodca vám pomôže s efektívnym vytváraním opatrení.</span><span class="sxs-lookup"><span data-stu-id="d9cf1-172">Detailed descriptions of the templates and a guided experience help you with efficient measure creation.</span></span> <span data-ttu-id="d9cf1-173">Šablóny vychádzajú z mapovaných údajov z entity *Zjednotená aktivita*.</span><span class="sxs-lookup"><span data-stu-id="d9cf1-173">Templates build on mapped data from the *Unified Activity* entity.</span></span> <span data-ttu-id="d9cf1-174">Uistite sa teda, že ste nakonfigurovali [aktivity zákazníkov](activities.md) pred vytvorením merania zo šablóny.</span><span class="sxs-lookup"><span data-stu-id="d9cf1-174">So make sure you have configured [customer activities](activities.md) before you create a measure from a template.</span></span>

<span data-ttu-id="d9cf1-175">Dostupné šablóny merania:</span><span class="sxs-lookup"><span data-stu-id="d9cf1-175">Available measure templates:</span></span> 
- <span data-ttu-id="d9cf1-176">Priemerná hodnota transakcie (ATV)</span><span class="sxs-lookup"><span data-stu-id="d9cf1-176">Average transaction value (ATV)</span></span>
- <span data-ttu-id="d9cf1-177">Celková hodnota transakcií</span><span class="sxs-lookup"><span data-stu-id="d9cf1-177">Total transaction value</span></span>
- <span data-ttu-id="d9cf1-178">Priemerný denný výnos</span><span class="sxs-lookup"><span data-stu-id="d9cf1-178">Average daily revenue</span></span>
- <span data-ttu-id="d9cf1-179">Priemerný ročný výnos</span><span class="sxs-lookup"><span data-stu-id="d9cf1-179">Average yearly revenue</span></span>
- <span data-ttu-id="d9cf1-180">Počet transakcií</span><span class="sxs-lookup"><span data-stu-id="d9cf1-180">Transaction count</span></span>
- <span data-ttu-id="d9cf1-181">Získané vernostné body</span><span class="sxs-lookup"><span data-stu-id="d9cf1-181">Loyalty points earned</span></span>
- <span data-ttu-id="d9cf1-182">Uplatnené vernostné body</span><span class="sxs-lookup"><span data-stu-id="d9cf1-182">Loyalty points redeemed</span></span>
- <span data-ttu-id="d9cf1-183">Zostatok vernostných bodov</span><span class="sxs-lookup"><span data-stu-id="d9cf1-183">Loyalty points balance</span></span>
- <span data-ttu-id="d9cf1-184">Životnosť aktívneho zákazníka</span><span class="sxs-lookup"><span data-stu-id="d9cf1-184">Active customer lifespan</span></span>
- <span data-ttu-id="d9cf1-185">Trvanie členstva vo vernostnom programe</span><span class="sxs-lookup"><span data-stu-id="d9cf1-185">Loyalty membership duration</span></span>
- <span data-ttu-id="d9cf1-186">Čas od posledného nákupu</span><span class="sxs-lookup"><span data-stu-id="d9cf1-186">Time since last purchase</span></span>

<span data-ttu-id="d9cf1-187">Nasledujúci postup popisuje kroky na vytvorenie nového opatrenia pomocou šablóny.</span><span class="sxs-lookup"><span data-stu-id="d9cf1-187">The following procedure outlines the steps to build a new measure using a template.</span></span>

1. <span data-ttu-id="d9cf1-188">V prehľadoch cieľových skupín prejdite na **Miery**.</span><span class="sxs-lookup"><span data-stu-id="d9cf1-188">In audience insights, go to **Measures**.</span></span>

1. <span data-ttu-id="d9cf1-189">Stlačte **Nový** a stlačte **Výber šablóny**.</span><span class="sxs-lookup"><span data-stu-id="d9cf1-189">Select **New** and select **Choose a template**.</span></span>

   :::image type="content" source="media/measure-use-template.png" alt-text="Snímka obrazovky z rozbaľovacej ponuky pri vytváraní nového opatrenia so zvýraznením šablóny.":::

1. <span data-ttu-id="d9cf1-191">Nájdite šablónu, ktorá vyhovuje vašim potrebám, a stlačte možnosť **Vybrať šablónu**.</span><span class="sxs-lookup"><span data-stu-id="d9cf1-191">Find the template that fits your need and select **Choose template**.</span></span>

1. <span data-ttu-id="d9cf1-192">Skontrolujte požadované údaje a vyberte **Začíname**, ak máte všetky údaje uvedené.</span><span class="sxs-lookup"><span data-stu-id="d9cf1-192">Review the required data and select **Get started** if you have all the data in place.</span></span>

1. <span data-ttu-id="d9cf1-193">Na table **Upraviť názov** nastavte názov svojej miery a výstupnú entitu.</span><span class="sxs-lookup"><span data-stu-id="d9cf1-193">In the **Edit name** pane, set the name for your measure and the output entity.</span></span> 

1. <span data-ttu-id="d9cf1-194">Vyberte položku **Hotovo**.</span><span class="sxs-lookup"><span data-stu-id="d9cf1-194">Select **Done**.</span></span>

1. <span data-ttu-id="d9cf1-195">V časti **Nastaviť časové obdobie** definujte časový rámec údajov, ktoré sa majú použiť.</span><span class="sxs-lookup"><span data-stu-id="d9cf1-195">In the **Set time period** section, define the time frame of the data to use.</span></span> <span data-ttu-id="d9cf1-196">Vyberte, či chcete, aby nové opatrenie pokrylo celú množinu údajov výberom **Vždy**.</span><span class="sxs-lookup"><span data-stu-id="d9cf1-196">Choose if you want the new measure to cover the entire data set by selecting **All time**.</span></span> <span data-ttu-id="d9cf1-197">Alebo ak chcete, aby sa opatrenie zameralo na **Konkrétne časové obdobie**.</span><span class="sxs-lookup"><span data-stu-id="d9cf1-197">Or if you want the measure to focus on a **Specific time period**.</span></span>

   :::image type="content" source="media/measure-set-time-period.png" alt-text="Snímka obrazovky zobrazujúca sekciu časového obdobia pri konfigurácii merania zo šablóny.":::

1. <span data-ttu-id="d9cf1-199">V ďalšej časti vyberte možnosť **Pridať údaje** a vyberte si činnosti a namapujte príslušné údaje z vašej entity *Zjednotenej aktivity*.</span><span class="sxs-lookup"><span data-stu-id="d9cf1-199">In the next section, select **Add data** to choose the activities and map the corresponding data from your *Unified Activity* entity.</span></span>

    1. <span data-ttu-id="d9cf1-200">Krok 1 z 2: V časti **Typ činnosti**, vyberte typ entity, ktorú chcete použiť.</span><span class="sxs-lookup"><span data-stu-id="d9cf1-200">Step 1 of 2: Under **Activity type**, choose the type of the entity you want to use.</span></span> <span data-ttu-id="d9cf1-201">Pre **Činnosti**, vyberte entity, ktoré chcete mapovať.</span><span class="sxs-lookup"><span data-stu-id="d9cf1-201">For **Activities**, select the entities you want to map.</span></span>
    1. <span data-ttu-id="d9cf1-202">Krok 2 z 2: Vyberte atribút z entity *Zjednotená činnosť* pre komponent požadovaný vzorcom.</span><span class="sxs-lookup"><span data-stu-id="d9cf1-202">Step 2 of 2: Choose the attribute from the *Unified Activity* entity for the component required by the formula.</span></span> <span data-ttu-id="d9cf1-203">Napríklad pre Priemernú hodnotu transakcie je to atribút predstavujúci hodnotu Transakcie.</span><span class="sxs-lookup"><span data-stu-id="d9cf1-203">For example, for Average transaction value, it's the attribute representing the Transaction value.</span></span> <span data-ttu-id="d9cf1-204">Pre **Časová pečiatka aktivity** vyberte atribút z entity Unified Activity, ktorá predstavuje dátum a čas aktivity.</span><span class="sxs-lookup"><span data-stu-id="d9cf1-204">For **Activity timestamp**, choose the attribute from the Unified Activity entity that represents the date and time of the activity.</span></span>
   
1. <span data-ttu-id="d9cf1-205">Po úspešnom mapovaní údajov môžete vidieť stav ako **Dokončené** a názov mapovaných aktivít a atribútov.</span><span class="sxs-lookup"><span data-stu-id="d9cf1-205">Once the data mapping is successful, you can see the status as **Complete** and the name of the mapped activities and attributes.</span></span>

   :::image type="content" source="media/measure-template-configured.png" alt-text="Snímka obrazovky z dokončenej konfigurácie šablóny mierky.":::

1. <span data-ttu-id="d9cf1-207">Teraz môžete stlačiť možnosť **Spustiť** na výpočet výsledkov opatrenia.</span><span class="sxs-lookup"><span data-stu-id="d9cf1-207">You can now select **Run** to calculate the results of the measure.</span></span> <span data-ttu-id="d9cf1-208">Ak ju chcete neskôr spresniť, stlačte možnosť **Uložiť koncept**.</span><span class="sxs-lookup"><span data-stu-id="d9cf1-208">To refine it later, select **Save draft**.</span></span>

## <a name="manage-your-measures"></a><span data-ttu-id="d9cf1-209">Spravovanie mier</span><span class="sxs-lookup"><span data-stu-id="d9cf1-209">Manage your measures</span></span>

<span data-ttu-id="d9cf1-210">Zoznam opatrení nájdete na stránke **Miery**.</span><span class="sxs-lookup"><span data-stu-id="d9cf1-210">You can find the list of measures on the **Measures** page.</span></span>

<span data-ttu-id="d9cf1-211">Nájdete informácie o type miery, jej tvorcovi, dátume vytvorenia, statuse a stave.</span><span class="sxs-lookup"><span data-stu-id="d9cf1-211">You'll find information about the measure type, the creator, creation date, status, and state.</span></span> <span data-ttu-id="d9cf1-212">Keď vyberiete mieru zo zoznamu, môžete si pozrieť ukážku výstupu a stiahnuť súbor .CSV.</span><span class="sxs-lookup"><span data-stu-id="d9cf1-212">When you select a measure from the list, you can preview the output and download a .CSV file.</span></span>

<span data-ttu-id="d9cf1-213">Ak chcete obnoviť všetky svoje miery naraz, vyberte položku **Obnoviť všetko** bez výberu konkrétnej miery.</span><span class="sxs-lookup"><span data-stu-id="d9cf1-213">To refresh all of your measures at the same time, select **Refresh all** without selecting a specific measure.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="d9cf1-214">![Akcie na spravovanie jednotlivých mier](media/measure-actions.png "Akcie na spravovanie jednotlivých mier")</span><span class="sxs-lookup"><span data-stu-id="d9cf1-214">![Actions to manage single measures](media/measure-actions.png "Actions to manage single measures")</span></span>

<span data-ttu-id="d9cf1-215">Vyberte mieru zo zoznamu a zobrazte nasledujúce možnosti:</span><span class="sxs-lookup"><span data-stu-id="d9cf1-215">Select a measure from the list for the following options:</span></span>

- <span data-ttu-id="d9cf1-216">Kliknutím na názov miery zobrazíte podrobnosti.</span><span class="sxs-lookup"><span data-stu-id="d9cf1-216">Select the measure name to see its details.</span></span>
- <span data-ttu-id="d9cf1-217">**Upravte** konfiguráciu miery.</span><span class="sxs-lookup"><span data-stu-id="d9cf1-217">**Edit** the configuration of the measure.</span></span>
- <span data-ttu-id="d9cf1-218">**Obnovte** mieru na základe najnovších údajov.</span><span class="sxs-lookup"><span data-stu-id="d9cf1-218">**Refresh** the measure based on the latest data.</span></span>
- <span data-ttu-id="d9cf1-219">**Premenujte** mieru.</span><span class="sxs-lookup"><span data-stu-id="d9cf1-219">**Rename** the measure.</span></span>
- <span data-ttu-id="d9cf1-220">**Odstráňte** mieru.</span><span class="sxs-lookup"><span data-stu-id="d9cf1-220">**Delete** the measure.</span></span>
- <span data-ttu-id="d9cf1-221">**Aktivujte** alebo **Deaktivujte**.</span><span class="sxs-lookup"><span data-stu-id="d9cf1-221">**Activate** or **Deactivate**.</span></span> <span data-ttu-id="d9cf1-222">Neaktívne miery sa počas [plánovaného obnovenia](system.md#schedule-tab) neobnovujú.</span><span class="sxs-lookup"><span data-stu-id="d9cf1-222">Inactive measures won't get refreshed during a [scheduled refresh](system.md#schedule-tab).</span></span>

> [!TIP]
> <span data-ttu-id="d9cf1-223">Existuje [šesť druhov stavov](system.md#status-types) pre úlohy/procesy.</span><span class="sxs-lookup"><span data-stu-id="d9cf1-223">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="d9cf1-224">Okrem toho väčšina procesov [závisí na ďalších nadväzujúcich procesoch](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="d9cf1-224">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="d9cf1-225">Môžete si vybrať stav procesu a zobraziť podrobnosti o priebehu celej úlohy.</span><span class="sxs-lookup"><span data-stu-id="d9cf1-225">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="d9cf1-226">Po výbere **Pozrieť detaily** pre jednu z úloh úlohy nájdete ďalšie informácie: čas spracovania, posledný dátum spracovania a všetky chyby a varovania spojené s úlohou.</span><span class="sxs-lookup"><span data-stu-id="d9cf1-226">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="d9cf1-227">Nasledujúci krok</span><span class="sxs-lookup"><span data-stu-id="d9cf1-227">Next step</span></span>

<span data-ttu-id="d9cf1-228">Môžete použiť existujúce miery na vytvorenie [vlastného segmentu](segments.md).</span><span class="sxs-lookup"><span data-stu-id="d9cf1-228">You cam use existing measures to create [a customer segment](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
