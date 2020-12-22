---
title: Vytváranie a úprava mier
description: Definovanie mier týkajúcich sa zákazníkov s cieľom analyzovať a odrážať výkonnosť určitých oblastí podnikania.
ms.date: 10/15/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: wameng
manager: shellyha
ms.openlocfilehash: 0e214a6eb66abd27f7292db3ce2c2a6e16a8ff33
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406933"
---
# <a name="define-and-manage-measures"></a><span data-ttu-id="badc1-103">Definovanie a spravovanie mier</span><span class="sxs-lookup"><span data-stu-id="badc1-103">Define and manage measures</span></span>

<span data-ttu-id="badc1-104">**Miery** predstavujú kľúčové ukazovatele výkonu (KPI), ktoré odrážajú výkonnosť a zdravie konkrétnych oblastí podnikania.</span><span class="sxs-lookup"><span data-stu-id="badc1-104">**Measures** represent key performance indicators (KPIs) that reflect the performance and health of specific business areas.</span></span> <span data-ttu-id="badc1-105">Prehľady cieľových skupín poskytujú intuitívne prostredie na vytváranie rôznych typov mier pomocou nástroja na tvorbu dotazov, ktorý nevyžaduje, aby ste svoje opatrenia programovali alebo overovali ručne.</span><span class="sxs-lookup"><span data-stu-id="badc1-105">Audience insights provides an intuitive experience for building different types of measures, using a query builder that doesn't require you to code or validate your measures manually.</span></span> <span data-ttu-id="badc1-106">Môžete sledovať svoje obchodné miery na stránke **Domov**, sledovať miery pre konkrétnych zákazníkov na **Karte zákazníka** a používať miery na definovanie segmentov zákazníka na stránke **Segmenty**.</span><span class="sxs-lookup"><span data-stu-id="badc1-106">You can track your business measures on the **Home** page, see measures for specific customers on the **Customer Card**, and use measures to define customer segments on the **Segments** page.</span></span>

## <a name="create-a-measure"></a><span data-ttu-id="badc1-107">Vytvorenie miery</span><span class="sxs-lookup"><span data-stu-id="badc1-107">Create a measure</span></span>

<span data-ttu-id="badc1-108">Táto časť vás prevedie vytvorením miery od nuly.</span><span class="sxs-lookup"><span data-stu-id="badc1-108">This section walks you through creating a measure from scratch.</span></span> <span data-ttu-id="badc1-109">Miery môžete vytvárať s údajmi z viacerých zdrojov údajov, ktoré sú pripojené prostredníctvom entity Zákazník.</span><span class="sxs-lookup"><span data-stu-id="badc1-109">You can build measures with data from multiple data sources that are connected through the Customer entity.</span></span> <span data-ttu-id="badc1-110">Platia niektoré [obmedzenia služby](service-limits.md).</span><span class="sxs-lookup"><span data-stu-id="badc1-110">Some [service limits](service-limits.md) apply.</span></span>

1. <span data-ttu-id="badc1-111">V prehľadoch cieľových skupín prejdite na **Miery**.</span><span class="sxs-lookup"><span data-stu-id="badc1-111">In audience insights, go to **Measures**.</span></span>

2. <span data-ttu-id="badc1-112">Vyberte **Nová miera**.</span><span class="sxs-lookup"><span data-stu-id="badc1-112">Select **New measure**.</span></span>

