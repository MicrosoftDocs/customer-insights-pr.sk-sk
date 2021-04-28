---
title: Obohaťte profily zákazníkov o údaje od spoločnosti Microsoft
description: Na obohatenie svojich zákazníckych údajov o záujmy značiek a záujmov použite patentované údaje spoločnosti Microsoft.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 6f19033236190547f68d2b91ec6b32074bf7912a
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896621"
---
# <a name="enrich-customer-profiles-with-brand-and-interest-affinities-preview"></a><span data-ttu-id="80c6a-103">Obohaťte profily zákazníkov o značky a záujmy (ukážka)</span><span class="sxs-lookup"><span data-stu-id="80c6a-103">Enrich customer profiles with brand and interest affinities (preview)</span></span>

<span data-ttu-id="80c6a-104">Na obohatenie svojich zákazníckych údajov o záujmy značiek a záujmov použite patentované údaje spoločnosti Microsoft.</span><span class="sxs-lookup"><span data-stu-id="80c6a-104">Use Microsoft's proprietary data to enrich your customer data with brand and interest affinities.</span></span> <span data-ttu-id="80c6a-105">Tieto afinity sa určujú na základe údajov od ľudí s podobnou demografiou ako vaši zákazníci.</span><span class="sxs-lookup"><span data-stu-id="80c6a-105">These affinities are determined based on data from people with similar demographics to your customers.</span></span> <span data-ttu-id="80c6a-106">Tieto informácie vám pomôžu lepšie porozumieť a segmentovať vašich zákazníkov na základe ich príslušnosti k určitým značkám a záujmom.</span><span class="sxs-lookup"><span data-stu-id="80c6a-106">This information helps you to better understand and segment your customers based on their affinities to specific brands and interests.</span></span>

<span data-ttu-id="80c6a-107">V prehľadoch cieľových skupín prejdite na **Údaje** > **Obohatenie** na [konfiguráciu a zobrazenie obohatení](enrichment-hub.md).</span><span class="sxs-lookup"><span data-stu-id="80c6a-107">In audience insights, go to **Data** > **Enrichment** to [configure and view enrichments](enrichment-hub.md).</span></span>

<span data-ttu-id="80c6a-108">Ak chcete nakonfigurovať obohatenie o afinity značiek, prejdite na stránku **Objavovať** a vyberte **Obohatiť moje údaje** na dlaždici **Značky**.</span><span class="sxs-lookup"><span data-stu-id="80c6a-108">To configure brand affinities enrichment, go to the **Discover** tab and select **Enrich my data** on the **Brands** tile.</span></span>

<span data-ttu-id="80c6a-109">Ak chcete nakonfigurovať obohatenie o afinity záujmov, prejdite na stránku **Objavovať** a vyberte **Obohatiť moje údaje** na dlaždici **Záujmy**.</span><span class="sxs-lookup"><span data-stu-id="80c6a-109">To configure interest affinities enrichment, go to the **Discover** tab and select **Enrich my data** on the **Interests** tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="80c6a-110">![Dlaždice Značky a záujmy](media/BrandsInterest-tile-Hub.png "Dlaždice Značky a záujmy")</span><span class="sxs-lookup"><span data-stu-id="80c6a-110">![Brands & Interests tiles](media/BrandsInterest-tile-Hub.png "Brands & Interest tiles")</span></span>

## <a name="how-we-determine-affinities"></a><span data-ttu-id="80c6a-111">Ako určujeme príbuznosti</span><span class="sxs-lookup"><span data-stu-id="80c6a-111">How we determine affinities</span></span>

<span data-ttu-id="80c6a-112">Údaje o vyhľadávaní online spoločnosti Microsoft používame na to, aby sme zistili príbuznosť značiek a záujmov v rôznych demografických segmentoch (definované podľa veku, pohlavia alebo umiestnenia).</span><span class="sxs-lookup"><span data-stu-id="80c6a-112">We use Microsoft’s online search data to find affinities for brands and interests across various demographic segments (defined by age, gender, or location).</span></span> <span data-ttu-id="80c6a-113">Objem online vyhľadávania pre určitú značku alebo záujem určuje, akú príbuznosť má demografický segment v porovnaní s inými segmentmi k tejto značke alebo záujmu.</span><span class="sxs-lookup"><span data-stu-id="80c6a-113">The online search volume for a brand or interest determines how much affinity a demographic segment, compared to other segments, has to that brand or interest.</span></span> <span data-ttu-id="80c6a-114">značka alebo záujem.</span><span class="sxs-lookup"><span data-stu-id="80c6a-114">brand or interest.</span></span>

