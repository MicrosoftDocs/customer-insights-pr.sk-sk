---
title: Export údajov Customer Insights do Omnisend
description: Zistite ako nakonfigurovať pripojenie a realizovať exportovanie do Omnisend.
ms.date: 05/21/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 8bd692819fa8451ded5e74191ee717f81f87425d
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124550"
---
# <a name="export-segments-to-omnisend-preview"></a><span data-ttu-id="17b7a-103">Export segmentov do Omnisend (verzia Preview)</span><span class="sxs-lookup"><span data-stu-id="17b7a-103">Export segments to Omnisend (preview)</span></span>

<span data-ttu-id="17b7a-104">Exportujte segmenty zjednotených profilov zákazníkov do Omnisend a použite ich na marketingové aktivity.</span><span class="sxs-lookup"><span data-stu-id="17b7a-104">Export segments of unified customer profiles to Omnisend and use them for marketing activities.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="17b7a-105">Predpoklady</span><span class="sxs-lookup"><span data-stu-id="17b7a-105">Prerequisites</span></span>

-   <span data-ttu-id="17b7a-106">Máte [účet Omnisend](https://www.omnisend.com/) a zodpovedajúce poverenia správcu.</span><span class="sxs-lookup"><span data-stu-id="17b7a-106">You have an [Omnisend account](https://www.omnisend.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="17b7a-107">Máte [konfigurované segmenty](segments.md) v prehľadoch cieľových skupín.</span><span class="sxs-lookup"><span data-stu-id="17b7a-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="17b7a-108">Zjednotené profily zákazníkov v exportovaných segmentoch obsahujú pole predstavujúce e-mailovú adresu.</span><span class="sxs-lookup"><span data-stu-id="17b7a-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="17b7a-109">Známe obmedzenia</span><span class="sxs-lookup"><span data-stu-id="17b7a-109">Known limitations</span></span>

- <span data-ttu-id="17b7a-110">Pri jednom exporte do Omnisend môžete exportovať až 1 milión profilov a jeho dokončenie môže trvať až 4 hodiny.</span><span class="sxs-lookup"><span data-stu-id="17b7a-110">You can export up to 1 million profiles per export to Omnisend and it can take up to 4 hours to complete.</span></span>
- <span data-ttu-id="17b7a-111">Exportovanie do Omnisend je obmedzené na segmenty.</span><span class="sxs-lookup"><span data-stu-id="17b7a-111">Exporting to Omnisend is limited to segments.</span></span>
- <span data-ttu-id="17b7a-112">Počet profilov, ktoré môžete exportovať do Omnisend, závisí od vašej zmluvy s Omnisend.</span><span class="sxs-lookup"><span data-stu-id="17b7a-112">The number of profiles that you can export to Omnisend depends on your contract with Omnisend.</span></span>

## <a name="set-up-connection-to-omnisend"></a><span data-ttu-id="17b7a-113">Nastavenie pripojenia k Omnisend</span><span class="sxs-lookup"><span data-stu-id="17b7a-113">Set up connection to Omnisend</span></span>

1. <span data-ttu-id="17b7a-114">Prejdite do časti **Správca** > **Pripojenia**.</span><span class="sxs-lookup"><span data-stu-id="17b7a-114">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="17b7a-115">Vyberte **Pridať pripojenie** a výberom možnosti **Omnisend** nakonfigurujte pripojenie.</span><span class="sxs-lookup"><span data-stu-id="17b7a-115">Select **Add connection** and choose **Omnisend** to configure the connection.</span></span>

1. <span data-ttu-id="17b7a-116">Do poľa **Zobrazovaný názov** zadajte rozpoznateľný názov pripojenia.</span><span class="sxs-lookup"><span data-stu-id="17b7a-116">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="17b7a-117">Zobrazovaný názov a typ spojenia, ktoré popisuje toto spojenie.</span><span class="sxs-lookup"><span data-stu-id="17b7a-117">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="17b7a-118">Odporúčame zvoliť názov, ktorý vysvetľuje účel a cieľ tohto spojenia.</span><span class="sxs-lookup"><span data-stu-id="17b7a-118">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="17b7a-119">Vyberte používateľov, ktorí môžu používať toto pripojenie.</span><span class="sxs-lookup"><span data-stu-id="17b7a-119">Choose who can use this connection.</span></span> <span data-ttu-id="17b7a-120">Predvolene sú to iba správcovia.</span><span class="sxs-lookup"><span data-stu-id="17b7a-120">By default it's only administrators.</span></span> <span data-ttu-id="17b7a-121">Viac informácií nájdete v časti [Umožnite prispievateľom použiť pripojenie na export](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="17b7a-121">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="17b7a-122">Zadajte svoj [kľúč API Omnisend](https://support.omnisend.com/en/articles/1061890-generating-api-key).</span><span class="sxs-lookup"><span data-stu-id="17b7a-122">Enter your [Omnisend API key](https://support.omnisend.com/en/articles/1061890-generating-api-key).</span></span>

1. <span data-ttu-id="17b7a-123">Vyberte **Súhlasím** na potvrdenie **Ochrany osobných údajov a dodržiavanie súladu s nariadeniami**.</span><span class="sxs-lookup"><span data-stu-id="17b7a-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="17b7a-124">Stlačte možnosť **Pripojiť** na inicializáciu pripojenia k Omnisend.</span><span class="sxs-lookup"><span data-stu-id="17b7a-124">Select **Connect** to initialize the connection to Omnisend.</span></span>

1. <span data-ttu-id="17b7a-125">Vyberte položku **Pridať samého seba ako používateľa exportu** a uveďte svoje poverenia pre Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="17b7a-125">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="17b7a-126">Stlačte možnosť **Uložiť** a dokončite pripojenie.</span><span class="sxs-lookup"><span data-stu-id="17b7a-126">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="17b7a-127">Nakonfigurujte export</span><span class="sxs-lookup"><span data-stu-id="17b7a-127">Configure an export</span></span>

<span data-ttu-id="17b7a-128">Tento export môžete nakonfigurovať, ak máte prístup k pripojeniu tohto typu.</span><span class="sxs-lookup"><span data-stu-id="17b7a-128">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="17b7a-129">Viac informácií nájdete na stránke [Na konfiguráciu exportu sú potrebné povolenia](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="17b7a-129">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="17b7a-130">Prejdite na **Údaje** > **Exporty**.</span><span class="sxs-lookup"><span data-stu-id="17b7a-130">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="17b7a-131">Na vytvorenie nového exportu stlačte možnosť **Pridať cieľ**.</span><span class="sxs-lookup"><span data-stu-id="17b7a-131">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="17b7a-132">V poli **Pripojenie na export** vyberte pripojenie v časti Omnisend.</span><span class="sxs-lookup"><span data-stu-id="17b7a-132">In the **Connection for export** field, choose a connection from the Omnisend section.</span></span> <span data-ttu-id="17b7a-133">Ak nevidíte názov tejto sekcie, nemáte k dispozícii žiadne spojenia tohto typu.</span><span class="sxs-lookup"><span data-stu-id="17b7a-133">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="17b7a-134">V sekcii **Párovanie údajov** v poli **E-mail** do svojho zjednoteného profilu zákazníka vyberte pole, ktoré predstavuje e-mailovú adresu zákazníka.</span><span class="sxs-lookup"><span data-stu-id="17b7a-134">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="17b7a-135">Je potrebné exportovať segmenty do Omnisend.</span><span class="sxs-lookup"><span data-stu-id="17b7a-135">It's required to export segments to Omnisend.</span></span> <span data-ttu-id="17b7a-136">Voliteľne možno exportovať Meno, Priezvisko, Adresu, Krajinu/oblasť, Štát, Mesto a PSČ a vytvoriť si viac prispôsobené e-maily.</span><span class="sxs-lookup"><span data-stu-id="17b7a-136">Optionally, you can export First name, Last name, Address, Country/Region, State, City, and Post Code to create more personalized emails.</span></span> <span data-ttu-id="17b7a-137">Výberom položky **Pridať atribút** namapujete tieto polia.</span><span class="sxs-lookup"><span data-stu-id="17b7a-137">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="17b7a-138">Vyberte položku **Uložiť**.</span><span class="sxs-lookup"><span data-stu-id="17b7a-138">Select **Save**.</span></span>

<span data-ttu-id="17b7a-139">Uloženie exportu nespustí export okamžite.</span><span class="sxs-lookup"><span data-stu-id="17b7a-139">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="17b7a-140">Export prebieha s každým [plánovaným obnovením](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="17b7a-140">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="17b7a-141">Môžete tiež [exportovať údaje na požiadanie](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="17b7a-141">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="17b7a-142">Ochrana osobných údajov a dodržiavanie súladu s nariadeniami</span><span class="sxs-lookup"><span data-stu-id="17b7a-142">Data privacy and compliance</span></span>

<span data-ttu-id="17b7a-143">Keď povolíte Dynamics 365 Customer Insights na prenos údajov do Ommisend, povolíte prenos údajov mimo hranice súladu s Dynamics 365 Customer Insights, a to vrátane potenciálne citlivých údajov, ako sú napríklad osobné údaje.</span><span class="sxs-lookup"><span data-stu-id="17b7a-143">When you enable Dynamics 365 Customer Insights to transmit data to Ommisend, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="17b7a-144">Spoločnosť Microsoft prenesie tieto údaje na váš pokyn, ale vy ste zodpovední za zabezpečenie toho, aby služba Omnisend spĺňala všetky vaše povinnosti v oblasti ochrany osobných údajov alebo bezpečnosti.</span><span class="sxs-lookup"><span data-stu-id="17b7a-144">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Omnisend meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="17b7a-145">Ďalšie informácie nájdete vo [vyhlásení o ochrane súkromia spoločnosti Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="17b7a-145">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="17b7a-146">Váš správca služby Dynamics 365 Customer Insights môže túto funkciu kedykoľvek prestať používať odstránením tohto cieľového umiestnenia exportu.</span><span class="sxs-lookup"><span data-stu-id="17b7a-146">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
