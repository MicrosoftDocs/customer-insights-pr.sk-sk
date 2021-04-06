---
title: Obohatenie profilov zákazníkov pomocou programu Microsoft Graph
description: Použite špeciálne údaje z programu Microsoft Graph na obohatenie údajov svojich zákazníkov značkami a záujmami.
ms.date: 12/10/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: aa46dac4f9c0d27881371877b14a92a6725710da
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596472"
---
# <a name="enrich-customer-profiles-with-brand-and-interest-affinities-preview"></a><span data-ttu-id="fc284-103">Obohaťte profily zákazníkov o značky a záujmy (ukážka)</span><span class="sxs-lookup"><span data-stu-id="fc284-103">Enrich customer profiles with brand and interest affinities (preview)</span></span>

<span data-ttu-id="fc284-104">Použite špeciálne údaje z programu Microsoft Graph na obohatenie údajov svojich zákazníkov značkami a záujmami.</span><span class="sxs-lookup"><span data-stu-id="fc284-104">Use proprietary data from the Microsoft Graph to enrich your customer data with brand and interest affinities.</span></span> <span data-ttu-id="fc284-105">Tieto afinity sa určujú na základe údajov od ľudí s podobnou demografiou ako vaši zákazníci.</span><span class="sxs-lookup"><span data-stu-id="fc284-105">These affinities are determined based on data from people with similar demographics to your customers.</span></span> <span data-ttu-id="fc284-106">Tieto informácie vám pomôžu lepšie porozumieť a segmentovať vašich zákazníkov na základe ich príslušnosti k určitým značkám a záujmom.</span><span class="sxs-lookup"><span data-stu-id="fc284-106">This information helps you to better understand and segment your customers based on their affinities to specific brands and interests.</span></span>

<span data-ttu-id="fc284-107">V prehľadoch cieľových skupín prejdite na **Údaje** > **Obohatenie** na [konfiguráciu a zobrazenie obohatení](enrichment-hub.md).</span><span class="sxs-lookup"><span data-stu-id="fc284-107">In audience insights, go to **Data** > **Enrichment** to [configure and view enrichments](enrichment-hub.md).</span></span>

<span data-ttu-id="fc284-108">Ak chcete nakonfigurovať obohatenie o afinity značiek, prejdite na stránku **Objavovať** a vyberte **Obohatiť moje údaje** na dlaždici **Značky**.</span><span class="sxs-lookup"><span data-stu-id="fc284-108">To configure brand affinities enrichment, go to the **Discover** tab and select **Enrich my data** on the **Brands** tile.</span></span>

<span data-ttu-id="fc284-109">Ak chcete nakonfigurovať obohatenie o afinity záujmov, prejdite na stránku **Objavovať** a vyberte **Obohatiť moje údaje** na dlaždici **Záujmy**.</span><span class="sxs-lookup"><span data-stu-id="fc284-109">To configure interest affinities enrichment, go to the **Discover** tab and select **Enrich my data** on the **Interests** tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="fc284-110">![Dlaždice Značky a záujmy](media/BrandsInterest-tile-Hub.png "Dlaždice Značky a záujmy")</span><span class="sxs-lookup"><span data-stu-id="fc284-110">![Brands & Interests tiles](media/BrandsInterest-tile-Hub.png "Brands & Interest tiles")</span></span>

## <a name="about-microsoft-graph"></a><span data-ttu-id="fc284-111">Informácie o Microsoft Graph</span><span class="sxs-lookup"><span data-stu-id="fc284-111">About Microsoft Graph</span></span>

<span data-ttu-id="fc284-112">Údaje vyhľadávania online z programu Microsoft Graph používame na nájdenie príbuznosti značiek a záujmov v rôznych demografických segmentoch (definovaných podľa veku, pohlavia alebo miesta).</span><span class="sxs-lookup"><span data-stu-id="fc284-112">We use online search data from the Microsoft Graph to find affinities for brands and interests across various demographic segments (defined by age, gender, or location).</span></span> <span data-ttu-id="fc284-113">Objem online vyhľadávania pre určitú značku alebo záujem určuje, akú príbuznosť má demografický segment v porovnaní s inými segmentmi k tejto značke alebo záujmu.</span><span class="sxs-lookup"><span data-stu-id="fc284-113">The online search volume for a brand or interest determines how much affinity a demographic segment, compared to other segments, has to that brand or interest.</span></span>

