---
title: Obohatenie pomocou obohatenia tretej strany Experian
description: Všeobecné informácie o obohatení pomocou obohatenia tretej stranou Experian.
ms.date: 12/10/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: baf3cc58a233b70c48fb94ac4a543d162f91bdd1
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269579"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a><span data-ttu-id="7cd1a-103">Obohatenie profilov zákazníkov o demografické údaje od spoločnosti Experian (ukážka)</span><span class="sxs-lookup"><span data-stu-id="7cd1a-103">Enrich customer profiles with demographics from Experian (preview)</span></span>

<span data-ttu-id="7cd1a-104">Experian je svetový líder v oblasti marketingových služieb a zisťovania kreditu spotrebiteľov a firiem.</span><span class="sxs-lookup"><span data-stu-id="7cd1a-104">Experian is a global leader in consumer and business credit reporting and marketing services.</span></span> <span data-ttu-id="7cd1a-105">So službami obohacovania údajov od spoločnosti Experian môžete hlbšie porozumieť svojim zákazníkom obohatením profilov svojich zákazníkov o demografické údaje, ako sú veľkosť domácnosti, príjem a ďalšie.</span><span class="sxs-lookup"><span data-stu-id="7cd1a-105">With Experian’s data enrichment services, you can build a deeper understanding of your customers by enriching your customer profiles with demographic data such as household size, income, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="7cd1a-106">Predpoklady</span><span class="sxs-lookup"><span data-stu-id="7cd1a-106">Prerequisites</span></span>

<span data-ttu-id="7cd1a-107">Ak chcete nakonfigurovať Experian, musia byť splnené nasledujúce predpoklady:</span><span class="sxs-lookup"><span data-stu-id="7cd1a-107">To configure Experian, the following prerequisites must be met:</span></span>

