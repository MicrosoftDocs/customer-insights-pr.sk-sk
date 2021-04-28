---
title: Obohatenie pomocou obohatenia tretej strany HERE Technologies
description: Všeobecné informácie o obohatení pomocou obohatenia tretej stranou HERE Technologies.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 5d1f037377010153045c9255d2d01f98ebf1fdfd
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896070"
---
# <a name="enrichment-of-customer-profiles-with-here-technologies-preview"></a><span data-ttu-id="65355-103">Obohatenie profilov zákazníkov s pomocou HERE Technologies (ukážka)</span><span class="sxs-lookup"><span data-stu-id="65355-103">Enrichment of customer profiles with HERE Technologies (preview)</span></span>

<span data-ttu-id="65355-104">HERE Technologies je spoločnosť s lokalizačnou platformou, ktorá poskytuje údaje a služby zamerané na lokalizáciu.</span><span class="sxs-lookup"><span data-stu-id="65355-104">HERE Technologies is a location platform company that provides location-centric data and services.</span></span> <span data-ttu-id="65355-105">So službami obohatenia údajov HERE Technologies môžete dosiahnuť presnejšie pochopenie polohy vašich zákazníkov pomocou normalizácie adresy, extrakcie zemepisnej šírky a dĺžky a ďalších údajov.</span><span class="sxs-lookup"><span data-stu-id="65355-105">With HERE Technologies' data enrichment services, you can build a more precise location understanding of your customers with address normalization, latitude and longitude extraction, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="65355-106">Predpoklady</span><span class="sxs-lookup"><span data-stu-id="65355-106">Prerequisites</span></span>

<span data-ttu-id="65355-107">Ak chcete nakonfigurovať obohatenia od HERE Technologies, musíte splniť nasledujúce predpoklady:</span><span class="sxs-lookup"><span data-stu-id="65355-107">To configure HERE Technologies enrichments, the following prerequisites must be met:</span></span>