<span data-ttu-id="fc284-114">[Ďalšie informácie o Microsoft Graph](/graph/overview).</span><span class="sxs-lookup"><span data-stu-id="fc284-114">[Learn more about Microsoft Graph](/graph/overview).</span></span>

## <a name="affinity-level-and-score"></a><span data-ttu-id="fc284-115">Úroveň afinity a skóre</span><span class="sxs-lookup"><span data-stu-id="fc284-115">Affinity level and score</span></span>

<span data-ttu-id="fc284-116">V každom obohatenom profile zákazníka poskytujeme dve súvisiace hodnoty – úroveň afinity a skóre afinity.</span><span class="sxs-lookup"><span data-stu-id="fc284-116">On every enriched customer profile, we provide two related values – affinity level and affinity score.</span></span> <span data-ttu-id="fc284-117">Tieto hodnoty vám pomôžu určiť, aká silná je afinita k demografickému segmentu daného profilu, k značke alebo záujmu v porovnaní s ostatnými demografickými segmentmi.</span><span class="sxs-lookup"><span data-stu-id="fc284-117">These values help you determine how strong the affinity is for that profile’s demographic segment, for a brand or interest, as compared to other demographic segments.</span></span>

<span data-ttu-id="fc284-118">*Úroveň afinity* pozostáva zo štyroch úrovní a *skóre afinity* sa počíta na 100-bodovej stupnici, ktorá sa mapuje na úrovne afinity.</span><span class="sxs-lookup"><span data-stu-id="fc284-118">*Affinity level* consists of four levels and *affinity score* is calculated on a 100-point scale that maps to the affinity levels.</span></span>


|<span data-ttu-id="fc284-119">Úroveň afinity</span><span class="sxs-lookup"><span data-stu-id="fc284-119">Affinity level</span></span> |<span data-ttu-id="fc284-120">Skóre afinity</span><span class="sxs-lookup"><span data-stu-id="fc284-120">Affinity score</span></span>  |
|---------|---------|
|<span data-ttu-id="fc284-121">Veľmi vysoká</span><span class="sxs-lookup"><span data-stu-id="fc284-121">Very high</span></span>     | <span data-ttu-id="fc284-122">85 – 100</span><span class="sxs-lookup"><span data-stu-id="fc284-122">85-100</span></span>       |
|<span data-ttu-id="fc284-123">Vysoký</span><span class="sxs-lookup"><span data-stu-id="fc284-123">High</span></span>     | <span data-ttu-id="fc284-124">70 – 84</span><span class="sxs-lookup"><span data-stu-id="fc284-124">70-84</span></span>        |
|<span data-ttu-id="fc284-125">Stredný</span><span class="sxs-lookup"><span data-stu-id="fc284-125">Medium</span></span>     | <span data-ttu-id="fc284-126">35 – 69</span><span class="sxs-lookup"><span data-stu-id="fc284-126">35-69</span></span>        |
|<span data-ttu-id="fc284-127">Nízky</span><span class="sxs-lookup"><span data-stu-id="fc284-127">Low</span></span>     | <span data-ttu-id="fc284-128">1 – 34</span><span class="sxs-lookup"><span data-stu-id="fc284-128">1-34</span></span>        |

<span data-ttu-id="fc284-129">V závislosti od podrobností, ktoré chcete pri meraní afinity, môžete použiť buď úroveň afinity alebo skóre.</span><span class="sxs-lookup"><span data-stu-id="fc284-129">Depending on the granularity you would like for measuring the affinity, you can use either affinity level or score.</span></span> <span data-ttu-id="fc284-130">Skóre afinity vám dáva presnejšiu kontrolu.</span><span class="sxs-lookup"><span data-stu-id="fc284-130">Affinity score gives you more precise control.</span></span>

