---
title: Export údajov služby Customer Insights do Dynamics 365 Sales
description: Naučte sa, ako nakonfigurovať pripojenie k Dynamics 365 Sales.
ms.date: 08/21/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: af0824e69dfdf620a0ac756e32a9bd3dd85e5151
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643837"
---
# <a name="connector-for-dynamics-365-sales-preview"></a><span data-ttu-id="831e2-103">Konektor pre Dynamics 365 Sales (ukážka)</span><span class="sxs-lookup"><span data-stu-id="831e2-103">Connector for Dynamics 365 Sales (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="831e2-104">Dynamics 365 Sales umožňuje pomocou zákazníckych údajov vytvárať marketingové zoznamy, sledovať pracovné postupy a odosielať propagačné akcie.</span><span class="sxs-lookup"><span data-stu-id="831e2-104">Use your customer data to create marketing lists, follow up workflows, and send out promotions with Dynamics 365 Sales.</span></span>

## <a name="prerequisite"></a><span data-ttu-id="831e2-105">Predpoklady</span><span class="sxs-lookup"><span data-stu-id="831e2-105">Prerequisite</span></span>

<span data-ttu-id="831e2-106">Záznamy kontaktov [z Dynamics 365 Sales prijaté z Common Data Service](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="831e2-106">Contact records [from Dynamics 365 Sales ingested using Common Data Service](connect-power-query.md).</span></span>

## <a name="configure-the-connector-for-sales"></a><span data-ttu-id="831e2-107">Nakonfigurujte konektor pre Predaj</span><span class="sxs-lookup"><span data-stu-id="831e2-107">Configure the connector for Sales</span></span>

1. <span data-ttu-id="831e2-108">V prehľadoch cieľových skupín prejdite na **Správca** > **Ciele exportu**.</span><span class="sxs-lookup"><span data-stu-id="831e2-108">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="831e2-109">Pod **Dynamics 365 Sales** vyberte **Nastaviť**.</span><span class="sxs-lookup"><span data-stu-id="831e2-109">Under **Dynamics 365 Sales**, select **Set up**.</span></span>

1. <span data-ttu-id="831e2-110">Do poľa **Zobrazovaný názov** zadajte rozpoznateľný názov cieľa exportu.</span><span class="sxs-lookup"><span data-stu-id="831e2-110">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="831e2-111">Zadajte marketingovú adresu Predaj URL svojej organizácie do poľa **Adresa servera**.</span><span class="sxs-lookup"><span data-stu-id="831e2-111">Enter your organization's Sales URL in the **Server address** field.</span></span>

1. <span data-ttu-id="831e2-112">V sekcii **Konto správcu servera** vyberte **Prihlásiť sa** a vyberte konto Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="831e2-112">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Sales account.</span></span>

1. <span data-ttu-id="831e2-113">Namapujte pole ID zákazníka k ID kontaktu služby Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="831e2-113">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="831e2-114">Vyberte **Ďalej**.</span><span class="sxs-lookup"><span data-stu-id="831e2-114">Select **Next**.</span></span>

1. <span data-ttu-id="831e2-115">Vyberte jeden alebo viac segmentov.</span><span class="sxs-lookup"><span data-stu-id="831e2-115">Choose one or more segments.</span></span>

1. <span data-ttu-id="831e2-116">Vyberte položku **Uložiť**.</span><span class="sxs-lookup"><span data-stu-id="831e2-116">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="831e2-117">Export údajov</span><span class="sxs-lookup"><span data-stu-id="831e2-117">Export the data</span></span>

<span data-ttu-id="831e2-118">Môžete [exportovať údaje na vyžiadanie](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="831e2-118">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="831e2-119">Export sa spustí aj pri každej [plánovanej obnove](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="831e2-119">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>
