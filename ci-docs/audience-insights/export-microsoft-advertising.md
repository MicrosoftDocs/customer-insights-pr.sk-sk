---
title: Export údajov služby Customer Insights do Microsoft Advertising
description: Zistite ako nakonfigurovať pripojenie a realizovať exportovanie do Microsoft Advertising.
ms.date: 05/12/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: c2ac92de2718cf7f0622b407bf198a7a7e50a37b
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124549"
---
# <a name="export-segments-to-microsoft-advertising-preview"></a><span data-ttu-id="101fc-103">Export segmentov do služby Microsoft Advertising (verzia Preview)</span><span class="sxs-lookup"><span data-stu-id="101fc-103">Export segments to Microsoft Advertising (preview)</span></span>

<span data-ttu-id="101fc-104">Exportujte segmenty Customer Insights do služby Microsoft Advertising a vytvorte cieľovú skupinu súladu so zákazníkmi.</span><span class="sxs-lookup"><span data-stu-id="101fc-104">Export Customer Insights segments to Microsoft Advertising to create Customer Match audiences.</span></span> <span data-ttu-id="101fc-105">Použite tieto cieľové skupiny pre svoje reklamné kampane.</span><span class="sxs-lookup"><span data-stu-id="101fc-105">Use these audiences for your ad campaigns.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="101fc-106">Predpoklady</span><span class="sxs-lookup"><span data-stu-id="101fc-106">Prerequisites</span></span>

