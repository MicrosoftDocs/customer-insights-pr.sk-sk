---
title: Entity a množiny údajov
description: Zobrazujte údaje na stránke Entity.
ms.date: 04/16/2020
ms.reviewer: mukeshpo
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: e71c69a6207147d8cd65363d51a5fa6bbf896151
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269395"
---
# <a name="entities-in-audience-insights"></a><span data-ttu-id="8cbc8-103">Entity v prehľadoch cieľových skupín</span><span class="sxs-lookup"><span data-stu-id="8cbc8-103">Entities in audience insights</span></span>

<span data-ttu-id="8cbc8-104">Po [nakonfigurovaní zdrojov údajov](data-sources.md) prejdite na stránku **Entity** a vyhodnoťte kvalitu údajov, ktoré boli prijaté.</span><span class="sxs-lookup"><span data-stu-id="8cbc8-104">After [configuring your data sources](data-sources.md), go to the **Entities** page to evaluate the quality of the ingested data.</span></span> <span data-ttu-id="8cbc8-105">Entity sa považujú za množiny údajov.</span><span class="sxs-lookup"><span data-stu-id="8cbc8-105">Entities are considered datasets.</span></span> <span data-ttu-id="8cbc8-106">Ďalšie funkcie služby Dynamics 365 Customer Insights súvisia s týmito entitami.</span><span class="sxs-lookup"><span data-stu-id="8cbc8-106">Multiple capabilities of Dynamics 365 Customer Insights are built around these entities.</span></span> <span data-ttu-id="8cbc8-107">Ich dôkladná revízia vám môže pomôcť overiť výstup týchto funkcií.</span><span class="sxs-lookup"><span data-stu-id="8cbc8-107">Reviewing them closely can help you validate the output of those capabilities.</span></span>

<span data-ttu-id="8cbc8-108">Stránka **Entity** uvádza entity a obsahuje niekoľko stĺpcov:</span><span class="sxs-lookup"><span data-stu-id="8cbc8-108">The **Entities** page lists entities and includes several columns:</span></span>

- <span data-ttu-id="8cbc8-109">**Názov**: Názov entity údajov.</span><span class="sxs-lookup"><span data-stu-id="8cbc8-109">**Name**: The name of your data entity.</span></span> <span data-ttu-id="8cbc8-110">Ak sa vedľa názvu entity zobrazí výstražný symbol, znamená to, že údaje pre danú entitu sa nenačítali úspešne.</span><span class="sxs-lookup"><span data-stu-id="8cbc8-110">If you see a warning symbol next to an entity name, it means that the data for that entity didn't load successfully.</span></span>
- <span data-ttu-id="8cbc8-111">**Zdroj**: Typ zdroja údajov, ktorý prijímala entita</span><span class="sxs-lookup"><span data-stu-id="8cbc8-111">**Source**: The type of data source that ingested the entity</span></span>
- <span data-ttu-id="8cbc8-112">**Autor**: Meno osoby, ktorá vytvorila entitu</span><span class="sxs-lookup"><span data-stu-id="8cbc8-112">**Created by**: Name of the person who created the entity</span></span>
- <span data-ttu-id="8cbc8-113">**Vytvorené**: Dátum a čas vytvorenia entity</span><span class="sxs-lookup"><span data-stu-id="8cbc8-113">**Created**: Date and time of the entity creation</span></span>
- <span data-ttu-id="8cbc8-114">**Aktualizoval používateľ**: Meno osoby, ktorá aktualizovala entitu</span><span class="sxs-lookup"><span data-stu-id="8cbc8-114">**Updated by**: Name of the person who updated the entity</span></span>
- <span data-ttu-id="8cbc8-115">**Naposledy aktualizované**: Dátum a čas poslednej aktualizácie entity</span><span class="sxs-lookup"><span data-stu-id="8cbc8-115">**Last updated**: Date and time of the last update of the entity</span></span>
- <span data-ttu-id="8cbc8-116">**Posledné obnovenie**: Dátum a čas posledného obnovenia údajov</span><span class="sxs-lookup"><span data-stu-id="8cbc8-116">**Last refresh**: Date and time of the last data refresh</span></span>

## <a name="exploring-a-specific-entitys-data"></a><span data-ttu-id="8cbc8-117">Skúmanie údajov konkrétnej entity</span><span class="sxs-lookup"><span data-stu-id="8cbc8-117">Exploring a specific entity's data</span></span>

<span data-ttu-id="8cbc8-118">Vyberte entitu a preskúmajte rôzne polia a záznamy zahrnuté v tejto entite.</span><span class="sxs-lookup"><span data-stu-id="8cbc8-118">Select an entity to explore the different fields and records included within that entity.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="8cbc8-119">![Vyberte entitu](media/data-manager-entities-data.png "Vyberte entitu")</span><span class="sxs-lookup"><span data-stu-id="8cbc8-119">![Select an entity](media/data-manager-entities-data.png "Select an entity")</span></span>

