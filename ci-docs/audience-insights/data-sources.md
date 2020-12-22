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
ms.openlocfilehash: a720641f7499fc71ff5bceeba48d296c51f77242
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643972"
---
# <a name="overview-about-data-sources"></a><span data-ttu-id="5b1ea-103">Prehľad o zdrojoch údajov</span><span class="sxs-lookup"><span data-stu-id="5b1ea-103">Overview about data sources</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="5b1ea-104">Funkcia prehľadov cieľových skupín v službe Dynamics 365 Customer Insights sa pripája sa k údajom zo širokej množiny zdrojov.</span><span class="sxs-lookup"><span data-stu-id="5b1ea-104">The audience insights capability in Dynamics 365 Customer Insights connects to data from a broad set of sources.</span></span> <span data-ttu-id="5b1ea-105">Pripojenie k zdroju údajov sa často označuje ako proces *prijímania údajov*.</span><span class="sxs-lookup"><span data-stu-id="5b1ea-105">Connecting to a data source is often referred to as the process of *data ingestion*.</span></span> <span data-ttu-id="5b1ea-106">Po prijatí údajov ich môžete [zjednotiť](data-unification.md) a podniknúť s nimi kroky.</span><span class="sxs-lookup"><span data-stu-id="5b1ea-106">After ingesting the data, you can [unify](data-unification.md) and take action on it.</span></span>

## <a name="add-a-data-source"></a><span data-ttu-id="5b1ea-107">Pridať zdroj údajov</span><span class="sxs-lookup"><span data-stu-id="5b1ea-107">Add a data source</span></span>

<span data-ttu-id="5b1ea-108">Prečítajte si podrobné články o tom, ako pridať zdroj údajov, podľa toho, ktorú možnosť si vyberiete.</span><span class="sxs-lookup"><span data-stu-id="5b1ea-108">Refer to the detailed articles on how to add a data source, depending on which option you choose.</span></span>

<span data-ttu-id="5b1ea-109">Zdroj údajov môžete pridať tromi hlavnými spôsobmi:</span><span class="sxs-lookup"><span data-stu-id="5b1ea-109">You can add a data source in three main ways:</span></span>

- [<span data-ttu-id="5b1ea-110">Prostredníctvom množstva konektorov Power Query</span><span class="sxs-lookup"><span data-stu-id="5b1ea-110">Through dozens of Power Query connectors</span></span>](connect-power-query.md)
- [<span data-ttu-id="5b1ea-111">Z priečinka Common Data Model</span><span class="sxs-lookup"><span data-stu-id="5b1ea-111">From a Common Data Model folder</span></span>](connect-common-data-model.md)
- [<span data-ttu-id="5b1ea-112">Z jazera Common Data Service</span><span class="sxs-lookup"><span data-stu-id="5b1ea-112">From your own Common Data Service lake</span></span>](connect-common-data-service-lake.md)

> [!NOTE]
> <span data-ttu-id="5b1ea-113">Zatiaľ nemôžete pridať údaje z lokálneho zdroja údajov.</span><span class="sxs-lookup"><span data-stu-id="5b1ea-113">You can't add data from on-premises data sources yet.</span></span>

## <a name="review-ingested-data"></a><span data-ttu-id="5b1ea-114">Kontrola prijatých údajov</span><span class="sxs-lookup"><span data-stu-id="5b1ea-114">Review ingested data</span></span>

<span data-ttu-id="5b1ea-115">Uvidíte názov každého prijatého zdroj údajov, jeho stav a poslednú aktualizáciu údajov pre tento zdroj.</span><span class="sxs-lookup"><span data-stu-id="5b1ea-115">You'll see the name of each ingested data source, its status, and the last time the data was refreshed for that source.</span></span> <span data-ttu-id="5b1ea-116">Zoznam zdrojov údajov môžete zoradiť podľa každého stĺpca.</span><span class="sxs-lookup"><span data-stu-id="5b1ea-116">You can sort the list of data sources by every column.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="5b1ea-117">![Pridaný zdroj údajov](media/configure-data-datasource-added.png "Pridaný zdroj údajov")</span><span class="sxs-lookup"><span data-stu-id="5b1ea-117">![Data source added](media/configure-data-datasource-added.png "Data source added")</span></span>