-   <span data-ttu-id="101fc-107">[Účet Microsoft Advertising](https://ads.microsoft.com/) a zodpovedajúce poverenia správcu.</span><span class="sxs-lookup"><span data-stu-id="101fc-107">An [Microsoft Advertising account](https://ads.microsoft.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="101fc-108">Prijali ste podmienky používania súladu so zákazníkmi.</span><span class="sxs-lookup"><span data-stu-id="101fc-108">You've accepted the Customer Match terms of use.</span></span> 
-   <span data-ttu-id="101fc-109">[Konfigurované segmenty](segments.md) v prehľadoch cieľových skupín.</span><span class="sxs-lookup"><span data-stu-id="101fc-109">[Configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="101fc-110">Zjednotené profily zákazníkov v exportovaných segmentoch obsahujú pole s e-mailovou adresou.</span><span class="sxs-lookup"><span data-stu-id="101fc-110">Unified customer profiles in the exported segments contain a field with an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="101fc-111">Známe obmedzenia</span><span class="sxs-lookup"><span data-stu-id="101fc-111">Known limitations</span></span>

- <span data-ttu-id="101fc-112">Na jeden export môžete exportovať do Microsoft Advertising až 500 tis. profilov.</span><span class="sxs-lookup"><span data-stu-id="101fc-112">You can export up to 500 K profiles per export to Microsoft Advertising.</span></span>
- <span data-ttu-id="101fc-113">Exportovanie do Microsoft Advertising je obmedzené na segmenty.</span><span class="sxs-lookup"><span data-stu-id="101fc-113">Exporting to Microsoft Advertising is limited to segments.</span></span>
- <span data-ttu-id="101fc-114">Exportovanie až 500 tis. profilov do aplikácie Microsoft Advertising môže trvať až 10 minút.</span><span class="sxs-lookup"><span data-stu-id="101fc-114">Exporting up to 500 K profiles to Microsoft Advertising can take up to 10 minutes to complete.</span></span> 


## <a name="set-up-the-connection-to-microsoft-advertising"></a><span data-ttu-id="101fc-115">Nastavenie pripojenia do Microsoft Advertising</span><span class="sxs-lookup"><span data-stu-id="101fc-115">Set up the connection to Microsoft Advertising</span></span>

1. <span data-ttu-id="101fc-116">Prejdite do časti **Správca** > **Pripojenia**.</span><span class="sxs-lookup"><span data-stu-id="101fc-116">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="101fc-117">Vyberte **Pridať pripojenie** a výberom možnosti **Microsoft Advertising** nakonfigurujte pripojenie.</span><span class="sxs-lookup"><span data-stu-id="101fc-117">Select **Add connection** and choose **Microsoft Advertising** to configure the connection.</span></span>

1. <span data-ttu-id="101fc-118">Do poľa **Zobrazovaný názov** zadajte rozpoznateľný názov pripojenia.</span><span class="sxs-lookup"><span data-stu-id="101fc-118">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="101fc-119">Zobrazovaný názov a typ spojenia, ktoré popisuje toto spojenie.</span><span class="sxs-lookup"><span data-stu-id="101fc-119">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="101fc-120">Odporúčame zvoliť názov, ktorý vysvetľuje účel a cieľ tohto spojenia.</span><span class="sxs-lookup"><span data-stu-id="101fc-120">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="101fc-121">Vyberte používateľov, ktorí môžu používať toto pripojenie.</span><span class="sxs-lookup"><span data-stu-id="101fc-121">Choose who can use this connection.</span></span> <span data-ttu-id="101fc-122">Predvolená hodnota je správcovia.</span><span class="sxs-lookup"><span data-stu-id="101fc-122">The default is administrators.</span></span> <span data-ttu-id="101fc-123">Viac informácií nájdete v časti [Umožnite prispievateľom použiť pripojenie na export](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="101fc-123">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="101fc-124">Vyberte **Súhlasím** na potvrdenie **Ochrany osobných údajov a dodržiavanie súladu s nariadeniami**.</span><span class="sxs-lookup"><span data-stu-id="101fc-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="101fc-125">Stlačte možnosť **Pripojiť** na inicializáciu pripojenia k Microsoft Advertising.</span><span class="sxs-lookup"><span data-stu-id="101fc-125">Select **Connect** to initialize the connection to Microsoft Advertising.</span></span>

1. <span data-ttu-id="101fc-126">Stlačte možnosť **Overenie pomocou služby Microsoft Advertising** a zadajte svoje poverenia správcu pre Microsoft Advertising.</span><span class="sxs-lookup"><span data-stu-id="101fc-126">Select **Authenticate with Microsoft Advertising** and provide your admin credentials for Microsoft Advertising.</span></span>

1. <span data-ttu-id="101fc-127">Vyberte položku **Pridať samého seba ako používateľa exportu** a uveďte svoje poverenia pre Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="101fc-127">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="101fc-128">Stlačte možnosť **Uložiť** a dokončite pripojenie.</span><span class="sxs-lookup"><span data-stu-id="101fc-128">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="101fc-129">Nakonfigurujte export</span><span class="sxs-lookup"><span data-stu-id="101fc-129">Configure an export</span></span>

<span data-ttu-id="101fc-130">Tento export môžete nakonfigurovať, ak máte prístup k pripojeniu tohto typu.</span><span class="sxs-lookup"><span data-stu-id="101fc-130">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="101fc-131">Viac informácií nájdete na stránke [Na konfiguráciu exportu sú potrebné povolenia](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="101fc-131">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="101fc-132">Prejdite na **Údaje** > **Exporty**.</span><span class="sxs-lookup"><span data-stu-id="101fc-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="101fc-133">Na vytvorenie nového exportu stlačte možnosť **Pridať cieľ**.</span><span class="sxs-lookup"><span data-stu-id="101fc-133">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="101fc-134">V poli **Pripojenie na export** vyberte pripojenie v časti Microsoft Advertising.</span><span class="sxs-lookup"><span data-stu-id="101fc-134">In the **Connection for export** field, choose a connection from the Microsoft Advertising section.</span></span> <span data-ttu-id="101fc-135">Ak nevidíte názov tejto sekcie, nemáte k dispozícii žiadne spojenia tohto typu.</span><span class="sxs-lookup"><span data-stu-id="101fc-135">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="101fc-136">Vyberte segmenty, ktoré chcete exportovať.</span><span class="sxs-lookup"><span data-stu-id="101fc-136">Select the segments to export.</span></span> <span data-ttu-id="101fc-137">Cieľové skupiny súladu so zákazníkmi v službe Microsoft Advertising sa automaticky vytvárajú s názvom segmentov vybratých na export.</span><span class="sxs-lookup"><span data-stu-id="101fc-137">The Customer Match audiences in Microsoft Advertising are automatically created with the name of the segments selected for export.</span></span> <span data-ttu-id="101fc-138">Výsledkom každého segmentu bude samostatná cieľová skupina súladu so zákazníkmi.</span><span class="sxs-lookup"><span data-stu-id="101fc-138">Each segment will result in a separate Customer Match audience.</span></span> 

1. <span data-ttu-id="101fc-139">Zadajte svoje **ID zákazníka Microsoft Advertising a ID konta**.</span><span class="sxs-lookup"><span data-stu-id="101fc-139">Enter your **Microsoft Advertising Customer ID and Account ID**.</span></span> <span data-ttu-id="101fc-140">ID zákazníka (`cid`) a ID obchodného vzťahu (`aid`) v parametroch adresy URL, keď ste prihlásení do služby Microsoft Advertising.</span><span class="sxs-lookup"><span data-stu-id="101fc-140">You can find the Customer ID (`cid`) and Account ID (`aid`) in the parameters of the URL when you're signed in Microsoft Advertising.</span></span>

1. <span data-ttu-id="101fc-141">V sekcii **Párovanie údajov** v poli **E-mail** vyberte pole vo svojom zjednotenom profile zákazníka s e-mailovou adresou zákazníka.</span><span class="sxs-lookup"><span data-stu-id="101fc-141">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile with a customer's email address.</span></span> <span data-ttu-id="101fc-142">Je potrebné exportovať segmenty do Microsoft Advertising.</span><span class="sxs-lookup"><span data-stu-id="101fc-142">It's required to export segments to Microsoft Advertising.</span></span>

1. <span data-ttu-id="101fc-143">Vyberte položku **Uložiť**.</span><span class="sxs-lookup"><span data-stu-id="101fc-143">Select **Save**.</span></span>

<span data-ttu-id="101fc-144">Uloženie exportu nespustí export okamžite.</span><span class="sxs-lookup"><span data-stu-id="101fc-144">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="101fc-145">Export prebieha s každým [plánovaným obnovením](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="101fc-145">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="101fc-146">Môžete tiež [exportovať údaje na požiadanie](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="101fc-146">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="101fc-147">Ochrana osobných údajov a dodržiavanie súladu s nariadeniami</span><span class="sxs-lookup"><span data-stu-id="101fc-147">Data privacy and compliance</span></span>

<span data-ttu-id="101fc-148">Keď povolíte Dynamics 365 Customer Insights na prenos údajov do Microsoft Advertising, povolíte prenos údajov mimo hranice súladu pre Dynamics 365 Customer Insights, a to vrátane potenciálne citlivých údajov, ako sú napríklad osobné údaje.</span><span class="sxs-lookup"><span data-stu-id="101fc-148">When you enable Dynamics 365 Customer Insights to transmit data to Microsoft Advertising, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="101fc-149">Spoločnosť Microsoft prenesie tieto údaje na váš pokyn, ale vy ste zodpovední za zabezpečenie toho, aby služba Microsoft Advertising spĺňala všetky vaše povinnosti v oblasti ochrany osobných údajov alebo bezpečnosti.</span><span class="sxs-lookup"><span data-stu-id="101fc-149">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Microsoft Advertising meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="101fc-150">Ďalšie informácie nájdete vo [vyhlásení o ochrane súkromia spoločnosti Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="101fc-150">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="101fc-151">Túto funkciu môžete kedykoľvek prestať používať odstránením tohto cieľového umiestnenia exportu správcom služby Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="101fc-151">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to stop use of this functionality.</span></span>