3. <span data-ttu-id="badc1-113">Vyberte mieru **Typ**:</span><span class="sxs-lookup"><span data-stu-id="badc1-113">Choose the measure **Type**:</span></span>

   - <span data-ttu-id="badc1-114">**Atribút zákazníka**: Jedno pole na zákazníka, ktoré odráža skóre, hodnotu alebo stav pre zákazníka.</span><span class="sxs-lookup"><span data-stu-id="badc1-114">**Customer attribute**: A single field per customer that reflects a score, value, or state for the customer.</span></span> <span data-ttu-id="badc1-115">Atribúty zákazníka sa vytvárajú ako atribúty v novej systémovo generovanej entite s názvom **Miera zákazníka**.</span><span class="sxs-lookup"><span data-stu-id="badc1-115">Customer attributes are created as attributes in a new system-generated entity called **Customer_Measure**.</span></span>

   - <span data-ttu-id="badc1-116">**Miera zákazníka**: Informácie o správaní sa zákazníka s rozpisom podľa vybraných dimenzií.</span><span class="sxs-lookup"><span data-stu-id="badc1-116">**Customer measure**: Insights on customer behavior with breakdown by selected dimensions.</span></span> <span data-ttu-id="badc1-117">Pre každú mieru sa vytvorí nová entita, potenciálne s viacerými záznamami na zákazníka.</span><span class="sxs-lookup"><span data-stu-id="badc1-117">A new entity is generated for each measure, potentially with multiple records per customer.</span></span>

   - <span data-ttu-id="badc1-118">**Obchodná miera**: Sleduje výkonnosť vašej firmy a jej zdravie.</span><span class="sxs-lookup"><span data-stu-id="badc1-118">**Business measure**: Tracks your business performance and health of the business.</span></span> <span data-ttu-id="badc1-119">Obchodné miery môžu mať dva rôzne výstupy: číselný výstup, ktorý sa zobrazuje na stránke **Domov** alebo novú entitu, ktorú nájdete na stránke **Entity**.</span><span class="sxs-lookup"><span data-stu-id="badc1-119">Business measures can have two different outputs: a numeric output that shows on the **Home** page or a new entity that you find on the **Entities** page.</span></span>

4. <span data-ttu-id="badc1-120">Uveďte **Názov** a voliteľný **Zobrazovaný názov**, potom vyberte **Ďalej**.</span><span class="sxs-lookup"><span data-stu-id="badc1-120">Provide a **Name** and an optional **Display name**, then select **Next**.</span></span>

5. <span data-ttu-id="badc1-121">V sekcii **Entity** vyberte prvú entitu z rozbaľovacieho zoznamu.</span><span class="sxs-lookup"><span data-stu-id="badc1-121">In the **Entities** section, select the first entity from the drop-down list.</span></span> <span data-ttu-id="badc1-122">V tomto okamihu by ste sa mali rozhodnúť, či sú potrebné ďalšie entity ako súčasť definície vašej miery.</span><span class="sxs-lookup"><span data-stu-id="badc1-122">At this point, you should decide whether additional entities are needed as part of your measure definition.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="badc1-123">![Definícia miery](media/measure-definition.png "Definícia miery")</span><span class="sxs-lookup"><span data-stu-id="badc1-123">![Measure definition](media/measure-definition.png "Measure definition")</span></span>

   <span data-ttu-id="badc1-124">Ak chcete pridať ďalšie entity, vyberte položku **Pridať entitu** a vyberte entity, ktoré chcete pre danú mieru použiť.</span><span class="sxs-lookup"><span data-stu-id="badc1-124">To add more entities, select **Add entity** and select entities you want to use for the measure.</span></span>

   > [!NOTE]
   > <span data-ttu-id="badc1-125">Môžete vybrať iba entity, ktoré majú vzťahy s východiskovou entitou.</span><span class="sxs-lookup"><span data-stu-id="badc1-125">You can select only entities that have relationships to your starting entity.</span></span> <span data-ttu-id="badc1-126">Ďalšie informácie o definovaní kľúčových vzťahov sa dozviete v časti [Vzťahy](relationships.md).</span><span class="sxs-lookup"><span data-stu-id="badc1-126">For more information about defining relationships, see [Relationships](relationships.md).</span></span>

6. <span data-ttu-id="badc1-127">Voliteľne môžete nakonfigurovať premenné.</span><span class="sxs-lookup"><span data-stu-id="badc1-127">Optionally, you can configure variables.</span></span> <span data-ttu-id="badc1-128">V sekcii **Premenné** vyberte **Nová premenná**.</span><span class="sxs-lookup"><span data-stu-id="badc1-128">In the **Variables** section, select **New variable**.</span></span>

   <span data-ttu-id="badc1-129">Premenné sú výpočty, ktoré sa vykonávajú na každom z vašich vybratých záznamov.</span><span class="sxs-lookup"><span data-stu-id="badc1-129">Variables are calculations that are made on each of your selected records.</span></span> <span data-ttu-id="badc1-130">Napríklad sčítanie predajov v kamenných predajniach (POS) a online pre každý záznam vašich zákazníkov.</span><span class="sxs-lookup"><span data-stu-id="badc1-130">For example, summing point-of-sale (POS) and online sales for each of your customers' records.</span></span>

