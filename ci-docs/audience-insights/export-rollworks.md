---
title: Export údajov Customer Insights do RollWorks
description: Zistite ako nakonfigurovať pripojenie a realizovať exportovanie do RollWorks.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: dce5d51ca4587b4d7a0644cc701c1826854882b5
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124108"
---
# <a name="export-segments-to-rollworks-preview"></a><span data-ttu-id="126c5-103">Export segmentov do RollWorks (verzia Preview)</span><span class="sxs-lookup"><span data-stu-id="126c5-103">Export segments to RollWorks (preview)</span></span>

<span data-ttu-id="126c5-104">Exportujte segmenty zjednotených profilov zákazníkov do RollWorks a použite ich na reklamu.</span><span class="sxs-lookup"><span data-stu-id="126c5-104">Export segments of unified customer profiles to RollWorks and use them for advertising.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="126c5-105">Predpoklad na pripojenie</span><span class="sxs-lookup"><span data-stu-id="126c5-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="126c5-106">Máte [účet RollWorks](https://www.rollworks.com/) a zodpovedajúce poverenia správcu.</span><span class="sxs-lookup"><span data-stu-id="126c5-106">You have an [RollWorks account](https://www.rollworks.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="126c5-107">Máte [konfigurované segmenty](segments.md) v prehľadoch cieľových skupín.</span><span class="sxs-lookup"><span data-stu-id="126c5-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="126c5-108">Zjednotené profily zákazníkov v exportovaných segmentoch obsahujú pole predstavujúce e-mailovú adresu.</span><span class="sxs-lookup"><span data-stu-id="126c5-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="126c5-109">Známe obmedzenia</span><span class="sxs-lookup"><span data-stu-id="126c5-109">Known limitations</span></span>

- <span data-ttu-id="126c5-110">Na jeden export do RollWorks môžete exportovať až 250 000 profilov.</span><span class="sxs-lookup"><span data-stu-id="126c5-110">You can export up to 250'000 profiles in per export to RollWorks.</span></span>
- <span data-ttu-id="126c5-111">Do RollWorks nemôžete exportovať segmenty s menej ako 100 profilmi.</span><span class="sxs-lookup"><span data-stu-id="126c5-111">You can't export segments with fewer than 100 profiles to RollWorks.</span></span> 
- <span data-ttu-id="126c5-112">Exportovanie do RollWorks je obmedzené na segmenty.</span><span class="sxs-lookup"><span data-stu-id="126c5-112">Exporting to RollWorks is limited to segments.</span></span>
- <span data-ttu-id="126c5-113">Exportovanie až 250 000 profilov do aplikácie RollWorks môže trvať až 10 minút.</span><span class="sxs-lookup"><span data-stu-id="126c5-113">Exporting up to 250'000 profiles to RollWorks can take up to 10 minutes to complete.</span></span> 
- <span data-ttu-id="126c5-114">Počet profilov, ktoré môžete exportovať do RollWorks, závisí a je obmedzený na vašu zmluvu so spoločnosťou RollWorks.</span><span class="sxs-lookup"><span data-stu-id="126c5-114">The number of profiles that you can export to RollWorks is dependent and limited on your contract with RollWorks.</span></span>

## <a name="set-up-connection-to-rollworks"></a><span data-ttu-id="126c5-115">Nastavenie pripojenia k RollWorks</span><span class="sxs-lookup"><span data-stu-id="126c5-115">Set up connection to RollWorks</span></span>

1. <span data-ttu-id="126c5-116">Prejdite do časti **Správca** > **Pripojenia**.</span><span class="sxs-lookup"><span data-stu-id="126c5-116">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="126c5-117">Stlačte možnosť **Pridať pripojenie** a stlačením možnosti **RollWorks** nakonfigurujte pripojenie.</span><span class="sxs-lookup"><span data-stu-id="126c5-117">Select **Add connection** and choose **RollWorks** to configure the connection.</span></span>

