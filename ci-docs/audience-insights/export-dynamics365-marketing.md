---
title: Export údajov služby Customer Insights do Dynamics 365 Marketing
description: Zistite ako nakonfigurovať pripojenie a realizovať exportovanie do Dynamics 365 Marketing.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: a13f6f81f5e2570d3302d88c02755f1d86321a01
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 03/31/2021
ms.locfileid: "5759656"
---
# <a name="use-segments-in-dynamics-365-marketing-preview"></a><span data-ttu-id="e6eac-103">Použitie segmentov v Dynamics 365 Marketing (ukážka)</span><span class="sxs-lookup"><span data-stu-id="e6eac-103">Use segments in Dynamics 365 Marketing (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="e6eac-104">Dynamics 365 Marketing umožňuje pomocou [segmentov](segments.md) generovať kampane a kontaktovať konkrétne skupiny zákazníkov.</span><span class="sxs-lookup"><span data-stu-id="e6eac-104">Use [segments](segments.md) to generate campaigns and contact specific groups of customers with Dynamics 365 Marketing.</span></span> <span data-ttu-id="e6eac-105">Viac informácií nájdete v článku [Použitie segmentov z Dynamics 365 Customer Insights s Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments)</span><span class="sxs-lookup"><span data-stu-id="e6eac-105">For more information, see [Use segments from Dynamics 365 Customer Insights with Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments)</span></span>

## <a name="prerequisite-for-a-connection"></a><span data-ttu-id="e6eac-106">Predpoklad na pripojenie</span><span class="sxs-lookup"><span data-stu-id="e6eac-106">Prerequisite for a connection</span></span>

