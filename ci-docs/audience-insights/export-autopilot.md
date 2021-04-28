---
title: Export údajov služby Customer Insights do Autopilot
description: Zistite ako nakonfigurovať pripojenie a realizovať exportovanie do Autopilot.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: e320a48d5b7c35b530e3a38567b226b804879e4e
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760162"
---
# <a name="export-segments-to-autopilot-preview"></a><span data-ttu-id="0824a-103">Export segmentov do Autopilot (ukážka)</span><span class="sxs-lookup"><span data-stu-id="0824a-103">Export segments to Autopilot (preview)</span></span>

<span data-ttu-id="0824a-104">Exportujte segmenty zjednotených profilov zákazníkov do služby Autopilot a použite ich na e-mailový marketing v službe Autopilot.</span><span class="sxs-lookup"><span data-stu-id="0824a-104">Export segments of unified customer profiles to Autopilot and use them for email marketing in Autopilot.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="0824a-105">Predpoklad na pripojenie</span><span class="sxs-lookup"><span data-stu-id="0824a-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="0824a-106">Máte [účet Autopilot](https://www.autopilothq.com/) a zodpovedajúce poverenia správcu.</span><span class="sxs-lookup"><span data-stu-id="0824a-106">You have an [Autopilot account](https://www.autopilothq.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="0824a-107">Máte [konfigurované segmenty](segments.md) v prehľadoch cieľových skupín.</span><span class="sxs-lookup"><span data-stu-id="0824a-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="0824a-108">Zjednotené profily zákazníkov v exportovaných segmentoch obsahujú pole predstavujúce e-mailovú adresu.</span><span class="sxs-lookup"><span data-stu-id="0824a-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="0824a-109">Známe obmedzenia</span><span class="sxs-lookup"><span data-stu-id="0824a-109">Known limitations</span></span>

- <span data-ttu-id="0824a-110">Do služby Autopilot môžete exportovať spolu až 100 000 profilov.</span><span class="sxs-lookup"><span data-stu-id="0824a-110">You can export up to 100'000 profiles in total to Autopilot.</span></span>
- <span data-ttu-id="0824a-111">Export do Autopilot je obmedzený na segmenty.</span><span class="sxs-lookup"><span data-stu-id="0824a-111">Exporting to Autopilot is limited to segments.</span></span>
- <span data-ttu-id="0824a-112">Export až 100 000 profilov do služby Autopilot môže trvať až niekoľko hodín.</span><span class="sxs-lookup"><span data-stu-id="0824a-112">Exporting up to 100'000 profiles to Autopilot can take up to a few hours to complete.</span></span> 
- <span data-ttu-id="0824a-113">Počet profilov, ktoré môžete exportovať do Autopilot, závisí a je obmedzený vašou zmluvou so spoločnosťou Autopilot.</span><span class="sxs-lookup"><span data-stu-id="0824a-113">The number of profiles that you can export to Autopilot is dependent and limited on your contract with Autopilot.</span></span>

## <a name="set-up-connection-to-autopilot"></a><span data-ttu-id="0824a-114">Nastavenie pripojenia k Autopilot</span><span class="sxs-lookup"><span data-stu-id="0824a-114">Set up connection to Autopilot</span></span>

1. <span data-ttu-id="0824a-115">Prejdite do časti **Správca** > **Pripojenia**.</span><span class="sxs-lookup"><span data-stu-id="0824a-115">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="0824a-116">Stlačte možnosť **Pridať pripojenie** a stlačením možnosti **Autopilot** nakonfigurujte pripojenie.</span><span class="sxs-lookup"><span data-stu-id="0824a-116">Select **Add connection** and choose **Autopilot** to configure the connection.</span></span>

1. <span data-ttu-id="0824a-117">Do poľa **Zobrazovaný názov** zadajte rozpoznateľný názov pripojenia.</span><span class="sxs-lookup"><span data-stu-id="0824a-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="0824a-118">Zobrazovaný názov a typ spojenia, ktoré popisuje toto spojenie.</span><span class="sxs-lookup"><span data-stu-id="0824a-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="0824a-119">Odporúčame zvoliť názov, ktorý vysvetľuje účel a cieľ tohto spojenia.</span><span class="sxs-lookup"><span data-stu-id="0824a-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="0824a-120">Vyberte používateľov, ktorí môžu používať toto pripojenie.</span><span class="sxs-lookup"><span data-stu-id="0824a-120">Choose who can use this connection.</span></span> <span data-ttu-id="0824a-121">Ak neurobíte nič, predvolená hodnota bude Správcovia.</span><span class="sxs-lookup"><span data-stu-id="0824a-121">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="0824a-122">Viac informácií nájdete v časti [Umožnite prispievateľom použiť pripojenie na export](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="0824a-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