7. <span data-ttu-id="badc1-131">Zadajte parameter **Názov** pre premennú.</span><span class="sxs-lookup"><span data-stu-id="badc1-131">Provide a **Name** for the variable.</span></span>

8. <span data-ttu-id="badc1-132">V oblasti **Vyjadrenie** vyberte pole, pri ktorom chcete začať s výpočtom.</span><span class="sxs-lookup"><span data-stu-id="badc1-132">In the **Expression** area, choose a field to begin your calculation with.</span></span>

9. <span data-ttu-id="badc1-133">Zadajte výraz do oblasti **Vyjadrenie** pri výbere ďalších polí, ktoré sa zahrnú do vášho výpočtu.</span><span class="sxs-lookup"><span data-stu-id="badc1-133">Type an expression in the **Expression** area while choosing more fields to be included in your calculation.</span></span>

   > [!NOTE]
   > <span data-ttu-id="badc1-134">V súčasnosti sú podporované iba aritmetické výrazy.</span><span class="sxs-lookup"><span data-stu-id="badc1-134">Currently, only arithmetic expressions are supported.</span></span> <span data-ttu-id="badc1-135">Výpočet premenných navyše nie je podporovaný pre entity z rôznych [ciest entít](relationships.md).</span><span class="sxs-lookup"><span data-stu-id="badc1-135">Additionally, variable calculation isn't supported for entities from different [entity paths](relationships.md).</span></span>

10. <span data-ttu-id="badc1-136">Vyberte **Hotovo**.</span><span class="sxs-lookup"><span data-stu-id="badc1-136">Select **Done**.</span></span>

11. <span data-ttu-id="badc1-137">V sekcii **Definícia entity** definujete, ako sa budú vybrané entity a vypočítané premenné agregovať do novej entity alebo atribútu miery.</span><span class="sxs-lookup"><span data-stu-id="badc1-137">In the **Measure definition** section, you'll define how your chosen entities and calculated variables are aggregated in a new measure entity or attribute.</span></span>

12. <span data-ttu-id="badc1-138">Vyberte **Nový rozmer**.</span><span class="sxs-lookup"><span data-stu-id="badc1-138">Select **New dimension**.</span></span> <span data-ttu-id="badc1-139">Rozmer si môžete predstaviť ako funkciu *zoskupiť podľa*.</span><span class="sxs-lookup"><span data-stu-id="badc1-139">You can think of a dimension as a *group by* function.</span></span> <span data-ttu-id="badc1-140">Výstup údajov vašej entity alebo atribútu miery bude zoskupený podľa všetkých vašich definovaných rozmerov.</span><span class="sxs-lookup"><span data-stu-id="badc1-140">The data output of your Measure entity or attribute will be grouped by all of your defined dimensions.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="badc1-141">![Vyberte agregovaný cyklus](media/measures-businessreport-measure-definition2.png "Vyberte agregovaný cyklus")</span><span class="sxs-lookup"><span data-stu-id="badc1-141">![Choose aggregate cycle](media/measures-businessreport-measure-definition2.png "Choose aggregate cycle")</span></span>

    <span data-ttu-id="badc1-142">Vyberte alebo zadajte nasledujúce informácie ako súčasť definície vašej dimenzie:</span><span class="sxs-lookup"><span data-stu-id="badc1-142">Select or enter the following information as part of your dimension's definition:</span></span>

    - <span data-ttu-id="badc1-143">**Entita**: Ak definujete entitu Miera, mala by obsahovať aspoň jeden atribút.</span><span class="sxs-lookup"><span data-stu-id="badc1-143">**Entity**: If you define a Measure entity, it should include at least one attribute.</span></span> <span data-ttu-id="badc1-144">Ak definujete atribút Miera, bude štandardne obsahovať iba jeden atribút.</span><span class="sxs-lookup"><span data-stu-id="badc1-144">If you define a Measure attribute, it will include only one attribute by default.</span></span> <span data-ttu-id="badc1-145">Tento výber sa týka výberu entity, ktorá tento atribút obsahuje.</span><span class="sxs-lookup"><span data-stu-id="badc1-145">This selection is about choosing the entity that includes that attribute.</span></span>
    - <span data-ttu-id="badc1-146">**Pole**: Vyberte konkrétny atribút, ktorý sa má zahrnúť do entity alebo atribútu Miera.</span><span class="sxs-lookup"><span data-stu-id="badc1-146">**Field**: Choose the specific attribute to be included either in your Measure entity or attribute.</span></span>
    - <span data-ttu-id="badc1-147">**Kontajner**: Vyberte, či chcete agregovať údaje denne, mesačne alebo ročne.</span><span class="sxs-lookup"><span data-stu-id="badc1-147">**Bucket**: Choose whether you want to aggregate data on a daily, monthly, or annual basis.</span></span> <span data-ttu-id="badc1-148">Je to povinný výber, iba ak ste vybrali atribút typu dátumu.</span><span class="sxs-lookup"><span data-stu-id="badc1-148">It's a required selection only if you've selected a Date type attribute.</span></span>
    - <span data-ttu-id="badc1-149">**Ako**: Definuje názov nového poľa.</span><span class="sxs-lookup"><span data-stu-id="badc1-149">**As**: Defines the name of your new field.</span></span>
    - <span data-ttu-id="badc1-150">**Zobrazovaný názov**: Definuje zobrazovaný názov poľa.</span><span class="sxs-lookup"><span data-stu-id="badc1-150">**Display name**: Defines the display name of your field.</span></span>

    > [!NOTE]
    > <span data-ttu-id="badc1-151">Vaša obchodná miera sa uloží ako entita s jediným číslom a objaví sa na stránke **Domov**, pokiaľ do merania nepridáte ďalšie dimenzie.</span><span class="sxs-lookup"><span data-stu-id="badc1-151">Your business measure will be saved as a single-number entity and will appear on the **Home** page unless you add more dimensions to your measure.</span></span> <span data-ttu-id="badc1-152">Po pridaní ďalších dimenzií sa miera *nebude* zobrazovať na stránke **Domov**.</span><span class="sxs-lookup"><span data-stu-id="badc1-152">After adding more dimensions, the measure will *not* show up on the **Home** page.</span></span>

