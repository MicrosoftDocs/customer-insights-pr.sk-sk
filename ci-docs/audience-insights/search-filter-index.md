---
title: Vyhľadávanie a filtrovanie profilov zákazníkov
description: Rýchlo vyhľadajte informácie o zjednotených profiloch zákazníkov a filtrujte konkrétne atribúty.
ms.date: 01/19/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: b6cc0ad1a47a6c00e3bf220271f42870fc53621b
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597162"
---
# <a name="customer-profiles-search--filter-index"></a><span data-ttu-id="88621-103">Profily zákazníkov: Index vyhľadávania a filtrovania</span><span class="sxs-lookup"><span data-stu-id="88621-103">Customer profiles: Search & filter index</span></span>

<span data-ttu-id="88621-104">Výsledkom zjednocovanie vašich zákazníckych údajov je entita profilu zákazníka, ktorá poskytuje zjednotený pohľad na celkovú zákaznícku základňu.</span><span class="sxs-lookup"><span data-stu-id="88621-104">The result of unifying your customer data is a Customer Profile entity that provides a unified view into your total customer base.</span></span> <span data-ttu-id="88621-105">Ak chcete [rýchlo vyhľadať informácie o konkrétnom zákazníkovi alebo skupine zákazníkov](customer-profiles.md), môžete nakonfigurovať možnosti **vyhľadávania** a **filtrovania** na stránke **zákazníci**.</span><span class="sxs-lookup"><span data-stu-id="88621-105">To quickly [find information on a specific customer or group of customers](customer-profiles.md), you can configure the **Search** and **Filter** capabilities on the **Customers** page.</span></span> <span data-ttu-id="88621-106">Čítajte ďalej a dozviete sa, ako môžu správcovia upravovať atribúty na stránke **indexu vyhľadávania a filtrovania**, ktoré sú k dispozícii používateľom na vyhľadávanie a filtrovanie.</span><span class="sxs-lookup"><span data-stu-id="88621-106">Read on to learn how admins can edit the attributes on the **Search & filter index** page, which are available to users for searching and filtering.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="88621-107">![Filter vyhľadávania](media/search-filter.png "Filter vyhľadávania")</span><span class="sxs-lookup"><span data-stu-id="88621-107">![Search filter](media/search-filter.png "Search filter")</span></span>

## <a name="add-fields-and-specify-attributes"></a><span data-ttu-id="88621-108">Pridanie polí a zadanie atribútov</span><span class="sxs-lookup"><span data-stu-id="88621-108">Add fields and specify attributes</span></span>

<span data-ttu-id="88621-109">Ak definujete atribúty s možnosťou vyhľadávania ako správca po prvý raz, musíte najprv definovať indexované polia.</span><span class="sxs-lookup"><span data-stu-id="88621-109">If it's the first time you define searchable attributes as an administrator, you need to define indexed fields first.</span></span> <span data-ttu-id="88621-110">Odporúčame, aby ste si vybrali všetky atribúty, podľa ktorých môžu používatelia vyhľadávať a filtrovať zákazníkov na stránke **Zákazníci**.</span><span class="sxs-lookup"><span data-stu-id="88621-110">We suggest you choose all the attributes by which users can search and filter customers on the **Customers** page.</span></span> <span data-ttu-id="88621-111">Môžete zadať iba atribúty, ktoré existujú v entite profilu zákazníka, ktorý ste vytvorili počas procesu zjednotenia údajov.</span><span class="sxs-lookup"><span data-stu-id="88621-111">You can only specify attributes that exist in the Customer Profile entity that you created during the data unification process.</span></span>

1. <span data-ttu-id="88621-112">Otvorte stránku **Zákazníci** a vyberte **Index vyhľadávania a filtrovania**.</span><span class="sxs-lookup"><span data-stu-id="88621-112">Open the **Customers** page and select **Search & filter index**.</span></span>

2. <span data-ttu-id="88621-113">Vyberte **+ pridať** a zadajte indexované polia.</span><span class="sxs-lookup"><span data-stu-id="88621-113">Select **+ Add** to specify the indexed fields.</span></span>

3. <span data-ttu-id="88621-114">Vyberte atribúty v zozname, ktoré chcete pridať ako indexované polia.</span><span class="sxs-lookup"><span data-stu-id="88621-114">Select the attributes in the list you want to add as indexed fields.</span></span> <span data-ttu-id="88621-115">Vždy môžete pridať ďalšie atribúty výberom položky **Pridať**.</span><span class="sxs-lookup"><span data-stu-id="88621-115">You can always add more attributes by selecting **Add**.</span></span> <span data-ttu-id="88621-116">Vybrané atribúty môžete tiež odstrániť výberom symbolu **Odstrániť**.</span><span class="sxs-lookup"><span data-stu-id="88621-116">You can also remove any selected attributes by selecting the **Remove** symbol.</span></span>

## <a name="explore-the-indexed-customer-fields-table"></a><span data-ttu-id="88621-117">Preskúmanie tabuľky Indexované polia zákazníkov</span><span class="sxs-lookup"><span data-stu-id="88621-117">Explore the Indexed customer fields table</span></span>

<span data-ttu-id="88621-118">V tabuľke sú uvedené nasledujúce informácie.</span><span class="sxs-lookup"><span data-stu-id="88621-118">The following information is presented in the table.</span></span>

