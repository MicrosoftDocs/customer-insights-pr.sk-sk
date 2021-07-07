---
title: Obohaťte profily zákazníkov o údaje od spoločnosti Microsoft
description: Na obohatenie svojich zákazníckych údajov o záujmy značiek a záujmov použite patentované údaje spoločnosti Microsoft.
ms.date: 06/14/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 1b11c325649b91ebb47cde924227eacedae64b7a
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305175"
---
# <a name="enrich-customer-profiles-with-brand-and-interest-affinities-preview"></a><span data-ttu-id="3376b-103">Obohaťte profily zákazníkov o značky a záujmy (ukážka)</span><span class="sxs-lookup"><span data-stu-id="3376b-103">Enrich customer profiles with brand and interest affinities (preview)</span></span>

<span data-ttu-id="3376b-104">Na obohatenie svojich zákazníckych údajov o záujmy značiek a záujmov použite patentované údaje spoločnosti Microsoft.</span><span class="sxs-lookup"><span data-stu-id="3376b-104">Use Microsoft's proprietary data to enrich your customer data with brand and interest affinities.</span></span> <span data-ttu-id="3376b-105">Tieto afinity vychádzajú z údajov od ľudí pochádzajúcich z podobnej demografickej oblasti ako vaši zákazníci.</span><span class="sxs-lookup"><span data-stu-id="3376b-105">These affinities are based on data from people with demographics similar to your customers.</span></span> <span data-ttu-id="3376b-106">Tieto informácie vám pomôžu lepšie porozumieť a segmentovať vašich zákazníkov na základe ich príslušnosti k určitým značkám a záujmom.</span><span class="sxs-lookup"><span data-stu-id="3376b-106">This information helps you to better understand and segment your customers based on their affinities to specific brands and interests.</span></span>

<span data-ttu-id="3376b-107">V prehľadoch cieľových skupín prejdite na **Údaje** > **Obohatenie** na [konfiguráciu a zobrazenie obohatení](enrichment-hub.md).</span><span class="sxs-lookup"><span data-stu-id="3376b-107">In audience insights, go to **Data** > **Enrichment** to [configure and view enrichments](enrichment-hub.md).</span></span>

<span data-ttu-id="3376b-108">Ak chcete nakonfigurovať obohatenie o afinity značiek, prejdite na stránku **Objavovať** a vyberte **Obohatiť moje údaje** na dlaždici **Značky**.</span><span class="sxs-lookup"><span data-stu-id="3376b-108">To configure brand affinities enrichment, go to the **Discover** tab and select **Enrich my data** on the **Brands** tile.</span></span>

<span data-ttu-id="3376b-109">Ak chcete nakonfigurovať obohatenie o afinity záujmov, prejdite na stránku **Objavovať** a vyberte **Obohatiť moje údaje** na dlaždici **Záujmy**.</span><span class="sxs-lookup"><span data-stu-id="3376b-109">To configure interest affinities enrichment, go to the **Discover** tab and select **Enrich my data** on the **Interests** tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="3376b-110">![Dlaždice značiek a záujmov](media/BrandsInterest-tile-Hub.png "Dlaždice značiek a záujmov")</span><span class="sxs-lookup"><span data-stu-id="3376b-110">![Brands and Interests tiles](media/BrandsInterest-tile-Hub.png "Brands and Interest tiles")</span></span>

## <a name="how-we-determine-affinities"></a><span data-ttu-id="3376b-111">Ako určujeme príbuznosti</span><span class="sxs-lookup"><span data-stu-id="3376b-111">How we determine affinities</span></span>

<span data-ttu-id="3376b-112">Údaje o vyhľadávaní online spoločnosti Microsoft používame na to, aby sme zistili príbuznosť značiek a záujmov v rôznych demografických segmentoch (definované podľa veku, pohlavia alebo umiestnenia).</span><span class="sxs-lookup"><span data-stu-id="3376b-112">We use Microsoft’s online search data to find affinities for brands and interests across various demographic segments (defined by age, gender, or location).</span></span> <span data-ttu-id="3376b-113">Objem online vyhľadávania pre určitú značku alebo záujem určuje, akú príbuznosť má demografický segment v porovnaní s inými segmentmi k tejto značke alebo záujmu.</span><span class="sxs-lookup"><span data-stu-id="3376b-113">The online search volume for a brand or interest determines how much affinity a demographic segment, compared to other segments, has to that brand or interest.</span></span>