13. <span data-ttu-id="badc1-153">Voliteľne pridajte agregačné funkcie.</span><span class="sxs-lookup"><span data-stu-id="badc1-153">Optionally, add aggregation functions.</span></span> <span data-ttu-id="badc1-154">Akákoľvek agregácia, ktorú vytvoríte, má za následok novú hodnotu v rámci vašej entity alebo atribútu Miery.</span><span class="sxs-lookup"><span data-stu-id="badc1-154">Any aggregation that you create results in a new value within your Measures entity or attribute.</span></span> <span data-ttu-id="badc1-155">Podporované agregačné funkcie sú: **Min**, **Max**, **Priemern**, **Medián**, **Súčet**, **Počet jedinečný**, **Prvý** (vezme prvý záznam hodnoty rozmeru) a **Posledný** (vezme posledný záznam pridaný do hodnoty rozmeru).</span><span class="sxs-lookup"><span data-stu-id="badc1-155">Supported aggregation functions are: **Min**, **Max**, **Average**, **Median**, **Sum**, **Count Unique**, **First** (takes the first record of a dimension value), and **Last** (takes the last record added to a dimension value).</span></span>

14. <span data-ttu-id="badc1-156">Výberom možnosti **Uložiť** použijete zmeny miery.</span><span class="sxs-lookup"><span data-stu-id="badc1-156">Select **Save** to apply your changes to the measure.</span></span>

## <a name="manage-your-measures"></a><span data-ttu-id="badc1-157">Spravovanie mier</span><span class="sxs-lookup"><span data-stu-id="badc1-157">Manage your measures</span></span>

<span data-ttu-id="badc1-158">Po vytvorení aspoň jednej miery sa zobrazí zoznam mier na stránke **Miery**.</span><span class="sxs-lookup"><span data-stu-id="badc1-158">After creating at least one measure, you'll see a list of measures on the **Measures** page.</span></span>