## <a name="supported-countriesregions"></a><span data-ttu-id="fc284-131">Podporované krajiny/regióny</span><span class="sxs-lookup"><span data-stu-id="fc284-131">Supported countries/regions</span></span>

<span data-ttu-id="fc284-132">V súčasnosti podporujeme možnosti nasledujúcich krajín/regiónov: Austrália, Kanada (angličtina), Francúzsko, Nemecko, Spojené kráľovstvo alebo Spojené štáty (angličtina).</span><span class="sxs-lookup"><span data-stu-id="fc284-132">We currently support the following country/region options: Australia, Canada (English), France, Germany, United Kingdom, or United States (English).</span></span>

<span data-ttu-id="fc284-133">Ak chcete vybrať krajinu, otvorte **Obohatenie značiek** alebo **Obohatenie záujmov** a vyberte **Zmeniť** vedľa **Krajiny/regiónu**.</span><span class="sxs-lookup"><span data-stu-id="fc284-133">To select a country, open the **Brands enrichment** or **Interest enrichment** and select **Change** next to **Country/Region**.</span></span> <span data-ttu-id="fc284-134">Na table **Nastavenia krajiny/regiónu** vyberte možnosť a následne položku **Použiť**.</span><span class="sxs-lookup"><span data-stu-id="fc284-134">In the **Country/Region settings** pane, choose an option and select **Apply**.</span></span>

### <a name="implications-related-to-country-selection"></a><span data-ttu-id="fc284-135">Dôsledky týkajúce sa výberu krajiny</span><span class="sxs-lookup"><span data-stu-id="fc284-135">Implications related to country selection</span></span>