## <a name="affinity-level-and-score"></a><span data-ttu-id="3376b-114">Úroveň afinity a skóre</span><span class="sxs-lookup"><span data-stu-id="3376b-114">Affinity level and score</span></span>

<span data-ttu-id="3376b-115">V každom obohatenom profile zákazníka poskytujeme dve súvisiace hodnoty: úroveň afinity a skóre afinity.</span><span class="sxs-lookup"><span data-stu-id="3376b-115">On every enriched customer profile, we provide two related values: affinity level and affinity score.</span></span> <span data-ttu-id="3376b-116">Tieto hodnoty vám pomôžu určiť, aká silná je afinita k demografickému segmentu daného profilu, k značke alebo záujmu v porovnaní s ostatnými demografickými segmentmi.</span><span class="sxs-lookup"><span data-stu-id="3376b-116">These values help you determine how strong the affinity is for that profile’s demographic segment, for a brand or interest, as compared to other demographic segments.</span></span>

<span data-ttu-id="3376b-117">*Úroveň afinity* pozostáva zo štyroch úrovní a *skóre afinity* sa počíta na 100-bodovej stupnici, ktorá sa mapuje na úrovne afinity.</span><span class="sxs-lookup"><span data-stu-id="3376b-117">*Affinity level* consists of four levels and *affinity score* is calculated on a 100-point scale that maps to the affinity levels.</span></span>


|<span data-ttu-id="3376b-118">Úroveň afinity</span><span class="sxs-lookup"><span data-stu-id="3376b-118">Affinity level</span></span> |<span data-ttu-id="3376b-119">Skóre afinity</span><span class="sxs-lookup"><span data-stu-id="3376b-119">Affinity score</span></span>  |
|---------|---------|
|<span data-ttu-id="3376b-120">Veľmi vysoká</span><span class="sxs-lookup"><span data-stu-id="3376b-120">Very high</span></span>     | <span data-ttu-id="3376b-121">85 – 100</span><span class="sxs-lookup"><span data-stu-id="3376b-121">85-100</span></span>       |
|<span data-ttu-id="3376b-122">Vysoký</span><span class="sxs-lookup"><span data-stu-id="3376b-122">High</span></span>     | <span data-ttu-id="3376b-123">70 – 84</span><span class="sxs-lookup"><span data-stu-id="3376b-123">70-84</span></span>        |
|<span data-ttu-id="3376b-124">Stredný</span><span class="sxs-lookup"><span data-stu-id="3376b-124">Medium</span></span>     | <span data-ttu-id="3376b-125">35 – 69</span><span class="sxs-lookup"><span data-stu-id="3376b-125">35-69</span></span>        |
|<span data-ttu-id="3376b-126">Nízky</span><span class="sxs-lookup"><span data-stu-id="3376b-126">Low</span></span>     | <span data-ttu-id="3376b-127">1 – 34</span><span class="sxs-lookup"><span data-stu-id="3376b-127">1-34</span></span>        |

<span data-ttu-id="3376b-128">V závislosti od podrobností, ktoré chcete pri meraní afinity, môžete použiť buď úroveň afinity alebo skóre.</span><span class="sxs-lookup"><span data-stu-id="3376b-128">Depending on the granularity you would like for measuring the affinity, you can use either affinity level or score.</span></span> <span data-ttu-id="3376b-129">Skóre afinity vám dáva presnejšiu kontrolu.</span><span class="sxs-lookup"><span data-stu-id="3376b-129">Affinity score gives you more precise control.</span></span>

## <a name="supported-countriesregions"></a><span data-ttu-id="3376b-130">Podporované krajiny/regióny</span><span class="sxs-lookup"><span data-stu-id="3376b-130">Supported countries/regions</span></span>

