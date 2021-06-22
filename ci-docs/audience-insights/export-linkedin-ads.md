---
title: Export údajov Customer Insights do LinkedIn Ads
description: Zistite ako nakonfigurovať pripojenie a realizovať exportovanie do LinkedIn Ads.
ms.date: 05/12/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 1c7b0c728bc4d4cf6b5aea79396cf0779fbf298d
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124551"
---
# <a name="export-segments-to-linkedin-ads-preview"></a><span data-ttu-id="7541e-103">Export segmentov do služby LinkedIn Ads (verzia Preview)</span><span class="sxs-lookup"><span data-stu-id="7541e-103">Export segments to LinkedIn Ads (preview)</span></span>

<span data-ttu-id="7541e-104">Exportujte segmenty zjednotených profilov zákazníkov do LinkedIn Ads a vytvorte párované cieľové skupiny.</span><span class="sxs-lookup"><span data-stu-id="7541e-104">Export segments of unified customer profiles to LinkedIn Ads to create matched audiences.</span></span> <span data-ttu-id="7541e-105">Použite párované cieľové skupiny na zacielenie na spoločnosť a kontakty.</span><span class="sxs-lookup"><span data-stu-id="7541e-105">Use the matched audiences for company targeting and contact targeting.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="7541e-106">Predpoklady</span><span class="sxs-lookup"><span data-stu-id="7541e-106">Prerequisites</span></span>

