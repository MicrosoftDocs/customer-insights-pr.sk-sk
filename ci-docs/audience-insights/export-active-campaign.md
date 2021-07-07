---
title: Export údajov z Customer Insights do ActiveCampaign
description: Zistite, ako nakonfigurovať pripojenie a exportovať do ActiveCampaign.
ms.date: 06/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6d85fa9836618e27f7f3da6ce17c07b4bc89e187
ms.sourcegitcommit: 057079532e31c12bac36f374857ba3dc847d6ad0
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 06/29/2021
ms.locfileid: "6314674"
---
# <a name="export-segments-to-activecampaign-preview"></a><span data-ttu-id="23a24-103">Export segmentov do ActiveCampaign (verzia Preview)</span><span class="sxs-lookup"><span data-stu-id="23a24-103">Export segments to ActiveCampaign (preview)</span></span>

<span data-ttu-id="23a24-104">Exportujte segmenty zjednotených profilov zákazníkov do ActiveCampaign a použite ich na marketingové aktivity.</span><span class="sxs-lookup"><span data-stu-id="23a24-104">Export segments of unified customer profiles to ActiveCampaign and use them for marketing activities.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="23a24-105">Predpoklady</span><span class="sxs-lookup"><span data-stu-id="23a24-105">Prerequisites</span></span>

