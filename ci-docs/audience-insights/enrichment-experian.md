---
title: Obohatenie pomocou obohatenia tretej strany Experian
description: Všeobecné informácie o obohatení pomocou obohatenia tretej stranou Experian.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 9cf2a7fa18ecc022ea67f6829f52381ad59f3172
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896392"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a><span data-ttu-id="3cdfb-103">Obohatenie profilov zákazníkov o demografické údaje od spoločnosti Experian (ukážka)</span><span class="sxs-lookup"><span data-stu-id="3cdfb-103">Enrich customer profiles with demographics from Experian (preview)</span></span>

<span data-ttu-id="3cdfb-104">Experian je svetový líder v oblasti marketingových služieb a zisťovania kreditu spotrebiteľov a firiem.</span><span class="sxs-lookup"><span data-stu-id="3cdfb-104">Experian is a global leader in consumer and business credit reporting and marketing services.</span></span> <span data-ttu-id="3cdfb-105">So službami obohacovania údajov od spoločnosti Experian môžete hlbšie porozumieť svojim zákazníkom obohatením profilov svojich zákazníkov o demografické údaje, ako sú veľkosť domácnosti, príjem a ďalšie.</span><span class="sxs-lookup"><span data-stu-id="3cdfb-105">With Experian’s data enrichment services, you can build a deeper understanding of your customers by enriching your customer profiles with demographic data such as household size, income, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="3cdfb-106">Predpoklady</span><span class="sxs-lookup"><span data-stu-id="3cdfb-106">Prerequisites</span></span>

<span data-ttu-id="3cdfb-107">Ak chcete nakonfigurovať Experian, musia byť splnené nasledujúce predpoklady:</span><span class="sxs-lookup"><span data-stu-id="3cdfb-107">To configure Experian, the following prerequisites must be met:</span></span>

