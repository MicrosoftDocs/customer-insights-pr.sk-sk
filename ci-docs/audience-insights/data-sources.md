---
title: Používanie zdrojov údajov na príjem údajov
description: Prečítajte si, ako importovať údaje z rôznych zdrojov.
ms.date: 11/03/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: 68aa1b56fb634da80a0c64db72f778d57507104d
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269717"
---
# <a name="data-sources-overview"></a><span data-ttu-id="02170-103">Prehľad zdrojov údajov</span><span class="sxs-lookup"><span data-stu-id="02170-103">Data sources overview</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="02170-104">Funkcia prehľadov cieľových skupín v službe Dynamics 365 Customer Insights sa pripája sa k údajom zo širokej množiny zdrojov.</span><span class="sxs-lookup"><span data-stu-id="02170-104">The audience insights capability in Dynamics 365 Customer Insights connects to data from a broad set of sources.</span></span> <span data-ttu-id="02170-105">Pripojenie k zdroju údajov sa často označuje ako proces *prijímania údajov*.</span><span class="sxs-lookup"><span data-stu-id="02170-105">Connecting to a data source is often referred to as the process of *data ingestion*.</span></span> <span data-ttu-id="02170-106">Po prijatí údajov ich môžete [zjednotiť](data-unification.md) a podniknúť s nimi kroky.</span><span class="sxs-lookup"><span data-stu-id="02170-106">After ingesting the data, you can [unify](data-unification.md) and take action on it.</span></span>

## <a name="add-a-data-source"></a><span data-ttu-id="02170-107">Pridať zdroj údajov</span><span class="sxs-lookup"><span data-stu-id="02170-107">Add a data source</span></span>

<span data-ttu-id="02170-108">Prečítajte si podrobné články o tom, ako pridať zdroj údajov, podľa toho, ktorú možnosť si vyberiete.</span><span class="sxs-lookup"><span data-stu-id="02170-108">Refer to the detailed articles on how to add a data source, depending on which option you choose.</span></span>

<span data-ttu-id="02170-109">Zdroj údajov môžete pridať tromi hlavnými spôsobmi:</span><span class="sxs-lookup"><span data-stu-id="02170-109">You can add a data source in three main ways:</span></span>

- [<span data-ttu-id="02170-110">Prostredníctvom množstva konektorov Power Query</span><span class="sxs-lookup"><span data-stu-id="02170-110">Through dozens of Power Query connectors</span></span>](connect-power-query.md)
- [<span data-ttu-id="02170-111">Z priečinka Common Data Model</span><span class="sxs-lookup"><span data-stu-id="02170-111">From a Common Data Model folder</span></span>](connect-common-data-model.md)
- [<span data-ttu-id="02170-112">Z jazera Common Data Service</span><span class="sxs-lookup"><span data-stu-id="02170-112">From your own Common Data Service lake</span></span>](connect-common-data-service-lake.md)

> [!NOTE]
> <span data-ttu-id="02170-113">Zatiaľ nemôžete pridať údaje z lokálneho zdroja údajov.</span><span class="sxs-lookup"><span data-stu-id="02170-113">You can't add data from on-premises data sources yet.</span></span>

## <a name="review-ingested-data"></a><span data-ttu-id="02170-114">Kontrola prijatých údajov</span><span class="sxs-lookup"><span data-stu-id="02170-114">Review ingested data</span></span>

<span data-ttu-id="02170-115">Uvidíte názov každého prijatého zdroj údajov, jeho stav a poslednú aktualizáciu údajov pre tento zdroj.</span><span class="sxs-lookup"><span data-stu-id="02170-115">You'll see the name of each ingested data source, its status, and the last time the data was refreshed for that source.</span></span> <span data-ttu-id="02170-116">Zoznam zdrojov údajov môžete zoradiť podľa každého stĺpca.</span><span class="sxs-lookup"><span data-stu-id="02170-116">You can sort the list of data sources by every column.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="02170-117">![Pridaný zdroj údajov](media/configure-data-datasource-added.png "Pridaný zdroj údajov")</span><span class="sxs-lookup"><span data-stu-id="02170-117">![Data source added](media/configure-data-datasource-added.png "Data source added")</span></span>