- <span data-ttu-id="65355-108">Musíte mať aktívne predplatné HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="65355-108">You have an active HERE Technologies subscription.</span></span> <span data-ttu-id="65355-109">Predplatné môžete získať tak, že [sa zaregistrujete tu](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) alebo že priamo [kontaktujete HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you).</span><span class="sxs-lookup"><span data-stu-id="65355-109">To get a subscription, you can [sign-up here](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) or [contact HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) directly.</span></span> [<span data-ttu-id="65355-110">Ďalšie informácie o obohacovaní lokalizačných údajov od HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="65355-110">Learn more about HERE Technologies Location Enrichment.</span></span>](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- <span data-ttu-id="65355-111">Existuje HERE [spojenie](connections.md) k dispozícii *alebo* máte povolenia [správcu](permissions.md#administrator) a kľúč API technológie HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="65355-111">There is a HERE [connection](connections.md) available *or* you have [administrator](permissions.md#administrator) permissions and the HERE Technologies API key.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="65355-112">Konfigurácia obohatenia</span><span class="sxs-lookup"><span data-stu-id="65355-112">Configure the enrichment</span></span>

1. <span data-ttu-id="65355-113">Prejdite na položku **Údaje** > **Obohatenie**.</span><span class="sxs-lookup"><span data-stu-id="65355-113">Go to **Data** > **Enrichment**.</span></span> 

1. <span data-ttu-id="65355-114">Zvoľte možnosť **Obohatiť moje údaje** na dlaždici HERE Technologies a stlačte možnosť **Začíname**.</span><span class="sxs-lookup"><span data-stu-id="65355-114">Select **Enrich my data** on the HERE Technologies tile and select **Get started**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="65355-115">![Dlaždica HERE Technologies](media/HERE-tile.png "Dlaždica HERE Technologies")</span><span class="sxs-lookup"><span data-stu-id="65355-115">![HERE Technologies tile](media/HERE-tile.png "HERE Technologies tile")</span></span>

1. <span data-ttu-id="65355-116">V rozbaľovacej ponuke stlačte možnosť [pripojenie](connections.md).</span><span class="sxs-lookup"><span data-stu-id="65355-116">Select a [connection](connections.md) from the drop-down.</span></span> <span data-ttu-id="65355-117">Ak nie je k dispozícii pripojenie, kontaktujte správcu.</span><span class="sxs-lookup"><span data-stu-id="65355-117">Contact  an administrator if no connection is available.</span></span> <span data-ttu-id="65355-118">Ak ste správca, pripojenie môžete vytvoriť výberom možnosti **Pridať pripojenie**.</span><span class="sxs-lookup"><span data-stu-id="65355-118">If you are an administrator, you can create a connection by selecting **Add connection**.</span></span> <span data-ttu-id="65355-119">V rozbaľovacom ponuke stlačte možnosť **HERE Technologies**.</span><span class="sxs-lookup"><span data-stu-id="65355-119">Choose **HERE Technologies** from the drop-down.</span></span> 

1. <span data-ttu-id="65355-120">Vyberte **Pripojiť k HERE Technologies** na potvrdenie zvoleného spojenia.</span><span class="sxs-lookup"><span data-stu-id="65355-120">Select **Connect to HERE Technologies** to confirm the selection.</span></span>

1.  <span data-ttu-id="65355-121">Stlačte možnosť **Ďalej** a vyberte **Množina údajov o zákazníkoch** na obohatenie o údaje umiestnenia z HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="65355-121">Select **Next** and choose the **Customer data set** you want to enrich with location data from HERE Technologies.</span></span> <span data-ttu-id="65355-122">Môžete zvoliť entitu **Zákazník**, aby ste obohatili všetky svoje zákaznícke profily, alebo vyberte entitu segmentu, aby ste obohatili iba profily zákazníkov obsiahnuté v danom segmente.</span><span class="sxs-lookup"><span data-stu-id="65355-122">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-HERE-configuration-customer-data-set.png" alt-text="Snímka obrazovky pri výbere množiny údajov o zákazníkoch.":::

1. <span data-ttu-id="65355-124">Vyberte, či chcete namapovať polia na primárnu a/alebo sekundárnu adresu.</span><span class="sxs-lookup"><span data-stu-id="65355-124">Choose if you want to map fields to the primary and/or secondary address.</span></span> <span data-ttu-id="65355-125">Môžete určiť mapovanie poľa pre obe adresy a profily pre obe adresy na samostatné obohatenie.</span><span class="sxs-lookup"><span data-stu-id="65355-125">You can specify a field mapping for both addresses and enrich the profiles for both addresses separately.</span></span> <span data-ttu-id="65355-126">Napríklad, ak je tam adresa domova a firmy.</span><span class="sxs-lookup"><span data-stu-id="65355-126">For example, if there's a home and a business address.</span></span> <span data-ttu-id="65355-127">Vyberte **Ďalej**.</span><span class="sxs-lookup"><span data-stu-id="65355-127">Select **Next**.</span></span>

1. <span data-ttu-id="65355-128">Definujte, ktoré polia z vašich zjednotených profilov sa majú použiť na vyhľadanie zodpovedajúcich údajov o polohe od spoločnosti HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="65355-128">Define which fields from your unified profiles should be used to look for matching location data from HERE Technologies.</span></span> <span data-ttu-id="65355-129">Polia **Ulica 1** a **PSČ** sú povinné pre vybranú primárnu a/alebo sekundárnu adresu.</span><span class="sxs-lookup"><span data-stu-id="65355-129">The **Street 1** and **Zip/Postal Code** fields are required for the selected primary and/or secondary address.</span></span> <span data-ttu-id="65355-130">Pre vyššiu presnosť zhody je možné pridať viac polí.</span><span class="sxs-lookup"><span data-stu-id="65355-130">For a higher match accuracy, more fields can be added.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="65355-131">![Stránka konfigurácie obohatenia od HERE Technologies](media/enrichment-HERE-configuration.png "Stránka konfigurácie obohatenia od HERE Technologies")</span><span class="sxs-lookup"><span data-stu-id="65355-131">![HERE Technologies enrichment configuration page](media/enrichment-HERE-configuration.png "HERE Technologies enrichment configuration page")</span></span>

1. <span data-ttu-id="65355-132">Stlačte možnosť **Ďalej** na vyplnenie mapovania poľa.</span><span class="sxs-lookup"><span data-stu-id="65355-132">Select **Next** to complete the field mapping.</span></span>

1. <span data-ttu-id="65355-133">Zadajte názov pre obohatenie.</span><span class="sxs-lookup"><span data-stu-id="65355-133">Provide a name for the enrichment.</span></span> 

<span data-ttu-id="65355-134">1. Stlačte možnosť **Uložiť obohatenie** po preskúmaní vašich možností.</span><span class="sxs-lookup"><span data-stu-id="65355-134">1.Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="configure-the-connection-for-here-technologies"></a><span data-ttu-id="65355-135">Nakonfigurujte pripojenie pre HERE Technologies</span><span class="sxs-lookup"><span data-stu-id="65355-135">Configure the connection for HERE technologies</span></span> 

<span data-ttu-id="65355-136">Na konfiguráciu pripojení musíte byť administrátor.</span><span class="sxs-lookup"><span data-stu-id="65355-136">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="65355-137">Stlačte možnosť **Pridať pripojenie** pri konfigurácii obohatenia *alebo* prejdite na **Správca** > **Pripojenia** a vyberte **Nastaviť** na dlaždici HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="65355-137">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the HERE Technologies tile.</span></span>

1. <span data-ttu-id="65355-138">Zadajte názov pripojenia do boxu **Zobrazovaný názov**.</span><span class="sxs-lookup"><span data-stu-id="65355-138">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="65355-139">Zadajte platný kľúč API technológie HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="65355-139">Provide a valid HERE Technologies API key.</span></span>

1. <span data-ttu-id="65355-140">Skontrolujte a poskytnite svoj súhlas pre **Ochrana osobných údajov a dodržiavanie súladu s nariadeniami** označením začiarkavacieho políčka **Súhlasím**.</span><span class="sxs-lookup"><span data-stu-id="65355-140">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox</span></span>

1. <span data-ttu-id="65355-141">Stlačte **Overiť** na overenie konfigurácie.</span><span class="sxs-lookup"><span data-stu-id="65355-141">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="65355-142">Po dokončení overenia stlačte možnosť **Uložiť**.</span><span class="sxs-lookup"><span data-stu-id="65355-142">After completing the verification, select **Save**.</span></span>

> [!div class="mx-imgBorder"]
   > <span data-ttu-id="65355-143">![Konfiguračná stránka pripojenia HERE Technologies](media/enrichment-HERE-connection.png "Konfiguračná stránka pripojenia HERE Technologies")</span><span class="sxs-lookup"><span data-stu-id="65355-143">![HERE Technologies connection configuration page](media/enrichment-HERE-connection.png "HERE Technologies connection configuration page")</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="65355-144">Výsledky obohatenia</span><span class="sxs-lookup"><span data-stu-id="65355-144">Enrichment results</span></span>

<span data-ttu-id="65355-145">Proces obohatenia spustíte výberom položky **Spustiť** z panela príkazov.</span><span class="sxs-lookup"><span data-stu-id="65355-145">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="65355-146">Môžete tiež nechať systém, aby obohatenie spustil automaticky ako súčasť a [plánovaného obnovenia](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="65355-146">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="65355-147">Čas spracovania bude závisieť od veľkosti vašich zákazníckych údajov a časov odozvy rozhraní API od HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="65355-147">The processing time will depend on the size of your customer data and the API response times from HERE Technologies.</span></span>

<span data-ttu-id="65355-148">Po dokončení procesu obohacovania môžete skontrolovať údaje o nových obohatených zákazníckych profiloch v časti **Moje obohatenia**.</span><span class="sxs-lookup"><span data-stu-id="65355-148">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="65355-149">Ďalej nájdete čas poslednej aktualizácie a počet obohatených profilov.</span><span class="sxs-lookup"><span data-stu-id="65355-149">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="65355-150">Môžete získať podrobné zobrazenie každého obohateného profilu výberom **Zobraziť obohatené údaje**.</span><span class="sxs-lookup"><span data-stu-id="65355-150">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="65355-151">Ďalšie kroky</span><span class="sxs-lookup"><span data-stu-id="65355-151">Next steps</span></span>

<span data-ttu-id="65355-152">Stavajte na svojich obohatených údajoch o zákazníkoch.</span><span class="sxs-lookup"><span data-stu-id="65355-152">Build on top of your enriched customer data.</span></span> <span data-ttu-id="65355-153">Vytvárajte [segmenty](segments.md), [miery](measures.md) a dokonca [exportujte údaje](export-destinations.md) na poskytovanie prispôsobenej používateľskej skúsenosti svojim zákazníkom.</span><span class="sxs-lookup"><span data-stu-id="65355-153">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="65355-154">Ochrana osobných údajov a dodržiavanie súladu s nariadeniami</span><span class="sxs-lookup"><span data-stu-id="65355-154">Data privacy and compliance</span></span>

<span data-ttu-id="65355-155">Keď povolíte prenos údajov spoločnosti HERE Technologies v službe Dynamics 365 Customer Insights, povoľujete tým prenos údajov mimo hranice súladu so službou Dynamics 365 Customer Insights vrátane potenciálne citlivých údajov, ako sú napríklad osobné údaje.</span><span class="sxs-lookup"><span data-stu-id="65355-155">When you enable Dynamics 365 Customer Insights to transmit data to HERE Technologies, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="65355-156">Spoločnosť Microsoft prenesie tieto údaje na váš pokyn, ale vy ste zodpovední za zabezpečenie toho, aby spoločnosť HERE Technologies plnila všetky prípadné povinnosti týkajúce sa ochrany vašich osobných údajov alebo zabezpečenia.</span><span class="sxs-lookup"><span data-stu-id="65355-156">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that HERE Technologies meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="65355-157">Ďalšie informácie nájdete vo [vyhlásení o ochrane súkromia spoločnosti Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="65355-157">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="65355-158">Váš správca služby Dynamics 365 Customer Insights môžete kedykoľvek prestať používať odstránením tohto obohatenia.</span><span class="sxs-lookup"><span data-stu-id="65355-158">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
