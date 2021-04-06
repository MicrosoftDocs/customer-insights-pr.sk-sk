---
title: Pripojte sa k entitám v spravovanom jazere služby Common Data Service
description: Import údajov zo spravovaného data lake Common Data Service.
ms.date: 09/29/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.reviewer: mhart
ms.openlocfilehash: b1cfab40c1edb32f4a7f359e1195cfb1e879a0d5
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596978"
---
# <a name="connect-to-data-in-a-common-data-service-managed-data-lake"></a><span data-ttu-id="8e93d-103">Pripojenie k údajom v dátovom jazere spravovanom cez Common Data Service</span><span class="sxs-lookup"><span data-stu-id="8e93d-103">Connect to data in a Common Data Service managed data lake</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="8e93d-104">Tento článok poskytuje informácie o tom, ako sa súčasní zákazníci Dynamics 365 môžu rýchlo pripojiť k svojim analytickým entitám v spravovanom jazere Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="8e93d-104">This article provides information on how existing Dynamics 365 customers can quickly connect to their analytical entities in the Common Data Service managed lake.</span></span> <span data-ttu-id="8e93d-105">Musíte byť správcom organizácie Common Data Service, aby ste mohli pokračovať a pozrieť si zoznam entít dostupných v spravovanom jazere.</span><span class="sxs-lookup"><span data-stu-id="8e93d-105">You must be an admin on the Common Data Service organization to proceed and see the list of entities available in the managed lake.</span></span>

## <a name="important-considerations"></a><span data-ttu-id="8e93d-106">Dôležité aspekty</span><span class="sxs-lookup"><span data-stu-id="8e93d-106">Important considerations</span></span>

