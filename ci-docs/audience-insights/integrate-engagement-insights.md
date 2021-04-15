---
title: Integrácia webových údajov z prehľadov o interakcii s prehľadmi cieľových skupín
description: Prineste webové informácie o zákazníkoch z prehľadov o interakcii do prehľadov cieľových skupín.
ms.date: 12/17/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 14ebff30d3ec7fc52dca6f86136309a3f454fa27
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597484"
---
# <a name="integrate-web-data-from-engagement-insights-with-audience-insights"></a><span data-ttu-id="a024e-103">Integrácia webových údajov z prehľadov o interakcii s prehľadmi cieľových skupín</span><span class="sxs-lookup"><span data-stu-id="a024e-103">Integrate web data from engagement insights with audience insights</span></span>

<span data-ttu-id="a024e-104">Zákazníci často vykonávajú svoje každodenné transakcie online pomocou webových stránok.</span><span class="sxs-lookup"><span data-stu-id="a024e-104">Customers often do their day to day transactions online using web sites.</span></span> <span data-ttu-id="a024e-105">Funkcia získať prehľady o interakcii v Dynamics 365 Customer Insights je užitočné riešenie na integráciu webových údajov ako zdroja.</span><span class="sxs-lookup"><span data-stu-id="a024e-105">The engagement insights capability in Dynamics 365 Customer Insights is a handy solution to integrate web data as a source.</span></span> <span data-ttu-id="a024e-106">Okrem transakčných, demografických údajov alebo údajov o správaní vidíme aktivity na webe v zjednotených zákazníckych profiloch.</span><span class="sxs-lookup"><span data-stu-id="a024e-106">In addition to transactional, demographic, or behavioral data we can see activities on the web in unified customer profiles.</span></span> <span data-ttu-id="a024e-107">Tento profil môžeme použiť na získanie ďalších prehľadov, ako sú segmenty, miery alebo predikcie aktivácie cieľovej skupiny.</span><span class="sxs-lookup"><span data-stu-id="a024e-107">We can use this profile to gain additional insights like segments, measures, or predictions for audience activation.</span></span>

<span data-ttu-id="a024e-108">Tento článok popisuje kroky, pomocou ktorých je možné preniesť údaje o aktivitách na webe vašich zákazníkov z prehľadov o interakcii do vášho existujúceho prostredia prehľadov cieľových skupín.</span><span class="sxs-lookup"><span data-stu-id="a024e-108">This article describes the steps to bring your customers’ web activity data from engagement insights into your existing audience insights environment.</span></span>

<span data-ttu-id="a024e-109">V tomto príklade predpokladáme prostredie, ktoré obsahuje zjednotené profily zákazníkov.</span><span class="sxs-lookup"><span data-stu-id="a024e-109">In this example, we assume an environment that contains unified customer profiles.</span></span> <span data-ttu-id="a024e-110">Profily boli zjednotené so zdrojmi z prieskumov, maloobchodného predaja a systému predaja lístkov.</span><span class="sxs-lookup"><span data-stu-id="a024e-110">The profiles were unified with sources from surveys, retail sales, and a ticketing system.</span></span> <span data-ttu-id="a024e-111">Ukazuje tiež súvisiace aktivity zákazníkov.</span><span class="sxs-lookup"><span data-stu-id="a024e-111">It also shows the related activities of the customers.</span></span> 

<span data-ttu-id="a024e-112">Teraz by sme chceli vedieť, či zákazník navštívi naše webové vlastnosti a porozumie ich aktivitám.</span><span class="sxs-lookup"><span data-stu-id="a024e-112">We now want to know if a customer visits our web properties and understand their activities.</span></span> <span data-ttu-id="a024e-113">Medzi aktivity patria napríklad navštívené webové stránky alebo zobrazené stránky produktov z odkazu prijatého v e-maile.</span><span class="sxs-lookup"><span data-stu-id="a024e-113">Activities include, for example, visited websites or viewed product pages from a link received in an email.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="a024e-114">Predpoklady</span><span class="sxs-lookup"><span data-stu-id="a024e-114">Prerequisites</span></span>

