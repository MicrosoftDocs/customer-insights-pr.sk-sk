---
title: Export údajov služby Customer Insights do Dynamics 365 Marketing
description: Naučte sa, ako nakonfigurovať pripojenie k Dynamics 365 Marketing.
ms.date: 02/01/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 892aff643872f11307a2c43e5670edab657d7848
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597622"
---
# <a name="connector-for-dynamics-365-marketing-preview"></a><span data-ttu-id="aae0e-103">Konektor pre Dynamics 365 Marketing (ukážka)</span><span class="sxs-lookup"><span data-stu-id="aae0e-103">Connector for Dynamics 365 Marketing (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="aae0e-104">Dynamics 365 Marketing umožňuje pomocou [segmentov](segments.md) generovať kampane a kontaktovať konkrétne skupiny zákazníkov.</span><span class="sxs-lookup"><span data-stu-id="aae0e-104">Use [segments](segments.md) to generate campaigns and contact specific groups of customers with Dynamics 365 Marketing.</span></span> <span data-ttu-id="aae0e-105">Viac informácií nájdete v článku [Použitie segmentov z Dynamics 365 Customer Insights s Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments)</span><span class="sxs-lookup"><span data-stu-id="aae0e-105">For more information, see [Use segments from Dynamics 365 Customer Insights with Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments)</span></span>

## <a name="prerequisite"></a><span data-ttu-id="aae0e-106">Predpoklady</span><span class="sxs-lookup"><span data-stu-id="aae0e-106">Prerequisite</span></span>

- <span data-ttu-id="aae0e-107">Pred exportom segmentu z Customer Insights do Sales Marketing byť záznamy kontaktov v Dynamics 365 Marketing.</span><span class="sxs-lookup"><span data-stu-id="aae0e-107">Contact records must be present in Dynamics 365 Marketing before you can export a segment from Customer Insights to Marketing.</span></span> <span data-ttu-id="aae0e-108">Prečítajte si viac o tom, ako prijímať kontakty v [Dynamics 365 Marketing pomocou Common Data Services](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="aae0e-108">Read more on how to ingest contacts in [Dynamics 365 Marketing using Common Data Services](connect-power-query.md).</span></span>

  > [!NOTE]
  > <span data-ttu-id="aae0e-109">Export segmentov z prehľadov cieľových skupín do Marketing nevytvorí nové záznamy kontaktov v inštanciách Marketing.</span><span class="sxs-lookup"><span data-stu-id="aae0e-109">Exporting segments from audience insights to Marketing will not create new contact records in the Marketing instances.</span></span> <span data-ttu-id="aae0e-110">Záznamy kontaktov z Marketing musia byť obsiahnuté v prehľadoch cieľových skupín a použité ako zdroj údajov.</span><span class="sxs-lookup"><span data-stu-id="aae0e-110">The contact records from Marketing must be ingested in audience insights and used as a data source.</span></span> <span data-ttu-id="aae0e-111">Pred exportom segmentov je ich tiež potrebné ich zahrnúť do zjednotenej entity zákazníka na mapovanie ID zákazníkov na ID kontaktov.</span><span class="sxs-lookup"><span data-stu-id="aae0e-111">They also need to be included in the unified Customer entity to map customer IDs to contact IDs before segments can be exported.</span></span>

## <a name="configure-the-connector-for-marketing"></a><span data-ttu-id="aae0e-112">Nakonfigurujte konektor pre Marketing</span><span class="sxs-lookup"><span data-stu-id="aae0e-112">Configure the connector for Marketing</span></span>

1. <span data-ttu-id="aae0e-113">V prehľadoch cieľových skupín prejdite na **Správca** > **Ciele exportu**.</span><span class="sxs-lookup"><span data-stu-id="aae0e-113">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="aae0e-114">Pod **Dynamics 365 Marketing** vyberte **Nastaviť**.</span><span class="sxs-lookup"><span data-stu-id="aae0e-114">Under **Dynamics 365 Marketing**, select **Set up**.</span></span>

1. <span data-ttu-id="aae0e-115">Do poľa **Zobrazovaný názov** zadajte rozpoznateľný názov cieľa exportu.</span><span class="sxs-lookup"><span data-stu-id="aae0e-115">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="aae0e-116">Zadajte marketingovú adresu URL svojej organizácie do poľa **Adresa servera**.</span><span class="sxs-lookup"><span data-stu-id="aae0e-116">Enter your organization's Marketing URL in the **Server address** field.</span></span>

1. <span data-ttu-id="aae0e-117">V sekcii **Konto správcu servera** vyberte **Prihlásiť sa** a vyberte Dynamics 365 Marketing.</span><span class="sxs-lookup"><span data-stu-id="aae0e-117">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Marketing account.</span></span>

1. <span data-ttu-id="aae0e-118">Namapujte pole ID zákazníka k ID kontaktu služby Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="aae0e-118">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="aae0e-119">Vyberte **Ďalej**.</span><span class="sxs-lookup"><span data-stu-id="aae0e-119">Select **Next**.</span></span>

1. <span data-ttu-id="aae0e-120">Vyberte jeden alebo viac segmentov.</span><span class="sxs-lookup"><span data-stu-id="aae0e-120">Choose one or more segments.</span></span>

1. <span data-ttu-id="aae0e-121">Vyberte položku **Uložiť**.</span><span class="sxs-lookup"><span data-stu-id="aae0e-121">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="aae0e-122">Export údajov</span><span class="sxs-lookup"><span data-stu-id="aae0e-122">Export the data</span></span>

<span data-ttu-id="aae0e-123">Môžete [exportovať údaje na vyžiadanie](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="aae0e-123">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="aae0e-124">Export sa spustí aj pri každej [plánovanej obnove](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="aae0e-124">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]