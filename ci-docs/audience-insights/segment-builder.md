---
title: Slúži na vytvorenie a spravovanie segmentov
description: Vytvorenie segmentov zákazníkov na ich zoskupenie na základe rôznych atribútov.
ms.date: 05/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 550e509a24701fe5fcdeb9d54311872dc954156c
ms.sourcegitcommit: 72603fb39c4d5dbca71128815a2e1692542ea4dc
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 05/19/2021
ms.locfileid: "6064956"
---
# <a name="create-and-manage-segments"></a><span data-ttu-id="261dd-103">Slúži na vytvorenie a spravovanie segmentov</span><span class="sxs-lookup"><span data-stu-id="261dd-103">Create and manage segments</span></span>

<span data-ttu-id="261dd-104">Definujte komplexné filtre okolo zjednotenej entity zákazníka a jej súvisiacich entít.</span><span class="sxs-lookup"><span data-stu-id="261dd-104">Define complex filters around the unified customer entity and its related entities.</span></span> <span data-ttu-id="261dd-105">Každý segment po spracovaní vytvorí skupinu zákazníckych záznamov, ktoré môžete exportovať a podniknúť kroky.</span><span class="sxs-lookup"><span data-stu-id="261dd-105">Each segment, after processing, creates a set of customer records that you can export and take action on.</span></span> <span data-ttu-id="261dd-106">Segmenty sú spravované na stránke **Segmenty**.</span><span class="sxs-lookup"><span data-stu-id="261dd-106">Segments are managed on the **Segments** page.</span></span> 

<span data-ttu-id="261dd-107">Nasledujúci príklad ilustruje možnosti segmentácie.</span><span class="sxs-lookup"><span data-stu-id="261dd-107">The following example illustrates the segmentation capability.</span></span> <span data-ttu-id="261dd-108">Definovali sme segment pre zákazníkov, ktorí za posledných 90 dní objednali tovar aspoň za 500 USD *a* ktorí boli zapojení do hovoru služieb pre zákazníkov, ktorý bol eskalovaný.</span><span class="sxs-lookup"><span data-stu-id="261dd-108">We've defined a segment for customers who ordered at least $500 of goods in the last 90 days *and* who were involved in a customer service call that got escalated.</span></span>

:::image type="content" source="media/segmentation-group1-2.png" alt-text="Snímka obrazovky používateľského rozhrania nástroja na tvorbu segmentov s dvoma skupinami, ktoré určujú segment zákazníka.":::

## <a name="create-a-new-segment"></a><span data-ttu-id="261dd-110">Vytvorenie nového segmentu</span><span class="sxs-lookup"><span data-stu-id="261dd-110">Create a new segment</span></span>

<span data-ttu-id="261dd-111">Existuje niekoľko spôsobov, ako vytvoriť nový segment.</span><span class="sxs-lookup"><span data-stu-id="261dd-111">There are multiple ways to create a new segment.</span></span> <span data-ttu-id="261dd-112">Táto časť popisuje, ako vytvoriť *prázdny segment* od začiatku.</span><span class="sxs-lookup"><span data-stu-id="261dd-112">This section describes how to create a *blank segment* from scratch.</span></span> <span data-ttu-id="261dd-113">Môžete tiež vytvoriť *rýchly segment* na základe existujúcich entít alebo využite modely strojového učenia na získanie *navrhovaných segmentov*.</span><span class="sxs-lookup"><span data-stu-id="261dd-113">You can also create a *quick segment* based on existing entities or make use of machine learning models to get *suggested segments*.</span></span> <span data-ttu-id="261dd-114">Ďalšie informácie: [Prehľad segmentov](segments.md).</span><span class="sxs-lookup"><span data-stu-id="261dd-114">More information: [Segments overview](segments.md).</span></span>

<span data-ttu-id="261dd-115">Pri vytváraní segmentu môžete uložiť koncept.</span><span class="sxs-lookup"><span data-stu-id="261dd-115">While creating a segment, you can save a draft.</span></span> <span data-ttu-id="261dd-116">Bude uložený ako neaktívny segment a nemožno ho aktivovať, pretože je dokončený s platnou konfiguráciou.</span><span class="sxs-lookup"><span data-stu-id="261dd-116">It will be saved as an inactive segment, and can't be activated it finished with a valid configuration.</span></span>

1. <span data-ttu-id="261dd-117">Prejdite na stránku **Segmenty**.</span><span class="sxs-lookup"><span data-stu-id="261dd-117">Go to the **Segments** page.</span></span>

