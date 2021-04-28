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
ms.openlocfilehash: 10c338b89a6f9971912d05986c105cba1221b01b
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896024"
---
# <a name="enrichment-for-customer-profiles-preview"></a><span data-ttu-id="d9216-103">Obohacovanie profilov zákazníkov (ukážka)</span><span class="sxs-lookup"><span data-stu-id="d9216-103">Enrichment for customer profiles (preview)</span></span>

<span data-ttu-id="d9216-104">Na obohatenie údajov o zákazníkoch použite údaje zo zdrojov ako Microsoft a ďalších partnerov.</span><span class="sxs-lookup"><span data-stu-id="d9216-104">Use data from sources like Microsoft and other partners to enrich your customer data.</span></span>

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Stránka centra obohatenia":::

<span data-ttu-id="d9216-106">V prehľadoch cieľových skupín prejdite na **Údaje** > **Obohatenie**, aby ste mohli pracovať s možnosťami obohacovania.</span><span class="sxs-lookup"><span data-stu-id="d9216-106">In audience insights, go to **Data** > **Enrichment** to work with enrichment options.</span></span>    
<span data-ttu-id="d9216-107">Ak chcete vytvárať alebo upravovať obohatenia, musíte mať oprávnenie prispievateľa alebo správcu.</span><span class="sxs-lookup"><span data-stu-id="d9216-107">You need to have Contributor or Administrator permissions to create or edit enrichments.</span></span> <span data-ttu-id="d9216-108">Ďalšie informácie nájdete v časti [Povolenia](permissions.md).</span><span class="sxs-lookup"><span data-stu-id="d9216-108">For more information, see [Permissions](permissions.md).</span></span>

<span data-ttu-id="d9216-109">Na internete **Objavovať** nájdete nasledujúce obohatenia:</span><span class="sxs-lookup"><span data-stu-id="d9216-109">On the **Discover** tab, you'll find the following enrichments:</span></span>

- <span data-ttu-id="d9216-110">[Značky](enrichment-microsoft.md) od spoločnosti Microsoft</span><span class="sxs-lookup"><span data-stu-id="d9216-110">[Brands](enrichment-microsoft.md) provided by Microsoft</span></span>
- <span data-ttu-id="d9216-111">[Záujmy](enrichment-microsoft.md) od spoločnosti Microsoft</span><span class="sxs-lookup"><span data-stu-id="d9216-111">[Interests](enrichment-microsoft.md) provided by Microsoft</span></span>
- <span data-ttu-id="d9216-112">[Údaje o spoločnosti](enrichment-leadspace.md) poskytované spoločnosťou Leadspace</span><span class="sxs-lookup"><span data-stu-id="d9216-112">[Company data](enrichment-leadspace.md) provided by Leadspace</span></span>
- <span data-ttu-id="d9216-113">[Demografické údaje](enrichment-experian.md) poskytované spoločnosťou Experian</span><span class="sxs-lookup"><span data-stu-id="d9216-113">[Demographics](enrichment-experian.md) provided by Experian</span></span>
- <span data-ttu-id="d9216-114">[Údaje o polohe](enrichment-here.md) poskytované spoločnosťou HERE Technologies</span><span class="sxs-lookup"><span data-stu-id="d9216-114">[Location data](enrichment-here.md) provided by HERE Technologies</span></span>
- <span data-ttu-id="d9216-115">[Vlastné údaje](enrichment-SFTP-custom-import.md) prostredníctvom protokolu SFTP (Secure File Transfer Protocol)</span><span class="sxs-lookup"><span data-stu-id="d9216-115">[Custom data](enrichment-SFTP-custom-import.md) through Secure File Transfer Protocol (SFTP)</span></span>

<span data-ttu-id="d9216-116">Na karte **Moje obohatenia** môžete vidieť obohatenia, ktoré ste nakonfigurovali, a upraviť ich vlastnosti.</span><span class="sxs-lookup"><span data-stu-id="d9216-116">On the **My enrichments** tab, you can see the enrichments you've configured and edit their properties.</span></span>

## <a name="manage-existing-enrichments"></a><span data-ttu-id="d9216-117">Spravovanie existujúcich obohatení</span><span class="sxs-lookup"><span data-stu-id="d9216-117">Manage existing enrichments</span></span>

<span data-ttu-id="d9216-118">Prejdite do **Moje obohatenia**, aby ste videli všetky nakonfigurované obohatenia.</span><span class="sxs-lookup"><span data-stu-id="d9216-118">Go to the **My enrichments** to see all configured enrichments.</span></span> <span data-ttu-id="d9216-119">Každé obohatenie je predstavované ako riadok, ktorý obsahuje ďalšie informácie o obohatení.</span><span class="sxs-lookup"><span data-stu-id="d9216-119">Each enrichment is represented as a row that includes additional information about the enrichment.</span></span>

<span data-ttu-id="d9216-120">Vyberte obohatenie a zobrazia sa dostupné možnosti.</span><span class="sxs-lookup"><span data-stu-id="d9216-120">Select an enrichment to see the available options.</span></span> <span data-ttu-id="d9216-121">Možnosti môžete zobraziť aj tak, že stlačíte tri bodky (...) v položke zoznamu.</span><span class="sxs-lookup"><span data-stu-id="d9216-121">You can also select the ellipsis (...) on a list item to see the options.</span></span>

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="Možnosti na spravovanie obohatení v zozname obohatení":::

