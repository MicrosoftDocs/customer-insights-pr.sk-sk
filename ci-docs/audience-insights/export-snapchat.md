---
title: Export údajov Customer Insights do Snapchat
description: Zistite ako nakonfigurovať pripojenie a realizovať exportovanie do Snapchat.
ms.date: 03/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6565ab81599abcc0f94465e1153f08e0bc119839
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124062"
---
# <a name="export-segments-to-snapchat-preview"></a><span data-ttu-id="97e6f-103">Export segmentov do Snapchat (verzia Preview)</span><span class="sxs-lookup"><span data-stu-id="97e6f-103">Export segments to Snapchat (preview)</span></span>

<span data-ttu-id="97e6f-104">Exportujte segmenty zjednotených profilov zákazníkov do Snapchat a použite ich na reklamu.</span><span class="sxs-lookup"><span data-stu-id="97e6f-104">Export segments of unified customer profiles to Snapchat and use them for advertising.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="97e6f-105">Predpoklad na pripojenie</span><span class="sxs-lookup"><span data-stu-id="97e6f-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="97e6f-106">Máte [Účet Snapchat Business](https://business.snapchat.com/) a [Účet Snapchat Ads](https://ads.snapchat.com/) a zodpovedajúce poverenia správcu.</span><span class="sxs-lookup"><span data-stu-id="97e6f-106">You have a [Snapchat Business account](https://business.snapchat.com/), a [Snapchat Ads account](https://ads.snapchat.com/), and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="97e6f-107">Máte [konfigurované segmenty](segments.md) v prehľadoch cieľových skupín.</span><span class="sxs-lookup"><span data-stu-id="97e6f-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="97e6f-108">Zjednotené profily zákazníkov v exportovaných segmentoch obsahujú pole predstavujúce e-mailovú adresu.</span><span class="sxs-lookup"><span data-stu-id="97e6f-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="97e6f-109">Známe obmedzenia</span><span class="sxs-lookup"><span data-stu-id="97e6f-109">Known limitations</span></span>

- <span data-ttu-id="97e6f-110">Exportovanie do Snapchat je obmedzené na segmenty.</span><span class="sxs-lookup"><span data-stu-id="97e6f-110">Exporting to Snapchat is limited to segments.</span></span>
- <span data-ttu-id="97e6f-111">Exportovanie až 1 milión profilov do aplikácie Snapchat môže trvať až 15 minút.</span><span class="sxs-lookup"><span data-stu-id="97e6f-111">Exporting up to 1 million profiles to Snapchat can take up to 15 minutes to complete.</span></span> 

## <a name="set-up-connection-to-snapchat"></a><span data-ttu-id="97e6f-112">Nastavenie pripojenia k Snapchat</span><span class="sxs-lookup"><span data-stu-id="97e6f-112">Set up connection to Snapchat</span></span>

1. <span data-ttu-id="97e6f-113">Prejdite do časti **Správca** > **Pripojenia**.</span><span class="sxs-lookup"><span data-stu-id="97e6f-113">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="97e6f-114">Stlačte možnosť **Pridať pripojenie** a stlačením možnosti **Snapchat** nakonfigurujte pripojenie.</span><span class="sxs-lookup"><span data-stu-id="97e6f-114">Select **Add connection** and choose **Snapchat** to configure the connection.</span></span>

