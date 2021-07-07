---
title: Export údajov z Customer Insights do Sendinblue
description: Zistite, ako nakonfigurovať pripojenie a exportovať do Sendinblue.
ms.date: 06/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 58ca0ae5ad4a3a291f4336984d14fefb23a58ab3
ms.sourcegitcommit: 057079532e31c12bac36f374857ba3dc847d6ad0
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 06/29/2021
ms.locfileid: "6314673"
---
# <a name="export-segments-to-sendinblue-preview"></a><span data-ttu-id="324db-103">Export segmentov do Sendinblue (verzia Preview)</span><span class="sxs-lookup"><span data-stu-id="324db-103">Export segments to Sendinblue (preview)</span></span>

<span data-ttu-id="324db-104">Sendinblue umožňuje export segmentov zjednotených zákazníkov na tvorbu kampaní, poskytovanie e-mailového marketingu a využívanie konkrétny skupín zákazníkov.</span><span class="sxs-lookup"><span data-stu-id="324db-104">Export segments of unified customer profiles to generate campaigns, provide email marketing and use specific groups of customers with Sendinblue.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="324db-105">Predpoklad na pripojenie</span><span class="sxs-lookup"><span data-stu-id="324db-105">Prerequisites for connection</span></span>

-   <span data-ttu-id="324db-106">Máte [účet Sendinblue](https://www.sendinblue.com/) a zodpovedajúce poverenia správcu.</span><span class="sxs-lookup"><span data-stu-id="324db-106">You have a [Sendinblue account](https://www.sendinblue.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="324db-107">V rámci Sendinblue existujú zoznamy a zodpovedajúce ID.</span><span class="sxs-lookup"><span data-stu-id="324db-107">There are existing lists in Sendinblue and the corresponding IDs.</span></span>
-   <span data-ttu-id="324db-108">Máte [nakonfigurované segmenty](segments.md).</span><span class="sxs-lookup"><span data-stu-id="324db-108">You have [configured segments](segments.md).</span></span>
-   <span data-ttu-id="324db-109">Zjednotené profily zákazníkov v exportovaných segmentoch obsahujú pole predstavujúce e-mailovú adresu.</span><span class="sxs-lookup"><span data-stu-id="324db-109">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="324db-110">Známe obmedzenia</span><span class="sxs-lookup"><span data-stu-id="324db-110">Known limitations</span></span>

- <span data-ttu-id="324db-111">Až 1 milión profilov na jeden export do Sendinblue.</span><span class="sxs-lookup"><span data-stu-id="324db-111">Up to 1 million profiles per export to Sendinblue.</span></span>
- <span data-ttu-id="324db-112">Export do Sendinblue je obmedzený na segmenty.</span><span class="sxs-lookup"><span data-stu-id="324db-112">Exporting to Sendinblue is limited to segments.</span></span>
- <span data-ttu-id="324db-113">Export segmentov s celkovým počtom 1 miliónov profilov môže trvať do 90 minút.</span><span class="sxs-lookup"><span data-stu-id="324db-113">Exporting segments with a total of 1 million profiles can take up to 90 minutes.</span></span> 
- <span data-ttu-id="324db-114">Počet profilov, ktoré môžete exportovať do Sendinblue, ovplyvňuje a limituje vaša zmluva so spoločnosťou Sendinblue.</span><span class="sxs-lookup"><span data-stu-id="324db-114">The number of profiles that you can export to Sendinblue is dependent and limited on your contract with Sendinblue.</span></span>

## <a name="set-up-connection-to-sendinblue"></a><span data-ttu-id="324db-115">Nastavenie pripojenia k Sendinblue</span><span class="sxs-lookup"><span data-stu-id="324db-115">Set up connection to Sendinblue</span></span>

1. <span data-ttu-id="324db-116">Prejdite do časti **Správca** > **Pripojenia**.</span><span class="sxs-lookup"><span data-stu-id="324db-116">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="324db-117">Vyberte možnosť **Pridať pripojenie** a výberom položky **Sendinblue** nakonfigurujte pripojenie.</span><span class="sxs-lookup"><span data-stu-id="324db-117">Select **Add connection** and choose **Sendinblue** to configure the connection.</span></span>

1. <span data-ttu-id="324db-118">Do poľa **Zobrazovaný názov** zadajte rozpoznateľný názov pripojenia.</span><span class="sxs-lookup"><span data-stu-id="324db-118">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="324db-119">Zobrazovaný názov a typ spojenia, ktoré popisuje toto spojenie.</span><span class="sxs-lookup"><span data-stu-id="324db-119">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="324db-120">Odporúčame zvoliť názov, ktorý vysvetľuje účel a cieľ tohto spojenia.</span><span class="sxs-lookup"><span data-stu-id="324db-120">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="324db-121">Vyberte používateľov, ktorí môžu používať toto pripojenie.</span><span class="sxs-lookup"><span data-stu-id="324db-121">Choose who can use this connection.</span></span> <span data-ttu-id="324db-122">Predvolene sú to iba správcovia.</span><span class="sxs-lookup"><span data-stu-id="324db-122">By default it's only administrators.</span></span> <span data-ttu-id="324db-123">Viac informácií nájdete v časti [Umožnite prispievateľom použiť pripojenie na export](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="324db-123">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="324db-124">Zadajte svoj **[kľúč rozhrania API pre SendinBlue](https://developers.sendinblue.com/docs/getting-started#:~:text=Get%20your%20API%20key&text=You%20can%20create%20one%20from,your%20settings%20This%20API%20key)**.</span><span class="sxs-lookup"><span data-stu-id="324db-124">Enter your **[SendinBlue API key](https://developers.sendinblue.com/docs/getting-started#:~:text=Get%20your%20API%20key&text=You%20can%20create%20one%20from,your%20settings%20This%20API%20key)**.</span></span>

1. <span data-ttu-id="324db-125">Výberom možnosti **Súhlasím** potvrďte položku **Ochrana osobných údajov a dodržiavanie súladu s nariadeniami** a výberom možnosti **Pripojiť** inicializujte pripojenie k Sendinblue.</span><span class="sxs-lookup"><span data-stu-id="324db-125">Select **I agree** to confirm the **Data privacy and compliance** and select **Connect** to initialize the connection to Sendinblue.</span></span>

1. <span data-ttu-id="324db-126">Vyberte položku **Pridať samého seba ako používateľa exportu** a uveďte svoje poverenia pre Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="324db-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="324db-127">Stlačte možnosť **Uložiť** a dokončite pripojenie.</span><span class="sxs-lookup"><span data-stu-id="324db-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="324db-128">Nakonfigurujte export</span><span class="sxs-lookup"><span data-stu-id="324db-128">Configure an export</span></span>

<span data-ttu-id="324db-129">Tento export môžete nakonfigurovať, ak máte prístup k pripojeniu tohto typu.</span><span class="sxs-lookup"><span data-stu-id="324db-129">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="324db-130">Viac informácií nájdete na stránke [Na konfiguráciu exportu sú potrebné povolenia](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="324db-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="324db-131">Prejdite na **Údaje** > **Exporty**.</span><span class="sxs-lookup"><span data-stu-id="324db-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="324db-132">Na vytvorenie nového exportu stlačte možnosť **Pridať cieľ**.</span><span class="sxs-lookup"><span data-stu-id="324db-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="324db-133">V poli **Pripojenie na export** vyberte pripojenie zo sekcie Sendinblue.</span><span class="sxs-lookup"><span data-stu-id="324db-133">In the **Connection for export** field, choose a connection from the Sendinblue section.</span></span> <span data-ttu-id="324db-134">Ak nevidíte názov tejto sekcie, nemáte k dispozícii žiadne spojenia tohto typu.</span><span class="sxs-lookup"><span data-stu-id="324db-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="324db-135">Zadajte svoje **ID zoznamu aplikácie Sendinblue**</span><span class="sxs-lookup"><span data-stu-id="324db-135">Enter your **Sendinblue list ID**</span></span> 

1. <span data-ttu-id="324db-136">V sekcii **Párovanie údajov** v poli **E-mail** do svojho zjednoteného profilu zákazníka vyberte pole, ktoré predstavuje e-mailovú adresu zákazníka.</span><span class="sxs-lookup"><span data-stu-id="324db-136">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="324db-137">Prípadne môžete aj exportovať **krstné meno**, **priezvisko** a **telefón**, a vytvoriť tak prispôsobenejšie e-maily.</span><span class="sxs-lookup"><span data-stu-id="324db-137">Optionally, you can export **First name**, **Last name**, and **Phone**  to create more personalized emails.</span></span> <span data-ttu-id="324db-138">Výberom položky **Pridať atribút** namapujete tieto polia.</span><span class="sxs-lookup"><span data-stu-id="324db-138">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="324db-139">Vyberte segmenty, ktoré chcete exportovať.</span><span class="sxs-lookup"><span data-stu-id="324db-139">Select the segments you want to export.</span></span> 

1. <span data-ttu-id="324db-140">Vyberte položku **Uložiť**.</span><span class="sxs-lookup"><span data-stu-id="324db-140">Select **Save**.</span></span>

<span data-ttu-id="324db-141">Uloženie exportu nespustí export okamžite.</span><span class="sxs-lookup"><span data-stu-id="324db-141">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="324db-142">Export prebieha s každým [plánovaným obnovením](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="324db-142">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="324db-143">Môžete tiež [exportovať údaje na požiadanie](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="324db-143">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="324db-144">Ochrana osobných údajov a dodržiavanie súladu s nariadeniami</span><span class="sxs-lookup"><span data-stu-id="324db-144">Data privacy and compliance</span></span>

<span data-ttu-id="324db-145">Keď povolíte službe Dynamics 365 Customer Insights, aby prenášala údaje do Sendinblue, povoľujete tým aj prenos údajov mimo hranice súladu so službou Dynamics 365 Customer Insights vrátane potenciálne citlivých údajov, ako sú napríklad osobné údaje.</span><span class="sxs-lookup"><span data-stu-id="324db-145">When you enable Dynamics 365 Customer Insights to transmit data to Sendinblue, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="324db-146">Microsoft prenesie tieto údaje na váš pokyn, ale vy ste zodpovední za zabezpečenie toho, aby Sendinblue spĺňal všetky záväzky týkajúce sa ochrany vášho súkromia alebo bezpečnosti.</span><span class="sxs-lookup"><span data-stu-id="324db-146">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Sendinblue meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="324db-147">Ďalšie informácie nájdete vo [vyhlásení o ochrane súkromia spoločnosti Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="324db-147">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="324db-148">Váš správca služby Dynamics 365 Customer Insights môže túto funkciu kedykoľvek prestať používať odstránením tohto cieľového umiestnenia exportu.</span><span class="sxs-lookup"><span data-stu-id="324db-148">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
