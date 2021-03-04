---
title: Export údajov služby Customer Insights do Marketo
description: Zistite, ako môžete nakonfigurovať pripojenie k Marketo.
ms.date: 11/12/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: e0245f2d01aabc86f43532822c056965ff7ae67a
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267100"
---
# <a name="connector-for-marketo-preview"></a><span data-ttu-id="384ec-103">Konektor pre Marketo (ukážka)</span><span class="sxs-lookup"><span data-stu-id="384ec-103">Connector for Marketo (preview)</span></span>

<span data-ttu-id="384ec-104">Marketo umožňuje export zjednotených profilov zákazníkov s cieľom vytvárať kampane, poskytovať e-mailový marketing a využívať konkrétne skupiny zákazníkov.</span><span class="sxs-lookup"><span data-stu-id="384ec-104">Export segments of unified customer profiles to generate campaigns, provide email marketing and use specific groups of customers with Marketo.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="384ec-105">Predpoklady</span><span class="sxs-lookup"><span data-stu-id="384ec-105">Prerequisites</span></span>

-   <span data-ttu-id="384ec-106">Máte [účet Marketo](https://login.marketo.com/) a zodpovedajúce poverenia správcu.</span><span class="sxs-lookup"><span data-stu-id="384ec-106">You have a [Marketo account](https://login.marketo.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="384ec-107">V službe Marketo a zodpovedajúcich ID existujú zoznamy.</span><span class="sxs-lookup"><span data-stu-id="384ec-107">There are existing lists in Marketo and the corresponding IDs.</span></span> <span data-ttu-id="384ec-108">Ďalšie informácie nájdete v téme [Zoznamy služby Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span><span class="sxs-lookup"><span data-stu-id="384ec-108">For more information, see [Marketo lists](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span></span>
-   <span data-ttu-id="384ec-109">Máte [nakonfigurované segmenty](segments.md).</span><span class="sxs-lookup"><span data-stu-id="384ec-109">You have [configured segments](segments.md).</span></span>
-   <span data-ttu-id="384ec-110">Zjednotené profily zákazníkov v exportovaných segmentoch obsahujú pole predstavujúce e-mailovú adresu.</span><span class="sxs-lookup"><span data-stu-id="384ec-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-marketo"></a><span data-ttu-id="384ec-111">Pripojiť sa k poskytovateľovi obsahu Marketo</span><span class="sxs-lookup"><span data-stu-id="384ec-111">Connect to Marketo</span></span>

1. <span data-ttu-id="384ec-112">Prejdite do ponuky **Správca** > **Ciele exportu**.</span><span class="sxs-lookup"><span data-stu-id="384ec-112">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="384ec-113">V časti **Marketo** vyberte položku **Nastaviť**.</span><span class="sxs-lookup"><span data-stu-id="384ec-113">Under **Marketo**, select **Set up**.</span></span>

1. <span data-ttu-id="384ec-114">Do poľa **Zobrazovaný názov** zadajte rozpoznateľný názov cieľa exportu.</span><span class="sxs-lookup"><span data-stu-id="384ec-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="384ec-115">Zadajte svoje **[ID klienta Marketo, tajný kľúč klienta a názov hostiteľa koncového bodu REST](https://developers.marketo.com/rest-api/authentication/)**.</span><span class="sxs-lookup"><span data-stu-id="384ec-115">Enter your **[Marketo client ID, Client secret and REST Endpoint Hostname](https://developers.marketo.com/rest-api/authentication/)**.</span></span>

1. <span data-ttu-id="384ec-116">Zadajte svoje **[ID zoznamu Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)**</span><span class="sxs-lookup"><span data-stu-id="384ec-116">Enter your **[Marketo list ID](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)**</span></span> 

1. <span data-ttu-id="384ec-117">Výberom položky **Súhlasím** potvrďte **Ochranu osobných údajov a dodržiavanie súladu s nariadeniami** a vyberte položku **Pripojiť** na inicializáciu pripojenia k službe Marketo.</span><span class="sxs-lookup"><span data-stu-id="384ec-117">Select **I agree** to confirm the **Data privacy and compliance** and select **Connect** to initialize the connection to Marketo.</span></span>

1. <span data-ttu-id="384ec-118">Vyberte položku **Pridať samého seba ako používateľa exportu** a uveďte svoje poverenia pre Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="384ec-118">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

   :::image type="content" source="media/export-connect-marketo.png" alt-text="Sníma obrazovky exportu pre pripojenie k Marketo":::

1. <span data-ttu-id="384ec-120">Vyberte **Ďalej** a nakonfigurujte export.</span><span class="sxs-lookup"><span data-stu-id="384ec-120">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="384ec-121">Nakonfigurujte konektor</span><span class="sxs-lookup"><span data-stu-id="384ec-121">Configure the connector</span></span>

1. <span data-ttu-id="384ec-122">V sekcii **Párovanie údajov** v poli **E-mail** do svojho zjednoteného profilu zákazníka vyberte pole, ktoré predstavuje e-mailovú adresu zákazníka.</span><span class="sxs-lookup"><span data-stu-id="384ec-122">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="384ec-123">Prípadne môžete exportovať **Krstné meno**, **Priezvisko**, **Mesto**, **Štát** a **Krajina/Región** ako dodatočné polia na vytvorenie viac prispôsobených e-mailov.</span><span class="sxs-lookup"><span data-stu-id="384ec-123">Optionally, you can export **First name**, **Last name**, **City**, **State**, and **Country/Region**  as additional fields to create more personalized emails.</span></span> <span data-ttu-id="384ec-124">Výberom položky **Pridať atribút** namapujete tieto polia.</span><span class="sxs-lookup"><span data-stu-id="384ec-124">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="384ec-125">Vyberte segmenty, ktoré chcete exportovať.</span><span class="sxs-lookup"><span data-stu-id="384ec-125">Select the segments you want to export.</span></span> <span data-ttu-id="384ec-126">Do služby Marketo môžete exportovať spolu až 1 milión zákazníckych profilov.</span><span class="sxs-lookup"><span data-stu-id="384ec-126">You can export up to 1 million customer profiles in total to Marketo.</span></span>

   :::image type="content" source="media/export-segment-marketo.png" alt-text="Vyberte polia a segmenty, ktoré chcete exportovať do Marketo":::

1. <span data-ttu-id="384ec-128">Vyberte položku **Uložiť**.</span><span class="sxs-lookup"><span data-stu-id="384ec-128">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="384ec-129">Export údajov</span><span class="sxs-lookup"><span data-stu-id="384ec-129">Export the data</span></span>

<span data-ttu-id="384ec-130">Môžete [exportovať údaje na vyžiadanie](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="384ec-130">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="384ec-131">Export sa spustí aj pri každej [plánovanej obnove](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="384ec-131">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="384ec-132">V službe Marketo teraz nájdete svoje segmenty v sekcii [Zoznamy Marketo](ttps://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span><span class="sxs-lookup"><span data-stu-id="384ec-132">In Marketo, you can now find your segments under [Marketo lists](ttps://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="384ec-133">Známe obmedzenia</span><span class="sxs-lookup"><span data-stu-id="384ec-133">Known limitations</span></span>

- <span data-ttu-id="384ec-134">Až 1 milión profilov na export do Marketo.</span><span class="sxs-lookup"><span data-stu-id="384ec-134">Up to 1 million profiles per export to Marketo.</span></span>
- <span data-ttu-id="384ec-135">Export do Marketo je obmedzený na segmenty.</span><span class="sxs-lookup"><span data-stu-id="384ec-135">Exporting to Marketo is limited to segments.</span></span>
- <span data-ttu-id="384ec-136">Export segmentov s celkovým počtom 1 miliónov profilov môže trvať až 3 hodiny.</span><span class="sxs-lookup"><span data-stu-id="384ec-136">Exporting segments with a total of 1 million profiles can take up to 3 hours.</span></span> 
- <span data-ttu-id="384ec-137">Počet profilov, ktoré môžete exportovať do Marketo, závisí a je obmedzený vašou zmluvou so spoločnosťou Marketo.</span><span class="sxs-lookup"><span data-stu-id="384ec-137">The number of profiles that you can export to Marketo is dependent and limited on your contract with Marketo.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="384ec-138">Ochrana osobných údajov a dodržiavanie súladu s nariadeniami</span><span class="sxs-lookup"><span data-stu-id="384ec-138">Data privacy and compliance</span></span>

<span data-ttu-id="384ec-139">Keď povolíte prenos údajov spoločnosti Marketo v službe Dynamics 365 Customer Insights, povoľujete tým prenos údajov mimo hranice súladu so službou Dynamics 365 Customer Insights vrátane potenciálne citlivých údajov, ako sú napríklad osobné údaje.</span><span class="sxs-lookup"><span data-stu-id="384ec-139">When you enable Dynamics 365 Customer Insights to transmit data to Marketo, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="384ec-140">Spoločnosť Microsoft prenesie tieto údaje na váš pokyn, ale vy ste zodpovední za zabezpečenie toho, aby spoločnosť Marketo plnila všetky prípadné povinnosti týkajúce sa ochrany vašich osobných údajov alebo zabezpečenia.</span><span class="sxs-lookup"><span data-stu-id="384ec-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Marketo meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="384ec-141">Ďalšie informácie nájdete vo [vyhlásení o ochrane súkromia spoločnosti Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="384ec-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="384ec-142">Váš správca služby Dynamics 365 Customer Insights môže túto funkciu kedykoľvek prestať používať odstránením tohto cieľového umiestnenia exportu.</span><span class="sxs-lookup"><span data-stu-id="384ec-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]