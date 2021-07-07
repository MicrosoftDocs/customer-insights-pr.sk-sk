---
title: Obohatenie pomocou tretej strany HERE Technologies
description: Všeobecné informácie o obohatení pomocou obohatenia tretej stranou HERE Technologies.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: b3c1da0f541efb85b2ca9d87a2e3b97bbfb6ca7f
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305313"
---
# <a name="enrichment-of-customer-profiles-with-here-technologies-preview"></a><span data-ttu-id="c2fef-103">Obohatenie profilov zákazníkov s pomocou HERE Technologies (ukážka)</span><span class="sxs-lookup"><span data-stu-id="c2fef-103">Enrichment of customer profiles with HERE Technologies (preview)</span></span>

<span data-ttu-id="c2fef-104">HERE Technologies je spoločnosť s lokalizačnou platformou, ktorá poskytuje údaje a služby zamerané na lokalizáciu.</span><span class="sxs-lookup"><span data-stu-id="c2fef-104">HERE Technologies is a location platform company that provides location-centric data and services.</span></span> <span data-ttu-id="c2fef-105">So službami obohatenia údajov HERE Technologies môžete dosiahnuť presnejšie pochopenie polohy vašich zákazníkov pomocou normalizácie adresy, extrakcie zemepisnej šírky a dĺžky a ďalších údajov.</span><span class="sxs-lookup"><span data-stu-id="c2fef-105">With HERE Technologies' data enrichment services, you can build a more precise location understanding of your customers with address normalization, latitude and longitude extraction, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="c2fef-106">Predpoklady</span><span class="sxs-lookup"><span data-stu-id="c2fef-106">Prerequisites</span></span>

<span data-ttu-id="c2fef-107">Ak chcete nakonfigurovať obohatenia od HERE Technologies, musíte splniť nasledujúce predpoklady:</span><span class="sxs-lookup"><span data-stu-id="c2fef-107">To configure HERE Technologies enrichments, the following prerequisites must be met:</span></span>

