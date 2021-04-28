---
title: Používanie zdrojov údajov na príjem údajov
description: Prečítajte si, ako importovať údaje z rôznych zdrojov.
ms.date: 04/12/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 0fc13d3ac0a5176637b6fe481dabe0b2aec11649
ms.sourcegitcommit: d89b19b2a3497722b78362aeee688ae7e94915d9
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 04/13/2021
ms.locfileid: "5887913"
---
# <a name="data-sources-overview"></a><span data-ttu-id="66e0a-103">Prehľad zdrojov údajov</span><span class="sxs-lookup"><span data-stu-id="66e0a-103">Data sources overview</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="66e0a-104">Funkcia prehľadov cieľových skupín v službe Dynamics 365 Customer Insights sa pripája sa k údajom zo širokej množiny zdrojov.</span><span class="sxs-lookup"><span data-stu-id="66e0a-104">The audience insights capability in Dynamics 365 Customer Insights connects to data from a broad set of sources.</span></span> <span data-ttu-id="66e0a-105">Pripojenie k zdroju údajov sa často označuje ako proces *prijímania údajov*.</span><span class="sxs-lookup"><span data-stu-id="66e0a-105">Connecting to a data source is often referred to as the process of *data ingestion*.</span></span> <span data-ttu-id="66e0a-106">Po prijatí údajov ich môžete [zjednotiť](data-unification.md) a podniknúť s nimi kroky.</span><span class="sxs-lookup"><span data-stu-id="66e0a-106">After ingesting the data, you can [unify](data-unification.md) and take action on it.</span></span>

## <a name="add-a-data-source"></a><span data-ttu-id="66e0a-107">Pridať zdroj údajov</span><span class="sxs-lookup"><span data-stu-id="66e0a-107">Add a data source</span></span>

<span data-ttu-id="66e0a-108">Prečítajte si podrobné články o tom, ako pridať zdroj údajov, podľa toho, ktorú možnosť si vyberiete.</span><span class="sxs-lookup"><span data-stu-id="66e0a-108">Refer to the detailed articles on how to add a data source, depending on which option you choose.</span></span>

<span data-ttu-id="66e0a-109">Zdroj údajov môžete pridať tromi hlavnými spôsobmi:</span><span class="sxs-lookup"><span data-stu-id="66e0a-109">You can add a data source in three main ways:</span></span>

- [<span data-ttu-id="66e0a-110">Prostredníctvom množstva konektorov Power Query</span><span class="sxs-lookup"><span data-stu-id="66e0a-110">Through dozens of Power Query connectors</span></span>](connect-power-query.md)
- [<span data-ttu-id="66e0a-111">Z priečinka Common Data Model</span><span class="sxs-lookup"><span data-stu-id="66e0a-111">From a Common Data Model folder</span></span>](connect-common-data-model.md)
- [<span data-ttu-id="66e0a-112">Z jazera Common Data Service</span><span class="sxs-lookup"><span data-stu-id="66e0a-112">From your own Common Data Service lake</span></span>](connect-common-data-service-lake.md)

## <a name="add-data-from-on-premises-data-sources"></a><span data-ttu-id="66e0a-113">Pridajte údaje z lokálny zdrojov údajov</span><span class="sxs-lookup"><span data-stu-id="66e0a-113">Add data from on-premises data sources</span></span>

