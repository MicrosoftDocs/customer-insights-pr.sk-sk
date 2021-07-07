---
title: Export údajov služby Customer Insights do AdRoll
description: Zistite ako nakonfigurovať pripojenie a realizovať exportovanie do AdRoll.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 67bfa23d56b26ae592efa4d7197713664bb02623
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 06/24/2021
ms.locfileid: "6304853"
---
# <a name="export-segments-to-adroll-preview"></a><span data-ttu-id="9409e-103">Export segmentov do AdRoll (verzia Preview)</span><span class="sxs-lookup"><span data-stu-id="9409e-103">Export segments to AdRoll (preview)</span></span>

<span data-ttu-id="9409e-104">Exportujte segmenty zjednotených profilov zákazníkov do služby AdRoll a použite ich na reklamu.</span><span class="sxs-lookup"><span data-stu-id="9409e-104">Export segments of unified customer profiles to AdRoll and use them for advertising.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="9409e-105">Predpoklad na pripojenie</span><span class="sxs-lookup"><span data-stu-id="9409e-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="9409e-106">Máte [účet AdRoll](https://www.adroll.com/) a zodpovedajúce poverenia správcu.</span><span class="sxs-lookup"><span data-stu-id="9409e-106">You have an [AdRoll account](https://www.adroll.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="9409e-107">Máte [konfigurované segmenty](segments.md) v prehľadoch cieľových skupín.</span><span class="sxs-lookup"><span data-stu-id="9409e-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="9409e-108">Zjednotené profily zákazníkov v exportovaných segmentoch obsahujú pole predstavujúce e-mailovú adresu.</span><span class="sxs-lookup"><span data-stu-id="9409e-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="9409e-109">Známe obmedzenia</span><span class="sxs-lookup"><span data-stu-id="9409e-109">Known limitations</span></span>

- <span data-ttu-id="9409e-110">Do AdRoll môžete exportovať až 250 000 profilov súčasne.</span><span class="sxs-lookup"><span data-stu-id="9409e-110">You can export up to 250,000 profiles at a time to AdRoll.</span></span>
- <span data-ttu-id="9409e-111">Do služby AdRoll nemôžete exportovať segmenty s menej ako 100 profilmi.</span><span class="sxs-lookup"><span data-stu-id="9409e-111">You can't export segments with fewer than 100 profiles to AdRoll.</span></span> 
- <span data-ttu-id="9409e-112">Export do AdRoll je obmedzený na segmenty.</span><span class="sxs-lookup"><span data-stu-id="9409e-112">Exporting to AdRoll is limited to segments.</span></span>
- <span data-ttu-id="9409e-113">Export až 250 000 profilov do služby AdRoll môže trvať až 10 minút.</span><span class="sxs-lookup"><span data-stu-id="9409e-113">Exporting up to 250,000 profiles to AdRoll can take up to 10 minutes to complete.</span></span> 
- <span data-ttu-id="9409e-114">Počet profilov, ktoré môžete exportovať do AdRoll, závisí od vašej zmluvy s AdRoll.</span><span class="sxs-lookup"><span data-stu-id="9409e-114">The number of profiles that you can export to AdRoll is dependent on your contract with AdRoll.</span></span>

## <a name="set-up-connection-to-adroll"></a><span data-ttu-id="9409e-115">Nastavenie pripojenia k AdRoll</span><span class="sxs-lookup"><span data-stu-id="9409e-115">Set up connection to AdRoll</span></span>

1. <span data-ttu-id="9409e-116">Prejdite do časti **Správca** > **Pripojenia**.</span><span class="sxs-lookup"><span data-stu-id="9409e-116">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="9409e-117">Stlačte možnosť **Pridať pripojenie** a stlačením možnosti **AdRoll** nakonfigurujte pripojenie.</span><span class="sxs-lookup"><span data-stu-id="9409e-117">Select **Add connection** and choose **AdRoll** to configure the connection.</span></span>

