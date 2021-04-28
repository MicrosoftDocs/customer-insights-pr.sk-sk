---
title: Export údajov služby Customer Insights do SendGrid
description: Zistite ako nakonfigurovať pripojenie a realizovať exportovanie do SendGrid.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: a4c64cf77c682e07f3d0759c43355336b5806fc8
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 03/31/2021
ms.locfileid: "5759784"
---
# <a name="export-segments-to-sendgrid-preview"></a><span data-ttu-id="0a13a-103">Export segmentov do SendGrid (ukážka)</span><span class="sxs-lookup"><span data-stu-id="0a13a-103">Export segments to SendGrid (preview)</span></span>

<span data-ttu-id="0a13a-104">Exportujte segmenty zjednotených profilov zákazníkov do zoznamov kontaktov SendGrid a použite ich pre kampane a e-mailový marketing v SendGrid.</span><span class="sxs-lookup"><span data-stu-id="0a13a-104">Export segments of unified customer profiles to SendGrid contact lists and use them for campaigns and email marketing in SendGrid.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="0a13a-105">Predpoklad na pripojenie</span><span class="sxs-lookup"><span data-stu-id="0a13a-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="0a13a-106">Máte [účet SendGrid](https://sendgrid.com/) a zodpovedajúce poverenia správcu.</span><span class="sxs-lookup"><span data-stu-id="0a13a-106">You have a [SendGrid account](https://sendgrid.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="0a13a-107">V službe SendGrid existujú zoznamy kontaktov a zodpovedajúce ID.</span><span class="sxs-lookup"><span data-stu-id="0a13a-107">There are existing contact lists in SendGrid and the corresponding IDs.</span></span> <span data-ttu-id="0a13a-108">Ďalšie informácie nájdete v časti [SendGrid – spravovanie kontaktov](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts).</span><span class="sxs-lookup"><span data-stu-id="0a13a-108">For more information, see [SendGrid - Manage contacts](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts).</span></span>
-   <span data-ttu-id="0a13a-109">Máte [konfigurované segmenty](segments.md) v prehľadoch cieľových skupín.</span><span class="sxs-lookup"><span data-stu-id="0a13a-109">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="0a13a-110">Zjednotené profily zákazníkov v exportovaných segmentoch obsahujú pole predstavujúce e-mailovú adresu.</span><span class="sxs-lookup"><span data-stu-id="0a13a-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="0a13a-111">Známe obmedzenia</span><span class="sxs-lookup"><span data-stu-id="0a13a-111">Known limitations</span></span>

- <span data-ttu-id="0a13a-112">Až 100 000 profilov celkovo do služby SendGrid.</span><span class="sxs-lookup"><span data-stu-id="0a13a-112">Up to 100'000 profiles in total to SendGrid.</span></span>
- <span data-ttu-id="0a13a-113">Export do SendGrid je obmedzený na segmenty.</span><span class="sxs-lookup"><span data-stu-id="0a13a-113">Exporting to SendGrid is limited to segments.</span></span>
- <span data-ttu-id="0a13a-114">Export až 100 000 profilov do služby SendGrid môže trvať až niekoľko hodín.</span><span class="sxs-lookup"><span data-stu-id="0a13a-114">Exporting up to 100'000 profiles to SendGrid can take up to a few hours to complete.</span></span> 
- <span data-ttu-id="0a13a-115">Počet profilov, ktoré môžete exportovať do SendGrid, závisí a je obmedzený vašou zmluvou so spoločnosťou SendGrid.</span><span class="sxs-lookup"><span data-stu-id="0a13a-115">The number of profiles that you can export to SendGrid is dependent and limited on your contract with SendGrid.</span></span>

## <a name="set-up-connection-to-sendgrid"></a><span data-ttu-id="0a13a-116">Nastavenie pripojenia k SendGrid</span><span class="sxs-lookup"><span data-stu-id="0a13a-116">Set up connection to SendGrid</span></span>

1. <span data-ttu-id="0a13a-117">Prejdite do časti **Správca** > **Pripojenia**.</span><span class="sxs-lookup"><span data-stu-id="0a13a-117">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="0a13a-118">Stlačte možnosť **Pridať pripojenie** a stlačením možnosti **SendGrid** nakonfigurujte pripojenie.</span><span class="sxs-lookup"><span data-stu-id="0a13a-118">Select **Add connection** and choose **SendGrid** to configure the connection.</span></span>