<span data-ttu-id="badc1-159">Nájdete tu informácie o type miery, tvorcovi, dátume a čase vytvorenia, poslednom dátume a čase úpravy, stave (či je miera aktívna, neaktívna alebo neúspešná) a poslednom dátume a čase obnovenia.</span><span class="sxs-lookup"><span data-stu-id="badc1-159">You'll find information about the measure type, the creator, creation date and time, last edit date and time, status (whether the measure is active, inactive, or failed), and last refresh date and time.</span></span> <span data-ttu-id="badc1-160">Keď vyberiete mieru zo zoznamu, zobrazí sa ukážka jej výstupu.</span><span class="sxs-lookup"><span data-stu-id="badc1-160">When you select a measure from the list, you can see a preview of its output.</span></span>

<span data-ttu-id="badc1-161">Ak chcete obnoviť všetky svoje miery naraz, vyberte položku **Obnoviť všetko** bez výberu konkrétnej miery.</span><span class="sxs-lookup"><span data-stu-id="badc1-161">To refresh all of your measures at the same time, select **Refresh all** without selecting a specific measure.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="badc1-162">![Akcie na spravovanie jednotlivých mier](media/measure-actions.png "Akcie na spravovanie jednotlivých mier")</span><span class="sxs-lookup"><span data-stu-id="badc1-162">![Actions to manage single measures](media/measure-actions.png "Actions to manage single measures")</span></span>

<span data-ttu-id="badc1-163">Prípadne vyberte mieru zo zoznamu a vykonajte jednu z nasledujúcich akcií:</span><span class="sxs-lookup"><span data-stu-id="badc1-163">Alternatively, select a measure from the list and perform one of the following actions:</span></span>

- <span data-ttu-id="badc1-164">Kliknutím na názov miery zobrazíte podrobnosti.</span><span class="sxs-lookup"><span data-stu-id="badc1-164">Select the measure name to see its details.</span></span>
- <span data-ttu-id="badc1-165">**Upravte** konfiguráciu miery.</span><span class="sxs-lookup"><span data-stu-id="badc1-165">**Edit** the configuration of the measure.</span></span>
- <span data-ttu-id="badc1-166">**Premenujte** mieru.</span><span class="sxs-lookup"><span data-stu-id="badc1-166">**Rename** the measure.</span></span>
- <span data-ttu-id="badc1-167">**Odstráňte** mieru.</span><span class="sxs-lookup"><span data-stu-id="badc1-167">**Delete** the measure.</span></span>
- <span data-ttu-id="badc1-168">Vyberte tri bodky (…) a potom **Obnoviť** na spustenie procesu obnovenia miery.</span><span class="sxs-lookup"><span data-stu-id="badc1-168">Select the ellipsis (...) and then **Refresh** to start the refresh process for the measure.</span></span>
- <span data-ttu-id="badc1-169">Vyberte tri bodky (…) a potom **Stiahnuť** na získanie súboru .CSV miery.</span><span class="sxs-lookup"><span data-stu-id="badc1-169">Select the ellipsis (...) and then **Download** to get a .CSV file of the measure.</span></span>

> [!TIP]
> <span data-ttu-id="badc1-170">Existuje [šesť druhov stavov](system.md#status-types) pre úlohy/procesy.</span><span class="sxs-lookup"><span data-stu-id="badc1-170">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="badc1-171">Okrem toho väčšina procesov [závisí na ďalších nadväzujúcich procesoch](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="badc1-171">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="badc1-172">Môžete si vybrať stav procesu a zobraziť podrobnosti o priebehu celej úlohy.</span><span class="sxs-lookup"><span data-stu-id="badc1-172">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="badc1-173">Po výbere **Pozrieť detaily** pre jednu z úloh úlohy nájdete ďalšie informácie: čas spracovania, posledný dátum spracovania a všetky chyby a varovania spojené s úlohou.</span><span class="sxs-lookup"><span data-stu-id="badc1-173">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="badc1-174">Nasledujúci krok</span><span class="sxs-lookup"><span data-stu-id="badc1-174">Next step</span></span>

<span data-ttu-id="badc1-175">Existujúce miery môžete využiť na vytvorenie svojho prvého segmentu zákazníkov na stránke **Segmenty**.</span><span class="sxs-lookup"><span data-stu-id="badc1-175">You cam use existing measures to create your first customer segment on the **Segments** page.</span></span> <span data-ttu-id="badc1-176">Ďalšie informácie nájdete v časti [Segmenty](segments.md).</span><span class="sxs-lookup"><span data-stu-id="badc1-176">For more information, see [Segments](segments.md).</span></span>
