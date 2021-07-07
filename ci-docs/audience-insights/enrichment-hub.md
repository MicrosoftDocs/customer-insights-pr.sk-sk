---
title: Obohatenie zjednotených profilov zákazníkov
description: Využite možnosti na obohatenie údajov vašich zákazníkov.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: c35e73b366fcd5db2ba5a757295ddda6db30efa0
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305267"
---
# <a name="enrichment-for-customer-profiles-preview"></a><span data-ttu-id="fddab-103">Obohacovanie profilov zákazníkov (ukážka)</span><span class="sxs-lookup"><span data-stu-id="fddab-103">Enrichment for customer profiles (preview)</span></span>

<span data-ttu-id="fddab-104">Na obohatenie údajov o zákazníkoch použite údaje zo zdrojov ako Microsoft a ďalších partnerov.</span><span class="sxs-lookup"><span data-stu-id="fddab-104">Use data from sources like Microsoft and other partners to enrich your customer data.</span></span>

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Stránka centra obohatenia":::

<span data-ttu-id="fddab-106">V prehľadoch cieľových skupín prejdite na **Údaje** > **Obohatenie**, aby ste mohli pracovať s možnosťami obohacovania.</span><span class="sxs-lookup"><span data-stu-id="fddab-106">In audience insights, go to **Data** > **Enrichment** to work with enrichment options.</span></span>  

<span data-ttu-id="fddab-107">Ak chcete vytvárať alebo upravovať obohatenia, musíte mať oprávnenie prispievateľa alebo správcu.</span><span class="sxs-lookup"><span data-stu-id="fddab-107">You need to have Contributor or Administrator permissions to create or edit enrichments.</span></span> <span data-ttu-id="fddab-108">Ďalšie informácie nájdete v časti [Povolenia](permissions.md).</span><span class="sxs-lookup"><span data-stu-id="fddab-108">For more information, see [Permissions](permissions.md).</span></span>

<span data-ttu-id="fddab-109">Na internete **Objavovať** nájdete nasledujúce obohatenia:</span><span class="sxs-lookup"><span data-stu-id="fddab-109">On the **Discover** tab, you'll find the following enrichments:</span></span>

- <span data-ttu-id="fddab-110">[Značky](enrichment-microsoft.md) od spoločnosti Microsoft</span><span class="sxs-lookup"><span data-stu-id="fddab-110">[Brands](enrichment-microsoft.md) provided by Microsoft</span></span>
- <span data-ttu-id="fddab-111">[Záujmy](enrichment-microsoft.md) od spoločnosti Microsoft</span><span class="sxs-lookup"><span data-stu-id="fddab-111">[Interests](enrichment-microsoft.md) provided by Microsoft</span></span>
- <span data-ttu-id="fddab-112">[Vylepšené adresy](enrichment-enhanced-addresses.md) poskytované spoločnosťou Microsoft</span><span class="sxs-lookup"><span data-stu-id="fddab-112">[Enhanced addresses](enrichment-enhanced-addresses.md) provided by Microsoft</span></span>
- <span data-ttu-id="fddab-113">[Údaje o spoločnosti](enrichment-leadspace.md) poskytované spoločnosťou Leadspace</span><span class="sxs-lookup"><span data-stu-id="fddab-113">[Company data](enrichment-leadspace.md) provided by Leadspace</span></span>
- <span data-ttu-id="fddab-114">[Demografické údaje](enrichment-experian.md), ktoré poskytuje Experian</span><span class="sxs-lookup"><span data-stu-id="fddab-114">[Demographics](enrichment-experian.md) provided by Experian</span></span>
- <span data-ttu-id="fddab-115">[Údaje o polohe](enrichment-here.md) poskytované spoločnosťou HERE Technologies</span><span class="sxs-lookup"><span data-stu-id="fddab-115">[Location data](enrichment-here.md) provided by HERE Technologies</span></span>
- <span data-ttu-id="fddab-116">[Vlastné údaje](enrichment-SFTP-custom-import.md) prostredníctvom protokolu SFTP (Secure File Transfer Protocol)</span><span class="sxs-lookup"><span data-stu-id="fddab-116">[Custom data](enrichment-SFTP-custom-import.md) through Secure File Transfer Protocol (SFTP)</span></span>

<span data-ttu-id="fddab-117">Na karte **Moje obohatenia** môžete vidieť obohatenia, ktoré ste nakonfigurovali, a upraviť ich vlastnosti.</span><span class="sxs-lookup"><span data-stu-id="fddab-117">On the **My enrichments** tab, you can see the enrichments you've configured and edit their properties.</span></span>

## <a name="manage-existing-enrichments"></a><span data-ttu-id="fddab-118">Spravovanie existujúcich obohatení</span><span class="sxs-lookup"><span data-stu-id="fddab-118">Manage existing enrichments</span></span>

<span data-ttu-id="fddab-119">Prejdite na kartu **Moje obohatenia**, kde nájdete všetky nakonfigurované obohatenia.</span><span class="sxs-lookup"><span data-stu-id="fddab-119">Go to the **My enrichments** tab to see all configured enrichments.</span></span> <span data-ttu-id="fddab-120">Každé obohatenie je predstavované ako riadok, ktorý obsahuje ďalšie informácie o obohatení.</span><span class="sxs-lookup"><span data-stu-id="fddab-120">Each enrichment is represented as a row that includes additional information about the enrichment.</span></span>