## <a name="affinity-level-and-score"></a><span data-ttu-id="80c6a-115">Úroveň afinity a skóre</span><span class="sxs-lookup"><span data-stu-id="80c6a-115">Affinity level and score</span></span>

<span data-ttu-id="80c6a-116">V každom obohatenom profile zákazníka poskytujeme dve súvisiace hodnoty – úroveň afinity a skóre afinity.</span><span class="sxs-lookup"><span data-stu-id="80c6a-116">On every enriched customer profile, we provide two related values – affinity level and affinity score.</span></span> <span data-ttu-id="80c6a-117">Tieto hodnoty vám pomôžu určiť, aká silná je afinita k demografickému segmentu daného profilu, k značke alebo záujmu v porovnaní s ostatnými demografickými segmentmi.</span><span class="sxs-lookup"><span data-stu-id="80c6a-117">These values help you determine how strong the affinity is for that profile’s demographic segment, for a brand or interest, as compared to other demographic segments.</span></span>

<span data-ttu-id="80c6a-118">*Úroveň afinity* pozostáva zo štyroch úrovní a *skóre afinity* sa počíta na 100-bodovej stupnici, ktorá sa mapuje na úrovne afinity.</span><span class="sxs-lookup"><span data-stu-id="80c6a-118">*Affinity level* consists of four levels and *affinity score* is calculated on a 100-point scale that maps to the affinity levels.</span></span>


|<span data-ttu-id="80c6a-119">Úroveň afinity</span><span class="sxs-lookup"><span data-stu-id="80c6a-119">Affinity level</span></span> |<span data-ttu-id="80c6a-120">Skóre afinity</span><span class="sxs-lookup"><span data-stu-id="80c6a-120">Affinity score</span></span>  |
|---------|---------|
|<span data-ttu-id="80c6a-121">Veľmi vysoká</span><span class="sxs-lookup"><span data-stu-id="80c6a-121">Very high</span></span>     | <span data-ttu-id="80c6a-122">85 – 100</span><span class="sxs-lookup"><span data-stu-id="80c6a-122">85-100</span></span>       |
|<span data-ttu-id="80c6a-123">Vysoký</span><span class="sxs-lookup"><span data-stu-id="80c6a-123">High</span></span>     | <span data-ttu-id="80c6a-124">70 – 84</span><span class="sxs-lookup"><span data-stu-id="80c6a-124">70-84</span></span>        |
|<span data-ttu-id="80c6a-125">Stredný</span><span class="sxs-lookup"><span data-stu-id="80c6a-125">Medium</span></span>     | <span data-ttu-id="80c6a-126">35 – 69</span><span class="sxs-lookup"><span data-stu-id="80c6a-126">35-69</span></span>        |
|<span data-ttu-id="80c6a-127">Nízky</span><span class="sxs-lookup"><span data-stu-id="80c6a-127">Low</span></span>     | <span data-ttu-id="80c6a-128">1 – 34</span><span class="sxs-lookup"><span data-stu-id="80c6a-128">1-34</span></span>        |

<span data-ttu-id="80c6a-129">V závislosti od podrobností, ktoré chcete pri meraní afinity, môžete použiť buď úroveň afinity alebo skóre.</span><span class="sxs-lookup"><span data-stu-id="80c6a-129">Depending on the granularity you would like for measuring the affinity, you can use either affinity level or score.</span></span> <span data-ttu-id="80c6a-130">Skóre afinity vám dáva presnejšiu kontrolu.</span><span class="sxs-lookup"><span data-stu-id="80c6a-130">Affinity score gives you more precise control.</span></span>

## <a name="supported-countriesregions"></a><span data-ttu-id="80c6a-131">Podporované krajiny/regióny</span><span class="sxs-lookup"><span data-stu-id="80c6a-131">Supported countries/regions</span></span>

