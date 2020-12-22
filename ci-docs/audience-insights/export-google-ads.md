---
title: Export údajov služby Customer Insights do Reklám Google
description: Zistite, ako môžete nakonfigurovať pripojenie k Reklamám Google.
ms.date: 11/18/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 06aa0b6ff3125d8735adc8c8f9f6dad69087d9f8
ms.sourcegitcommit: ff824bbbd31fd666ab0da682bf48ea31580d242c
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 11/18/2020
ms.locfileid: "4568499"
---
# <a name="connector-for-google-ads-preview"></a><span data-ttu-id="f8c85-103">Konektor pre Reklamy Google (ukážka)</span><span class="sxs-lookup"><span data-stu-id="f8c85-103">Connector for Google Ads (preview)</span></span>

<span data-ttu-id="f8c85-104">Exportujte segmenty zjednotených profilov zákazníkov do zoznamu cieľových skupín v Reklamách Google a použite ich na inzerciu v službách Vyhľadávanie Google, Gmail, YouTube a Obsahová sieť Google.</span><span class="sxs-lookup"><span data-stu-id="f8c85-104">Export segments of unified customer profiles to Google Ads audience list and use them to advertise on Google Search, Gmail, YouTube, and Google Display Network.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="f8c85-105">Predpoklady</span><span class="sxs-lookup"><span data-stu-id="f8c85-105">Prerequisites</span></span>