<span data-ttu-id="3376b-131">V súčasnosti podporujeme možnosti nasledujúcich krajín/regiónov: Austrália, Kanada (angličtina), Francúzsko, Nemecko, Spojené kráľovstvo alebo Spojené štáty (angličtina).</span><span class="sxs-lookup"><span data-stu-id="3376b-131">We currently support the following country/region options: Australia, Canada (English), France, Germany, United Kingdom, or United States (English).</span></span>

<span data-ttu-id="3376b-132">Ak chcete zvoliť krajinu alebo región, otvorte stránku **Obohatenie značiek** alebo **Obohatenie záujmov** a vyberte položku **Zmeniť** vedľa položky **Krajina/región**.</span><span class="sxs-lookup"><span data-stu-id="3376b-132">To select a country or region, open **Brands enrichment** or **Interest enrichment** and select **Change** next to **Country/Region**.</span></span> <span data-ttu-id="3376b-133">Na table **Nastavenia krajiny/regiónu** vyberte možnosť a následne položku **Použiť**.</span><span class="sxs-lookup"><span data-stu-id="3376b-133">In the **Country/Region settings** pane, choose an option and select **Apply**.</span></span>

### <a name="implications-related-to-country-selection"></a><span data-ttu-id="3376b-134">Dôsledky týkajúce sa výberu krajiny</span><span class="sxs-lookup"><span data-stu-id="3376b-134">Implications related to country selection</span></span>

