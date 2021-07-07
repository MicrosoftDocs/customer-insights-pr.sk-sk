---
title: Obohatenie pomocou tretej strany Experian
description: Všeobecné informácie o obohatení pomocou tretej strany Experian.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 7c82fe92b3351a782a4fa6510300d870b742d042
ms.sourcegitcommit: 42b3bce1e20e7cc707d232844dacfeed3d6fc096
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 06/28/2021
ms.locfileid: "6309839"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a><span data-ttu-id="94622-103">Obohaťte profily zákazníkov o demografické údaje od spoločnosti Experian (verzia Preview)</span><span class="sxs-lookup"><span data-stu-id="94622-103">Enrich customer profiles with demographics from Experian (preview)</span></span>

<span data-ttu-id="94622-104">Experian je svetovým lídrom v oblasti vykazovania spotrebiteľských a obchodných úverov a marketingových služieb.</span><span class="sxs-lookup"><span data-stu-id="94622-104">Experian is a global leader in consumer and business credit reporting and marketing services.</span></span> <span data-ttu-id="94622-105">So službami obohatenia údajov spoločnosti Experian môžete lepšie porozumieť svojim zákazníkom tým, že obohatíte ich zákaznícke profily o demografické údaje, ako je veľkosť domácnosti, príjem a podobne.</span><span class="sxs-lookup"><span data-stu-id="94622-105">With Experian’s data enrichment services, you can build a deeper understanding of your customers by enriching your customer profiles with demographic data such as household size, income, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="94622-106">Predpoklady</span><span class="sxs-lookup"><span data-stu-id="94622-106">Prerequisites</span></span>

<span data-ttu-id="94622-107">Ak chcete nakonfigurovať Experian, musia byť splnené nasledujúce podmienky:</span><span class="sxs-lookup"><span data-stu-id="94622-107">To configure Experian, the following prerequisites must be met:</span></span>