|<span data-ttu-id="02170-118">Status</span><span class="sxs-lookup"><span data-stu-id="02170-118">Status</span></span>  |<span data-ttu-id="02170-119">Popis</span><span class="sxs-lookup"><span data-stu-id="02170-119">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="02170-120">Úspešné</span><span class="sxs-lookup"><span data-stu-id="02170-120">Successful</span></span>   |<span data-ttu-id="02170-121">Zdroj údajov bol úspešne prijatý, ak je v stĺpci **Obnovené** uvedený čas.</span><span class="sxs-lookup"><span data-stu-id="02170-121">Data source was successfully ingested if a time is mentioned in the **Refreshed** column.</span></span>
|<span data-ttu-id="02170-122">Nespustené</span><span class="sxs-lookup"><span data-stu-id="02170-122">Not started</span></span>   |<span data-ttu-id="02170-123">Zdroj údajov zatiaľ nemá žiadne prijaté údaje alebo je stále v režime konceptu.</span><span class="sxs-lookup"><span data-stu-id="02170-123">The data source has no data ingested yet or still in draft mode.</span></span>         |
|<span data-ttu-id="02170-124">Obnovuje sa</span><span class="sxs-lookup"><span data-stu-id="02170-124">Refreshing</span></span>    |<span data-ttu-id="02170-125">Prebieha prijímanie údajov.</span><span class="sxs-lookup"><span data-stu-id="02170-125">Data ingestion is in progress.</span></span> <span data-ttu-id="02170-126">Túto operáciu môžete zrušiť tak, že v stĺpci **Akcie** vyberiete **Zastaviť obnovovanie**.</span><span class="sxs-lookup"><span data-stu-id="02170-126">You can cancel this operation by selecting **Stop refreshing** in the **Actions** column.</span></span> <span data-ttu-id="02170-127">Zastavenie obnovovania zdroja údajov sa obnoví do posledného stavu obnovenia.</span><span class="sxs-lookup"><span data-stu-id="02170-127">Stopping the refresh of a data source will revert it to its last refresh state.</span></span>       |
|<span data-ttu-id="02170-128">Zlyhalo</span><span class="sxs-lookup"><span data-stu-id="02170-128">Failed</span></span>     |<span data-ttu-id="02170-129">Pri prijímaní údajov nastali chyby.</span><span class="sxs-lookup"><span data-stu-id="02170-129">Data ingestion ran into errors.</span></span>         |

<span data-ttu-id="02170-130">Vyberte hodnotu v stĺpci **Stav** ľubovoľného zdroja údajov, aby ste skontrolovali ďalšie podrobnosti.</span><span class="sxs-lookup"><span data-stu-id="02170-130">Select the value in the **Status** column of any data source to review more details.</span></span> <span data-ttu-id="02170-131">V table **Podrobnosti o postupe** rozbaľte **Zdroje údajov**.</span><span class="sxs-lookup"><span data-stu-id="02170-131">In the **Progress details** pane, expand **Data sources**.</span></span> <span data-ttu-id="02170-132">Výberom položky **Zobraziť podrobnosti** zobrazíte viac informácií o stave obnovenia vrátane podrobností o chybách a následných aktualizáciách procesu.</span><span class="sxs-lookup"><span data-stu-id="02170-132">Select **See details** for more information about the refresh status, including error details and downstream process updates.</span></span>

<span data-ttu-id="02170-133">Načítanie údajov môže chvíľu trvať.</span><span class="sxs-lookup"><span data-stu-id="02170-133">Loading data can take some time.</span></span> <span data-ttu-id="02170-134">Po úspešnom obnovení môžu byť prijaté údaje preskúmané na stránke **Entity**.</span><span class="sxs-lookup"><span data-stu-id="02170-134">After a successful refresh, the ingested data can be reviewed from the **Entities** page.</span></span> <span data-ttu-id="02170-135">Ďalšie informácie nájdete v časti [Entity](entities.md).</span><span class="sxs-lookup"><span data-stu-id="02170-135">For more information, see [Entities](entities.md).</span></span>

