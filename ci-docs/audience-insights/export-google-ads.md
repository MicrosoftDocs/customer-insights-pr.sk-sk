---
title: Export údajov služby Customer Insights do Reklám Google
description: Zistite ako nakonfigurovať pripojenie a realizovať exportovanie do Google Ads.
ms.date: 03/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 73f3257a3ae6e8423f45410546535df5e3b400ce
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976337"
---
# <a name="export-segments-to-google-ads-preview"></a><span data-ttu-id="8a24b-103">Exportovať segmenty do služby Google Ads (ukážka)</span><span class="sxs-lookup"><span data-stu-id="8a24b-103">Export segments to Google Ads (preview)</span></span>

<span data-ttu-id="8a24b-104">Exportujte segmenty zjednotených profilov zákazníkov do zoznamu cieľových skupín v Reklamách Google a použite ich na inzerciu v službách Vyhľadávanie Google, Gmail, YouTube a Obsahová sieť Google.</span><span class="sxs-lookup"><span data-stu-id="8a24b-104">Export segments of unified customer profiles to Google Ads audience list and use them to advertise on Google Search, Gmail, YouTube, and Google Display Network.</span></span> 

## <a name="prerequisites-for-connection"></a><span data-ttu-id="8a24b-105">Predpoklad na pripojenie</span><span class="sxs-lookup"><span data-stu-id="8a24b-105">Prerequisites for connection</span></span>

