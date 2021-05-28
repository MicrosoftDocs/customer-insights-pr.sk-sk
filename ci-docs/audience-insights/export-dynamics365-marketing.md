---
title: Export údajov služby Customer Insights do Dynamics 365 Marketing
description: Zistite ako nakonfigurovať pripojenie a realizovať exportovanie do Dynamics 365 Marketing.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 195bee789dc043057b47c12c8d93e6d53edb59cd
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976819"
---
# <a name="use-segments-in-dynamics-365-marketing-preview"></a><span data-ttu-id="70e8d-103">Použitie segmentov v Dynamics 365 Marketing (ukážka)</span><span class="sxs-lookup"><span data-stu-id="70e8d-103">Use segments in Dynamics 365 Marketing (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="70e8d-104">Dynamics 365 Marketing umožňuje pomocou [segmentov](segments.md) generovať kampane a kontaktovať konkrétne skupiny zákazníkov.</span><span class="sxs-lookup"><span data-stu-id="70e8d-104">Use [segments](segments.md) to generate campaigns and contact specific groups of customers with Dynamics 365 Marketing.</span></span> <span data-ttu-id="70e8d-105">Viac informácií nájdete v článku [Použitie segmentov z Dynamics 365 Customer Insights s Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments)</span><span class="sxs-lookup"><span data-stu-id="70e8d-105">For more information, see [Use segments from Dynamics 365 Customer Insights with Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments)</span></span>

## <a name="prerequisite-for-a-connection"></a><span data-ttu-id="70e8d-106">Predpoklad na pripojenie</span><span class="sxs-lookup"><span data-stu-id="70e8d-106">Prerequisite for a connection</span></span>