<span data-ttu-id="a024e-115">Ak chcete integrovať údaje z prehľadov o interakcii, je potrebné splniť niekoľko predpokladov:</span><span class="sxs-lookup"><span data-stu-id="a024e-115">To integrate data from engagement insights, a few prerequisites need to be met:</span></span> 

- <span data-ttu-id="a024e-116">Integrovať súpravu SDK prehľadov o interakcii so svojím webom.</span><span class="sxs-lookup"><span data-stu-id="a024e-116">Integrate the engagement insights SDK with your website.</span></span> <span data-ttu-id="a024e-117">Ďalšie informácie nájdete v téme [Začíname s webovou súpravou SDK](../engagement-insights/instrument-website.md).</span><span class="sxs-lookup"><span data-stu-id="a024e-117">For more information, see [Get started with the web SDK](../engagement-insights/instrument-website.md).</span></span>
- <span data-ttu-id="a024e-118">Export webových udalostí z prehľadov o interakcii vyžaduje prístup k účtu úložiska ADLS Gen 2, ktorý sa použije na príjem údajov z webových udalostí do prehľadov cieľových skupín.</span><span class="sxs-lookup"><span data-stu-id="a024e-118">Exporting web events from engagement insights requires access to an ADLS Gen 2 storage account that will be used to ingest the web events data to audience insights.</span></span> <span data-ttu-id="a024e-119">Ďalšie informácie nájdete v téme [Export udalostí](../engagement-insights/export-events.md).</span><span class="sxs-lookup"><span data-stu-id="a024e-119">For more information, see [Export events](../engagement-insights/export-events.md).</span></span>

## <a name="configure-refined-events-in-engagement-insights"></a><span data-ttu-id="a024e-120">Konfigurácia prepracovaných udalostí v prehľadoch o interakcii</span><span class="sxs-lookup"><span data-stu-id="a024e-120">Configure refined events in engagement insights</span></span>

<span data-ttu-id="a024e-121">Potom, čo správca vybavil web pomocou súpravy SDK prehľadov o interakcii, *základné udalosti* sa zhromažďujú, keď si používateľ prezrie webovú stránku alebo niekde klikne.</span><span class="sxs-lookup"><span data-stu-id="a024e-121">After an administrator instrumented a website with the engagement insights SDK, *base events* are gathered when a user views a web page or clicks somewhere.</span></span> <span data-ttu-id="a024e-122">Základné udalosti zvyknú obsahovať početné podrobnosti.</span><span class="sxs-lookup"><span data-stu-id="a024e-122">Base events tend to contain numerous details.</span></span> <span data-ttu-id="a024e-123">V závislosti od vášho prípadu použitia potrebujete iba podmnožinu údajov v základnej udalosti.</span><span class="sxs-lookup"><span data-stu-id="a024e-123">Depending on your use case, you only need a subset of the data in a base event.</span></span> <span data-ttu-id="a024e-124">Prehľady interakcií vám umožňujú vytvárať *prepracované udalosti* ktoré obsahujú iba vlastnosti základnej udalosti, ktorú vyberiete.</span><span class="sxs-lookup"><span data-stu-id="a024e-124">Engagement insights let you create *refined events* that contain only the properties of a base event that you select.</span></span>     

<span data-ttu-id="a024e-125">Viac informácií nájdete v časti [Vytváranie a úprava spresnených udalostí](../engagement-insights/refined-events.md).</span><span class="sxs-lookup"><span data-stu-id="a024e-125">For more information, see [Create and modify refined events](../engagement-insights/refined-events.md).</span></span>

<span data-ttu-id="a024e-126">Čo treba zohľadniť pri vytváraní spresnených udalostí:</span><span class="sxs-lookup"><span data-stu-id="a024e-126">Considerations when creating refined events:</span></span> 

