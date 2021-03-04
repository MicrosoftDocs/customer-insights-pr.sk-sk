---
title: Prírastkové obnovenie pre zdroje údajov založené na doplnku Power Query
description: Obnovenie nových a aktualizovaných údajov pre veľké zdroje údajov na základe Power Query.
ms.date: 09/28/2020
ms.reviewer: adkuppa
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: d4b01be75d25fa0e120904924a193171eefec579
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268567"
---
# <a name="incremental-refresh-for-data-sources-based-on-power-query"></a><span data-ttu-id="b8e18-103">Prírastkové obnovenie pre zdroje údajov založené na Power Query</span><span class="sxs-lookup"><span data-stu-id="b8e18-103">Incremental refresh for data sources based on Power Query</span></span>

<span data-ttu-id="b8e18-104">Prírastkové obnovenie pre zdroje údajov poskytuje nasledujúce výhody:</span><span class="sxs-lookup"><span data-stu-id="b8e18-104">Incremental refresh for data sources provides the following advantages:</span></span>

- <span data-ttu-id="b8e18-105">**Rýchlejšie obnovenie** – Obnovia sa iba údaje, ktoré sa zmenili.</span><span class="sxs-lookup"><span data-stu-id="b8e18-105">**Faster refreshes** - Only data that has changed gets refreshed.</span></span> <span data-ttu-id="b8e18-106">Môžete napríklad obnoviť iba posledných päť dní historického súboru údajov.</span><span class="sxs-lookup"><span data-stu-id="b8e18-106">For example, you might refresh only the past five days of a historical dataset.</span></span>
- <span data-ttu-id="b8e18-107">**Zvýšená spoľahlivosť** – Pri menších aktualizáciách nemusíte udržiavať pripojenia k systémom pohyblivých zdrojov tak dlho, aby ste znížili riziko problémov s pripojením.</span><span class="sxs-lookup"><span data-stu-id="b8e18-107">**Increased reliability** - With smaller refreshes, you don't need to maintain connections to volatile source systems for as long, reducing the risk of connection issues.</span></span>
- <span data-ttu-id="b8e18-108">**Znížená spotreba zdrojov** – Obnovenie iba podskupiny vašich celkových údajov vedie k efektívnejšiemu využívaniu výpočtových zdrojov a znižuje environmentálnu stopu.</span><span class="sxs-lookup"><span data-stu-id="b8e18-108">**Reduced resource consumption** - Refreshing only a subset of your total data leads to more efficient use of computing resources and decreases the environmental footprint.</span></span>

## <a name="configure-incremental-refresh"></a><span data-ttu-id="b8e18-109">Konfigurácia prírastkového obnovenia</span><span class="sxs-lookup"><span data-stu-id="b8e18-109">Configure incremental refresh</span></span>

<span data-ttu-id="b8e18-110">Prehľady cieľových skupín umožňujú prírastkové obnovenie pre zdroje údajov importované prostredníctvom doplnku Power Query, ktoré podporujú prírastkové prijímanie.</span><span class="sxs-lookup"><span data-stu-id="b8e18-110">Audience insights allows incremental refresh for data sources imported through Power Query that support incremental ingestion.</span></span> <span data-ttu-id="b8e18-111">Napríklad databázy Azure SQL s poliami dátum a čas, ktoré označujú, kedy boli záznamy údajov naposledy aktualizované.</span><span class="sxs-lookup"><span data-stu-id="b8e18-111">For example, Azure SQL databases with date and time fields, which indicate when data records were last updated.</span></span>