|<span data-ttu-id="5b1ea-118">Status</span><span class="sxs-lookup"><span data-stu-id="5b1ea-118">Status</span></span>  |<span data-ttu-id="5b1ea-119">Popis</span><span class="sxs-lookup"><span data-stu-id="5b1ea-119">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="5b1ea-120">Úspešné</span><span class="sxs-lookup"><span data-stu-id="5b1ea-120">Successful</span></span>   |<span data-ttu-id="5b1ea-121">Zdroj údajov bol úspešne prijatý, ak je v stĺpci **Obnovené** uvedený čas.</span><span class="sxs-lookup"><span data-stu-id="5b1ea-121">Data source was successfully ingested if a time is mentioned in the **Refreshed** column.</span></span>
|<span data-ttu-id="5b1ea-122">Nespustené</span><span class="sxs-lookup"><span data-stu-id="5b1ea-122">Not started</span></span>   |<span data-ttu-id="5b1ea-123">Zdroj údajov zatiaľ nemá žiadne prijaté údaje alebo je stále v režime konceptu.</span><span class="sxs-lookup"><span data-stu-id="5b1ea-123">The data source has no data ingested yet or still in draft mode.</span></span>         |
|<span data-ttu-id="5b1ea-124">Obnovuje sa</span><span class="sxs-lookup"><span data-stu-id="5b1ea-124">Refreshing</span></span>    |<span data-ttu-id="5b1ea-125">Prebieha prijímanie údajov.</span><span class="sxs-lookup"><span data-stu-id="5b1ea-125">Data ingestion is in progress.</span></span> <span data-ttu-id="5b1ea-126">Túto operáciu môžete zrušiť tak, že v stĺpci **Akcie** vyberiete **Zastaviť obnovovanie**.</span><span class="sxs-lookup"><span data-stu-id="5b1ea-126">You can cancel this operation by selecting **Stop refreshing** in the **Actions** column.</span></span> <span data-ttu-id="5b1ea-127">Zastavenie obnovovania zdroja údajov sa obnoví do posledného stavu obnovenia.</span><span class="sxs-lookup"><span data-stu-id="5b1ea-127">Stopping the refresh of a data source will revert it to its last refresh state.</span></span>       |
|<span data-ttu-id="5b1ea-128">Zlyhalo</span><span class="sxs-lookup"><span data-stu-id="5b1ea-128">Failed</span></span>     |<span data-ttu-id="5b1ea-129">Pri prijímaní údajov nastali chyby.</span><span class="sxs-lookup"><span data-stu-id="5b1ea-129">Data ingestion ran into errors.</span></span>         |

<span data-ttu-id="5b1ea-130">Výberom položky **Stav obnovenia** zobrazíte ďalšie podrobnosti o stave obnovenia vrátane podrobností o chybách a následných aktualizáciách procesu.</span><span class="sxs-lookup"><span data-stu-id="5b1ea-130">Select **Refresh status** to review more details on the refresh status, including error details and downstream process updates.</span></span>

<span data-ttu-id="5b1ea-131">Načítanie údajov môže chvíľu trvať.</span><span class="sxs-lookup"><span data-stu-id="5b1ea-131">Loading data can take some time.</span></span> <span data-ttu-id="5b1ea-132">Po úspešnom obnovení môžu byť prijaté údaje preskúmané na stránke **Entity**.</span><span class="sxs-lookup"><span data-stu-id="5b1ea-132">After a successful refresh, the ingested data can be reviewed from the **Entities** page.</span></span> <span data-ttu-id="5b1ea-133">Ďalšie informácie nájdete v časti [Entity](entities.md).</span><span class="sxs-lookup"><span data-stu-id="5b1ea-133">For more information, see [Entities](entities.md).</span></span>