- <span data-ttu-id="a024e-127">Zadajte zmysluplný názov pre spresnenú udalosť.</span><span class="sxs-lookup"><span data-stu-id="a024e-127">Provide a meaningful name for the refined event.</span></span> <span data-ttu-id="a024e-128">Používa sa ako názov aktivity v prehľadoch cieľovej skupiny.</span><span class="sxs-lookup"><span data-stu-id="a024e-128">It's be used as an activity name in audience insights.</span></span>
- <span data-ttu-id="a024e-129">Vyberte aspoň nasledujúce vlastnosti na vytvorenie aktivity v prehľadoch cieľovej skupiny:</span><span class="sxs-lookup"><span data-stu-id="a024e-129">Select at least the following properties to create an activity in audience insights:</span></span> 
    - <span data-ttu-id="a024e-130">Signal.Action.Name – s uvedením podrobností aktivity</span><span class="sxs-lookup"><span data-stu-id="a024e-130">Signal.Action.Name - indicating the activity details</span></span>
    - <span data-ttu-id="a024e-131">Signal.User.Id – slúži na mapovanie s ID zákazníka</span><span class="sxs-lookup"><span data-stu-id="a024e-131">Signal.User.Id - used to map with the customer ID</span></span>
    - <span data-ttu-id="a024e-132">Signal.View.Uri – používa sa ako webová adresa ako základ pre segmenty alebo miery</span><span class="sxs-lookup"><span data-stu-id="a024e-132">Signal.View.Uri - used as a web address as a basis for segments or measures</span></span>
    - <span data-ttu-id="a024e-133">Signal.Export.Id – používa sa ako primárny kľúč pre udalosti</span><span class="sxs-lookup"><span data-stu-id="a024e-133">Signal.Export.Id - to use as a primary key for events</span></span> <!-- system generated, do we need to list?-->
    - <span data-ttu-id="a024e-134">Signal.Timestamp – na určenie dátumu a času aktivity</span><span class="sxs-lookup"><span data-stu-id="a024e-134">Signal.Timestamp - to determine the date and time for the activity</span></span>

<span data-ttu-id="a024e-135">Vyberte filtre a zamerajte sa na udalosti a stránky, ktoré sú dôležité pre váš prípad použitia.</span><span class="sxs-lookup"><span data-stu-id="a024e-135">Select the filters to focus on the events and pages that matter for your use case.</span></span> <span data-ttu-id="a024e-136">V tomto príklade použijeme názov akcie „Zvýšenie úrovne e-mailu“.</span><span class="sxs-lookup"><span data-stu-id="a024e-136">In this example, we'll use the "Email promotion" action name.</span></span>

## <a name="export-the-refined-web-events"></a><span data-ttu-id="a024e-137">Export spresnených webových udalostí</span><span class="sxs-lookup"><span data-stu-id="a024e-137">Export the Refined Web Events</span></span> 

<span data-ttu-id="a024e-138">Po definovaní spresnenej udalosti musíte nakonfigurovať export údajov udalosti do Azure Data Lake Storage, ktoré je možné nastaviť ako zdroj údajov na príjem prehľadov cieľovej skupiny.</span><span class="sxs-lookup"><span data-stu-id="a024e-138">After defining the refined event is defined, you have to configure the export of the event data to an Azure Data Lake Storage, that can be set as a data source for ingestion in audience insights.</span></span> <span data-ttu-id="a024e-139">Exporty prebiehajú neustále, keď udalosti prúdia z webu.</span><span class="sxs-lookup"><span data-stu-id="a024e-139">Exports happen constantly as the events flow from the web property.</span></span>

<span data-ttu-id="a024e-140">Ďalšie informácie nájdete v téme [Export udalostí](../engagement-insights/export-events.md).</span><span class="sxs-lookup"><span data-stu-id="a024e-140">For more information, see [Export events](../engagement-insights/export-events.md).</span></span>

## <a name="ingest-event-data-to-audience-insights"></a><span data-ttu-id="a024e-141">Príjem údajov udalosti do prehľadov cieľových skupín</span><span class="sxs-lookup"><span data-stu-id="a024e-141">Ingest event data to audience insights</span></span>

<span data-ttu-id="a024e-142">Teraz, keď ste definovali prepracovanú udalosť a nakonfigurovali jej export, pokračujeme k prijímaniu údajov do prehľadov publika.</span><span class="sxs-lookup"><span data-stu-id="a024e-142">Now that you have defined the refined event and configured its export, we move on to ingesting the data to audience insights.</span></span> <span data-ttu-id="a024e-143">Musíte vytvoriť nový zdroj údajov na základe priečinka Common Data Model.</span><span class="sxs-lookup"><span data-stu-id="a024e-143">You need to create a new data source based on a Common Data Model folder.</span></span> <span data-ttu-id="a024e-144">Zadajte podrobnosti o účte úložiska, do ktorého udalosti exportujete.</span><span class="sxs-lookup"><span data-stu-id="a024e-144">Enter the details for the storage account you export the events to.</span></span> <span data-ttu-id="a024e-145">V súbore *default.cdm.json* vyberte prepracovanú udalosť, ktorú chcete prijať, a vytvorte entitu v prehľadoch cieľových skupín.</span><span class="sxs-lookup"><span data-stu-id="a024e-145">In the *default.cdm.json* file, select the refined event to ingest and create the entity in audience insights.</span></span>