- <span data-ttu-id="e6eac-107">Pred exportom segmentu z Customer Insights do Sales Marketing byť záznamy kontaktov v Dynamics 365 Marketing.</span><span class="sxs-lookup"><span data-stu-id="e6eac-107">Contact records must be present in Dynamics 365 Marketing before you can export a segment from Customer Insights to Marketing.</span></span> <span data-ttu-id="e6eac-108">Prečítajte si viac o tom, ako prijímať kontakty v [Dynamics 365 Marketing pomocou Common Data Services](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="e6eac-108">Read more on how to ingest contacts in [Dynamics 365 Marketing using Common Data Services](connect-power-query.md).</span></span>

  > [!NOTE]
  > <span data-ttu-id="e6eac-109">Export segmentov z prehľadov cieľových skupín do Marketing nevytvorí nové záznamy kontaktov v inštanciách Marketing.</span><span class="sxs-lookup"><span data-stu-id="e6eac-109">Exporting segments from audience insights to Marketing will not create new contact records in the Marketing instances.</span></span> <span data-ttu-id="e6eac-110">Záznamy kontaktov z Marketing musia byť obsiahnuté v prehľadoch cieľových skupín a použité ako zdroj údajov.</span><span class="sxs-lookup"><span data-stu-id="e6eac-110">The contact records from Marketing must be ingested in audience insights and used as a data source.</span></span> <span data-ttu-id="e6eac-111">Pred exportom segmentov je ich tiež potrebné ich zahrnúť do zjednotenej entity zákazníka na mapovanie ID zákazníkov na ID kontaktov.</span><span class="sxs-lookup"><span data-stu-id="e6eac-111">They also need to be included in the unified Customer entity to map customer IDs to contact IDs before segments can be exported.</span></span>

## <a name="set-up-connection-to-marketing"></a><span data-ttu-id="e6eac-112">Nastavenie pripojenia k Marketing</span><span class="sxs-lookup"><span data-stu-id="e6eac-112">Set up connection to Marketing</span></span>

1. <span data-ttu-id="e6eac-113">Prejdite do časti **Správca** > **Pripojenia**.</span><span class="sxs-lookup"><span data-stu-id="e6eac-113">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="e6eac-114">Stlačte možnosť **Pridať pripojenie** a stlačením možnosti **Dynamics 365 Marketing** nakonfigurujte pripojenie.</span><span class="sxs-lookup"><span data-stu-id="e6eac-114">Select **Add connection** and choose **Dynamics 365 Marketing** to configure the connection.</span></span>

1. <span data-ttu-id="e6eac-115">Do poľa **Zobrazovaný názov** zadajte rozpoznateľný názov pripojenia.</span><span class="sxs-lookup"><span data-stu-id="e6eac-115">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="e6eac-116">Zobrazovaný názov a typ spojenia, ktoré popisuje toto spojenie.</span><span class="sxs-lookup"><span data-stu-id="e6eac-116">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="e6eac-117">Odporúčame zvoliť názov, ktorý vysvetľuje účel a cieľ tohto spojenia.</span><span class="sxs-lookup"><span data-stu-id="e6eac-117">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="e6eac-118">Vyberte používateľov, ktorí môžu používať toto pripojenie.</span><span class="sxs-lookup"><span data-stu-id="e6eac-118">Choose who can use this connection.</span></span> <span data-ttu-id="e6eac-119">Ak neurobíte nič, predvolená hodnota bude Správcovia.</span><span class="sxs-lookup"><span data-stu-id="e6eac-119">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="e6eac-120">Viac informácií nájdete v časti [Umožnite prispievateľom použiť pripojenie na export](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="e6eac-120">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="e6eac-121">Zadajte marketingovú adresu URL svojej organizácie do poľa **Adresa servera**.</span><span class="sxs-lookup"><span data-stu-id="e6eac-121">Enter your organization's Marketing URL in the **Server address** field.</span></span>

1. <span data-ttu-id="e6eac-122">V sekcii **Konto správcu servera** vyberte **Prihlásiť sa** a vyberte Dynamics 365 Marketing.</span><span class="sxs-lookup"><span data-stu-id="e6eac-122">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Marketing account.</span></span>

1. <span data-ttu-id="e6eac-123">Namapujte pole ID zákazníka k ID kontaktu služby Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="e6eac-123">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="e6eac-124">Stlačte možnosť **Uložiť** a dokončite pripojenie.</span><span class="sxs-lookup"><span data-stu-id="e6eac-124">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="e6eac-125">Nakonfigurujte export</span><span class="sxs-lookup"><span data-stu-id="e6eac-125">Configure an export</span></span>

<span data-ttu-id="e6eac-126">Tento export môžete nakonfigurovať, ak máte prístup k pripojeniu tohto typu.</span><span class="sxs-lookup"><span data-stu-id="e6eac-126">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="e6eac-127">Viac informácií nájdete na stránke [Na konfiguráciu exportu sú potrebné povolenia](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="e6eac-127">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="e6eac-128">Prejdite na **Údaje** > **Exporty**.</span><span class="sxs-lookup"><span data-stu-id="e6eac-128">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="e6eac-129">Na vytvorenie nového exportu stlačte možnosť **Pridať cieľ**.</span><span class="sxs-lookup"><span data-stu-id="e6eac-129">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="e6eac-130">V poli **Pripojenie na export** vyberte pripojenie v časti Dynamics 365 Marketing.</span><span class="sxs-lookup"><span data-stu-id="e6eac-130">In the **Connection for export** field, choose a connection from the Dynamics 365 Marketing section.</span></span> <span data-ttu-id="e6eac-131">Ak nevidíte názov tejto sekcie, nemáte k dispozícii žiadne spojenia tohto typu.</span><span class="sxs-lookup"><span data-stu-id="e6eac-131">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="e6eac-132">Vyberte jeden alebo viac segmentov.</span><span class="sxs-lookup"><span data-stu-id="e6eac-132">Choose one or more segments.</span></span>

1. <span data-ttu-id="e6eac-133">Vyberte položku **Uložiť**.</span><span class="sxs-lookup"><span data-stu-id="e6eac-133">Select **Save**.</span></span>

<span data-ttu-id="e6eac-134">Uloženie exportu nespustí export okamžite.</span><span class="sxs-lookup"><span data-stu-id="e6eac-134">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="e6eac-135">Export prebieha s každým [plánovaným obnovením](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="e6eac-135">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="e6eac-136">Môžete tiež [exportovať údaje na požiadanie](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="e6eac-136">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
