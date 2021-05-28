---
title: Obohatenie vylepšenia adresy
description: Obohaťte a normalizujte informácie o adrese profilov zákazníkov pomocou modelov spoločnosti Microsoft.
ms.date: 04/21/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 07271d491460764f2c738e760e41c3492f2b6de9
ms.sourcegitcommit: 27f9dd837304ef9fc00f055a6e900fbf6fce1429
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 04/30/2021
ms.locfileid: "5965597"
---
# <a name="enrichment-of-customer-profiles-with-enhanced-addresses"></a><span data-ttu-id="fcde0-103">Obohatenie zákazníckych profilov vylepšenými adresami</span><span class="sxs-lookup"><span data-stu-id="fcde0-103">Enrichment of customer profiles with enhanced addresses</span></span>

<span data-ttu-id="fcde0-104">Adresy vo vašich údajoch môžu byť neštruktúrované, neúplné alebo nesprávne.</span><span class="sxs-lookup"><span data-stu-id="fcde0-104">Addresses in your data can be unstructured, incomplete, or incorrect.</span></span> <span data-ttu-id="fcde0-105">Použite modely spoločnosti Microsoft na normalizáciu a obohatenie vašich adries do [formátu Common Data Model](/common-data-model/schema/core/applicationcommon/address), aby bola zaistená lepšia presnosť a prehľad.</span><span class="sxs-lookup"><span data-stu-id="fcde0-105">Use Microsoft's models to normalize and enrich your addresses into the [Common Data Model format](/common-data-model/schema/core/applicationcommon/address) for better accuracy and insights.</span></span>

## <a name="how-we-enhance-addresses"></a><span data-ttu-id="fcde0-106">Ako vylepšujeme adresy</span><span class="sxs-lookup"><span data-stu-id="fcde0-106">How we enhance addresses</span></span>

<span data-ttu-id="fcde0-107">Náš model prechádza vylepšením adresy v dvoch krokoch.</span><span class="sxs-lookup"><span data-stu-id="fcde0-107">Our model goes through a two-step process to enhance an address.</span></span> <span data-ttu-id="fcde0-108">Najskôr analyzuje adresu, aby identifikovala jej súčasti, a umiestni ich do štruktúrovaného formátu.</span><span class="sxs-lookup"><span data-stu-id="fcde0-108">First, it parses the address to identify its components and puts them into a structured format.</span></span> <span data-ttu-id="fcde0-109">Potom pomocou umelej inteligencie opravíme, doplníme a štandardizujeme hodnoty v adrese.</span><span class="sxs-lookup"><span data-stu-id="fcde0-109">Then, we use artificial intelligence to correct, complete, and standardize the values in the address.</span></span>

### <a name="example"></a><span data-ttu-id="fcde0-110">Príklad</span><span class="sxs-lookup"><span data-stu-id="fcde0-110">Example</span></span>

<span data-ttu-id="fcde0-111">Informácie o adrese môžu byť v neštandardnom formáte a obsahovať pravopisné chyby.</span><span class="sxs-lookup"><span data-stu-id="fcde0-111">Address information might be in a non-standard format and contain spelling errors.</span></span> <span data-ttu-id="fcde0-112">Model dokáže tieto problémy vyriešiť a vytvoriť jednotné adresy v zjednotených profiloch zákazníkov.</span><span class="sxs-lookup"><span data-stu-id="fcde0-112">The model can fix these issues and create consistent addresses in unified customer profiles.</span></span>

```Input
4567 w main stret californa missouri 54321 us
```

```Output
- Street1: 4567 W Main St
- City: California
- StateOrProvince: MO
- ZipOrPostalCode: 54321
- CountryOrRegion: United States of America

- Address: 4567 W Main St, California, MO, 54321, United States of America
```

### <a name="limitations"></a><span data-ttu-id="fcde0-113">Obmedzenia</span><span class="sxs-lookup"><span data-stu-id="fcde0-113">Limitations</span></span>

<span data-ttu-id="fcde0-114">Vylepšené adresy fungujú iba s hodnotami, ktoré už existujú v údajoch o prijatej adrese.</span><span class="sxs-lookup"><span data-stu-id="fcde0-114">Enhanced addresses only works with the values that already exist in your ingested address data.</span></span> <span data-ttu-id="fcde0-115">Čo model nerobí:</span><span class="sxs-lookup"><span data-stu-id="fcde0-115">The model doesn't:</span></span> 

