---
title: Obohatenie profilov spoločností pomocou obohatenia tretej strany Leadspace
description: Všeobecné informácie o obohatení pomocou obohatenia tretej stranou Leadspace.
ms.date: 11/24/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 41c56aece043c2d7658fd2655713e1e98775edec
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597668"
---
# <a name="enrichment-of-company-profiles-with-leadspace-preview"></a><span data-ttu-id="6d519-103">Obohatenie profilov spoločnosti pomocou Leadspace (náhľad)</span><span class="sxs-lookup"><span data-stu-id="6d519-103">Enrichment of company profiles with Leadspace (preview)</span></span>

<span data-ttu-id="6d519-104">Leadspace je spoločnosť zaoberajúca dátovou vedou, ktorá poskytuje platformu B2B Customer Data.</span><span class="sxs-lookup"><span data-stu-id="6d519-104">Leadspace is a data science company that provides a B2B Customer Data Platform.</span></span> <span data-ttu-id="6d519-105">Umožňuje zákazníkom so zjednotenými zákazníckymi profilmi pre spoločnosti obohacovať svoje údaje.</span><span class="sxs-lookup"><span data-stu-id="6d519-105">It enables customers with unified customer profiles for companies to enrich their data.</span></span> <span data-ttu-id="6d519-106">Obohatenia zahŕňajú ďalšie atribúty, ako napríklad veľkosť, umiestnenie, odvetvie spoločnosti a ďalšie.</span><span class="sxs-lookup"><span data-stu-id="6d519-106">Enrichments include additional attributes such as company size, location, industry, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="6d519-107">Predpoklady</span><span class="sxs-lookup"><span data-stu-id="6d519-107">Prerequisites</span></span>

<span data-ttu-id="6d519-108">Na konfiguráciu Leadspace musia byť splnené nasledujúce predpoklady:</span><span class="sxs-lookup"><span data-stu-id="6d519-108">To configure Leadspace, the following prerequisites must be met:</span></span>

