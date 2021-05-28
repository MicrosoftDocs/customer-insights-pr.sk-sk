---
title: Export údajov služby Customer Insights do Mailchimp
description: Zistite ako nakonfigurovať pripojenie a realizovať exportovanie do Mailchimp.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 35848998e738c7ecc1642f2b75912ff78d85f79e
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976174"
---
# <a name="export-segment-lists-to-mailchimp-preview"></a><span data-ttu-id="7f0b3-103">Exportovanie zoznamov segmentov do Mailchimp (ukážka)</span><span class="sxs-lookup"><span data-stu-id="7f0b3-103">Export segment lists to Mailchimp (preview)</span></span>

<span data-ttu-id="7f0b3-104">Exportujte segmenty zjednotených profilov zákazníkov do služby Mailchimp a vytvárajte bulletiny a e-mailové kampane.</span><span class="sxs-lookup"><span data-stu-id="7f0b3-104">Export segments of unified customer profiles to Mailchimp to create newsletters and email campaigns.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="7f0b3-105">Predpoklad na pripojenie</span><span class="sxs-lookup"><span data-stu-id="7f0b3-105">Prerequisites for connection</span></span>

-   <span data-ttu-id="7f0b3-106">Máte [účet Mailchimp](https://mailchimp.com/) a zodpovedajúce poverenia správcu.</span><span class="sxs-lookup"><span data-stu-id="7f0b3-106">You have a [Mailchimp account](https://mailchimp.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="7f0b3-107">V Mailchimp a zodpovedajúcich ID existujú cieľové skupiny.</span><span class="sxs-lookup"><span data-stu-id="7f0b3-107">There are existing audiences in Mailchimp and the corresponding IDs.</span></span> <span data-ttu-id="7f0b3-108">Ďalšie informácie nájdete v časti [Cieľové skupiny Mailchimp](https://mailchimp.com/help/create-audience/).</span><span class="sxs-lookup"><span data-stu-id="7f0b3-108">For more information, see [Mailchimp audiences](https://mailchimp.com/help/create-audience/).</span></span>
-   <span data-ttu-id="7f0b3-109">Máte [nakonfigurované segmenty](segments.md)</span><span class="sxs-lookup"><span data-stu-id="7f0b3-109">You have [configured segments](segments.md)</span></span>
-   <span data-ttu-id="7f0b3-110">Zjednotené profily zákazníkov v exportovaných segmentoch obsahujú pole predstavujúce e-mailovú adresu.</span><span class="sxs-lookup"><span data-stu-id="7f0b3-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="7f0b3-111">Známe obmedzenia</span><span class="sxs-lookup"><span data-stu-id="7f0b3-111">Known limitations</span></span>

- <span data-ttu-id="7f0b3-112">Až 1 milión profilov na export do Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="7f0b3-112">Up to 1 million profiles per export to Mailchimp.</span></span>
- <span data-ttu-id="7f0b3-113">Export do Mailchimp je obmedzený na segmenty.</span><span class="sxs-lookup"><span data-stu-id="7f0b3-113">Exporting to Mailchimp is limited to segments.</span></span>
- <span data-ttu-id="7f0b3-114">Export segmentov s miliónom profilov môže trvať až tri hodiny.</span><span class="sxs-lookup"><span data-stu-id="7f0b3-114">Exporting segments with 1 million profiles can take up to three hours.</span></span> 
- <span data-ttu-id="7f0b3-115">Počet profilov, ktoré môžete exportovať do Mailchimp, závisí a je obmedzený vašou zmluvou so spoločnosťou Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="7f0b3-115">The number of profiles that you can export to Mailchimp is dependent and limited on your contract with Mailchimp.</span></span>

## <a name="set-up-connection-to-mailchimp"></a><span data-ttu-id="7f0b3-116">Nastavenie pripojenia k Mailchimp</span><span class="sxs-lookup"><span data-stu-id="7f0b3-116">Set up connection to Mailchimp</span></span>

1. <span data-ttu-id="7f0b3-117">Prejdite do časti **Správca** > **Pripojenia**.</span><span class="sxs-lookup"><span data-stu-id="7f0b3-117">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="7f0b3-118">Stlačte možnosť **Pridať pripojenie** a stlačením možnosti **Autopilot** nakonfigurujte pripojenie.</span><span class="sxs-lookup"><span data-stu-id="7f0b3-118">Select **Add connection** and choose **Autopilot** to configure the connection.</span></span>

1. <span data-ttu-id="7f0b3-119">Do poľa **Zobrazovaný názov** zadajte rozpoznateľný názov pripojenia.</span><span class="sxs-lookup"><span data-stu-id="7f0b3-119">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="7f0b3-120">Zobrazovaný názov a typ spojenia, ktoré popisuje toto spojenie.</span><span class="sxs-lookup"><span data-stu-id="7f0b3-120">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="7f0b3-121">Odporúčame zvoliť názov, ktorý vysvetľuje účel a cieľ tohto spojenia.</span><span class="sxs-lookup"><span data-stu-id="7f0b3-121">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="7f0b3-122">Vyberte používateľov, ktorí môžu používať toto pripojenie.</span><span class="sxs-lookup"><span data-stu-id="7f0b3-122">Choose who can use this connection.</span></span> <span data-ttu-id="7f0b3-123">Ak neurobíte nič, predvolená hodnota bude Správcovia.</span><span class="sxs-lookup"><span data-stu-id="7f0b3-123">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="7f0b3-124">Viac informácií nájdete v časti [Umožnite prispievateľom použiť pripojenie na export](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="7f0b3-124">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="7f0b3-125">Vyberte **Súhlasím** na potvrdenie **Ochrany osobných údajov a dodržiavanie súladu s nariadeniami**.</span><span class="sxs-lookup"><span data-stu-id="7f0b3-125">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="7f0b3-126">Stlačte možnosť **Pripojiť** na inicializáciu pripojenia k Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="7f0b3-126">Select **Connect** to initialize the connection to Mailchimp.</span></span>

1. <span data-ttu-id="7f0b3-127">Vyberte položku **Overenie pomocou služby Mailchimp** a poskytnite svoje poverenia pre Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="7f0b3-127">Select **Authenticate with Mailchimp** and provide your Mailchimp credentials.</span></span>

1. <span data-ttu-id="7f0b3-128">Vyberte položku **Pridať samého seba ako používateľa exportu** a uveďte svoje poverenia pre Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="7f0b3-128">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="7f0b3-129">Stlačte možnosť **Uložiť** a dokončite pripojenie.</span><span class="sxs-lookup"><span data-stu-id="7f0b3-129">Select **Save** to complete the connection.</span></span> 

## <a name="configure-the-connector"></a><span data-ttu-id="7f0b3-130">Nakonfigurujte konektor</span><span class="sxs-lookup"><span data-stu-id="7f0b3-130">Configure the connector</span></span>

<span data-ttu-id="7f0b3-131">Tento export môžete nakonfigurovať, ak máte prístup k pripojeniu tohto typu.</span><span class="sxs-lookup"><span data-stu-id="7f0b3-131">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="7f0b3-132">Viac informácií nájdete na stránke [Na konfiguráciu exportu sú potrebné povolenia](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="7f0b3-132">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="7f0b3-133">Prejdite na **Údaje**> **Exporty**.</span><span class="sxs-lookup"><span data-stu-id="7f0b3-133">Go to **Data**> **Exports**.</span></span>

1. <span data-ttu-id="7f0b3-134">Na vytvorenie nového exportu stlačte možnosť **Pridať cieľ**.</span><span class="sxs-lookup"><span data-stu-id="7f0b3-134">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="7f0b3-135">V poli **Pripojenie na export** vyberte pripojenie v časti Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="7f0b3-135">In the **Connection for export** field, choose a connection from the Mailchimp section.</span></span> <span data-ttu-id="7f0b3-136">Ak nevidíte názov tejto sekcie, nemáte k dispozícii žiadne spojenia tohto typu.</span><span class="sxs-lookup"><span data-stu-id="7f0b3-136">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="7f0b3-137">Zadajte svoj **[identifikátor cieľovej skupiny Mailchimp](https://mailchimp.com/help/find-audience-id/)**</span><span class="sxs-lookup"><span data-stu-id="7f0b3-137">Enter your **[Mailchimp audience ID](https://mailchimp.com/help/find-audience-id/)**</span></span>

3. <span data-ttu-id="7f0b3-138">V sekcii **Párovanie údajov** v poli **E-mail** do svojho zjednoteného profilu zákazníka vyberte pole, ktoré predstavuje e-mailovú adresu zákazníka.</span><span class="sxs-lookup"><span data-stu-id="7f0b3-138">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="7f0b3-139">Voliteľné možno exportovať **Krstné meno** a **Priezvisko** a vytvorte si viac prispôsobené e-maily.</span><span class="sxs-lookup"><span data-stu-id="7f0b3-139">Optionally, you can export **First name** and **Last name** to create more personalized emails.</span></span> <span data-ttu-id="7f0b3-140">Výberom položky **Pridať atribút** namapujete tieto polia.</span><span class="sxs-lookup"><span data-stu-id="7f0b3-140">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="7f0b3-141">Vyberte segmenty, ktoré chcete exportovať.</span><span class="sxs-lookup"><span data-stu-id="7f0b3-141">Select the segments you want to export.</span></span> <span data-ttu-id="7f0b3-142">Do služby Mailchimp môžete exportovať spolu až 1 milión zákazníckych profilov.</span><span class="sxs-lookup"><span data-stu-id="7f0b3-142">You can export up to 1 million customer profiles in total to Mailchimp.</span></span>

1. <span data-ttu-id="7f0b3-143">Vyberte položku **Uložiť**.</span><span class="sxs-lookup"><span data-stu-id="7f0b3-143">Select **Save**.</span></span>

<span data-ttu-id="7f0b3-144">Uloženie exportu nespustí export okamžite.</span><span class="sxs-lookup"><span data-stu-id="7f0b3-144">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="7f0b3-145">Export prebieha s každým [plánovaným obnovením](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="7f0b3-145">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="7f0b3-146">Môžete tiež [exportovať údaje na požiadanie](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="7f0b3-146">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="7f0b3-147">Ochrana osobných údajov a dodržiavanie súladu s nariadeniami</span><span class="sxs-lookup"><span data-stu-id="7f0b3-147">Data privacy and compliance</span></span>

<span data-ttu-id="7f0b3-148">Keď povolíte prenos údajov spoločnosti Mailchimp v službe Dynamics 365 Customer Insights, povoľujete tým prenos údajov mimo hranice súladu so službou Dynamics 365 Customer Insights vrátane potenciálne citlivých údajov, ako sú napríklad osobné údaje.</span><span class="sxs-lookup"><span data-stu-id="7f0b3-148">When you enable Dynamics 365 Customer Insights to transmit data to Mailchimp, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="7f0b3-149">Spoločnosť Microsoft prenesie tieto údaje na váš pokyn, ale vy ste zodpovední za zabezpečenie toho, aby spoločnosť Mailchimp plnila všetky prípadné povinnosti týkajúce sa ochrany vašich osobných údajov alebo zabezpečenia.</span><span class="sxs-lookup"><span data-stu-id="7f0b3-149">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Mailchimp meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="7f0b3-150">Ďalšie informácie nájdete vo [vyhlásení o ochrane súkromia spoločnosti Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="7f0b3-150">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="7f0b3-151">Váš správca služby Dynamics 365 Customer Insights môže túto funkciu kedykoľvek prestať používať odstránením tohto cieľového umiestnenia exportu.</span><span class="sxs-lookup"><span data-stu-id="7f0b3-151">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