1. <span data-ttu-id="fcde0-116">Skontrolujte, či je adresa platná.</span><span class="sxs-lookup"><span data-stu-id="fcde0-116">Verify if the address is a valid address.</span></span>
2. <span data-ttu-id="fcde0-117">Overte si platnosť niektorej z hodnôt, ako sú PSČ alebo názvy ulíc.</span><span class="sxs-lookup"><span data-stu-id="fcde0-117">Verify if any of the values, such as ZIP codes or street names, are valid.</span></span>
3. <span data-ttu-id="fcde0-118">Zmeňte hodnoty, ktoré nerozpozná.</span><span class="sxs-lookup"><span data-stu-id="fcde0-118">Change values it doesn't recognize.</span></span>

<span data-ttu-id="fcde0-119">Model používa na vylepšenie adries techniky založené na strojovom učení.</span><span class="sxs-lookup"><span data-stu-id="fcde0-119">The model uses machine learning-based techniques to enhance addresses.</span></span> <span data-ttu-id="fcde0-120">Aj keď pri zmene modelu vstupnej hodnoty použijeme vysoký prah spoľahlivosti, rovnako ako pri iných modeloch založených na ML, nie je zaručená 100 % presnosť.</span><span class="sxs-lookup"><span data-stu-id="fcde0-120">While we apply a high confidence threshold for when the model changes an input value, as with any ML-based model, 100% accuracy is not guaranteed.</span></span>

## <a name="supported-countries-or-regions"></a><span data-ttu-id="fcde0-121">Podporované krajiny alebo regióny</span><span class="sxs-lookup"><span data-stu-id="fcde0-121">Supported countries or regions</span></span>

<span data-ttu-id="fcde0-122">V súčasnosti podporujeme obohatenie adries v týchto krajinách alebo regiónoch:</span><span class="sxs-lookup"><span data-stu-id="fcde0-122">We currently support enriching addresses in these countries or regions:</span></span> 

- <span data-ttu-id="fcde0-123">Austrália</span><span class="sxs-lookup"><span data-stu-id="fcde0-123">Australia</span></span>
- <span data-ttu-id="fcde0-124">Kanada</span><span class="sxs-lookup"><span data-stu-id="fcde0-124">Canada</span></span>
- <span data-ttu-id="fcde0-125">Spojené kráľovstvo</span><span class="sxs-lookup"><span data-stu-id="fcde0-125">United Kingdom</span></span>
- <span data-ttu-id="fcde0-126">Spojené štáty americké</span><span class="sxs-lookup"><span data-stu-id="fcde0-126">United States</span></span>

<span data-ttu-id="fcde0-127">Adresy musia obsahovať hodnotu krajiny alebo regiónu.</span><span class="sxs-lookup"><span data-stu-id="fcde0-127">Addresses must contain a country/region value.</span></span> <span data-ttu-id="fcde0-128">Nespracovávame adresy pre krajiny alebo regióny, ktoré nie sú podporované, a adresy, pre ktoré nie je uvedená žiadna krajina alebo región.</span><span class="sxs-lookup"><span data-stu-id="fcde0-128">We don't process addresses for countries or regions that aren't supported and addresses that have no country or region provided.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="fcde0-129">Konfigurácia obohatenia</span><span class="sxs-lookup"><span data-stu-id="fcde0-129">Configure the enrichment</span></span>

1. <span data-ttu-id="fcde0-130">Prejdite na položku **Údaje** > **Obohatenie**.</span><span class="sxs-lookup"><span data-stu-id="fcde0-130">Go to **Data** > **Enrichment**.</span></span>

1. <span data-ttu-id="fcde0-131">Stlačte možnosť **Obohatiť moje údaje** na dlaždici **Vylepšené adresy**.</span><span class="sxs-lookup"><span data-stu-id="fcde0-131">Select **Enrich my data** on the **Enhanced addresses** tile.</span></span>

   :::image type="content" source="media/enhanced-addresses-tile.png" alt-text="Snímka obrazovky z dlaždice Vylepšené adresy.":::

1. <span data-ttu-id="fcde0-133">Stlačte možnosť **Množina zákazníckych údajov** a vyberte entitu obsahujúcu adresy, ktoré chcete obohatiť.</span><span class="sxs-lookup"><span data-stu-id="fcde0-133">Select the **Customer data set** and choose the entity containing the addresses you want to enrich.</span></span> <span data-ttu-id="fcde0-134">Môžete zvoliť entitu *Zákazník* na obohatenie adries vo všetkých vašich zákazníckych profiloch alebo vyberte entitu segmentu na obohatenie adries iba v profiloch zákazníkov obsiahnutých v danom segmente.</span><span class="sxs-lookup"><span data-stu-id="fcde0-134">You can select the *Customer* entity to enrich addresses in all your customer profiles or select a segment entity to enrich addresses only in customer profiles contained in that segment.</span></span>