-   <span data-ttu-id="7541e-107">Máte [obchodný vzťah LinkedIn Campaign Manager](https://business.linkedin.com/marketing-solutions/ads) a zodpovedajúce poverenia správcu.</span><span class="sxs-lookup"><span data-stu-id="7541e-107">You have an [LinkedIn Campaign Manager account](https://business.linkedin.com/marketing-solutions/ads) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="7541e-108">Máte [konfigurované segmenty](segments.md) v prehľadoch cieľových skupín.</span><span class="sxs-lookup"><span data-stu-id="7541e-108">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="7541e-109">Profily zákazníkov v exportovaných segmentoch obsahujú pole s e-mailovou adresou.</span><span class="sxs-lookup"><span data-stu-id="7541e-109">Customer profiles in the exported segments contain a field with an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="7541e-110">Známe obmedzenia</span><span class="sxs-lookup"><span data-stu-id="7541e-110">Known limitations</span></span>

- <span data-ttu-id="7541e-111">Na jeden export do LinkedIn Ads môžete exportovať až 100 000 profilov.</span><span class="sxs-lookup"><span data-stu-id="7541e-111">You can export up to 100K profiles per export to LinkedIn Ads.</span></span>
- <span data-ttu-id="7541e-112">Exportovanie do LinkedIn Ads je obmedzené na segmenty.</span><span class="sxs-lookup"><span data-stu-id="7541e-112">Exporting to LinkedIn Ads is limited to segments.</span></span>
- <span data-ttu-id="7541e-113">Exportovanie až 100 000 profilov do aplikácie LinkedIn Ads môže trvať až 10 minút.</span><span class="sxs-lookup"><span data-stu-id="7541e-113">Exporting up to 100K profiles to LinkedIn Ads can take up to 10 minutes to complete.</span></span> 

## <a name="set-up-the-connection-to-linkedin-ads"></a><span data-ttu-id="7541e-114">Príprava pripojenia do LinkedIn Ads</span><span class="sxs-lookup"><span data-stu-id="7541e-114">Set up the connection to LinkedIn Ads</span></span>

1. <span data-ttu-id="7541e-115">V prehľadoch cieľovej skupiny prejdite na **Správca** > **Pripojenia**.</span><span class="sxs-lookup"><span data-stu-id="7541e-115">In audience insights, go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="7541e-116">Stlačte možnosť **Pridať pripojenie** a stlačením možnosti **LinkedIn Ads** nakonfigurujte pripojenie.</span><span class="sxs-lookup"><span data-stu-id="7541e-116">Select **Add connection** and choose **LinkedIn Ads** to configure the connection.</span></span>

1. <span data-ttu-id="7541e-117">Do poľa **Zobrazovaný názov** zadajte rozpoznateľný názov pripojenia.</span><span class="sxs-lookup"><span data-stu-id="7541e-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="7541e-118">Zobrazovaný názov a typ spojenia, ktoré popisuje toto spojenie.</span><span class="sxs-lookup"><span data-stu-id="7541e-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="7541e-119">Odporúčame zvoliť názov, ktorý vysvetľuje účel a cieľ tohto spojenia.</span><span class="sxs-lookup"><span data-stu-id="7541e-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="7541e-120">Vyberte používateľov, ktorí môžu používať toto pripojenie.</span><span class="sxs-lookup"><span data-stu-id="7541e-120">Choose who can use this connection.</span></span> <span data-ttu-id="7541e-121">Ak neurobíte nič, predvolená hodnota bude správcovia.</span><span class="sxs-lookup"><span data-stu-id="7541e-121">If you take no action, the default is administrators.</span></span> <span data-ttu-id="7541e-122">Viac informácií nájdete v časti [Umožnite prispievateľom použiť pripojenie na export](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="7541e-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="7541e-123">Poskytnite svoje [ID účtu LinkedIn Campaign Manager](https://www.linkedin.com/help/lms/answer/a424270).</span><span class="sxs-lookup"><span data-stu-id="7541e-123">Provide your [LinkedIn Campaign Manager Account ID](https://www.linkedin.com/help/lms/answer/a424270).</span></span>

1. <span data-ttu-id="7541e-124">Vyberte **Súhlasím** na potvrdenie **Ochrany osobných údajov a dodržiavanie súladu s nariadeniami**.</span><span class="sxs-lookup"><span data-stu-id="7541e-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="7541e-125">Stlačte možnosť **Pripojiť** na inicializáciu pripojenia k Campaign Monitor.</span><span class="sxs-lookup"><span data-stu-id="7541e-125">Select **Connect** to initialize the connection to Campaign Monitor.</span></span>

1. <span data-ttu-id="7541e-126">Stlačte možnosť **Overenie pomocou služby LinkedIn** a zadajte svoje poverenia správcu pre LinkedIn Campaign Manager.</span><span class="sxs-lookup"><span data-stu-id="7541e-126">Select **Authenticate with LinkedIn** and provide your admin credentials for LinkedIn Campaign Manager.</span></span>

1. <span data-ttu-id="7541e-127">Vyberte položku **Pridať samého seba ako používateľa exportu** a uveďte svoje poverenia pre Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="7541e-127">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="7541e-128">Stlačte možnosť **Uložiť** a dokončite pripojenie.</span><span class="sxs-lookup"><span data-stu-id="7541e-128">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="7541e-129">Nakonfigurujte export</span><span class="sxs-lookup"><span data-stu-id="7541e-129">Configure an export</span></span>

<span data-ttu-id="7541e-130">Export môžete nakonfigurovať, ak máte prístup k pripojeniu tohto typu.</span><span class="sxs-lookup"><span data-stu-id="7541e-130">You can configure an export if you have access to a connection of this type.</span></span> <span data-ttu-id="7541e-131">Viac informácií nájdete na stránke [Na konfiguráciu exportu sú potrebné povolenia](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="7541e-131">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="7541e-132">Prejdite na **Údaje** > **Exporty**.</span><span class="sxs-lookup"><span data-stu-id="7541e-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="7541e-133">Na vytvorenie nového exportu stlačte možnosť **Pridať cieľ**.</span><span class="sxs-lookup"><span data-stu-id="7541e-133">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="7541e-134">V poli **Pripojenie na export** vyberte pripojenie v časti LinkedIn Ads.</span><span class="sxs-lookup"><span data-stu-id="7541e-134">In the **Connection for export** field, choose a connection from the LinkedIn Ads section.</span></span> <span data-ttu-id="7541e-135">Ak nevidíte názov tejto sekcie, nemáte k dispozícii žiadne spojenia tohto typu.</span><span class="sxs-lookup"><span data-stu-id="7541e-135">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="7541e-136">Vyberte, či chcete exportovať údaje a vykonať [zacielenie na kontakty](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting) alebo [zacielenie na spoločnosť](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting) na LinkedIn.</span><span class="sxs-lookup"><span data-stu-id="7541e-136">Choose whether you want to export data to do [contact targeting](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting) or [company targeting](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting) on LinkedIn.</span></span> 

1. <span data-ttu-id="7541e-137">V sekcii **Párovanie údajov** vyberte pole vo svojom zjednotenom profile zákazníka, ktorý reprezentuje e-mailovú adresu zákazníka.</span><span class="sxs-lookup"><span data-stu-id="7541e-137">In the **Data matching** section, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="7541e-138">Je potrebné exportovať segmenty do LinkedIn Ads.</span><span class="sxs-lookup"><span data-stu-id="7541e-138">It's required to export segments to LinkedIn Ads.</span></span>

1. <span data-ttu-id="7541e-139">Vyberte segmenty, ktoré chcete exportovať.</span><span class="sxs-lookup"><span data-stu-id="7541e-139">Select the segments you want to export.</span></span> <span data-ttu-id="7541e-140">Priradené cieľové skupiny v LinkedIn Campaign Manager sa automaticky vytvoria s názvom segmentov, ktoré ste vybrali na export.</span><span class="sxs-lookup"><span data-stu-id="7541e-140">The matched audiences in LinkedIn Campaign Manager will automatically be created with the name of the segments that you selected to export.</span></span> <span data-ttu-id="7541e-141">Výsledkom každého segmentu bude samostatná priradená cieľová skupina.</span><span class="sxs-lookup"><span data-stu-id="7541e-141">Each segment will result in a separate matched audience.</span></span> 

1. <span data-ttu-id="7541e-142">Vyberte položku **Uložiť**.</span><span class="sxs-lookup"><span data-stu-id="7541e-142">Select **Save**.</span></span>

<span data-ttu-id="7541e-143">Uloženie exportu nespustí export okamžite.</span><span class="sxs-lookup"><span data-stu-id="7541e-143">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="7541e-144">Export prebieha s každým [plánovaným obnovením](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="7541e-144">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="7541e-145">Môžete tiež [exportovať údaje na požiadanie](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="7541e-145">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="7541e-146">Ochrana osobných údajov a dodržiavanie súladu s nariadeniami</span><span class="sxs-lookup"><span data-stu-id="7541e-146">Data privacy and compliance</span></span>

<span data-ttu-id="7541e-147">Keď povolíte Dynamics 365 Customer Insights na prenos údajov do LinkedIn Ads, povolíte prenos údajov mimo hranice súladu s Dynamics 365 Customer Insights, a to vrátane potenciálne citlivých údajov, ako sú napríklad osobné údaje.</span><span class="sxs-lookup"><span data-stu-id="7541e-147">When you enable Dynamics 365 Customer Insights to transmit data to LinkedIn Ads, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="7541e-148">Spoločnosť Microsoft prenesie tieto údaje na váš pokyn, ale vy ste zodpovední za zabezpečenie toho, aby služba LinkedIn Ads spĺňala všetky vaše povinnosti v oblasti ochrany osobných údajov alebo bezpečnosti.</span><span class="sxs-lookup"><span data-stu-id="7541e-148">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that LinkedIn Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="7541e-149">Ďalšie informácie nájdete vo [vyhlásení o ochrane súkromia spoločnosti Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="7541e-149">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="7541e-150">Túto funkciu môžete kedykoľvek prestať používať odstránením tohto cieľového umiestnenia exportu správcom služby Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="7541e-150">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to stop the use of this functionality.</span></span>