-   <span data-ttu-id="f8c85-106">Máte [účet Reklám Google](https://ads.google.com/) a zodpovedajúce poverenia správcu.</span><span class="sxs-lookup"><span data-stu-id="f8c85-106">You have a [Google Ads account](https://ads.google.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="f8c85-107">V Reklamách Google a zodpovedajúcich ID existujú cieľové skupiny.</span><span class="sxs-lookup"><span data-stu-id="f8c85-107">There are existing audiences in Google Ads and the corresponding IDs.</span></span> <span data-ttu-id="f8c85-108">Ďalšie informácie nájdete v časti [Cieľové skupiny Reklám Google](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).</span><span class="sxs-lookup"><span data-stu-id="f8c85-108">For more information, see [Google Ads audiences](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).</span></span>
-   <span data-ttu-id="f8c85-109">Máte [nakonfigurované segmenty](segments.md)</span><span class="sxs-lookup"><span data-stu-id="f8c85-109">You have [configured segments](segments.md)</span></span>
-   <span data-ttu-id="f8c85-110">Zjednotené profily zákazníkov v exportovaných segmentoch obsahujú polia predstavujúce e-mailovú adresu, krstné meno a priezvisko</span><span class="sxs-lookup"><span data-stu-id="f8c85-110">Unified customer profiles in the exported segments contain fields representing an email address, first name, and last name</span></span>

## <a name="connect-to-google-ads"></a><span data-ttu-id="f8c85-111">Pripojenie k službe Google Ads</span><span class="sxs-lookup"><span data-stu-id="f8c85-111">Connect to Google Ads</span></span>

1. <span data-ttu-id="f8c85-112">Prejdite do ponuky **Správca** > **Ciele exportu**.</span><span class="sxs-lookup"><span data-stu-id="f8c85-112">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="f8c85-113">V časti **Reklamy Google** vyberte položku **Nastavenie**.</span><span class="sxs-lookup"><span data-stu-id="f8c85-113">Under **Google Ads**, select **Set up**.</span></span>

1. <span data-ttu-id="f8c85-114">Do poľa **Zobrazovaný názov** zadajte rozpoznateľný názov cieľa exportu.</span><span class="sxs-lookup"><span data-stu-id="f8c85-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="f8c85-115">Zadajte vaše **[ID zákazníka v Reklamách Google](https://support.google.com/google-ads/answer/1704344)**.</span><span class="sxs-lookup"><span data-stu-id="f8c85-115">Enter your **[Google Ads customer ID](https://support.google.com/google-ads/answer/1704344)**.</span></span>

1. <span data-ttu-id="f8c85-116">Zadajte váš **[Token vývojára schválený Reklamami Google](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**.</span><span class="sxs-lookup"><span data-stu-id="f8c85-116">Enter your **[Google Ads approved developer token](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**.</span></span>

1. <span data-ttu-id="f8c85-117">Vyberte **Súhlasím** na potvrdenie **Ochrany osobných údajov a dodržiavanie súladu s nariadeniami**.</span><span class="sxs-lookup"><span data-stu-id="f8c85-117">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="f8c85-118">Zadajte vaše **[ID cieľovej skupiny Reklám Google](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** a vyberte položku **Pripojiť** na inicializáciu pripojenia k Reklamám Google.</span><span class="sxs-lookup"><span data-stu-id="f8c85-118">Enter your **[Google Ads audience ID](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** and select **Connect** to initialize the connection to Google Ads.</span></span>

1. <span data-ttu-id="f8c85-119">Vyberte položku **Overenie pomocou Reklám Google** a poskytnite svoje poverenia pre Reklamy Google.</span><span class="sxs-lookup"><span data-stu-id="f8c85-119">Select **Authenticate with Google Ads** and provide your Google Ads credentials.</span></span>

1. <span data-ttu-id="f8c85-120">Vyberte položku **Pridať samého seba ako používateľa exportu** a uveďte svoje poverenia pre Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="f8c85-120">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

   :::image type="content" source="media/export-segments-googleads.PNG" alt-text="Sníma obrazovky exportu pre pripojenie k Reklamám Google":::

1. <span data-ttu-id="f8c85-122">Vyberte **Ďalej** a nakonfigurujte export.</span><span class="sxs-lookup"><span data-stu-id="f8c85-122">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="f8c85-123">Nakonfigurujte konektor</span><span class="sxs-lookup"><span data-stu-id="f8c85-123">Configure the connector</span></span>

1. <span data-ttu-id="f8c85-124">V sekcii **Párovanie údajov** v poli **E-mail** do svojho zjednoteného profilu zákazníka vyberte pole, ktoré predstavuje e-mailovú adresu zákazníka.</span><span class="sxs-lookup"><span data-stu-id="f8c85-124">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="f8c85-125">Rovnaký postup opakujte aj pre polia **Krstné meno** a **Priezvisko**.</span><span class="sxs-lookup"><span data-stu-id="f8c85-125">Repeat the same steps for \*\*First name" and **Last name** fields.</span></span>

1. <span data-ttu-id="f8c85-126">Vyberte segmenty, ktoré chcete exportovať.</span><span class="sxs-lookup"><span data-stu-id="f8c85-126">Select the segments you want to export.</span></span> <span data-ttu-id="f8c85-127">Do Reklám Google môžete exportovať spolu až 1 milión zákazníckych profilov.</span><span class="sxs-lookup"><span data-stu-id="f8c85-127">You can export up to 1 million customer profiles in total to Google Ads.</span></span>

1. <span data-ttu-id="f8c85-128">Vyberte položku **Uložiť**.</span><span class="sxs-lookup"><span data-stu-id="f8c85-128">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="f8c85-129">Export údajov</span><span class="sxs-lookup"><span data-stu-id="f8c85-129">Export the data</span></span>

<span data-ttu-id="f8c85-130">Môžete [exportovať údaje na vyžiadanie](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="f8c85-130">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="f8c85-131">Export sa spustí aj pri každej [plánovanej obnove](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="f8c85-131">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="f8c85-132">V Reklamách Google teraz nájdete svoje segmenty v sekcii [Cieľové skupiny Reklám Google](https://support.google.com/google-ads/answer/7558048?hl=en/).</span><span class="sxs-lookup"><span data-stu-id="f8c85-132">In Google Ads, you can now find your segments under [Google Ads audiences](https://support.google.com/google-ads/answer/7558048?hl=en/).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="f8c85-133">Známe obmedzenia</span><span class="sxs-lookup"><span data-stu-id="f8c85-133">Known limitations</span></span>

- <span data-ttu-id="f8c85-134">Až 1 milión profilov na export do Reklám Google.</span><span class="sxs-lookup"><span data-stu-id="f8c85-134">Up to 1 million profiles per export to Google Ads.</span></span>
- <span data-ttu-id="f8c85-135">Export do Reklám Google je obmedzený na segmenty.</span><span class="sxs-lookup"><span data-stu-id="f8c85-135">Exporting to Google Ads is limited to segments.</span></span>
- <span data-ttu-id="f8c85-136">Export segmentov s celkovým počtom 1 miliónov profilov môže trvať až 5 minút z dôvodu obmedzení na strane poskytovateľa.</span><span class="sxs-lookup"><span data-stu-id="f8c85-136">Exporting segments with a total of 1 million profiles can take up to 5 minutes because of limitations on the provider side.</span></span> 
- <span data-ttu-id="f8c85-137">Priraďovanie v Reklamách Google môže trvať až 48 hodín.</span><span class="sxs-lookup"><span data-stu-id="f8c85-137">The matching in Google Ads can take up to 48 hours.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="f8c85-138">Ochrana osobných údajov a dodržiavanie súladu s nariadeniami</span><span class="sxs-lookup"><span data-stu-id="f8c85-138">Data privacy and compliance</span></span>

<span data-ttu-id="f8c85-139">Keď povolíte prenos údajov do Reklám Google v službe Dynamics 365 Customer Insights, povoľujete tým prenos údajov mimo hranice súladu so službou Dynamics 365 Customer Insights vrátane potenciálne citlivých údajov, ako sú napríklad osobné údaje.</span><span class="sxs-lookup"><span data-stu-id="f8c85-139">When you enable Dynamics 365 Customer Insights to transmit data to Google Ads, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="f8c85-140">Spoločnosť Microsoft prenesie tieto údaje na váš pokyn, ale vy ste zodpovední za zabezpečenie toho, aby Reklamy Google plnili všetky prípadné povinnosti týkajúce sa ochrany vašich osobných údajov alebo zabezpečenia.</span><span class="sxs-lookup"><span data-stu-id="f8c85-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Google Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="f8c85-141">Ďalšie informácie nájdete vo [vyhlásení o ochrane súkromia spoločnosti Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="f8c85-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="f8c85-142">Váš správca služby Dynamics 365 Customer Insights môže túto funkciu kedykoľvek prestať používať odstránením tohto cieľového umiestnenia exportu.</span><span class="sxs-lookup"><span data-stu-id="f8c85-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