1. <span data-ttu-id="fcde0-135">Vyberte spôsob formátovania adries vo svojich množinách údajov.</span><span class="sxs-lookup"><span data-stu-id="fcde0-135">Select how addresses are formatted in your data set.</span></span> <span data-ttu-id="fcde0-136">Stlačte možnosť **Adresa s jedným atribútom** ak adresy vo vašich údajoch používajú jedno pole.</span><span class="sxs-lookup"><span data-stu-id="fcde0-136">Choose **Single-attribute address** if addresses in your data use a single field.</span></span> <span data-ttu-id="fcde0-137">Stlačte možnosť **Adresa s viacerými atribútmi** ak adresy vo vašich údajoch používajú viac než jedno údajové pole.</span><span class="sxs-lookup"><span data-stu-id="fcde0-137">Choose **Multiple-attribute address** if addresses in your data use more than one data field.</span></span>

   > [!NOTE]
   > <span data-ttu-id="fcde0-138">Krajina alebo oblasť je povinná v adrese s jedným atribútom aj s viacerými atribútmi.</span><span class="sxs-lookup"><span data-stu-id="fcde0-138">Country/Region is mandatory in both single-attribute and multiple-attribute address.</span></span> <span data-ttu-id="fcde0-139">Adresy, ktoré neobsahujú platné alebo podporované hodnoty krajín alebo oblastí, nebudú obohatené</span><span class="sxs-lookup"><span data-stu-id="fcde0-139">Addresses that don't contain valid or supported country/region values won't be enriched</span></span>

1.  <span data-ttu-id="fcde0-140">Mapujte polia adresy od svojej zjednotenej zákazníckej entity.</span><span class="sxs-lookup"><span data-stu-id="fcde0-140">Map the address fields from your unified customer entity.</span></span>

    :::image type="content" source="media/enhanced-address-mapping.png" alt-text="Vylepšená stránka na mapovanie polí adries.":::

1. <span data-ttu-id="fcde0-142">Stlačte možnosť **Ďalej** na vyplnenie mapovania poľa.</span><span class="sxs-lookup"><span data-stu-id="fcde0-142">Select **Next** to complete the field mapping.</span></span>

1. <span data-ttu-id="fcde0-143">Uveďte názov obohatenia a názov výstupnej entity.</span><span class="sxs-lookup"><span data-stu-id="fcde0-143">Provide a name for the enrichment and the output entity.</span></span>

1. <span data-ttu-id="fcde0-144">Stlačte možnosť **Uložiť obohatenie** po preskúmaní vašich možností.</span><span class="sxs-lookup"><span data-stu-id="fcde0-144">Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="fcde0-145">Výsledky obohatenia</span><span class="sxs-lookup"><span data-stu-id="fcde0-145">Enrichment results</span></span>

<span data-ttu-id="fcde0-146">Proces obohatenia spustíte výberom položky **Spustiť** z panela príkazov.</span><span class="sxs-lookup"><span data-stu-id="fcde0-146">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="fcde0-147">Môžete tiež nechať systém, aby obohatenie spustil automaticky ako súčasť a [plánovaného obnovenia](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="fcde0-147">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="fcde0-148">Čas spracovania závisí od veľkosti vašich zákazníckych údajov.</span><span class="sxs-lookup"><span data-stu-id="fcde0-148">The processing time depends on the size of your customer data.</span></span>

<span data-ttu-id="fcde0-149">Po dokončení procesu obohacovania môžete skontrolovať údaje o nových obohatených zákazníckych profiloch v časti **Moje obohatenia**.</span><span class="sxs-lookup"><span data-stu-id="fcde0-149">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="fcde0-150">Ďalej nájdete čas poslednej aktualizácie a počet obohatených profilov.</span><span class="sxs-lookup"><span data-stu-id="fcde0-150">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="fcde0-151">Môžete získať podrobné zobrazenie každého obohateného profilu výberom **Zobraziť obohatené údaje**.</span><span class="sxs-lookup"><span data-stu-id="fcde0-151">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="fcde0-152">Ďalšie kroky</span><span class="sxs-lookup"><span data-stu-id="fcde0-152">Next steps</span></span>

<span data-ttu-id="fcde0-153">Stavajte na svojich obohatených údajoch o zákazníkoch.</span><span class="sxs-lookup"><span data-stu-id="fcde0-153">Build on top of your enriched customer data.</span></span> <span data-ttu-id="fcde0-154">Vytvárajte [segmenty](segments.md), [miery](measures.md) a dokonca [exportujte údaje](export-destinations.md) na poskytovanie prispôsobenej používateľskej skúsenosti svojim zákazníkom.</span><span class="sxs-lookup"><span data-stu-id="fcde0-154">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