- <span data-ttu-id="7cd1a-108">Máte aktívne predplatné Experian.</span><span class="sxs-lookup"><span data-stu-id="7cd1a-108">You have an active Experian subscription.</span></span> <span data-ttu-id="7cd1a-109">Ak chcete získať predplatné, [kontaktujte Experian](https://www.experian.com/marketing-services/contact) priamo.</span><span class="sxs-lookup"><span data-stu-id="7cd1a-109">To get a subscription, [contact Experian](https://www.experian.com/marketing-services/contact) directly.</span></span> <span data-ttu-id="7cd1a-110">[Ďalšie informácie o obohacovaní údajov Experian](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span><span class="sxs-lookup"><span data-stu-id="7cd1a-110">[Learn more about Experian Data Enrichment](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span></span>
- <span data-ttu-id="7cd1a-111">Máte ID používateľa, ID strany a číslo modely pre svoj účet Secure Transport (ST) s podporou SSH, ktoré pre vás vytvorila spoločnosť Experian.</span><span class="sxs-lookup"><span data-stu-id="7cd1a-111">You have the User ID, Party ID, and Model Number for your SSH-enabled Secure Transport (ST) account that Experian created for you.</span></span>
- <span data-ttu-id="7cd1a-112">Máte povolenia roly [Správca](permissions.md#administrator) prehľadoch cieľových skupín.</span><span class="sxs-lookup"><span data-stu-id="7cd1a-112">You have [Administrator](permissions.md#administrator) permissions in audience insights.</span></span>

## <a name="configuration"></a><span data-ttu-id="7cd1a-113">Konfigurácia</span><span class="sxs-lookup"><span data-stu-id="7cd1a-113">Configuration</span></span>

1. <span data-ttu-id="7cd1a-114">Prejdite na **Údaje** > **Obohatenie** a vyberte kartu **Objavovať**.</span><span class="sxs-lookup"><span data-stu-id="7cd1a-114">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="7cd1a-115">Vyberte **Obohatiť moje údaje** na dlaždici Experian.</span><span class="sxs-lookup"><span data-stu-id="7cd1a-115">Select **Enrich my data** on the Experian tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="7cd1a-116">![Dlaždica Experian](media/experian-tile.png "Dlaždica Experian")</span><span class="sxs-lookup"><span data-stu-id="7cd1a-116">![Experian tile](media/experian-tile.png "Experian tile")</span></span>

1. <span data-ttu-id="7cd1a-117">Vyberte **Začíname** a zadajte ID používateľa, ID strany a Číslo modelu pre váš účet Secure Transport spoločnosti Experian.</span><span class="sxs-lookup"><span data-stu-id="7cd1a-117">Select **Get started** and enter the User ID, Party ID, and Model Number for your Experian Secure Transport account.</span></span> <span data-ttu-id="7cd1a-118">Skontrolujte a poskytnite svoj súhlas pre **Ochranu osobných údajov a dodržiavanie súladu s nariadeniami** výberom začiarkavacieho políčka **Súhlasím**.</span><span class="sxs-lookup"><span data-stu-id="7cd1a-118">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span> <span data-ttu-id="7cd1a-119">Všetky zadané údaje potvrďte výberom položky **Použiť**.</span><span class="sxs-lookup"><span data-stu-id="7cd1a-119">Confirm all inputs by selecting **Apply**.</span></span>

## <a name="map-your-fields"></a><span data-ttu-id="7cd1a-120">Priraďte svoje polia</span><span class="sxs-lookup"><span data-stu-id="7cd1a-120">Map your fields</span></span>

1.  <span data-ttu-id="7cd1a-121">Vyberte **Pridať údaje** a vyberte **Množinu zákazníckych údajov**, ktorú chcete obohatiť o demografické údaje od spoločnosti Experian.</span><span class="sxs-lookup"><span data-stu-id="7cd1a-121">Select **Add data** and choose the **Customer data set** you want to enrich with demographics data from Experian.</span></span> <span data-ttu-id="7cd1a-122">Môžete zvoliť entitu **Zákazník**, aby ste obohatili všetky svoje zákaznícke profily, alebo vyberte entitu segmentu, aby ste obohatili iba profily zákazníkov obsiahnuté v danom segmente.</span><span class="sxs-lookup"><span data-stu-id="7cd1a-122">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

1. <span data-ttu-id="7cd1a-123">Vyberte svoje kľúčové identifikátory spomedzi **Meno a adresa**,**E-mail** alebo **Telefón**, ktoré odošlete spoločnosti Experian na zistenie identity.</span><span class="sxs-lookup"><span data-stu-id="7cd1a-123">Select your key identifiers from **Name and Address**, **E-mail**, or **Phone** to send to Experian for identity resolution.</span></span>

   > [!TIP]
   > <span data-ttu-id="7cd1a-124">Viac kľúčových identifikačných atribútov zaslaných spoločnosti Experian pravdepodobne prinesie vyššiu mieru zhody.</span><span class="sxs-lookup"><span data-stu-id="7cd1a-124">More key identifier attributes sent to Experian likely yield a higher match rate.</span></span>

1. <span data-ttu-id="7cd1a-125">Vyberte **Ďalej** a mapujte zodpovedajúce atribúty z vašej zjednotenej entity zákazníka pre vybrané polia kľúčového identifikátora.</span><span class="sxs-lookup"><span data-stu-id="7cd1a-125">Select **Next** and map the corresponding attributes from your unified customer entity for the selected key identifier fields.</span></span>

1. <span data-ttu-id="7cd1a-126">Vyberte **Pridať atribút** na mapovanie akýchkoľvek ďalších atribútov, ktoré by ste chceli poslať spoločnosti Experian.</span><span class="sxs-lookup"><span data-stu-id="7cd1a-126">Select **Add attribute** to map any additional attributes you would like to send to Experian.</span></span>

1.  <span data-ttu-id="7cd1a-127">Vyberte **Uložiť** na dokončenie mapovania polí.</span><span class="sxs-lookup"><span data-stu-id="7cd1a-127">Select **Save** to complete the field mapping.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="7cd1a-128">![Mapovanie polí Experian](media/experian-field-mapping.png "Mapovanie polí Experian")</span><span class="sxs-lookup"><span data-stu-id="7cd1a-128">![Experian field mapping](media/experian-field-mapping.png "Experian field mapping")</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="7cd1a-129">Výsledky obohatenia</span><span class="sxs-lookup"><span data-stu-id="7cd1a-129">Enrichment results</span></span>

<span data-ttu-id="7cd1a-130">Proces obohatenia spustíte výberom položky **Spustiť** z panela príkazov.</span><span class="sxs-lookup"><span data-stu-id="7cd1a-130">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="7cd1a-131">Môžete tiež nechať systém, aby obohatenie spustil automaticky ako súčasť a [plánovaného obnovenia](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="7cd1a-131">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="7cd1a-132">Doba spracovania bude závisieť od veľkosti vašich zákazníckych údajov a procesov obohacovania nastavených pre váš účet spoločnosťou Experian.</span><span class="sxs-lookup"><span data-stu-id="7cd1a-132">The processing time will depend on the size of your customer data and the enrichment processes set up for your account by Experian.</span></span>

<span data-ttu-id="7cd1a-133">Po dokončení procesu obohacovania môžete skontrolovať údaje o nových obohatených zákazníckych profiloch v časti **Moje obohatenia**.</span><span class="sxs-lookup"><span data-stu-id="7cd1a-133">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="7cd1a-134">Ďalej nájdete čas poslednej aktualizácie a počet obohatených profilov.</span><span class="sxs-lookup"><span data-stu-id="7cd1a-134">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="7cd1a-135">Môžete získať podrobné zobrazenie každého obohateného profilu výberom **Zobraziť obohatené údaje**.</span><span class="sxs-lookup"><span data-stu-id="7cd1a-135">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="7cd1a-136">Ďalšie kroky</span><span class="sxs-lookup"><span data-stu-id="7cd1a-136">Next steps</span></span>

<span data-ttu-id="7cd1a-137">Stavajte na svojich obohatených údajoch o zákazníkoch.</span><span class="sxs-lookup"><span data-stu-id="7cd1a-137">Build on top of your enriched customer data.</span></span> <span data-ttu-id="7cd1a-138">Vytvárajte [segmenty](segments.md), [miery](measures.md) a dokonca [exportujte údaje](export-destinations.md) na poskytovanie prispôsobenej používateľskej skúsenosti svojim zákazníkom.</span><span class="sxs-lookup"><span data-stu-id="7cd1a-138">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="7cd1a-139">Ochrana osobných údajov a dodržiavanie súladu s nariadeniami</span><span class="sxs-lookup"><span data-stu-id="7cd1a-139">Data privacy and compliance</span></span>

<span data-ttu-id="7cd1a-140">Keď povolíte prenos údajov spoločnosti Experian v službe Dynamics 365 Customer Insights, povoľujete tým prenos údajov mimo hranice súladu so službou Dynamics 365 Customer Insights vrátane potenciálne citlivých údajov, ako sú napríklad osobné údaje.</span><span class="sxs-lookup"><span data-stu-id="7cd1a-140">When you enable Dynamics 365 Customer Insights to transmit data to Experian, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="7cd1a-141">Spoločnosť Microsoft prenesie tieto údaje na váš pokyn, ale vy ste zodpovední za zabezpečenie toho, aby spoločnosť Experian plnila všetky prípadné povinnosti týkajúce sa ochrany vašich osobných údajov alebo zabezpečenia.</span><span class="sxs-lookup"><span data-stu-id="7cd1a-141">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Experian meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="7cd1a-142">Ďalšie informácie nájdete vo [vyhlásení o ochrane súkromia spoločnosti Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="7cd1a-142">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="7cd1a-143">Váš správca služby Dynamics 365 Customer Insights môžete kedykoľvek prestať používať odstránením tohto obohatenia.</span><span class="sxs-lookup"><span data-stu-id="7cd1a-143">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]