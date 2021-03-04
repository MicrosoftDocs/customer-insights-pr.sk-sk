---
title: Konektor služby Power BI
description: Informácie o používaní konektora Dynamics 365 Customer Insights v Power BI.
ms.date: 09/21/2020
ms.reviewer: sthe
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 0607a4644ac7d7beb19e4faecf012efcd197d48c
ms.sourcegitcommit: 0260ed244b97c2fd0be5e9a084c4c489358e8d4f
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 02/18/2021
ms.locfileid: "5477107"
---
# <a name="connector-for-power-bi-preview"></a><span data-ttu-id="73441-103">Konektor pre Power BI (ukážka)</span><span class="sxs-lookup"><span data-stu-id="73441-103">Connector for Power BI (preview)</span></span>

<span data-ttu-id="73441-104">Vytvorte vizualizácie svojich údajov cez Power BI Desktop.</span><span class="sxs-lookup"><span data-stu-id="73441-104">Create visualizations for your data with the Power BI Desktop.</span></span> <span data-ttu-id="73441-105">Vytvárajte ďalšie informácie a zostavujte prehľady s vašimi zjednotenými údajmi o zákazníkoch.</span><span class="sxs-lookup"><span data-stu-id="73441-105">Generate additional insights and build reports with your unified customer data.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="73441-106">Predpoklady</span><span class="sxs-lookup"><span data-stu-id="73441-106">Prerequisites</span></span>

