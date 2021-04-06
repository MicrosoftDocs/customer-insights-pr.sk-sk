---
title: Export údajov služby Customer Insights do Autopilot
description: Zistite, ako môžete nakonfigurovať pripojenie k Autopilot.
ms.date: 12/08/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6d039c4afd84eaad942d214d4e6fb8ef7b1ec72a
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596150"
---
# <a name="connector-for-autopilot-preview"></a><span data-ttu-id="1266a-103">Konektor pre Autopilot (ukážka)</span><span class="sxs-lookup"><span data-stu-id="1266a-103">Connector for Autopilot (preview)</span></span>

<span data-ttu-id="1266a-104">Exportujte segmenty zjednotených profilov zákazníkov do služby Autopilot a použite ich na e-mailový marketing v službe Autopilot.</span><span class="sxs-lookup"><span data-stu-id="1266a-104">Export segments of unified customer profiles to Autopilot and use them for email marketing in Autopilot.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="1266a-105">Predpoklady</span><span class="sxs-lookup"><span data-stu-id="1266a-105">Prerequisites</span></span>

-   <span data-ttu-id="1266a-106">Máte [účet Autopilot](https://www.autopilothq.com/) a zodpovedajúce poverenia správcu.</span><span class="sxs-lookup"><span data-stu-id="1266a-106">You have an [Autopilot account](https://www.autopilothq.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="1266a-107">Máte [konfigurované segmenty](segments.md) v prehľadoch cieľových skupín.</span><span class="sxs-lookup"><span data-stu-id="1266a-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="1266a-108">Zjednotené profily zákazníkov v exportovaných segmentoch obsahujú pole predstavujúce e-mailovú adresu.</span><span class="sxs-lookup"><span data-stu-id="1266a-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-autopilot"></a><span data-ttu-id="1266a-109">Pripojenie k službe AutoPilot</span><span class="sxs-lookup"><span data-stu-id="1266a-109">Connect to Autopilot</span></span>

1. <span data-ttu-id="1266a-110">Prejdite do ponuky **Správca** > **Ciele exportu**.</span><span class="sxs-lookup"><span data-stu-id="1266a-110">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="1266a-111">V časti **Autopilot** vyberte položku **Nastaviť**.</span><span class="sxs-lookup"><span data-stu-id="1266a-111">Under **Autopilot**, select **Set up**.</span></span>

1. <span data-ttu-id="1266a-112">Do poľa **Zobrazovaný názov** zadajte rozpoznateľný názov cieľa exportu.</span><span class="sxs-lookup"><span data-stu-id="1266a-112">Give your export destination a recognizable name in the **Display name** field.</span></span>

   :::image type="content" source="media/export-autopilot.PNG" alt-text="Konfiguračná tabla na pripojenie služby Autopilot.":::

1. <span data-ttu-id="1266a-114">Zadajte svoj **Kľúč API pre Autopilot** [Kľúč API pre Autopilot](https://autopilot.docs.apiary.io/#).</span><span class="sxs-lookup"><span data-stu-id="1266a-114">Enter your **Autopilot API key** [Autopilot API key](https://autopilot.docs.apiary.io/#).</span></span>

1. <span data-ttu-id="1266a-115">Vyberte **Súhlasím** na potvrdenie **Ochrany osobných údajov a dodržiavanie súladu s nariadeniami**.</span><span class="sxs-lookup"><span data-stu-id="1266a-115">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="1266a-116">Vyberte položku **Pripojiť** na inicializáciu pripojenia k Autopilot.</span><span class="sxs-lookup"><span data-stu-id="1266a-116">Select **Connect** to initialize the connection to Autopilot.</span></span>

1. <span data-ttu-id="1266a-117">Vyberte položku **Pridať samého seba ako používateľa exportu** a uveďte svoje poverenia pre Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="1266a-117">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="1266a-118">Vyberte **Ďalej** a nakonfigurujte export.</span><span class="sxs-lookup"><span data-stu-id="1266a-118">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="1266a-119">Nakonfigurujte konektor</span><span class="sxs-lookup"><span data-stu-id="1266a-119">Configure the connector</span></span>

1. <span data-ttu-id="1266a-120">V sekcii **Párovanie údajov** v poli **E-mail** do svojho zjednoteného profilu zákazníka vyberte pole, ktoré predstavuje e-mailovú adresu zákazníka.</span><span class="sxs-lookup"><span data-stu-id="1266a-120">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="1266a-121">Rovnaký postup zopakujte pri ďalších voliteľných poliach, ako je **Krstné meno** a **Priezvisko**.</span><span class="sxs-lookup"><span data-stu-id="1266a-121">Repeat the same steps for other optional fields such as **First name**, **Last name**.</span></span>

1. <span data-ttu-id="1266a-122">Vyberte segmenty, ktoré chcete exportovať.</span><span class="sxs-lookup"><span data-stu-id="1266a-122">Select the segments you want to export.</span></span> <span data-ttu-id="1266a-123">Dôrazne **odporúčame neexportovať celkovo viac ako 100 000 profilov zákazníkov** do Autopilot.</span><span class="sxs-lookup"><span data-stu-id="1266a-123">We strongly **recommend to not export more than 100'000 customer profiles in total** to Autopilot.</span></span> 

1. <span data-ttu-id="1266a-124">Vyberte položku **Uložiť**.</span><span class="sxs-lookup"><span data-stu-id="1266a-124">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="1266a-125">Export údajov</span><span class="sxs-lookup"><span data-stu-id="1266a-125">Export the data</span></span>

<span data-ttu-id="1266a-126">Môžete [exportovať údaje na vyžiadanie](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="1266a-126">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="1266a-127">Export sa spustí aj pri každej [plánovanej obnove](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="1266a-127">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="1266a-128">Známe obmedzenia</span><span class="sxs-lookup"><span data-stu-id="1266a-128">Known limitations</span></span>

- <span data-ttu-id="1266a-129">Do služby Autopilot môžete exportovať spolu až 100 000 profilov.</span><span class="sxs-lookup"><span data-stu-id="1266a-129">You can export up to 100'000 profiles in total to Autopilot.</span></span>
- <span data-ttu-id="1266a-130">Export do Autopilot je obmedzený na segmenty.</span><span class="sxs-lookup"><span data-stu-id="1266a-130">Exporting to Autopilot is limited to segments.</span></span>
- <span data-ttu-id="1266a-131">Export až 100 000 profilov do služby Autopilot môže trvať až niekoľko hodín.</span><span class="sxs-lookup"><span data-stu-id="1266a-131">Exporting up to 100'000 profiles to Autopilot can take up to a few hours to complete.</span></span> 
- <span data-ttu-id="1266a-132">Počet profilov, ktoré môžete exportovať do Autopilot, závisí a je obmedzený vašou zmluvou so spoločnosťou Autopilot.</span><span class="sxs-lookup"><span data-stu-id="1266a-132">The number of profiles that you can export to Autopilot is dependent and limited on your contract with Autopilot.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="1266a-133">Ochrana osobných údajov a dodržiavanie súladu s nariadeniami</span><span class="sxs-lookup"><span data-stu-id="1266a-133">Data privacy and compliance</span></span>

<span data-ttu-id="1266a-134">Keď povolíte prenos údajov spoločnosti Autopilot v službe Dynamics 365 Customer Insights, povoľujete tým prenos údajov mimo hranice súladu so službou Dynamics 365 Customer Insights vrátane potenciálne citlivých údajov, ako sú napríklad osobné údaje.</span><span class="sxs-lookup"><span data-stu-id="1266a-134">When you enable Dynamics 365 Customer Insights to transmit data to Autopilot, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="1266a-135">Spoločnosť Microsoft prenesie tieto údaje na váš pokyn, ale vy ste zodpovední za zabezpečenie toho, aby spoločnosť Autopilot plnila všetky prípadné povinnosti týkajúce sa ochrany vašich osobných údajov alebo zabezpečenia.</span><span class="sxs-lookup"><span data-stu-id="1266a-135">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Autopilot meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="1266a-136">Ďalšie informácie nájdete vo [vyhlásení o ochrane súkromia spoločnosti Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="1266a-136">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="1266a-137">Váš správca služby Dynamics 365 Customer Insights môže túto funkciu kedykoľvek prestať používať odstránením tohto cieľového umiestnenia exportu.</span><span class="sxs-lookup"><span data-stu-id="1266a-137">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]