<span data-ttu-id="66e0a-114">Na základe je podporované prijímanie údajov z lokálnych zdrojov údajov v prehľadoch cieľovej skupiny tokov údajov Power Platform.</span><span class="sxs-lookup"><span data-stu-id="66e0a-114">Ingesting data from on-premises data sources in Audience Insights is supported based on Power Platform dataflows.</span></span> <span data-ttu-id="66e0a-115">Toky údajov je možné v nástroji Customer Insights povoliť používateľom [poskytuje adresu URL prostredia Microsoft Dataverse](manage-environments.md#create-an-environment-in-an-existing-organization) pri nastavovaní prostredia.</span><span class="sxs-lookup"><span data-stu-id="66e0a-115">Dataflows can be enabled in Customer Insights by [providing the Microsoft Dataverse environment URL](manage-environments.md#create-an-environment-in-an-existing-organization) when setting up the environment.</span></span>

<span data-ttu-id="66e0a-116">Zdroje údajov, ktoré sa predvolene vytvoria po priradení a prostredí Dataverse s nástrojom Customer Insights [Toky údajov Power Platform](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365).</span><span class="sxs-lookup"><span data-stu-id="66e0a-116">Data sources that are created after associating a Dataverse environment with Customer Insights will use [Power Platform dataflows](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) by default.</span></span> <span data-ttu-id="66e0a-117">Dátové toky podporujú lokálne pripojenie pomocou brány údajov.</span><span class="sxs-lookup"><span data-stu-id="66e0a-117">Dataflows support on-prem connectivity using the data gateways.</span></span> <span data-ttu-id="66e0a-118">Odstrániť a znovu vytvoriť zdroje údajov, ktoré existovali pred prostredím Dataverse bolo spojené s používaním lokálnych dátových brán.</span><span class="sxs-lookup"><span data-stu-id="66e0a-118">Remove and recreate data sources that existed before a Dataverse environment was associated to use the on-premises data gateways.</span></span>

<span data-ttu-id="66e0a-119">Dátové brány z existujúceho prostredia Power BI alebo Power Apps bude viditeľné a môžete ho znova použiť v nástroji Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="66e0a-119">Data gateways from an existing Power BI or Power Apps environment will be visible and you can reuse in Customer Insights.</span></span> <span data-ttu-id="66e0a-120">Na stránke zdrojov údajov sú zobrazené odkazy, pomocou ktorých môžete prejsť do prostredia Power Platform, kde môžete zobraziť a nakonfigurovať lokálne dátové brány.</span><span class="sxs-lookup"><span data-stu-id="66e0a-120">The data sources page shows links to go the Power Platform environment where you can view and configure on-premises data gateways.</span></span>

:::image type="content" source="media/data-sources-onpremises-gateways.png" alt-text="Snímka obrazovky zo stránky zdrojov údajov zobrazujúci odkazy smerujúce do prostredia Power Platform.":::

## <a name="review-ingested-data"></a><span data-ttu-id="66e0a-122">Kontrola prijatých údajov</span><span class="sxs-lookup"><span data-stu-id="66e0a-122">Review ingested data</span></span>

<span data-ttu-id="66e0a-123">Uvidíte názov každého prijatého zdroj údajov, jeho stav a poslednú aktualizáciu údajov pre tento zdroj.</span><span class="sxs-lookup"><span data-stu-id="66e0a-123">You'll see the name of each ingested data source, its status, and the last time the data was refreshed for that source.</span></span> <span data-ttu-id="66e0a-124">Zoznam zdrojov údajov môžete zoradiť podľa každého stĺpca.</span><span class="sxs-lookup"><span data-stu-id="66e0a-124">You can sort the list of data sources by every column.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="66e0a-125">![Pridaný zdroj údajov](media/configure-data-datasource-added.png "Pridaný zdroj údajov")</span><span class="sxs-lookup"><span data-stu-id="66e0a-125">![Data source added](media/configure-data-datasource-added.png "Data source added")</span></span>

|<span data-ttu-id="66e0a-126">Status</span><span class="sxs-lookup"><span data-stu-id="66e0a-126">Status</span></span>  |<span data-ttu-id="66e0a-127">Popis</span><span class="sxs-lookup"><span data-stu-id="66e0a-127">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="66e0a-128">Úspešné</span><span class="sxs-lookup"><span data-stu-id="66e0a-128">Successful</span></span>   |<span data-ttu-id="66e0a-129">Zdroj údajov bol úspešne prijatý, ak je v stĺpci **Obnovené** uvedený čas.</span><span class="sxs-lookup"><span data-stu-id="66e0a-129">Data source was successfully ingested if a time is mentioned in the **Refreshed** column.</span></span>
|<span data-ttu-id="66e0a-130">Nespustené</span><span class="sxs-lookup"><span data-stu-id="66e0a-130">Not started</span></span>   |<span data-ttu-id="66e0a-131">Zdroj údajov zatiaľ nemá žiadne prijaté údaje alebo je stále v režime konceptu.</span><span class="sxs-lookup"><span data-stu-id="66e0a-131">The data source has no data ingested yet or still in draft mode.</span></span>         |
|<span data-ttu-id="66e0a-132">Obnovuje sa</span><span class="sxs-lookup"><span data-stu-id="66e0a-132">Refreshing</span></span>    |<span data-ttu-id="66e0a-133">Prebieha prijímanie údajov.</span><span class="sxs-lookup"><span data-stu-id="66e0a-133">Data ingestion is in progress.</span></span> <span data-ttu-id="66e0a-134">Túto operáciu môžete zrušiť tak, že v stĺpci **Akcie** vyberiete **Zastaviť obnovovanie**.</span><span class="sxs-lookup"><span data-stu-id="66e0a-134">You can cancel this operation by selecting **Stop refreshing** in the **Actions** column.</span></span> <span data-ttu-id="66e0a-135">Zastavenie obnovovania zdroja údajov sa obnoví do posledného stavu obnovenia.</span><span class="sxs-lookup"><span data-stu-id="66e0a-135">Stopping the refresh of a data source will revert it to its last refresh state.</span></span>       |
|<span data-ttu-id="66e0a-136">Zlyhalo</span><span class="sxs-lookup"><span data-stu-id="66e0a-136">Failed</span></span>     |<span data-ttu-id="66e0a-137">Pri prijímaní údajov nastali chyby.</span><span class="sxs-lookup"><span data-stu-id="66e0a-137">Data ingestion ran into errors.</span></span>         |

<span data-ttu-id="66e0a-138">Vyberte hodnotu v stĺpci **Stav** ľubovoľného zdroja údajov, aby ste skontrolovali ďalšie podrobnosti.</span><span class="sxs-lookup"><span data-stu-id="66e0a-138">Select the value in the **Status** column of any data source to review more details.</span></span> <span data-ttu-id="66e0a-139">V table **Podrobnosti o postupe** rozbaľte **Zdroje údajov**.</span><span class="sxs-lookup"><span data-stu-id="66e0a-139">In the **Progress details** pane, expand **Data sources**.</span></span> <span data-ttu-id="66e0a-140">Výberom položky **Zobraziť podrobnosti** zobrazíte viac informácií o stave obnovenia vrátane podrobností o chybách a následných aktualizáciách procesu.</span><span class="sxs-lookup"><span data-stu-id="66e0a-140">Select **See details** for more information about the refresh status, including error details and downstream process updates.</span></span>

<span data-ttu-id="66e0a-141">Načítanie údajov môže chvíľu trvať.</span><span class="sxs-lookup"><span data-stu-id="66e0a-141">Loading data can take some time.</span></span> <span data-ttu-id="66e0a-142">Po úspešnom obnovení môžu byť prijaté údaje preskúmané na stránke **Entity**.</span><span class="sxs-lookup"><span data-stu-id="66e0a-142">After a successful refresh, the ingested data can be reviewed from the **Entities** page.</span></span> <span data-ttu-id="66e0a-143">Ďalšie informácie nájdete v časti [Entity](entities.md).</span><span class="sxs-lookup"><span data-stu-id="66e0a-143">For more information, see [Entities](entities.md).</span></span>

## <a name="refresh-a-data-source"></a><span data-ttu-id="66e0a-144">Obnovte zdroj údajov</span><span class="sxs-lookup"><span data-stu-id="66e0a-144">Refresh a data source</span></span>

<span data-ttu-id="66e0a-145">Zdroje údajov je možné obnovovať automaticky alebo podľa potreby manuálne.</span><span class="sxs-lookup"><span data-stu-id="66e0a-145">Data sources can be refreshed on an automatic schedule or refreshed manually on demand.</span></span> 

<span data-ttu-id="66e0a-146">Prejdite na časť **Správca** > **Systém** > [**Plánovať**](system.md#schedule-tab) a nakonfigurujte plánované obnovenie všetkých vašich prijatých zdrojov údajov.</span><span class="sxs-lookup"><span data-stu-id="66e0a-146">Go to **Admin** > **System** > [**Schedule**](system.md#schedule-tab) to configure scheduled refreshes of all your ingested data sources.</span></span>

<span data-ttu-id="66e0a-147">Ak chcete obnoviť zdroj údajov na požiadanie, postupujte takto:</span><span class="sxs-lookup"><span data-stu-id="66e0a-147">To refresh a data source on demand, follow these steps:</span></span>

1. <span data-ttu-id="66e0a-148">V prehľadoch cieľových skupín prejdite na **Údaje** > **Zdroje údajov**</span><span class="sxs-lookup"><span data-stu-id="66e0a-148">In audience insights, go to **Data** > **Data sources**</span></span>

2. <span data-ttu-id="66e0a-149">Vyberte zvislé tri bodky vedľa zdroja údajov, ktorý chcete obnoviť, a vyberte položku **Obnoviť** z rozbaľovacieho zoznamu.</span><span class="sxs-lookup"><span data-stu-id="66e0a-149">Select the vertical ellipsis next to the data source you want to refresh and select **Refresh** from the drop-down list.</span></span>

3. <span data-ttu-id="66e0a-150">Zdroj údajov je teraz spustený na účely manuálneho obnovenia.</span><span class="sxs-lookup"><span data-stu-id="66e0a-150">The data source is now triggered for a manual refresh.</span></span> <span data-ttu-id="66e0a-151">Obnovením zdroja údajov sa aktualizuje schéma entity aj údaje pre všetky entity uvedené v zdroji údajov.</span><span class="sxs-lookup"><span data-stu-id="66e0a-151">Refreshing a data source will update both the entity schema and data for all the entities specified in the data source.</span></span>

4. <span data-ttu-id="66e0a-152">Vyberte položku **Zastaviť obnovovanie**, ak chcete zrušiť existujúce obnovenie a zdroj údajov sa vráti do posledného stavu obnovenia.</span><span class="sxs-lookup"><span data-stu-id="66e0a-152">Select **Stop refreshing** if you want to cancel an existing refresh and the data source will revert to its last refresh status.</span></span>

## <a name="delete-a-data-source"></a><span data-ttu-id="66e0a-153">Odstránenie zdroja údajov</span><span class="sxs-lookup"><span data-stu-id="66e0a-153">Delete a data source</span></span>

1. <span data-ttu-id="66e0a-154">V prehľadoch cieľových skupín prejdite na **Údaje** > **Zdroje údajov**.</span><span class="sxs-lookup"><span data-stu-id="66e0a-154">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="66e0a-155">Vyberte zvislé tri bodky vedľa zdroja údajov, ktorý chcete odstrániť, a vyberte **Odstrániť** z rozbaľovacej ponuky.</span><span class="sxs-lookup"><span data-stu-id="66e0a-155">Select the vertical ellipsis next to the data source you want to remove and select **Delete** from the drop-down menu.</span></span>

3. <span data-ttu-id="66e0a-156">Potvrďte odstránenie.</span><span class="sxs-lookup"><span data-stu-id="66e0a-156">Confirm your deletion.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