- <span data-ttu-id="fc284-136">Pri [výbere vlastných značiek](#define-your-brands-or-interests) systém poskytuje návrhy na základe vybranej krajiny alebo regiónu.</span><span class="sxs-lookup"><span data-stu-id="fc284-136">When [choosing your own brands](#define-your-brands-or-interests), the system provides suggestions based on the selected country or region.</span></span>

- <span data-ttu-id="fc284-137">Pri [výbere odvetvia](#define-your-brands-or-interests) získate najrelevantnejšie značky alebo záujmy na základe vybranej krajiny alebo regiónu.</span><span class="sxs-lookup"><span data-stu-id="fc284-137">When [choosing an industry](#define-your-brands-or-interests), you'll get the most relevant brands or interests based on the selected country or region.</span></span>

- <span data-ttu-id="fc284-138">Pri [obohacovaní profilov](#refresh-enrichment) obohatíme všetky profily zákazníkov, pre ktoré získame údaje o vybraných značkách a záujmoch.</span><span class="sxs-lookup"><span data-stu-id="fc284-138">When [enriching profiles](#refresh-enrichment), we'll enrich all customer profiles for which we get data for the selected brands and interests.</span></span> <span data-ttu-id="fc284-139">Zahrnutie profilov, ktoré sa nenachádzajú vo vybranej krajine alebo oblasti.</span><span class="sxs-lookup"><span data-stu-id="fc284-139">Including profiles that are not in the selected country or region.</span></span> <span data-ttu-id="fc284-140">Ak ste napríklad vybrali Nemecko, obohatíme profily umiestnené v USA, ak budeme mať k dispozícii údaje programu Microsoft Graph pre vybrané značky a záujmy v USA.</span><span class="sxs-lookup"><span data-stu-id="fc284-140">For example, if you selected Germany, we'll enrich profiles located in the United States if we have Microsoft Graph data available for the selected brands and interests in the US.</span></span>

## <a name="configure-enrichment"></a><span data-ttu-id="fc284-141">Konfigurácia obohatenia</span><span class="sxs-lookup"><span data-stu-id="fc284-141">Configure Enrichment</span></span>

### <a name="define-your-brands-or-interests"></a><span data-ttu-id="fc284-142">Definujte svoje značky alebo záujmy</span><span class="sxs-lookup"><span data-stu-id="fc284-142">Define your brands or interests</span></span>

<span data-ttu-id="fc284-143">Vyberte jednu z nasledujúcich možností:</span><span class="sxs-lookup"><span data-stu-id="fc284-143">Select one of the following options:</span></span>

- <span data-ttu-id="fc284-144">**Odvetvie**: Systém identifikuje top značky alebo záujmy relevantné pre vaše odvetvie a obohacuje o nich vaše zákaznícke údaje.</span><span class="sxs-lookup"><span data-stu-id="fc284-144">**Industry**: The system identifies the top brands or interests relevant to your industry and enriches your customer data with them.</span></span>
- <span data-ttu-id="fc284-145">**Vyberte svoje vlastné**: Vyberte až päť položiek zo zoznamu značiek alebo záujmov, ktoré sú pre vašu organizáciu najrelevantnejšie.</span><span class="sxs-lookup"><span data-stu-id="fc284-145">**Choose your own**: Select up to five items from the list of brands or interests that are most relevant to your organization.</span></span>

<span data-ttu-id="fc284-146">Ak chcete pridať značku alebo záujem, zadajte ich do vstupnej oblasti a získajte návrhy na základe zhodných výrazov.</span><span class="sxs-lookup"><span data-stu-id="fc284-146">To add a brand or interest, enter it in the input area to get suggestions based on matching terms.</span></span> <span data-ttu-id="fc284-147">Ak neuvedieme hľadanú značku alebo záujem, pošlite nám svoje pripomienky pomocou odkazu **Navrhnúť**.</span><span class="sxs-lookup"><span data-stu-id="fc284-147">If we don't list a brand or interest you're looking for, send us feedback using the **Suggest** link.</span></span>

### <a name="review-enrichment-preferences"></a><span data-ttu-id="fc284-148">Kontrola predvolieb obohacovania</span><span class="sxs-lookup"><span data-stu-id="fc284-148">Review enrichment preferences</span></span>

<span data-ttu-id="fc284-149">Skontrolujte svoje predvolené predvoľby obohatenia a podľa potreby ich aktualizujte.</span><span class="sxs-lookup"><span data-stu-id="fc284-149">Review your default enrichment preferences and update them as needed.</span></span>

:::image type="content" source="media/affinity-enrichment-preferences.png" alt-text="Snímka obrazovky okna s predvoľbami obohacovania.":::

### <a name="select-entity-to-enrich"></a><span data-ttu-id="fc284-151">Vyberte entitu na obohatenie</span><span class="sxs-lookup"><span data-stu-id="fc284-151">Select entity to enrich</span></span>

<span data-ttu-id="fc284-152">Vyberte **Obohatená entita** a vyberte množinu údajov, ktorú chcete obohatiť o údaje spoločnosti z programu Microsoft Graph.</span><span class="sxs-lookup"><span data-stu-id="fc284-152">Select **Enriched entity** and choose the data set you want to enrich with company data from the Microsoft Graph.</span></span> <span data-ttu-id="fc284-153">Môžete zvoliť entitu Zákazník, aby ste obohatili všetky svoje zákaznícke profily, alebo vyberte entitu segmentu, aby ste obohatili iba profily zákazníkov obsiahnuté v danom segmente.</span><span class="sxs-lookup"><span data-stu-id="fc284-153">You can select the Customer entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

### <a name="map-your-fields"></a><span data-ttu-id="fc284-154">Priraďte svoje polia</span><span class="sxs-lookup"><span data-stu-id="fc284-154">Map your fields</span></span>

<span data-ttu-id="fc284-155">Mapujte polia z vašej zjednotenej entity zákazníka a definujte demografický segment, ktorý má systém používať na obohatenie vašich údajov o zákazníkoch.</span><span class="sxs-lookup"><span data-stu-id="fc284-155">Map fields from your unified customer entity to define the demographic segment you want the system to use for enriching your customer data.</span></span> <span data-ttu-id="fc284-156">Mapujte krajinu/región a minimálne atribúty Dátum narodenia alebo Pohlavie.</span><span class="sxs-lookup"><span data-stu-id="fc284-156">Map Country/Region and at least Date of Birth or Gender attributes.</span></span> <span data-ttu-id="fc284-157">Okrem toho musíte namapovať aspoň jedno mesto (a štát/kraj) alebo PSČ.</span><span class="sxs-lookup"><span data-stu-id="fc284-157">Additionally, you must map at least one of City (and State/Province) or Postal code.</span></span> <span data-ttu-id="fc284-158">Zvoľte možnosť **Upraviť** na definovanie mapovania polí a keď to dokončíte, stlačte možnosť **Použiť**.</span><span class="sxs-lookup"><span data-stu-id="fc284-158">Select **Edit** to define the mapping of the fields and select **Apply** when you're done.</span></span> <span data-ttu-id="fc284-159">Vyberte **Uložiť** na dokončenie mapovania polí.</span><span class="sxs-lookup"><span data-stu-id="fc284-159">Select **Save** to complete the field mapping.</span></span>

<span data-ttu-id="fc284-160">Podporované sú nasledujúce formáty a hodnoty, hodnoty nerozlišujú veľké a malé písmená:</span><span class="sxs-lookup"><span data-stu-id="fc284-160">The following formats and values are supported, values are not case-sensitive:</span></span>

- <span data-ttu-id="fc284-161">**Dátum narodenia**: Počas prijímania údajov vám odporúčame previesť dátum narodenia na typ DateTime.</span><span class="sxs-lookup"><span data-stu-id="fc284-161">**Date of Birth**: We recommend that date of birth is converted to DateTime type during data ingestion.</span></span> <span data-ttu-id="fc284-162">Alternatívne to môže byť reťazec vo formáte [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) „rrrr-MM-dd“ alebo „rrrr-MM-ddTHH: mm: ssZ“.</span><span class="sxs-lookup"><span data-stu-id="fc284-162">Alternatively, it can be a string in [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) format "yyyy-MM-dd" or "yyyy-MM-ddTHH:mm:ssZ".</span></span>
- <span data-ttu-id="fc284-163">**Pohlavie**: muž, žena, neznáme</span><span class="sxs-lookup"><span data-stu-id="fc284-163">**Gender**: Male, Female, Unknown</span></span>
- <span data-ttu-id="fc284-164">**Poštové smerovacie číslo**: Päťmiestne PSČ pre USA, štandardné poštové smerovacie číslo všade inde</span><span class="sxs-lookup"><span data-stu-id="fc284-164">**Postal code**: Five-digit ZIP Codes for US, standard postal code everywhere else</span></span>
- <span data-ttu-id="fc284-165">**Mesto**: Názov mesta v angličtine</span><span class="sxs-lookup"><span data-stu-id="fc284-165">**City**: City name in English</span></span>
- <span data-ttu-id="fc284-166">**Štát/provincia**: Dvojpísmenová skratka pre USA a Kanadu.</span><span class="sxs-lookup"><span data-stu-id="fc284-166">**State/Province**: Two-letter abbreviation for the US and Canada.</span></span> <span data-ttu-id="fc284-167">Dvoj- alebo trojpísmenná skratka pre Austráliu.</span><span class="sxs-lookup"><span data-stu-id="fc284-167">Two or three letter abbreviation for Australia.</span></span> <span data-ttu-id="fc284-168">Nevzťahuje sa na Francúzsko, Nemecko ani Spojené kráľovstvo.</span><span class="sxs-lookup"><span data-stu-id="fc284-168">Not applicable for France, Germany, or the UK.</span></span>
- <span data-ttu-id="fc284-169">**Krajina/oblasť**:</span><span class="sxs-lookup"><span data-stu-id="fc284-169">**Country/Region**:</span></span>

  - <span data-ttu-id="fc284-170">USA: Spojené štáty americké, Spojené štáty, USA, US, Amerika</span><span class="sxs-lookup"><span data-stu-id="fc284-170">US: United States of America, United States, USA, US, America</span></span>
  - <span data-ttu-id="fc284-171">CA: Kanada, CA</span><span class="sxs-lookup"><span data-stu-id="fc284-171">CA: Canada, CA</span></span>
  - <span data-ttu-id="fc284-172">GB: Spojené kráľovstvo, UK, Veľká Británia, GB, Spojené kráľovstvo Veľkej Británie a Severného Írska, Spojené kráľovstvo Veľkej Británie</span><span class="sxs-lookup"><span data-stu-id="fc284-172">GB: United Kingdom, UK, Great Britain, GB, United Kingdom of Great Britain and Northern Ireland, United Kingdom of Great Britain</span></span>
  - <span data-ttu-id="fc284-173">AU: Austrália, AU, Austrálske spoločenstvo</span><span class="sxs-lookup"><span data-stu-id="fc284-173">AU: Australia, AU, Common Wealth of Australia</span></span>
  - <span data-ttu-id="fc284-174">FR: Francúzsko, FR, Francúzska republika</span><span class="sxs-lookup"><span data-stu-id="fc284-174">FR: France, FR, French Republic</span></span>
  - <span data-ttu-id="fc284-175">DE: Nemecko, Deutschland, Allemagne, DE, Spolková republika Nemecko, Nemecká republika</span><span class="sxs-lookup"><span data-stu-id="fc284-175">DE: Germany, German, Deutschland, Allemagne, DE, Federal Republic of Germany, Republic of Germany</span></span>

## <a name="refresh-enrichment"></a><span data-ttu-id="fc284-176">Obnovenie obohatenia</span><span class="sxs-lookup"><span data-stu-id="fc284-176">Refresh enrichment</span></span>

<span data-ttu-id="fc284-177">Spustite obohatenie po nakonfigurovaní značiek, záujmov a mapovania terénu pre demografické údaje.</span><span class="sxs-lookup"><span data-stu-id="fc284-177">Run the enrichment after configuring brands, interests, and the field mapping for demographics.</span></span> <span data-ttu-id="fc284-178">Ak chcete proces spustiť, vyberte položku **Spustiť** na stránke konfigurácie značky alebo záujmu.</span><span class="sxs-lookup"><span data-stu-id="fc284-178">To start the process, select **Run** on the brand or interest configuration page.</span></span> <span data-ttu-id="fc284-179">Okrem toho môžete nechať systém, aby obohatenie spustil automaticky ako súčasť plánovanej obnovy.</span><span class="sxs-lookup"><span data-stu-id="fc284-179">Additionally, you can let the system run the enrichment automatically as part of a scheduled refresh.</span></span>
<span data-ttu-id="fc284-180">V závislosti od veľkosti vašich zákazníckych údajov môže dokončenie procesu obohatenia trvať niekoľko minút.</span><span class="sxs-lookup"><span data-stu-id="fc284-180">Depending on the size of your customer data, it may take several minutes for an enrichment run to complete.</span></span>

> [!TIP]
> <span data-ttu-id="fc284-181">Existuje [šesť druhov stavov](system.md#status-types) pre úlohy/procesy.</span><span class="sxs-lookup"><span data-stu-id="fc284-181">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="fc284-182">Okrem toho väčšina procesov [závisí na ďalších nadväzujúcich procesoch](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="fc284-182">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="fc284-183">Môžete si vybrať stav procesu a zobraziť podrobnosti o priebehu celej úlohy.</span><span class="sxs-lookup"><span data-stu-id="fc284-183">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="fc284-184">Po výbere **Pozrieť detaily** pre jednu z úloh úlohy nájdete ďalšie informácie: čas spracovania, posledný dátum spracovania a všetky chyby a varovania spojené s úlohou.</span><span class="sxs-lookup"><span data-stu-id="fc284-184">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="fc284-185">Výsledky obohatenia</span><span class="sxs-lookup"><span data-stu-id="fc284-185">Enrichment results</span></span>

<span data-ttu-id="fc284-186">Po dokončení procesu obohacovania prejdite na **Moje obohatenia** a skontrolujte celkový počet obohatených zákazníkov a prehľad značiek a záujmov v obohatených profiloch zákazníkov.</span><span class="sxs-lookup"><span data-stu-id="fc284-186">After running the enrichment process, go to **My enrichments** to review the total number of enriched customers and a breakdown of brands or interests in the enriched customer profiles.</span></span>

:::image type="content" source="media/my-enrichments.png" alt-text="Ukážka výsledkov po spustení procesu obohacovania":::

<span data-ttu-id="fc284-188">Vyberte obohatené údaje výberom **Zobraziť obohatené údaje** v tabuľke.</span><span class="sxs-lookup"><span data-stu-id="fc284-188">Review the enriched data by selecting **View enriched data** in the chart.</span></span> <span data-ttu-id="fc284-189">Obohatené údaje o značkách prejdú do entity **BrandAffinityFromMicrosoft**.</span><span class="sxs-lookup"><span data-stu-id="fc284-189">Enriched data for brands goes to the **BrandAffinityFromMicrosoft** entity.</span></span> <span data-ttu-id="fc284-190">Údaje o záujmoch sú v entite **InterestAffinityFromMicrosoft**.</span><span class="sxs-lookup"><span data-stu-id="fc284-190">Data for interests is in the **InterestAffinityFromMicrosoft** entity.</span></span> <span data-ttu-id="fc284-191">Tieto entity nájdete uvedené aj v skupine **Obohatenie** v časti **Údaje** > **Entity**.</span><span class="sxs-lookup"><span data-stu-id="fc284-191">You'll also find these entities listed in the **Enrichment** group in **Data** > **Entities**.</span></span>

## <a name="see-enrichment-data-on-the-customer-card"></a><span data-ttu-id="fc284-192">Pozrite si údaje o obohatení na karte zákazníka</span><span class="sxs-lookup"><span data-stu-id="fc284-192">See enrichment data on the customer card</span></span>

<span data-ttu-id="fc284-193">Značky a záujmy môžu byť zobrazené aj na jednotlivých zákazníckych kartách.</span><span class="sxs-lookup"><span data-stu-id="fc284-193">Brand and interest affinities can also be viewed on individual customer cards.</span></span> <span data-ttu-id="fc284-194">Prejdite na možnosť **Zákazníci** a zvoľte si profil zákazníka.</span><span class="sxs-lookup"><span data-stu-id="fc284-194">Go to **Customers** and select a customer profile.</span></span> <span data-ttu-id="fc284-195">Na zákazníckej karte nájdete grafy značiek alebo záujmov, ku ktorým majú ľudia v demografickom profile daného zákazníka afinitu.</span><span class="sxs-lookup"><span data-stu-id="fc284-195">In the customer card, you'll find charts for the brands or interests that people in that customer's demographic profile have affinity for.</span></span>

:::image type="content" source="media/enrichment-customer-card.png" alt-text="Karta zákazníka s obohatenými údajmi":::

## <a name="next-steps"></a><span data-ttu-id="fc284-197">Ďalšie kroky</span><span class="sxs-lookup"><span data-stu-id="fc284-197">Next steps</span></span>

<span data-ttu-id="fc284-198">Stavajte na svojich obohatených údajoch o zákazníkoch.</span><span class="sxs-lookup"><span data-stu-id="fc284-198">Build on top of your enriched customer data.</span></span> <span data-ttu-id="fc284-199">Vytvárajte [segmenty](segments.md), [merania](measures.md) a dokonca [exportujte údaje](export-destinations.md) na poskytovanie prispôsobenej používateľskej skúsenosti svojim zákazníkom.</span><span class="sxs-lookup"><span data-stu-id="fc284-199">Create [Segments](segments.md), [Measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]