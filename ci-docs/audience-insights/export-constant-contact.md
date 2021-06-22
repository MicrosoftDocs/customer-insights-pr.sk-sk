---
title: Export údajov Customer Insights do Constant Contact
description: Zistite ako nakonfigurovať pripojenie a realizovať exportovanie do Constant Contact.
ms.date: 03/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 29f4320c798db62609283e3c48f0b47a4f0b982f
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124292"
---
# <a name="export-segments-to-constant-contact-preview"></a><span data-ttu-id="a8d60-103">Export segmentov do Constant Contact (verzia Preview)</span><span class="sxs-lookup"><span data-stu-id="a8d60-103">Export segments to Constant Contact (preview)</span></span>

<span data-ttu-id="a8d60-104">Exportujte segmenty zjednotených profilov zákazníkov do Constant Contact a použite ich na marketingové aktivity.</span><span class="sxs-lookup"><span data-stu-id="a8d60-104">Export segments of unified customer profiles to Constant Contact and use them for marketing activities.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="a8d60-105">Predpoklad na pripojenie</span><span class="sxs-lookup"><span data-stu-id="a8d60-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="a8d60-106">Máte [účet Constant Contact](https://www.constantcontact.com/account-home) a zodpovedajúce poverenia správcu.</span><span class="sxs-lookup"><span data-stu-id="a8d60-106">You have an [Constant Contact account](https://www.constantcontact.com/account-home) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="a8d60-107">Máte [konfigurované segmenty](segments.md) v prehľadoch cieľových skupín.</span><span class="sxs-lookup"><span data-stu-id="a8d60-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="a8d60-108">Zjednotené profily zákazníkov v exportovaných segmentoch obsahujú pole predstavujúce e-mailovú adresu.</span><span class="sxs-lookup"><span data-stu-id="a8d60-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="a8d60-109">Známe obmedzenia</span><span class="sxs-lookup"><span data-stu-id="a8d60-109">Known limitations</span></span>

- <span data-ttu-id="a8d60-110">Na jeden export do 1 miliónov profilov môžete exportovať až Constant Contact.</span><span class="sxs-lookup"><span data-stu-id="a8d60-110">You can export up to 1 million profiles per export to Constant Contact.</span></span>
- <span data-ttu-id="a8d60-111">Exportovanie do Constant Contact je obmedzené na segmenty.</span><span class="sxs-lookup"><span data-stu-id="a8d60-111">Exporting to Constant Contact is limited to segments.</span></span>
- <span data-ttu-id="a8d60-112">Exportovanie až 1 milión profilov do aplikácie Constant Contact môže trvať až 1 hodinu.</span><span class="sxs-lookup"><span data-stu-id="a8d60-112">Exporting up to 1 million profiles to Constant Contact can take up to 1 hour to complete.</span></span> 
- <span data-ttu-id="a8d60-113">Počet profilov, ktoré môžete exportovať do Constant Contact, závisí a je obmedzený na vašu zmluvu so spoločnosťou Constant Contact.</span><span class="sxs-lookup"><span data-stu-id="a8d60-113">The number of profiles that you can export to Constant Contact is dependent and limited on your contract with Constant Contact.</span></span>

## <a name="set-up-connection-to-constant-contact"></a><span data-ttu-id="a8d60-114">Nastavenie pripojenia do Constant Contact</span><span class="sxs-lookup"><span data-stu-id="a8d60-114">Set up connection to Constant Contact</span></span>

1. <span data-ttu-id="a8d60-115">Prejdite do časti **Správca** > **Pripojenia**.</span><span class="sxs-lookup"><span data-stu-id="a8d60-115">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="a8d60-116">Stlačte možnosť **Pridať pripojenie** a stlačením možnosti **Constant Contact** nakonfigurujte pripojenie.</span><span class="sxs-lookup"><span data-stu-id="a8d60-116">Select **Add connection** and choose **Constant Contact** to configure the connection.</span></span>

1. <span data-ttu-id="a8d60-117">Do poľa **Zobrazovaný názov** zadajte rozpoznateľný názov pripojenia.</span><span class="sxs-lookup"><span data-stu-id="a8d60-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="a8d60-118">Zobrazovaný názov a typ spojenia, ktoré popisuje toto spojenie.</span><span class="sxs-lookup"><span data-stu-id="a8d60-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="a8d60-119">Odporúčame zvoliť názov, ktorý vysvetľuje účel a cieľ tohto spojenia.</span><span class="sxs-lookup"><span data-stu-id="a8d60-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="a8d60-120">Vyberte používateľov, ktorí môžu používať toto pripojenie.</span><span class="sxs-lookup"><span data-stu-id="a8d60-120">Choose who can use this connection.</span></span> <span data-ttu-id="a8d60-121">Ak neurobíte nič, predvolená hodnota bude Správcovia.</span><span class="sxs-lookup"><span data-stu-id="a8d60-121">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="a8d60-122">Viac informácií nájdete v časti [Umožnite prispievateľom použiť pripojenie na export](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="a8d60-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="a8d60-123">Vyberte **Súhlasím** na potvrdenie **Ochrany osobných údajov a dodržiavanie súladu s nariadeniami**.</span><span class="sxs-lookup"><span data-stu-id="a8d60-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="a8d60-124">Stlačte možnosť **Pripojiť** na inicializáciu pripojenia k Constant Contact.</span><span class="sxs-lookup"><span data-stu-id="a8d60-124">Select **Connect** to initialize the connection to Constant Contact.</span></span>

