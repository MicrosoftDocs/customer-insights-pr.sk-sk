---
title: Export údajov služby Customer Insights do AdRoll
description: Zistite, ako môžete nakonfigurovať pripojenie k AdRoll.
ms.date: 02/15/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6fedd549c2e7de362f36e3fb23d363200bb92a04
ms.sourcegitcommit: d24e52150fe5a4fab45128e12d6a03637771d9b9
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 03/19/2021
ms.locfileid: "5697093"
---
# <a name="connector-for-adroll-preview"></a><span data-ttu-id="3b019-103">Konektor pre AdRoll (ukážka)</span><span class="sxs-lookup"><span data-stu-id="3b019-103">Connector for AdRoll (preview)</span></span>

<span data-ttu-id="3b019-104">Exportujte segmenty zjednotených profilov zákazníkov do služby AdRoll a použite ich na reklamu.</span><span class="sxs-lookup"><span data-stu-id="3b019-104">Export segments of unified customer profiles to AdRoll and use them for advertising.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="3b019-105">Predpoklady</span><span class="sxs-lookup"><span data-stu-id="3b019-105">Prerequisites</span></span>

-   <span data-ttu-id="3b019-106">Máte [účet AdRoll](https://www.adroll.com/) a zodpovedajúce poverenia správcu.</span><span class="sxs-lookup"><span data-stu-id="3b019-106">You have an [AdRoll account](https://www.adroll.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="3b019-107">Máte [konfigurované segmenty](segments.md) v prehľadoch cieľových skupín.</span><span class="sxs-lookup"><span data-stu-id="3b019-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="3b019-108">Zjednotené profily zákazníkov v exportovaných segmentoch obsahujú pole predstavujúce e-mailovú adresu.</span><span class="sxs-lookup"><span data-stu-id="3b019-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-adroll"></a><span data-ttu-id="3b019-109">Pripojenie k službe AdRoll</span><span class="sxs-lookup"><span data-stu-id="3b019-109">Connect to AdRoll</span></span>

1. <span data-ttu-id="3b019-110">Prejdite do ponuky **Správca** > **Ciele exportu**.</span><span class="sxs-lookup"><span data-stu-id="3b019-110">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="3b019-111">V časti **AdRoll** vyberte položku **Nastaviť**.</span><span class="sxs-lookup"><span data-stu-id="3b019-111">Under **AdRoll**, select **Set up**.</span></span>

1. <span data-ttu-id="3b019-112">Do poľa **Zobrazovaný názov** zadajte rozpoznateľný názov cieľa exportu.</span><span class="sxs-lookup"><span data-stu-id="3b019-112">Give your export destination a recognizable name in the **Display name** field.</span></span>

   :::image type="content" source="media/AdRoll_config.PNG" alt-text="Konfiguračná tabla na pripojenie služby AdRoll.":::

1. <span data-ttu-id="3b019-114">Vyberte **Súhlasím** na potvrdenie **Ochrany osobných údajov a dodržiavanie súladu s nariadeniami**.</span><span class="sxs-lookup"><span data-stu-id="3b019-114">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="3b019-115">Vyberte položku **Pripojiť** na inicializáciu pripojenia k AdRoll.</span><span class="sxs-lookup"><span data-stu-id="3b019-115">Select **Connect** to initialize the connection to AdRoll.</span></span>

1. <span data-ttu-id="3b019-116">Vyberte položku **Overenie pomocou AdRoll** a poskytnite svoje poverenia správcu pre AdRoll.</span><span class="sxs-lookup"><span data-stu-id="3b019-116">Select **Authenticate with AdRoll** and provide your admin credentials for AdRoll.</span></span> 

1. <span data-ttu-id="3b019-117">Vyberte položku **Pridať samého seba ako používateľa exportu** a uveďte svoje poverenia pre Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="3b019-117">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="3b019-118">Zadajte svoje **ID inzerenta AdRoll** [AdRoll inzerovateľný](https://help.adroll.com/hc/en-us/articles/212011838-Advertiser-Profiles).</span><span class="sxs-lookup"><span data-stu-id="3b019-118">Enter your **AdRoll Advertiser ID** [AdRoll Advertisable](https://help.adroll.com/hc/en-us/articles/212011838-Advertiser-Profiles).</span></span>

1. <span data-ttu-id="3b019-119">Vyberte **Ďalej** a nakonfigurujte export.</span><span class="sxs-lookup"><span data-stu-id="3b019-119">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="3b019-120">Nakonfigurujte konektor</span><span class="sxs-lookup"><span data-stu-id="3b019-120">Configure the connector</span></span>

1. <span data-ttu-id="3b019-121">V sekcii **Párovanie údajov** v poli **E-mail** do svojho zjednoteného profilu zákazníka vyberte pole, ktoré predstavuje e-mailovú adresu zákazníka.</span><span class="sxs-lookup"><span data-stu-id="3b019-121">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="3b019-122">Je potrebné exportovať segmenty do služby AdRoll.</span><span class="sxs-lookup"><span data-stu-id="3b019-122">It's required to export segments to AdRoll.</span></span>

1. <span data-ttu-id="3b019-123">Vyberte segmenty, ktoré chcete exportovať.</span><span class="sxs-lookup"><span data-stu-id="3b019-123">Select the segments you want to export.</span></span> <span data-ttu-id="3b019-124">Vyberte segment s najmenej 100 členmi.</span><span class="sxs-lookup"><span data-stu-id="3b019-124">Select a segment with a least 100 members.</span></span> <span data-ttu-id="3b019-125">Menšie segmenty nemôžete exportovať.</span><span class="sxs-lookup"><span data-stu-id="3b019-125">You can't export smaller segments.</span></span> <span data-ttu-id="3b019-126">Maximálna veľkosť segmentu na export je 250 000 členov na export.</span><span class="sxs-lookup"><span data-stu-id="3b019-126">Additionally the maximum size of a segment to export is 250'000 members per export.</span></span> 

1. <span data-ttu-id="3b019-127">Vyberte položku **Uložiť**.</span><span class="sxs-lookup"><span data-stu-id="3b019-127">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="3b019-128">Export údajov</span><span class="sxs-lookup"><span data-stu-id="3b019-128">Export the data</span></span>

<span data-ttu-id="3b019-129">Môžete [exportovať údaje na vyžiadanie](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="3b019-129">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="3b019-130">Export sa spustí aj pri každej [plánovanej obnove](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="3b019-130">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="3b019-131">Známe obmedzenia</span><span class="sxs-lookup"><span data-stu-id="3b019-131">Known limitations</span></span>

- <span data-ttu-id="3b019-132">Do služby AdRoll môžete exportovať spolu až 250 000 profilov na export.</span><span class="sxs-lookup"><span data-stu-id="3b019-132">You can export up to 250'000 profiles in per export to AdRoll.</span></span>
- <span data-ttu-id="3b019-133">Do služby AdRoll nemôžete exportovať segmenty s menej ako 100 profilmi.</span><span class="sxs-lookup"><span data-stu-id="3b019-133">You can't export segments with fewer than 100 profiles to AdRoll.</span></span> 
- <span data-ttu-id="3b019-134">Export do AdRoll je obmedzený na segmenty.</span><span class="sxs-lookup"><span data-stu-id="3b019-134">Exporting to AdRoll is limited to segments.</span></span>
- <span data-ttu-id="3b019-135">Export až 250 000 profilov do služby AdRoll môže trvať až 10 minút.</span><span class="sxs-lookup"><span data-stu-id="3b019-135">Exporting up to 250'000 profiles to AdRoll can take up to 10 minutes to complete.</span></span> 
- <span data-ttu-id="3b019-136">Počet profilov, ktoré môžete exportovať do AdRoll, závisí a je obmedzený vašou zmluvou so spoločnosťou AdRoll.</span><span class="sxs-lookup"><span data-stu-id="3b019-136">The number of profiles that you can export to AdRoll is dependent and limited on your contract with AdRoll.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="3b019-137">Ochrana osobných údajov a dodržiavanie súladu s nariadeniami</span><span class="sxs-lookup"><span data-stu-id="3b019-137">Data privacy and compliance</span></span>

<span data-ttu-id="3b019-138">Keď povolíte prenos údajov do AdRoll v službe Dynamics 365 Customer Insights, povoľujete tým prenos údajov mimo hranice súladu so službou Dynamics 365 Customer Insights vrátane potenciálne citlivých údajov, ako sú napríklad osobné údaje.</span><span class="sxs-lookup"><span data-stu-id="3b019-138">When you enable Dynamics 365 Customer Insights to transmit data to AdRoll, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="3b019-139">Spoločnosť Microsoft prenesie tieto údaje na váš pokyn, ale vy ste zodpovední za zabezpečenie toho, aby AdRoll plnila všetky prípadné povinnosti týkajúce sa ochrany vašich osobných údajov alebo zabezpečenia.</span><span class="sxs-lookup"><span data-stu-id="3b019-139">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that AdRoll meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="3b019-140">Ďalšie informácie nájdete vo [vyhlásení o ochrane súkromia spoločnosti Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="3b019-140">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="3b019-141">Váš správca služby Dynamics 365 Customer Insights môže túto funkciu kedykoľvek prestať používať odstránením tohto cieľového umiestnenia exportu.</span><span class="sxs-lookup"><span data-stu-id="3b019-141">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