- <span data-ttu-id="6d519-109">Máte aktívnu licenciu pre Leadspace a „večný kľúč“ (označovaný ako **token pre Leadspace**).</span><span class="sxs-lookup"><span data-stu-id="6d519-109">You have an active Leadspace license and the “perpetual key” (referred to as **Leadspace token**).</span></span> <span data-ttu-id="6d519-110">Kontaktujte priamo [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) pre podrobnosti o ich produkte.</span><span class="sxs-lookup"><span data-stu-id="6d519-110">Contact directly [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) for details about their product.</span></span>
- <span data-ttu-id="6d519-111">Máte povolenia roly [Správca](permissions.md#administrator).</span><span class="sxs-lookup"><span data-stu-id="6d519-111">You have [Administrator](permissions.md#administrator) permissions.</span></span>
- <span data-ttu-id="6d519-112">Máte [zjednotené profily zákazníkov](customer-profiles.md) pre spoločnosti.</span><span class="sxs-lookup"><span data-stu-id="6d519-112">You have [unified customer profiles](customer-profiles.md) for companies.</span></span>

## <a name="configuration"></a><span data-ttu-id="6d519-113">Konfigurácia</span><span class="sxs-lookup"><span data-stu-id="6d519-113">Configuration</span></span>

1. <span data-ttu-id="6d519-114">V prehľadoch cieľových skupín prejdite na **Údaje** > **Obohatenie**.</span><span class="sxs-lookup"><span data-stu-id="6d519-114">In audience insights, go to **Data** > **Enrichment**.</span></span>

1. <span data-ttu-id="6d519-115">Vyberte **Obohatiť moje údaje** na dlaždici Leadspace.</span><span class="sxs-lookup"><span data-stu-id="6d519-115">Select **Enrich my data** on the Leadspace tile.</span></span>

   :::image type="content" source="media/leadspace-tile.png" alt-text="Snímka obrazovky dlaždice Leadspace.":::

1. <span data-ttu-id="6d519-117">Vyberte položku **Začíname** a potom zadajte aktívny **token pre Leadspace** (večný kľúč).</span><span class="sxs-lookup"><span data-stu-id="6d519-117">Select **Get Started** and then enter an active **Leadspace token** (perpetual key).</span></span> <span data-ttu-id="6d519-118">Skontrolujte a poskytnite svoj súhlas pre **Ochranu osobných údajov a dodržiavanie súladu s nariadeniami** výberom začiarkavacieho políčka **Súhlasím**.</span><span class="sxs-lookup"><span data-stu-id="6d519-118">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span> <span data-ttu-id="6d519-119">Potvrďte obidva vstupy výberom položky **Pripojiť k Leadspace**.</span><span class="sxs-lookup"><span data-stu-id="6d519-119">Confirm both inputs by selecting **Connect to Leadspace**.</span></span>

1. <span data-ttu-id="6d519-120">Vyberte **Mapovanie údajov** a vyberte množinu údajov, ktorú chcete obohatiť o údaje spoločnosti z programu Leadspace.</span><span class="sxs-lookup"><span data-stu-id="6d519-120">Select **Map data** and choose the data set you want to enrich with company data from Leadspace.</span></span> <span data-ttu-id="6d519-121">Môžete zvoliť entitu *Zákazník*, aby ste obohatili všetky svoje zákaznícke profily, alebo vyberte entitu segmentu, aby ste obohatili iba profily zákazníkov obsiahnuté v danom segmente.</span><span class="sxs-lookup"><span data-stu-id="6d519-121">You can select the *Customer* entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

   :::image type="content" source="media/enrichment-leadspace-select-segment.png" alt-text="Vyberte si medzi profilom zákazníka a obohatením segmentu.":::

1. <span data-ttu-id="6d519-123">Kliknite na **Ďalej** a definujte, ktoré polia z vašich zjednotených profilov sa majú použiť na vyhľadanie zodpovedajúcich údajov spoločnosti z Leadspace.</span><span class="sxs-lookup"><span data-stu-id="6d519-123">Click **Next** and define which fields from your unified profiles should be used to look for matching company data from Leadspace.</span></span> <span data-ttu-id="6d519-124">Pole **Názov spoločnosti** je povinné.</span><span class="sxs-lookup"><span data-stu-id="6d519-124">The **Name of company** field is required.</span></span> <span data-ttu-id="6d519-125">Pre vyššiu presnosť zhody možno pridať až dve ďalšie polia, **Webová lokalita spoločnosti** a **Sídlo spoločnosti**.</span><span class="sxs-lookup"><span data-stu-id="6d519-125">For a higher match accuracy, up to two other fields, **Company website** and **Company location**, can be added.</span></span>

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="Tabla mapovania polí Leadspace.":::
   
1. <span data-ttu-id="6d519-127">Výberom položky **Použiť** dokončíte mapovanie polí.</span><span class="sxs-lookup"><span data-stu-id="6d519-127">Select **Apply** to complete the field mapping.</span></span>

1. <span data-ttu-id="6d519-128">Vyberte **Spustiť** na obohatenie profilov spoločnosti.</span><span class="sxs-lookup"><span data-stu-id="6d519-128">Select **Run** to enrich the company profiles.</span></span> <span data-ttu-id="6d519-129">Dĺžka trvania obohacovania závisí od počtu zjednotených profilov zákazníkov.</span><span class="sxs-lookup"><span data-stu-id="6d519-129">How long an enrichment takes depends on the number of unified customer profiles.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="6d519-130">Výsledky obohatenia</span><span class="sxs-lookup"><span data-stu-id="6d519-130">Enrichment results</span></span>

<span data-ttu-id="6d519-131">Po aktualizácii obohatenia si môžete prezrieť novo obohatené údaje spoločnosti v časti [Moje obohatenia](enrichment-hub.md).</span><span class="sxs-lookup"><span data-stu-id="6d519-131">After refreshing the enrichment, you can review the newly enriched company data under [My enrichments](enrichment-hub.md).</span></span> <span data-ttu-id="6d519-132">Nájdete čas poslednej aktualizácie a počet obohatených profilov.</span><span class="sxs-lookup"><span data-stu-id="6d519-132">You can find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="6d519-133">Môžete získať podrobné zobrazenie každého obohateného profilu výberom **Zobraziť obohatené údaje**.</span><span class="sxs-lookup"><span data-stu-id="6d519-133">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

<span data-ttu-id="6d519-134">Ďalšie informácie sa dozviete v časti [API Leadspace](https://support.leadspace.com/hc/en-us/sections/201997649-API).</span><span class="sxs-lookup"><span data-stu-id="6d519-134">For more information, see [Leadspace APIs](https://support.leadspace.com/hc/en-us/sections/201997649-API).</span></span>

## <a name="next-steps"></a><span data-ttu-id="6d519-135">Ďalšie kroky</span><span class="sxs-lookup"><span data-stu-id="6d519-135">Next steps</span></span>

<span data-ttu-id="6d519-136">Stavajte na svojich obohatených údajoch o zákazníkoch.</span><span class="sxs-lookup"><span data-stu-id="6d519-136">Build on top of your enriched customer data.</span></span> <span data-ttu-id="6d519-137">Vytvárajte [segmenty](segments.md), [miery](measures.md) a dokonca [exportujte údaje](export-destinations.md) na poskytovanie prispôsobenej používateľskej skúsenosti svojim zákazníkom.</span><span class="sxs-lookup"><span data-stu-id="6d519-137">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="6d519-138">Ochrana osobných údajov a dodržiavanie súladu s nariadeniami</span><span class="sxs-lookup"><span data-stu-id="6d519-138">Data privacy and compliance</span></span>

<span data-ttu-id="6d519-139">Keď povolíte prenos údajov spoločnosti Leadspace v službe Dynamics 365 Customer Insights, povoľujete tým prenos údajov mimo hranice súladu so službou Dynamics 365 Customer Insights vrátane potenciálne citlivých údajov, ako sú napríklad osobné údaje.</span><span class="sxs-lookup"><span data-stu-id="6d519-139">When you enable Dynamics 365 Customer Insights to transmit data to Leadspace, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="6d519-140">Spoločnosť Microsoft prenesie tieto údaje na váš pokyn, ale vy ste zodpovední za zabezpečenie toho, aby spoločnosť Leadspace plnila všetky prípadné povinnosti týkajúce sa ochrany vašich osobných údajov alebo zabezpečenia.</span><span class="sxs-lookup"><span data-stu-id="6d519-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Leadspace meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="6d519-141">Ďalšie informácie nájdete vo [vyhlásení o ochrane súkromia spoločnosti Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="6d519-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="6d519-142">Váš správca služby Dynamics 365 Customer Insights môžete kedykoľvek prestať používať odstránením tohto obohatenia.</span><span class="sxs-lookup"><span data-stu-id="6d519-142">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]