- <span data-ttu-id="73441-107">Máte zjednotené profily zákazníkov.</span><span class="sxs-lookup"><span data-stu-id="73441-107">You have unified customer profiles.</span></span>
- <span data-ttu-id="73441-108">Najnovšia verzia [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) je nainštalovaná vo vašom počítači.</span><span class="sxs-lookup"><span data-stu-id="73441-108">The latest version of [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) is installed on your computer.</span></span> <span data-ttu-id="73441-109">[Ďalšie informácie o Power BI Desktop](https://docs.microsoft.com/power-bi/desktop-what-is-desktop)</span><span class="sxs-lookup"><span data-stu-id="73441-109">[Learn more about Power BI Desktop](https://docs.microsoft.com/power-bi/desktop-what-is-desktop).</span></span>

## <a name="configure-the-connector-for-power-bi"></a><span data-ttu-id="73441-110">Nakonfigurujte konektor pre Power BI</span><span class="sxs-lookup"><span data-stu-id="73441-110">Configure the connector for Power BI</span></span>

1. <span data-ttu-id="73441-111">V Power BI Desktop vyberte **Súbor** > **Získať údaje**.</span><span class="sxs-lookup"><span data-stu-id="73441-111">In Power BI Desktop, select **File** > **Get Data**.</span></span>

1. <span data-ttu-id="73441-112">Vyberte **Zobraziť viac** and vyhľadajte **Dynamics 365 Customer Insights**</span><span class="sxs-lookup"><span data-stu-id="73441-112">Select **See more** and search for **Dynamics 365 Customer Insights**</span></span>

1. <span data-ttu-id="73441-113">Vyberte možnosť **Pripojiť**.</span><span class="sxs-lookup"><span data-stu-id="73441-113">Select **Connect**.</span></span>

1. <span data-ttu-id="73441-114">**Prihláste sa** s účtom tej istej organizácie, ktorý používate pre Customer Insights a vyberte **Pripojiť sa**.</span><span class="sxs-lookup"><span data-stu-id="73441-114">**Sign in** with the same organizational account you use for Customer Insights and select **Connect**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="73441-115">Účet, ktorý v tomto kroku uvediete, sa použije na načítanie údajov zo služby Customer Insights a nemusí byť totožný s tým, do ktorého ste prihlásení v Power BI.</span><span class="sxs-lookup"><span data-stu-id="73441-115">The account you indicate in this step is used to fetch data from Customer Insights and doesn't need to be the same you are signed in to Power BI.</span></span> <span data-ttu-id="73441-116">Ak chcete resetovať účet, ktorý sa používa na načítanie údajov, otvorte Power BI a prejdite na **Súbor** > **Možnosti** > **Nastavenia** > **Nastavenia zdroja údajov**.</span><span class="sxs-lookup"><span data-stu-id="73441-116">To reset the account that is used for data fetching, open Power BI and go to **File** > **Options** > **Settings** > **Data source settings**.</span></span> <span data-ttu-id="73441-117">V zozname zdrojov údajov vyberte **Prihlásiť sa do Dynamics 365 Customer Insights** a vyberte **Vymazať povolenia**.</span><span class="sxs-lookup"><span data-stu-id="73441-117">In the list of data sources, select **Dynamics 365 Customer Insights Login** and select **Clear permissions**.</span></span>  

1. <span data-ttu-id="73441-118">V dialógovom okne **Navigátor**.</span><span class="sxs-lookup"><span data-stu-id="73441-118">In the **Navigator** dialog box.</span></span> <span data-ttu-id="73441-119">zobrazí zoznam všetkých prostredí, ku ktorým máte prístup.</span><span class="sxs-lookup"><span data-stu-id="73441-119">you see the list of all environments you have access to.</span></span> <span data-ttu-id="73441-120">Rozbaľte prostredie a otvorte ktorýkoľvek z priečinkov (entity, miery, segmenty, obohatenia).</span><span class="sxs-lookup"><span data-stu-id="73441-120">Expand an environment and open any of the folders (entities, measures, segments, enrichments).</span></span> <span data-ttu-id="73441-121">Napríklad otvorte priečinok **Entity**, aby ste videli všetky entity, ktoré môžete importovať.</span><span class="sxs-lookup"><span data-stu-id="73441-121">For example, open the **Entities** folder, to see all entities you can import.</span></span>

   <span data-ttu-id="73441-122">![Navigátor konektora Power BI](media/power-bi-navigator.png "Navigátor konektora Power BI")</span><span class="sxs-lookup"><span data-stu-id="73441-122">![Power BI Connector Navigator](media/power-bi-navigator.png "Power BI Connector Navigator")</span></span>

1. <span data-ttu-id="73441-123">Začiarknite políčka vedľa entít, ktoré chcete zahrnúť, a vyberte **Načítať**.</span><span class="sxs-lookup"><span data-stu-id="73441-123">Select the check boxes next to the entities to include and **Load**.</span></span> <span data-ttu-id="73441-124">Môžete zvoliť viacero entít z viacerých prostredí.</span><span class="sxs-lookup"><span data-stu-id="73441-124">You can select multiple entities from multiple environments.</span></span>

1. <span data-ttu-id="73441-125">Pri načítaní entít sa zobrazí dialógové okno načítania.</span><span class="sxs-lookup"><span data-stu-id="73441-125">You'll see a loading dialog box while your entities are loaded.</span></span> <span data-ttu-id="73441-126">Po načítaní všetkých vybratých entít môžete využívať možnosti služby Power BI na vizualizáciu údajov.</span><span class="sxs-lookup"><span data-stu-id="73441-126">Once all of your selected entities have loaded, you can use the capabilities of Power BI to visualize the data.</span></span>

## <a name="large-data-sets"></a><span data-ttu-id="73441-127">Veľké množiny údajov</span><span class="sxs-lookup"><span data-stu-id="73441-127">Large data sets</span></span>

<span data-ttu-id="73441-128">Konektor Customer Insights pre Power BI je navrhnutý tak, aby fungoval pre súbory údajov, ktoré obsahujú až 1 milión profilov zákazníkov.</span><span class="sxs-lookup"><span data-stu-id="73441-128">The Customer Insights connector for Power BI is designed to work for data sets that contain up to 1 million customer profiles.</span></span> <span data-ttu-id="73441-129">Import väčších množín údajov môže fungovať, ale trvá to dlho.</span><span class="sxs-lookup"><span data-stu-id="73441-129">Importing larger data sets may work, but it takes a long time.</span></span> <span data-ttu-id="73441-130">Proces by navyše mohol vypršať kvôli časovému limitu Power BI.</span><span class="sxs-lookup"><span data-stu-id="73441-130">Additionally, the process could run into a time-out because of Power BI limitations.</span></span> <span data-ttu-id="73441-131">Viac informácií nájdete v časti [Power BI: Odporúčania pre veľké množiny údajov](https://docs.microsoft.com/power-bi/admin/service-premium-what-is#large-datasets).</span><span class="sxs-lookup"><span data-stu-id="73441-131">For more information, see [Power BI: Recommendations for large data sets](https://docs.microsoft.com/power-bi/admin/service-premium-what-is#large-datasets).</span></span> 

### <a name="work-with-a-subset-of-data"></a><span data-ttu-id="73441-132">Práca s podmnožinou údajov</span><span class="sxs-lookup"><span data-stu-id="73441-132">Work with a subset of data</span></span>

<span data-ttu-id="73441-133">Zvážte prácu s podmnožinou svojich údajov.</span><span class="sxs-lookup"><span data-stu-id="73441-133">Consider working with a subset of your data.</span></span> <span data-ttu-id="73441-134">Môžete napríklad vytvárať [segmenty](segments.md) namiesto exportovania všetkých záznamov zákazníkov do služby Power BI.</span><span class="sxs-lookup"><span data-stu-id="73441-134">For example, you can create [segments](segments.md) instead of exporting all customer records to Power BI.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="73441-135">Riešenie problémov</span><span class="sxs-lookup"><span data-stu-id="73441-135">Troubleshooting</span></span>

### <a name="customer-insights-environment-doesnt-show-in-power-bi"></a><span data-ttu-id="73441-136">Prostredie Customer Insights sa nezobrazuje v Power BI</span><span class="sxs-lookup"><span data-stu-id="73441-136">Customer Insights environment doesn't show in Power BI</span></span>

<span data-ttu-id="73441-137">Prostredia, ktoré majú viac ako jeden [vzťah](relationships.md) definovaný medzi dvoma rovnakými entitami v prehľadoch cieľových skupín, nebudú k dispozícii v konektore Power BI.</span><span class="sxs-lookup"><span data-stu-id="73441-137">Environments that have more than one [relationship](relationships.md) defined between two identical entities in audience insights will not be available in the Power BI connector.</span></span>

<span data-ttu-id="73441-138">Môžete identifikovať a odstrániť duplicitné vzťahy.</span><span class="sxs-lookup"><span data-stu-id="73441-138">You can identify and remove the duplicated relationships.</span></span>

1. <span data-ttu-id="73441-139">V prehľadoch cieľových skupín choďte na **Údaje** > **Vzťahy** v prostredí, v ktorom vám chýba v Power BI.</span><span class="sxs-lookup"><span data-stu-id="73441-139">In audience insights, go to **Data** > **Relationships** on the environment you're missing in Power BI.</span></span>
2. <span data-ttu-id="73441-140">Identifikujte duplicitné vzťahy:</span><span class="sxs-lookup"><span data-stu-id="73441-140">Identify duplicated relationships:</span></span>
   - <span data-ttu-id="73441-141">Skontrolujte, či je medzi rovnakými dvoma entitami definovaných viac ako jeden vzťah.</span><span class="sxs-lookup"><span data-stu-id="73441-141">Check if there is more than one relationship defined between the same two entities.</span></span>
   - <span data-ttu-id="73441-142">Skontrolujte, či existuje vzťah medzi dvoma entitami, ktoré sú obe zahrnuté v procese zjednotenia.</span><span class="sxs-lookup"><span data-stu-id="73441-142">Check if there is a relationship created between two entities that are both included in the unification process.</span></span> <span data-ttu-id="73441-143">Existuje implicitný vzťah definovaný medzi všetkými entitami zahrnutými do procesu zjednotenia.</span><span class="sxs-lookup"><span data-stu-id="73441-143">There is an implicit relationship defined between all entities included in the unification process.</span></span>
3. <span data-ttu-id="73441-144">Odstráňte všetky zistené duplicitné vzťahy.</span><span class="sxs-lookup"><span data-stu-id="73441-144">Remove any duplicate relationships identified.</span></span>

<span data-ttu-id="73441-145">Po odstránení duplicitných vzťahov sa pokúste konektor Power BI nakonfigurovať znova.</span><span class="sxs-lookup"><span data-stu-id="73441-145">After removal of the duplicated relationships, try to configure the Power BI connector again.</span></span> <span data-ttu-id="73441-146">Prostredie by malo byť dostupné hneď.</span><span class="sxs-lookup"><span data-stu-id="73441-146">The environment should be available now.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]

