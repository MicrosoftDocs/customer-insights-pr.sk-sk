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
ms.openlocfilehash: e92360bb886739cfe477ce1d2eb62219228a0292
ms.sourcegitcommit: d4b4053f6ee8f60f1a214982c4726c9de84615ef
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 06/14/2021
ms.locfileid: "6245726"
---
# <a name="enrich-customer-profiles-with-brand-and-interest-affinities-preview"></a><span data-ttu-id="a3be0-103">Obohaťte profily zákazníkov o značky a záujmy (ukážka)</span><span class="sxs-lookup"><span data-stu-id="a3be0-103">Enrich customer profiles with brand and interest affinities (preview)</span></span>

<span data-ttu-id="a3be0-104">Na obohatenie svojich zákazníckych údajov o záujmy značiek a záujmov použite patentované údaje spoločnosti Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a3be0-104">Use Microsoft's proprietary data to enrich your customer data with brand and interest affinities.</span></span> <span data-ttu-id="a3be0-105">Tieto afinity sa určujú na základe údajov od ľudí s podobnou demografiou ako vaši zákazníci.</span><span class="sxs-lookup"><span data-stu-id="a3be0-105">These affinities are determined based on data from people with similar demographics to your customers.</span></span> <span data-ttu-id="a3be0-106">Tieto informácie vám pomôžu lepšie porozumieť a segmentovať vašich zákazníkov na základe ich príslušnosti k určitým značkám a záujmom.</span><span class="sxs-lookup"><span data-stu-id="a3be0-106">This information helps you to better understand and segment your customers based on their affinities to specific brands and interests.</span></span>

<span data-ttu-id="a3be0-107">V prehľadoch cieľových skupín prejdite na **Údaje** > **Obohatenie** na [konfiguráciu a zobrazenie obohatení](enrichment-hub.md).</span><span class="sxs-lookup"><span data-stu-id="a3be0-107">In audience insights, go to **Data** > **Enrichment** to [configure and view enrichments](enrichment-hub.md).</span></span>

<span data-ttu-id="a3be0-108">Ak chcete nakonfigurovať obohatenie o afinity značiek, prejdite na stránku **Objavovať** a vyberte **Obohatiť moje údaje** na dlaždici **Značky**.</span><span class="sxs-lookup"><span data-stu-id="a3be0-108">To configure brand affinities enrichment, go to the **Discover** tab and select **Enrich my data** on the **Brands** tile.</span></span>

<span data-ttu-id="a3be0-109">Ak chcete nakonfigurovať obohatenie o afinity záujmov, prejdite na stránku **Objavovať** a vyberte **Obohatiť moje údaje** na dlaždici **Záujmy**.</span><span class="sxs-lookup"><span data-stu-id="a3be0-109">To configure interest affinities enrichment, go to the **Discover** tab and select **Enrich my data** on the **Interests** tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="a3be0-110">![Dlaždice Značky a záujmy](media/BrandsInterest-tile-Hub.png "Dlaždice Značky a záujmy")</span><span class="sxs-lookup"><span data-stu-id="a3be0-110">![Brands & Interests tiles](media/BrandsInterest-tile-Hub.png "Brands & Interest tiles")</span></span>

## <a name="how-we-determine-affinities"></a><span data-ttu-id="a3be0-111">Ako určujeme príbuznosti</span><span class="sxs-lookup"><span data-stu-id="a3be0-111">How we determine affinities</span></span>

<span data-ttu-id="a3be0-112">Údaje o vyhľadávaní online spoločnosti Microsoft používame na to, aby sme zistili príbuznosť značiek a záujmov v rôznych demografických segmentoch (definované podľa veku, pohlavia alebo umiestnenia).</span><span class="sxs-lookup"><span data-stu-id="a3be0-112">We use Microsoft’s online search data to find affinities for brands and interests across various demographic segments (defined by age, gender, or location).</span></span> <span data-ttu-id="a3be0-113">Objem online vyhľadávania pre určitú značku alebo záujem určuje, akú príbuznosť má demografický segment v porovnaní s inými segmentmi k tejto značke alebo záujmu.</span><span class="sxs-lookup"><span data-stu-id="a3be0-113">The online search volume for a brand or interest determines how much affinity a demographic segment, compared to other segments, has to that brand or interest.</span></span>