-   <span data-ttu-id="23a24-106">Máte [účet ActiveCampaign](https://www.activecampaign.com/) a zodpovedajúce poverenia správcu.</span><span class="sxs-lookup"><span data-stu-id="23a24-106">You have an [ActiveCampaign account](https://www.activecampaign.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="23a24-107">Máte [konfigurované segmenty](segments.md) v prehľadoch cieľových skupín.</span><span class="sxs-lookup"><span data-stu-id="23a24-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="23a24-108">Zjednotené profily zákazníkov v exportovaných segmentoch obsahujú pole s e-mailovou adresou.</span><span class="sxs-lookup"><span data-stu-id="23a24-108">Unified customer profiles in the exported segments contain a field with an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="23a24-109">Známe obmedzenia</span><span class="sxs-lookup"><span data-stu-id="23a24-109">Known limitations</span></span>

- <span data-ttu-id="23a24-110">Na jeden export môžete do ActiveCampaign exportovať až 1 milión profilov a jeho dokončenie môže trvať až 90 minút.</span><span class="sxs-lookup"><span data-stu-id="23a24-110">You can export up to 1 million profiles per export to ActiveCampaign and it can take up to 90 minutes to complete.</span></span>
- <span data-ttu-id="23a24-111">Export do ActiveCampaign je obmedzený na segmenty.</span><span class="sxs-lookup"><span data-stu-id="23a24-111">Exporting to ActiveCampaign is limited to segments.</span></span>
- <span data-ttu-id="23a24-112">Počet profilov, ktoré môžete exportovať do ActiveCampaign, závisí od vašej zmluvy s ActiveCampaign.</span><span class="sxs-lookup"><span data-stu-id="23a24-112">The number of profiles that you can export to ActiveCampaign depends on your contract with ActiveCampaign.</span></span>

## <a name="set-up-connection-to-activecampaign"></a><span data-ttu-id="23a24-113">Nastavenie pripojenia k ActiveCampaign</span><span class="sxs-lookup"><span data-stu-id="23a24-113">Set up connection to ActiveCampaign</span></span>

1. <span data-ttu-id="23a24-114">Prejdite do časti **Správca** > **Pripojenia**.</span><span class="sxs-lookup"><span data-stu-id="23a24-114">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="23a24-115">Vyberte možnosť **Pridať pripojenie** a výberom položky **ActiveCampaign** nakonfigurujte pripojenie.</span><span class="sxs-lookup"><span data-stu-id="23a24-115">Select **Add connection** and choose **ActiveCampaign** to configure the connection.</span></span>

1. <span data-ttu-id="23a24-116">Do poľa **Zobrazovaný názov** zadajte rozpoznateľný názov pripojenia.</span><span class="sxs-lookup"><span data-stu-id="23a24-116">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="23a24-117">Zobrazovaný názov a typ spojenia, ktoré popisuje toto spojenie.</span><span class="sxs-lookup"><span data-stu-id="23a24-117">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="23a24-118">Odporúčame zvoliť názov, ktorý vysvetľuje účel a cieľ tohto spojenia.</span><span class="sxs-lookup"><span data-stu-id="23a24-118">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="23a24-119">Vyberte používateľov, ktorí môžu používať toto pripojenie.</span><span class="sxs-lookup"><span data-stu-id="23a24-119">Choose who can use this connection.</span></span> <span data-ttu-id="23a24-120">Predvolene sú to iba správcovia.</span><span class="sxs-lookup"><span data-stu-id="23a24-120">By default, it's only administrators.</span></span> <span data-ttu-id="23a24-121">Viac informácií nájdete v časti [Umožnite prispievateľom použiť pripojenie na export](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="23a24-121">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="23a24-122">Zadajte svoj [kľúč rozhrania API ActiveCampaign a názov hostiteľa koncového bodu REST](https://help.activecampaign.com/hc/articles/207317590-Getting-started-with-the-API#how-to-obtain-your-activecampaign-api-url-and-key).</span><span class="sxs-lookup"><span data-stu-id="23a24-122">Enter your [ActiveCampaign API Key and REST Endpoint Hostname](https://help.activecampaign.com/hc/articles/207317590-Getting-started-with-the-API#how-to-obtain-your-activecampaign-api-url-and-key).</span></span> <span data-ttu-id="23a24-123">Názov hostiteľa koncového bodu REST je iba názov hostiteľa bez https://.</span><span class="sxs-lookup"><span data-stu-id="23a24-123">The REST Endpoint Hostname is the hostname only, without https://.</span></span> 

1. <span data-ttu-id="23a24-124">Vyberte **Súhlasím** na potvrdenie **Ochrany osobných údajov a dodržiavanie súladu s nariadeniami**.</span><span class="sxs-lookup"><span data-stu-id="23a24-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="23a24-125">Výberom možnosti **Pripojiť** nadviažete pripojenie k ActiveCampaign.</span><span class="sxs-lookup"><span data-stu-id="23a24-125">Select **Connect** to initialize the connection to ActiveCampaign.</span></span>

1. <span data-ttu-id="23a24-126">Vyberte položku **Pridať samého seba ako používateľa exportu** a uveďte svoje poverenia pre Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="23a24-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="23a24-127">Stlačte možnosť **Uložiť** a dokončite pripojenie.</span><span class="sxs-lookup"><span data-stu-id="23a24-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="23a24-128">Nakonfigurujte export</span><span class="sxs-lookup"><span data-stu-id="23a24-128">Configure an export</span></span>

<span data-ttu-id="23a24-129">Export môžete nakonfigurovať, ak máte prístup k pripojeniu tohto typu.</span><span class="sxs-lookup"><span data-stu-id="23a24-129">You can configure an export if you have access to a connection of this type.</span></span> <span data-ttu-id="23a24-130">Viac informácií nájdete na stránke [Na konfiguráciu exportu sú potrebné povolenia](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="23a24-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="23a24-131">Prejdite na **Údaje** > **Exporty**.</span><span class="sxs-lookup"><span data-stu-id="23a24-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="23a24-132">Na vytvorenie nového exportu stlačte možnosť **Pridať cieľ**.</span><span class="sxs-lookup"><span data-stu-id="23a24-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="23a24-133">V poli **Pripojenie na export** vyberte pripojenie zo sekcie ActiveCampaign.</span><span class="sxs-lookup"><span data-stu-id="23a24-133">In the **Connection for export** field, choose a connection from the ActiveCampaign section.</span></span> <span data-ttu-id="23a24-134">Ak nevidíte názov tejto sekcie, nemáte k dispozícii žiadne spojenia tohto typu.</span><span class="sxs-lookup"><span data-stu-id="23a24-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="23a24-135">Zadajte svoje [**ID zoznamu aplikácie ActiveCampaign**](https://help.activecampaign.com/hc/articles/360000030559-How-to-create-a-list-in-ActiveCampaign).</span><span class="sxs-lookup"><span data-stu-id="23a24-135">Enter your [**ActiveCampaign List ID**](https://help.activecampaign.com/hc/articles/360000030559-How-to-create-a-list-in-ActiveCampaign).</span></span>    

3. <span data-ttu-id="23a24-136">V sekcii **Párovanie údajov** v poli **E-mail** do svojho zjednoteného profilu zákazníka vyberte pole, ktoré predstavuje e-mailovú adresu zákazníka.</span><span class="sxs-lookup"><span data-stu-id="23a24-136">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="23a24-137">Je to potrebné na export segmentov do ActiveCampaign.</span><span class="sxs-lookup"><span data-stu-id="23a24-137">It's required to export segments to ActiveCampaign.</span></span> <span data-ttu-id="23a24-138">Prípadne môžete aj exportovať krstné meno, priezvisko a telefón, a vytvoriť tak prispôsobenejšie e-maily.</span><span class="sxs-lookup"><span data-stu-id="23a24-138">Optionally, you can export First name, Last name, and Phone to create more personalized emails.</span></span> <span data-ttu-id="23a24-139">Výberom položky Pridať atribút namapujete tieto polia.</span><span class="sxs-lookup"><span data-stu-id="23a24-139">Select Add attribute to map these fields.</span></span>

1. <span data-ttu-id="23a24-140">Vyberte položku **Uložiť**.</span><span class="sxs-lookup"><span data-stu-id="23a24-140">Select **Save**.</span></span>

<span data-ttu-id="23a24-141">Uloženie exportu nespustí export okamžite.</span><span class="sxs-lookup"><span data-stu-id="23a24-141">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="23a24-142">Export prebieha s každým [plánovaným obnovením](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="23a24-142">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="23a24-143">Môžete tiež [exportovať údaje na požiadanie](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="23a24-143">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="23a24-144">Ochrana osobných údajov a dodržiavanie súladu s nariadeniami</span><span class="sxs-lookup"><span data-stu-id="23a24-144">Data privacy and compliance</span></span>

<span data-ttu-id="23a24-145">Keď povolíte službe Dynamics 365 Customer Insights, aby prenášala údaje do ActiveCampaign, povoľujete tým aj prenos údajov mimo hranice súladu so službou Dynamics 365 Customer Insights vrátane potenciálne citlivých údajov, ako sú napríklad osobné údaje.</span><span class="sxs-lookup"><span data-stu-id="23a24-145">When you enable Dynamics 365 Customer Insights to transmit data to ActiveCampaign, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="23a24-146">Microsoft prenesie tieto údaje na váš pokyn, ale vy ste zodpovední za zabezpečenie toho, aby ActiveCampaign spĺňal všetky záväzky týkajúce sa ochrany vášho súkromia alebo bezpečnosti.</span><span class="sxs-lookup"><span data-stu-id="23a24-146">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that ActiveCampaign meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="23a24-147">Ďalšie informácie nájdete vo [vyhlásení o ochrane súkromia spoločnosti Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="23a24-147">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="23a24-148">Váš správca služby Dynamics 365 Customer Insights môže túto funkciu kedykoľvek prestať používať odstránením tohto cieľového umiestnenia exportu.</span><span class="sxs-lookup"><span data-stu-id="23a24-148">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