-   <span data-ttu-id="8a24b-106">Máte [účet Reklám Google](https://ads.google.com/) a zodpovedajúce poverenia správcu.</span><span class="sxs-lookup"><span data-stu-id="8a24b-106">You have a [Google Ads account](https://ads.google.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="8a24b-107">Máte [schválený token vývojára Google Ads](https://developers.google.com/google-ads/api/docs/first-call/dev-token)</span><span class="sxs-lookup"><span data-stu-id="8a24b-107">You have an [approved Google Ads Developer token](https://developers.google.com/google-ads/api/docs/first-call/dev-token)</span></span> 
-   <span data-ttu-id="8a24b-108">Spĺňate požiadavky [pravidiel pre priradenie zákazníkov](https://support.google.com/adspolicy/answer/6299717)</span><span class="sxs-lookup"><span data-stu-id="8a24b-108">You fulfill the requirements of the [Customer Match Policy](https://support.google.com/adspolicy/answer/6299717)</span></span>
-   <span data-ttu-id="8a24b-109">Spĺňate požiadavky [veľkostí remarketingového zoznamu](https://support.google.com/google-ads/answer/7558048)</span><span class="sxs-lookup"><span data-stu-id="8a24b-109">You fulfill the requirements of the [remarketing list sizes](https://support.google.com/google-ads/answer/7558048)</span></span> 

-   <span data-ttu-id="8a24b-110">V Reklamách Google a zodpovedajúcich ID existujú cieľové skupiny.</span><span class="sxs-lookup"><span data-stu-id="8a24b-110">There are existing audiences in Google Ads and the corresponding IDs.</span></span> <span data-ttu-id="8a24b-111">Ďalšie informácie nájdete v časti [Cieľové skupiny Reklám Google](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).</span><span class="sxs-lookup"><span data-stu-id="8a24b-111">For more information, see [Google Ads audiences](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).</span></span>
-   <span data-ttu-id="8a24b-112">Máte [nakonfigurované segmenty](segments.md)</span><span class="sxs-lookup"><span data-stu-id="8a24b-112">You have [configured segments](segments.md)</span></span>
-   <span data-ttu-id="8a24b-113">Zjednotené profily zákazníkov v exportovaných segmentoch obsahujú polia predstavujúce e-mailovú adresu, krstné meno a priezvisko</span><span class="sxs-lookup"><span data-stu-id="8a24b-113">Unified customer profiles in the exported segments contain fields representing an email address, first name, and last name</span></span>

## <a name="known-limitations"></a><span data-ttu-id="8a24b-114">Známe obmedzenia</span><span class="sxs-lookup"><span data-stu-id="8a24b-114">Known limitations</span></span>

- <span data-ttu-id="8a24b-115">Až 1 milión profilov na export do Reklám Google.</span><span class="sxs-lookup"><span data-stu-id="8a24b-115">Up to 1 million profiles per export to Google Ads.</span></span>
- <span data-ttu-id="8a24b-116">Export do Reklám Google je obmedzený na segmenty.</span><span class="sxs-lookup"><span data-stu-id="8a24b-116">Exporting to Google Ads is limited to segments.</span></span>
- <span data-ttu-id="8a24b-117">Export segmentov s celkovým počtom 1 miliónov profilov môže trvať až 5 minút z dôvodu obmedzení na strane poskytovateľa.</span><span class="sxs-lookup"><span data-stu-id="8a24b-117">Exporting segments with a total of 1 million profiles can take up to 5 minutes because of limitations on the provider side.</span></span> 
- <span data-ttu-id="8a24b-118">Priraďovanie v Reklamách Google môže trvať až 48 hodín.</span><span class="sxs-lookup"><span data-stu-id="8a24b-118">The matching in Google Ads can take up to 48 hours.</span></span>

## <a name="set-up-connection-to-google-ads"></a><span data-ttu-id="8a24b-119">Nastavenie pripojenia do Google Ads</span><span class="sxs-lookup"><span data-stu-id="8a24b-119">Set up connection to Google Ads</span></span>

1. <span data-ttu-id="8a24b-120">Prejdite do časti **Správca** > **Pripojenia**.</span><span class="sxs-lookup"><span data-stu-id="8a24b-120">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="8a24b-121">Stlačte možnosť **Pridať pripojenie** a stlačením možnosti **Google Ads** nakonfigurujte pripojenie.</span><span class="sxs-lookup"><span data-stu-id="8a24b-121">Select **Add connection** and choose **Google Ads** to configure the connection.</span></span>

1. <span data-ttu-id="8a24b-122">Do poľa **Zobrazovaný názov** zadajte rozpoznateľný názov pripojenia.</span><span class="sxs-lookup"><span data-stu-id="8a24b-122">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="8a24b-123">Zobrazovaný názov a typ spojenia, ktoré popisuje toto spojenie.</span><span class="sxs-lookup"><span data-stu-id="8a24b-123">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="8a24b-124">Odporúčame zvoliť názov, ktorý vysvetľuje účel a cieľ tohto spojenia.</span><span class="sxs-lookup"><span data-stu-id="8a24b-124">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="8a24b-125">Vyberte používateľov, ktorí môžu používať toto pripojenie.</span><span class="sxs-lookup"><span data-stu-id="8a24b-125">Choose who can use this connection.</span></span> <span data-ttu-id="8a24b-126">Ak neurobíte nič, predvolená hodnota bude Správcovia.</span><span class="sxs-lookup"><span data-stu-id="8a24b-126">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="8a24b-127">Viac informácií nájdete v časti [Umožnite prispievateľom použiť pripojenie na export](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="8a24b-127">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="8a24b-128">Zadajte vaše **[ID zákazníka v Reklamách Google](https://support.google.com/google-ads/answer/1704344)**.</span><span class="sxs-lookup"><span data-stu-id="8a24b-128">Enter your **[Google Ads customer ID](https://support.google.com/google-ads/answer/1704344)**.</span></span>

1. <span data-ttu-id="8a24b-129">Zadajte váš **[Token vývojára schválený Reklamami Google](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**.</span><span class="sxs-lookup"><span data-stu-id="8a24b-129">Enter your **[Google Ads approved developer token](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**.</span></span>

1. <span data-ttu-id="8a24b-130">Vyberte **Súhlasím** na potvrdenie **Ochrany osobných údajov a dodržiavanie súladu s nariadeniami**.</span><span class="sxs-lookup"><span data-stu-id="8a24b-130">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="8a24b-131">Vyberte položku **Overenie pomocou Reklám Google** a poskytnite svoje poverenia pre Reklamy Google.</span><span class="sxs-lookup"><span data-stu-id="8a24b-131">Select **Authenticate with Google Ads** and provide your Google Ads credentials.</span></span>

1. <span data-ttu-id="8a24b-132">Vyberte položku **Pridať samého seba ako používateľa exportu** a uveďte svoje poverenia pre Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="8a24b-132">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="8a24b-133">Stlačte možnosť **Uložiť** a dokončite pripojenie.</span><span class="sxs-lookup"><span data-stu-id="8a24b-133">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="8a24b-134">Nakonfigurujte export</span><span class="sxs-lookup"><span data-stu-id="8a24b-134">Configure an export</span></span>

<span data-ttu-id="8a24b-135">Tento export môžete nakonfigurovať, ak máte prístup k pripojeniu tohto typu.</span><span class="sxs-lookup"><span data-stu-id="8a24b-135">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="8a24b-136">Viac informácií nájdete na stránke [Na konfiguráciu exportu sú potrebné povolenia](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="8a24b-136">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="8a24b-137">Prejdite na **Údaje** > **Exporty**.</span><span class="sxs-lookup"><span data-stu-id="8a24b-137">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="8a24b-138">Na vytvorenie nového exportu stlačte možnosť **Pridať cieľ**.</span><span class="sxs-lookup"><span data-stu-id="8a24b-138">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="8a24b-139">V poli **Pripojenie na export** vyberte pripojenie v časti Google Ads.</span><span class="sxs-lookup"><span data-stu-id="8a24b-139">In the **Connection for export** field, choose a connection from the Google Ads section.</span></span> <span data-ttu-id="8a24b-140">Ak nevidíte názov tejto sekcie, nemáte k dispozícii žiadne spojenia tohto typu.</span><span class="sxs-lookup"><span data-stu-id="8a24b-140">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="8a24b-141">Zadajte vaše **[ID cieľovej skupiny Reklám Google](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** a vyberte položku **Pripojiť** na inicializáciu pripojenia k Reklamám Google.</span><span class="sxs-lookup"><span data-stu-id="8a24b-141">Enter your **[Google Ads audience ID](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** and select **Connect** to initialize the connection to Google Ads.</span></span>

1. <span data-ttu-id="8a24b-142">V sekcii **Párovanie údajov** v poli **E-mail** do svojho zjednoteného profilu zákazníka vyberte pole, ktoré predstavuje e-mailovú adresu zákazníka.</span><span class="sxs-lookup"><span data-stu-id="8a24b-142">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="8a24b-143">Rovnaký postup opakujte aj pre polia **Krstné meno** a **Priezvisko**.</span><span class="sxs-lookup"><span data-stu-id="8a24b-143">Repeat the same steps for \*\*First name" and **Last name** fields.</span></span>

1. <span data-ttu-id="8a24b-144">Vyberte segmenty, ktoré chcete exportovať.</span><span class="sxs-lookup"><span data-stu-id="8a24b-144">Select the segments you want to export.</span></span> <span data-ttu-id="8a24b-145">Do Reklám Google môžete exportovať spolu až 1 milión zákazníckych profilov.</span><span class="sxs-lookup"><span data-stu-id="8a24b-145">You can export up to 1 million customer profiles in total to Google Ads.</span></span>

<span data-ttu-id="8a24b-146">Uloženie exportu nespustí export okamžite.</span><span class="sxs-lookup"><span data-stu-id="8a24b-146">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="8a24b-147">Export prebieha s každým [plánovaným obnovením](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="8a24b-147">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="8a24b-148">Môžete tiež [exportovať údaje na požiadanie](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="8a24b-148">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="8a24b-149">Ochrana osobných údajov a dodržiavanie súladu s nariadeniami</span><span class="sxs-lookup"><span data-stu-id="8a24b-149">Data privacy and compliance</span></span>

<span data-ttu-id="8a24b-150">Keď povolíte prenos údajov do Reklám Google v službe Dynamics 365 Customer Insights, povoľujete tým prenos údajov mimo hranice súladu so službou Dynamics 365 Customer Insights vrátane potenciálne citlivých údajov, ako sú napríklad osobné údaje.</span><span class="sxs-lookup"><span data-stu-id="8a24b-150">When you enable Dynamics 365 Customer Insights to transmit data to Google Ads, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="8a24b-151">Spoločnosť Microsoft prenesie tieto údaje na váš pokyn, ale vy ste zodpovední za zabezpečenie toho, aby Reklamy Google plnili všetky prípadné povinnosti týkajúce sa ochrany vašich osobných údajov alebo zabezpečenia.</span><span class="sxs-lookup"><span data-stu-id="8a24b-151">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Google Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="8a24b-152">Ďalšie informácie nájdete vo [vyhlásení o ochrane súkromia spoločnosti Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="8a24b-152">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="8a24b-153">Váš správca služby Dynamics 365 Customer Insights môže túto funkciu kedykoľvek prestať používať odstránením tohto cieľového umiestnenia exportu.</span><span class="sxs-lookup"><span data-stu-id="8a24b-153">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
