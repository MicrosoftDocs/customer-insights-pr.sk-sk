---
title: Export údajov služby Customer Insights do Mailchimp
description: Zistite, ako môžete nakonfigurovať pripojenie k Mailchimp.
ms.date: 10/26/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: edff494f6edf26a8b641cb1d788a715389ddb346
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406896"
---
# <a name="connector-for-mailchimp-preview"></a><span data-ttu-id="255ff-103">Konektor pre Mailchimp (ukážka)</span><span class="sxs-lookup"><span data-stu-id="255ff-103">Connector for Mailchimp (preview)</span></span>

<span data-ttu-id="255ff-104">Exportujte segmenty zjednotených profilov zákazníkov do služby Mailchimp a vytvárajte bulletiny a e-mailové kampane.</span><span class="sxs-lookup"><span data-stu-id="255ff-104">Export segments of unified customer profiles to Mailchimp to create newsletters and email campaigns.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="255ff-105">Predpoklady</span><span class="sxs-lookup"><span data-stu-id="255ff-105">Prerequisites</span></span>

-   <span data-ttu-id="255ff-106">Máte [účet Mailchimp](https://mailchimp.com/) a zodpovedajúce poverenia správcu.</span><span class="sxs-lookup"><span data-stu-id="255ff-106">You have a [Mailchimp account](https://mailchimp.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="255ff-107">V Mailchimp a zodpovedajúcich ID existujú cieľové skupiny.</span><span class="sxs-lookup"><span data-stu-id="255ff-107">There are existing audiences in Mailchimp and the corresponding IDs.</span></span> <span data-ttu-id="255ff-108">Ďalšie informácie nájdete v časti [Cieľové skupiny Mailchimp](https://mailchimp.com/help/create-audience/).</span><span class="sxs-lookup"><span data-stu-id="255ff-108">For more information, see [Mailchimp audiences](https://mailchimp.com/help/create-audience/).</span></span>
-   <span data-ttu-id="255ff-109">Máte [nakonfigurované segmenty](segments.md)</span><span class="sxs-lookup"><span data-stu-id="255ff-109">You have [configured segments](segments.md)</span></span>
-   <span data-ttu-id="255ff-110">Zjednotené profily zákazníkov v exportovaných segmentoch obsahujú pole predstavujúce e-mailovú adresu.</span><span class="sxs-lookup"><span data-stu-id="255ff-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-mailchimp"></a><span data-ttu-id="255ff-111">Pripojiť k Mailchimpu</span><span class="sxs-lookup"><span data-stu-id="255ff-111">Connect to Mailchimp</span></span>

1. <span data-ttu-id="255ff-112">Prejdite do ponuky **Správca** > **Ciele exportu**.</span><span class="sxs-lookup"><span data-stu-id="255ff-112">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="255ff-113">V časti **Mailchimp** vyberte položku **Nastaviť**.</span><span class="sxs-lookup"><span data-stu-id="255ff-113">Under **Mailchimp**, select **Set up**.</span></span>

1. <span data-ttu-id="255ff-114">Do poľa **Zobrazovaný názov** zadajte rozpoznateľný názov cieľa exportu.</span><span class="sxs-lookup"><span data-stu-id="255ff-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="255ff-115">Vyberte **Súhlasím** na potvrdenie **Ochrany osobných údajov a dodržiavanie súladu s nariadeniami**.</span><span class="sxs-lookup"><span data-stu-id="255ff-115">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="255ff-116">Zadajte vaše **[ID cieľovej skupiny Mailchimp](https://mailchimp.com/help/find-audience-id/)** a vyberte položku **Pripojiť** na inicializáciu pripojenia k Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="255ff-116">Enter your **[Mailchimp audience ID](https://mailchimp.com/help/find-audience-id/)** and select **Connect** to initialize the connection to Mailchimp.</span></span>

1. <span data-ttu-id="255ff-117">Vyberte položku **Overenie pomocou služby Mailchimp** a poskytnite svoje poverenia pre Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="255ff-117">Select **Authenticate with Mailchimp** and provide your Mailchimp credentials.</span></span>

1. <span data-ttu-id="255ff-118">Vyberte položku **Pridať samého seba ako používateľa exportu** a uveďte svoje poverenia pre Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="255ff-118">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

   :::image type="content" source="media/export-connect-mailchimp.png" alt-text="Sníma obrazovky exportu pre pripojenie k Mailchimp":::

1. <span data-ttu-id="255ff-120">Vyberte **Ďalej** a nakonfigurujte export.</span><span class="sxs-lookup"><span data-stu-id="255ff-120">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="255ff-121">Nakonfigurujte konektor</span><span class="sxs-lookup"><span data-stu-id="255ff-121">Configure the connector</span></span>

1. <span data-ttu-id="255ff-122">V sekcii **Párovanie údajov** v poli **E-mail** do svojho zjednoteného profilu zákazníka vyberte pole, ktoré predstavuje e-mailovú adresu zákazníka.</span><span class="sxs-lookup"><span data-stu-id="255ff-122">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="255ff-123">Prípadne môžete exportovať **Krstné meno** a **Priezvisko** ako dodatočné polia na vytvorenie viac prispôsobených e-mailov.</span><span class="sxs-lookup"><span data-stu-id="255ff-123">Optionally, you can export **First name** and **Last name** as additional fields to create more personalized emails.</span></span> <span data-ttu-id="255ff-124">Výberom položky **Pridať atribút** namapujete tieto polia.</span><span class="sxs-lookup"><span data-stu-id="255ff-124">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="255ff-125">Vyberte segmenty, ktoré chcete exportovať.</span><span class="sxs-lookup"><span data-stu-id="255ff-125">Select the segments you want to export.</span></span> <span data-ttu-id="255ff-126">Do služby Mailchimp môžete exportovať spolu až 1 milión zákazníckych profilov.</span><span class="sxs-lookup"><span data-stu-id="255ff-126">You can export up to 1 million customer profiles in total to Mailchimp.</span></span>

   :::image type="content" source="media/export-segments-mailchimp.png" alt-text="Vyberte polia a segmenty, ktoré chcete exportovať do Mailchimp":::

1. <span data-ttu-id="255ff-128">Vyberte položku **Uložiť**.</span><span class="sxs-lookup"><span data-stu-id="255ff-128">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="255ff-129">Export údajov</span><span class="sxs-lookup"><span data-stu-id="255ff-129">Export the data</span></span>

<span data-ttu-id="255ff-130">Môžete [exportovať údaje na vyžiadanie](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="255ff-130">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="255ff-131">Export sa spustí aj pri každej [plánovanej obnove](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="255ff-131">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="255ff-132">V službe Mailchimp teraz nájdete svoje segmenty v sekcii [Cieľové skupiny služby Mailchimp](https://mailchimp.com/help/create-audience/).</span><span class="sxs-lookup"><span data-stu-id="255ff-132">In Mailchimp, you can now find your segments under [Mailchimp audiences](https://mailchimp.com/help/create-audience/).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="255ff-133">Známe obmedzenia</span><span class="sxs-lookup"><span data-stu-id="255ff-133">Known limitations</span></span>

- <span data-ttu-id="255ff-134">Až 1 milión profilov na export do Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="255ff-134">Up to 1 million profiles per export to Mailchimp.</span></span>
- <span data-ttu-id="255ff-135">Export do Mailchimp je obmedzený na segmenty.</span><span class="sxs-lookup"><span data-stu-id="255ff-135">Exporting to Mailchimp is limited to segments.</span></span>
- <span data-ttu-id="255ff-136">Export segmentov s celkovým počtom 1 miliónov profilov môže trvať až tri hodiny z dôvodu obmedzení na strane poskytovateľa.</span><span class="sxs-lookup"><span data-stu-id="255ff-136">Exporting segments with a total of 1 million profiles can take up to three hours due to limitations on the provider side.</span></span> 
- <span data-ttu-id="255ff-137">Počet profilov, ktoré môžete exportovať do Mailchimp, závisí a je obmedzený vašou zmluvou so spoločnosťou Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="255ff-137">The number of profiles that you can export to Mailchimp is dependent and limited on your contract with Mailchimp.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="255ff-138">Ochrana osobných údajov a dodržiavanie súladu s nariadeniami</span><span class="sxs-lookup"><span data-stu-id="255ff-138">Data privacy and compliance</span></span>

<span data-ttu-id="255ff-139">Keď povolíte prenos údajov spoločnosti Mailchimp v službe Dynamics 365 Customer Insights, povoľujete tým prenos údajov mimo hranice súladu so službou Dynamics 365 Customer Insights vrátane potenciálne citlivých údajov, ako sú napríklad osobné údaje.</span><span class="sxs-lookup"><span data-stu-id="255ff-139">When you enable Dynamics 365 Customer Insights to transmit data to Mailchimp, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="255ff-140">Spoločnosť Microsoft prenesie tieto údaje na váš pokyn, ale vy ste zodpovední za zabezpečenie toho, aby spoločnosť Mailchimp plnila všetky prípadné povinnosti týkajúce sa ochrany vašich osobných údajov alebo zabezpečenia.</span><span class="sxs-lookup"><span data-stu-id="255ff-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Mailchimp meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="255ff-141">Ďalšie informácie nájdete vo [vyhlásení o ochrane súkromia spoločnosti Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="255ff-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="255ff-142">Váš správca služby Dynamics 365 Customer Insights môže túto funkciu kedykoľvek prestať používať odstránením tohto cieľového umiestnenia exportu.</span><span class="sxs-lookup"><span data-stu-id="255ff-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
