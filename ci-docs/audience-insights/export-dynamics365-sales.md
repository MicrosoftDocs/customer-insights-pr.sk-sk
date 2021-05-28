---
title: Export údajov služby Customer Insights do Dynamics 365 Sales
description: Zistite ako nakonfigurovať pripojenie a realizovať exportovanie do Dynamics 365 Sales.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 328bb2f26ebcea234fb645e5225930ab12f82a8b
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976245"
---
# <a name="use-segments-in-dynamics-365-sales-preview"></a><span data-ttu-id="d81ee-103">Použitie segmentov v Dynamics 365 Sales (ukážka)</span><span class="sxs-lookup"><span data-stu-id="d81ee-103">Use segments in Dynamics 365 Sales (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="d81ee-104">Dynamics 365 Sales umožňuje pomocou zákazníckych údajov vytvárať marketingové zoznamy, sledovať pracovné postupy a odosielať propagačné akcie.</span><span class="sxs-lookup"><span data-stu-id="d81ee-104">Use your customer data to create marketing lists, follow up workflows, and send out promotions with Dynamics 365 Sales.</span></span>

## <a name="prerequisite-for-connection"></a><span data-ttu-id="d81ee-105">Predpoklad na pripojenie</span><span class="sxs-lookup"><span data-stu-id="d81ee-105">Prerequisite for connection</span></span>

1. <span data-ttu-id="d81ee-106">Pred exportom segmentu z Customer Insights do Sales musia byť záznamy kontaktov v Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="d81ee-106">Contact records must be present in Dynamics 365 Sales before you can export a segment from Customer Insights to Sales.</span></span> <span data-ttu-id="d81ee-107">Prečítajte si viac o tom, ako prijímať kontakty v [Dynamics 365 Sales pomocou Common Data Services](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="d81ee-107">Read more on how to ingest contacts in [Dynamics 365 Sales using Common Data Services](connect-power-query.md).</span></span>

   > [!NOTE]
   > <span data-ttu-id="d81ee-108">Export segmentov z prehľadov cieľových skupín do Sales nevytvorí nové záznamy kontaktov v inštanciách Sales.</span><span class="sxs-lookup"><span data-stu-id="d81ee-108">Exporting segments from audience insights to Sales will not create new contact records in the Sales instances.</span></span> <span data-ttu-id="d81ee-109">Záznamy kontaktov zo Sales musia byť obsiahnuté v prehľadoch cieľových skupín a použité ako zdroj údajov.</span><span class="sxs-lookup"><span data-stu-id="d81ee-109">The contact records from Sales must be ingested in audience insights and used as a data source.</span></span> <span data-ttu-id="d81ee-110">Pred exportom segmentov je ich tiež potrebné ich zahrnúť do zjednotenej entity zákazníka na mapovanie ID zákazníkov na ID kontaktov.</span><span class="sxs-lookup"><span data-stu-id="d81ee-110">They also need to be included in the unified Customer entity to map customer IDs to contact IDs before segments can be exported.</span></span>

## <a name="set-up-the-connection-to-sales"></a><span data-ttu-id="d81ee-111">Nastavenie pripojenia k Sales</span><span class="sxs-lookup"><span data-stu-id="d81ee-111">Set up the connection to Sales</span></span>

1. <span data-ttu-id="d81ee-112">Prejdite do časti **Správca** > **Pripojenia**.</span><span class="sxs-lookup"><span data-stu-id="d81ee-112">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="d81ee-113">Stlačte možnosť **Pridať pripojenie** a stlačením možnosti **Dynamics 365 Sales** nakonfigurujte pripojenie.</span><span class="sxs-lookup"><span data-stu-id="d81ee-113">Select **Add connection** and choose **Dynamics 365 Sales** to configure the connection.</span></span>

1. <span data-ttu-id="d81ee-114">Do poľa **Zobrazovaný názov** zadajte rozpoznateľný názov pripojenia.</span><span class="sxs-lookup"><span data-stu-id="d81ee-114">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="d81ee-115">Zobrazovaný názov a typ spojenia, ktoré popisuje toto spojenie.</span><span class="sxs-lookup"><span data-stu-id="d81ee-115">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="d81ee-116">Odporúčame zvoliť názov, ktorý vysvetľuje účel a cieľ tohto spojenia.</span><span class="sxs-lookup"><span data-stu-id="d81ee-116">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="d81ee-117">Vyberte používateľov, ktorí môžu používať toto pripojenie.</span><span class="sxs-lookup"><span data-stu-id="d81ee-117">Choose who can use this connection.</span></span> <span data-ttu-id="d81ee-118">Ak neurobíte nič, predvolená hodnota bude Správcovia.</span><span class="sxs-lookup"><span data-stu-id="d81ee-118">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="d81ee-119">Viac informácií nájdete v časti [Umožnite prispievateľom použiť pripojenie na export](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="d81ee-119">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="d81ee-120">Zadajte marketingovú adresu Predaj URL svojej organizácie do poľa **Adresa servera**.</span><span class="sxs-lookup"><span data-stu-id="d81ee-120">Enter your organization's Sales URL in the **Server address** field.</span></span>

1. <span data-ttu-id="d81ee-121">V sekcii **Konto správcu servera** vyberte **Prihlásiť sa** a vyberte konto Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="d81ee-121">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Sales account.</span></span>

1. <span data-ttu-id="d81ee-122">Namapujte pole ID zákazníka k ID kontaktu služby Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="d81ee-122">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="d81ee-123">Stlačte možnosť **Uložiť** a dokončite pripojenie.</span><span class="sxs-lookup"><span data-stu-id="d81ee-123">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="d81ee-124">Nakonfigurujte export</span><span class="sxs-lookup"><span data-stu-id="d81ee-124">Configure an export</span></span>

<span data-ttu-id="d81ee-125">Tento export môžete nakonfigurovať, ak máte prístup k pripojeniu tohto typu.</span><span class="sxs-lookup"><span data-stu-id="d81ee-125">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="d81ee-126">Viac informácií nájdete na stránke [Na konfiguráciu exportu sú potrebné povolenia](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="d81ee-126">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="d81ee-127">Prejdite na **Údaje** > **Exporty**.</span><span class="sxs-lookup"><span data-stu-id="d81ee-127">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="d81ee-128">Na vytvorenie nového exportu stlačte možnosť **Pridať cieľ**.</span><span class="sxs-lookup"><span data-stu-id="d81ee-128">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="d81ee-129">V poli **Pripojenie na export** vyberte pripojenie v časti Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="d81ee-129">In the **Connection for export** field, choose a connection from the Dynamics 365 Sales section.</span></span> <span data-ttu-id="d81ee-130">Ak nevidíte názov tejto sekcie, nemáte k dispozícii žiadne spojenia tohto typu.</span><span class="sxs-lookup"><span data-stu-id="d81ee-130">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="d81ee-131">Vyberte jeden alebo viac segmentov.</span><span class="sxs-lookup"><span data-stu-id="d81ee-131">Choose one or more segments.</span></span>

1. <span data-ttu-id="d81ee-132">Stlačte možnosť **Uložiť**</span><span class="sxs-lookup"><span data-stu-id="d81ee-132">Select **Save**</span></span>

<span data-ttu-id="d81ee-133">Uloženie exportu nespustí export okamžite.</span><span class="sxs-lookup"><span data-stu-id="d81ee-133">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="d81ee-134">Export prebieha s každým [plánovaným obnovením](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="d81ee-134">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="d81ee-135">Môžete tiež [exportovať údaje na požiadanie](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="d81ee-135">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