## <a name="refresh-a-data-source"></a><span data-ttu-id="02170-136">Obnovte zdroj údajov</span><span class="sxs-lookup"><span data-stu-id="02170-136">Refresh a data source</span></span>

<span data-ttu-id="02170-137">Zdroje údajov je možné obnovovať automaticky alebo podľa potreby manuálne.</span><span class="sxs-lookup"><span data-stu-id="02170-137">Data sources can be refreshed on an automatic schedule or refreshed manually on demand.</span></span> 

<span data-ttu-id="02170-138">Prejdite na časť **Správca** > **Systém** > [**Plánovať**](system.md#schedule-tab) a nakonfigurujte plánované obnovenie všetkých vašich prijatých zdrojov údajov.</span><span class="sxs-lookup"><span data-stu-id="02170-138">Go to **Admin** > **System** > [**Schedule**](system.md#schedule-tab) to configure scheduled refreshes of all your ingested data sources.</span></span>

<span data-ttu-id="02170-139">Ak chcete obnoviť zdroj údajov na požiadanie, postupujte takto:</span><span class="sxs-lookup"><span data-stu-id="02170-139">To refresh a data source on demand, follow these steps:</span></span>

1. <span data-ttu-id="02170-140">V prehľadoch cieľových skupín prejdite na **Údaje** > **Zdroje údajov**</span><span class="sxs-lookup"><span data-stu-id="02170-140">In audience insights, go to **Data** > **Data sources**</span></span>

2. <span data-ttu-id="02170-141">Vyberte zvislé tri bodky vedľa zdroja údajov, ktorý chcete obnoviť, a vyberte položku **Obnoviť** z rozbaľovacieho zoznamu.</span><span class="sxs-lookup"><span data-stu-id="02170-141">Select the vertical ellipsis next to the data source you want to refresh and select **Refresh** from the drop-down list.</span></span>

3. <span data-ttu-id="02170-142">Zdroj údajov je teraz spustený na účely manuálneho obnovenia.</span><span class="sxs-lookup"><span data-stu-id="02170-142">The data source is now triggered for a manual refresh.</span></span> <span data-ttu-id="02170-143">Obnovením zdroja údajov aktualizujete schému entít aj údaje pre všetky entity uvedené v zdroji údajov.</span><span class="sxs-lookup"><span data-stu-id="02170-143">Refreshing a data source will update both the entity schema as well as data for all the entities specified in the data source.</span></span>

4. <span data-ttu-id="02170-144">Vyberte položku **Zastaviť obnovovanie**, ak chcete zrušiť existujúce obnovenie a zdroj údajov sa vráti do posledného stavu obnovenia.</span><span class="sxs-lookup"><span data-stu-id="02170-144">Select **Stop refreshing** if you want to cancel an existing refresh and the data source will revert to its last refresh status.</span></span>

## <a name="delete-a-data-source"></a><span data-ttu-id="02170-145">Odstránenie zdroja údajov</span><span class="sxs-lookup"><span data-stu-id="02170-145">Delete a data source</span></span>

1. <span data-ttu-id="02170-146">V prehľadoch cieľových skupín prejdite na **Údaje** > **Zdroje údajov**.</span><span class="sxs-lookup"><span data-stu-id="02170-146">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="02170-147">Vyberte zvislé tri bodky vedľa zdroja údajov, ktorý chcete odstrániť, a vyberte **Odstrániť** z rozbaľovacej ponuky.</span><span class="sxs-lookup"><span data-stu-id="02170-147">Select the vertical ellipsis next to the data source you want to remove and select **Delete** from the drop-down menu.</span></span>

3. <span data-ttu-id="02170-148">Potvrďte odstránenie.</span><span class="sxs-lookup"><span data-stu-id="02170-148">Confirm your deletion.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]