- <span data-ttu-id="c2fef-108">Musíte mať aktívne predplatné HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="c2fef-108">You have an active HERE Technologies subscription.</span></span> <span data-ttu-id="c2fef-109">Predplatné môžete získať tak, že [sa zaregistrujete tu](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) alebo že priamo [kontaktujete HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you).</span><span class="sxs-lookup"><span data-stu-id="c2fef-109">To get a subscription, you can [sign up here](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) or [contact HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) directly.</span></span> [<span data-ttu-id="c2fef-110">Ďalšie informácie o obohacovaní lokalizačných údajov od HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="c2fef-110">Learn more about HERE Technologies Location Enrichment.</span></span>](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- <span data-ttu-id="c2fef-111">Je k dispozícii [pripojenie](connections.md) HERE *alebo* máte povolania [správcu](permissions.md#administrator) a kľúč rozhrania API pre HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="c2fef-111">A HERE [connection](connections.md) is available *or* you have [administrator](permissions.md#administrator) permissions and the HERE Technologies API key.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="c2fef-112">Konfigurácia obohatenia</span><span class="sxs-lookup"><span data-stu-id="c2fef-112">Configure the enrichment</span></span>

1. <span data-ttu-id="c2fef-113">Prejdite na položku **Údaje** > **Obohatenie**.</span><span class="sxs-lookup"><span data-stu-id="c2fef-113">Go to **Data** > **Enrichment**.</span></span> 

1. <span data-ttu-id="c2fef-114">Zvoľte možnosť **Obohatiť moje údaje** na dlaždici HERE Technologies a stlačte možnosť **Začíname**.</span><span class="sxs-lookup"><span data-stu-id="c2fef-114">Select **Enrich my data** on the HERE Technologies tile and select **Get started**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c2fef-115">![Dlaždica HERE Technologies](media/HERE-tile.png "Dlaždica HERE Technologies")</span><span class="sxs-lookup"><span data-stu-id="c2fef-115">![HERE Technologies tile](media/HERE-tile.png "HERE Technologies tile")</span></span>

1. <span data-ttu-id="c2fef-116">Vyberte si z rozbaľovacieho zoznamu [pripojenie](connections.md).</span><span class="sxs-lookup"><span data-stu-id="c2fef-116">Select a [connection](connections.md) from the dropdown list.</span></span> <span data-ttu-id="c2fef-117">Ak nie je k dispozícii pripojenie, kontaktujte správcu.</span><span class="sxs-lookup"><span data-stu-id="c2fef-117">Contact  an administrator if no connection is available.</span></span> <span data-ttu-id="c2fef-118">Ak ste správca, pripojenie môžete vytvoriť výberom možnosti **Pridať pripojenie**.</span><span class="sxs-lookup"><span data-stu-id="c2fef-118">If you are an administrator, you can create a connection by selecting **Add connection**.</span></span> <span data-ttu-id="c2fef-119">Vyberte si z rozbaľovacieho zoznamu možnosť **HERE Technologies**.</span><span class="sxs-lookup"><span data-stu-id="c2fef-119">Choose **HERE Technologies** from the dropdown list.</span></span> 

1. <span data-ttu-id="c2fef-120">Vyberte **Pripojiť k HERE Technologies** na potvrdenie zvoleného spojenia.</span><span class="sxs-lookup"><span data-stu-id="c2fef-120">Select **Connect to HERE Technologies** to confirm the selection.</span></span>

1.  <span data-ttu-id="c2fef-121">Stlačte možnosť **Ďalej** a vyberte **Množina údajov o zákazníkoch** na obohatenie o údaje umiestnenia z HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="c2fef-121">Select **Next** and choose the **Customer data set** you want to enrich with location data from HERE Technologies.</span></span> <span data-ttu-id="c2fef-122">Môžete zvoliť entitu **Zákazník**, aby ste obohatili všetky svoje zákaznícke profily, alebo vyberte entitu segmentu, aby ste obohatili iba profily zákazníkov obsiahnuté v danom segmente.</span><span class="sxs-lookup"><span data-stu-id="c2fef-122">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-HERE-configuration-customer-data-set.png" alt-text="Snímka obrazovky pri výbere množiny údajov o zákazníkoch.":::

1. <span data-ttu-id="c2fef-124">Vyberte, či chcete namapovať polia na primárnu a/alebo sekundárnu adresu.</span><span class="sxs-lookup"><span data-stu-id="c2fef-124">Choose if you want to map fields to the primary and/or secondary address.</span></span> <span data-ttu-id="c2fef-125">Môžete určiť mapovanie poľa pre obe adresy a profily pre obe adresy na samostatné obohatenie.</span><span class="sxs-lookup"><span data-stu-id="c2fef-125">You can specify a field mapping for both addresses and enrich the profiles for both addresses separately.</span></span> <span data-ttu-id="c2fef-126">Napríklad, ak je tam adresa domova a firmy.</span><span class="sxs-lookup"><span data-stu-id="c2fef-126">For example, if there's a home and a business address.</span></span> <span data-ttu-id="c2fef-127">Vyberte **Ďalej**.</span><span class="sxs-lookup"><span data-stu-id="c2fef-127">Select **Next**.</span></span>

1. <span data-ttu-id="c2fef-128">Definujte, ktoré polia z vašich zjednotených profilov sa majú použiť na vyhľadanie zodpovedajúcich údajov o polohe od spoločnosti HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="c2fef-128">Define which fields from your unified profiles should be used to look for matching location data from HERE Technologies.</span></span> <span data-ttu-id="c2fef-129">Polia **Ulica 1** a **PSČ** sú povinné pre vybranú primárnu a/alebo sekundárnu adresu.</span><span class="sxs-lookup"><span data-stu-id="c2fef-129">The **Street 1** and **Zip/Postal Code** fields are required for the selected primary and/or secondary address.</span></span> <span data-ttu-id="c2fef-130">Pre vyššiu presnosť zhody je možné pridať viac polí.</span><span class="sxs-lookup"><span data-stu-id="c2fef-130">For a higher match accuracy, more fields can be added.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c2fef-131">![Stránka konfigurácie obohatenia od HERE Technologies](media/enrichment-HERE-configuration.png "Stránka konfigurácie obohatenia od HERE Technologies")</span><span class="sxs-lookup"><span data-stu-id="c2fef-131">![HERE Technologies enrichment configuration page](media/enrichment-HERE-configuration.png "HERE Technologies enrichment configuration page")</span></span>

1. <span data-ttu-id="c2fef-132">Stlačte možnosť **Ďalej** na vyplnenie mapovania poľa.</span><span class="sxs-lookup"><span data-stu-id="c2fef-132">Select **Next** to complete the field mapping.</span></span>

1. <span data-ttu-id="c2fef-133">Zadajte názov pre obohatenie.</span><span class="sxs-lookup"><span data-stu-id="c2fef-133">Provide a name for the enrichment.</span></span> 

1. <span data-ttu-id="c2fef-134">Stlačte možnosť **Uložiť obohatenie** po preskúmaní vašich možností.</span><span class="sxs-lookup"><span data-stu-id="c2fef-134">Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="configure-the-connection-for-here-technologies"></a><span data-ttu-id="c2fef-135">Nakonfigurujte pripojenie pre HERE Technologies</span><span class="sxs-lookup"><span data-stu-id="c2fef-135">Configure the connection for HERE Technologies</span></span> 

<span data-ttu-id="c2fef-136">Na konfiguráciu pripojení musíte byť administrátor.</span><span class="sxs-lookup"><span data-stu-id="c2fef-136">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="c2fef-137">Stlačte možnosť **Pridať pripojenie** pri konfigurácii obohatenia *alebo* prejdite na **Správca** > **Pripojenia** a vyberte **Nastaviť** na dlaždici HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="c2fef-137">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the HERE Technologies tile.</span></span>

1. <span data-ttu-id="c2fef-138">Zadajte názov pripojenia do boxu **Zobrazovaný názov**.</span><span class="sxs-lookup"><span data-stu-id="c2fef-138">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="c2fef-139">Zadajte platný kľúč API technológie HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="c2fef-139">Provide a valid HERE Technologies API key.</span></span>

1. <span data-ttu-id="c2fef-140">Skontrolujte a poskytnite svoj súhlas pre **Ochranu osobných údajov a dodržiavanie súladu s nariadeniami** výberom možnosti **Súhlasím**.</span><span class="sxs-lookup"><span data-stu-id="c2fef-140">Review and provide your consent for **Data privacy and compliance** by selecting **I agree**.</span></span>

1. <span data-ttu-id="c2fef-141">Stlačte **Overiť** na overenie konfigurácie.</span><span class="sxs-lookup"><span data-stu-id="c2fef-141">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="c2fef-142">Po dokončení overenia stlačte možnosť **Uložiť**.</span><span class="sxs-lookup"><span data-stu-id="c2fef-142">After completing the verification, select **Save**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c2fef-143">![Konfiguračná stránka pripojenia HERE Technologies](media/enrichment-HERE-connection.png "Konfiguračná stránka pripojenia HERE Technologies")</span><span class="sxs-lookup"><span data-stu-id="c2fef-143">![HERE Technologies connection configuration page](media/enrichment-HERE-connection.png "HERE Technologies connection configuration page")</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="c2fef-144">Výsledky obohatenia</span><span class="sxs-lookup"><span data-stu-id="c2fef-144">Enrichment results</span></span>

<span data-ttu-id="c2fef-145">Proces obohatenia spustíte výberom položky **Spustiť** z panela príkazov.</span><span class="sxs-lookup"><span data-stu-id="c2fef-145">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="c2fef-146">Môžete tiež nechať systém, aby obohatenie spustil automaticky ako súčasť a [plánovaného obnovenia](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="c2fef-146">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="c2fef-147">Čas spracovania bude závisieť od veľkosti vašich zákazníckych údajov a časov odozvy rozhraní API od HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="c2fef-147">The processing time will depend on the size of your customer data and the API response times from HERE Technologies.</span></span>

<span data-ttu-id="c2fef-148">Po dokončení procesu obohacovania môžete skontrolovať údaje o nových obohatených zákazníckych profiloch v časti **Moje obohatenia**.</span><span class="sxs-lookup"><span data-stu-id="c2fef-148">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="c2fef-149">Ďalej nájdete čas poslednej aktualizácie a počet obohatených profilov.</span><span class="sxs-lookup"><span data-stu-id="c2fef-149">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="c2fef-150">Môžete získať podrobné zobrazenie každého obohateného profilu výberom **Zobraziť obohatené údaje**.</span><span class="sxs-lookup"><span data-stu-id="c2fef-150">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="c2fef-151">Ďalšie kroky</span><span class="sxs-lookup"><span data-stu-id="c2fef-151">Next steps</span></span>

<span data-ttu-id="c2fef-152">Stavajte na svojich obohatených údajoch o zákazníkoch.</span><span class="sxs-lookup"><span data-stu-id="c2fef-152">Build on top of your enriched customer data.</span></span> <span data-ttu-id="c2fef-153">Vytvárajte [segmenty](segments.md) a [opatrenia](measures.md), a dokonca [exportujte údaje](export-destinations.md), aby ste mohli poskytovať svojim zákazníkom zážitky šité na mieru.</span><span class="sxs-lookup"><span data-stu-id="c2fef-153">Create [segments](segments.md) and [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="c2fef-154">Ochrana osobných údajov a dodržiavanie súladu s nariadeniami</span><span class="sxs-lookup"><span data-stu-id="c2fef-154">Data privacy and compliance</span></span>

<span data-ttu-id="c2fef-155">Keď povolíte prenos údajov spoločnosti HERE Technologies v službe Dynamics 365 Customer Insights, povoľujete tým prenos údajov mimo hranice súladu so službou Dynamics 365 Customer Insights vrátane potenciálne citlivých údajov, ako sú napríklad osobné údaje.</span><span class="sxs-lookup"><span data-stu-id="c2fef-155">When you enable Dynamics 365 Customer Insights to transmit data to HERE Technologies, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="c2fef-156">Spoločnosť Microsoft prenesie tieto údaje na váš pokyn, ale vy ste zodpovední za zabezpečenie toho, aby spoločnosť HERE Technologies plnila všetky prípadné povinnosti týkajúce sa ochrany vašich osobných údajov alebo zabezpečenia.</span><span class="sxs-lookup"><span data-stu-id="c2fef-156">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that HERE Technologies meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="c2fef-157">Ďalšie informácie nájdete vo [vyhlásení o ochrane súkromia spoločnosti Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="c2fef-157">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="c2fef-158">Váš správca služby Dynamics 365 Customer Insights môžete kedykoľvek prestať používať odstránením tohto obohatenia.</span><span class="sxs-lookup"><span data-stu-id="c2fef-158">Your Dynamics 365 Customer Insights administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
