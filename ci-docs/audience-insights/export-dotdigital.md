---
title: Export údajov služby Customer Insights do DotDigital
description: Zistite, ako môžete nakonfigurovať pripojenie k DotDigital.
ms.date: 11/14/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: ed6bd40e8575fc90258f79f60abffe54f136d274
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 11/25/2020
ms.locfileid: "4644467"
---
# <a name="connector-for-dotdigital-preview"></a><span data-ttu-id="66f92-103">Konektor pre DotDigital (ukážka)</span><span class="sxs-lookup"><span data-stu-id="66f92-103">Connector for DotDigital (preview)</span></span>

<span data-ttu-id="66f92-104">Exportujte segmenty zjednotených profilov zákazníkov do adresárov DotDigital a použite ich na kampane, e-mailový marketing a na vytváranie segmentov zákazníkov cez DotDigital.</span><span class="sxs-lookup"><span data-stu-id="66f92-104">Export segments of unified customer profiles to DotDigital address books and use them for campaigns, email marketing, and to build customer segments with DotDigital.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="66f92-105">Predpoklady</span><span class="sxs-lookup"><span data-stu-id="66f92-105">Prerequisites</span></span>

-   <span data-ttu-id="66f92-106">Máte [účet DotDigital](https://dotdigital.com/) a zodpovedajúce poverenia správcu.</span><span class="sxs-lookup"><span data-stu-id="66f92-106">You have a [DotDigital account](https://dotdigital.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="66f92-107">V DotDigital a zodpovedajúcich ID existujú adresáre.</span><span class="sxs-lookup"><span data-stu-id="66f92-107">There are existing address books in DotDigital and the corresponding IDs.</span></span> <span data-ttu-id="66f92-108">ID nájdete v adrese URL, keď vyberiete a otvoríte adresár.</span><span class="sxs-lookup"><span data-stu-id="66f92-108">The ID can be found in the URL when you select and open an address book.</span></span> <span data-ttu-id="66f92-109">Ďalšie informácie nájdete v [adresároch DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span><span class="sxs-lookup"><span data-stu-id="66f92-109">For more information, see [DotDigital address books](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span></span>
-   <span data-ttu-id="66f92-110">Máte [konfigurované segmenty](segments.md) v prehľadoch cieľových skupín.</span><span class="sxs-lookup"><span data-stu-id="66f92-110">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="66f92-111">Zjednotené profily zákazníkov v exportovaných segmentoch obsahujú pole predstavujúce e-mailovú adresu.</span><span class="sxs-lookup"><span data-stu-id="66f92-111">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-dotdigital"></a><span data-ttu-id="66f92-112">Pripojiť k DotDigital</span><span class="sxs-lookup"><span data-stu-id="66f92-112">Connect to DotDigital</span></span>

1. <span data-ttu-id="66f92-113">Prejdite do ponuky **Správca** > **Ciele exportu**.</span><span class="sxs-lookup"><span data-stu-id="66f92-113">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="66f92-114">V časti **DotDigital** vyberte položku **Nastaviť**.</span><span class="sxs-lookup"><span data-stu-id="66f92-114">Under **DotDigital**, select **Set up**.</span></span>

1. <span data-ttu-id="66f92-115">Do poľa **Zobrazovaný názov** zadajte rozpoznateľný názov cieľa exportu.</span><span class="sxs-lookup"><span data-stu-id="66f92-115">Give your export destination a recognizable name in the **Display name** field.</span></span>

   :::image type="content" source="media/DotDigital_config.PNG" alt-text="Konfiguračná tabla pre export do DotDigital.":::

1. <span data-ttu-id="66f92-117">Zadajte **používateľské meno a heslo pre DotDigital**.</span><span class="sxs-lookup"><span data-stu-id="66f92-117">Enter your **DotDigital username and password**.</span></span>

1. <span data-ttu-id="66f92-118">Zadajte **[ID adresára DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**.</span><span class="sxs-lookup"><span data-stu-id="66f92-118">Enter your **[DotDigital address book ID](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**.</span></span>

1. <span data-ttu-id="66f92-119">Vyberte **Súhlasím** na potvrdenie **Ochrany osobných údajov a dodržiavanie súladu s nariadeniami**.</span><span class="sxs-lookup"><span data-stu-id="66f92-119">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="66f92-120">Vyberte položku **Pripojiť** na inicializáciu pripojenia k DotDigital.</span><span class="sxs-lookup"><span data-stu-id="66f92-120">Select **Connect** to initialize the connection to DotDigital.</span></span>

1. <span data-ttu-id="66f92-121">Vyberte položku **Pridať samého seba ako používateľa exportu** a uveďte svoje poverenia pre Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="66f92-121">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="66f92-122">Vyberte **Ďalej** a nakonfigurujte export.</span><span class="sxs-lookup"><span data-stu-id="66f92-122">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="66f92-123">Nakonfigurujte konektor</span><span class="sxs-lookup"><span data-stu-id="66f92-123">Configure the connector</span></span>

1. <span data-ttu-id="66f92-124">V sekcii **Párovanie údajov** v poli **E-mail** do svojho zjednoteného profilu zákazníka vyberte pole, ktoré predstavuje e-mailovú adresu zákazníka.</span><span class="sxs-lookup"><span data-stu-id="66f92-124">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="66f92-125">Rovnaký postup zopakujte pri ďalších voliteľných poliach, ako je **Krstné meno**, **Priezvisko**, **Celé meno**, **Rod** a **PSČ**.</span><span class="sxs-lookup"><span data-stu-id="66f92-125">Repeat the same steps for other optional fields such as **First name**, **Last name**, **Full name**, **Gender**, and **Post code**.</span></span>

1. <span data-ttu-id="66f92-126">Vyberte segmenty, ktoré chcete exportovať.</span><span class="sxs-lookup"><span data-stu-id="66f92-126">Select the segments you want to export.</span></span> <span data-ttu-id="66f92-127">Do DotDigital môžete exportovať spolu až 1 milión zákazníckych profilov.</span><span class="sxs-lookup"><span data-stu-id="66f92-127">You can export up to 1 million customer profiles in total to DotDigital.</span></span>

1. <span data-ttu-id="66f92-128">Vyberte položku **Uložiť**.</span><span class="sxs-lookup"><span data-stu-id="66f92-128">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="66f92-129">Export údajov</span><span class="sxs-lookup"><span data-stu-id="66f92-129">Export the data</span></span>

<span data-ttu-id="66f92-130">Môžete [exportovať údaje na vyžiadanie](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="66f92-130">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="66f92-131">Export sa spustí aj pri každej [plánovanej obnove](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="66f92-131">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="66f92-132">V DotDigital teraz nájdete svoje segmenty v [adresároch DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span><span class="sxs-lookup"><span data-stu-id="66f92-132">In DotDigital, you can now find your segments in [DotDigital address books](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="66f92-133">Známe obmedzenia</span><span class="sxs-lookup"><span data-stu-id="66f92-133">Known limitations</span></span>

- <span data-ttu-id="66f92-134">Až 1 milión profilov na export do DotDigital.</span><span class="sxs-lookup"><span data-stu-id="66f92-134">Up to 1 million profiles per export to DotDigital.</span></span>
- <span data-ttu-id="66f92-135">Export do DotDigital je obmedzený na segmenty.</span><span class="sxs-lookup"><span data-stu-id="66f92-135">Exporting to DotDigital is limited to segments.</span></span>
- <span data-ttu-id="66f92-136">Export segmentov s celkovým počtom 1 miliónov profilov môže trvať až 3 hodiny z dôvodu obmedzení na strane poskytovateľa.</span><span class="sxs-lookup"><span data-stu-id="66f92-136">Exporting segments with a total of 1 million profiles can take up to 3 hours because of limitations on the provider side.</span></span> 
- <span data-ttu-id="66f92-137">Počet profilov, ktoré môžete exportovať do DotDigital, závisí a je obmedzený vašou zmluvou so spoločnosťou DotDigital.</span><span class="sxs-lookup"><span data-stu-id="66f92-137">The number of profiles that you can export to DotDigital is dependent and limited on your contract with DotDigital.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="66f92-138">Ochrana osobných údajov a dodržiavanie súladu s nariadeniami</span><span class="sxs-lookup"><span data-stu-id="66f92-138">Data privacy and compliance</span></span>

<span data-ttu-id="66f92-139">Keď povolíte prenos údajov spoločnosti DotDigital v službe Dynamics 365 Customer Insights, povoľujete tým prenos údajov mimo hranice súladu so službou Dynamics 365 Customer Insights vrátane potenciálne citlivých údajov, ako sú napríklad osobné údaje.</span><span class="sxs-lookup"><span data-stu-id="66f92-139">When you enable Dynamics 365 Customer Insights to transmit data to DotDigital, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="66f92-140">Spoločnosť Microsoft prenesie tieto údaje na váš pokyn, ale vy ste zodpovední za zabezpečenie toho, aby spoločnosť DotDigital plnila všetky prípadné povinnosti týkajúce sa ochrany vašich osobných údajov alebo zabezpečenia.</span><span class="sxs-lookup"><span data-stu-id="66f92-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that DotDigital meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="66f92-141">Ďalšie informácie nájdete vo [vyhlásení o ochrane súkromia spoločnosti Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="66f92-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="66f92-142">Váš správca služby Dynamics 365 Customer Insights môže túto funkciu kedykoľvek prestať používať odstránením tohto cieľového umiestnenia exportu.</span><span class="sxs-lookup"><span data-stu-id="66f92-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