- <span data-ttu-id="94622-108">Mať aktívne predplatné služby Experian.</span><span class="sxs-lookup"><span data-stu-id="94622-108">You have an active Experian subscription.</span></span> <span data-ttu-id="94622-109">Ak chcete získať predplatné, [kontaktujte priamo spoločnosť Experian](https://www.experian.com/marketing-services/contact).</span><span class="sxs-lookup"><span data-stu-id="94622-109">To get a subscription, [contact Experian](https://www.experian.com/marketing-services/contact) directly.</span></span> <span data-ttu-id="94622-110">[Získajte ďalšie informácie obohatení údajov Experian](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span><span class="sxs-lookup"><span data-stu-id="94622-110">[Learn more about Experian Data Enrichment](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span></span>

- <span data-ttu-id="94622-111">Pripojenie Experian už nakonfiguroval správca *alebo* máte povolenia [správcu](permissions.md#administrator).</span><span class="sxs-lookup"><span data-stu-id="94622-111">An Experian connection has already been configured by an administrator *or* you have [administrator](permissions.md#administrator) permissions.</span></span> <span data-ttu-id="94622-112">Potrebujete tiež ID používateľa, ID strany a číslo modelu pre svoj účet Secure Transport (ST) s povoleným SSH, ktoré vám Experian vytvorí.</span><span class="sxs-lookup"><span data-stu-id="94622-112">You also need the User ID, Party ID, and Model Number for your SSH-enabled Secure Transport (ST) account that Experian created for you.</span></span>

## <a name="supported-countriesregions"></a><span data-ttu-id="94622-113">Podporované krajiny/regióny</span><span class="sxs-lookup"><span data-stu-id="94622-113">Supported countries/regions</span></span>

<span data-ttu-id="94622-114">V súčasnosti podporujeme obohacovanie profilov zákazníkov iba v Spojených štátoch.</span><span class="sxs-lookup"><span data-stu-id="94622-114">We currently support enriching customer profiles in the United States only.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="94622-115">Konfigurácia obohatenia</span><span class="sxs-lookup"><span data-stu-id="94622-115">Configure the enrichment</span></span>

1. <span data-ttu-id="94622-116">Prejdite na **Údaje** > **Obohatenie** a vyberte kartu **Objavovať**.</span><span class="sxs-lookup"><span data-stu-id="94622-116">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="94622-117">Vyberte možnosť **Obohatiť moje údaje** na dlaždici Experian.</span><span class="sxs-lookup"><span data-stu-id="94622-117">Select **Enrich my data** on the Experian tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="94622-118">![Experian dlaždic](media/experian-tile.png "Experian tile")</span><span class="sxs-lookup"><span data-stu-id="94622-118">![Experian tile](media/experian-tile.png "Experian tile")</span></span>
   > 

1. <span data-ttu-id="94622-119">Vyberte si z rozbaľovacieho zoznamu [pripojenie](connections.md).</span><span class="sxs-lookup"><span data-stu-id="94622-119">Select a [connection](connections.md) from the dropdown list.</span></span> <span data-ttu-id="94622-120">Ak nie je k dispozícii pripojenie, kontaktujte správcu.</span><span class="sxs-lookup"><span data-stu-id="94622-120">Contact an administrator if no connection is available.</span></span> <span data-ttu-id="94622-121">Ak ste správca, pripojenie môžete vytvoriť výberom možnosti **Pridať pripojenie** a následne položky Experian z rozbaľovacieho zoznamu.</span><span class="sxs-lookup"><span data-stu-id="94622-121">If you are an administrator, you can create a connection by selecting **Add connection** and choosing Experian from the dropdown list.</span></span> 

1. <span data-ttu-id="94622-122">Výberom možnosti **Pripojiť k Experian** potvrdíte výber pripojenia.</span><span class="sxs-lookup"><span data-stu-id="94622-122">Select **Connect to Experian** to confirm the connection selection.</span></span>

1.  <span data-ttu-id="94622-123">Vyberte možnosť **Ďalej** a vyberte si **množinu údajov zákazníkov**, ktorú chcete obohatiť o demografické údaje od spoločnosti Experian.</span><span class="sxs-lookup"><span data-stu-id="94622-123">Select **Next** and choose the **Customer data set** you want to enrich with demographics data from Experian.</span></span> <span data-ttu-id="94622-124">Môžete zvoliť entitu **Zákazník**, aby ste obohatili všetky svoje zákaznícke profily, alebo vyberte entitu segmentu, aby ste obohatili iba profily zákazníkov obsiahnuté v danom segmente.</span><span class="sxs-lookup"><span data-stu-id="94622-124">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-Experian-configuration-customer-data-set.png" alt-text="Snímka obrazovky pri výbere množiny údajov o zákazníkoch.":::

1. <span data-ttu-id="94622-126">Vyberte možnosť **Ďalej** a definujte, ktorý typ polí z vašich zjednotených profilov sa má použiť na vyhľadanie zodpovedajúcich demografických údajov od spoločnosti Experian.</span><span class="sxs-lookup"><span data-stu-id="94622-126">Select **Next** and define which type of fields from your unified profiles should be used to look for matching demographics data from Experian.</span></span> <span data-ttu-id="94622-127">Aspoň jedno z polí **Meno a adresa**, **Telefón** alebo **Email** je požadované.</span><span class="sxs-lookup"><span data-stu-id="94622-127">At least one of the fields **Name and address**, **Phone**, or **Email** is required.</span></span> <span data-ttu-id="94622-128">Pre vyššiu presnosť zhody je možné pridať až dve ďalšie polia.</span><span class="sxs-lookup"><span data-stu-id="94622-128">For a higher match accuracy, up to two other fields can be added.</span></span> <span data-ttu-id="94622-129">Tento výber ovplyvní mapovacie polia, ku ktorým máte prístup v ďalšom kroku.</span><span class="sxs-lookup"><span data-stu-id="94622-129">This selection will affect the mapping fields you have access to in the next step.</span></span>

    > [!TIP]
    > <span data-ttu-id="94622-130">Viac kľúčových atribútov identifikátora odoslaných spoločnosti Experian pravdepodobne prinesie vyššiu mieru zhody.</span><span class="sxs-lookup"><span data-stu-id="94622-130">More key identifier attributes sent to Experian likely yield a higher match rate.</span></span>

1. <span data-ttu-id="94622-131">Stlačte možnosť **Ďalej** na spustenie mapovania poľa.</span><span class="sxs-lookup"><span data-stu-id="94622-131">Select **Next** to start the field mapping.</span></span>

1. <span data-ttu-id="94622-132">Definujte, ktorý typ polí z vašich zjednotených profilov sa má použiť na vyhľadanie zodpovedajúcich demografických údajov od spoločnosti Experian.</span><span class="sxs-lookup"><span data-stu-id="94622-132">Define which fields from your unified profiles should be used to look for matching demographics data from Experian.</span></span> <span data-ttu-id="94622-133">Požadované polia sú označené.</span><span class="sxs-lookup"><span data-stu-id="94622-133">Required fields are marked.</span></span>

1. <span data-ttu-id="94622-134">Uveďte názov obohatenia a názov výstupnej entity.</span><span class="sxs-lookup"><span data-stu-id="94622-134">Provide a name for the enrichment and a name for the output entity.</span></span>

1. <span data-ttu-id="94622-135">Stlačte možnosť **Uložiť obohatenie** po preskúmaní vašich možností.</span><span class="sxs-lookup"><span data-stu-id="94622-135">Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="configure-the-connection-for-experian"></a><span data-ttu-id="94622-136">Konfigurácia pripojenia pre Experian</span><span class="sxs-lookup"><span data-stu-id="94622-136">Configure the connection for Experian</span></span> 

<span data-ttu-id="94622-137">Na konfiguráciu pripojení musíte byť administrátor.</span><span class="sxs-lookup"><span data-stu-id="94622-137">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="94622-138">Vyberte možnosť **Pridať pripojenie** pri konfigurácii obohatenia *alebo* prejdite na položku **Správca** > **Pripojenia** a vyberte možnosť **Nastaviť** na dlaždici Experian.</span><span class="sxs-lookup"><span data-stu-id="94622-138">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the Experian tile.</span></span>

1. <span data-ttu-id="94622-139">Vyberte položku **Začíname**.</span><span class="sxs-lookup"><span data-stu-id="94622-139">Select **Get Started**.</span></span>

1. <span data-ttu-id="94622-140">Zadajte názov pripojenia do boxu **Zobrazovaný názov**.</span><span class="sxs-lookup"><span data-stu-id="94622-140">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="94622-141">Zadajte platné ID používateľa, ID strany a číslo modelu pre svoj účet Experian Secure Transport.</span><span class="sxs-lookup"><span data-stu-id="94622-141">Enter valid User ID, Party ID, and Model Number for your Experian Secure Transport account.</span></span>

1. <span data-ttu-id="94622-142">Skontrolujte a poskytnite svoj súhlas pre **Ochranu osobných údajov a dodržiavanie súladu s nariadeniami** výberom možnosti **Súhlasím**.</span><span class="sxs-lookup"><span data-stu-id="94622-142">Review and provide your consent for **Data privacy and compliance** by selecting **I agree**.</span></span>

1. <span data-ttu-id="94622-143">Stlačte **Overiť** na overenie konfigurácie.</span><span class="sxs-lookup"><span data-stu-id="94622-143">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="94622-144">Po dokončení overenia stlačte možnosť **Uložiť**.</span><span class="sxs-lookup"><span data-stu-id="94622-144">After completing the verification, select **Save**.</span></span>
   
   :::image type="content" source="media/enrichment-Experian-connection.png" alt-text="Tabla konfigurácie pripojenia Experian.":::

## <a name="enrichment-results"></a><span data-ttu-id="94622-146">Výsledky obohatenia</span><span class="sxs-lookup"><span data-stu-id="94622-146">Enrichment results</span></span>

<span data-ttu-id="94622-147">Proces obohatenia spustíte výberom položky **Spustiť** z panela príkazov.</span><span class="sxs-lookup"><span data-stu-id="94622-147">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="94622-148">Môžete tiež nechať systém, aby obohatenie spustil automaticky ako súčasť a [plánovaného obnovenia](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="94622-148">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="94622-149">Čas spracovania bude závisieť od rozsahu vašich zákazníckych údajov a procesov obohacovania nastavených pre váš účet spoločnosťou Experian.</span><span class="sxs-lookup"><span data-stu-id="94622-149">The processing time will depend on the size of your customer data and the enrichment processes set up for your account by Experian.</span></span>

<span data-ttu-id="94622-150">Po dokončení procesu obohacovania môžete skontrolovať údaje o nových obohatených zákazníckych profiloch v časti **Moje obohatenia**.</span><span class="sxs-lookup"><span data-stu-id="94622-150">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="94622-151">Ďalej nájdete čas poslednej aktualizácie a počet obohatených profilov.</span><span class="sxs-lookup"><span data-stu-id="94622-151">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="94622-152">Môžete získať podrobné zobrazenie každého obohateného profilu výberom **Zobraziť obohatené údaje**.</span><span class="sxs-lookup"><span data-stu-id="94622-152">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="94622-153">Ďalšie kroky</span><span class="sxs-lookup"><span data-stu-id="94622-153">Next steps</span></span>

<span data-ttu-id="94622-154">Stavajte na svojich obohatených údajoch o zákazníkoch.</span><span class="sxs-lookup"><span data-stu-id="94622-154">Build on top of your enriched customer data.</span></span> <span data-ttu-id="94622-155">Vytvárajte [segmenty](segments.md) a [opatrenia](measures.md), a dokonca [exportujte údaje](export-destinations.md), aby ste mohli poskytovať svojim zákazníkom zážitky šité na mieru.</span><span class="sxs-lookup"><span data-stu-id="94622-155">Create [segments](segments.md) and [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="94622-156">Ochrana osobných údajov a dodržiavanie súladu s nariadeniami</span><span class="sxs-lookup"><span data-stu-id="94622-156">Data privacy and compliance</span></span>

<span data-ttu-id="94622-157">Keď povolíte službe Dynamics 365 Customer Insights, aby prenášala údaje spoločnosti Experian, povoľujete tým aj prenos údajov mimo hranice súladu so službou Dynamics 365 Customer Insights vrátane potenciálne citlivých údajov, ako sú napríklad osobné údaje.</span><span class="sxs-lookup"><span data-stu-id="94622-157">When you enable Dynamics 365 Customer Insights to transmit data to Experian, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="94622-158">Microsoft prenesie tieto údaje na váš pokyn, ale vy ste zodpovední za zabezpečenie toho, aby Experian spĺňal všetky záväzky týkajúce sa ochrany vášho súkromia alebo bezpečnosti.</span><span class="sxs-lookup"><span data-stu-id="94622-158">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Experian meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="94622-159">Ďalšie informácie nájdete vo [vyhlásení o ochrane súkromia spoločnosti Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="94622-159">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="94622-160">Váš správca služby Dynamics 365 Customer Insights môžete kedykoľvek prestať používať odstránením tohto obohatenia.</span><span class="sxs-lookup"><span data-stu-id="94622-160">Your Dynamics 365 Customer Insights administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