1. <span data-ttu-id="b8e18-112">[Vytvorenie nového zdroja údajov na základe Power Query](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="b8e18-112">[Create a new data source based on Power Query](connect-power-query.md).</span></span>

1. <span data-ttu-id="b8e18-113">Zadajte názov pre zdroj údajov.</span><span class="sxs-lookup"><span data-stu-id="b8e18-113">Provide a name for the data source.</span></span>

1. <span data-ttu-id="b8e18-114">Vyberte zdroj údajov, ktorý podporuje postupné obnovovanie, ako je napríklad databáza Azure SQL.</span><span class="sxs-lookup"><span data-stu-id="b8e18-114">Select a data source that supports incremental refresh, such as Azure SQL database.</span></span>

1. <span data-ttu-id="b8e18-115">Vyberte entity alebo tabuľky, ktoré chcete prijať.</span><span class="sxs-lookup"><span data-stu-id="b8e18-115">Select the entities or tables to ingest.</span></span>

1. <span data-ttu-id="b8e18-116">Dokončite kroky transformácie a vyberte položku **Ďalej**.</span><span class="sxs-lookup"><span data-stu-id="b8e18-116">Complete the transformation steps and select **Next**.</span></span>

1. <span data-ttu-id="b8e18-117">V dialógovom okne **Nastaviť prírastkové obnovovanie** zvoľte možnosť **Nastaviť**, čím sa otvorí **Nastavenia prírastkového obnovovania**.</span><span class="sxs-lookup"><span data-stu-id="b8e18-117">In the **Set up incremental refresh** dialog box, select **Set up** to open the **Incremental refresh settings**.</span></span> <span data-ttu-id="b8e18-118">Ak zvolíte možnosť **Preskočiť**, zdroj údajov obnoví celú množinu údajov.</span><span class="sxs-lookup"><span data-stu-id="b8e18-118">If you select **Skip**, the data source will refresh the entire data set.</span></span>
   > [!TIP]
   > <span data-ttu-id="b8e18-119">Prírastkové obnovenie môžete použiť aj neskôr úpravou existujúceho zdroja údajov.</span><span class="sxs-lookup"><span data-stu-id="b8e18-119">You can also apply incremental refresh later by editing an existing data source.</span></span>

1. <span data-ttu-id="b8e18-120">V časti **Nastavenia prírastkového obnovovania** nakonfigurujete prírastkové obnovovanie pre všetky entity, ktoré ste si vybrali pri vytváraní zdroja údajov.</span><span class="sxs-lookup"><span data-stu-id="b8e18-120">On **Incremental refresh settings**, you'll configure the incremental refresh for all entities that you selected when creating the data source.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="b8e18-121">![Nakonfigurujte entity v zdroj údajov na prírastkové obnovovanie](media/incremental-refresh-settings.png "Nakonfigurujte entity v zdroj údajov na prírastkové obnovovanie")</span><span class="sxs-lookup"><span data-stu-id="b8e18-121">![Configure entities in a data source for incremental refresh](media/incremental-refresh-settings.png "Configure entities in a data source for incremental refresh")</span></span>

1. <span data-ttu-id="b8e18-122">Vyberte entitu a zadajte nasledujúce podrobnosti:</span><span class="sxs-lookup"><span data-stu-id="b8e18-122">Select an entity, and provide the following details:</span></span>

   - <span data-ttu-id="b8e18-123">**Definujte primárny kľúč**: Vyberte primárny kľúč pre entitu alebo tabuľku.</span><span class="sxs-lookup"><span data-stu-id="b8e18-123">**Define the primary key**: Select a primary key for the entity or table.</span></span>
   - <span data-ttu-id="b8e18-124">**Definujte pole Naposledy aktualizované**: Toto pole zobrazí iba atribúty typu dátum alebo čas.</span><span class="sxs-lookup"><span data-stu-id="b8e18-124">**Define the "last updated" field**: This field will only display attributes of type date or time.</span></span> <span data-ttu-id="b8e18-125">Vyberte atribút, ktorý označuje, kedy boli záznamy naposledy aktualizované.</span><span class="sxs-lookup"><span data-stu-id="b8e18-125">Select an attribute that indicates when the records were last updated.</span></span> <span data-ttu-id="b8e18-126">Bude sa používať na identifikáciu záznamov, ktoré spadajú do časového rámca prírastkovej obnovy.</span><span class="sxs-lookup"><span data-stu-id="b8e18-126">It will be used to identify the records that fall within the incremental refresh time frame.</span></span>
   - <span data-ttu-id="b8e18-127">**Vyhľadávať aktualizácie s frekvenciou**: Zadajte, ako dlho chcete, aby bol časový rámec prírastkového obnovovania.</span><span class="sxs-lookup"><span data-stu-id="b8e18-127">**Check for updates every**: Specify how long you want the incremental refresh time frame to be.</span></span>

1. <span data-ttu-id="b8e18-128">Stlačte možnosť **Uložiť** na dokončenie vytvorenia zdroja údajov.</span><span class="sxs-lookup"><span data-stu-id="b8e18-128">Select **Save** to complete the creation of the data source.</span></span> <span data-ttu-id="b8e18-129">Počiatočná obnova dát bude úplne obnovená.</span><span class="sxs-lookup"><span data-stu-id="b8e18-129">The initial data refresh will be a full refresh.</span></span> <span data-ttu-id="b8e18-130">Potom sa prírastkové obnovenie údajov uskutoční tak, ako bolo nakonfigurované v predchádzajúcom kroku.</span><span class="sxs-lookup"><span data-stu-id="b8e18-130">Afterwards, the incremental data refresh happens as configured in the previous step.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]