1. <span data-ttu-id="97e6f-115">Do poľa **Zobrazovaný názov** zadajte rozpoznateľný názov pripojenia.</span><span class="sxs-lookup"><span data-stu-id="97e6f-115">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="97e6f-116">Zobrazovaný názov a typ spojenia, ktoré popisuje toto spojenie.</span><span class="sxs-lookup"><span data-stu-id="97e6f-116">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="97e6f-117">Odporúčame zvoliť názov, ktorý vysvetľuje účel a cieľ tohto spojenia.</span><span class="sxs-lookup"><span data-stu-id="97e6f-117">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="97e6f-118">Vyberte používateľov, ktorí môžu používať toto pripojenie.</span><span class="sxs-lookup"><span data-stu-id="97e6f-118">Choose who can use this connection.</span></span> <span data-ttu-id="97e6f-119">Ak neurobíte nič, predvolená hodnota bude Správcovia.</span><span class="sxs-lookup"><span data-stu-id="97e6f-119">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="97e6f-120">Viac informácií nájdete v časti [Umožnite prispievateľom použiť pripojenie na export](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="97e6f-120">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="97e6f-121">Vyberte **Súhlasím** na potvrdenie **Ochrany osobných údajov a dodržiavanie súladu s nariadeniami**.</span><span class="sxs-lookup"><span data-stu-id="97e6f-121">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="97e6f-122">Stlačte možnosť **Pripojiť** na inicializáciu pripojenia k Snapchat.</span><span class="sxs-lookup"><span data-stu-id="97e6f-122">Select **Connect** to initialize the connection to Snapchat.</span></span>

1. <span data-ttu-id="97e6f-123">Stlačte možnosť **Overenie pomocou služby Snapchat** a zadajte svoje poverenia správcu pre Snapchat.</span><span class="sxs-lookup"><span data-stu-id="97e6f-123">Select **Authenticate with Snapchat** and provide your admin credentials for Snapchat.</span></span> 

1. <span data-ttu-id="97e6f-124">Vyberte položku **Pridať samého seba ako používateľa exportu** a uveďte svoje poverenia pre Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="97e6f-124">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="97e6f-125">Stlačte možnosť **Uložiť** a dokončite pripojenie.</span><span class="sxs-lookup"><span data-stu-id="97e6f-125">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="97e6f-126">Nakonfigurujte export</span><span class="sxs-lookup"><span data-stu-id="97e6f-126">Configure an export</span></span>

<span data-ttu-id="97e6f-127">Tento export môžete nakonfigurovať, ak máte prístup k pripojeniu tohto typu.</span><span class="sxs-lookup"><span data-stu-id="97e6f-127">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="97e6f-128">Viac informácií nájdete na stránke [Na konfiguráciu exportu sú potrebné povolenia](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="97e6f-128">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="97e6f-129">Prejdite na **Údaje** > **Exporty**.</span><span class="sxs-lookup"><span data-stu-id="97e6f-129">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="97e6f-130">Na vytvorenie nového exportu stlačte možnosť **Pridať cieľ**.</span><span class="sxs-lookup"><span data-stu-id="97e6f-130">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="97e6f-131">V poli **Pripojenie na export** vyberte pripojenie v časti Snapchat.</span><span class="sxs-lookup"><span data-stu-id="97e6f-131">In the **Connection for export** field, choose a connection from the Snapchat section.</span></span> <span data-ttu-id="97e6f-132">Ak nevidíte názov tejto sekcie, nemáte k dispozícii žiadne spojenia tohto typu.</span><span class="sxs-lookup"><span data-stu-id="97e6f-132">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="97e6f-133">Zadajte [**ID cieľovej skupiny Snapchat**](https://businesshelp.snapchat.com/s/article/custom-audiences).</span><span class="sxs-lookup"><span data-stu-id="97e6f-133">Enter the [**Snapchat Audience ID**](https://businesshelp.snapchat.com/s/article/custom-audiences).</span></span>

1. <span data-ttu-id="97e6f-134">V sekcii **Párovanie údajov** v poli **E-mail** do svojho zjednoteného profilu zákazníka vyberte pole, ktoré predstavuje e-mailovú adresu zákazníka.</span><span class="sxs-lookup"><span data-stu-id="97e6f-134">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="97e6f-135">Je potrebné exportovať segmenty do Snapchat.</span><span class="sxs-lookup"><span data-stu-id="97e6f-135">It's required to export segments to Snapchat.</span></span>

1. <span data-ttu-id="97e6f-136">Vyberte segmenty, ktoré chcete exportovať.</span><span class="sxs-lookup"><span data-stu-id="97e6f-136">Select the segments you want to export.</span></span> 

1. <span data-ttu-id="97e6f-137">Vyberte položku **Uložiť**.</span><span class="sxs-lookup"><span data-stu-id="97e6f-137">Select **Save**.</span></span>

<span data-ttu-id="97e6f-138">Uloženie exportu nespustí export okamžite.</span><span class="sxs-lookup"><span data-stu-id="97e6f-138">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="97e6f-139">Export prebieha s každým [plánovaným obnovením](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="97e6f-139">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="97e6f-140">Môžete tiež [exportovať údaje na požiadanie](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="97e6f-140">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="97e6f-141">Ochrana osobných údajov a dodržiavanie súladu s nariadeniami</span><span class="sxs-lookup"><span data-stu-id="97e6f-141">Data privacy and compliance</span></span>

<span data-ttu-id="97e6f-142">Keď povolíte Dynamics 365 Customer Insights na prenos údajov do Snapchat, povolíte prenos údajov mimo hranice súladu s Dynamics 365 Customer Insights, a to vrátane potenciálne citlivých údajov, ako sú napríklad osobné údaje.</span><span class="sxs-lookup"><span data-stu-id="97e6f-142">When you enable Dynamics 365 Customer Insights to transmit data to Snapchat, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="97e6f-143">Spoločnosť Microsoft prenesie tieto údaje na váš pokyn, ale vy ste zodpovední za zabezpečenie toho, aby služba Snapchat spĺňala všetky vaše povinnosti v oblasti ochrany osobných údajov alebo bezpečnosti.</span><span class="sxs-lookup"><span data-stu-id="97e6f-143">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Snapchat meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="97e6f-144">Ďalšie informácie nájdete vo [vyhlásení o ochrane súkromia spoločnosti Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="97e6f-144">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="97e6f-145">Váš správca služby Dynamics 365 Customer Insights môže túto funkciu kedykoľvek prestať používať odstránením tohto cieľového umiestnenia exportu.</span><span class="sxs-lookup"><span data-stu-id="97e6f-145">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
