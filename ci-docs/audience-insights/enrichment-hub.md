---
title: Obohatenie zjednotených profilov zákazníkov
description: Využite možnosti na obohatenie údajov vašich zákazníkov.
ms.date: 11/02/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 36e6f7f8fcd64fc2591e913910918b83bf27567b
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597714"
---
# <a name="enrichment-for-customer-profiles-preview"></a><span data-ttu-id="72bac-103">Obohacovanie profilov zákazníkov (ukážka)</span><span class="sxs-lookup"><span data-stu-id="72bac-103">Enrichment for customer profiles (preview)</span></span>

<span data-ttu-id="72bac-104">Na obohatenie údajov o zákazníkoch použite údaje zo zdrojov ako Microsoft a ďalších partnerov.</span><span class="sxs-lookup"><span data-stu-id="72bac-104">Use data from sources like Microsoft and other partners to enrich your customer data.</span></span>

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Stránka centra obohatenia":::

<span data-ttu-id="72bac-106">V prehľadoch cieľových skupín prejdite na **Údaje** > **Obohatenie**, aby ste mohli pracovať s možnosťami obohacovania.</span><span class="sxs-lookup"><span data-stu-id="72bac-106">In audience insights, go to **Data** > **Enrichment** to work with enrichment options.</span></span>    
<span data-ttu-id="72bac-107">Ak chcete vytvárať alebo upravovať obohatenia, musíte mať oprávnenie prispievateľa alebo správcu.</span><span class="sxs-lookup"><span data-stu-id="72bac-107">You need to have Contributor or Administrator permissions to create or edit enrichments.</span></span> <span data-ttu-id="72bac-108">Ďalšie informácie nájdete v časti [Povolenia](permissions.md).</span><span class="sxs-lookup"><span data-stu-id="72bac-108">For more information, see [Permissions](permissions.md).</span></span>

<span data-ttu-id="72bac-109">Na internete **Objavovať** nájdete nasledujúce obohatenia:</span><span class="sxs-lookup"><span data-stu-id="72bac-109">On the **Discover** tab, you'll find the following enrichments:</span></span>

- <span data-ttu-id="72bac-110">[Značky](enrichment-microsoft-graph.md) poskytuje Microsoft Graph</span><span class="sxs-lookup"><span data-stu-id="72bac-110">[Brands](enrichment-microsoft-graph.md) provided by Microsoft Graph</span></span>
- <span data-ttu-id="72bac-111">[Záujmy](enrichment-microsoft-graph.md) poskytuje Microsoft Graph</span><span class="sxs-lookup"><span data-stu-id="72bac-111">[Interests](enrichment-microsoft-graph.md) provided by Microsoft Graph</span></span>
- <span data-ttu-id="72bac-112">[Údaje o spoločnosti](enrichment-leadspace.md) poskytované spoločnosťou Leadspace</span><span class="sxs-lookup"><span data-stu-id="72bac-112">[Company data](enrichment-leadspace.md) provided by Leadspace</span></span>
- <span data-ttu-id="72bac-113">[Demografické údaje](enrichment-experian.md) poskytované spoločnosťou Experian</span><span class="sxs-lookup"><span data-stu-id="72bac-113">[Demographics](enrichment-experian.md) provided by Experian</span></span>
- <span data-ttu-id="72bac-114">[Údaje o polohe](enrichment-here.md) poskytované spoločnosťou HERE Technologies</span><span class="sxs-lookup"><span data-stu-id="72bac-114">[Location data](enrichment-here.md) provided by HERE Technologies</span></span>
- <span data-ttu-id="72bac-115">[Vlastné údaje](enrichment-SFTP-custom-import.md) prostredníctvom protokolu SFTP (Secure File Transfer Protocol)</span><span class="sxs-lookup"><span data-stu-id="72bac-115">[Custom data](enrichment-SFTP-custom-import.md) through Secure File Transfer Protocol (SFTP)</span></span>