1. <span data-ttu-id="9409e-118">Do poľa **Zobrazovaný názov** zadajte rozpoznateľný názov pripojenia.</span><span class="sxs-lookup"><span data-stu-id="9409e-118">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="9409e-119">Zobrazovaný názov a typ spojenia, ktoré popisuje toto spojenie.</span><span class="sxs-lookup"><span data-stu-id="9409e-119">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="9409e-120">Odporúčame zvoliť názov, ktorý vysvetľuje účel a cieľ tohto spojenia.</span><span class="sxs-lookup"><span data-stu-id="9409e-120">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="9409e-121">Vyberte používateľov, ktorí môžu používať toto pripojenie.</span><span class="sxs-lookup"><span data-stu-id="9409e-121">Choose who can use this connection.</span></span> <span data-ttu-id="9409e-122">Ak neurobíte nič, predvolená hodnota bude Správcovia.</span><span class="sxs-lookup"><span data-stu-id="9409e-122">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="9409e-123">Viac informácií nájdete v časti [Umožnite prispievateľom použiť pripojenie na export](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="9409e-123">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="9409e-124">Vyberte **Súhlasím** na potvrdenie **Ochrany osobných údajov a dodržiavanie súladu s nariadeniami**.</span><span class="sxs-lookup"><span data-stu-id="9409e-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="9409e-125">Vyberte položku **Pripojiť** na inicializáciu pripojenia k AdRoll.</span><span class="sxs-lookup"><span data-stu-id="9409e-125">Select **Connect** to initialize the connection to AdRoll.</span></span>

1. <span data-ttu-id="9409e-126">Vyberte položku **Overenie pomocou AdRoll** a poskytnite svoje poverenia správcu pre AdRoll.</span><span class="sxs-lookup"><span data-stu-id="9409e-126">Select **Authenticate with AdRoll** and provide your admin credentials for AdRoll.</span></span> 

1. <span data-ttu-id="9409e-127">Vyberte položku **Pridať samého seba ako používateľa exportu** a uveďte svoje poverenia pre Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="9409e-127">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="9409e-128">Stlačte možnosť **Uložiť** a dokončite pripojenie.</span><span class="sxs-lookup"><span data-stu-id="9409e-128">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="9409e-129">Nakonfigurujte export</span><span class="sxs-lookup"><span data-stu-id="9409e-129">Configure an export</span></span>

<span data-ttu-id="9409e-130">Tento export môžete nakonfigurovať, ak máte prístup k pripojeniu tohto typu.</span><span class="sxs-lookup"><span data-stu-id="9409e-130">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="9409e-131">Viac informácií nájdete na stránke [Na konfiguráciu exportu sú potrebné povolenia](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="9409e-131">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="9409e-132">Prejdite na **Údaje** > **Exporty**.</span><span class="sxs-lookup"><span data-stu-id="9409e-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="9409e-133">Na vytvorenie nového exportu stlačte možnosť **Pridať cieľ**.</span><span class="sxs-lookup"><span data-stu-id="9409e-133">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="9409e-134">V poli **Pripojenie na export** vyberte pripojenie v časti AdRoll.</span><span class="sxs-lookup"><span data-stu-id="9409e-134">In the **Connection for export** field, choose a connection from the AdRoll section.</span></span> <span data-ttu-id="9409e-135">Ak nevidíte názov tejto sekcie, nemáte k dispozícii žiadne pripojenia tohto typu.</span><span class="sxs-lookup"><span data-stu-id="9409e-135">If you don't see this section name, then no connections of this type are available to you.</span></span>

1. <span data-ttu-id="9409e-136">Zadajte svoje **ID zadávateľa reklamy v službe AdRoll**.</span><span class="sxs-lookup"><span data-stu-id="9409e-136">Enter your **AdRoll Advertiser ID**.</span></span> <span data-ttu-id="9409e-137">Ďalšie informácie nájdete v sekcii [Profily zadávateľov reklamy v službe AdRoll](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).</span><span class="sxs-lookup"><span data-stu-id="9409e-137">For more information, see [AdRoll Advertiser Profiles](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).</span></span>

3. <span data-ttu-id="9409e-138">V sekcii **Párovanie údajov** v poli **E-mail** do svojho zjednoteného profilu zákazníka vyberte pole, ktoré predstavuje e-mailovú adresu zákazníka.</span><span class="sxs-lookup"><span data-stu-id="9409e-138">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="9409e-139">Je potrebné exportovať segmenty do služby AdRoll.</span><span class="sxs-lookup"><span data-stu-id="9409e-139">It's required to export segments to AdRoll.</span></span>

1. <span data-ttu-id="9409e-140">Vyberte segmenty, ktoré chcete exportovať.</span><span class="sxs-lookup"><span data-stu-id="9409e-140">Select the segments you want to export.</span></span> <span data-ttu-id="9409e-141">Vyberte segment s najmenej 100 členmi.</span><span class="sxs-lookup"><span data-stu-id="9409e-141">Select a segment with a least 100 members.</span></span> <span data-ttu-id="9409e-142">Menšie segmenty nemôžete exportovať.</span><span class="sxs-lookup"><span data-stu-id="9409e-142">You can't export smaller segments.</span></span> <span data-ttu-id="9409e-143">Maximálna veľkosť segmentu na export je 250 000 členov na export.</span><span class="sxs-lookup"><span data-stu-id="9409e-143">Additionally the maximum size of a segment to export is 250,000 members per export.</span></span> 

1. <span data-ttu-id="9409e-144">Vyberte položku **Uložiť**.</span><span class="sxs-lookup"><span data-stu-id="9409e-144">Select **Save**.</span></span>

<span data-ttu-id="9409e-145">Uloženie exportu nespustí export okamžite.</span><span class="sxs-lookup"><span data-stu-id="9409e-145">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="9409e-146">Export prebieha s každým [plánovaným obnovením](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="9409e-146">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> 

<span data-ttu-id="9409e-147">Môžete tiež [exportovať údaje na požiadanie](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="9409e-147">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="9409e-148">Ochrana osobných údajov a dodržiavanie súladu s nariadeniami</span><span class="sxs-lookup"><span data-stu-id="9409e-148">Data privacy and compliance</span></span>

<span data-ttu-id="9409e-149">Keď povolíte prenos údajov do AdRoll v službe Dynamics 365 Customer Insights, povoľujete tým prenos údajov mimo hranice súladu so službou Dynamics 365 Customer Insights vrátane potenciálne citlivých údajov, ako sú napríklad osobné údaje.</span><span class="sxs-lookup"><span data-stu-id="9409e-149">When you enable Dynamics 365 Customer Insights to transmit data to AdRoll, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="9409e-150">Spoločnosť Microsoft prenesie tieto údaje na váš pokyn, ale vy ste zodpovední za zabezpečenie toho, aby AdRoll plnila všetky prípadné povinnosti týkajúce sa ochrany vašich osobných údajov alebo zabezpečenia.</span><span class="sxs-lookup"><span data-stu-id="9409e-150">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that AdRoll meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="9409e-151">Ďalšie informácie nájdete vo [vyhlásení o ochrane súkromia spoločnosti Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="9409e-151">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="9409e-152">Váš správca služby Dynamics 365 Customer Insights môže túto funkciu kedykoľvek prestať používať odstránením tohto cieľového umiestnenia exportu.</span><span class="sxs-lookup"><span data-stu-id="9409e-152">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