- <span data-ttu-id="d9216-123">**Zobrazenie** podrobností o obohatení s počtom obohatených profilov zákazníkov.</span><span class="sxs-lookup"><span data-stu-id="d9216-123">**View** enrichment details with the number of enriched customer profiles.</span></span>
- <span data-ttu-id="d9216-124">**Úprava** konfigurácie obohacovania.</span><span class="sxs-lookup"><span data-stu-id="d9216-124">**Edit** the enrichment configuration.</span></span>
- <span data-ttu-id="d9216-125">**Spustite** obohatenie na aktualizáciu profilov zákazníkov o najnovšie údaje.</span><span class="sxs-lookup"><span data-stu-id="d9216-125">**Run** the enrichment to update customer profiles with the latest data.</span></span>
- <span data-ttu-id="d9216-126">**Deaktivácia** existujúceho obohatenie, ktoré zabráni automatickému obnoveniu pri každom plánovanom obnovení.</span><span class="sxs-lookup"><span data-stu-id="d9216-126">**Deactivate** an existing enrichment to stop it from refreshing automatically with every scheduled refresh.</span></span> <span data-ttu-id="d9216-127">Dáta z poslednej úspešnej obnovy budú naďalej k dispozícii.</span><span class="sxs-lookup"><span data-stu-id="d9216-127">Data from the last successful refresh will continue to be available.</span></span> <span data-ttu-id="d9216-128">**Aktivácia** neaktívneho obohatenie na reštartovanie automatického obnovovania pri každom plánovanom obnovení.</span><span class="sxs-lookup"><span data-stu-id="d9216-128">**Activate** an inactive enrichment to restart automatic refreshing with every scheduled refresh.</span></span>
- <span data-ttu-id="d9216-129">**Odstráňte** obohatenie.</span><span class="sxs-lookup"><span data-stu-id="d9216-129">**Delete** an enrichment.</span></span>

<span data-ttu-id="d9216-130">Výberom v zozname môžete spustiť alebo deaktivovať viac obohatení naraz.</span><span class="sxs-lookup"><span data-stu-id="d9216-130">You can run or deactivate multiple enrichments at once by selecting them in the list.</span></span> <span data-ttu-id="d9216-131">Možnosti zobrazenia a úpravy nie sú k dispozícii ako hromadná akcia a fungujú naraz iba pre jedno obohatenie.</span><span class="sxs-lookup"><span data-stu-id="d9216-131">View and edit options aren't available as bulk action and only work for one enrichment at a time.</span></span>

## <a name="enrichments-and-connections"></a><span data-ttu-id="d9216-132">Obohatenia a pripojenia</span><span class="sxs-lookup"><span data-stu-id="d9216-132">Enrichments and connections</span></span>

<span data-ttu-id="d9216-133">Obohatenia tretích strán sa konfigurujú pomocou [spojení](connections.md), ktorý správca zriadi pomocou prihlasovacích údajov a poskytne súhlas na prenos údajov.</span><span class="sxs-lookup"><span data-stu-id="d9216-133">Third-party enrichments are configured using [connections](connections.md), which an administrator sets up with credentials and provides consent for data transfers.</span></span> <span data-ttu-id="d9216-134">Pripojenie môžu správcovia a prispievatelia použiť na konfiguráciu obohatení.</span><span class="sxs-lookup"><span data-stu-id="d9216-134">The connection can be used by administrators and contributors to configure enrichments.</span></span>  

## <a name="multiple-enrichments-of-the-same-type"></a><span data-ttu-id="d9216-135">Viacnásobné obohatenie rovnakého typu</span><span class="sxs-lookup"><span data-stu-id="d9216-135">Multiple enrichments of the same type</span></span>

<span data-ttu-id="d9216-136">Entita, ktorá sa má obohatiť, sa špecifikuje počas konfigurácie obohatenia, ktorá umožňuje obohatiť iba podmnožinu vašich profilov.</span><span class="sxs-lookup"><span data-stu-id="d9216-136">The entity to be enriched is specified during the enrichment configuration, which allows you to enrich only a subset of your profiles.</span></span> <span data-ttu-id="d9216-137">V prípade obohaťte údaje iba o konkrétny segment.</span><span class="sxs-lookup"><span data-stu-id="d9216-137">For exmaple, enrich data only for a specific segment.</span></span> <span data-ttu-id="d9216-138">Môžete nakonfigurovať niekoľko obohatení rovnakého typu a znova použiť to isté pripojenie.</span><span class="sxs-lookup"><span data-stu-id="d9216-138">You can configure several enrichments of the same type and reuse the same connection.</span></span> <span data-ttu-id="d9216-139">Niektoré obohatenia budú mať obmedzený počet obohatení rovnakého typu, ktoré je možné vytvoriť.</span><span class="sxs-lookup"><span data-stu-id="d9216-139">Some enrichments will have limits to the number of enrichments of the same type that can be created.</span></span> <span data-ttu-id="d9216-140">Limity a súčasné použitie sú uvedené na stránke **Obohatenie**.</span><span class="sxs-lookup"><span data-stu-id="d9216-140">The limits and current use can be seen on the **Enrichment** page.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