- <span data-ttu-id="8cbc8-120">Karta **Údaje** je predvolene vybratá a zobrazuje tabuľku so zoznamom podrobností o jednotlivých záznamoch entity.</span><span class="sxs-lookup"><span data-stu-id="8cbc8-120">The **Data** tab is selected by default and shows a table listing details about individual records of the entity.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="8cbc8-121">![Tabuľka Polia](media/data-manager-entities-fields.PNG "Tabuľka Polia")</span><span class="sxs-lookup"><span data-stu-id="8cbc8-121">![Fields table](media/data-manager-entities-fields.PNG "Fields table")</span></span>

- <span data-ttu-id="8cbc8-122">Karta **Polia** zobrazuje tabuľku na kontrolu podrobností vybratej entity, ako sú napríklad názvy polí, typy údajov a typy.</span><span class="sxs-lookup"><span data-stu-id="8cbc8-122">The **Fields** tab shows a table to review details for the selected entity, such as field names, data types, and types.</span></span> <span data-ttu-id="8cbc8-123">Stĺpec **Typ** zobrazuje typy asociované s modelom Common Data Model, ktoré sú buď automaticky identifikované systémom alebo [manuálne priradené](map-entities.md) používateľmi.</span><span class="sxs-lookup"><span data-stu-id="8cbc8-123">The **Type** column shows Common Data Model associated types, which are either auto-identified by the system or [manually mapped](map-entities.md) by users.</span></span> <span data-ttu-id="8cbc8-124">Ide o sémantické typy, ktoré sa môžu odlišovať od typov údajov atribútov, napríklad pole *E-mail* nižšie má typ údajov *Text*, ale jeho (sémantický) typ modelu Common Data Model môže byť *E-mail* alebo *EmailAddress*.</span><span class="sxs-lookup"><span data-stu-id="8cbc8-124">These are semantic types that can differ from the attributes' data types—for example, the field *Email* below has a data type *Text* but its (semantic) Common Data Model type might be *Email* or *EmailAddress*.</span></span>

> [!NOTE]
> <span data-ttu-id="8cbc8-125">Obidve tabuľky zobrazujú iba vzorku údajov entity.</span><span class="sxs-lookup"><span data-stu-id="8cbc8-125">Both tables show only a sample of your entity's data.</span></span> <span data-ttu-id="8cbc8-126">Ak chcete zobraziť celú množinu údajov, prejdite na stránku **Zdroje údajov**, vyberte entitu, vyberte položku **Upraviť** a potom zobrazte údaje tejto entity pomocou editora Power Query, ako je vysvetlené v [zdrojoch údajov](data-sources.md).</span><span class="sxs-lookup"><span data-stu-id="8cbc8-126">To view the full data set, go to the **Data sources** page, select an entity, select **Edit**, and then view this entity's data with the Power Query editor as explained in [Data sources](data-sources.md).</span></span>

<span data-ttu-id="8cbc8-127">Ak sa chcete dozvedieť viac o údajoch prijatých v entite, stĺpec **Súhrn** vám poskytuje niektoré dôležité vlastnosti údajov, ako sú napríklad hodnoty null, chýbajúce údaje, jedinečné hodnoty, počty a rozdelenia, ktoré sa vzťahujú na vaše dáta.</span><span class="sxs-lookup"><span data-stu-id="8cbc8-127">To learn more about the data ingested in the entity, the **Summary** column provides you with some important characteristics of the data, such as nulls, missing values, unique values, counts, and distributions, as applicable to your data.</span></span>

<span data-ttu-id="8cbc8-128">Ak chcete zobraziť súhrn údajov, vyberte ikonu grafu.</span><span class="sxs-lookup"><span data-stu-id="8cbc8-128">Select the chart icon to see the summary of the data.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="8cbc8-129">![Súhrnný symbol](media/data-manager-entities-summary.png "Tabuľka so zhrnutím údajov")</span><span class="sxs-lookup"><span data-stu-id="8cbc8-129">![Summary symbol](media/data-manager-entities-summary.png "Data summary table")</span></span>

### <a name="next-step"></a><span data-ttu-id="8cbc8-130">Nasledujúci krok</span><span class="sxs-lookup"><span data-stu-id="8cbc8-130">Next step</span></span>

<span data-ttu-id="8cbc8-131">Pozrite si tému [Zjednotenie](data-unification.md), kde sa dozviete ,ako *mapovať*, *zosúladiť* a *zlúčiť* prijaté údaje.</span><span class="sxs-lookup"><span data-stu-id="8cbc8-131">See the [Unify](data-unification.md) topic to learn how to *map*, *match*, and *merge* the ingested data.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]