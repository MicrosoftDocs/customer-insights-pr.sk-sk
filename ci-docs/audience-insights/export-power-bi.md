---
title: Konektor služby Power BI
description: Informácie o používaní konektora Dynamics 365 Customer Insights v Power BI.
ms.date: 09/21/2020
ms.reviewer: sthe
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: d497ca779a337c512a7254524f597cff226bcb45
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406895"
---
# <a name="connector-for-power-bi-preview"></a><span data-ttu-id="4d8e4-103">Konektor pre Power BI (ukážka)</span><span class="sxs-lookup"><span data-stu-id="4d8e4-103">Connector for Power BI (preview)</span></span>

<span data-ttu-id="4d8e4-104">Vytvorte vizualizácie svojich údajov cez Power BI Desktop.</span><span class="sxs-lookup"><span data-stu-id="4d8e4-104">Create visualizations for your data with the Power BI Desktop.</span></span> <span data-ttu-id="4d8e4-105">Vytvárajte ďalšie informácie a zostavujte prehľady s vašimi zjednotenými údajmi o zákazníkoch.</span><span class="sxs-lookup"><span data-stu-id="4d8e4-105">Generate additional insights and build reports with your unified customer data.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="4d8e4-106">Predpoklady</span><span class="sxs-lookup"><span data-stu-id="4d8e4-106">Prerequisites</span></span>

