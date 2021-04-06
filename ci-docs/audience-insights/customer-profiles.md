---
title: Zobrazenie profilov zákazníkov
description: Získajte kombinovaný pohľad na vaše zjednotené údaje o zákazníkoch.
ms.date: 12/01/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: d6a9e7872a488b6d68afce35b547f93cc4a7c652
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596886"
---
# <a name="customer-profiles"></a><span data-ttu-id="cbea8-103">Profily zákazníkov</span><span class="sxs-lookup"><span data-stu-id="cbea8-103">Customer profiles</span></span>

<span data-ttu-id="cbea8-104">Na stránke **Zákazníci** je uvedený kombinovaný pohľad na vašich zákazníkov na základe údajov z profilu získaných z [všetkých zdrojov údajov](data-sources.md).</span><span class="sxs-lookup"><span data-stu-id="cbea8-104">The **Customers** page shows a combined view of your customers, based on profile data gathered from [all data sources](data-sources.md).</span></span> <span data-ttu-id="cbea8-105">Profily zákazníkov sú k dispozícii, keď [vytvoríte zjednotenú entitu Zákazník](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="cbea8-105">Customer profiles are available once you [create the unified Customer entity](data-unification.md).</span></span> <span data-ttu-id="cbea8-106">Uistite sa, že ste dokončili proces zjednotenia údajov, aby ste získali bohatší prehľad o svojich zákazníkoch.</span><span class="sxs-lookup"><span data-stu-id="cbea8-106">Make sure you complete the data unification process to get richer views of your customers.</span></span> <span data-ttu-id="cbea8-107">Táto stránka tiež umožňuje vyhľadávať zákazníkov.</span><span class="sxs-lookup"><span data-stu-id="cbea8-107">The page also lets you search for customers.</span></span>

<span data-ttu-id="cbea8-108">Zákazníkmi môžu byť jednotlivci alebo organizácie (ukážka).</span><span class="sxs-lookup"><span data-stu-id="cbea8-108">Customers can be individuals or organizations (preview).</span></span> <span data-ttu-id="cbea8-109">Každý profil zákazníka alebo organizácie je reprezentovaný dlaždicou.</span><span class="sxs-lookup"><span data-stu-id="cbea8-109">Each customer or organization profile is represented by a tile.</span></span> <span data-ttu-id="cbea8-110">Vyberte dlaždicu a zobrazte ďalšie informácie o konkrétnom zákazníkovi alebo organizácii.</span><span class="sxs-lookup"><span data-stu-id="cbea8-110">Select a tile to see additional information on that specific customer or organization.</span></span> <span data-ttu-id="cbea8-111">Ak chcete zobraziť ďalšie záznamy, použite ovládacie prvky stránkovania v dolnej časti stránky.</span><span class="sxs-lookup"><span data-stu-id="cbea8-111">Use the pagination controls at the bottom of the page to see additional records.</span></span>

> [!div class="mx-imgBorder"] 
> <span data-ttu-id="cbea8-112">![Profily zákazníka B2C](media/profiles-customers.png "Profily zákazníka B2C")</span><span class="sxs-lookup"><span data-stu-id="cbea8-112">![B2C customer profiles](media/profiles-customers.png "B2C customer profiles")</span></span>

<span data-ttu-id="cbea8-113">Organizácie (ukážka)</span><span class="sxs-lookup"><span data-stu-id="cbea8-113">Organizations (Preview)</span></span>
> [!div class="mx-imgBorder"] 
> <span data-ttu-id="cbea8-114">![Profily zákazníka B2B](media/profile-customers-b2b.png "Profily zákazníka B2B")</span><span class="sxs-lookup"><span data-stu-id="cbea8-114">![B2B customer profiles](media/profile-customers-b2b.png "B2B customer profiles")</span></span>

> [!NOTE]
> <span data-ttu-id="cbea8-115">Ak nevidíte dlaždice, keď vyberiete **Zákazníci** v navigácii, musí váš správca [definovať aspoň jeden prehľadávateľný atribút](search-filter-index.md) na stránke **Index vyhľadávania a filtrovania**.</span><span class="sxs-lookup"><span data-stu-id="cbea8-115">If you can't see the tiles when you select **Customers** in navigation, your administrator needs to [define at least one searchable attribute](search-filter-index.md) on the **Search & filter index**.</span></span>

## <a name="search-for-customers"></a><span data-ttu-id="cbea8-116">Vyhľadávanie zákazníkov</span><span class="sxs-lookup"><span data-stu-id="cbea8-116">Search for customers</span></span>

<span data-ttu-id="cbea8-117">Vyhľadajte zákazníkov zadaním mena alebo iného atribútu do vyhľadávacieho poľa.</span><span class="sxs-lookup"><span data-stu-id="cbea8-117">Search for customers by entering a name or some other attribute in the search box.</span></span> <span data-ttu-id="cbea8-118">Vyhľadávanie funguje iba v rámci entity Profil zákazníka vytvorenej počas procesu zjednotenia údajov.</span><span class="sxs-lookup"><span data-stu-id="cbea8-118">The search only works within the Customer Profile entity created during the data unification process.</span></span>

<span data-ttu-id="cbea8-119">Ako správca môžete konfigurovať vyhľadávané atribúty pomocou stránky **Index vyhľadávania a filtrovania**.</span><span class="sxs-lookup"><span data-stu-id="cbea8-119">As an admin, you can configure the searchable attributes using the **Search & filter index** page.</span></span> <span data-ttu-id="cbea8-120">Viac informácií nájdete v článku [Spravujte index vyhľadávania a filtrovania](search-filter-index.md).</span><span class="sxs-lookup"><span data-stu-id="cbea8-120">For more information, see [Manage search & filter index](search-filter-index.md).</span></span>

## <a name="filter-customers"></a><span data-ttu-id="cbea8-121">Filtrovanie zákazníkov</span><span class="sxs-lookup"><span data-stu-id="cbea8-121">Filter customers</span></span>

<span data-ttu-id="cbea8-122">Zákazníkov môžete filtrovať podľa polí entity Profil zákazníka.</span><span class="sxs-lookup"><span data-stu-id="cbea8-122">You can filter customers by the Customer Profile entity fields.</span></span> <span data-ttu-id="cbea8-123">Podobne ako pri vyhľadávaní aj váš správca musí najprv definovať polia ako filtrovateľné pomocou stránky **Index vyhľadávania a filtrovania**.</span><span class="sxs-lookup"><span data-stu-id="cbea8-123">Similar to search, your admin will first need to define the fields as filterable using the **Search & filter index** page.</span></span>

1. <span data-ttu-id="cbea8-124">Vyberte položku **Filtrovať** na stránke **Zákazníci**.</span><span class="sxs-lookup"><span data-stu-id="cbea8-124">Select **Filter** on the **Customers** page.</span></span>

2. <span data-ttu-id="cbea8-125">Začiarknite políčka vedľa atribútov, podľa ktorých chcete filtrovať zákazníkov.</span><span class="sxs-lookup"><span data-stu-id="cbea8-125">Check the boxes next to the attributes you want to filter customers by.</span></span>

   > [!div class="mx-imgBorder"] 
   > <span data-ttu-id="cbea8-126">![Profily zákazníkov](media/profiles-customers3.png "Profily zákazníkov")</span><span class="sxs-lookup"><span data-stu-id="cbea8-126">![Customer profiles](media/profiles-customers3.png "Customer profiles")</span></span>

3. <span data-ttu-id="cbea8-127">Odstráňte svoje filtre výberom položky **Vymazať filtre** na stránke **Zákazníci**.</span><span class="sxs-lookup"><span data-stu-id="cbea8-127">Remove your filters by selecting **Clear filters** on the **Customers** page.</span></span>

##  <a name="customer-details-page"></a><span data-ttu-id="cbea8-128">Stránka s podrobnosťami o zákazníkovi</span><span class="sxs-lookup"><span data-stu-id="cbea8-128">Customer details page</span></span>

<span data-ttu-id="cbea8-129">Vyberte ktorúkoľvek z dlaždíc zákazníka a otvorte **stránku s podrobnosťami o zákazníkovi**.</span><span class="sxs-lookup"><span data-stu-id="cbea8-129">Select any of the customer tiles to open the **Customer details page**.</span></span> <span data-ttu-id="cbea8-130">Toto zobrazenie obsahuje zjednotené informácie o vybranom zákazníkovi.</span><span class="sxs-lookup"><span data-stu-id="cbea8-130">This view contains unified information for the selected customer.</span></span>

<span data-ttu-id="cbea8-131">Podrobnosti o zákazníkovi zahŕňajú tieto údaje:</span><span class="sxs-lookup"><span data-stu-id="cbea8-131">Customer details include:</span></span>

-   <span data-ttu-id="cbea8-132">**Dlaždica profilu zákazníka:** Táto dlaždica ukazuje rôzne hodnoty z entity zjednoteného profilu zákazníka.</span><span class="sxs-lookup"><span data-stu-id="cbea8-132">**Customer profile tile:** This tile shows the different values from the unified customer profile entity.</span></span> <span data-ttu-id="cbea8-133">Tieto podrobnosti môžu zahŕňať e-mailovú adresu, meno, mesto atď.</span><span class="sxs-lookup"><span data-stu-id="cbea8-133">These details can include email address, name, city, and so on.</span></span> 

-   <span data-ttu-id="cbea8-134">**Potenciálne záujmy, potenciálne značky:** Ukazuje, či ste nakonfigurovali obohatenie prvej strany.</span><span class="sxs-lookup"><span data-stu-id="cbea8-134">**Potential interests, potential brands:** Shows if you configured a first-party enrichment.</span></span> <span data-ttu-id="cbea8-135">Predstavuje potenciálne záujmy a príbuznosti značiek, ktoré môže mať zákazník s podobným profilom ako tento zákazník.</span><span class="sxs-lookup"><span data-stu-id="cbea8-135">It represents potential interests and affinities for brands a customer with a profile similar to this customer might have.</span></span> <span data-ttu-id="cbea8-136">Ďalšie informácie nájdete v sekcii [Obohatenie profilov zákazníkov o značky a záujmy](enrichment-microsoft-graph.md).</span><span class="sxs-lookup"><span data-stu-id="cbea8-136">For more information, see [Enrich customer profiles with brand and interest affinities](enrichment-microsoft-graph.md).</span></span>

-   <span data-ttu-id="cbea8-137">**Miery:** Ukazuje, či ste nakonfigurovali jednu alebo viac mier konkrétneho typu: miery atribútov zákazníka.</span><span class="sxs-lookup"><span data-stu-id="cbea8-137">**Measures:** Shows if you configured one or more measures of a specific type: customer attribute measures.</span></span> <span data-ttu-id="cbea8-138">Tie zahŕňajú vypočítané KPI v súvislosti s vašimi zákazníkmi na úrovni jednotlivých zákazníkov.</span><span class="sxs-lookup"><span data-stu-id="cbea8-138">They include calculated KPIs around your customers on the individual customer level.</span></span> <span data-ttu-id="cbea8-139">Ďalšie informácie nájdete v sekcii [Definovanie a správa mier](measures.md).</span><span class="sxs-lookup"><span data-stu-id="cbea8-139">For more information, see [Define and manage measures](measures.md).</span></span>

-   <span data-ttu-id="cbea8-140">**Časová os aktivít:** Zobrazuje, či máte nakonfigurované aktivity.</span><span class="sxs-lookup"><span data-stu-id="cbea8-140">**Activity timeline:** Shows if you have configured activities.</span></span> <span data-ttu-id="cbea8-141">Zobrazenie na časovej osi obsahuje chronologicky zoradené aktivity tohto zákazníka, počnúc najnovšou aktivitou.</span><span class="sxs-lookup"><span data-stu-id="cbea8-141">The timeline view contains chronologically sorted activities of this customer, starting with the most recent activity.</span></span> <span data-ttu-id="cbea8-142">Ďalšie informácie nájdete v článku [Aktivity zákazníka](activities.md).</span><span class="sxs-lookup"><span data-stu-id="cbea8-142">For more information, see [Customer activities](activities.md).</span></span>

<span data-ttu-id="cbea8-143">Výberom položky **Späť k zákazníkom** sa vrátite na stránku vyhľadávania zákazníkov.</span><span class="sxs-lookup"><span data-stu-id="cbea8-143">Select **Back to Customers** to return to the customer search page.</span></span>

## <a name="next-steps"></a><span data-ttu-id="cbea8-144">Ďalšie kroky</span><span class="sxs-lookup"><span data-stu-id="cbea8-144">Next steps</span></span>

<span data-ttu-id="cbea8-145">[Pridanie ďalších zdrojov údajov](data-sources.md) alebo [vytváranie zákazníckych segmentov](segments.md).</span><span class="sxs-lookup"><span data-stu-id="cbea8-145">[Add more data sources](data-sources.md) or [create customer segments](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]