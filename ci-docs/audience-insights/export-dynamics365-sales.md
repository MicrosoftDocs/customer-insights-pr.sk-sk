---
title: Export údajov služby Customer Insights do Dynamics 365 Sales
description: Naučte sa, ako nakonfigurovať pripojenie k Dynamics 365 Sales.
ms.date: 02/01/2021
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 0013c4e6a96401d6cdbea55ed38f85f5e10dcc56
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269027"
---
# <a name="connector-for-dynamics-365-sales-preview"></a><span data-ttu-id="3792f-103">Konektor pre Dynamics 365 Sales (ukážka)</span><span class="sxs-lookup"><span data-stu-id="3792f-103">Connector for Dynamics 365 Sales (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="3792f-104">Dynamics 365 Sales umožňuje pomocou zákazníckych údajov vytvárať marketingové zoznamy, sledovať pracovné postupy a odosielať propagačné akcie.</span><span class="sxs-lookup"><span data-stu-id="3792f-104">Use your customer data to create marketing lists, follow up workflows, and send out promotions with Dynamics 365 Sales.</span></span>

## <a name="prerequisite"></a><span data-ttu-id="3792f-105">Predpoklady</span><span class="sxs-lookup"><span data-stu-id="3792f-105">Prerequisite</span></span>

1. <span data-ttu-id="3792f-106">Pred exportom segmentu z Customer Insights do Sales musia byť záznamy kontaktov v Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="3792f-106">Contact records must be present in Dynamics 365 Sales before you can export a segment from Customer Insights to Sales.</span></span> <span data-ttu-id="3792f-107">Prečítajte si viac o tom, ako prijímať kontakty v [Dynamics 365 Sales pomocou Common Data Services](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="3792f-107">Read more on how to ingest contacts in [Dynamics 365 Sales using Common Data Services](connect-power-query.md).</span></span>

   > [!NOTE]
   > <span data-ttu-id="3792f-108">Export segmentov z prehľadov cieľových skupín do Sales nevytvorí nové záznamy kontaktov v inštanciách Sales.</span><span class="sxs-lookup"><span data-stu-id="3792f-108">Exporting segments from audience insights to Sales will not create new contact records in the Sales instances.</span></span> <span data-ttu-id="3792f-109">Záznamy kontaktov zo Sales musia byť obsiahnuté v prehľadoch cieľových skupín a použité ako zdroj údajov.</span><span class="sxs-lookup"><span data-stu-id="3792f-109">The contact records from Sales must be ingested in audience insights and used as a data source.</span></span> <span data-ttu-id="3792f-110">Pred exportom segmentov je ich tiež potrebné ich zahrnúť do zjednotenej entity zákazníka na mapovanie ID zákazníkov na ID kontaktov.</span><span class="sxs-lookup"><span data-stu-id="3792f-110">They also need to be included in the unified Customer entity to map customer IDs to contact IDs before segments can be exported.</span></span>

## <a name="configure-the-connector-for-sales"></a><span data-ttu-id="3792f-111">Nakonfigurujte konektor pre Predaj</span><span class="sxs-lookup"><span data-stu-id="3792f-111">Configure the connector for Sales</span></span>

1. <span data-ttu-id="3792f-112">V prehľadoch cieľových skupín prejdite na **Správca** > **Ciele exportu**.</span><span class="sxs-lookup"><span data-stu-id="3792f-112">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="3792f-113">Pod **Dynamics 365 Sales** vyberte **Nastaviť**.</span><span class="sxs-lookup"><span data-stu-id="3792f-113">Under **Dynamics 365 Sales**, select **Set up**.</span></span>

1. <span data-ttu-id="3792f-114">Do poľa **Zobrazovaný názov** zadajte rozpoznateľný názov cieľa exportu.</span><span class="sxs-lookup"><span data-stu-id="3792f-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="3792f-115">Zadajte marketingovú adresu Predaj URL svojej organizácie do poľa **Adresa servera**.</span><span class="sxs-lookup"><span data-stu-id="3792f-115">Enter your organization's Sales URL in the **Server address** field.</span></span>

1. <span data-ttu-id="3792f-116">V sekcii **Konto správcu servera** vyberte **Prihlásiť sa** a vyberte konto Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="3792f-116">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Sales account.</span></span>

1. <span data-ttu-id="3792f-117">Namapujte pole ID zákazníka k ID kontaktu služby Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="3792f-117">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="3792f-118">Vyberte **Ďalej**.</span><span class="sxs-lookup"><span data-stu-id="3792f-118">Select **Next**.</span></span>

1. <span data-ttu-id="3792f-119">Vyberte jeden alebo viac segmentov.</span><span class="sxs-lookup"><span data-stu-id="3792f-119">Choose one or more segments.</span></span>

1. <span data-ttu-id="3792f-120">Vyberte položku **Uložiť**.</span><span class="sxs-lookup"><span data-stu-id="3792f-120">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="3792f-121">Export údajov</span><span class="sxs-lookup"><span data-stu-id="3792f-121">Export the data</span></span>

<span data-ttu-id="3792f-122">Môžete [exportovať údaje na vyžiadanie](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="3792f-122">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="3792f-123">Export sa spustí aj pri každej [plánovanej obnove](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="3792f-123">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]