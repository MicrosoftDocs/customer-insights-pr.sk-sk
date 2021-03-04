---
title: Konektor služby Power Apps
description: Pripojte sa k Power Apps a Power Automate.
ms.date: 01/19/2021
ms.reviewer: nikeller
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 5a8bbb9a09218d54228589d43c21c8894680b56e
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268935"
---
# <a name="microsoft-power-apps-connector-preview"></a><span data-ttu-id="eb7d5-103">Konektor Microsoft Power Apps (ukážka)</span><span class="sxs-lookup"><span data-stu-id="eb7d5-103">Microsoft Power Apps connector (preview)</span></span>

<span data-ttu-id="eb7d5-104">Prineste zjednotené profily zákazníkov do svojich prispôsobených aplikácií pomocou Power Apps.</span><span class="sxs-lookup"><span data-stu-id="eb7d5-104">Bring unified customer profiles into your personalized apps with Power Apps.</span></span>

## <a name="connect-power-apps-and-dynamics-365-customer-insights"></a><span data-ttu-id="eb7d5-105">Pripojenie k Power Apps a Dynamics 365 Customer Insights</span><span class="sxs-lookup"><span data-stu-id="eb7d5-105">Connect Power Apps and Dynamics 365 Customer Insights</span></span>

<span data-ttu-id="eb7d5-106">Customer Insights sú jedným z mnohých [dostupných zdrojov údajov v Power Apps](https://docs.microsoft.com/powerapps/maker/canvas-apps/working-with-data-sources).</span><span class="sxs-lookup"><span data-stu-id="eb7d5-106">Customer Insights is one of the many [available sources for data in Power Apps](https://docs.microsoft.com/powerapps/maker/canvas-apps/working-with-data-sources).</span></span>

<span data-ttu-id="eb7d5-107">Prečítajte si dokumentáciu k Power Apps, kde sa dozviete, ako [pridať dátové pripojenie k aplikácii](https://docs.microsoft.com/powerapps/maker/canvas-apps/add-data-connection).</span><span class="sxs-lookup"><span data-stu-id="eb7d5-107">Refer to the Power Apps documentation to learn how to [add a data connection to an app](https://docs.microsoft.com/powerapps/maker/canvas-apps/add-data-connection).</span></span> <span data-ttu-id="eb7d5-108">Odporúčame tiež si prečítať článok [ako Power Apps využíva delegovanie na spracovanie veľkých množín údajov v aplikáciách plátna](https://docs.microsoft.com/powerapps/maker/canvas-apps/delegation-overview).</span><span class="sxs-lookup"><span data-stu-id="eb7d5-108">We recommend you also review [how Power Apps uses delegation to handle large datasets in Canvas apps](https://docs.microsoft.com/powerapps/maker/canvas-apps/delegation-overview).</span></span>

## <a name="available-entities"></a><span data-ttu-id="eb7d5-109">Dostupné entity</span><span class="sxs-lookup"><span data-stu-id="eb7d5-109">Available entities</span></span>

<span data-ttu-id="eb7d5-110">Po pridaní Customer Insights ako dátového pripojenia si môžete vybrať nasledujúce entity v systéme Power Apps:</span><span class="sxs-lookup"><span data-stu-id="eb7d5-110">After adding Customer Insights as a data connection, you can choose the following entities in Power Apps:</span></span>

- <span data-ttu-id="eb7d5-111">Zákazník: použitie údajov zo [zjednoteného profilu zákazníka](customer-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="eb7d5-111">Customer: to use data from the [unified customer profile](customer-profiles.md).</span></span>
- <span data-ttu-id="eb7d5-112">UnifiedActivity: na zobrazenie [časovej osi aktivity](activities.md) v aplikácii.</span><span class="sxs-lookup"><span data-stu-id="eb7d5-112">UnifiedActivity: to display the [activity timeline](activities.md) on the app.</span></span>

## <a name="limitations"></a><span data-ttu-id="eb7d5-113">Obmedzenia</span><span class="sxs-lookup"><span data-stu-id="eb7d5-113">Limitations</span></span>

### <a name="retrievable-entities"></a><span data-ttu-id="eb7d5-114">Získateľné entity</span><span class="sxs-lookup"><span data-stu-id="eb7d5-114">Retrievable entities</span></span>

<span data-ttu-id="eb7d5-115">Entity **Zákazník**, **Zjednotená aktivita** a **Segmenty** môžete získať len prostredníctvom konektora Power Apps.</span><span class="sxs-lookup"><span data-stu-id="eb7d5-115">You can only retrieve the **Customer**, **UnifiedActivity**, and **Segments** entities through the Power Apps connector.</span></span> <span data-ttu-id="eb7d5-116">Ostatné entity sa zobrazujú, pretože podkladový konektor ich podporuje prostredníctvom spúšťačov v Power Automate.</span><span class="sxs-lookup"><span data-stu-id="eb7d5-116">Other entities are shown because the underlying connector supports them through triggers in Power Automate.</span></span>  

### <a name="delegation"></a><span data-ttu-id="eb7d5-117">Delegovanie</span><span class="sxs-lookup"><span data-stu-id="eb7d5-117">Delegation</span></span>

<span data-ttu-id="eb7d5-118">Delegovanie funguje pre entitu Zákazník a entitu Zjednotená aktivita.</span><span class="sxs-lookup"><span data-stu-id="eb7d5-118">Delegation works for the Customer entity and UnifiedActivity entity.</span></span> 

- <span data-ttu-id="eb7d5-119">Delegovanie pre entitu **Zákazník**: Ak chcete použiť delegovanie pre túto entitu, polia musia byť indexované v [indexe vyhľadávania a filtrovania](search-filter-index.md).</span><span class="sxs-lookup"><span data-stu-id="eb7d5-119">Delegation for **Customer** entity: To use delegation for this entity, the fields need to be indexed in [Search & filter index](search-filter-index.md).</span></span>  

- <span data-ttu-id="eb7d5-120">Delegovanie pre entitu **Zjednotená aktivita**: Delegovanie pre túto entitu funguje iba pre polia **ActivityId** a **CustomerId**.</span><span class="sxs-lookup"><span data-stu-id="eb7d5-120">Delegation for **UnifiedActivity**: Delegation for this entity only works for the fields **ActivityId** and **CustomerId**.</span></span>  

- <span data-ttu-id="eb7d5-121">Ďalšie informácie o delegovaní nájdete v časti [Delegovateľné funkcie a operácie Power Apps](https://docs.microsoft.com/connectors/commondataservice/#power-apps-delegable-functions-and-operations-for-the-cds-for-apps).</span><span class="sxs-lookup"><span data-stu-id="eb7d5-121">For more information about delegation, see [Power Apps delegable functions and operations](https://docs.microsoft.com/connectors/commondataservice/#power-apps-delegable-functions-and-operations-for-the-cds-for-apps).</span></span> 

## <a name="example-gallery-control"></a><span data-ttu-id="eb7d5-122">Príklad ovládacieho prvku galérie</span><span class="sxs-lookup"><span data-stu-id="eb7d5-122">Example gallery control</span></span>

<span data-ttu-id="eb7d5-123">Napríklad pridáte profily zákazníkov do [ovládacieho prvku galérie](https://docs.microsoft.com/powerapps/maker/canvas-apps/add-gallery).</span><span class="sxs-lookup"><span data-stu-id="eb7d5-123">For example, you add customer profiles to a [gallery control](https://docs.microsoft.com/powerapps/maker/canvas-apps/add-gallery).</span></span>

1. <span data-ttu-id="eb7d5-124">Pridajte ovládací prvok **Galéria** do aplikácie, ktorú vytvárate.</span><span class="sxs-lookup"><span data-stu-id="eb7d5-124">Add a **Gallery** control to an app you're building.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="eb7d5-125">![Pridanie prvku galérie](media/connector-powerapps9.png "Pridanie prvku galérie")</span><span class="sxs-lookup"><span data-stu-id="eb7d5-125">![Add a gallery element](media/connector-powerapps9.png "Add a gallery element")</span></span>

1. <span data-ttu-id="eb7d5-126">Vyberte **Zákazník** ako zdroj údajov pre položky.</span><span class="sxs-lookup"><span data-stu-id="eb7d5-126">Select **Customer** as the data source for items.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="eb7d5-127">![Výber zdroja údajov](media/choose-datasource-powerapps.png "Výber zdroja údajov")</span><span class="sxs-lookup"><span data-stu-id="eb7d5-127">![Select a data source](media/choose-datasource-powerapps.png "Select a data source")</span></span>

1. <span data-ttu-id="eb7d5-128">Na pravej strane môžete zmeniť dátový panel a zvoliť, ktoré pole pre entitu zákazníka sa má zobraziť v galérii.</span><span class="sxs-lookup"><span data-stu-id="eb7d5-128">You can change the data panel on the right to select which field for the Customer entity to show on the gallery.</span></span>

1. <span data-ttu-id="eb7d5-129">Ak chcete v galérii zobraziť akékoľvek pole od vybraného zákazníka, vyplňte vlastnosť Text štítka: **{Name_of_the_gallery}.Selected.{property_name}**</span><span class="sxs-lookup"><span data-stu-id="eb7d5-129">If you want to show any field from the selected customer on the gallery, fill in the Text property of a label:  **{Name_of_the_gallery}.Selected.{property_name}**</span></span>

    <span data-ttu-id="eb7d5-130">Príklad: Gallery1.Selected.address1_city</span><span class="sxs-lookup"><span data-stu-id="eb7d5-130">Example: Gallery1.Selected.address1_city</span></span>

1. <span data-ttu-id="eb7d5-131">Ak chcete zobraziť jednotnú časovú os pre zákazníka, pridajte prvok Galéria a pridajte vlastnosť Položky: **Filter ('UnifiedActivity', CustomerId = {Customer_Id})**</span><span class="sxs-lookup"><span data-stu-id="eb7d5-131">To display the unified timeline for a customer, add a Gallery element, and add the Items property: **Filter('UnifiedActivity', CustomerId = {Customer_Id})**</span></span>

    <span data-ttu-id="eb7d5-132">Príklad: Filter('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)</span><span class="sxs-lookup"><span data-stu-id="eb7d5-132">Example: Filter('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]