## <a name="refresh-a-data-source"></a><span data-ttu-id="5b1ea-134">Obnovte zdroj údajov</span><span class="sxs-lookup"><span data-stu-id="5b1ea-134">Refresh a data source</span></span>

<span data-ttu-id="5b1ea-135">Zdroje údajov je možné obnovovať automaticky alebo podľa potreby manuálne.</span><span class="sxs-lookup"><span data-stu-id="5b1ea-135">Data sources can be refreshed on an automatic schedule or refreshed manually on demand.</span></span> 

<span data-ttu-id="5b1ea-136">Prejdite na časť **Správca** > **Systém** > [**Plánovať**](system.md#schedule-tab) a nakonfigurujte plánované obnovenie všetkých vašich prijatých zdrojov údajov.</span><span class="sxs-lookup"><span data-stu-id="5b1ea-136">Go to **Admin** > **System** > [**Schedule**](system.md#schedule-tab) to configure scheduled refreshes of all your ingested data sources.</span></span>

<span data-ttu-id="5b1ea-137">Ak chcete obnoviť zdroj údajov na požiadanie, postupujte takto:</span><span class="sxs-lookup"><span data-stu-id="5b1ea-137">To refresh a data source on demand, follow these steps:</span></span>

1. <span data-ttu-id="5b1ea-138">V prehľadoch cieľových skupín prejdite na **Údaje** > **Zdroje údajov**</span><span class="sxs-lookup"><span data-stu-id="5b1ea-138">In audience insights, go to **Data** > **Data sources**</span></span>

2. <span data-ttu-id="5b1ea-139">Vyberte zvislé tri bodky vedľa zdroja údajov, ktorý chcete obnoviť, a vyberte položku **Obnoviť** z rozbaľovacieho zoznamu.</span><span class="sxs-lookup"><span data-stu-id="5b1ea-139">Select the vertical ellipsis next to the data source you want to refresh and select **Refresh** from the drop-down list.</span></span>

3. <span data-ttu-id="5b1ea-140">Zdroj údajov je teraz spustený na účely manuálneho obnovenia.</span><span class="sxs-lookup"><span data-stu-id="5b1ea-140">The data source is now triggered for a manual refresh.</span></span> <span data-ttu-id="5b1ea-141">Obnovením zdroja údajov aktualizujete schému entít aj údaje pre všetky entity uvedené v zdroji údajov.</span><span class="sxs-lookup"><span data-stu-id="5b1ea-141">Refreshing a data source will update both the entity schema as well as data for all the entities specified in the data source.</span></span>

4. <span data-ttu-id="5b1ea-142">Vyberte položku **Zastaviť obnovovanie**, ak chcete zrušiť existujúce obnovenie a zdroj údajov sa vráti do posledného stavu obnovenia.</span><span class="sxs-lookup"><span data-stu-id="5b1ea-142">Select **Stop refreshing** if you want to cancel an existing refresh and the data source will revert to its last refresh status.</span></span>

## <a name="delete-a-data-source"></a><span data-ttu-id="5b1ea-143">Odstránenie zdroja údajov</span><span class="sxs-lookup"><span data-stu-id="5b1ea-143">Delete a data source</span></span>

1. <span data-ttu-id="5b1ea-144">V prehľadoch cieľových skupín prejdite na **Údaje** > **Zdroje údajov**.</span><span class="sxs-lookup"><span data-stu-id="5b1ea-144">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="5b1ea-145">Vyberte zvislé tri bodky vedľa zdroja údajov, ktorý chcete odstrániť, a vyberte **Odstrániť** z rozbaľovacej ponuky.</span><span class="sxs-lookup"><span data-stu-id="5b1ea-145">Select the vertical ellipsis next to the data source you want to remove and select **Delete** from the drop-down menu.</span></span>

3. <span data-ttu-id="5b1ea-146">Potvrďte odstránenie.</span><span class="sxs-lookup"><span data-stu-id="5b1ea-146">Confirm your deletion.</span></span>