<span data-ttu-id="80c6a-132">V súčasnosti podporujeme možnosti nasledujúcich krajín/regiónov: Austrália, Kanada (angličtina), Francúzsko, Nemecko, Spojené kráľovstvo alebo Spojené štáty (angličtina).</span><span class="sxs-lookup"><span data-stu-id="80c6a-132">We currently support the following country/region options: Australia, Canada (English), France, Germany, United Kingdom, or United States (English).</span></span>

<span data-ttu-id="80c6a-133">Ak chcete vybrať krajinu, otvorte **Obohatenie značiek** alebo **Obohatenie záujmov** a vyberte **Zmeniť** vedľa **Krajiny/regiónu**.</span><span class="sxs-lookup"><span data-stu-id="80c6a-133">To select a country, open the **Brands enrichment** or **Interest enrichment** and select **Change** next to **Country/Region**.</span></span> <span data-ttu-id="80c6a-134">Na table **Nastavenia krajiny/regiónu** vyberte možnosť a následne položku **Použiť**.</span><span class="sxs-lookup"><span data-stu-id="80c6a-134">In the **Country/Region settings** pane, choose an option and select **Apply**.</span></span>

### <a name="implications-related-to-country-selection"></a><span data-ttu-id="80c6a-135">Dôsledky týkajúce sa výberu krajiny</span><span class="sxs-lookup"><span data-stu-id="80c6a-135">Implications related to country selection</span></span>