- <span data-ttu-id="4d8e4-107">Máte zjednotené profily zákazníkov.</span><span class="sxs-lookup"><span data-stu-id="4d8e4-107">You have unified customer profiles.</span></span>
- <span data-ttu-id="4d8e4-108">Najnovšia verzia [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) je nainštalovaná vo vašom počítači.</span><span class="sxs-lookup"><span data-stu-id="4d8e4-108">The latest version of [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) is installed on your computer.</span></span> <span data-ttu-id="4d8e4-109">[Ďalšie informácie o Power BI Desktop](https://docs.microsoft.com/power-bi/desktop-what-is-desktop)</span><span class="sxs-lookup"><span data-stu-id="4d8e4-109">[Learn more about Power BI Desktop](https://docs.microsoft.com/power-bi/desktop-what-is-desktop).</span></span>

## <a name="configure-the-connector-for-power-bi"></a><span data-ttu-id="4d8e4-110">Nakonfigurujte konektor pre Power BI</span><span class="sxs-lookup"><span data-stu-id="4d8e4-110">Configure the connector for Power BI</span></span>

1. <span data-ttu-id="4d8e4-111">V Power BI Desktop vyberte **Súbor** > **Získať údaje**.</span><span class="sxs-lookup"><span data-stu-id="4d8e4-111">In Power BI Desktop, select **File** > **Get Data**.</span></span>

1. <span data-ttu-id="4d8e4-112">Vyberte **Zobraziť viac** and vyhľadajte **Dynamics 365 Customer Insights**</span><span class="sxs-lookup"><span data-stu-id="4d8e4-112">Select **See more** and search for **Dynamics 365 Customer Insights**</span></span>

1. <span data-ttu-id="4d8e4-113">Vyberte výsledok a položku **Pripojiť**.</span><span class="sxs-lookup"><span data-stu-id="4d8e4-113">Select the result and select **Connect**.</span></span>

1. <span data-ttu-id="4d8e4-114">**Prihláste sa** s účtom tej istej organizácie, ktorý používate pre Customer Insights a vyberte **Pripojiť sa**.</span><span class="sxs-lookup"><span data-stu-id="4d8e4-114">**Sign in** with the same organizational account you use for Customer Insights and select **Connect**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="4d8e4-115">Účet, ktorý v tomto kroku uvediete, sa použije na načítanie údajov zo služby Customer Insights a nemusí byť totožný s tým, do ktorého ste prihlásení v Power BI.</span><span class="sxs-lookup"><span data-stu-id="4d8e4-115">The account you indicate in this step is used to fetch data from Customer Insights and doesn't need to be the same you are signed in to Power BI.</span></span> <span data-ttu-id="4d8e4-116">Ak chcete resetovať účet, ktorý sa používa na načítanie údajov, otvorte Power BI a prejdite na **Súbor** > **Možnosti** > **Nastavenia** > **Nastavenia zdroja údajov**.</span><span class="sxs-lookup"><span data-stu-id="4d8e4-116">To reset the account that is used for data fetching, open Power BI and go to **File** > **Options** > **Settings** > **Data source settings**.</span></span> <span data-ttu-id="4d8e4-117">V zozname zdrojov údajov vyberte **Prihlásiť sa do Dynamics 365 Customer Insights** a vyberte **Vymazať povolenia**.</span><span class="sxs-lookup"><span data-stu-id="4d8e4-117">In the list of data sources, select **Dynamics 365 Customer Insights Login** and select **Clear permissions**.</span></span>  

1. <span data-ttu-id="4d8e4-118">V dialógovom okne **Navigátor**.</span><span class="sxs-lookup"><span data-stu-id="4d8e4-118">In the **Navigator** dialog box.</span></span> <span data-ttu-id="4d8e4-119">zobrazí zoznam všetkých prostredí, ku ktorým máte prístup.</span><span class="sxs-lookup"><span data-stu-id="4d8e4-119">you see the list of all environments you have access to.</span></span> <span data-ttu-id="4d8e4-120">Rozbaľte prostredie a otvorte ktorýkoľvek z priečinkov (entity, miery, segmenty, obohatenia).</span><span class="sxs-lookup"><span data-stu-id="4d8e4-120">Expand an environment and open any of the folders (entities, measures, segments, enrichments).</span></span> <span data-ttu-id="4d8e4-121">Napríklad otvorte priečinok **Entity**, aby ste videli všetky entity, ktoré môžete importovať.</span><span class="sxs-lookup"><span data-stu-id="4d8e4-121">For example, open the **Entities** folder, to see all entities you can import.</span></span>

   <span data-ttu-id="4d8e4-122">![Navigátor konektora Power BI](media/power-bi-navigator.png "Navigátor konektora Power BI")</span><span class="sxs-lookup"><span data-stu-id="4d8e4-122">![Power BI Connector Navigator](media/power-bi-navigator.png "Power BI Connector Navigator")</span></span>

1. <span data-ttu-id="4d8e4-123">Začiarknite políčka vedľa entít, ktoré chcete zahrnúť, a vyberte **Načítať**.</span><span class="sxs-lookup"><span data-stu-id="4d8e4-123">Select the check boxes next to the entities to include and **Load**.</span></span> <span data-ttu-id="4d8e4-124">Môžete zvoliť viacero entít z viacerých prostredí.</span><span class="sxs-lookup"><span data-stu-id="4d8e4-124">You can select multiple entities from multiple environments.</span></span>

1. <span data-ttu-id="4d8e4-125">Pri načítaní entít sa zobrazí dialógové okno načítania.</span><span class="sxs-lookup"><span data-stu-id="4d8e4-125">You'll see a loading dialog box while your entities are loaded.</span></span> <span data-ttu-id="4d8e4-126">Po načítaní všetkých vybratých entít môžete využívať možnosti služby Power BI na vizualizáciu údajov.</span><span class="sxs-lookup"><span data-stu-id="4d8e4-126">Once all of your selected entities have loaded, you can use the capabilities of Power BI to visualize the data.</span></span>

## <a name="large-data-sets"></a><span data-ttu-id="4d8e4-127">Veľké množiny údajov</span><span class="sxs-lookup"><span data-stu-id="4d8e4-127">Large data sets</span></span>

<span data-ttu-id="4d8e4-128">Konektor Customer Insights pre Power BI je navrhnutý tak, aby fungoval pre súbory údajov, ktoré obsahujú až 1 milión profilov zákazníkov.</span><span class="sxs-lookup"><span data-stu-id="4d8e4-128">The Customer Insights connector for Power BI is designed to work for data sets that contain up to 1 million customer profiles.</span></span> <span data-ttu-id="4d8e4-129">Import väčších množín údajov môže fungovať, ale trvá to dlho.</span><span class="sxs-lookup"><span data-stu-id="4d8e4-129">Importing larger data sets may work, but it takes a long time.</span></span> <span data-ttu-id="4d8e4-130">Proces by navyše mohol vypršať kvôli časovému limitu Power BI.</span><span class="sxs-lookup"><span data-stu-id="4d8e4-130">Additionally, the process could run into a time-out because of Power BI limitations.</span></span> <span data-ttu-id="4d8e4-131">Viac informácií nájdete v časti [Power BI: Odporúčania pre veľké množiny údajov](https://docs.microsoft.com/power-bi/admin/service-premium-what-is#large-datasets).</span><span class="sxs-lookup"><span data-stu-id="4d8e4-131">For more information, see [Power BI: Recommendations for large data sets](https://docs.microsoft.com/power-bi/admin/service-premium-what-is#large-datasets).</span></span> 

### <a name="work-with-a-subset-of-data"></a><span data-ttu-id="4d8e4-132">Práca s podmnožinou údajov</span><span class="sxs-lookup"><span data-stu-id="4d8e4-132">Work with a subset of data</span></span>

<span data-ttu-id="4d8e4-133">Zvážte prácu s podmnožinou svojich údajov.</span><span class="sxs-lookup"><span data-stu-id="4d8e4-133">Consider working with a subset of your data.</span></span> <span data-ttu-id="4d8e4-134">Môžete napríklad vytvárať [segmenty](segments.md) namiesto exportovania všetkých záznamov zákazníkov do služby Power BI.</span><span class="sxs-lookup"><span data-stu-id="4d8e4-134">For example, you can create [segments](segments.md) instead of exporting all customer records to Power BI.</span></span>