- <span data-ttu-id="3376b-135">Pri [výbere vlastných značiek](#define-your-brands-or-interests) systém poskytuje návrhy na základe vybranej krajiny alebo regiónu.</span><span class="sxs-lookup"><span data-stu-id="3376b-135">When [choosing your own brands](#define-your-brands-or-interests), the system provides suggestions based on the selected country or region.</span></span>

- <span data-ttu-id="3376b-136">Pri [výbere odvetvia](#define-your-brands-or-interests) získate najrelevantnejšie značky alebo záujmy na základe vybranej krajiny alebo regiónu.</span><span class="sxs-lookup"><span data-stu-id="3376b-136">When [choosing an industry](#define-your-brands-or-interests), you'll get the most relevant brands or interests based on the selected country or region.</span></span>

- <span data-ttu-id="3376b-137">Pri [obohacovaní profilov](#refresh-enrichment) obohatíme všetky profily zákazníkov, pre ktoré získame údaje o vybraných značkách a záujmoch, vrátane profilov, ktoré sa nenachádzajú vo vybranej krajine alebo regióne.</span><span class="sxs-lookup"><span data-stu-id="3376b-137">When [enriching profiles](#refresh-enrichment), we'll enrich all customer profiles for which we get data for the selected brands and interests, including profiles that are not in the selected country or region.</span></span> <span data-ttu-id="3376b-138">Napríklad ak ste vybrali Nemecko, obohatíme profily nachádzajúce sa v USA, ak máme k dispozícii údaje o vybraných značkách a záujmoch v USA.</span><span class="sxs-lookup"><span data-stu-id="3376b-138">For example, if you selected Germany, we'll enrich profiles located in the United States if we have data available for the selected brands and interests in the US.</span></span>

## <a name="configure-enrichment"></a><span data-ttu-id="3376b-139">Konfigurácia obohatenia</span><span class="sxs-lookup"><span data-stu-id="3376b-139">Configure enrichment</span></span>

<span data-ttu-id="3376b-140">Prehliadka so sprievodcom vám pomôže pri konfigurácii obohatení.</span><span class="sxs-lookup"><span data-stu-id="3376b-140">A guided experience helps you through the configuration of the enrichments.</span></span> 

### <a name="define-your-brands-or-interests"></a><span data-ttu-id="3376b-141">Definujte svoje značky alebo záujmy</span><span class="sxs-lookup"><span data-stu-id="3376b-141">Define your brands or interests</span></span>

<span data-ttu-id="3376b-142">Vyberte si až päť značiek alebo záujmov pomocou jednej alebo oboch z týchto možností:</span><span class="sxs-lookup"><span data-stu-id="3376b-142">Choose up to five brands or interests using one or both of these options:</span></span>

- <span data-ttu-id="3376b-143">**Odvetvie**: Z rozbaľovacieho zoznamu vyberte svoje odvetvie a potom si vyberte z top značiek alebo záujmov pre dané odvetvie.</span><span class="sxs-lookup"><span data-stu-id="3376b-143">**Industry**: Select your industry from the dropdown list and then choose from the top brands or interests for that industry.</span></span>
- <span data-ttu-id="3376b-144">**Vyberte svoje vlastné**: Zadajte značku alebo záujem, ktorý je relevantný pre vašu organizáciu, a potom si vyberte zodpovedajúce návrhy.</span><span class="sxs-lookup"><span data-stu-id="3376b-144">**Choose your own**: Enter a brand or interest that is relevant to your organization and then choose from the matching suggestions.</span></span> <span data-ttu-id="3376b-145">Ak neuvedieme hľadanú značku alebo záujem, pošlite nám svoje pripomienky pomocou odkazu **Navrhnúť**.</span><span class="sxs-lookup"><span data-stu-id="3376b-145">If we don't list a brand or interest you're looking for, send us feedback using the **Suggest** link.</span></span>

### <a name="review-enrichment-preferences"></a><span data-ttu-id="3376b-146">Kontrola predvolieb obohacovania</span><span class="sxs-lookup"><span data-stu-id="3376b-146">Review enrichment preferences</span></span>

<span data-ttu-id="3376b-147">Skontrolujte svoje predvolené predvoľby obohatenia a podľa potreby ich aktualizujte.</span><span class="sxs-lookup"><span data-stu-id="3376b-147">Review your default enrichment preferences and update them as needed.</span></span>

:::image type="content" source="media/affinity-enrichment-preferences.png" alt-text="Snímka obrazovky okna s predvoľbami obohacovania.":::

### <a name="select-entity-to-enrich"></a><span data-ttu-id="3376b-149">Vyberte entitu na obohatenie</span><span class="sxs-lookup"><span data-stu-id="3376b-149">Select entity to enrich</span></span>

<span data-ttu-id="3376b-150">Stlačte možnosť **Obohatená entita** a vyberte množinu údajov, ktorú chcete obohatiť o údaje spoločnosti od spoločnosti Microsoft.</span><span class="sxs-lookup"><span data-stu-id="3376b-150">Select **Enriched entity** and choose the data set you want to enrich with company data from the Microsoft.</span></span> <span data-ttu-id="3376b-151">Môžete zvoliť entitu Zákazník, aby ste obohatili všetky svoje zákaznícke profily, alebo vyberte entitu segmentu, aby ste obohatili iba profily zákazníkov obsiahnuté v danom segmente.</span><span class="sxs-lookup"><span data-stu-id="3376b-151">You can select the Customer entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

### <a name="map-your-fields"></a><span data-ttu-id="3376b-152">Priraďte svoje polia</span><span class="sxs-lookup"><span data-stu-id="3376b-152">Map your fields</span></span>

<span data-ttu-id="3376b-153">Mapujte polia z vašej zjednotenej entity zákazníka a definujte demografický segment, ktorý má systém používať na obohatenie vašich údajov o zákazníkoch.</span><span class="sxs-lookup"><span data-stu-id="3376b-153">Map fields from your unified customer entity to define the demographic segment you want the system to use for enriching your customer data.</span></span> <span data-ttu-id="3376b-154">Mapujte krajinu/región a minimálne atribúty Dátum narodenia alebo Pohlavie.</span><span class="sxs-lookup"><span data-stu-id="3376b-154">Map Country/Region and at least Date of Birth or Gender attributes.</span></span> <span data-ttu-id="3376b-155">Okrem toho musíte namapovať aspoň jedno mesto (a štát/kraj) alebo PSČ.</span><span class="sxs-lookup"><span data-stu-id="3376b-155">Additionally, you must map at least one of City (and State/Province) or Postal code.</span></span> <span data-ttu-id="3376b-156">Zvoľte možnosť **Upraviť** na definovanie mapovania polí a keď to dokončíte, stlačte možnosť **Použiť**.</span><span class="sxs-lookup"><span data-stu-id="3376b-156">Select **Edit** to define the mapping of the fields and select **Apply** when you're done.</span></span> <span data-ttu-id="3376b-157">Vyberte **Uložiť** na dokončenie mapovania polí.</span><span class="sxs-lookup"><span data-stu-id="3376b-157">Select **Save** to complete the field mapping.</span></span>

<span data-ttu-id="3376b-158">Podporované sú nasledujúce formáty a hodnoty (hodnoty nerozlišujú veľké a malé písmená):</span><span class="sxs-lookup"><span data-stu-id="3376b-158">The following formats and values are supported (values are not case-sensitive):</span></span>

- <span data-ttu-id="3376b-159">**Dátum narodenia**: Počas prijímania údajov vám odporúčame previesť dátum narodenia na typ DateTime.</span><span class="sxs-lookup"><span data-stu-id="3376b-159">**Date of Birth**: We recommend that date of birth is converted to DateTime type during data ingestion.</span></span> <span data-ttu-id="3376b-160">Prípadne to môže byť reťazec vo formáte [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) „rrrr-MM-dd“ alebo „rrrr-MM-ddTHH:mm:ss“.</span><span class="sxs-lookup"><span data-stu-id="3376b-160">Alternatively, it can be a string in [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) format "yyyy-MM-dd" or "yyyy-MM-ddTHH:mm:ss".</span></span>
- <span data-ttu-id="3376b-161">**Pohlavie**: muž, žena, neznáme.</span><span class="sxs-lookup"><span data-stu-id="3376b-161">**Gender**: Male, Female, Unknown.</span></span>
- <span data-ttu-id="3376b-162">**Poštové smerovacie číslo**: Päťmiestne PSČ pre Spojené štáty, štandardné poštové smerovacie číslo v ostatných štátoch.</span><span class="sxs-lookup"><span data-stu-id="3376b-162">**Postal code**: Five-digit ZIP codes for United States, standard postal code everywhere else.</span></span>
- <span data-ttu-id="3376b-163">**Mesto**: názov mesta v angličtine.</span><span class="sxs-lookup"><span data-stu-id="3376b-163">**City**: City name in English.</span></span>
- <span data-ttu-id="3376b-164">**Štát/provincia**: Dvojpísmenová skratka pre USA a Kanadu.</span><span class="sxs-lookup"><span data-stu-id="3376b-164">**State/Province**: Two-letter abbreviation for the US and Canada.</span></span> <span data-ttu-id="3376b-165">Dvoj- alebo trojpísmenková skratka pre Austráliu.</span><span class="sxs-lookup"><span data-stu-id="3376b-165">Two- or three-letter abbreviation for Australia.</span></span> <span data-ttu-id="3376b-166">Nevzťahuje sa na Francúzsko, Nemecko ani Spojené kráľovstvo.</span><span class="sxs-lookup"><span data-stu-id="3376b-166">Not applicable for France, Germany, or the UK.</span></span>
- <span data-ttu-id="3376b-167">**Krajina/oblasť**:</span><span class="sxs-lookup"><span data-stu-id="3376b-167">**Country/Region**:</span></span>

  - <span data-ttu-id="3376b-168">USA: Spojené štáty americké, Spojené štáty, USA, US, Amerika</span><span class="sxs-lookup"><span data-stu-id="3376b-168">US: United States of America, United States, USA, US, America</span></span>
  - <span data-ttu-id="3376b-169">CA: Kanada, CA</span><span class="sxs-lookup"><span data-stu-id="3376b-169">CA: Canada, CA</span></span>
  - <span data-ttu-id="3376b-170">GB: Spojené kráľovstvo, UK, Veľká Británia, GB, Spojené kráľovstvo Veľkej Británie a Severného Írska, Spojené kráľovstvo Veľkej Británie</span><span class="sxs-lookup"><span data-stu-id="3376b-170">GB: United Kingdom, UK, Great Britain, GB, United Kingdom of Great Britain and Northern Ireland, United Kingdom of Great Britain</span></span>
  - <span data-ttu-id="3376b-171">AU: Austrália, AU, Austrálske spoločenstvo</span><span class="sxs-lookup"><span data-stu-id="3376b-171">AU: Australia, AU, Commonwealth of Australia</span></span>
  - <span data-ttu-id="3376b-172">FR: Francúzsko, FR, Francúzska republika</span><span class="sxs-lookup"><span data-stu-id="3376b-172">FR: France, FR, French Republic</span></span>
  - <span data-ttu-id="3376b-173">DE: Nemecko, Deutschland, Allemagne, DE, Spolková republika Nemecko, Nemecká republika</span><span class="sxs-lookup"><span data-stu-id="3376b-173">DE: Germany, German, Deutschland, Allemagne, DE, Federal Republic of Germany, Republic of Germany</span></span>

## <a name="review-and-name-the-enrichment"></a><span data-ttu-id="3376b-174">Skontrolujte a pomenujte obohatenie</span><span class="sxs-lookup"><span data-stu-id="3376b-174">Review and name the enrichment</span></span>

<span data-ttu-id="3376b-175">Nakoniec si prečítate informácie a uvediete názov obohatenia.</span><span class="sxs-lookup"><span data-stu-id="3376b-175">Finally, you get to review the information and provide a name for the enrichment.</span></span>

:::image type="content" source="media/enrichment-interests-summary.png" alt-text="Stránka kontroly záujmov a pomenovania.":::

## <a name="refresh-enrichment"></a><span data-ttu-id="3376b-177">Obnovenie obohatenia</span><span class="sxs-lookup"><span data-stu-id="3376b-177">Refresh enrichment</span></span>

<span data-ttu-id="3376b-178">Spustite obohatenie po nakonfigurovaní značiek, záujmov a mapovania terénu pre demografické údaje.</span><span class="sxs-lookup"><span data-stu-id="3376b-178">Run the enrichment after configuring brands, interests, and the field mapping for demographics.</span></span> <span data-ttu-id="3376b-179">Ak chcete proces spustiť, vyberte položku **Spustiť** na stránke konfigurácie značky alebo záujmu.</span><span class="sxs-lookup"><span data-stu-id="3376b-179">To start the process, select **Run** on the brand or interest configuration page.</span></span> <span data-ttu-id="3376b-180">Okrem toho môžete nechať systém, aby obohatenie spustil automaticky ako súčasť plánovanej obnovy.</span><span class="sxs-lookup"><span data-stu-id="3376b-180">Additionally, you can let the system run the enrichment automatically as part of a scheduled refresh.</span></span>

<span data-ttu-id="3376b-181">V závislosti od veľkosti vašich zákazníckych údajov môže dokončenie procesu obohatenia trvať niekoľko minút.</span><span class="sxs-lookup"><span data-stu-id="3376b-181">Depending on the size of your customer data, it may take several minutes for an enrichment run to complete.</span></span>

> [!TIP]
> <span data-ttu-id="3376b-182">Existuje [šesť druhov stavov](system.md#status-types) pre úlohy/procesy.</span><span class="sxs-lookup"><span data-stu-id="3376b-182">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="3376b-183">Okrem toho väčšina procesov [závisí na ďalších nadväzujúcich procesoch](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="3376b-183">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="3376b-184">Môžete si vybrať stav procesu a zobraziť podrobnosti o priebehu celej úlohy.</span><span class="sxs-lookup"><span data-stu-id="3376b-184">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="3376b-185">Po výbere možnosti **Zobraziť podrobnosti** pre jednu z pracovných úloh nájdete ďalšie informácie: čas spracovania, posledný dátum spracovania a všetky chyby a varovania spojené s danou úlohou.</span><span class="sxs-lookup"><span data-stu-id="3376b-185">After selecting **See details** for one of the job's tasks, you'll find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="3376b-186">Výsledky obohatenia</span><span class="sxs-lookup"><span data-stu-id="3376b-186">Enrichment results</span></span>

<span data-ttu-id="3376b-187">Po dokončení procesu obohacovania prejdite na **Moje obohatenia** a skontrolujte celkový počet obohatených zákazníkov a prehľad značiek a záujmov v obohatených profiloch zákazníkov.</span><span class="sxs-lookup"><span data-stu-id="3376b-187">After running the enrichment process, go to **My enrichments** to review the total number of enriched customers and a breakdown of brands or interests in the enriched customer profiles.</span></span>

:::image type="content" source="media/my-enrichments.png" alt-text="Ukážka výsledkov po spustení procesu obohacovania":::

<span data-ttu-id="3376b-189">Vyberte obohatené údaje výberom **Zobraziť obohatené údaje** v tabuľke.</span><span class="sxs-lookup"><span data-stu-id="3376b-189">Review the enriched data by selecting **View enriched data** in the chart.</span></span> <span data-ttu-id="3376b-190">Obohatené údaje o značkách prejdú do entity **BrandAffinityFromMicrosoft**.</span><span class="sxs-lookup"><span data-stu-id="3376b-190">Enriched data for brands goes to the **BrandAffinityFromMicrosoft** entity.</span></span> <span data-ttu-id="3376b-191">Údaje o záujmoch sú v entite **InterestAffinityFromMicrosoft**.</span><span class="sxs-lookup"><span data-stu-id="3376b-191">Data for interests is in the **InterestAffinityFromMicrosoft** entity.</span></span> <span data-ttu-id="3376b-192">Tieto entity nájdete uvedené aj v skupine **Obohatenie** v časti **Údaje** > **Entity**.</span><span class="sxs-lookup"><span data-stu-id="3376b-192">You'll also find these entities listed in the **Enrichment** group in **Data** > **Entities**.</span></span>

## <a name="see-enrichment-data-on-the-customer-card"></a><span data-ttu-id="3376b-193">Pozrite si údaje o obohatení na karte zákazníka</span><span class="sxs-lookup"><span data-stu-id="3376b-193">See enrichment data on the customer card</span></span>

<span data-ttu-id="3376b-194">Značky a záujmy môžu byť zobrazené aj na jednotlivých zákazníckych kartách.</span><span class="sxs-lookup"><span data-stu-id="3376b-194">Brand and interest affinities can also be viewed on individual customer cards.</span></span> <span data-ttu-id="3376b-195">Prejdite na možnosť **Zákazníci** a zvoľte si profil zákazníka.</span><span class="sxs-lookup"><span data-stu-id="3376b-195">Go to **Customers** and select a customer profile.</span></span> <span data-ttu-id="3376b-196">Na zákazníckej karte nájdete grafy značiek alebo záujmov, ku ktorým majú ľudia v demografickom profile daného zákazníka afinitu.</span><span class="sxs-lookup"><span data-stu-id="3376b-196">In the customer card, you'll find charts for the brands or interests that people in that customer's demographic profile have affinity for.</span></span>

:::image type="content" source="media/enrichment-customer-card.png" alt-text="Karta zákazníka s obohatenými údajmi":::

## <a name="next-steps"></a><span data-ttu-id="3376b-198">Ďalšie kroky</span><span class="sxs-lookup"><span data-stu-id="3376b-198">Next steps</span></span>

<span data-ttu-id="3376b-199">Stavajte na svojich obohatených údajoch o zákazníkoch.</span><span class="sxs-lookup"><span data-stu-id="3376b-199">Build on top of your enriched customer data.</span></span> <span data-ttu-id="3376b-200">Vytvárajte [segmenty](segments.md) a [opatrenia](measures.md), a dokonca [exportujte údaje](export-destinations.md), aby ste mohli poskytovať svojim zákazníkom zážitky šité na mieru.</span><span class="sxs-lookup"><span data-stu-id="3376b-200">Create [Segments](segments.md) and [Measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