## <a name="affinity-level-and-score"></a><span data-ttu-id="a3be0-114">Úroveň afinity a skóre</span><span class="sxs-lookup"><span data-stu-id="a3be0-114">Affinity level and score</span></span>

<span data-ttu-id="a3be0-115">V každom obohatenom profile zákazníka poskytujeme dve súvisiace hodnoty – úroveň afinity a skóre afinity.</span><span class="sxs-lookup"><span data-stu-id="a3be0-115">On every enriched customer profile, we provide two related values – affinity level and affinity score.</span></span> <span data-ttu-id="a3be0-116">Tieto hodnoty vám pomôžu určiť, aká silná je afinita k demografickému segmentu daného profilu, k značke alebo záujmu v porovnaní s ostatnými demografickými segmentmi.</span><span class="sxs-lookup"><span data-stu-id="a3be0-116">These values help you determine how strong the affinity is for that profile’s demographic segment, for a brand or interest, as compared to other demographic segments.</span></span>

<span data-ttu-id="a3be0-117">*Úroveň afinity* pozostáva zo štyroch úrovní a *skóre afinity* sa počíta na 100-bodovej stupnici, ktorá sa mapuje na úrovne afinity.</span><span class="sxs-lookup"><span data-stu-id="a3be0-117">*Affinity level* consists of four levels and *affinity score* is calculated on a 100-point scale that maps to the affinity levels.</span></span>


|<span data-ttu-id="a3be0-118">Úroveň afinity</span><span class="sxs-lookup"><span data-stu-id="a3be0-118">Affinity level</span></span> |<span data-ttu-id="a3be0-119">Skóre afinity</span><span class="sxs-lookup"><span data-stu-id="a3be0-119">Affinity score</span></span>  |
|---------|---------|
|<span data-ttu-id="a3be0-120">Veľmi vysoká</span><span class="sxs-lookup"><span data-stu-id="a3be0-120">Very high</span></span>     | <span data-ttu-id="a3be0-121">85 – 100</span><span class="sxs-lookup"><span data-stu-id="a3be0-121">85-100</span></span>       |
|<span data-ttu-id="a3be0-122">Vysoký</span><span class="sxs-lookup"><span data-stu-id="a3be0-122">High</span></span>     | <span data-ttu-id="a3be0-123">70 – 84</span><span class="sxs-lookup"><span data-stu-id="a3be0-123">70-84</span></span>        |
|<span data-ttu-id="a3be0-124">Stredný</span><span class="sxs-lookup"><span data-stu-id="a3be0-124">Medium</span></span>     | <span data-ttu-id="a3be0-125">35 – 69</span><span class="sxs-lookup"><span data-stu-id="a3be0-125">35-69</span></span>        |
|<span data-ttu-id="a3be0-126">Nízky</span><span class="sxs-lookup"><span data-stu-id="a3be0-126">Low</span></span>     | <span data-ttu-id="a3be0-127">1 – 34</span><span class="sxs-lookup"><span data-stu-id="a3be0-127">1-34</span></span>        |

<span data-ttu-id="a3be0-128">V závislosti od podrobností, ktoré chcete pri meraní afinity, môžete použiť buď úroveň afinity alebo skóre.</span><span class="sxs-lookup"><span data-stu-id="a3be0-128">Depending on the granularity you would like for measuring the affinity, you can use either affinity level or score.</span></span> <span data-ttu-id="a3be0-129">Skóre afinity vám dáva presnejšiu kontrolu.</span><span class="sxs-lookup"><span data-stu-id="a3be0-129">Affinity score gives you more precise control.</span></span>

## <a name="supported-countriesregions"></a><span data-ttu-id="a3be0-130">Podporované krajiny/regióny</span><span class="sxs-lookup"><span data-stu-id="a3be0-130">Supported countries/regions</span></span>

