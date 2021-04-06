---
title: Export údajov služby Customer Insights do SendGrid
description: Zistite, ako môžete nakonfigurovať pripojenie k SendGrid.
ms.date: 12/08/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 1a1f679fa42d47d524ebfdd6e931ae2822565f77
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597300"
---
# <a name="connector-for-sendgrid-preview"></a><span data-ttu-id="c5b8f-103">Konektor pre SendGrid (ukážka)</span><span class="sxs-lookup"><span data-stu-id="c5b8f-103">Connector for SendGrid (preview)</span></span>

<span data-ttu-id="c5b8f-104">Exportujte segmenty zjednotených profilov zákazníkov do zoznamov kontaktov SendGrid a použite ich pre kampane a e-mailový marketing v SendGrid.</span><span class="sxs-lookup"><span data-stu-id="c5b8f-104">Export segments of unified customer profiles to SendGrid contact lists and use them for campaigns and email marketing in SendGrid.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="c5b8f-105">Predpoklady</span><span class="sxs-lookup"><span data-stu-id="c5b8f-105">Prerequisites</span></span>

-   <span data-ttu-id="c5b8f-106">Máte [účet SendGrid](https://sendgrid.com/) a zodpovedajúce poverenia správcu.</span><span class="sxs-lookup"><span data-stu-id="c5b8f-106">You have a [SendGrid account](https://sendgrid.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="c5b8f-107">V službe SendGrid existujú zoznamy kontaktov a zodpovedajúce ID.</span><span class="sxs-lookup"><span data-stu-id="c5b8f-107">There are existing contact lists in SendGrid and the corresponding IDs.</span></span> <span data-ttu-id="c5b8f-108">Ďalšie informácie nájdete v časti [SendGrid – spravovanie kontaktov](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts).</span><span class="sxs-lookup"><span data-stu-id="c5b8f-108">For more information, see [SendGrid - Manage contacts](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts).</span></span>
-   <span data-ttu-id="c5b8f-109">Máte [konfigurované segmenty](segments.md) v prehľadoch cieľových skupín.</span><span class="sxs-lookup"><span data-stu-id="c5b8f-109">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="c5b8f-110">Zjednotené profily zákazníkov v exportovaných segmentoch obsahujú pole predstavujúce e-mailovú adresu.</span><span class="sxs-lookup"><span data-stu-id="c5b8f-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-sendgrid"></a><span data-ttu-id="c5b8f-111">Pripojenie k SendGrid</span><span class="sxs-lookup"><span data-stu-id="c5b8f-111">Connect to SendGrid</span></span>

1. <span data-ttu-id="c5b8f-112">Prejdite do ponuky **Správca** > **Ciele exportu**.</span><span class="sxs-lookup"><span data-stu-id="c5b8f-112">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="c5b8f-113">V časti **SendGrid** vyberte položku **Nastaviť**.</span><span class="sxs-lookup"><span data-stu-id="c5b8f-113">Under **SendGrid**, select **Set up**.</span></span>

1. <span data-ttu-id="c5b8f-114">Do poľa **Zobrazovaný názov** zadajte rozpoznateľný názov cieľa exportu.</span><span class="sxs-lookup"><span data-stu-id="c5b8f-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

   :::image type="content" source="media/export-sendgrid.PNG" alt-text="Tabla konfigurácie exportu SendGrid.":::

1. <span data-ttu-id="c5b8f-116">Zadajte svoj **Kľúč API SendGrid** [Kľúč API SendGrid](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).</span><span class="sxs-lookup"><span data-stu-id="c5b8f-116">Enter your **SendGrid API key** [SendGrid API key](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).</span></span>

1. <span data-ttu-id="c5b8f-117">Zadajte svoje **[ID zoznamu SendGrid](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)**.</span><span class="sxs-lookup"><span data-stu-id="c5b8f-117">Enter your **[SendGrid list ID](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)**.</span></span>

1. <span data-ttu-id="c5b8f-118">Vyberte **Súhlasím** na potvrdenie **Ochrany osobných údajov a dodržiavanie súladu s nariadeniami**.</span><span class="sxs-lookup"><span data-stu-id="c5b8f-118">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="c5b8f-119">Vyberte položku **Pripojiť** na inicializáciu pripojenia k SendGrid.</span><span class="sxs-lookup"><span data-stu-id="c5b8f-119">Select **Connect** to initialize the connection to SendGrid.</span></span>

1. <span data-ttu-id="c5b8f-120">Vyberte položku **Pridať samého seba ako používateľa exportu** a uveďte svoje poverenia pre Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="c5b8f-120">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="c5b8f-121">Vyberte **Ďalej** a nakonfigurujte export.</span><span class="sxs-lookup"><span data-stu-id="c5b8f-121">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="c5b8f-122">Nakonfigurujte konektor</span><span class="sxs-lookup"><span data-stu-id="c5b8f-122">Configure the connector</span></span>

1. <span data-ttu-id="c5b8f-123">V sekcii **Párovanie údajov** v poli **E-mail** do svojho zjednoteného profilu zákazníka vyberte pole, ktoré predstavuje e-mailovú adresu zákazníka.</span><span class="sxs-lookup"><span data-stu-id="c5b8f-123">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="c5b8f-124">Rovnaký postup zopakujte pri ďalších voliteľných poliach, ako je **Krstné meno**, **Priezvisko**, **Krajina/región**, **Štát**, **Mesto** a **PSČ**.</span><span class="sxs-lookup"><span data-stu-id="c5b8f-124">Repeat the same steps for other optional fields such as **First name**, **Last name**, **Country/Region**, **State**, **City**, and **Post code**.</span></span>

1. <span data-ttu-id="c5b8f-125">Vyberte segmenty, ktoré chcete exportovať.</span><span class="sxs-lookup"><span data-stu-id="c5b8f-125">Select the segments you want to export.</span></span> <span data-ttu-id="c5b8f-126">Dôrazne **odporúčame neexportovať celkovo viac ako 100 000 profilov zákazníkov** do SendGrid.</span><span class="sxs-lookup"><span data-stu-id="c5b8f-126">We strongly **recommend to not export more than 100'000 customer profiles in total** to SendGrid.</span></span> 

1. <span data-ttu-id="c5b8f-127">Vyberte položku **Uložiť**.</span><span class="sxs-lookup"><span data-stu-id="c5b8f-127">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="c5b8f-128">Export údajov</span><span class="sxs-lookup"><span data-stu-id="c5b8f-128">Export the data</span></span>

<span data-ttu-id="c5b8f-129">Môžete [exportovať údaje na vyžiadanie](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="c5b8f-129">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="c5b8f-130">Export sa spustí aj pri každej [plánovanej obnove](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="c5b8f-130">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="c5b8f-131">Známe obmedzenia</span><span class="sxs-lookup"><span data-stu-id="c5b8f-131">Known limitations</span></span>

- <span data-ttu-id="c5b8f-132">Až 100 000 profilov celkovo do služby SendGrid.</span><span class="sxs-lookup"><span data-stu-id="c5b8f-132">Up to 100'000 profiles in total to SendGrid.</span></span>
- <span data-ttu-id="c5b8f-133">Export do SendGrid je obmedzený na segmenty.</span><span class="sxs-lookup"><span data-stu-id="c5b8f-133">Exporting to SendGrid is limited to segments.</span></span>
- <span data-ttu-id="c5b8f-134">Export až 100 000 profilov do služby SendGrid môže trvať až niekoľko hodín.</span><span class="sxs-lookup"><span data-stu-id="c5b8f-134">Exporting up to 100'000 profiles to SendGrid can take up to a few hours to complete.</span></span> 
- <span data-ttu-id="c5b8f-135">Počet profilov, ktoré môžete exportovať do SendGrid, závisí a je obmedzený vašou zmluvou so spoločnosťou SendGrid.</span><span class="sxs-lookup"><span data-stu-id="c5b8f-135">The number of profiles that you can export to SendGrid is dependent and limited on your contract with SendGrid.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="c5b8f-136">Ochrana osobných údajov a dodržiavanie súladu s nariadeniami</span><span class="sxs-lookup"><span data-stu-id="c5b8f-136">Data privacy and compliance</span></span>

<span data-ttu-id="c5b8f-137">Keď povolíte službe Dynamics 365 Customer Insights prenos údajov do SendGrid, povoľujete tým prenos údajov mimo hranice súladu so službou Dynamics 365 Customer Insights vrátane potenciálne citlivých údajov, ako sú napríklad osobné údaje.</span><span class="sxs-lookup"><span data-stu-id="c5b8f-137">When you enable Dynamics 365 Customer Insights to transmit data to SendGrid, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="c5b8f-138">Spoločnosť Microsoft prenesie tieto údaje na váš pokyn, ale vy ste zodpovední za zabezpečenie toho, aby SendGrid plnila všetky prípadné povinnosti týkajúce sa ochrany vašich osobných údajov alebo zabezpečenia.</span><span class="sxs-lookup"><span data-stu-id="c5b8f-138">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that SendGrid meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="c5b8f-139">Ďalšie informácie nájdete vo [vyhlásení o ochrane súkromia spoločnosti Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="c5b8f-139">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="c5b8f-140">Váš správca služby Dynamics 365 Customer Insights môže túto funkciu kedykoľvek prestať používať odstránením tohto cieľového umiestnenia exportu.</span><span class="sxs-lookup"><span data-stu-id="c5b8f-140">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]