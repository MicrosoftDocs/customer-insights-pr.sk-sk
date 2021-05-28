---
title: Export údajov služby Customer Insights do Marketo
description: Zistite ako nakonfigurovať pripojenie a realizovať exportovanie do Marketo.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: b5a644e286bd44d4ebf7d1837255326c005b48d6
ms.sourcegitcommit: 74cd4fa9cbb784d9dff174c0eec7b4dcb408d66b
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 05/18/2021
ms.locfileid: "6059335"
---
# <a name="export-segments-to-marketo-preview"></a><span data-ttu-id="37c07-103">Export segmentov do Marketo (ukážka)</span><span class="sxs-lookup"><span data-stu-id="37c07-103">Export segments to Marketo (preview)</span></span>

<span data-ttu-id="37c07-104">Marketo umožňuje export zjednotených profilov zákazníkov s cieľom vytvárať kampane, poskytovať e-mailový marketing a využívať konkrétne skupiny zákazníkov.</span><span class="sxs-lookup"><span data-stu-id="37c07-104">Export segments of unified customer profiles to generate campaigns, provide email marketing and use specific groups of customers with Marketo.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="37c07-105">Predpoklad na pripojenie</span><span class="sxs-lookup"><span data-stu-id="37c07-105">Prerequisites for connection</span></span>