3. <span data-ttu-id="0824a-123">Zadajte svoj [kľúč API Autopilot](https://autopilot.docs.apiary.io/#).</span><span class="sxs-lookup"><span data-stu-id="0824a-123">Enter your [Autopilot API key](https://autopilot.docs.apiary.io/#).</span></span>

1. <span data-ttu-id="0824a-124">Vyberte **Súhlasím** na potvrdenie **Ochrany osobných údajov a dodržiavanie súladu s nariadeniami**.</span><span class="sxs-lookup"><span data-stu-id="0824a-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="0824a-125">Vyberte položku **Pripojiť** na inicializáciu pripojenia k Autopilot.</span><span class="sxs-lookup"><span data-stu-id="0824a-125">Select **Connect** to initialize the connection to Autopilot.</span></span>

1. <span data-ttu-id="0824a-126">Vyberte položku **Pridať samého seba ako používateľa exportu** a uveďte svoje poverenia pre Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="0824a-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="0824a-127">Stlačte možnosť **Uložiť** a dokončite pripojenie.</span><span class="sxs-lookup"><span data-stu-id="0824a-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="0824a-128">Nakonfigurujte export</span><span class="sxs-lookup"><span data-stu-id="0824a-128">Configure an export</span></span>

<span data-ttu-id="0824a-129">Tento export môžete nakonfigurovať, ak máte prístup k pripojeniu tohto typu.</span><span class="sxs-lookup"><span data-stu-id="0824a-129">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="0824a-130">Viac informácií nájdete na stránke [Na konfiguráciu exportu sú potrebné povolenia](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="0824a-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="0824a-131">Prejdite na **Údaje** > **Exporty**.</span><span class="sxs-lookup"><span data-stu-id="0824a-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="0824a-132">Na vytvorenie nového exportu stlačte možnosť **Pridať cieľ**.</span><span class="sxs-lookup"><span data-stu-id="0824a-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="0824a-133">V poli **Pripojenie na export** vyberte pripojenie v časti Autopilot.</span><span class="sxs-lookup"><span data-stu-id="0824a-133">In the **Connection for export** field, choose a connection from the Autopilot section.</span></span> <span data-ttu-id="0824a-134">Ak nevidíte názov tejto sekcie, nemáte k dispozícii žiadne spojenia tohto typu.</span><span class="sxs-lookup"><span data-stu-id="0824a-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

3. <span data-ttu-id="0824a-135">V sekcii **Párovanie údajov** v poli **E-mail** do svojho zjednoteného profilu zákazníka vyberte pole, ktoré predstavuje e-mailovú adresu zákazníka.</span><span class="sxs-lookup"><span data-stu-id="0824a-135">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="0824a-136">Rovnaký postup zopakujte pri ďalších voliteľných poliach, ako je **Krstné meno** a **Priezvisko**.</span><span class="sxs-lookup"><span data-stu-id="0824a-136">Repeat the same steps for other optional fields such as **First name**, **Last name**.</span></span>

1. <span data-ttu-id="0824a-137">Vyberte segmenty, ktoré chcete exportovať.</span><span class="sxs-lookup"><span data-stu-id="0824a-137">Select the segments you want to export.</span></span> <span data-ttu-id="0824a-138">Dôrazne **odporúčame neexportovať celkovo viac ako 100 000 profilov zákazníkov** do Autopilot.</span><span class="sxs-lookup"><span data-stu-id="0824a-138">We strongly **recommend to not export more than 100'000 customer profiles in total** to Autopilot.</span></span> 

1. <span data-ttu-id="0824a-139">Vyberte položku **Uložiť**.</span><span class="sxs-lookup"><span data-stu-id="0824a-139">Select **Save**.</span></span>

<span data-ttu-id="0824a-140">Uloženie exportu nespustí export okamžite.</span><span class="sxs-lookup"><span data-stu-id="0824a-140">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="0824a-141">Export prebieha s každým [plánovaným obnovením](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="0824a-141">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="0824a-142">Môžete tiež [exportovať údaje na požiadanie](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="0824a-142">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="0824a-143">Ochrana osobných údajov a dodržiavanie súladu s nariadeniami</span><span class="sxs-lookup"><span data-stu-id="0824a-143">Data privacy and compliance</span></span>

<span data-ttu-id="0824a-144">Keď povolíte prenos údajov spoločnosti Autopilot v službe Dynamics 365 Customer Insights, povoľujete tým prenos údajov mimo hranice súladu so službou Dynamics 365 Customer Insights vrátane potenciálne citlivých údajov, ako sú napríklad osobné údaje.</span><span class="sxs-lookup"><span data-stu-id="0824a-144">When you enable Dynamics 365 Customer Insights to transmit data to Autopilot, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="0824a-145">Spoločnosť Microsoft prenesie tieto údaje na váš pokyn, ale vy ste zodpovední za zabezpečenie toho, aby spoločnosť Autopilot plnila všetky prípadné povinnosti týkajúce sa ochrany vašich osobných údajov alebo zabezpečenia.</span><span class="sxs-lookup"><span data-stu-id="0824a-145">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Autopilot meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="0824a-146">Ďalšie informácie nájdete vo [vyhlásení o ochrane súkromia spoločnosti Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="0824a-146">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="0824a-147">Váš správca služby Dynamics 365 Customer Insights môže túto funkciu kedykoľvek prestať používať odstránením tohto cieľového umiestnenia exportu.</span><span class="sxs-lookup"><span data-stu-id="0824a-147">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