1. <span data-ttu-id="126c5-118">Do poľa **Zobrazovaný názov** zadajte rozpoznateľný názov pripojenia.</span><span class="sxs-lookup"><span data-stu-id="126c5-118">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="126c5-119">Zobrazovaný názov a typ spojenia, ktoré popisuje toto spojenie.</span><span class="sxs-lookup"><span data-stu-id="126c5-119">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="126c5-120">Odporúčame zvoliť názov, ktorý vysvetľuje účel a cieľ tohto spojenia.</span><span class="sxs-lookup"><span data-stu-id="126c5-120">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="126c5-121">Vyberte používateľov, ktorí môžu používať toto pripojenie.</span><span class="sxs-lookup"><span data-stu-id="126c5-121">Choose who can use this connection.</span></span> <span data-ttu-id="126c5-122">Ak neurobíte nič, predvolená hodnota bude Správcovia.</span><span class="sxs-lookup"><span data-stu-id="126c5-122">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="126c5-123">Viac informácií nájdete v časti [Umožnite prispievateľom použiť pripojenie na export](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="126c5-123">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="126c5-124">Vyberte **Súhlasím** na potvrdenie **Ochrany osobných údajov a dodržiavanie súladu s nariadeniami**.</span><span class="sxs-lookup"><span data-stu-id="126c5-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="126c5-125">Stlačte možnosť **Pripojiť** na inicializáciu pripojenia k RollWorks.</span><span class="sxs-lookup"><span data-stu-id="126c5-125">Select **Connect** to initialize the connection to RollWorks.</span></span>

1. <span data-ttu-id="126c5-126">Stlačte možnosť **Overenie pomocou služby RollWorks** a zadajte svoje poverenia správcu pre RollWorks.</span><span class="sxs-lookup"><span data-stu-id="126c5-126">Select **Authenticate with RollWorks** and provide your admin credentials for RollWorks.</span></span>

1. <span data-ttu-id="126c5-127">Vyberte položku **Pridať samého seba ako používateľa exportu** a uveďte svoje poverenia pre Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="126c5-127">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="126c5-128">Stlačte možnosť **Uložiť** a dokončite pripojenie.</span><span class="sxs-lookup"><span data-stu-id="126c5-128">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="126c5-129">Nakonfigurujte export</span><span class="sxs-lookup"><span data-stu-id="126c5-129">Configure an export</span></span>

<span data-ttu-id="126c5-130">Tento export môžete nakonfigurovať, ak máte prístup k pripojeniu tohto typu.</span><span class="sxs-lookup"><span data-stu-id="126c5-130">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="126c5-131">Viac informácií nájdete na stránke [Na konfiguráciu exportu sú potrebné povolenia](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="126c5-131">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="126c5-132">Prejdite na **Údaje** > **Exporty**.</span><span class="sxs-lookup"><span data-stu-id="126c5-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="126c5-133">Na vytvorenie nového exportu stlačte možnosť **Pridať cieľ**.</span><span class="sxs-lookup"><span data-stu-id="126c5-133">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="126c5-134">V poli **Pripojenie na export** vyberte pripojenie v časti RollWorks.</span><span class="sxs-lookup"><span data-stu-id="126c5-134">In the **Connection for export** field, choose a connection from the RollWorks section.</span></span> <span data-ttu-id="126c5-135">Ak nevidíte názov tejto sekcie, nemáte k dispozícii žiadne spojenia tohto typu.</span><span class="sxs-lookup"><span data-stu-id="126c5-135">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="126c5-136">Zadajte svoje **ID inzerenta RollWorks** [Inzerovateľné v službe RollWorks](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).</span><span class="sxs-lookup"><span data-stu-id="126c5-136">Enter your **RollWorks Advertiser ID** [RollWorks Advertisable](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).</span></span>

3. <span data-ttu-id="126c5-137">V sekcii **Párovanie údajov** v poli **E-mail** do svojho zjednoteného profilu zákazníka vyberte pole, ktoré predstavuje e-mailovú adresu zákazníka.</span><span class="sxs-lookup"><span data-stu-id="126c5-137">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="126c5-138">Je potrebné exportovať segmenty do RollWorks.</span><span class="sxs-lookup"><span data-stu-id="126c5-138">It's required to export segments to RollWorks.</span></span>

1. <span data-ttu-id="126c5-139">Vyberte segmenty, ktoré chcete exportovať.</span><span class="sxs-lookup"><span data-stu-id="126c5-139">Select the segments you want to export.</span></span> <span data-ttu-id="126c5-140">Vyberte segment s najmenej 100 členmi.</span><span class="sxs-lookup"><span data-stu-id="126c5-140">Select a segment with a least 100 members.</span></span> <span data-ttu-id="126c5-141">Menšie segmenty nemôžete exportovať.</span><span class="sxs-lookup"><span data-stu-id="126c5-141">You can't export smaller segments.</span></span> <span data-ttu-id="126c5-142">Maximálna veľkosť segmentu na export je 250 000 členov na export.</span><span class="sxs-lookup"><span data-stu-id="126c5-142">Additionally the maximum size of a segment to export is 250'000 members per export.</span></span> 

1. <span data-ttu-id="126c5-143">Vyberte položku **Uložiť**.</span><span class="sxs-lookup"><span data-stu-id="126c5-143">Select **Save**.</span></span>

<span data-ttu-id="126c5-144">Uloženie exportu nespustí export okamžite.</span><span class="sxs-lookup"><span data-stu-id="126c5-144">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="126c5-145">Export prebieha s každým [plánovaným obnovením](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="126c5-145">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="126c5-146">Môžete tiež [exportovať údaje na požiadanie](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="126c5-146">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="126c5-147">Ochrana osobných údajov a dodržiavanie súladu s nariadeniami</span><span class="sxs-lookup"><span data-stu-id="126c5-147">Data privacy and compliance</span></span>

<span data-ttu-id="126c5-148">Keď povolíte Dynamics 365 Customer Insights na prenos údajov do RollWorks, povolíte prenos údajov mimo hranice súladu s Dynamics 365 Customer Insights, a to vrátane potenciálne citlivých údajov, ako sú napríklad osobné údaje.</span><span class="sxs-lookup"><span data-stu-id="126c5-148">When you enable Dynamics 365 Customer Insights to transmit data to RollWorks, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="126c5-149">Spoločnosť Microsoft prenesie tieto údaje na váš pokyn, ale vy ste zodpovední za zabezpečenie toho, aby služba RollWorks spĺňala všetky vaše povinnosti v oblasti ochrany osobných údajov alebo bezpečnosti.</span><span class="sxs-lookup"><span data-stu-id="126c5-149">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that RollWorks meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="126c5-150">Ďalšie informácie nájdete vo [vyhlásení o ochrane súkromia spoločnosti Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="126c5-150">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="126c5-151">Váš správca služby Dynamics 365 Customer Insights môže túto funkciu kedykoľvek prestať používať odstránením tohto cieľového umiestnenia exportu.</span><span class="sxs-lookup"><span data-stu-id="126c5-151">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