- <span data-ttu-id="80c6a-136">Pri [výbere vlastných značiek](#define-your-brands-or-interests) systém poskytuje návrhy na základe vybranej krajiny alebo regiónu.</span><span class="sxs-lookup"><span data-stu-id="80c6a-136">When [choosing your own brands](#define-your-brands-or-interests), the system provides suggestions based on the selected country or region.</span></span>

- <span data-ttu-id="80c6a-137">Pri [výbere odvetvia](#define-your-brands-or-interests) získate najrelevantnejšie značky alebo záujmy na základe vybranej krajiny alebo regiónu.</span><span class="sxs-lookup"><span data-stu-id="80c6a-137">When [choosing an industry](#define-your-brands-or-interests), you'll get the most relevant brands or interests based on the selected country or region.</span></span>

- <span data-ttu-id="80c6a-138">Pri [obohacovaní profilov](#refresh-enrichment) obohatíme všetky profily zákazníkov, pre ktoré získame údaje o vybraných značkách a záujmoch.</span><span class="sxs-lookup"><span data-stu-id="80c6a-138">When [enriching profiles](#refresh-enrichment), we'll enrich all customer profiles for which we get data for the selected brands and interests.</span></span> <span data-ttu-id="80c6a-139">Zahrnutie profilov, ktoré sa nenachádzajú vo vybranej krajine alebo oblasti.</span><span class="sxs-lookup"><span data-stu-id="80c6a-139">Including profiles that are not in the selected country or region.</span></span> <span data-ttu-id="80c6a-140">Napríklad ak ste vybrali Nemecko, obohatíme profily nachádzajúce sa v USA, ak máme k dispozícii údaje o vybraných značkách a záujmoch v USA.</span><span class="sxs-lookup"><span data-stu-id="80c6a-140">For example, if you selected Germany, we'll enrich profiles located in the United States if we have data available for the selected brands and interests in the US.</span></span>

## <a name="configure-enrichment"></a><span data-ttu-id="80c6a-141">Konfigurácia obohatenia</span><span class="sxs-lookup"><span data-stu-id="80c6a-141">Configure Enrichment</span></span>

<span data-ttu-id="80c6a-142">Prehliadka so sprievodcom vám pomôže pri konfigurácii obohatení.</span><span class="sxs-lookup"><span data-stu-id="80c6a-142">A guided experience helps you through the configuration of the enrichments.</span></span> 

### <a name="define-your-brands-or-interests"></a><span data-ttu-id="80c6a-143">Definujte svoje značky alebo záujmy</span><span class="sxs-lookup"><span data-stu-id="80c6a-143">Define your brands or interests</span></span>

<span data-ttu-id="80c6a-144">Vyberte jednu z nasledujúcich možností:</span><span class="sxs-lookup"><span data-stu-id="80c6a-144">Select one of the following options:</span></span>

- <span data-ttu-id="80c6a-145">**Odvetvie**: Systém identifikuje top značky alebo záujmy relevantné pre vaše odvetvie a obohacuje o nich vaše zákaznícke údaje.</span><span class="sxs-lookup"><span data-stu-id="80c6a-145">**Industry**: The system identifies the top brands or interests relevant to your industry and enriches your customer data with them.</span></span>
- <span data-ttu-id="80c6a-146">**Vyberte svoje vlastné**: Vyberte až päť položiek zo zoznamu značiek alebo záujmov, ktoré sú pre vašu organizáciu najrelevantnejšie.</span><span class="sxs-lookup"><span data-stu-id="80c6a-146">**Choose your own**: Select up to five items from the list of brands or interests that are most relevant to your organization.</span></span>

<span data-ttu-id="80c6a-147">Ak chcete pridať značku alebo záujem, zadajte ich do vstupnej oblasti a získajte návrhy na základe zhodných výrazov.</span><span class="sxs-lookup"><span data-stu-id="80c6a-147">To add a brand or interest, enter it in the input area to get suggestions based on matching terms.</span></span> <span data-ttu-id="80c6a-148">Ak neuvedieme hľadanú značku alebo záujem, pošlite nám svoje pripomienky pomocou odkazu **Navrhnúť**.</span><span class="sxs-lookup"><span data-stu-id="80c6a-148">If we don't list a brand or interest you're looking for, send us feedback using the **Suggest** link.</span></span>

### <a name="review-enrichment-preferences"></a><span data-ttu-id="80c6a-149">Kontrola predvolieb obohacovania</span><span class="sxs-lookup"><span data-stu-id="80c6a-149">Review enrichment preferences</span></span>

<span data-ttu-id="80c6a-150">Skontrolujte svoje predvolené predvoľby obohatenia a podľa potreby ich aktualizujte.</span><span class="sxs-lookup"><span data-stu-id="80c6a-150">Review your default enrichment preferences and update them as needed.</span></span>

:::image type="content" source="media/affinity-enrichment-preferences.png" alt-text="Snímka obrazovky okna s predvoľbami obohacovania.":::

### <a name="select-entity-to-enrich"></a><span data-ttu-id="80c6a-152">Vyberte entitu na obohatenie</span><span class="sxs-lookup"><span data-stu-id="80c6a-152">Select entity to enrich</span></span>

<span data-ttu-id="80c6a-153">Stlačte možnosť **Obohatená entita** a vyberte množinu údajov, ktorú chcete obohatiť o údaje spoločnosti od spoločnosti Microsoft.</span><span class="sxs-lookup"><span data-stu-id="80c6a-153">Select **Enriched entity** and choose the data set you want to enrich with company data from the Microsoft.</span></span> <span data-ttu-id="80c6a-154">Môžete zvoliť entitu Zákazník, aby ste obohatili všetky svoje zákaznícke profily, alebo vyberte entitu segmentu, aby ste obohatili iba profily zákazníkov obsiahnuté v danom segmente.</span><span class="sxs-lookup"><span data-stu-id="80c6a-154">You can select the Customer entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

### <a name="map-your-fields"></a><span data-ttu-id="80c6a-155">Priraďte svoje polia</span><span class="sxs-lookup"><span data-stu-id="80c6a-155">Map your fields</span></span>

<span data-ttu-id="80c6a-156">Mapujte polia z vašej zjednotenej entity zákazníka a definujte demografický segment, ktorý má systém používať na obohatenie vašich údajov o zákazníkoch.</span><span class="sxs-lookup"><span data-stu-id="80c6a-156">Map fields from your unified customer entity to define the demographic segment you want the system to use for enriching your customer data.</span></span> <span data-ttu-id="80c6a-157">Mapujte krajinu/región a minimálne atribúty Dátum narodenia alebo Pohlavie.</span><span class="sxs-lookup"><span data-stu-id="80c6a-157">Map Country/Region and at least Date of Birth or Gender attributes.</span></span> <span data-ttu-id="80c6a-158">Okrem toho musíte namapovať aspoň jedno mesto (a štát/kraj) alebo PSČ.</span><span class="sxs-lookup"><span data-stu-id="80c6a-158">Additionally, you must map at least one of City (and State/Province) or Postal code.</span></span> <span data-ttu-id="80c6a-159">Zvoľte možnosť **Upraviť** na definovanie mapovania polí a keď to dokončíte, stlačte možnosť **Použiť**.</span><span class="sxs-lookup"><span data-stu-id="80c6a-159">Select **Edit** to define the mapping of the fields and select **Apply** when you're done.</span></span> <span data-ttu-id="80c6a-160">Vyberte **Uložiť** na dokončenie mapovania polí.</span><span class="sxs-lookup"><span data-stu-id="80c6a-160">Select **Save** to complete the field mapping.</span></span>

<span data-ttu-id="80c6a-161">Podporované sú nasledujúce formáty a hodnoty, hodnoty nerozlišujú veľké a malé písmená:</span><span class="sxs-lookup"><span data-stu-id="80c6a-161">The following formats and values are supported, values are not case-sensitive:</span></span>

- <span data-ttu-id="80c6a-162">**Dátum narodenia**: Počas prijímania údajov vám odporúčame previesť dátum narodenia na typ DateTime.</span><span class="sxs-lookup"><span data-stu-id="80c6a-162">**Date of Birth**: We recommend that date of birth is converted to DateTime type during data ingestion.</span></span> <span data-ttu-id="80c6a-163">Alternatívne to môže byť reťazec vo formáte [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) „rrrr-MM-dd“ alebo „rrrr-MM-ddTHH: mm: ssZ“.</span><span class="sxs-lookup"><span data-stu-id="80c6a-163">Alternatively, it can be a string in [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) format "yyyy-MM-dd" or "yyyy-MM-ddTHH:mm:ssZ".</span></span>
- <span data-ttu-id="80c6a-164">**Pohlavie**: muž, žena, neznáme</span><span class="sxs-lookup"><span data-stu-id="80c6a-164">**Gender**: Male, Female, Unknown</span></span>
- <span data-ttu-id="80c6a-165">**Poštové smerovacie číslo**: Päťmiestne PSČ pre USA, štandardné poštové smerovacie číslo všade inde</span><span class="sxs-lookup"><span data-stu-id="80c6a-165">**Postal code**: Five-digit ZIP Codes for US, standard postal code everywhere else</span></span>
- <span data-ttu-id="80c6a-166">**Mesto**: Názov mesta v angličtine</span><span class="sxs-lookup"><span data-stu-id="80c6a-166">**City**: City name in English</span></span>
- <span data-ttu-id="80c6a-167">**Štát/provincia**: Dvojpísmenová skratka pre USA a Kanadu.</span><span class="sxs-lookup"><span data-stu-id="80c6a-167">**State/Province**: Two-letter abbreviation for the US and Canada.</span></span> <span data-ttu-id="80c6a-168">Dvoj- alebo trojpísmenná skratka pre Austráliu.</span><span class="sxs-lookup"><span data-stu-id="80c6a-168">Two or three letter abbreviation for Australia.</span></span> <span data-ttu-id="80c6a-169">Nevzťahuje sa na Francúzsko, Nemecko ani Spojené kráľovstvo.</span><span class="sxs-lookup"><span data-stu-id="80c6a-169">Not applicable for France, Germany, or the UK.</span></span>
- <span data-ttu-id="80c6a-170">**Krajina/oblasť**:</span><span class="sxs-lookup"><span data-stu-id="80c6a-170">**Country/Region**:</span></span>

  - <span data-ttu-id="80c6a-171">USA: Spojené štáty americké, Spojené štáty, USA, US, Amerika</span><span class="sxs-lookup"><span data-stu-id="80c6a-171">US: United States of America, United States, USA, US, America</span></span>
  - <span data-ttu-id="80c6a-172">CA: Kanada, CA</span><span class="sxs-lookup"><span data-stu-id="80c6a-172">CA: Canada, CA</span></span>
  - <span data-ttu-id="80c6a-173">GB: Spojené kráľovstvo, UK, Veľká Británia, GB, Spojené kráľovstvo Veľkej Británie a Severného Írska, Spojené kráľovstvo Veľkej Británie</span><span class="sxs-lookup"><span data-stu-id="80c6a-173">GB: United Kingdom, UK, Great Britain, GB, United Kingdom of Great Britain and Northern Ireland, United Kingdom of Great Britain</span></span>
  - <span data-ttu-id="80c6a-174">AU: Austrália, AU, Austrálske spoločenstvo</span><span class="sxs-lookup"><span data-stu-id="80c6a-174">AU: Australia, AU, Common Wealth of Australia</span></span>
  - <span data-ttu-id="80c6a-175">FR: Francúzsko, FR, Francúzska republika</span><span class="sxs-lookup"><span data-stu-id="80c6a-175">FR: France, FR, French Republic</span></span>
  - <span data-ttu-id="80c6a-176">DE: Nemecko, Deutschland, Allemagne, DE, Spolková republika Nemecko, Nemecká republika</span><span class="sxs-lookup"><span data-stu-id="80c6a-176">DE: Germany, German, Deutschland, Allemagne, DE, Federal Republic of Germany, Republic of Germany</span></span>

## <a name="review-and-name-the-enrichment"></a><span data-ttu-id="80c6a-177">Skontrolujte a pomenujte obohatenie</span><span class="sxs-lookup"><span data-stu-id="80c6a-177">Review and name the enrichment</span></span>

<span data-ttu-id="80c6a-178">Nakoniec si prečítate informácie a uvediete názov obohatenia.</span><span class="sxs-lookup"><span data-stu-id="80c6a-178">Finally, you get to review the information and provide a name for the enrichment.</span></span>

:::image type="content" source="media/enrichment-interests-summary.png" alt-text="Stránka kontroly záujmov a pomenovania.":::

## <a name="refresh-enrichment"></a><span data-ttu-id="80c6a-180">Obnovenie obohatenia</span><span class="sxs-lookup"><span data-stu-id="80c6a-180">Refresh enrichment</span></span>

<span data-ttu-id="80c6a-181">Spustite obohatenie po nakonfigurovaní značiek, záujmov a mapovania terénu pre demografické údaje.</span><span class="sxs-lookup"><span data-stu-id="80c6a-181">Run the enrichment after configuring brands, interests, and the field mapping for demographics.</span></span> <span data-ttu-id="80c6a-182">Ak chcete proces spustiť, vyberte položku **Spustiť** na stránke konfigurácie značky alebo záujmu.</span><span class="sxs-lookup"><span data-stu-id="80c6a-182">To start the process, select **Run** on the brand or interest configuration page.</span></span> <span data-ttu-id="80c6a-183">Okrem toho môžete nechať systém, aby obohatenie spustil automaticky ako súčasť plánovanej obnovy.</span><span class="sxs-lookup"><span data-stu-id="80c6a-183">Additionally, you can let the system run the enrichment automatically as part of a scheduled refresh.</span></span>
<span data-ttu-id="80c6a-184">V závislosti od veľkosti vašich zákazníckych údajov môže dokončenie procesu obohatenia trvať niekoľko minút.</span><span class="sxs-lookup"><span data-stu-id="80c6a-184">Depending on the size of your customer data, it may take several minutes for an enrichment run to complete.</span></span>

> [!TIP]
> <span data-ttu-id="80c6a-185">Existuje [šesť druhov stavov](system.md#status-types) pre úlohy/procesy.</span><span class="sxs-lookup"><span data-stu-id="80c6a-185">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="80c6a-186">Okrem toho väčšina procesov [závisí na ďalších nadväzujúcich procesoch](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="80c6a-186">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="80c6a-187">Môžete si vybrať stav procesu a zobraziť podrobnosti o priebehu celej úlohy.</span><span class="sxs-lookup"><span data-stu-id="80c6a-187">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="80c6a-188">Po výbere **Pozrieť detaily** pre jednu z úloh úlohy nájdete ďalšie informácie: čas spracovania, posledný dátum spracovania a všetky chyby a varovania spojené s úlohou.</span><span class="sxs-lookup"><span data-stu-id="80c6a-188">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="80c6a-189">Výsledky obohatenia</span><span class="sxs-lookup"><span data-stu-id="80c6a-189">Enrichment results</span></span>

<span data-ttu-id="80c6a-190">Po dokončení procesu obohacovania prejdite na **Moje obohatenia** a skontrolujte celkový počet obohatených zákazníkov a prehľad značiek a záujmov v obohatených profiloch zákazníkov.</span><span class="sxs-lookup"><span data-stu-id="80c6a-190">After running the enrichment process, go to **My enrichments** to review the total number of enriched customers and a breakdown of brands or interests in the enriched customer profiles.</span></span>

:::image type="content" source="media/my-enrichments.png" alt-text="Ukážka výsledkov po spustení procesu obohacovania":::

<span data-ttu-id="80c6a-192">Vyberte obohatené údaje výberom **Zobraziť obohatené údaje** v tabuľke.</span><span class="sxs-lookup"><span data-stu-id="80c6a-192">Review the enriched data by selecting **View enriched data** in the chart.</span></span> <span data-ttu-id="80c6a-193">Obohatené údaje o značkách prejdú do entity **BrandAffinityFromMicrosoft**.</span><span class="sxs-lookup"><span data-stu-id="80c6a-193">Enriched data for brands goes to the **BrandAffinityFromMicrosoft** entity.</span></span> <span data-ttu-id="80c6a-194">Údaje o záujmoch sú v entite **InterestAffinityFromMicrosoft**.</span><span class="sxs-lookup"><span data-stu-id="80c6a-194">Data for interests is in the **InterestAffinityFromMicrosoft** entity.</span></span> <span data-ttu-id="80c6a-195">Tieto entity nájdete uvedené aj v skupine **Obohatenie** v časti **Údaje** > **Entity**.</span><span class="sxs-lookup"><span data-stu-id="80c6a-195">You'll also find these entities listed in the **Enrichment** group in **Data** > **Entities**.</span></span>

## <a name="see-enrichment-data-on-the-customer-card"></a><span data-ttu-id="80c6a-196">Pozrite si údaje o obohatení na karte zákazníka</span><span class="sxs-lookup"><span data-stu-id="80c6a-196">See enrichment data on the customer card</span></span>

<span data-ttu-id="80c6a-197">Značky a záujmy môžu byť zobrazené aj na jednotlivých zákazníckych kartách.</span><span class="sxs-lookup"><span data-stu-id="80c6a-197">Brand and interest affinities can also be viewed on individual customer cards.</span></span> <span data-ttu-id="80c6a-198">Prejdite na možnosť **Zákazníci** a zvoľte si profil zákazníka.</span><span class="sxs-lookup"><span data-stu-id="80c6a-198">Go to **Customers** and select a customer profile.</span></span> <span data-ttu-id="80c6a-199">Na zákazníckej karte nájdete grafy značiek alebo záujmov, ku ktorým majú ľudia v demografickom profile daného zákazníka afinitu.</span><span class="sxs-lookup"><span data-stu-id="80c6a-199">In the customer card, you'll find charts for the brands or interests that people in that customer's demographic profile have affinity for.</span></span>

:::image type="content" source="media/enrichment-customer-card.png" alt-text="Karta zákazníka s obohatenými údajmi":::

## <a name="next-steps"></a><span data-ttu-id="80c6a-201">Ďalšie kroky</span><span class="sxs-lookup"><span data-stu-id="80c6a-201">Next steps</span></span>

<span data-ttu-id="80c6a-202">Stavajte na svojich obohatených údajoch o zákazníkoch.</span><span class="sxs-lookup"><span data-stu-id="80c6a-202">Build on top of your enriched customer data.</span></span> <span data-ttu-id="80c6a-203">Vytvárajte [segmenty](segments.md), [merania](measures.md) a dokonca [exportujte údaje](export-destinations.md) na poskytovanie prispôsobenej používateľskej skúsenosti svojim zákazníkom.</span><span class="sxs-lookup"><span data-stu-id="80c6a-203">Create [Segments](segments.md), [Measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
