---
title: Obohatenie pomocou obohatenia tretej strany HERE Technologies
description: Všeobecné informácie o obohatení pomocou obohatenia tretej stranou HERE Technologies.
ms.date: 10/27/2020
ms.reviewer: jodahl
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 7082fcfec099c3c9436b233c193be23625f6691a
ms.sourcegitcommit: a9b2cf598f256d07a48bba8617347ee90024a1dd
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 12/03/2020
ms.locfileid: "4668697"
---
# <a name="enrichment-of-customer-profiles-with-here-technologies-preview"></a><span data-ttu-id="231d9-103">Obohatenie profilov zákazníkov s pomocou HERE Technologies (ukážka)</span><span class="sxs-lookup"><span data-stu-id="231d9-103">Enrichment of customer profiles with HERE Technologies (preview)</span></span>

<span data-ttu-id="231d9-104">HERE Technologies je spoločnosť s lokalizačnou platformou, ktorá poskytuje údaje a služby zamerané na lokalizáciu.</span><span class="sxs-lookup"><span data-stu-id="231d9-104">HERE Technologies is a location platform company that provides location-centric data and services.</span></span> <span data-ttu-id="231d9-105">So službami obohatenia údajov HERE Technologies môžete dosiahnuť presnejšie pochopenie polohy vašich zákazníkov pomocou normalizácie adresy, extrakcie zemepisnej šírky a dĺžky a ďalších údajov.</span><span class="sxs-lookup"><span data-stu-id="231d9-105">With HERE Technologies' data enrichment services, you can build a more precise location understanding of your customers with address normalization, latitude and longitude extraction, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="231d9-106">Predpoklady</span><span class="sxs-lookup"><span data-stu-id="231d9-106">Prerequisites</span></span>

<span data-ttu-id="231d9-107">Ak chcete nakonfigurovať obohatenia od HERE Technologies, musíte splniť nasledujúce predpoklady:</span><span class="sxs-lookup"><span data-stu-id="231d9-107">To configure HERE Technologies enrichments, the following prerequisites must be met:</span></span>