-   <span data-ttu-id="37c07-106">Máte [účet Marketo](https://login.marketo.com/) a zodpovedajúce poverenia správcu.</span><span class="sxs-lookup"><span data-stu-id="37c07-106">You have a [Marketo account](https://login.marketo.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="37c07-107">V službe Marketo a zodpovedajúcich ID existujú zoznamy.</span><span class="sxs-lookup"><span data-stu-id="37c07-107">There are existing lists in Marketo and the corresponding IDs.</span></span> <span data-ttu-id="37c07-108">Ďalšie informácie nájdete v téme [Zoznamy služby Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span><span class="sxs-lookup"><span data-stu-id="37c07-108">For more information, see [Marketo lists](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span></span>
-   <span data-ttu-id="37c07-109">Máte [nakonfigurované segmenty](segments.md).</span><span class="sxs-lookup"><span data-stu-id="37c07-109">You have [configured segments](segments.md).</span></span>
-   <span data-ttu-id="37c07-110">Zjednotené profily zákazníkov v exportovaných segmentoch obsahujú pole predstavujúce e-mailovú adresu.</span><span class="sxs-lookup"><span data-stu-id="37c07-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="37c07-111">Známe obmedzenia</span><span class="sxs-lookup"><span data-stu-id="37c07-111">Known limitations</span></span>

- <span data-ttu-id="37c07-112">Až 1 milión profilov na export do Marketo.</span><span class="sxs-lookup"><span data-stu-id="37c07-112">Up to 1 million profiles per export to Marketo.</span></span>
- <span data-ttu-id="37c07-113">Export do Marketo je obmedzený na segmenty.</span><span class="sxs-lookup"><span data-stu-id="37c07-113">Exporting to Marketo is limited to segments.</span></span>
- <span data-ttu-id="37c07-114">Export segmentov s celkovým počtom 1 miliónov profilov môže trvať až 3 hodiny.</span><span class="sxs-lookup"><span data-stu-id="37c07-114">Exporting segments with a total of 1 million profiles can take up to 3 hours.</span></span> 
- <span data-ttu-id="37c07-115">Počet profilov, ktoré môžete exportovať do Marketo, závisí a je obmedzený vašou zmluvou so spoločnosťou Marketo.</span><span class="sxs-lookup"><span data-stu-id="37c07-115">The number of profiles that you can export to Marketo is dependent and limited on your contract with Marketo.</span></span>

## <a name="set-up-connection-to-marketo"></a><span data-ttu-id="37c07-116">Nastavenie pripojenia k Marketo</span><span class="sxs-lookup"><span data-stu-id="37c07-116">Set up connection to Marketo</span></span>

1. <span data-ttu-id="37c07-117">Prejdite do časti **Správca** > **Pripojenia**.</span><span class="sxs-lookup"><span data-stu-id="37c07-117">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="37c07-118">Stlačte možnosť **Pridať pripojenie** a stlačením možnosti **Marketo** nakonfigurujte pripojenie.</span><span class="sxs-lookup"><span data-stu-id="37c07-118">Select **Add connection** and choose **Marketo** to configure the connection.</span></span>

1. <span data-ttu-id="37c07-119">Do poľa **Zobrazovaný názov** zadajte rozpoznateľný názov pripojenia.</span><span class="sxs-lookup"><span data-stu-id="37c07-119">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="37c07-120">Zobrazovaný názov a typ spojenia, ktoré popisuje toto spojenie.</span><span class="sxs-lookup"><span data-stu-id="37c07-120">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="37c07-121">Odporúčame zvoliť názov, ktorý vysvetľuje účel a cieľ tohto spojenia.</span><span class="sxs-lookup"><span data-stu-id="37c07-121">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="37c07-122">Vyberte používateľov, ktorí môžu používať toto pripojenie.</span><span class="sxs-lookup"><span data-stu-id="37c07-122">Choose who can use this connection.</span></span> <span data-ttu-id="37c07-123">Ak neurobíte nič, predvolená hodnota bude Správcovia.</span><span class="sxs-lookup"><span data-stu-id="37c07-123">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="37c07-124">Viac informácií nájdete v časti [Umožnite prispievateľom použiť pripojenie na export](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="37c07-124">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="37c07-125">Zadajte svoje **[ID klienta Marketo, tajný kľúč klienta a názov hostiteľa koncového bodu REST](https://developers.marketo.com/rest-api/authentication/)**.</span><span class="sxs-lookup"><span data-stu-id="37c07-125">Enter your **[Marketo client ID, Client secret, and REST Endpoint Hostname](https://developers.marketo.com/rest-api/authentication/)**.</span></span> <span data-ttu-id="37c07-126">Názov hostiteľa koncového bodu REST je iba názov hostiteľa bez `https://`.</span><span class="sxs-lookup"><span data-stu-id="37c07-126">The REST Endpoint Hostname is the hostname only, without `https://`.</span></span> <span data-ttu-id="37c07-127">Príklad: `xyz-abc-123.mktorest.com`.</span><span class="sxs-lookup"><span data-stu-id="37c07-127">Example: `xyz-abc-123.mktorest.com`.</span></span> 

1. <span data-ttu-id="37c07-128">Výberom položky **Súhlasím** potvrďte **Ochranu osobných údajov a dodržiavanie súladu s nariadeniami** a vyberte položku **Pripojiť** na inicializáciu pripojenia k službe Marketo.</span><span class="sxs-lookup"><span data-stu-id="37c07-128">Select **I agree** to confirm the **Data privacy and compliance** and select **Connect** to initialize the connection to Marketo.</span></span>

1. <span data-ttu-id="37c07-129">Vyberte položku **Pridať samého seba ako používateľa exportu** a uveďte svoje poverenia pre Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="37c07-129">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="37c07-130">Stlačte možnosť **Uložiť** a dokončite pripojenie.</span><span class="sxs-lookup"><span data-stu-id="37c07-130">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="37c07-131">Nakonfigurujte export</span><span class="sxs-lookup"><span data-stu-id="37c07-131">Configure an export</span></span>

<span data-ttu-id="37c07-132">Tento export môžete nakonfigurovať, ak máte prístup k pripojeniu tohto typu.</span><span class="sxs-lookup"><span data-stu-id="37c07-132">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="37c07-133">Viac informácií nájdete na stránke [Na konfiguráciu exportu sú potrebné povolenia](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="37c07-133">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="37c07-134">Prejdite na **Údaje** > **Exporty**.</span><span class="sxs-lookup"><span data-stu-id="37c07-134">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="37c07-135">Na vytvorenie nového exportu stlačte možnosť **Pridať cieľ**.</span><span class="sxs-lookup"><span data-stu-id="37c07-135">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="37c07-136">V poli **Pripojenie na export** vyberte pripojenie v časti Marketo.</span><span class="sxs-lookup"><span data-stu-id="37c07-136">In the **Connection for export** field, choose a connection from the Marketo section.</span></span> <span data-ttu-id="37c07-137">Ak nevidíte názov tejto sekcie, nemáte k dispozícii žiadne spojenia tohto typu.</span><span class="sxs-lookup"><span data-stu-id="37c07-137">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="37c07-138">Zadajte svoje **[ID zoznamu Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)**.</span><span class="sxs-lookup"><span data-stu-id="37c07-138">Enter your **[Marketo list ID](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)**.</span></span> <span data-ttu-id="37c07-139">ID zoznamu je čisto číselná hodnota.</span><span class="sxs-lookup"><span data-stu-id="37c07-139">The list ID is a purely numerical value.</span></span> <span data-ttu-id="37c07-140">Napríklad, ak je vaše ID v zozname Marketo ST12345A7, odstráňte znak pred a za číslicami a zadajte `12345`.</span><span class="sxs-lookup"><span data-stu-id="37c07-140">For example, if your Marketo list ID is ST12345A7, remove the character before and after the numerals and enter `12345`.</span></span> 

1. <span data-ttu-id="37c07-141">V sekcii **Párovanie údajov** v poli **E-mail** do svojho zjednoteného profilu zákazníka vyberte pole, ktoré predstavuje e-mailovú adresu zákazníka.</span><span class="sxs-lookup"><span data-stu-id="37c07-141">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="37c07-142">Voliteľné možno exportovať **Meno**, **Priezvisko**, **Mesto**, **Štát** a **Krajina/oblasť** a vytvorte si viac prispôsobené e-maily.</span><span class="sxs-lookup"><span data-stu-id="37c07-142">Optionally, you can export **First name**, **Last name**, **City**, **State**, and **Country/Region**  to create more personalized emails.</span></span> <span data-ttu-id="37c07-143">Výberom položky **Pridať atribút** namapujete tieto polia.</span><span class="sxs-lookup"><span data-stu-id="37c07-143">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="37c07-144">Vyberte segmenty, ktoré chcete exportovať.</span><span class="sxs-lookup"><span data-stu-id="37c07-144">Select the segments you want to export.</span></span> <span data-ttu-id="37c07-145">Do služby Marketo môžete exportovať spolu až 1 milión zákazníckych profilov.</span><span class="sxs-lookup"><span data-stu-id="37c07-145">You can export up to 1 million customer profiles in total to Marketo.</span></span>

1. <span data-ttu-id="37c07-146">Vyberte položku **Uložiť**.</span><span class="sxs-lookup"><span data-stu-id="37c07-146">Select **Save**.</span></span>

<span data-ttu-id="37c07-147">Uloženie exportu nespustí export okamžite.</span><span class="sxs-lookup"><span data-stu-id="37c07-147">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="37c07-148">Export prebieha s každým [plánovaným obnovením](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="37c07-148">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="37c07-149">Môžete tiež [exportovať údaje na požiadanie](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="37c07-149">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> <span data-ttu-id="37c07-150">V službe Marketo teraz nájdete svoje segmenty v sekcii [Zoznamy Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span><span class="sxs-lookup"><span data-stu-id="37c07-150">In Marketo, you can now find your segments under [Marketo lists](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span></span>


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="37c07-151">Ochrana osobných údajov a dodržiavanie súladu s nariadeniami</span><span class="sxs-lookup"><span data-stu-id="37c07-151">Data privacy and compliance</span></span>

<span data-ttu-id="37c07-152">Keď povolíte prenos údajov spoločnosti Marketo v službe Dynamics 365 Customer Insights, povoľujete tým prenos údajov mimo hranice súladu so službou Dynamics 365 Customer Insights vrátane potenciálne citlivých údajov, ako sú napríklad osobné údaje.</span><span class="sxs-lookup"><span data-stu-id="37c07-152">When you enable Dynamics 365 Customer Insights to transmit data to Marketo, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="37c07-153">Spoločnosť Microsoft prenesie tieto údaje na váš pokyn, ale vy ste zodpovední za zabezpečenie toho, aby spoločnosť Marketo plnila všetky prípadné povinnosti týkajúce sa ochrany vašich osobných údajov alebo zabezpečenia.</span><span class="sxs-lookup"><span data-stu-id="37c07-153">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Marketo meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="37c07-154">Ďalšie informácie nájdete vo [vyhlásení o ochrane súkromia spoločnosti Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="37c07-154">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="37c07-155">Váš správca služby Dynamics 365 Customer Insights môže túto funkciu kedykoľvek prestať používať odstránením tohto cieľového umiestnenia exportu.</span><span class="sxs-lookup"><span data-stu-id="37c07-155">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