- <span data-ttu-id="70e8d-107">Pred exportom segmentu z Customer Insights do Sales Marketing byť záznamy kontaktov v Dynamics 365 Marketing.</span><span class="sxs-lookup"><span data-stu-id="70e8d-107">Contact records must be present in Dynamics 365 Marketing before you can export a segment from Customer Insights to Marketing.</span></span> <span data-ttu-id="70e8d-108">Prečítajte si viac o tom, ako prijímať kontakty v [Dynamics 365 Marketing pomocou Common Data Services](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="70e8d-108">Read more on how to ingest contacts in [Dynamics 365 Marketing using Common Data Services](connect-power-query.md).</span></span>

  > [!NOTE]
  > <span data-ttu-id="70e8d-109">Export segmentov z prehľadov cieľových skupín do Marketing nevytvorí nové záznamy kontaktov v inštanciách Marketing.</span><span class="sxs-lookup"><span data-stu-id="70e8d-109">Exporting segments from audience insights to Marketing will not create new contact records in the Marketing instances.</span></span> <span data-ttu-id="70e8d-110">Záznamy kontaktov z Marketing musia byť obsiahnuté v prehľadoch cieľových skupín a použité ako zdroj údajov.</span><span class="sxs-lookup"><span data-stu-id="70e8d-110">The contact records from Marketing must be ingested in audience insights and used as a data source.</span></span> <span data-ttu-id="70e8d-111">Pred exportom segmentov je ich tiež potrebné ich zahrnúť do zjednotenej entity zákazníka na mapovanie ID zákazníkov na ID kontaktov.</span><span class="sxs-lookup"><span data-stu-id="70e8d-111">They also need to be included in the unified Customer entity to map customer IDs to contact IDs before segments can be exported.</span></span>

## <a name="set-up-connection-to-marketing"></a><span data-ttu-id="70e8d-112">Nastavenie pripojenia k Marketing</span><span class="sxs-lookup"><span data-stu-id="70e8d-112">Set up connection to Marketing</span></span>

1. <span data-ttu-id="70e8d-113">Prejdite do časti **Správca** > **Pripojenia**.</span><span class="sxs-lookup"><span data-stu-id="70e8d-113">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="70e8d-114">Stlačte možnosť **Pridať pripojenie** a stlačením možnosti **Dynamics 365 Marketing** nakonfigurujte pripojenie.</span><span class="sxs-lookup"><span data-stu-id="70e8d-114">Select **Add connection** and choose **Dynamics 365 Marketing** to configure the connection.</span></span>

1. <span data-ttu-id="70e8d-115">Do poľa **Zobrazovaný názov** zadajte rozpoznateľný názov pripojenia.</span><span class="sxs-lookup"><span data-stu-id="70e8d-115">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="70e8d-116">Zobrazovaný názov a typ spojenia, ktoré popisuje toto spojenie.</span><span class="sxs-lookup"><span data-stu-id="70e8d-116">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="70e8d-117">Odporúčame zvoliť názov, ktorý vysvetľuje účel a cieľ tohto spojenia.</span><span class="sxs-lookup"><span data-stu-id="70e8d-117">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="70e8d-118">Vyberte používateľov, ktorí môžu používať toto pripojenie.</span><span class="sxs-lookup"><span data-stu-id="70e8d-118">Choose who can use this connection.</span></span> <span data-ttu-id="70e8d-119">Ak neurobíte nič, predvolená hodnota bude Správcovia.</span><span class="sxs-lookup"><span data-stu-id="70e8d-119">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="70e8d-120">Viac informácií nájdete v časti [Umožnite prispievateľom použiť pripojenie na export](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="70e8d-120">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="70e8d-121">Zadajte marketingovú adresu URL svojej organizácie do poľa **Adresa servera**.</span><span class="sxs-lookup"><span data-stu-id="70e8d-121">Enter your organization's Marketing URL in the **Server address** field.</span></span>

1. <span data-ttu-id="70e8d-122">V sekcii **Konto správcu servera** vyberte **Prihlásiť sa** a vyberte Dynamics 365 Marketing.</span><span class="sxs-lookup"><span data-stu-id="70e8d-122">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Marketing account.</span></span>

1. <span data-ttu-id="70e8d-123">Namapujte pole ID zákazníka k ID kontaktu služby Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="70e8d-123">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="70e8d-124">Stlačte možnosť **Uložiť** a dokončite pripojenie.</span><span class="sxs-lookup"><span data-stu-id="70e8d-124">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="70e8d-125">Nakonfigurujte export</span><span class="sxs-lookup"><span data-stu-id="70e8d-125">Configure an export</span></span>

<span data-ttu-id="70e8d-126">Tento export môžete nakonfigurovať, ak máte prístup k pripojeniu tohto typu.</span><span class="sxs-lookup"><span data-stu-id="70e8d-126">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="70e8d-127">Viac informácií nájdete na stránke [Na konfiguráciu exportu sú potrebné povolenia](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="70e8d-127">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="70e8d-128">Prejdite na **Údaje** > **Exporty**.</span><span class="sxs-lookup"><span data-stu-id="70e8d-128">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="70e8d-129">Na vytvorenie nového exportu stlačte možnosť **Pridať cieľ**.</span><span class="sxs-lookup"><span data-stu-id="70e8d-129">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="70e8d-130">V poli **Pripojenie na export** vyberte pripojenie v časti Dynamics 365 Marketing.</span><span class="sxs-lookup"><span data-stu-id="70e8d-130">In the **Connection for export** field, choose a connection from the Dynamics 365 Marketing section.</span></span> <span data-ttu-id="70e8d-131">Ak nevidíte názov tejto sekcie, nemáte k dispozícii žiadne spojenia tohto typu.</span><span class="sxs-lookup"><span data-stu-id="70e8d-131">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="70e8d-132">Vyberte jeden alebo viac segmentov.</span><span class="sxs-lookup"><span data-stu-id="70e8d-132">Choose one or more segments.</span></span>

1. <span data-ttu-id="70e8d-133">Vyberte položku **Uložiť**.</span><span class="sxs-lookup"><span data-stu-id="70e8d-133">Select **Save**.</span></span>

<span data-ttu-id="70e8d-134">Uloženie exportu nespustí export okamžite.</span><span class="sxs-lookup"><span data-stu-id="70e8d-134">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="70e8d-135">Export prebieha s každým [plánovaným obnovením](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="70e8d-135">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="70e8d-136">Môžete tiež [exportovať údaje na požiadanie](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="70e8d-136">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