- <span data-ttu-id="3cdfb-108">Máte aktívne predplatné Experian.</span><span class="sxs-lookup"><span data-stu-id="3cdfb-108">You have an active Experian subscription.</span></span> <span data-ttu-id="3cdfb-109">Ak chcete získať predplatné, [kontaktujte Experian](https://www.experian.com/marketing-services/contact) priamo.</span><span class="sxs-lookup"><span data-stu-id="3cdfb-109">To get a subscription, [contact Experian](https://www.experian.com/marketing-services/contact) directly.</span></span> <span data-ttu-id="3cdfb-110">[Ďalšie informácie o obohacovaní údajov Experian](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span><span class="sxs-lookup"><span data-stu-id="3cdfb-110">[Learn more about Experian Data Enrichment](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span></span>

- <span data-ttu-id="3cdfb-111">Pripojenie Experian už nakonfiguroval správca *alebo* máte povolenia [správcu](permissions.md#administrator).</span><span class="sxs-lookup"><span data-stu-id="3cdfb-111">An Experian connection has already been configured by an administrator *or* you have [administrator](permissions.md#administrator) permissions.</span></span> <span data-ttu-id="3cdfb-112">Pre svoj účet Secure Transport (ST) s povoleným SSH, ktorý pre vás spoločnosť Experian vytvorila, potrebujete tiež ID používateľa, ID strany a Číslo modelu.</span><span class="sxs-lookup"><span data-stu-id="3cdfb-112">You also need the User ID, Party ID, and Model Number for your SSH-enabled Secure Transport (ST) account that Experian created for you.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="3cdfb-113">Konfigurácia obohatenia</span><span class="sxs-lookup"><span data-stu-id="3cdfb-113">Configure the enrichment</span></span>

1. <span data-ttu-id="3cdfb-114">Prejdite na **Údaje** > **Obohatenie** a vyberte kartu **Objavovať**.</span><span class="sxs-lookup"><span data-stu-id="3cdfb-114">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="3cdfb-115">Vyberte **Obohatiť moje údaje** na dlaždici Experian.</span><span class="sxs-lookup"><span data-stu-id="3cdfb-115">Select **Enrich my data** on the Experian tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="3cdfb-116">![Dlaždica Experian](media/experian-tile.png "Dlaždica Experian")</span><span class="sxs-lookup"><span data-stu-id="3cdfb-116">![Experian tile](media/experian-tile.png "Experian tile")</span></span>
   > 

1. <span data-ttu-id="3cdfb-117">V rozbaľovacej ponuke stlačte možnosť [pripojenie](connections.md).</span><span class="sxs-lookup"><span data-stu-id="3cdfb-117">Select a [connection](connections.md) from the drop-down.</span></span> <span data-ttu-id="3cdfb-118">Ak nie je k dispozícii pripojenie, kontaktujte správcu.</span><span class="sxs-lookup"><span data-stu-id="3cdfb-118">Contact an administrator if no connection is available.</span></span> <span data-ttu-id="3cdfb-119">Ak ste správca, pripojenie môžete vytvoriť výberom možnosti **Pridať pripojenie** a v rozbaľovacej ponuke Experian stlačte možnosť Vlastný import SFTP.</span><span class="sxs-lookup"><span data-stu-id="3cdfb-119">If you are an administrator, you can create a connection by selecting **Add connection** and choosing Experian from the drop-down.</span></span> 

1. <span data-ttu-id="3cdfb-120">Vyberte **Pripojiť sa k Experian** na potvrdenie zvoleného spojenia.</span><span class="sxs-lookup"><span data-stu-id="3cdfb-120">Select **Connect to Experian** to confirm the connection selection.</span></span>

1.  <span data-ttu-id="3cdfb-121">Stlačte možnosť **Ďalej** a vyberte **Množina údajov o zákazníkoch** na obohatenie o demografické údaje z Experian.</span><span class="sxs-lookup"><span data-stu-id="3cdfb-121">Select **Next** and choose the **Customer data set** you want to enrich with demographics data from Experian.</span></span> <span data-ttu-id="3cdfb-122">Môžete zvoliť entitu **Zákazník**, aby ste obohatili všetky svoje zákaznícke profily, alebo vyberte entitu segmentu, aby ste obohatili iba profily zákazníkov obsiahnuté v danom segmente.</span><span class="sxs-lookup"><span data-stu-id="3cdfb-122">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-Experian-configuration-customer-data-set.png" alt-text="Snímka obrazovky pri výbere množiny údajov o zákazníkoch.":::

1. <span data-ttu-id="3cdfb-124">Stlačte možnosť **Ďalej** a definujte, ktorý typ polí z vašich zjednotených profilov sa má použiť na vyhľadanie zodpovedajúcich demografických údajov z Experian.</span><span class="sxs-lookup"><span data-stu-id="3cdfb-124">Select **Next** and define which type of fields from your unified profiles should be used to look for matching demographics data from Experian.</span></span> <span data-ttu-id="3cdfb-125">Aspoň jedno z polí **Meno a adresa**, **Telefón** alebo **Email** je požadované.</span><span class="sxs-lookup"><span data-stu-id="3cdfb-125">At least one of the fields **Name and address**, **Phone**, or **Email** is required.</span></span> <span data-ttu-id="3cdfb-126">Pre vyššiu presnosť zhody je možné pridať až dve ďalšie polia.</span><span class="sxs-lookup"><span data-stu-id="3cdfb-126">For a higher match accuracy, up to two other fields can be added.</span></span> <span data-ttu-id="3cdfb-127">Tento výber ovplyvní mapovacie polia, ku ktorým máte prístup v ďalšom kroku.</span><span class="sxs-lookup"><span data-stu-id="3cdfb-127">This selection will affect the mapping fields you have access to in the next step.</span></span>

    > [!TIP]
    > <span data-ttu-id="3cdfb-128">Viac kľúčových identifikačných atribútov zaslaných spoločnosti Experian pravdepodobne prinesie vyššiu mieru zhody.</span><span class="sxs-lookup"><span data-stu-id="3cdfb-128">More key identifier attributes sent to Experian likely yield a higher match rate.</span></span>

1. <span data-ttu-id="3cdfb-129">Stlačte možnosť **Ďalej** na spustenie mapovania poľa.</span><span class="sxs-lookup"><span data-stu-id="3cdfb-129">Select **Next** to start the field mapping.</span></span>

1. <span data-ttu-id="3cdfb-130">Definujte, ktorý typ polí z vašich zjednotených profilov sa má použiť na vyhľadanie zodpovedajúcich demografických údajov z Experian.</span><span class="sxs-lookup"><span data-stu-id="3cdfb-130">Define which fields from your unified profiles should be used to look for matching demographics data from Experian.</span></span> <span data-ttu-id="3cdfb-131">Požadované polia sú označené.</span><span class="sxs-lookup"><span data-stu-id="3cdfb-131">Required fields are marked.</span></span>

1. <span data-ttu-id="3cdfb-132">Uveďte názov obohatenia a názov výstupnej entity.</span><span class="sxs-lookup"><span data-stu-id="3cdfb-132">Provide a name for the enrichment and a name for the output entity.</span></span>

1. <span data-ttu-id="3cdfb-133">Stlačte možnosť **Uložiť obohatenie** po preskúmaní vašich možností.</span><span class="sxs-lookup"><span data-stu-id="3cdfb-133">Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="configure-the-connection-for-experian"></a><span data-ttu-id="3cdfb-134">Nakonfigurujte pripojenie pre Experian</span><span class="sxs-lookup"><span data-stu-id="3cdfb-134">Configure the connection for Experian</span></span> 

<span data-ttu-id="3cdfb-135">Na konfiguráciu pripojení musíte byť administrátor.</span><span class="sxs-lookup"><span data-stu-id="3cdfb-135">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="3cdfb-136">Stlačte možnosť **Pridať pripojenie** pri konfigurácii obohatenia *alebo* prejdite na **Správca** > **Pripojenia** a vyberte **Nastaviť** na dlaždici Experian.</span><span class="sxs-lookup"><span data-stu-id="3cdfb-136">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the Experian tile.</span></span>

1. <span data-ttu-id="3cdfb-137">Vyberte položku **Začíname**.</span><span class="sxs-lookup"><span data-stu-id="3cdfb-137">Select **Get Started**.</span></span>

1. <span data-ttu-id="3cdfb-138">Zadajte názov pripojenia do boxu **Zobrazovaný názov**.</span><span class="sxs-lookup"><span data-stu-id="3cdfb-138">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="3cdfb-139">Zadajte platné ID používateľa, ID strany a číslo modelu pre váš účet Experian Secure Transport.</span><span class="sxs-lookup"><span data-stu-id="3cdfb-139">Enter valid User ID, Party ID, and Model Number for your Experian Secure Transport account.</span></span>

1. <span data-ttu-id="3cdfb-140">Skontrolujte a poskytnite svoj súhlas pre **Ochrana osobných údajov a dodržiavanie súladu s nariadeniami** označením začiarkavacieho políčka **Súhlasím**.</span><span class="sxs-lookup"><span data-stu-id="3cdfb-140">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox</span></span>

1. <span data-ttu-id="3cdfb-141">Stlačte **Overiť** na overenie konfigurácie.</span><span class="sxs-lookup"><span data-stu-id="3cdfb-141">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="3cdfb-142">Po dokončení overenia stlačte možnosť **Uložiť**.</span><span class="sxs-lookup"><span data-stu-id="3cdfb-142">After completing the verification, select **Save**.</span></span>
   
   :::image type="content" source="media/enrichment-Experian-connection.png" alt-text="Konfiguračná tabla pripojenia Experian":::

## <a name="enrichment-results"></a><span data-ttu-id="3cdfb-144">Výsledky obohatenia</span><span class="sxs-lookup"><span data-stu-id="3cdfb-144">Enrichment results</span></span>

<span data-ttu-id="3cdfb-145">Proces obohatenia spustíte výberom položky **Spustiť** z panela príkazov.</span><span class="sxs-lookup"><span data-stu-id="3cdfb-145">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="3cdfb-146">Môžete tiež nechať systém, aby obohatenie spustil automaticky ako súčasť a [plánovaného obnovenia](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="3cdfb-146">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="3cdfb-147">Doba spracovania bude závisieť od veľkosti vašich zákazníckych údajov a procesov obohacovania nastavených pre váš účet spoločnosťou Experian.</span><span class="sxs-lookup"><span data-stu-id="3cdfb-147">The processing time will depend on the size of your customer data and the enrichment processes set up for your account by Experian.</span></span>

<span data-ttu-id="3cdfb-148">Po dokončení procesu obohacovania môžete skontrolovať údaje o nových obohatených zákazníckych profiloch v časti **Moje obohatenia**.</span><span class="sxs-lookup"><span data-stu-id="3cdfb-148">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="3cdfb-149">Ďalej nájdete čas poslednej aktualizácie a počet obohatených profilov.</span><span class="sxs-lookup"><span data-stu-id="3cdfb-149">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="3cdfb-150">Môžete získať podrobné zobrazenie každého obohateného profilu výberom **Zobraziť obohatené údaje**.</span><span class="sxs-lookup"><span data-stu-id="3cdfb-150">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="3cdfb-151">Ďalšie kroky</span><span class="sxs-lookup"><span data-stu-id="3cdfb-151">Next steps</span></span>

<span data-ttu-id="3cdfb-152">Stavajte na svojich obohatených údajoch o zákazníkoch.</span><span class="sxs-lookup"><span data-stu-id="3cdfb-152">Build on top of your enriched customer data.</span></span> <span data-ttu-id="3cdfb-153">Vytvárajte [segmenty](segments.md), [miery](measures.md) a dokonca [exportujte údaje](export-destinations.md) na poskytovanie prispôsobenej používateľskej skúsenosti svojim zákazníkom.</span><span class="sxs-lookup"><span data-stu-id="3cdfb-153">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="3cdfb-154">Ochrana osobných údajov a dodržiavanie súladu s nariadeniami</span><span class="sxs-lookup"><span data-stu-id="3cdfb-154">Data privacy and compliance</span></span>

<span data-ttu-id="3cdfb-155">Keď povolíte prenos údajov spoločnosti Experian v službe Dynamics 365 Customer Insights, povoľujete tým prenos údajov mimo hranice súladu so službou Dynamics 365 Customer Insights vrátane potenciálne citlivých údajov, ako sú napríklad osobné údaje.</span><span class="sxs-lookup"><span data-stu-id="3cdfb-155">When you enable Dynamics 365 Customer Insights to transmit data to Experian, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="3cdfb-156">Spoločnosť Microsoft prenesie tieto údaje na váš pokyn, ale vy ste zodpovední za zabezpečenie toho, aby spoločnosť Experian plnila všetky prípadné povinnosti týkajúce sa ochrany vašich osobných údajov alebo zabezpečenia.</span><span class="sxs-lookup"><span data-stu-id="3cdfb-156">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Experian meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="3cdfb-157">Ďalšie informácie nájdete vo [vyhlásení o ochrane súkromia spoločnosti Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="3cdfb-157">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="3cdfb-158">Váš správca služby Dynamics 365 Customer Insights môžete kedykoľvek prestať používať odstránením tohto obohatenia.</span><span class="sxs-lookup"><span data-stu-id="3cdfb-158">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