<span data-ttu-id="72bac-116">Na karte **Moje obohatenia** môžete vidieť obohatenia, ktoré ste nakonfigurovali, a upraviť ich vlastnosti.</span><span class="sxs-lookup"><span data-stu-id="72bac-116">On the **My enrichments** tab, you can see the enrichments you've configured and edit their properties.</span></span>

## <a name="manage-existing-enrichments"></a><span data-ttu-id="72bac-117">Spravovanie existujúcich obohatení</span><span class="sxs-lookup"><span data-stu-id="72bac-117">Manage existing enrichments</span></span>

<span data-ttu-id="72bac-118">Prejdite do **Moje obohatenia**, aby ste videli všetky nakonfigurované obohatenia.</span><span class="sxs-lookup"><span data-stu-id="72bac-118">Go to the **My enrichments** to see all configured enrichments.</span></span> <span data-ttu-id="72bac-119">Každé obohatenie je predstavované ako riadok, ktorý obsahuje ďalšie informácie o obohatení.</span><span class="sxs-lookup"><span data-stu-id="72bac-119">Each enrichment is represented as a row that includes additional information about the enrichment.</span></span>

<span data-ttu-id="72bac-120">Vyberte obohatenie a zobrazia sa dostupné možnosti.</span><span class="sxs-lookup"><span data-stu-id="72bac-120">Select an enrichment to see the available options.</span></span> <span data-ttu-id="72bac-121">Môžete tiež zvoliť tri bodky (...) v položke zoznamu a zobraziť možnosti.</span><span class="sxs-lookup"><span data-stu-id="72bac-121">Alternatively, you can select the ellipsis (...) on a list item to see the options.</span></span>

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="Možnosti na spravovanie obohatení v zozname obohatení":::

- <span data-ttu-id="72bac-123">**Zobrazenie** podrobností o obohatení s počtom obohatených profilov zákazníkov.</span><span class="sxs-lookup"><span data-stu-id="72bac-123">**View** enrichment details with the number of enriched customer profiles.</span></span>
- <span data-ttu-id="72bac-124">**Úprava** konfigurácie obohacovania.</span><span class="sxs-lookup"><span data-stu-id="72bac-124">**Edit** the enrichment configuration.</span></span>
- <span data-ttu-id="72bac-125">**Spustite** obohatenie na aktualizáciu profilov zákazníkov o najnovšie údaje.</span><span class="sxs-lookup"><span data-stu-id="72bac-125">**Run** the enrichment to update customer profiles with the latest data.</span></span>
- <span data-ttu-id="72bac-126">**Deaktivácia** existujúceho obohatenie, ktoré zabráni automatickému obnoveniu pri každom plánovanom obnovení.</span><span class="sxs-lookup"><span data-stu-id="72bac-126">**Deactivate** an existing enrichment to stop it from refreshing automatically with every scheduled refresh.</span></span> <span data-ttu-id="72bac-127">Dáta z poslednej úspešnej obnovy budú naďalej k dispozícii.</span><span class="sxs-lookup"><span data-stu-id="72bac-127">Data from the last successful refresh will continue to be available.</span></span> <span data-ttu-id="72bac-128">**Aktivácia** neaktívneho obohatenie na reštartovanie automatického obnovovania pri každom plánovanom obnovení.</span><span class="sxs-lookup"><span data-stu-id="72bac-128">**Activate** an inactive enrichment to restart automatic refreshing with every scheduled refresh.</span></span>
- <span data-ttu-id="72bac-129">**Odstráňte** obohatenie.</span><span class="sxs-lookup"><span data-stu-id="72bac-129">**Delete** an enrichment.</span></span>

<span data-ttu-id="72bac-130">Výberom v zozname môžete spustiť alebo deaktivovať viac obohatení naraz.</span><span class="sxs-lookup"><span data-stu-id="72bac-130">You can run or deactivate multiple enrichments at once by selecting them in the list.</span></span> <span data-ttu-id="72bac-131">Možnosti zobrazenia a úpravy nie sú k dispozícii ako hromadná akcia a fungujú naraz iba pre jedno obohatenie.</span><span class="sxs-lookup"><span data-stu-id="72bac-131">View and edit options aren't available as bulk action and only work for one enrichment at a time.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]