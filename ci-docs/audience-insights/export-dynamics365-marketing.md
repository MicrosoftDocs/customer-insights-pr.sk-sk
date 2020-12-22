---
title: Export údajov služby Customer Insights do Dynamics 365 Marketing
description: Naučte sa, ako nakonfigurovať pripojenie k Dynamics 365 Marketing.
ms.date: 08/21/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 163387779b64bd78ef08e2d96a5f1c9615062f28
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643792"
---
# <a name="connector-for-dynamics-365-marketing-preview"></a><span data-ttu-id="f1d1a-103">Konektor pre Dynamics 365 Marketing (ukážka)</span><span class="sxs-lookup"><span data-stu-id="f1d1a-103">Connector for Dynamics 365 Marketing (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="f1d1a-104">Dynamics 365 Marketing umožňuje pomocou [segmentov](segments.md) generovať kampane a kontaktovať konkrétne skupiny zákazníkov.</span><span class="sxs-lookup"><span data-stu-id="f1d1a-104">Use [segments](segments.md) to generate campaigns and contact specific groups of customers with Dynamics 365 Marketing.</span></span> <span data-ttu-id="f1d1a-105">Viac informácií nájdete v článku [Použitie segmentov z Dynamics 365 Customer Insights s Dynamics 365 Marketing](https://docs.microsoft.com/dynamics365/marketing/customer-insights-segments)</span><span class="sxs-lookup"><span data-stu-id="f1d1a-105">For more information, see [Use segments from Dynamics 365 Customer Insights with Dynamics 365 Marketing](https://docs.microsoft.com/dynamics365/marketing/customer-insights-segments)</span></span>

## <a name="prerequisite"></a><span data-ttu-id="f1d1a-106">Predpoklady</span><span class="sxs-lookup"><span data-stu-id="f1d1a-106">Prerequisite</span></span>

<span data-ttu-id="f1d1a-107">Záznamy kontaktov [z Dynamics 365 Marketing prijaté z Common Data Service](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="f1d1a-107">Contact records [from Dynamics 365 Marketing ingested Common Data Service](connect-power-query.md).</span></span>

## <a name="configure-the-connector-for-marketing"></a><span data-ttu-id="f1d1a-108">Nakonfigurujte konektor pre Marketing</span><span class="sxs-lookup"><span data-stu-id="f1d1a-108">Configure the connector for Marketing</span></span>

1. <span data-ttu-id="f1d1a-109">V prehľadoch cieľových skupín prejdite na **Správca** > **Ciele exportu**.</span><span class="sxs-lookup"><span data-stu-id="f1d1a-109">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="f1d1a-110">Pod **Dynamics 365 Marketing** vyberte **Nastaviť**.</span><span class="sxs-lookup"><span data-stu-id="f1d1a-110">Under **Dynamics 365 Marketing**, select **Set up**.</span></span>

1. <span data-ttu-id="f1d1a-111">Do poľa **Zobrazovaný názov** zadajte rozpoznateľný názov cieľa exportu.</span><span class="sxs-lookup"><span data-stu-id="f1d1a-111">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="f1d1a-112">Zadajte marketingovú adresu URL svojej organizácie do poľa **Adresa servera**.</span><span class="sxs-lookup"><span data-stu-id="f1d1a-112">Enter your organization's Marketing URL in the **Server address** field.</span></span>

1. <span data-ttu-id="f1d1a-113">V sekcii **Konto správcu servera** vyberte **Prihlásiť sa** a vyberte Dynamics 365 Marketing.</span><span class="sxs-lookup"><span data-stu-id="f1d1a-113">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Marketing account.</span></span>

1. <span data-ttu-id="f1d1a-114">Namapujte pole ID zákazníka k ID kontaktu služby Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="f1d1a-114">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="f1d1a-115">Vyberte **Ďalej**.</span><span class="sxs-lookup"><span data-stu-id="f1d1a-115">Select **Next**.</span></span>

1. <span data-ttu-id="f1d1a-116">Vyberte jeden alebo viac segmentov.</span><span class="sxs-lookup"><span data-stu-id="f1d1a-116">Choose one or more segments.</span></span>

1. <span data-ttu-id="f1d1a-117">Vyberte položku **Uložiť**.</span><span class="sxs-lookup"><span data-stu-id="f1d1a-117">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="f1d1a-118">Export údajov</span><span class="sxs-lookup"><span data-stu-id="f1d1a-118">Export the data</span></span>

<span data-ttu-id="f1d1a-119">Môžete [exportovať údaje na vyžiadanie](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="f1d1a-119">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="f1d1a-120">Export sa spustí aj pri každej [plánovanej obnove](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="f1d1a-120">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>