- <span data-ttu-id="231d9-108">Musíte mať aktívne predplatné HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="231d9-108">You have an active HERE Technologies subscription.</span></span> <span data-ttu-id="231d9-109">Predplatné môžete získať tak, že [sa zaregistrujete tu](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) alebo že priamo [kontaktujete HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you).</span><span class="sxs-lookup"><span data-stu-id="231d9-109">To get a subscription, you can [sign-up here](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) or [contact HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) directly.</span></span> [<span data-ttu-id="231d9-110">Ďalšie informácie o obohacovaní lokalizačných údajov od HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="231d9-110">Learn more about HERE Technologies Location Enrichment.</span></span>](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- <span data-ttu-id="231d9-111">Máte kľúč rozhrania API pre HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="231d9-111">You have the HERE Technologies API key.</span></span>

- <span data-ttu-id="231d9-112">Máte povolenia roly [Správca](permissions.md#administrator).</span><span class="sxs-lookup"><span data-stu-id="231d9-112">You have [Administrator](permissions.md#administrator) permissions.</span></span>

## <a name="configuration"></a><span data-ttu-id="231d9-113">Konfigurácia</span><span class="sxs-lookup"><span data-stu-id="231d9-113">Configuration</span></span>

1. <span data-ttu-id="231d9-114">Prejdite na položku **Údaje** > **Obohatenie**.</span><span class="sxs-lookup"><span data-stu-id="231d9-114">Go to **Data** > **Enrichment**.</span></span>

1. <span data-ttu-id="231d9-115">Vyberte položku **Obohatiť moje údaje** na dlaždici HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="231d9-115">Select **Enrich my data** on the HERE Technologies tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="231d9-116">![Dlaždica HERE Technologies](media/HERE-tile.png "Dlaždica HERE Technologies")</span><span class="sxs-lookup"><span data-stu-id="231d9-116">![HERE Technologies tile](media/HERE-tile.png "HERE Technologies tile")</span></span>

1. <span data-ttu-id="231d9-117">Zadajte aktívny **kľúč rozhrania API pre HERE Technologies**.</span><span class="sxs-lookup"><span data-stu-id="231d9-117">Enter an active **HERE Technologies API key**.</span></span> <span data-ttu-id="231d9-118">Skontrolujte a poskytnite svoj súhlas pre **Ochranu osobných údajov a dodržiavanie súladu s nariadeniami** výberom začiarkavacieho políčka **Súhlasím**.</span><span class="sxs-lookup"><span data-stu-id="231d9-118">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span> 

1. <span data-ttu-id="231d9-119">Potvrďte obidva vstupy výberom položky **Pripojiť k HERE**.</span><span class="sxs-lookup"><span data-stu-id="231d9-119">Confirm both inputs by selecting **Connect to HERE**.</span></span>

1. <span data-ttu-id="231d9-120">Vyberte položku **Pridať údaje** a vyberte, či chcete namapovať polia na primárnu a/alebo sekundárnu adresu.</span><span class="sxs-lookup"><span data-stu-id="231d9-120">Select **Add data** and choose if you want to map fields to the primary and/or secondary address.</span></span> <span data-ttu-id="231d9-121">Môžete určiť mapovanie polí pre obe adresy (napríklad adresu bydliska a firmy) a profily pre obe adresy obohatiť osobitne.</span><span class="sxs-lookup"><span data-stu-id="231d9-121">You can specify a field mapping for both addresses (for example, a home and a business address) and enrich the profiles for both addresses separately.</span></span> <span data-ttu-id="231d9-122">Vyberte **Ďalej**.</span><span class="sxs-lookup"><span data-stu-id="231d9-122">Select **Next**.</span></span>

1. <span data-ttu-id="231d9-123">Definujte, ktoré polia z vašich zjednotených profilov sa majú použiť na vyhľadanie zodpovedajúcich údajov o polohe od spoločnosti HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="231d9-123">Define which fields from your unified profiles should be used to look for matching location data from HERE Technologies.</span></span> <span data-ttu-id="231d9-124">Polia **Ulica 1** a **PSČ** sú povinné pre vybranú primárnu a/alebo sekundárnu adresu.</span><span class="sxs-lookup"><span data-stu-id="231d9-124">The **Street 1** and **Zip/Postal Code** fields are required for the selected primary and/or secondary address.</span></span> <span data-ttu-id="231d9-125">Pre vyššiu presnosť zhody je možné pridať viac polí.</span><span class="sxs-lookup"><span data-stu-id="231d9-125">For a higher match accuracy, more fields can be added.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="231d9-126">![Stránka konfigurácie obohatenia od HERE Technologies](media/enrichment-HERE-configuration.png "Stránka konfigurácie obohatenia od HERE Technologies")</span><span class="sxs-lookup"><span data-stu-id="231d9-126">![HERE Technologies enrichment configuration page](media/enrichment-HERE-configuration.png "HERE Technologies enrichment configuration page")</span></span>

1. <span data-ttu-id="231d9-127">Výberom položky **Použiť** dokončíte mapovanie polí.</span><span class="sxs-lookup"><span data-stu-id="231d9-127">Select **Apply** to complete the field mapping.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="231d9-128">Výsledky obohatenia</span><span class="sxs-lookup"><span data-stu-id="231d9-128">Enrichment results</span></span>

<span data-ttu-id="231d9-129">Proces obohatenia spustíte výberom položky **Spustiť** z panela príkazov.</span><span class="sxs-lookup"><span data-stu-id="231d9-129">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="231d9-130">Môžete tiež nechať systém, aby obohatenie spustil automaticky ako súčasť a [plánovaného obnovenia](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="231d9-130">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="231d9-131">Čas spracovania bude závisieť od veľkosti vašich zákazníckych údajov a časov odozvy rozhraní API od HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="231d9-131">The processing time will depend on the size of your customer data and the API response times from HERE Technologies.</span></span>

<span data-ttu-id="231d9-132">Po dokončení procesu obohacovania môžete skontrolovať údaje o nových obohatených zákazníckych profiloch v časti **Moje obohatenia**.</span><span class="sxs-lookup"><span data-stu-id="231d9-132">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="231d9-133">Ďalej nájdete čas poslednej aktualizácie a počet obohatených profilov.</span><span class="sxs-lookup"><span data-stu-id="231d9-133">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="231d9-134">Môžete získať podrobné zobrazenie každého obohateného profilu výberom **Zobraziť obohatené údaje**.</span><span class="sxs-lookup"><span data-stu-id="231d9-134">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="231d9-135">Ďalšie kroky</span><span class="sxs-lookup"><span data-stu-id="231d9-135">Next steps</span></span>

<span data-ttu-id="231d9-136">Stavajte na svojich obohatených údajoch o zákazníkoch.</span><span class="sxs-lookup"><span data-stu-id="231d9-136">Build on top of your enriched customer data.</span></span> <span data-ttu-id="231d9-137">Vytvárajte [segmenty](segments.md), [miery](measures.md) a dokonca [exportujte údaje](export-destinations.md) na poskytovanie prispôsobenej používateľskej skúsenosti svojim zákazníkom.</span><span class="sxs-lookup"><span data-stu-id="231d9-137">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="231d9-138">Ochrana osobných údajov a dodržiavanie súladu s nariadeniami</span><span class="sxs-lookup"><span data-stu-id="231d9-138">Data privacy and compliance</span></span>

<span data-ttu-id="231d9-139">Keď povolíte prenos údajov spoločnosti HERE Technologies v službe Dynamics 365 Customer Insights, povoľujete tým prenos údajov mimo hranice súladu so službou Dynamics 365 Customer Insights vrátane potenciálne citlivých údajov, ako sú napríklad osobné údaje.</span><span class="sxs-lookup"><span data-stu-id="231d9-139">When you enable Dynamics 365 Customer Insights to transmit data to HERE Technologies, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="231d9-140">Spoločnosť Microsoft prenesie tieto údaje na váš pokyn, ale vy ste zodpovední za zabezpečenie toho, aby spoločnosť HERE Technologies plnila všetky prípadné povinnosti týkajúce sa ochrany vašich osobných údajov alebo zabezpečenia.</span><span class="sxs-lookup"><span data-stu-id="231d9-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that HERE Technologies meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="231d9-141">Ďalšie informácie nájdete vo [vyhlásení o ochrane súkromia spoločnosti Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="231d9-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="231d9-142">Váš správca služby Dynamics 365 Customer Insights môžete kedykoľvek prestať používať odstránením tohto obohatenia.</span><span class="sxs-lookup"><span data-stu-id="231d9-142">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>
