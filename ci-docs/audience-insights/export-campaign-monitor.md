---
title: Export údajov Customer Insights do Campaign Monitor
description: Zistite ako nakonfigurovať pripojenie a realizovať exportovanie do Campaign Monitor.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 091a3197dc0c19ff78f0419fb4e88868e0f78359
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124200"
---
# <a name="export-segments-to-campaign-monitor-preview"></a><span data-ttu-id="a8bc1-103">Export segmentov do Campaign Monitor (verzia Preview)</span><span class="sxs-lookup"><span data-stu-id="a8bc1-103">Export segments to Campaign Monitor (preview)</span></span>

<span data-ttu-id="a8bc1-104">Exportujte segmenty zjednotených profilov zákazníkov do Campaign Monitor a použite ich na marketingové aktivity.</span><span class="sxs-lookup"><span data-stu-id="a8bc1-104">Export segments of unified customer profiles to Campaign Monitor and use them for marketing activities.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="a8bc1-105">Predpoklady</span><span class="sxs-lookup"><span data-stu-id="a8bc1-105">Prerequisites</span></span>

-   <span data-ttu-id="a8bc1-106">Máte [účet Campaign Monitor](https://www.campaignmonitor.com/) a zodpovedajúce poverenia správcu.</span><span class="sxs-lookup"><span data-stu-id="a8bc1-106">You have an [Campaign Monitor account](https://www.campaignmonitor.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="a8bc1-107">Máte [konfigurované segmenty](segments.md) v prehľadoch cieľových skupín.</span><span class="sxs-lookup"><span data-stu-id="a8bc1-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="a8bc1-108">Zjednotené profily zákazníkov v exportovaných segmentoch obsahujú pole predstavujúce e-mailovú adresu.</span><span class="sxs-lookup"><span data-stu-id="a8bc1-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="a8bc1-109">Známe obmedzenia</span><span class="sxs-lookup"><span data-stu-id="a8bc1-109">Known limitations</span></span>

- <span data-ttu-id="a8bc1-110">Na jeden export do 1 miliónov profilov môžete exportovať až Campaign Monitor.</span><span class="sxs-lookup"><span data-stu-id="a8bc1-110">You can export up to 1 million profiles per export to Campaign Monitor.</span></span>
- <span data-ttu-id="a8bc1-111">Exportovanie do Campaign Monitor je obmedzené na segmenty.</span><span class="sxs-lookup"><span data-stu-id="a8bc1-111">Exporting to Campaign Monitor is limited to segments.</span></span>
- <span data-ttu-id="a8bc1-112">Exportovanie až 1 milión profilov do aplikácie Campaign Monitor môže trvať až 20 minút.</span><span class="sxs-lookup"><span data-stu-id="a8bc1-112">Exporting up to 1 million profiles to Campaign Monitor can take up to 20 minutes to complete.</span></span> 
- <span data-ttu-id="a8bc1-113">Počet profilov, ktoré môžete exportovať do Campaign Monitor, závisí a je obmedzený na vašu zmluvu so spoločnosťou Campaign Monitor.</span><span class="sxs-lookup"><span data-stu-id="a8bc1-113">The number of profiles that you can export to Campaign Monitor is dependent and limited on your contract with Campaign Monitor.</span></span>

## <a name="set-up-connection-to-campaign-monitor"></a><span data-ttu-id="a8bc1-114">Nastavenie pripojenia k Campaign Monitor</span><span class="sxs-lookup"><span data-stu-id="a8bc1-114">Set up connection to Campaign Monitor</span></span>

1. <span data-ttu-id="a8bc1-115">Prejdite do časti **Správca** > **Pripojenia**.</span><span class="sxs-lookup"><span data-stu-id="a8bc1-115">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="a8bc1-116">Stlačte možnosť **Pridať pripojenie** a stlačením možnosti **Campaign Monitor** nakonfigurujte pripojenie.</span><span class="sxs-lookup"><span data-stu-id="a8bc1-116">Select **Add connection** and choose **Campaign Monitor** to configure the connection.</span></span>

1. <span data-ttu-id="a8bc1-117">Do poľa **Zobrazovaný názov** zadajte rozpoznateľný názov pripojenia.</span><span class="sxs-lookup"><span data-stu-id="a8bc1-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="a8bc1-118">Zobrazovaný názov a typ spojenia, ktoré popisuje toto spojenie.</span><span class="sxs-lookup"><span data-stu-id="a8bc1-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="a8bc1-119">Odporúčame zvoliť názov, ktorý vysvetľuje účel a cieľ tohto spojenia.</span><span class="sxs-lookup"><span data-stu-id="a8bc1-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="a8bc1-120">Vyberte používateľov, ktorí môžu používať toto pripojenie.</span><span class="sxs-lookup"><span data-stu-id="a8bc1-120">Choose who can use this connection.</span></span> <span data-ttu-id="a8bc1-121">Ak neurobíte nič, predvolená hodnota bude Správcovia.</span><span class="sxs-lookup"><span data-stu-id="a8bc1-121">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="a8bc1-122">Viac informácií nájdete v časti [Umožnite prispievateľom použiť pripojenie na export](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="a8bc1-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="a8bc1-123">Vyberte **Súhlasím** na potvrdenie **Ochrany osobných údajov a dodržiavanie súladu s nariadeniami**.</span><span class="sxs-lookup"><span data-stu-id="a8bc1-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="a8bc1-124">Stlačte možnosť **Pripojiť** na inicializáciu pripojenia k Campaign Monitor.</span><span class="sxs-lookup"><span data-stu-id="a8bc1-124">Select **Connect** to initialize the connection to Campaign Monitor.</span></span>

1. <span data-ttu-id="a8bc1-125">Stlačte možnosť **Overenie pomocou služby Campaign Monitor** a zadajte svoje poverenia správcu pre Campaign Monitor.</span><span class="sxs-lookup"><span data-stu-id="a8bc1-125">Select **Authenticate with Campaign Monitor** and provide your admin credentials for Campaign Monitor.</span></span>

1. <span data-ttu-id="a8bc1-126">Vyberte položku **Pridať samého seba ako používateľa exportu** a uveďte svoje poverenia pre Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="a8bc1-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="a8bc1-127">Stlačte možnosť **Uložiť** a dokončite pripojenie.</span><span class="sxs-lookup"><span data-stu-id="a8bc1-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="a8bc1-128">Nakonfigurujte export</span><span class="sxs-lookup"><span data-stu-id="a8bc1-128">Configure an export</span></span>

<span data-ttu-id="a8bc1-129">Tento export môžete nakonfigurovať, ak máte prístup k pripojeniu tohto typu.</span><span class="sxs-lookup"><span data-stu-id="a8bc1-129">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="a8bc1-130">Viac informácií nájdete na stránke [Na konfiguráciu exportu sú potrebné povolenia](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="a8bc1-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="a8bc1-131">Prejdite na **Údaje** > **Exporty**.</span><span class="sxs-lookup"><span data-stu-id="a8bc1-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="a8bc1-132">Na vytvorenie nového exportu stlačte možnosť **Pridať cieľ**.</span><span class="sxs-lookup"><span data-stu-id="a8bc1-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="a8bc1-133">V poli **Pripojenie na export** vyberte pripojenie v časti Campaign Monitor.</span><span class="sxs-lookup"><span data-stu-id="a8bc1-133">In the **Connection for export** field, choose a connection from the Campaign Monitor section.</span></span> <span data-ttu-id="a8bc1-134">Ak nevidíte názov tejto sekcie, nemáte k dispozícii žiadne spojenia tohto typu.</span><span class="sxs-lookup"><span data-stu-id="a8bc1-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="a8bc1-135">Zadajte svoj [**Identifikátor zoznamu Campaign Monitor**](https://www.campaignmonitor.com/api/getting-started/#your-list-id).</span><span class="sxs-lookup"><span data-stu-id="a8bc1-135">Enter your [**Campaign Monitor List ID**](https://www.campaignmonitor.com/api/getting-started/#your-list-id).</span></span>    
   <span data-ttu-id="a8bc1-136">[Vygenerujte kľúč API](https://www.campaignmonitor.com/api/getting-started/) od **Nastavenia účtu** najskôr v nástroji Campaign Monitor na zobrazenie ID zoznamu API.</span><span class="sxs-lookup"><span data-stu-id="a8bc1-136">[Generate the API key](https://www.campaignmonitor.com/api/getting-started/) from **Account Settings** in Campaign Monitor first to view the API list ID.</span></span>  

3. <span data-ttu-id="a8bc1-137">V sekcii **Párovanie údajov** v poli **E-mail** do svojho zjednoteného profilu zákazníka vyberte pole, ktoré predstavuje e-mailovú adresu zákazníka.</span><span class="sxs-lookup"><span data-stu-id="a8bc1-137">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="a8bc1-138">Je potrebné exportovať segmenty do Campaign Monitor.</span><span class="sxs-lookup"><span data-stu-id="a8bc1-138">It's required to export segments to Campaign Monitor.</span></span>

1. <span data-ttu-id="a8bc1-139">Vyberte položku **Uložiť**.</span><span class="sxs-lookup"><span data-stu-id="a8bc1-139">Select **Save**.</span></span>

<span data-ttu-id="a8bc1-140">Uloženie exportu nespustí export okamžite.</span><span class="sxs-lookup"><span data-stu-id="a8bc1-140">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="a8bc1-141">Export prebieha s každým [plánovaným obnovením](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="a8bc1-141">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="a8bc1-142">Môžete tiež [exportovať údaje na požiadanie](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="a8bc1-142">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="a8bc1-143">Ochrana osobných údajov a dodržiavanie súladu s nariadeniami</span><span class="sxs-lookup"><span data-stu-id="a8bc1-143">Data privacy and compliance</span></span>

<span data-ttu-id="a8bc1-144">Keď povolíte Dynamics 365 Customer Insights na prenos údajov do Campaign Monitor, povolíte prenos údajov mimo hranice súladu s Dynamics 365 Customer Insights, a to vrátane potenciálne citlivých údajov, ako sú napríklad osobné údaje.</span><span class="sxs-lookup"><span data-stu-id="a8bc1-144">When you enable Dynamics 365 Customer Insights to transmit data to Campaign Monitor, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="a8bc1-145">Spoločnosť Microsoft prenesie tieto údaje na váš pokyn, ale vy ste zodpovední za zabezpečenie toho, aby služba Campaign Monitor spĺňala všetky vaše povinnosti v oblasti ochrany osobných údajov alebo bezpečnosti.</span><span class="sxs-lookup"><span data-stu-id="a8bc1-145">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Campaign Monitor meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="a8bc1-146">Ďalšie informácie nájdete vo [vyhlásení o ochrane súkromia spoločnosti Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="a8bc1-146">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="a8bc1-147">Váš správca služby Dynamics 365 Customer Insights môže túto funkciu kedykoľvek prestať používať odstránením tohto cieľového umiestnenia exportu.</span><span class="sxs-lookup"><span data-stu-id="a8bc1-147">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