<span data-ttu-id="a024e-146">Viac informácií nájdete v časti [Pripojenie k priečinku Common Data Model pomocou účtu Azure Data Lake](connect-common-data-model.md)</span><span class="sxs-lookup"><span data-stu-id="a024e-146">For more information, see [Connect to a Common Data Model folder using an Azure Data Lake account](connect-common-data-model.md)</span></span>


## <a name="relate-refined-event-data-as-an-activity-of-a-customer-profile"></a><span data-ttu-id="a024e-147">Prepojenie prepracovaných údajov udalostí ako aktivity v profile zákazníka</span><span class="sxs-lookup"><span data-stu-id="a024e-147">Relate refined event data as an activity of a customer profile</span></span>

<span data-ttu-id="a024e-148">Po dokončení príjmu entity môžete nakonfigurovať aktivitu pre profil zákazníka.</span><span class="sxs-lookup"><span data-stu-id="a024e-148">After completing the entity ingestion, you can configure the activity for the customer profile.</span></span>

<span data-ttu-id="a024e-149">Ďalšie informácie nájdete v článku [Aktivity zákazníka](activities.md).</span><span class="sxs-lookup"><span data-stu-id="a024e-149">For more information, see [Customer activities](activities.md).</span></span>

:::image type="content" source="media/web-event-activity.png" alt-text="Stránka Aktivity s rozbaleným panelom Upraviť aktivitu a vyplnenými poľami.":::

<span data-ttu-id="a024e-151">Nakonfigurujte novú aktivitu pomocou nasledujúceho mapovania:</span><span class="sxs-lookup"><span data-stu-id="a024e-151">Configure the new activity with the following mapping:</span></span> 

- <span data-ttu-id="a024e-152">**Primárny kľúč:** Signal.Export.Id, jedinečný identifikátor, ktorý je k dispozícii pre každý záznam udalosti v prehľadoch interakcií.</span><span class="sxs-lookup"><span data-stu-id="a024e-152">**Primary Key:** Signal.Export.Id, a unique ID that is available for every event record in engagement insights.</span></span> <span data-ttu-id="a024e-153">Táto vlastnosť sa generuje automaticky.</span><span class="sxs-lookup"><span data-stu-id="a024e-153">This property is automatically generated.</span></span>

- <span data-ttu-id="a024e-154">**Časová pečiatka:** Signal.Timestamp vo vlastnosti udalosti.</span><span class="sxs-lookup"><span data-stu-id="a024e-154">**Timestamp:** Signal.Timestamp in the event property.</span></span>

- <span data-ttu-id="a024e-155">**Udalosť** Signal.Name, názov udalosti, ktorý chcete sledovať.</span><span class="sxs-lookup"><span data-stu-id="a024e-155">**Event:** Signal.Name, the event name that you want to track.</span></span>

- <span data-ttu-id="a024e-156">**Webová adresa:** Signal.View.Uri s odkazom na URI stránky, ktorá vytvorila udalosť.</span><span class="sxs-lookup"><span data-stu-id="a024e-156">**Web address:** Signal.View.Uri referring to the uri of the page that created the event.</span></span>

- <span data-ttu-id="a024e-157">**Detaily:** Signal.Action.Name na zastupovanie informácií, ktoré sa dajú priradiť k udalosti.</span><span class="sxs-lookup"><span data-stu-id="a024e-157">**Details:** Signal.Action.Name to represent the information to associate with the event.</span></span> <span data-ttu-id="a024e-158">Vybraná vlastnosť v tomto prípade indikuje, že udalosť je určená na zvýšenie úrovne e-mailov.</span><span class="sxs-lookup"><span data-stu-id="a024e-158">The selected property in this case indicates that the event is for email promotion.</span></span>