- <span data-ttu-id="88621-119">**Názov**: Predstavuje názov atribútu, ako sa zobrazuje v entite profilu zákazníka.</span><span class="sxs-lookup"><span data-stu-id="88621-119">**Name**: Represents the attribute's name as it appears in the Customer Profile entity.</span></span>
- <span data-ttu-id="88621-120">**Typ údajov**: Určuje, či je typ údajov reťazec, číslo alebo dátum.</span><span class="sxs-lookup"><span data-stu-id="88621-120">**Data type**: Specifies whether the data type is a string, a number, or a date.</span></span>
- <span data-ttu-id="88621-121">**Zahrnuté do vyhľadávania**: Určuje, či sa tento atribút môže použiť na vyhľadávanie zákazníkov na stránke **Zákazníci** pomocou **vyhľadávacieho** poľa.</span><span class="sxs-lookup"><span data-stu-id="88621-121">**Included in search**: Specifies whether this attribute can be used for searching customers on the **Customers** page using the **Search** field.</span></span>
- <span data-ttu-id="88621-122">**Pridať filter**: Ovládací prvok na definovanie spôsobu, akým sa tento atribút môže použiť na filtrovanie na stránke **Zákazníci**.</span><span class="sxs-lookup"><span data-stu-id="88621-122">**Add Filter**: Control to define how this attribute can be used for filtering on the **Customers** page.</span></span>

## <a name="editing-filtering-options-for-a-given-attribute"></a><span data-ttu-id="88621-123">Úprava možností filtrovania pre daný atribút</span><span class="sxs-lookup"><span data-stu-id="88621-123">Editing filtering options for a given attribute</span></span>

<span data-ttu-id="88621-124">Ponuka **Filter** na stránke **Zákazníci** môže obsahovať rôzny počet úrovní atribútov (napríklad rôzne vekové skupiny na filtrovanie zákazníkov).</span><span class="sxs-lookup"><span data-stu-id="88621-124">The **Filter** menu on the **Customers** page can include a varying number of attribute levels (for example, different age groups to filter customers by).</span></span>

1. <span data-ttu-id="88621-125">Vyberte **Pridať filter** pre daný atribút na stránke **Index vyhľadávania a filtrovania**.</span><span class="sxs-lookup"><span data-stu-id="88621-125">Select **Add Filter** for a given attribute on the **Search & filter index** page.</span></span> <span data-ttu-id="88621-126">Môžete definovať počet výsledkov a poradie, v ktorom budú usporiadané.</span><span class="sxs-lookup"><span data-stu-id="88621-126">You can define the number of results and the order in which they'll be organized.</span></span> <span data-ttu-id="88621-127">V závislosti od typu údajov atribútu sa zobrazí jedna z nasledujúcich tabiel.</span><span class="sxs-lookup"><span data-stu-id="88621-127">Depending on the attribute's data type, one of the following panes appears.</span></span>

- <span data-ttu-id="88621-128">Atribúty typu Reťazec: Zadajte počet požadovaných výsledkov na table **Možnosti filtrovania reťazcov** a pravidlá poradia, podľa ktorých budú usporiadané.</span><span class="sxs-lookup"><span data-stu-id="88621-128">String-type attributes: Specify the number of desired results on the **String filter options** pane and the order policy by which they'll be organized.</span></span>

- <span data-ttu-id="88621-129">Atribúty typu Číselný: Zadajte počet intervalov obsiahnutých na table **Možnosti filtrovania čísiel** a pravidlá poradia, podľa ktorých budú usporiadané.</span><span class="sxs-lookup"><span data-stu-id="88621-129">Numerical-type attributes: Specify the intervals included on the **Number filter options** pane and the order policy by which they'll be organized.</span></span>

- <span data-ttu-id="88621-130">Atribúty typu Údaje: Zadajte počet intervalov obsiahnutých na table **Možnosti filtrovania údajov** a pravidlá poradia, podľa ktorých budú usporiadané.</span><span class="sxs-lookup"><span data-stu-id="88621-130">Date-type attributes:  Specify the intervals included on the **Date filter options** pane and the order policy by which they'll be organized.</span></span>

2. <span data-ttu-id="88621-131">Zmeny vykonajte výberom položky **Uložiť**.</span><span class="sxs-lookup"><span data-stu-id="88621-131">Select **Save** to apply your changes.</span></span>

3. <span data-ttu-id="88621-132">Vyberte položku **Spustiť**, keď budete pripravení použiť svoje nastavenia.</span><span class="sxs-lookup"><span data-stu-id="88621-132">Select **Run** once you're ready to apply your settings.</span></span>

## <a name="next-steps"></a><span data-ttu-id="88621-133">Ďalšie kroky</span><span class="sxs-lookup"><span data-stu-id="88621-133">Next steps</span></span>

<span data-ttu-id="88621-134">Choďte na stránku **Zákazníci** a vyhľadajte profily zákazníkov alebo pomocou indexovaných polí zobrazte podmnožinu všetkých profilov zákazníkov.</span><span class="sxs-lookup"><span data-stu-id="88621-134">Go to the **Customers** page to search for customer profiles or use the indexed fields to see a subset of all customer profiles.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]