<span data-ttu-id="fddab-121">Vyberte obohatenie a zobrazia sa dostupné možnosti.</span><span class="sxs-lookup"><span data-stu-id="fddab-121">Select an enrichment to see the available options.</span></span> <span data-ttu-id="fddab-122">Možnosti môžete zobraziť aj tak, že stlačíte tri bodky (...) v položke zoznamu.</span><span class="sxs-lookup"><span data-stu-id="fddab-122">You can also select the ellipsis (...) on a list item to see the options.</span></span>

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="Možnosti na spravovanie obohatení v zozname obohatení":::

- <span data-ttu-id="fddab-124">**Zobrazenie** podrobností o obohatení s počtom obohatených profilov zákazníkov.</span><span class="sxs-lookup"><span data-stu-id="fddab-124">**View** enrichment details with the number of enriched customer profiles.</span></span>
- <span data-ttu-id="fddab-125">**Úprava** konfigurácie obohacovania.</span><span class="sxs-lookup"><span data-stu-id="fddab-125">**Edit** the enrichment configuration.</span></span>
- <span data-ttu-id="fddab-126">**Spustite** obohatenie na aktualizáciu profilov zákazníkov o najnovšie údaje.</span><span class="sxs-lookup"><span data-stu-id="fddab-126">**Run** the enrichment to update customer profiles with the latest data.</span></span>
- <span data-ttu-id="fddab-127">**Deaktivácia** existujúceho obohatenie, ktoré zabráni automatickému obnoveniu pri každom plánovanom obnovení.</span><span class="sxs-lookup"><span data-stu-id="fddab-127">**Deactivate** an existing enrichment to stop it from refreshing automatically with every scheduled refresh.</span></span> <span data-ttu-id="fddab-128">Dáta z poslednej úspešnej obnovy budú naďalej k dispozícii.</span><span class="sxs-lookup"><span data-stu-id="fddab-128">Data from the last successful refresh will continue to be available.</span></span> <span data-ttu-id="fddab-129">**Aktivácia** neaktívneho obohatenie na reštartovanie automatického obnovovania pri každom plánovanom obnovení.</span><span class="sxs-lookup"><span data-stu-id="fddab-129">**Activate** an inactive enrichment to restart automatic refreshing with every scheduled refresh.</span></span>
- <span data-ttu-id="fddab-130">**Odstráňte** obohatenie.</span><span class="sxs-lookup"><span data-stu-id="fddab-130">**Delete** an enrichment.</span></span>

<span data-ttu-id="fddab-131">Výberom v zozname môžete spustiť alebo deaktivovať viac obohatení naraz.</span><span class="sxs-lookup"><span data-stu-id="fddab-131">You can run or deactivate multiple enrichments at once by selecting them in the list.</span></span> <span data-ttu-id="fddab-132">Možnosti zobrazenia a úpravy nie sú k dispozícii ako hromadná akcia a fungujú naraz iba pre jedno obohatenie.</span><span class="sxs-lookup"><span data-stu-id="fddab-132">View and edit options aren't available as bulk action and only work for one enrichment at a time.</span></span>

## <a name="enrichments-and-connections"></a><span data-ttu-id="fddab-133">Obohatenia a pripojenia</span><span class="sxs-lookup"><span data-stu-id="fddab-133">Enrichments and connections</span></span>

<span data-ttu-id="fddab-134">Obohatenia tretích strán sa konfigurujú pomocou [spojení](connections.md), ktorý správca zriadi pomocou prihlasovacích údajov a poskytne súhlas na prenos údajov.</span><span class="sxs-lookup"><span data-stu-id="fddab-134">Third-party enrichments are configured using [connections](connections.md), which an administrator sets up with credentials and provides consent for data transfers.</span></span> <span data-ttu-id="fddab-135">Pripojenie môžu správcovia a prispievatelia použiť na konfiguráciu obohatení.</span><span class="sxs-lookup"><span data-stu-id="fddab-135">The connection can be used by administrators and contributors to configure enrichments.</span></span>  

## <a name="multiple-enrichments-of-the-same-type"></a><span data-ttu-id="fddab-136">Viacnásobné obohatenie rovnakého typu</span><span class="sxs-lookup"><span data-stu-id="fddab-136">Multiple enrichments of the same type</span></span>

<span data-ttu-id="fddab-137">Entita, ktorá sa má obohatiť, sa špecifikuje počas konfigurácie obohatenia, ktorá umožňuje obohatiť iba podmnožinu vašich profilov.</span><span class="sxs-lookup"><span data-stu-id="fddab-137">The entity to be enriched is specified during the enrichment configuration, which allows you to enrich only a subset of your profiles.</span></span> <span data-ttu-id="fddab-138">Môžete napríklad obohatiť údaje iba v konkrétnom segmente.</span><span class="sxs-lookup"><span data-stu-id="fddab-138">For example, enrich data only for a specific segment.</span></span> <span data-ttu-id="fddab-139">Môžete nakonfigurovať niekoľko obohatení rovnakého typu a znova použiť to isté pripojenie.</span><span class="sxs-lookup"><span data-stu-id="fddab-139">You can configure several enrichments of the same type and reuse the same connection.</span></span> <span data-ttu-id="fddab-140">Niektoré obohatenia budú mať obmedzený počet obohatení rovnakého typu, ktoré je možné vytvoriť.</span><span class="sxs-lookup"><span data-stu-id="fddab-140">Some enrichments will have limits to the number of enrichments of the same type that can be created.</span></span> <span data-ttu-id="fddab-141">Limity a súčasné použitie sú uvedené na stránke **Obohatenie**.</span><span class="sxs-lookup"><span data-stu-id="fddab-141">The limits and current use can be seen on the **Enrichment** page.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