- <span data-ttu-id="a024e-159">**Typ aktivity:** V tomto príklade si vyberieme typ existujúcej aktivity WebLog.</span><span class="sxs-lookup"><span data-stu-id="a024e-159">**Activity type:** In this example, we choose the exsting activity type WebLog.</span></span> <span data-ttu-id="a024e-160">Tento výber ponúka užitočnú možnosť filtrovania na spustenie modelov predikcie alebo na vytvorenie segmentov na základe tohto typu aktivity.</span><span class="sxs-lookup"><span data-stu-id="a024e-160">This selection is a useful filter option to run prediction models or create segments based on this activity type.</span></span>

- <span data-ttu-id="a024e-161">**Nastavenie vzťahu:** Toto dôležité nastavenie viaže aktivitu na existujúce profily zákazníkov.</span><span class="sxs-lookup"><span data-stu-id="a024e-161">**Set up relationship:** This important setting ties the activity to existing customer profiles.</span></span> <span data-ttu-id="a024e-162">**Signal.User.Id** je identifikátor nakonfigurovaný v súprave SDK, ktorý sa má zhromažďovať, a ktorý sa týka ID používateľa v iných zdrojoch údajov, ktoré sú nakonfigurované v prehľadoch cieľovej skupiny.</span><span class="sxs-lookup"><span data-stu-id="a024e-162">**Signal.User.Id** is the identifier configured in the SDK to be collected and that relates to the user ID in other data sources that are configured in audience insights.</span></span> <span data-ttu-id="a024e-163">V tomto príklade konfigurujeme vzťah medzi Signal.User.Id a RetailCustomers:CustomerRetailId, čo je primárny kľúč, ktorý bol definovaný v kroku mapy procesu zjednotenia údajov.</span><span class="sxs-lookup"><span data-stu-id="a024e-163">In this example, we configure the relationship between Signal.User.Id and RetailCustomers:CustomerRetailId, which is the primary key that was deinfed in the map step of the data unification process.</span></span>


<span data-ttu-id="a024e-164">Po spracovaní aktivít môžete skontrolovať záznamy zákazníkov a otvoriť kartu zákazníka, aby ste si na časovej osi mohli pozrieť prehľady z prehľadov o interakcii.</span><span class="sxs-lookup"><span data-stu-id="a024e-164">After processing the activities, you can review customer records and open a customer card to see activities from engagement insights in the timeline.</span></span> 

> [!TIP]
> <span data-ttu-id="a024e-165">Ak chcete nájsť ID zákazníka, ktorý má aktivitu v prehľadoch o interakcii, prejdite na **Entity** a zobrazte údaje pre entitu UnifiedActivity.</span><span class="sxs-lookup"><span data-stu-id="a024e-165">To find a customer id that has an engagement insights activity, go to **Entities** and preview the data for the UnifiedActivity entity.</span></span> <span data-ttu-id="a024e-166">ActivityTypeDisplay = WebLog obsahuje aktivitu prehľadov o interakcii nakonfigurovanú v príklade vyššie.</span><span class="sxs-lookup"><span data-stu-id="a024e-166">ActivityTypeDisplay = WebLog contain the engagement insights activity configured in the example above.</span></span> <span data-ttu-id="a024e-167">Skopírujte ID zákazníka pre jeden z týchto záznamov a pre toto ID na stránku **Zákazníci**.</span><span class="sxs-lookup"><span data-stu-id="a024e-167">Copy the customer ID for one of those records and for that ID on the **Customers** page.</span></span>

## <a name="next-steps"></a><span data-ttu-id="a024e-168">Ďalšie kroky</span><span class="sxs-lookup"><span data-stu-id="a024e-168">Next Steps</span></span>

<span data-ttu-id="a024e-169">Teraz môžete vytvárať [segmenty](segments.md), [miery](measures.md) a [predikcie](predictions.md) a vytvoriť zmysluplné spojenie so svojimi zákazníkmi.</span><span class="sxs-lookup"><span data-stu-id="a024e-169">You can now create [segments](segments.md), [measures](measures.md), and [predictions](predictions.md) to make a meaningful connection with your customers.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]