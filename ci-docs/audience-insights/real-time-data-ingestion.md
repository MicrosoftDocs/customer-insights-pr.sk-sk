---
title: Príjem údajov v reálnom čase a obmedzenia
description: Všeobecné informácie o možnostiach v reálnom čase v prehľadoch cieľovej skupiny.
ms.date: 10/27/2020
ms.reviewer: nikeller
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 7421ed9d2cb399d546815b2d1b0ea5ec51ca6b6d
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 02/15/2021
ms.locfileid: "5270299"
---
# <a name="real-time-data-ingestion-preview"></a><span data-ttu-id="9a259-103">Prijímanie údajov v reálnom čase (ukážka)</span><span class="sxs-lookup"><span data-stu-id="9a259-103">Real-time data ingestion (preview)</span></span>

<span data-ttu-id="9a259-104">Vďaka funkcii takmer reálneho času môžete v priebehu niekoľkých sekúnd vidieť najnovšie interakcie, ktoré zákazníci vykonali s vašimi produktmi alebo službami.</span><span class="sxs-lookup"><span data-stu-id="9a259-104">The near real-time functionality lets you see, within seconds, the latest interactions that your customers have made with your products or services.</span></span>

<span data-ttu-id="9a259-105">[Plánované obnovenia](system.md#schedule-tab) zahŕňajú veľké množstvo záznamov a niekoľko zložitých operácií.</span><span class="sxs-lookup"><span data-stu-id="9a259-105">[Scheduled refreshes](system.md#schedule-tab) include large numbers of records and several complex operations.</span></span> <span data-ttu-id="9a259-106">Najskôr sa údaje načítajú zo zdroja údajov.</span><span class="sxs-lookup"><span data-stu-id="9a259-106">First, data is pulled from the data source.</span></span> <span data-ttu-id="9a259-107">Ďalej sú údaje zjednotené a potom obohatené o ďalšie informácie.</span><span class="sxs-lookup"><span data-stu-id="9a259-107">Next, the data is unified, and then enriched with additional information.</span></span> <span data-ttu-id="9a259-108">Každé spustenie tohto procesu môže trvať minúty až hodiny.</span><span class="sxs-lookup"><span data-stu-id="9a259-108">Every run of this process can take minutes to hours.</span></span>

<span data-ttu-id="9a259-109">Funkcia v reálnom čase sprístupňuje údaje okamžite na spotrebu, až kým nasledujúce naplánované obnovenie nenačíta tieto údaje zo zdroja údajov.</span><span class="sxs-lookup"><span data-stu-id="9a259-109">The real-time functionality provides data immediately for consumption, until the subsequent scheduled refresh pulls this data from the data source.</span></span>

<span data-ttu-id="9a259-110">Aktualizácie v reálnom čase majú čas uplynutia platnosti, po ktorom už neprepíšu hodnotu zo zdroja údajov:</span><span class="sxs-lookup"><span data-stu-id="9a259-110">Real-time updates have an expiration time after which they no longer override the value from the data source:</span></span>

- <span data-ttu-id="9a259-111">Aktualizácie profilu sa budú uchovávať 4 hodiny</span><span class="sxs-lookup"><span data-stu-id="9a259-111">Profile updates will be kept for 4 hours</span></span>
- <span data-ttu-id="9a259-112">Aktivity sa budú uchovávať 30 dní</span><span class="sxs-lookup"><span data-stu-id="9a259-112">Activities will be kept for 30 days</span></span>

<span data-ttu-id="9a259-113">Tieto hodnoty sú parametre volaní API, ktoré môžete zmeniť.</span><span class="sxs-lookup"><span data-stu-id="9a259-113">These values are API call parameters that you can change.</span></span> <span data-ttu-id="9a259-114">Ich cieľom je zabezpečiť, aby vaše zdrojové údaje zostali zdrojom pravdy.</span><span class="sxs-lookup"><span data-stu-id="9a259-114">They aim to ensure that your source data remains your source of truth.</span></span> <span data-ttu-id="9a259-115">Ak chcete, aby boli aktualizácie v reálnom čase zahrnuté na dlhšie obdobie, musíte ich pridať do zdroja údajov, aby sa načítali počas nasledujúcej plánovanej obnovy.</span><span class="sxs-lookup"><span data-stu-id="9a259-115">If you want real-time updates to be included for longer, you need to add them to a data source so they get pulled during the next scheduled refresh.</span></span>

## <a name="real-time-update-of-the-unified-customer-profile-fields"></a><span data-ttu-id="9a259-116">Aktualizácia zjednotených polí profilu zákazníka v reálnom čase</span><span class="sxs-lookup"><span data-stu-id="9a259-116">Real-time update of the unified customer profile fields</span></span>

<span data-ttu-id="9a259-117">Aktualizované profily sa v priebehu niekoľkých sekúnd zobrazia v zobrazení karty zákazníka alebo v akejkoľvek inej vizualizácii.</span><span class="sxs-lookup"><span data-stu-id="9a259-117">Updated profiles will show in the customer card view, or any other visualization, within a few seconds.</span></span>

<span data-ttu-id="9a259-118">Pretože operácie v reálnom čase sa uskutočňujú po zjednotení údajov, vzťahujú sa iba na zjednotené profily zákazníkov.</span><span class="sxs-lookup"><span data-stu-id="9a259-118">Because real-time operations take place after the data unification has happened, they only apply to the unified customer profiles.</span></span> <span data-ttu-id="9a259-119">V dôsledku toho zmeny profilu v reálnom čase neaktualizujú opatrenia, členstvo v segmentoch ani obohatenia.</span><span class="sxs-lookup"><span data-stu-id="9a259-119">Consequently, real-time profile changes will not update measures, segment membership, or enrichments.</span></span>

### <a name="limitations"></a><span data-ttu-id="9a259-120">Obmedzenia</span><span class="sxs-lookup"><span data-stu-id="9a259-120">Limitations</span></span>

- <span data-ttu-id="9a259-121">Profily zákazníkov môžu byť aktualizované, ale nemôžu byť vytvorené alebo odstránené.</span><span class="sxs-lookup"><span data-stu-id="9a259-121">Customer profiles can be updated, but not created or deleted.</span></span>
- <span data-ttu-id="9a259-122">Export aktualizácií v reálnom čase do externých systémov, napr. Power BI, momentálne nie je možný.</span><span class="sxs-lookup"><span data-stu-id="9a259-122">Exporting real-time updates to external systems, like Power BI, is not possible at the moment.</span></span>

## <a name="real-time-creation-of-activities"></a><span data-ttu-id="9a259-123">Tvorba aktivít v reálnom čase</span><span class="sxs-lookup"><span data-stu-id="9a259-123">Real-time creation of activities</span></span>

<span data-ttu-id="9a259-124">Rozhranie API v reálnom čase vám umožňuje publikovať novú aktivitu z vášho zdrojového systému (individuálny zdrojový záznam) do zjednoteného profilu zákazníka.</span><span class="sxs-lookup"><span data-stu-id="9a259-124">The real-time API lets you publish a new activity from your source system (an individual source record) to a unified customer profile.</span></span> <span data-ttu-id="9a259-125">Nová aktivita bude dostupná ako jednotná aktivita v časovej osi tohto zjednoteného profilu zákazníka do niekoľkých sekúnd.</span><span class="sxs-lookup"><span data-stu-id="9a259-125">The new activity will be available as a unified activity in that unified customer profile's timeline within seconds.</span></span> <span data-ttu-id="9a259-126">Časovú os môžete vidieť v zobrazení karty zákazníka alebo v akejkoľvek inej integrácii časovej osi, ktorú ste nakonfigurovali.</span><span class="sxs-lookup"><span data-stu-id="9a259-126">You can see the timeline in the customer card view or any other timeline integration you configured.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="9a259-127">Aktivity sú nemenné.</span><span class="sxs-lookup"><span data-stu-id="9a259-127">Activities are immutable.</span></span> <span data-ttu-id="9a259-128">Po vytvorení sa nemenia.</span><span class="sxs-lookup"><span data-stu-id="9a259-128">They don't change once created.</span></span>
> - <span data-ttu-id="9a259-129">V súčasnosti sa segmenty a miery na základe novej aktivity neaktualizujú.</span><span class="sxs-lookup"><span data-stu-id="9a259-129">Currently, segments and measures won't update based on the new activity.</span></span>
> - <span data-ttu-id="9a259-130">Aktivity pridané iba prostredníctvom rozhrania API v reálnom čase nie sú súčasťou exportu a nezobrazia sa v PowerBI.</span><span class="sxs-lookup"><span data-stu-id="9a259-130">Activities added only through the real-time API are not part of exports and won't show up in PowerBI.</span></span>

<span data-ttu-id="9a259-131">Existujú dva spôsoby pripojenia k API v reálnom čase:</span><span class="sxs-lookup"><span data-stu-id="9a259-131">There are two ways to connect to the real-time API:</span></span>

- <span data-ttu-id="9a259-132">[nepriamo](#connect-via-the-dynamics-365-customer-insights-connector), pomocou [konektora Dynamics 365 Customer Insights](https://docs.microsoft.com/connectors/customerinsights/)</span><span class="sxs-lookup"><span data-stu-id="9a259-132">[indirectly](#connect-via-the-dynamics-365-customer-insights-connector), using the [Dynamics 365 Customer Insights connector](https://docs.microsoft.com/connectors/customerinsights/)</span></span>
- <span data-ttu-id="9a259-133">[priamo](#connect-directly-to-the-real-time-api), s kódom</span><span class="sxs-lookup"><span data-stu-id="9a259-133">[directly](#connect-directly-to-the-real-time-api), with code</span></span>

<span data-ttu-id="9a259-134">Oba spôsoby vyžadujú splnenie nasledujúcich predpokladov:</span><span class="sxs-lookup"><span data-stu-id="9a259-134">Both ways share the following prerequisites:</span></span>

- <span data-ttu-id="9a259-135">Prostredie Customer Insights</span><span class="sxs-lookup"><span data-stu-id="9a259-135">A Customer Insights environment</span></span>
- <span data-ttu-id="9a259-136">Zjednotené profily zákazníka</span><span class="sxs-lookup"><span data-stu-id="9a259-136">Unified customer profiles</span></span>
- <span data-ttu-id="9a259-137">Aktivity boli nakonfigurované a spustené</span><span class="sxs-lookup"><span data-stu-id="9a259-137">Activities configured and run</span></span>
- <span data-ttu-id="9a259-138">Povolenia prispievateľa alebo správcu na overenie vášho účtu</span><span class="sxs-lookup"><span data-stu-id="9a259-138">Contributor or Administrator permissions to authenticate your account</span></span>

## <a name="connect-via-the-dynamics-365-customer-insights-connector"></a><span data-ttu-id="9a259-139">Pripojenie cez konektor Dynamics 365 Customer Insights</span><span class="sxs-lookup"><span data-stu-id="9a259-139">Connect via the Dynamics 365 Customer Insights connector</span></span>

<span data-ttu-id="9a259-140">Rozhranie API v reálnom čase môže prijímať údaje z vyhradeného konektora Power Platform, konektora [Dynamics 365 Customer Insights](https://docs.microsoft.com/connectors/customerinsights/), bez potreby písania a nasadenia akéhokoľvek kódu.</span><span class="sxs-lookup"><span data-stu-id="9a259-140">The real-time API can ingest data from a dedicated Power Platform connector, the [Dynamics 365 Customer Insights connector](https://docs.microsoft.com/connectors/customerinsights/), without the need to write and deploy any code.</span></span>    
<span data-ttu-id="9a259-141">Konektor môže vykonávať rovnaké akcie v reálnom čase ako API.</span><span class="sxs-lookup"><span data-stu-id="9a259-141">The connector can do the same real-time actions as the API.</span></span> <span data-ttu-id="9a259-142">Pre prémiové konektory potrebujete platnú licenciu.</span><span class="sxs-lookup"><span data-stu-id="9a259-142">You need a valid license for premium connectors.</span></span> <span data-ttu-id="9a259-143">Ďalšie informácie nájdete v časti [Najčastejšie otázky o licenciách k Power Apps a Power Automate](https://docs.microsoft.com/power-platform/admin/powerapps-flow-licensing-faq).</span><span class="sxs-lookup"><span data-stu-id="9a259-143">For more information, see [Power Apps and Power Automate licensing FAQs](https://docs.microsoft.com/power-platform/admin/powerapps-flow-licensing-faq).</span></span>

- <span data-ttu-id="9a259-144">Power Platform [Power Apps a/alebo Power Automate](https://docs.microsoft.com/connectors/)</span><span class="sxs-lookup"><span data-stu-id="9a259-144">Power Platform [Power Apps and/or Power Automate](https://docs.microsoft.com/connectors/)</span></span>
- <span data-ttu-id="9a259-145">[Logické aplikácie platformy Azure](https://docs.microsoft.com/azure/connectors/apis-list)</span><span class="sxs-lookup"><span data-stu-id="9a259-145">Azure [Logic Apps](https://docs.microsoft.com/azure/connectors/apis-list)</span></span>

<span data-ttu-id="9a259-146">Podrobnosti o vytváraní postupov nájdete v [dokumentácii Power Automate](https://docs.microsoft.com/power-automate/).</span><span class="sxs-lookup"><span data-stu-id="9a259-146">For details about creating flows, see the [Power Automate documentation](https://docs.microsoft.com/power-automate/).</span></span>

## <a name="connect-directly-to-the-real-time-api"></a><span data-ttu-id="9a259-147">Priame pripojenie k API v reálnom čase</span><span class="sxs-lookup"><span data-stu-id="9a259-147">Connect directly to the real-time API</span></span>

<span data-ttu-id="9a259-148">Funkcie v reálnom čase môžete využiť vytvorením vlastného kanála a priamym pripojením k rozhraniu API v reálnom čase.</span><span class="sxs-lookup"><span data-stu-id="9a259-148">You can use the real-time capabilities by building your own pipeline and connecting directly to the real-time API.</span></span>    
<span data-ttu-id="9a259-149">Aktivitu môžete uverejniť vo formáte zdrojového systému alebo vo formáte UnifiedActivity.</span><span class="sxs-lookup"><span data-stu-id="9a259-149">You can post an activity in the format of your source system or in the UnifiedActivity format.</span></span> <span data-ttu-id="9a259-150">Získajte formát pomocou volania rozhrania API na /api/instances/{instanceId}/manage/entities/UnifiedActivity.</span><span class="sxs-lookup"><span data-stu-id="9a259-150">Get the format by making an API call to /api/instances/{instanceId}/manage/entities/UnifiedActivity.</span></span>

<span data-ttu-id="9a259-151">Podrobnosti o tomto API vrátane parametrov a odpovedí nájdete v časti **EntityData** v [referenčnej príručke rozhraní API pre Customer Insights](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights).</span><span class="sxs-lookup"><span data-stu-id="9a259-151">Details of this API, including parameters and responses, can be found in the **EntityData** section on the [Customer Insights APIs reference](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights).</span></span> <span data-ttu-id="9a259-152">Ďalšie informácie nájdete v téme [Práca s rozhraniami API pre Customer Insights](apis.md).</span><span class="sxs-lookup"><span data-stu-id="9a259-152">For more information, see [Work with Customer Insights APIs](apis.md).</span></span>

## <a name="understand-your-real-time-usage-with-telemetry"></a><span data-ttu-id="9a259-153">Získajte informácie o svojom využití v reálnom čase pomocou telemetrie</span><span class="sxs-lookup"><span data-stu-id="9a259-153">Understand your real-time usage with telemetry</span></span>

<span data-ttu-id="9a259-154">Získajte prehľad o objeme požiadaviek na API v reálnom čase a informácie o problémoch, s ktorými sa systém môže stretnúť.</span><span class="sxs-lookup"><span data-stu-id="9a259-154">Get an overview of the volume of requests to the real-time API and information about issues the system may encounter.</span></span> <span data-ttu-id="9a259-155">Môžete [pristupovať k telemetrii v reálnom čase](system.md#api-usage-tab).</span><span class="sxs-lookup"><span data-stu-id="9a259-155">You can [access the real-time telemetry](system.md#api-usage-tab).</span></span> 


[!INCLUDE[footer-include](../includes/footer-banner.md)]