<span data-ttu-id="a3be0-131">V súčasnosti podporujeme možnosti nasledujúcich krajín/regiónov: Austrália, Kanada (angličtina), Francúzsko, Nemecko, Spojené kráľovstvo alebo Spojené štáty (angličtina).</span><span class="sxs-lookup"><span data-stu-id="a3be0-131">We currently support the following country/region options: Australia, Canada (English), France, Germany, United Kingdom, or United States (English).</span></span>

<span data-ttu-id="a3be0-132">Ak chcete vybrať krajinu, otvorte **Obohatenie značiek** alebo **Obohatenie záujmov** a vyberte **Zmeniť** vedľa **Krajiny/regiónu**.</span><span class="sxs-lookup"><span data-stu-id="a3be0-132">To select a country, open the **Brands enrichment** or **Interest enrichment** and select **Change** next to **Country/Region**.</span></span> <span data-ttu-id="a3be0-133">Na table **Nastavenia krajiny/regiónu** vyberte možnosť a následne položku **Použiť**.</span><span class="sxs-lookup"><span data-stu-id="a3be0-133">In the **Country/Region settings** pane, choose an option and select **Apply**.</span></span>

### <a name="implications-related-to-country-selection"></a><span data-ttu-id="a3be0-134">Dôsledky týkajúce sa výberu krajiny</span><span class="sxs-lookup"><span data-stu-id="a3be0-134">Implications related to country selection</span></span>