<span data-ttu-id="8e93d-107">Údaje uložené v online službách, ako napríklad Azure Data Lake Storage, môžu byť uložené na inom mieste, ako je miesto, kde sa údaje spracúvajú alebo ukladajú v rámci Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="8e93d-107">Data stored in online services, such as Azure Data Lake Storage, may be stored in a different location than where data is processed or stored in Dynamics 365 Customer Insights.</span></span><span data-ttu-id="8e93d-108">Importovaním alebo pripojením sa k údajom uloženým v online službách súhlasíte s tým, že údaje je možné prenášať a ukladať pomocou Dynamics 365 Customer Insights.  [Ďalšie informácie nájdete v Centre dôveryhodnosti spoločnosti Microsoft.](https://www.microsoft.com/trust-center)</span><span class="sxs-lookup"><span data-stu-id="8e93d-108"> By importing or connecting to data stored in online services, you agree that data can be transferred to and stored with Dynamics 365 Customer Insights. [Learn more at the Microsoft Trust Center.](https://www.microsoft.com/trust-center)</span></span>

## <a name="connect-to-a-common-data-service-managed-lake"></a><span data-ttu-id="8e93d-109">Pripojte sa k spravovanému fondu Common Data Service</span><span class="sxs-lookup"><span data-stu-id="8e93d-109">Connect to a Common Data Service managed lake</span></span>

1. <span data-ttu-id="8e93d-110">V prehľadoch cieľových skupín prejdite na **Údaje** > **Zdroje údajov**.</span><span class="sxs-lookup"><span data-stu-id="8e93d-110">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="8e93d-111">Vyberte položku **Pridať zdroj údajov**.</span><span class="sxs-lookup"><span data-stu-id="8e93d-111">Select **Add data source**.</span></span>

3. <span data-ttu-id="8e93d-112">Stlačte možnosť **Pripojiť k Common Data Service** a stlačte **Ďalej**.</span><span class="sxs-lookup"><span data-stu-id="8e93d-112">Select **Connect to Common Data Service** and select **Next**.</span></span>

4. <span data-ttu-id="8e93d-113">Zadajte **Názov** zdroja údajov a následne vyberte položku **Ďalej**.</span><span class="sxs-lookup"><span data-stu-id="8e93d-113">Enter a **Name** for the data source and select **Next**.</span></span> <span data-ttu-id="8e93d-114">Pokyny týkajúce sa pomenovania:</span><span class="sxs-lookup"><span data-stu-id="8e93d-114">Name guidelines:</span></span> 
   - <span data-ttu-id="8e93d-115">Začnite písmenom.</span><span class="sxs-lookup"><span data-stu-id="8e93d-115">Start with a letter.</span></span>
   - <span data-ttu-id="8e93d-116">Používajte iba písmená a číslice.</span><span class="sxs-lookup"><span data-stu-id="8e93d-116">Use letters and numbers only.</span></span> <span data-ttu-id="8e93d-117">Nie je povolené zadávanie špeciálnych znakov a medzier.</span><span class="sxs-lookup"><span data-stu-id="8e93d-117">Special characters and spaces are not allowed.</span></span>
   - <span data-ttu-id="8e93d-118">Použite 3 až 64 znakov.</span><span class="sxs-lookup"><span data-stu-id="8e93d-118">Use between 3 and 64 characters.</span></span>

5. <span data-ttu-id="8e93d-119">Zadajte **Adresa servera** pre svoju organizáciu Common Data Service a potom stlačte možnosť **Prihlásiť sa**.</span><span class="sxs-lookup"><span data-stu-id="8e93d-119">Provide the **Server address** for your Common Data Service organization, and select **Sign in**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="8e93d-120">![Dialógové okno zadávania serverovej adresy Common Data Service](media/enter-CDS-org-details.png)</span><span class="sxs-lookup"><span data-stu-id="8e93d-120">![Dialog box to enter Common Data Service server address](media/enter-CDS-org-details.png)</span></span>

6. <span data-ttu-id="8e93d-121">Z dostupného zoznamu vyberte entity, ktoré chcete prijať.</span><span class="sxs-lookup"><span data-stu-id="8e93d-121">Select the entities you want to ingest from the available list.</span></span>    

   > [!NOTE]
   > <span data-ttu-id="8e93d-122">Ak sú niektoré entity už vybrané, môžu ich používať iné aplikácie Dynamics 365 (napríklad Dynamics 365 Sales Insights alebo Customer Service Insights).</span><span class="sxs-lookup"><span data-stu-id="8e93d-122">If some entities are already selected, they might be used by other Dynamics 365 applications (such as Dynamics 365 Sales Insights or Customer Service Insights).</span></span> <span data-ttu-id="8e93d-123">Výber nemožno meniť.</span><span class="sxs-lookup"><span data-stu-id="8e93d-123">You can't change the selection.</span></span> <span data-ttu-id="8e93d-124">Tieto entity budú k dispozícii po vytvorení zdroja údajov.</span><span class="sxs-lookup"><span data-stu-id="8e93d-124">These entities will be available once the data source is created.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="8e93d-125">![Dialógové okno so zoznamom entít v organizácii Common Data Service](media/select-analytical-entities.png)</span><span class="sxs-lookup"><span data-stu-id="8e93d-125">![Dialog box showing a list of entities in the Common Data Service org](media/select-analytical-entities.png)</span></span>

7. <span data-ttu-id="8e93d-126">Uložte výber a začnite synchronizovať vybrané entity so spravovaným fondom Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="8e93d-126">Save your selection to start syncing the selected entities to the Common Data Service managed lake.</span></span> <span data-ttu-id="8e93d-127">Novo pridané pripojenie nájdete na stránke **Zdroje údajov**.</span><span class="sxs-lookup"><span data-stu-id="8e93d-127">You'll find the newly added connection on the **Data sources** page.</span></span> <span data-ttu-id="8e93d-128">Bude zaradená do frontu na obnovenie a zobrazí počet entít ako 0, kým sa všetky entity nesynchronizujú.</span><span class="sxs-lookup"><span data-stu-id="8e93d-128">It will be queued for refresh and show the entities count as 0 until all the entities are synced.</span></span>

<span data-ttu-id="8e93d-129">Iba jeden zdroj údajov z prostredia môže súčasne používať to isté spravované jazero služby Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="8e93d-129">Only one data source of an environment can simultaneously use the same Common Data Service managed lake.</span></span>

## <a name="edit-a-common-data-service-managed-lake-data-source"></a><span data-ttu-id="8e93d-130">Upravte zdroj údajov spravovaného fondu Common Data Service</span><span class="sxs-lookup"><span data-stu-id="8e93d-130">Edit a Common Data Service managed lake data source</span></span>

<span data-ttu-id="8e93d-131">Výber entity môžete upraviť až po vytvorení zdroju údajov.</span><span class="sxs-lookup"><span data-stu-id="8e93d-131">You only edit the entity selection after creating the data source.</span></span> <span data-ttu-id="8e93d-132">Napríklad ak boli do entity pridané ďalšie entity Common Data Service a chcete ich tiež importovať.</span><span class="sxs-lookup"><span data-stu-id="8e93d-132">For example, if additional entities were added to Common Data Service and you want to import them too.</span></span>    
<span data-ttu-id="8e93d-133">Ak sa chcete pripojiť k inému Common Data Service, [vytvorte nový zdroj údajov](#connect-to-a-common-data-service-managed-lake).</span><span class="sxs-lookup"><span data-stu-id="8e93d-133">To connect to a different Common Data Service, [create a new data source](#connect-to-a-common-data-service-managed-lake).</span></span>

1. <span data-ttu-id="8e93d-134">V prehľadoch cieľových skupín prejdite na **Údaje** > **Zdroje údajov**.</span><span class="sxs-lookup"><span data-stu-id="8e93d-134">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="8e93d-135">Vedľa zdroja údajov, ktorý chcete aktualizovať, vyberte tri bodky.</span><span class="sxs-lookup"><span data-stu-id="8e93d-135">Next to the data source you'd like to update, select the ellipsis.</span></span>

3. <span data-ttu-id="8e93d-136">Zo zoznamu vyberte možnosť **Upraviť**.</span><span class="sxs-lookup"><span data-stu-id="8e93d-136">Select the **Edit** option from the list.</span></span>

4. <span data-ttu-id="8e93d-137">Vyberte ďalšie entity z dostupného zoznamu entít a vyberte položku **Uložiť**.</span><span class="sxs-lookup"><span data-stu-id="8e93d-137">Select additional entities from the available list of entities and select **Save**.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]