1. <span data-ttu-id="a8d60-125">Stlačte možnosť **Overenie pomocou služby AdRoll** a zadajte svoje poverenia správcu pre Constant Contact.</span><span class="sxs-lookup"><span data-stu-id="a8d60-125">Select **Authenticate with AdRoll** and provide your admin credentials for Constant Contact.</span></span> 

1. <span data-ttu-id="a8d60-126">Vyberte položku **Pridať samého seba ako používateľa exportu** a uveďte svoje poverenia pre Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="a8d60-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="a8d60-127">Stlačte možnosť **Uložiť** a dokončite pripojenie.</span><span class="sxs-lookup"><span data-stu-id="a8d60-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="a8d60-128">Nakonfigurujte export</span><span class="sxs-lookup"><span data-stu-id="a8d60-128">Configure an export</span></span>

<span data-ttu-id="a8d60-129">Tento export môžete nakonfigurovať, ak máte prístup k pripojeniu tohto typu.</span><span class="sxs-lookup"><span data-stu-id="a8d60-129">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="a8d60-130">Viac informácií nájdete na stránke [Na konfiguráciu exportu sú potrebné povolenia](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="a8d60-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="a8d60-131">Prejdite na **Údaje** > **Exporty**.</span><span class="sxs-lookup"><span data-stu-id="a8d60-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="a8d60-132">Na vytvorenie nového exportu stlačte možnosť **Pridať cieľ**.</span><span class="sxs-lookup"><span data-stu-id="a8d60-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="a8d60-133">V poli **Pripojenie na export** vyberte pripojenie v časti Constant Contact.</span><span class="sxs-lookup"><span data-stu-id="a8d60-133">In the **Connection for export** field, choose a connection from the Constant Contact section.</span></span> <span data-ttu-id="a8d60-134">Ak nevidíte názov tejto sekcie, nemáte k dispozícii žiadne spojenia tohto typu.</span><span class="sxs-lookup"><span data-stu-id="a8d60-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="a8d60-135">Zadajte [**Identifikátor zoznamu Constant Contact**](https://app.constantcontact.com/pages/contacts/ui#lists).</span><span class="sxs-lookup"><span data-stu-id="a8d60-135">Enter your [**Constant Contact List ID**](https://app.constantcontact.com/pages/contacts/ui#lists).</span></span> <span data-ttu-id="a8d60-136">Otvorte zoznam v zozname Constant Contact a vyhľadajte identifikátor zoznamu v adrese URL.</span><span class="sxs-lookup"><span data-stu-id="a8d60-136">Open a list in Constant Contact to find the list ID in the URL.</span></span>

1. <span data-ttu-id="a8d60-137">V sekcii **Párovanie údajov** v poli **E-mail** do svojho zjednoteného profilu zákazníka vyberte pole, ktoré predstavuje e-mailovú adresu zákazníka.</span><span class="sxs-lookup"><span data-stu-id="a8d60-137">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="a8d60-138">Je potrebné exportovať segmenty do Constant Contact.</span><span class="sxs-lookup"><span data-stu-id="a8d60-138">It's required to export segments to Constant Contact.</span></span>

1. <span data-ttu-id="a8d60-139">Prípadne môžete exportovať Krstné meno a Priezvisko ako dodatočné polia na vytvorenie viac prispôsobených e-mailov.</span><span class="sxs-lookup"><span data-stu-id="a8d60-139">Optionally, you can export First name and Last name as additional fields to create more personalized emails.</span></span> <span data-ttu-id="a8d60-140">Výberom položky **Pridať atribút** namapujete tieto polia.</span><span class="sxs-lookup"><span data-stu-id="a8d60-140">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="a8d60-141">Vyberte segmenty, ktoré chcete exportovať.</span><span class="sxs-lookup"><span data-stu-id="a8d60-141">Select the segments you want to export.</span></span>

1. <span data-ttu-id="a8d60-142">Vyberte položku **Uložiť**.</span><span class="sxs-lookup"><span data-stu-id="a8d60-142">Select **Save**.</span></span>

<span data-ttu-id="a8d60-143">Uloženie exportu nespustí export okamžite.</span><span class="sxs-lookup"><span data-stu-id="a8d60-143">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="a8d60-144">Export prebieha s každým [plánovaným obnovením](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="a8d60-144">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="a8d60-145">Môžete tiež [exportovať údaje na požiadanie](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="a8d60-145">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="a8d60-146">Ochrana osobných údajov a dodržiavanie súladu s nariadeniami</span><span class="sxs-lookup"><span data-stu-id="a8d60-146">Data privacy and compliance</span></span>

<span data-ttu-id="a8d60-147">Keď povolíte Dynamics 365 Customer Insights na prenos údajov do Constant Contact, povolíte prenos údajov mimo hranice súladu s Dynamics 365 Customer Insights, a to vrátane potenciálne citlivých údajov, ako sú napríklad osobné údaje.</span><span class="sxs-lookup"><span data-stu-id="a8d60-147">When you enable Dynamics 365 Customer Insights to transmit data to Constant Contact, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="a8d60-148">Spoločnosť Microsoft prenesie tieto údaje na váš pokyn, ale vy ste zodpovední za zabezpečenie toho, aby služba Constant Contact spĺňala všetky vaše povinnosti v oblasti ochrany osobných údajov alebo bezpečnosti.</span><span class="sxs-lookup"><span data-stu-id="a8d60-148">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Constant Contact meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="a8d60-149">Ďalšie informácie nájdete vo [vyhlásení o ochrane súkromia spoločnosti Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="a8d60-149">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="a8d60-150">Váš správca služby Dynamics 365 Customer Insights môže túto funkciu kedykoľvek prestať používať odstránením tohto cieľového umiestnenia exportu.</span><span class="sxs-lookup"><span data-stu-id="a8d60-150">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