- <span data-ttu-id="a3be0-135">Pri [výbere vlastných značiek](#define-your-brands-or-interests) systém poskytuje návrhy na základe vybranej krajiny alebo regiónu.</span><span class="sxs-lookup"><span data-stu-id="a3be0-135">When [choosing your own brands](#define-your-brands-or-interests), the system provides suggestions based on the selected country or region.</span></span>

- <span data-ttu-id="a3be0-136">Pri [výbere odvetvia](#define-your-brands-or-interests) získate najrelevantnejšie značky alebo záujmy na základe vybranej krajiny alebo regiónu.</span><span class="sxs-lookup"><span data-stu-id="a3be0-136">When [choosing an industry](#define-your-brands-or-interests), you'll get the most relevant brands or interests based on the selected country or region.</span></span>

- <span data-ttu-id="a3be0-137">Pri [obohacovaní profilov](#refresh-enrichment) obohatíme všetky profily zákazníkov, pre ktoré získame údaje o vybraných značkách a záujmoch.</span><span class="sxs-lookup"><span data-stu-id="a3be0-137">When [enriching profiles](#refresh-enrichment), we'll enrich all customer profiles for which we get data for the selected brands and interests.</span></span> <span data-ttu-id="a3be0-138">Zahrnutie profilov, ktoré sa nenachádzajú vo vybranej krajine alebo oblasti.</span><span class="sxs-lookup"><span data-stu-id="a3be0-138">Including profiles that are not in the selected country or region.</span></span> <span data-ttu-id="a3be0-139">Napríklad ak ste vybrali Nemecko, obohatíme profily nachádzajúce sa v USA, ak máme k dispozícii údaje o vybraných značkách a záujmoch v USA.</span><span class="sxs-lookup"><span data-stu-id="a3be0-139">For example, if you selected Germany, we'll enrich profiles located in the United States if we have data available for the selected brands and interests in the US.</span></span>

## <a name="configure-enrichment"></a><span data-ttu-id="a3be0-140">Konfigurácia obohatenia</span><span class="sxs-lookup"><span data-stu-id="a3be0-140">Configure Enrichment</span></span>

<span data-ttu-id="a3be0-141">Prehliadka so sprievodcom vám pomôže pri konfigurácii obohatení.</span><span class="sxs-lookup"><span data-stu-id="a3be0-141">A guided experience helps you through the configuration of the enrichments.</span></span> 

### <a name="define-your-brands-or-interests"></a><span data-ttu-id="a3be0-142">Definujte svoje značky alebo záujmy</span><span class="sxs-lookup"><span data-stu-id="a3be0-142">Define your brands or interests</span></span>

<span data-ttu-id="a3be0-143">Vyberte si až päť značiek alebo záujmov pomocou jednej alebo oboch z týchto možností:</span><span class="sxs-lookup"><span data-stu-id="a3be0-143">Choose up to five brands or interests using one or both of these options:</span></span>

- <span data-ttu-id="a3be0-144">**Priemysel**: Z rozbaľovacieho zoznamu vyberte svoje odvetvie a potom vyberte z top značiek alebo záujmov pre dané odvetvie.</span><span class="sxs-lookup"><span data-stu-id="a3be0-144">**Industry**: Select your industry from the drop-down list and then choose from the top brands or interests for that industry.</span></span>
- <span data-ttu-id="a3be0-145">**Vyberte svoje vlastné**: Zadajte značku alebo záujem, ktorý je relevantný pre vašu organizáciu, a potom si vyberte zodpovedajúce návrhy.</span><span class="sxs-lookup"><span data-stu-id="a3be0-145">**Choose your own**: Enter a brand or interest that is relevant to your organization and then choose from the matching suggestions.</span></span> <span data-ttu-id="a3be0-146">Ak neuvedieme hľadanú značku alebo záujem, pošlite nám svoje pripomienky pomocou odkazu **Navrhnúť**.</span><span class="sxs-lookup"><span data-stu-id="a3be0-146">If we don't list a brand or interest you're looking for, send us feedback using the **Suggest** link.</span></span>

### <a name="review-enrichment-preferences"></a><span data-ttu-id="a3be0-147">Kontrola predvolieb obohacovania</span><span class="sxs-lookup"><span data-stu-id="a3be0-147">Review enrichment preferences</span></span>

<span data-ttu-id="a3be0-148">Skontrolujte svoje predvolené predvoľby obohatenia a podľa potreby ich aktualizujte.</span><span class="sxs-lookup"><span data-stu-id="a3be0-148">Review your default enrichment preferences and update them as needed.</span></span>

:::image type="content" source="media/affinity-enrichment-preferences.png" alt-text="Snímka obrazovky okna s predvoľbami obohacovania.":::

### <a name="select-entity-to-enrich"></a><span data-ttu-id="a3be0-150">Vyberte entitu na obohatenie</span><span class="sxs-lookup"><span data-stu-id="a3be0-150">Select entity to enrich</span></span>

<span data-ttu-id="a3be0-151">Stlačte možnosť **Obohatená entita** a vyberte množinu údajov, ktorú chcete obohatiť o údaje spoločnosti od spoločnosti Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a3be0-151">Select **Enriched entity** and choose the data set you want to enrich with company data from the Microsoft.</span></span> <span data-ttu-id="a3be0-152">Môžete zvoliť entitu Zákazník, aby ste obohatili všetky svoje zákaznícke profily, alebo vyberte entitu segmentu, aby ste obohatili iba profily zákazníkov obsiahnuté v danom segmente.</span><span class="sxs-lookup"><span data-stu-id="a3be0-152">You can select the Customer entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

### <a name="map-your-fields"></a><span data-ttu-id="a3be0-153">Priraďte svoje polia</span><span class="sxs-lookup"><span data-stu-id="a3be0-153">Map your fields</span></span>

<span data-ttu-id="a3be0-154">Mapujte polia z vašej zjednotenej entity zákazníka a definujte demografický segment, ktorý má systém používať na obohatenie vašich údajov o zákazníkoch.</span><span class="sxs-lookup"><span data-stu-id="a3be0-154">Map fields from your unified customer entity to define the demographic segment you want the system to use for enriching your customer data.</span></span> <span data-ttu-id="a3be0-155">Mapujte krajinu/región a minimálne atribúty Dátum narodenia alebo Pohlavie.</span><span class="sxs-lookup"><span data-stu-id="a3be0-155">Map Country/Region and at least Date of Birth or Gender attributes.</span></span> <span data-ttu-id="a3be0-156">Okrem toho musíte namapovať aspoň jedno mesto (a štát/kraj) alebo PSČ.</span><span class="sxs-lookup"><span data-stu-id="a3be0-156">Additionally, you must map at least one of City (and State/Province) or Postal code.</span></span> <span data-ttu-id="a3be0-157">Zvoľte možnosť **Upraviť** na definovanie mapovania polí a keď to dokončíte, stlačte možnosť **Použiť**.</span><span class="sxs-lookup"><span data-stu-id="a3be0-157">Select **Edit** to define the mapping of the fields and select **Apply** when you're done.</span></span> <span data-ttu-id="a3be0-158">Vyberte **Uložiť** na dokončenie mapovania polí.</span><span class="sxs-lookup"><span data-stu-id="a3be0-158">Select **Save** to complete the field mapping.</span></span>

<span data-ttu-id="a3be0-159">Podporované sú nasledujúce formáty a hodnoty, hodnoty nerozlišujú veľké a malé písmená:</span><span class="sxs-lookup"><span data-stu-id="a3be0-159">The following formats and values are supported, values are not case-sensitive:</span></span>

- <span data-ttu-id="a3be0-160">**Dátum narodenia**: Počas prijímania údajov vám odporúčame previesť dátum narodenia na typ DateTime.</span><span class="sxs-lookup"><span data-stu-id="a3be0-160">**Date of Birth**: We recommend that date of birth is converted to DateTime type during data ingestion.</span></span> <span data-ttu-id="a3be0-161">Alternatívne to môže byť reťazec vo formáte [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) „rrrr-MM-dd“ alebo „rrrr-MM-ddTHH: mm: ssZ“.</span><span class="sxs-lookup"><span data-stu-id="a3be0-161">Alternatively, it can be a string in [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) format "yyyy-MM-dd" or "yyyy-MM-ddTHH:mm:ssZ".</span></span>
- <span data-ttu-id="a3be0-162">**Pohlavie**: muž, žena, neznáme</span><span class="sxs-lookup"><span data-stu-id="a3be0-162">**Gender**: Male, Female, Unknown</span></span>
- <span data-ttu-id="a3be0-163">**Poštové smerovacie číslo**: Päťmiestne PSČ pre USA, štandardné poštové smerovacie číslo všade inde</span><span class="sxs-lookup"><span data-stu-id="a3be0-163">**Postal code**: Five-digit ZIP Codes for US, standard postal code everywhere else</span></span>
- <span data-ttu-id="a3be0-164">**Mesto**: Názov mesta v angličtine</span><span class="sxs-lookup"><span data-stu-id="a3be0-164">**City**: City name in English</span></span>
- <span data-ttu-id="a3be0-165">**Štát/provincia**: Dvojpísmenová skratka pre USA a Kanadu.</span><span class="sxs-lookup"><span data-stu-id="a3be0-165">**State/Province**: Two-letter abbreviation for the US and Canada.</span></span> <span data-ttu-id="a3be0-166">Dvoj- alebo trojpísmenná skratka pre Austráliu.</span><span class="sxs-lookup"><span data-stu-id="a3be0-166">Two or three letter abbreviation for Australia.</span></span> <span data-ttu-id="a3be0-167">Nevzťahuje sa na Francúzsko, Nemecko ani Spojené kráľovstvo.</span><span class="sxs-lookup"><span data-stu-id="a3be0-167">Not applicable for France, Germany, or the UK.</span></span>
- <span data-ttu-id="a3be0-168">**Krajina/oblasť**:</span><span class="sxs-lookup"><span data-stu-id="a3be0-168">**Country/Region**:</span></span>

  - <span data-ttu-id="a3be0-169">USA: Spojené štáty americké, Spojené štáty, USA, US, Amerika</span><span class="sxs-lookup"><span data-stu-id="a3be0-169">US: United States of America, United States, USA, US, America</span></span>
  - <span data-ttu-id="a3be0-170">CA: Kanada, CA</span><span class="sxs-lookup"><span data-stu-id="a3be0-170">CA: Canada, CA</span></span>
  - <span data-ttu-id="a3be0-171">GB: Spojené kráľovstvo, UK, Veľká Británia, GB, Spojené kráľovstvo Veľkej Británie a Severného Írska, Spojené kráľovstvo Veľkej Británie</span><span class="sxs-lookup"><span data-stu-id="a3be0-171">GB: United Kingdom, UK, Great Britain, GB, United Kingdom of Great Britain and Northern Ireland, United Kingdom of Great Britain</span></span>
  - <span data-ttu-id="a3be0-172">AU: Austrália, AU, Austrálske spoločenstvo</span><span class="sxs-lookup"><span data-stu-id="a3be0-172">AU: Australia, AU, Common Wealth of Australia</span></span>
  - <span data-ttu-id="a3be0-173">FR: Francúzsko, FR, Francúzska republika</span><span class="sxs-lookup"><span data-stu-id="a3be0-173">FR: France, FR, French Republic</span></span>
  - <span data-ttu-id="a3be0-174">DE: Nemecko, Deutschland, Allemagne, DE, Spolková republika Nemecko, Nemecká republika</span><span class="sxs-lookup"><span data-stu-id="a3be0-174">DE: Germany, German, Deutschland, Allemagne, DE, Federal Republic of Germany, Republic of Germany</span></span>

## <a name="review-and-name-the-enrichment"></a><span data-ttu-id="a3be0-175">Skontrolujte a pomenujte obohatenie</span><span class="sxs-lookup"><span data-stu-id="a3be0-175">Review and name the enrichment</span></span>

<span data-ttu-id="a3be0-176">Nakoniec si prečítate informácie a uvediete názov obohatenia.</span><span class="sxs-lookup"><span data-stu-id="a3be0-176">Finally, you get to review the information and provide a name for the enrichment.</span></span>

:::image type="content" source="media/enrichment-interests-summary.png" alt-text="Stránka kontroly záujmov a pomenovania.":::

## <a name="refresh-enrichment"></a><span data-ttu-id="a3be0-178">Obnovenie obohatenia</span><span class="sxs-lookup"><span data-stu-id="a3be0-178">Refresh enrichment</span></span>

<span data-ttu-id="a3be0-179">Spustite obohatenie po nakonfigurovaní značiek, záujmov a mapovania terénu pre demografické údaje.</span><span class="sxs-lookup"><span data-stu-id="a3be0-179">Run the enrichment after configuring brands, interests, and the field mapping for demographics.</span></span> <span data-ttu-id="a3be0-180">Ak chcete proces spustiť, vyberte položku **Spustiť** na stránke konfigurácie značky alebo záujmu.</span><span class="sxs-lookup"><span data-stu-id="a3be0-180">To start the process, select **Run** on the brand or interest configuration page.</span></span> <span data-ttu-id="a3be0-181">Okrem toho môžete nechať systém, aby obohatenie spustil automaticky ako súčasť plánovanej obnovy.</span><span class="sxs-lookup"><span data-stu-id="a3be0-181">Additionally, you can let the system run the enrichment automatically as part of a scheduled refresh.</span></span>
<span data-ttu-id="a3be0-182">V závislosti od veľkosti vašich zákazníckych údajov môže dokončenie procesu obohatenia trvať niekoľko minút.</span><span class="sxs-lookup"><span data-stu-id="a3be0-182">Depending on the size of your customer data, it may take several minutes for an enrichment run to complete.</span></span>

> [!TIP]
> <span data-ttu-id="a3be0-183">Existuje [šesť druhov stavov](system.md#status-types) pre úlohy/procesy.</span><span class="sxs-lookup"><span data-stu-id="a3be0-183">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="a3be0-184">Okrem toho väčšina procesov [závisí na ďalších nadväzujúcich procesoch](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="a3be0-184">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="a3be0-185">Môžete si vybrať stav procesu a zobraziť podrobnosti o priebehu celej úlohy.</span><span class="sxs-lookup"><span data-stu-id="a3be0-185">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="a3be0-186">Po výbere **Pozrieť detaily** pre jednu z úloh úlohy nájdete ďalšie informácie: čas spracovania, posledný dátum spracovania a všetky chyby a varovania spojené s úlohou.</span><span class="sxs-lookup"><span data-stu-id="a3be0-186">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="a3be0-187">Výsledky obohatenia</span><span class="sxs-lookup"><span data-stu-id="a3be0-187">Enrichment results</span></span>

<span data-ttu-id="a3be0-188">Po dokončení procesu obohacovania prejdite na **Moje obohatenia** a skontrolujte celkový počet obohatených zákazníkov a prehľad značiek a záujmov v obohatených profiloch zákazníkov.</span><span class="sxs-lookup"><span data-stu-id="a3be0-188">After running the enrichment process, go to **My enrichments** to review the total number of enriched customers and a breakdown of brands or interests in the enriched customer profiles.</span></span>

:::image type="content" source="media/my-enrichments.png" alt-text="Ukážka výsledkov po spustení procesu obohacovania":::

<span data-ttu-id="a3be0-190">Vyberte obohatené údaje výberom **Zobraziť obohatené údaje** v tabuľke.</span><span class="sxs-lookup"><span data-stu-id="a3be0-190">Review the enriched data by selecting **View enriched data** in the chart.</span></span> <span data-ttu-id="a3be0-191">Obohatené údaje o značkách prejdú do entity **BrandAffinityFromMicrosoft**.</span><span class="sxs-lookup"><span data-stu-id="a3be0-191">Enriched data for brands goes to the **BrandAffinityFromMicrosoft** entity.</span></span> <span data-ttu-id="a3be0-192">Údaje o záujmoch sú v entite **InterestAffinityFromMicrosoft**.</span><span class="sxs-lookup"><span data-stu-id="a3be0-192">Data for interests is in the **InterestAffinityFromMicrosoft** entity.</span></span> <span data-ttu-id="a3be0-193">Tieto entity nájdete uvedené aj v skupine **Obohatenie** v časti **Údaje** > **Entity**.</span><span class="sxs-lookup"><span data-stu-id="a3be0-193">You'll also find these entities listed in the **Enrichment** group in **Data** > **Entities**.</span></span>

## <a name="see-enrichment-data-on-the-customer-card"></a><span data-ttu-id="a3be0-194">Pozrite si údaje o obohatení na karte zákazníka</span><span class="sxs-lookup"><span data-stu-id="a3be0-194">See enrichment data on the customer card</span></span>

<span data-ttu-id="a3be0-195">Značky a záujmy môžu byť zobrazené aj na jednotlivých zákazníckych kartách.</span><span class="sxs-lookup"><span data-stu-id="a3be0-195">Brand and interest affinities can also be viewed on individual customer cards.</span></span> <span data-ttu-id="a3be0-196">Prejdite na možnosť **Zákazníci** a zvoľte si profil zákazníka.</span><span class="sxs-lookup"><span data-stu-id="a3be0-196">Go to **Customers** and select a customer profile.</span></span> <span data-ttu-id="a3be0-197">Na zákazníckej karte nájdete grafy značiek alebo záujmov, ku ktorým majú ľudia v demografickom profile daného zákazníka afinitu.</span><span class="sxs-lookup"><span data-stu-id="a3be0-197">In the customer card, you'll find charts for the brands or interests that people in that customer's demographic profile have affinity for.</span></span>

:::image type="content" source="media/enrichment-customer-card.png" alt-text="Karta zákazníka s obohatenými údajmi":::

## <a name="next-steps"></a><span data-ttu-id="a3be0-199">Ďalšie kroky</span><span class="sxs-lookup"><span data-stu-id="a3be0-199">Next steps</span></span>

<span data-ttu-id="a3be0-200">Stavajte na svojich obohatených údajoch o zákazníkoch.</span><span class="sxs-lookup"><span data-stu-id="a3be0-200">Build on top of your enriched customer data.</span></span> <span data-ttu-id="a3be0-201">Vytvárajte [segmenty](segments.md), [merania](measures.md) a dokonca [exportujte údaje](export-destinations.md) na poskytovanie prispôsobenej používateľskej skúsenosti svojim zákazníkom.</span><span class="sxs-lookup"><span data-stu-id="a3be0-201">Create [Segments](segments.md), [Measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