1. <span data-ttu-id="261dd-118">Vyberte **Nový** > **Prázdny segment**.</span><span class="sxs-lookup"><span data-stu-id="261dd-118">Select **New** > **Blank segment**.</span></span>

1. <span data-ttu-id="261dd-119">Na table **Nový segment** vyberte typ segmentu:</span><span class="sxs-lookup"><span data-stu-id="261dd-119">In the **New segment** pane, choose a segment type:</span></span>

   - <span data-ttu-id="261dd-120">**Dynamické segmenty** [sa obnovujú](segments.md#refresh-segments) podľa opakujúceho sa harmonogramu.</span><span class="sxs-lookup"><span data-stu-id="261dd-120">**Dynamic segments** [refresh](segments.md#refresh-segments) on a recurring schedule.</span></span>
   - <span data-ttu-id="261dd-121">**Statické segmenty** sa spustia raz po vytvorení.</span><span class="sxs-lookup"><span data-stu-id="261dd-121">**Static segments** run once when you create it.</span></span>

1. <span data-ttu-id="261dd-122">Uveďte **Názov výstupnej entity** pre daný segment.</span><span class="sxs-lookup"><span data-stu-id="261dd-122">Provide an **Output entity name** for the segment.</span></span> <span data-ttu-id="261dd-123">Voliteľne uveďte zobrazovaný názov a popis, ktorý pomôže identifikovať segment.</span><span class="sxs-lookup"><span data-stu-id="261dd-123">Optionally, provide a display name, and a description that helps identifying the segment.</span></span>

1. <span data-ttu-id="261dd-124">Vyberte **Ďalšie** a prejdite na stránku **Tvorca segmentov**, kde definujete skupinu.</span><span class="sxs-lookup"><span data-stu-id="261dd-124">Select **Next** to get to the **Segment builder** page where you define a group.</span></span> <span data-ttu-id="261dd-125">Skupina je množina zákazníkov.</span><span class="sxs-lookup"><span data-stu-id="261dd-125">A group is a set of customers.</span></span>

1. <span data-ttu-id="261dd-126">Vyberte entity, ktorá obsahuje atribút, podľa ktorého chcete segmentovať.</span><span class="sxs-lookup"><span data-stu-id="261dd-126">Choose the entity that includes the attribute you want to segment by.</span></span>

1. <span data-ttu-id="261dd-127">Vyberte atribút pre segment podľa.</span><span class="sxs-lookup"><span data-stu-id="261dd-127">Choose the attribute to segment by.</span></span> <span data-ttu-id="261dd-128">Tento atribút môže mať jeden zo štyroch typov hodnôt: číselný, reťazec, dátum alebo logický.</span><span class="sxs-lookup"><span data-stu-id="261dd-128">This attribute can have one of four value types: numerical, string, date, or Boolean.</span></span>

1. <span data-ttu-id="261dd-129">Vyberte operátora a hodnotu pre vybraného atribútu.</span><span class="sxs-lookup"><span data-stu-id="261dd-129">Choose an operator and a value for the selected attribute.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="261dd-130">![Filter vlastnej skupiny](media/customer-group-numbers.png "Filter skupiny zákazníkov")</span><span class="sxs-lookup"><span data-stu-id="261dd-130">![Custom group filter](media/customer-group-numbers.png "Customer group filter")</span></span>

   |<span data-ttu-id="261dd-131">Číslo</span><span class="sxs-lookup"><span data-stu-id="261dd-131">Number</span></span> |<span data-ttu-id="261dd-132">Definícia</span><span class="sxs-lookup"><span data-stu-id="261dd-132">Definition</span></span>  |
   |---------|---------|
   |<span data-ttu-id="261dd-133">1</span><span class="sxs-lookup"><span data-stu-id="261dd-133">1</span></span>     |<span data-ttu-id="261dd-134">Entity</span><span class="sxs-lookup"><span data-stu-id="261dd-134">Entity</span></span>          |
   |<span data-ttu-id="261dd-135">2</span><span class="sxs-lookup"><span data-stu-id="261dd-135">2</span></span>     |<span data-ttu-id="261dd-136">Atribút</span><span class="sxs-lookup"><span data-stu-id="261dd-136">Attribute</span></span>          |
   |<span data-ttu-id="261dd-137">3</span><span class="sxs-lookup"><span data-stu-id="261dd-137">3</span></span>    |<span data-ttu-id="261dd-138">Operátor</span><span class="sxs-lookup"><span data-stu-id="261dd-138">Operator</span></span>         |
   |<span data-ttu-id="261dd-139">4</span><span class="sxs-lookup"><span data-stu-id="261dd-139">4</span></span>    |<span data-ttu-id="261dd-140">Hodnota</span><span class="sxs-lookup"><span data-stu-id="261dd-140">Value</span></span>         |

   1. <span data-ttu-id="261dd-141">Na pridanie ďalších podmienok do skupiny môžete použiť dva logické operátory:</span><span class="sxs-lookup"><span data-stu-id="261dd-141">To add more conditions to a group, you can use two logical operators:</span></span>

      - <span data-ttu-id="261dd-142">Operátor **A**: Obe podmienky musia byť splnené ako súčasť procesu segmentácie.</span><span class="sxs-lookup"><span data-stu-id="261dd-142">**AND** operator: Both conditions must be met as part of the segmentation process.</span></span> <span data-ttu-id="261dd-143">Táto voľba je najužitočnejšia, keď definujete podmienky pre rôzne entity.</span><span class="sxs-lookup"><span data-stu-id="261dd-143">This option is most useful when you define conditions across different entities.</span></span>

      - <span data-ttu-id="261dd-144">Operátor **ALEBO**: V rámci procesu segmentácie musí byť splnená jedna z podmienok.</span><span class="sxs-lookup"><span data-stu-id="261dd-144">**OR** operator: Either one of the conditions needs to be met as part of the segmentation process.</span></span> <span data-ttu-id="261dd-145">Táto voľba je najužitočnejšia, keď definujete viac podmienok pre jednu entitu.</span><span class="sxs-lookup"><span data-stu-id="261dd-145">This option is most useful when you define multiple conditions for the same entity.</span></span>

      > [!div class="mx-imgBorder"]
      > <span data-ttu-id="261dd-146">![Operátor ALEBO, ktorý musí splniť ktorúkoľvek z podmienok](media/segmentation-either-condition.png "Operátor ALEBO, ktorý musí splniť ktorúkoľvek z podmienok")</span><span class="sxs-lookup"><span data-stu-id="261dd-146">![OR operator where either condition needs to be met](media/segmentation-either-condition.png "OR operator where either condition needs to be met")</span></span>

      <span data-ttu-id="261dd-147">V súčasnosti je možné vnoriť operátor **ALEBO** pod operátor **A**, ale nie naopak.</span><span class="sxs-lookup"><span data-stu-id="261dd-147">It's currently possible to nest an **OR** operator under an **AND** operator, but not the other way around.</span></span>

   1. <span data-ttu-id="261dd-148">Každá skupina zodpovedá skupine zákazníkov.</span><span class="sxs-lookup"><span data-stu-id="261dd-148">Each group matches set of customers.</span></span> <span data-ttu-id="261dd-149">Skupiny môžete skombinovať tak, aby zahŕňali zákazníkov požadovaných pre váš obchodný prípad.</span><span class="sxs-lookup"><span data-stu-id="261dd-149">You can combine groups to include the customers required for your business case.</span></span>    
   <span data-ttu-id="261dd-150">Vyberte **Pridať skupinu**.</span><span class="sxs-lookup"><span data-stu-id="261dd-150">Select **Add Group**.</span></span>

      > [!div class="mx-imgBorder"]
      > <span data-ttu-id="261dd-151">![Skupina zákazníkov – pridanie skupiny](media/customer-group-add-group.png "Skupina zákazníkov – pridanie skupiny")</span><span class="sxs-lookup"><span data-stu-id="261dd-151">![Customer group add group](media/customer-group-add-group.png "Customer group add group")</span></span>

   1. <span data-ttu-id="261dd-152">Vyberte jedného z nastavených operátorov: **Zjednotiť**, **Prienik** alebo **Okrem**.</span><span class="sxs-lookup"><span data-stu-id="261dd-152">Select one of the set operators: **Union**, **Intersect**, or **Except**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="261dd-153">![Skupina zákazníkov – pridanie zjednotenia](media/customer-group-union.png "Skupina zákazníkov – pridanie zjednotenia")</span><span class="sxs-lookup"><span data-stu-id="261dd-153">![Customer group add union](media/customer-group-union.png "Customer group add union")</span></span>

   - <span data-ttu-id="261dd-154">**Zjednotenie** zjednocuje obe skupiny.</span><span class="sxs-lookup"><span data-stu-id="261dd-154">**Union** unites the two groups.</span></span>

   - <span data-ttu-id="261dd-155">**Prienik** prekrýva obe skupiny.</span><span class="sxs-lookup"><span data-stu-id="261dd-155">**Intersect** overlaps the two groups.</span></span> <span data-ttu-id="261dd-156">Iba údaje, ktoré *sú spoločné* pre obe skupiny, sa zachovávajú v zjednotenej skupine.</span><span class="sxs-lookup"><span data-stu-id="261dd-156">Only data that *is common* to both groups is retained in the unified group.</span></span>

   - <span data-ttu-id="261dd-157">Možnosť **Okrem** kombinuje dve skupiny.</span><span class="sxs-lookup"><span data-stu-id="261dd-157">**Except** combines the two groups.</span></span> <span data-ttu-id="261dd-158">Zachovajú sa iba údaje v skupine A, ktoré *nie sú spoločné* s údajmi v skupine B.</span><span class="sxs-lookup"><span data-stu-id="261dd-158">Only data in group A that *is not common* to data in group B is retained.</span></span>

1. <span data-ttu-id="261dd-159">Ak je entita prepojená so zjednotenou entitou zákazníka prostredníctvom [vzťahov](relationships.md), musíte definovať cestu vzťahov, aby ste vytvorili platný segment.</span><span class="sxs-lookup"><span data-stu-id="261dd-159">If the entity is connected to the unified customer entity through [relationships](relationships.md), you need to define the relationship path to create a valid segment.</span></span> <span data-ttu-id="261dd-160">Pridajte entity z cesty vzťahov, kým si nevyberiete entitu **Zákazník: CustomerInsights** z rozbaľovacej ponuky.</span><span class="sxs-lookup"><span data-stu-id="261dd-160">Add the entities from the relationship path until you can select the **Customer:CustomerInsights** entity from the dropdown.</span></span> <span data-ttu-id="261dd-161">Potom stlačte možnosť **Všetky záznamy** pre každý krok.</span><span class="sxs-lookup"><span data-stu-id="261dd-161">Then, choose **All records** for each step.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="261dd-162">![Cesta vzťahov pri vytváraní segmentov](media/segments-multiple-relationships.png "Cesta vzťahov pri vytváraní segmentov")</span><span class="sxs-lookup"><span data-stu-id="261dd-162">![Relationship path during segment creation](media/segments-multiple-relationships.png "Relationship path during segment creation")</span></span>

1. <span data-ttu-id="261dd-163">V predvolenom nastavení segmenty generujú výstupnú entitu, ktorá obsahuje všetky atribúty profilov zákazníkov, ktoré zodpovedajú definovaným filtrom.</span><span class="sxs-lookup"><span data-stu-id="261dd-163">By default, segments generate an output entity that contains all attributes of customer profiles which match the defined filters.</span></span> <span data-ttu-id="261dd-164">Ak je segment založený na iných entitách ako entita *Zákazník*, môžete do výstupnej entity pridať ďalšie atribúty z týchto entít.</span><span class="sxs-lookup"><span data-stu-id="261dd-164">If a segment is based on other entities than the *Customer* entity, you can add more attributes from these entities to the output entity.</span></span> <span data-ttu-id="261dd-165">Stlačte možnosť **Atribúty projektu** na výber atribútov, ktoré sa pripoja k výstupnej entite.</span><span class="sxs-lookup"><span data-stu-id="261dd-165">Select **Project attributes** to choose the attributes that will be appended to the output entity.</span></span>  
  
   <span data-ttu-id="261dd-166">Príklad: Segment je založený na entite, ktorá obsahuje údaje o činnosti zákazníkov súvisiace s entitou *Zákazník*.</span><span class="sxs-lookup"><span data-stu-id="261dd-166">Example: A segment is based on an entity that contains customer activity data which is related to the *Customer* entity.</span></span> <span data-ttu-id="261dd-167">Segment vyhľadáva všetkých zákazníkov, ktorí zavolali na technickú podporu za posledných 60 dní.</span><span class="sxs-lookup"><span data-stu-id="261dd-167">The segment looks for all customers that called the help desk in the last 60 days.</span></span> <span data-ttu-id="261dd-168">Môžete sa rozhodnúť pridať trvanie hovoru a počet hovorov ku všetkým zodpovedajúcim záznamom zákazníka vo výstupnej entite.</span><span class="sxs-lookup"><span data-stu-id="261dd-168">You can choose to append the call duration and the number of calls to all matching customer records in the output entity.</span></span> <span data-ttu-id="261dd-169">Tieto informácie môžu byť užitočné pri zasielaní e-mailov s užitočnými odkazmi na články online pomoci a časté otázky zákazníkom, ktorí často volali.</span><span class="sxs-lookup"><span data-stu-id="261dd-169">This information might be useful to send an email with helpful links to online help articles and FAQs to customers who called frequently.</span></span>

   > [!NOTE]
   > - <span data-ttu-id="261dd-170">Projektované atribúty fungujú iba pre entity, ktoré majú vzťah typu jedna k mnohým so entitou zákazníka.</span><span class="sxs-lookup"><span data-stu-id="261dd-170">Projected attributes only work for entities that have a one-to-many relationship with the customer entity.</span></span> <span data-ttu-id="261dd-171">Napríklad jeden zákazník môže mať viac predplatných.</span><span class="sxs-lookup"><span data-stu-id="261dd-171">For example, one customer can have multiple subscriptions.</span></span>
   > - <span data-ttu-id="261dd-172">Atribúty môžete projektovať iba z entity, ktorá sa používa v každej skupine segmentových dotazov, ktoré zostavujete.</span><span class="sxs-lookup"><span data-stu-id="261dd-172">You can only project attributes from an entity that is used in every group of segment query you are building.</span></span>
   > - <span data-ttu-id="261dd-173">Pri použití množinových operátorov sa zohľadňujú projektované atribúty.</span><span class="sxs-lookup"><span data-stu-id="261dd-173">Projected attributes are factored in when using set operators.</span></span>

1. <span data-ttu-id="261dd-174">Segment uložte výberom položky **Uložiť**.</span><span class="sxs-lookup"><span data-stu-id="261dd-174">Select **Save** to save your segment.</span></span> <span data-ttu-id="261dd-175">Váš segment bude uložený a spracovaný, ak budú splnené všetky požiadavky.</span><span class="sxs-lookup"><span data-stu-id="261dd-175">Your segment will be saved and processed if all requirements are validated.</span></span> <span data-ttu-id="261dd-176">V opačnom prípade sa uloží ako koncept.</span><span class="sxs-lookup"><span data-stu-id="261dd-176">Otherwise, it will be saved as a draft.</span></span>

1. <span data-ttu-id="261dd-177">Ak sa chcete vrátiť späť na stránku **Segmenty**, vyberte **Späť na segmenty**.</span><span class="sxs-lookup"><span data-stu-id="261dd-177">Select **Back to segments** to go back to the **Segments** page.</span></span>



## <a name="quick-segments"></a><span data-ttu-id="261dd-178">Rýchle segmenty</span><span class="sxs-lookup"><span data-stu-id="261dd-178">Quick segments</span></span>

<span data-ttu-id="261dd-179">Rýchle segmenty vám umožňujú rýchlo vytvárať jednoduché segmenty pomocou jedného operátora a získať tak rýchlejší prehľad.</span><span class="sxs-lookup"><span data-stu-id="261dd-179">Quick segments let you build simple segments with a single operator quickly for faster insights.</span></span>

1. <span data-ttu-id="261dd-180">Na stránke **Segmenty** stlačte možnosť **Nový** > **Vytvoriť z**.</span><span class="sxs-lookup"><span data-stu-id="261dd-180">On the **Segments** page, select **New** > **Create from**.</span></span>

   - <span data-ttu-id="261dd-181">Vyberte možnosť **Profily** na vytvorenie segmentu, ktorý je založený na *zjednotenej entite zákazníka*.</span><span class="sxs-lookup"><span data-stu-id="261dd-181">Select the **Profiles** option to build a segment that is based on the *unified customer* entity.</span></span>
   - <span data-ttu-id="261dd-182">Stlačte možnosť **Opatrenia** a vytvorte segment okolo opatrení, ktoré ste predtým vytvorili.</span><span class="sxs-lookup"><span data-stu-id="261dd-182">Select the **Measures** option to build a segment around  measures you have previously created.</span></span>
   - <span data-ttu-id="261dd-183">Vyberte možnosť **Analýza** na zostavenie segmentu okolo jednej z výstupných entít, ktoré ste vygenerovali pomocou funkcií **Predpovede** alebo **Vlastné modely**.</span><span class="sxs-lookup"><span data-stu-id="261dd-183">Select the **Intelligence** option to build a segment around one of the output entities you generated using either the **Predictions** or **Custom Models** capabilities.</span></span>

2. <span data-ttu-id="261dd-184">V dialógovom okne **Nový rýchly segment** vyberte atribút z rozbaľovacej ponuky **Pole**.</span><span class="sxs-lookup"><span data-stu-id="261dd-184">In the **New quick segment** dialog box, select an attribute from the **Field** dropdown.</span></span>

3. <span data-ttu-id="261dd-185">Systém poskytne niektoré ďalšie informácie, ktoré vám pomôžu vytvoriť lepšie segmenty vašich zákazníkov.</span><span class="sxs-lookup"><span data-stu-id="261dd-185">The system will provide some additional insights that help you create better segments of your customers.</span></span>
   - <span data-ttu-id="261dd-186">Pre kategorické polia zobrazíme 10 najvyšších počtov zákazníkov.</span><span class="sxs-lookup"><span data-stu-id="261dd-186">For categorical fields, we'll show 10 top customer counts.</span></span> <span data-ttu-id="261dd-187">Vyberte **Hodnota** a potom **Skontrolovať**.</span><span class="sxs-lookup"><span data-stu-id="261dd-187">Choose a **Value** and select **Review**.</span></span>

   - <span data-ttu-id="261dd-188">Pokiaľ ide o číselný atribút, systém ukáže, ktorá hodnota atribútu spadá pod percentil každého zákazníka.</span><span class="sxs-lookup"><span data-stu-id="261dd-188">For a numerical attribute, the system will show what attribute value falls under each customer's percentile.</span></span> <span data-ttu-id="261dd-189">Vyberte **Operátor** a **Hodnota**, potom vyberte **Skontrolovať**.</span><span class="sxs-lookup"><span data-stu-id="261dd-189">Choose an **Operator** and a **Value**, then select **Review**.</span></span>

4. <span data-ttu-id="261dd-190">Systém vám poskytne **Odhadovanú veľkosť segmentu**.</span><span class="sxs-lookup"><span data-stu-id="261dd-190">The system will provide you with an **Estimated segment size**.</span></span> <span data-ttu-id="261dd-191">Môžete si vybrať, či chcete vygenerovať segment, ktorý ste definovali, alebo ho znova opraviť, aby ste získali inú veľkosť segmentu.</span><span class="sxs-lookup"><span data-stu-id="261dd-191">You can choose whether to generate the segment you've defined, or first revisit it to get a different segment size.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="261dd-192">![Názov a odhad rýchleho segmentu](media/quick-segment-name.png "Názov a odhad rýchleho segmentu")</span><span class="sxs-lookup"><span data-stu-id="261dd-192">![Name and estimation for a quick segment](media/quick-segment-name.png "Name and estimation for a quick segment")</span></span>

5. <span data-ttu-id="261dd-193">Zadajte **Názov** pre svoj segment.</span><span class="sxs-lookup"><span data-stu-id="261dd-193">Provide a **Name** for your segment.</span></span> <span data-ttu-id="261dd-194">Voliteľne zadajte **Zobrazovaný názov**.</span><span class="sxs-lookup"><span data-stu-id="261dd-194">Optionally, provide a **Display name**.</span></span>

6. <span data-ttu-id="261dd-195">Výberom položky **Uložiť** vytvorte segment.</span><span class="sxs-lookup"><span data-stu-id="261dd-195">Select **Save** to create your segment.</span></span>

7. <span data-ttu-id="261dd-196">Po dokončení spracovania môžete segment zobraziť ako akýkoľvek iný segment, ktorý ste vytvorili.</span><span class="sxs-lookup"><span data-stu-id="261dd-196">After the segment has finished processing, you can view it like any other segment you've created.</span></span>

## <a name="next-steps"></a><span data-ttu-id="261dd-197">Ďalšie kroky</span><span class="sxs-lookup"><span data-stu-id="261dd-197">Next steps</span></span>

<span data-ttu-id="261dd-198">[Exportujte segment](export-destinations.md) a preskúmajte [kartu zákazníka](customer-card-add-in.md) a [konektory](export-power-bi.md), aby ste získali prehľad o úrovni zákazníka.</span><span class="sxs-lookup"><span data-stu-id="261dd-198">[Export a segment](export-destinations.md) and explore the [Customer Card](customer-card-add-in.md) and [Connectors](export-power-bi.md) to get insights on the customer level.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