1. <span data-ttu-id="0a13a-119">Do poľa **Zobrazovaný názov** zadajte rozpoznateľný názov pripojenia.</span><span class="sxs-lookup"><span data-stu-id="0a13a-119">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="0a13a-120">Zobrazovaný názov a typ spojenia, ktoré popisuje toto spojenie.</span><span class="sxs-lookup"><span data-stu-id="0a13a-120">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="0a13a-121">Odporúčame zvoliť názov, ktorý vysvetľuje účel a cieľ tohto spojenia.</span><span class="sxs-lookup"><span data-stu-id="0a13a-121">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="0a13a-122">Vyberte používateľov, ktorí môžu používať toto pripojenie.</span><span class="sxs-lookup"><span data-stu-id="0a13a-122">Choose who can use this connection.</span></span> <span data-ttu-id="0a13a-123">Ak neurobíte nič, predvolená hodnota bude Správcovia.</span><span class="sxs-lookup"><span data-stu-id="0a13a-123">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="0a13a-124">Viac informácií nájdete v časti [Umožnite prispievateľom použiť pripojenie na export](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="0a13a-124">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="0a13a-125">Zadajte svoj **Kľúč API SendGrid** [Kľúč API SendGrid](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).</span><span class="sxs-lookup"><span data-stu-id="0a13a-125">Enter your **SendGrid API key** [SendGrid API key](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).</span></span>

1. <span data-ttu-id="0a13a-126">Vyberte **Súhlasím** na potvrdenie **Ochrany osobných údajov a dodržiavanie súladu s nariadeniami**.</span><span class="sxs-lookup"><span data-stu-id="0a13a-126">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="0a13a-127">Vyberte položku **Pripojiť** na inicializáciu pripojenia k SendGrid.</span><span class="sxs-lookup"><span data-stu-id="0a13a-127">Select **Connect** to initialize the connection to SendGrid.</span></span>

1. <span data-ttu-id="0a13a-128">Vyberte položku **Pridať samého seba ako používateľa exportu** a uveďte svoje poverenia pre Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="0a13a-128">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="0a13a-129">Stlačte možnosť **Uložiť** a dokončite pripojenie.</span><span class="sxs-lookup"><span data-stu-id="0a13a-129">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="0a13a-130">Nakonfigurujte export</span><span class="sxs-lookup"><span data-stu-id="0a13a-130">Configure an export</span></span>

<span data-ttu-id="0a13a-131">Tento export môžete nakonfigurovať, ak máte prístup k pripojeniu tohto typu.</span><span class="sxs-lookup"><span data-stu-id="0a13a-131">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="0a13a-132">Viac informácií nájdete na stránke [Na konfiguráciu exportu sú potrebné povolenia](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="0a13a-132">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="0a13a-133">Prejdite na **Údaje** > **Exporty**.</span><span class="sxs-lookup"><span data-stu-id="0a13a-133">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="0a13a-134">Na vytvorenie nového exportu stlačte možnosť **Pridať cieľ**.</span><span class="sxs-lookup"><span data-stu-id="0a13a-134">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="0a13a-135">V poli **Pripojenie na export** vyberte pripojenie v časti SendGrid.</span><span class="sxs-lookup"><span data-stu-id="0a13a-135">In the **Connection for export** field, choose a connection from the SendGrid section.</span></span> <span data-ttu-id="0a13a-136">Ak nevidíte názov tejto sekcie, nemáte k dispozícii žiadne spojenia tohto typu.</span><span class="sxs-lookup"><span data-stu-id="0a13a-136">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="0a13a-137">Zadajte svoje **[ID zoznamu SendGrid](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)**.</span><span class="sxs-lookup"><span data-stu-id="0a13a-137">Enter your **[SendGrid list ID](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)**.</span></span>

1. <span data-ttu-id="0a13a-138">V sekcii **Párovanie údajov** v poli **E-mail** do svojho zjednoteného profilu zákazníka vyberte pole, ktoré predstavuje e-mailovú adresu zákazníka.</span><span class="sxs-lookup"><span data-stu-id="0a13a-138">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="0a13a-139">Rovnaký postup zopakujte pri ďalších voliteľných poliach, ako je **Krstné meno**, **Priezvisko**, **Krajina/región**, **Štát**, **Mesto** a **PSČ**.</span><span class="sxs-lookup"><span data-stu-id="0a13a-139">Repeat the same steps for other optional fields such as **First name**, **Last name**, **Country/Region**, **State**, **City**, and **Post code**.</span></span>

1. <span data-ttu-id="0a13a-140">Vyberte segmenty, ktoré chcete exportovať.</span><span class="sxs-lookup"><span data-stu-id="0a13a-140">Select the segments you want to export.</span></span> <span data-ttu-id="0a13a-141">Dôrazne **odporúčame neexportovať celkovo viac ako 100 000 profilov zákazníkov** do SendGrid.</span><span class="sxs-lookup"><span data-stu-id="0a13a-141">We strongly **recommend to not export more than 100'000 customer profiles in total** to SendGrid.</span></span> 

1. <span data-ttu-id="0a13a-142">Vyberte položku **Uložiť**.</span><span class="sxs-lookup"><span data-stu-id="0a13a-142">Select **Save**.</span></span>

<span data-ttu-id="0a13a-143">Uloženie exportu nespustí export okamžite.</span><span class="sxs-lookup"><span data-stu-id="0a13a-143">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="0a13a-144">Export prebieha s každým [plánovaným obnovením](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="0a13a-144">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="0a13a-145">Môžete tiež [exportovať údaje na požiadanie](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="0a13a-145">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="0a13a-146">Ochrana osobných údajov a dodržiavanie súladu s nariadeniami</span><span class="sxs-lookup"><span data-stu-id="0a13a-146">Data privacy and compliance</span></span>

<span data-ttu-id="0a13a-147">Keď povolíte službe Dynamics 365 Customer Insights prenos údajov do SendGrid, povoľujete tým prenos údajov mimo hranice súladu so službou Dynamics 365 Customer Insights vrátane potenciálne citlivých údajov, ako sú napríklad osobné údaje.</span><span class="sxs-lookup"><span data-stu-id="0a13a-147">When you enable Dynamics 365 Customer Insights to transmit data to SendGrid, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="0a13a-148">Spoločnosť Microsoft prenesie tieto údaje na váš pokyn, ale vy ste zodpovední za zabezpečenie toho, aby SendGrid plnila všetky prípadné povinnosti týkajúce sa ochrany vašich osobných údajov alebo zabezpečenia.</span><span class="sxs-lookup"><span data-stu-id="0a13a-148">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that SendGrid meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="0a13a-149">Ďalšie informácie nájdete vo [vyhlásení o ochrane súkromia spoločnosti Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="0a13a-149">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="0a13a-150">Váš správca služby Dynamics 365 Customer Insights môže túto funkciu kedykoľvek prestať používať odstránením tohto cieľového umiestnenia exportu.</span><span class="sxs-lookup"><span data-stu-id="0a13a-150">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]