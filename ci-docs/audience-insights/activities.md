---
title: Aktivity zákazníkov
description: Definujte aktivity zákazníkov a zobrazte ich na časovej osi zákazníkov.
ms.date: 10/13/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.reviewer: adkuppa
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 1c95cba333266a73959de0a3afe1c8677130a3ec
ms.sourcegitcommit: 334633cbd58f5659d20b4f87252c1a10cc7130db
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 12/03/2020
ms.locfileid: "4667248"
---
# <a name="customer-activities"></a><span data-ttu-id="7c3e0-103">Aktivity zákazníkov</span><span class="sxs-lookup"><span data-stu-id="7c3e0-103">Customer activities</span></span>

<span data-ttu-id="7c3e0-104">Spojte aktivity zákazníkov z [rôznych zdrojov údajov](data-sources.md) v službe Dynamics 365 Customer Insights na vytvorenie časovej osi zákazníkov, ktorá ukazuje aktivity v chronologickom poradí.</span><span class="sxs-lookup"><span data-stu-id="7c3e0-104">Combine customer activities from [various data sources](data-sources.md) in Dynamics 365 Customer Insights to create a customer timeline that lists the activities in chronological order.</span></span> <span data-ttu-id="7c3e0-105">Časovú os môžete zahrnúť do aplikácií pre zapojenie zákazníkov v Dynamics 365 cez [doplnok karty zákazníka](customer-card-add-in.md) alebo v tabuli Power BI.</span><span class="sxs-lookup"><span data-stu-id="7c3e0-105">You can include the timeline in customer engagement apps in Dynamics 365 via the [Customer Card add-in](customer-card-add-in.md), or in a Power BI dashboard.</span></span>

## <a name="define-an-activity"></a><span data-ttu-id="7c3e0-106">Definícia aktivity</span><span class="sxs-lookup"><span data-stu-id="7c3e0-106">Define an activity</span></span>

<span data-ttu-id="7c3e0-107">Vaše zdroje údajov zahŕňajú entity s údajmi o transakciách a aktivitách z viacerých zdrojov údajov.</span><span class="sxs-lookup"><span data-stu-id="7c3e0-107">Your data sources include entities with transactional and activity data from multiple data sources.</span></span> <span data-ttu-id="7c3e0-108">Identifikujte tieto entity a vyberte aktivity, ktoré chcete zobraziť na časovej osi zákazníka.</span><span class="sxs-lookup"><span data-stu-id="7c3e0-108">Identify these entities and select the activities you want to view on the customer's timeline.</span></span> <span data-ttu-id="7c3e0-109">Vyberte entitu, ktorá obsahuje vašu cieľovú aktivitu alebo aktivity.</span><span class="sxs-lookup"><span data-stu-id="7c3e0-109">Choose the entity that includes your target activity or activities.</span></span>

1. <span data-ttu-id="7c3e0-110">V prehľadoch cieľových skupín prejdite na **Údaje** > **Aktivity**.</span><span class="sxs-lookup"><span data-stu-id="7c3e0-110">In audience insights, go to **Data** > **Activities**.</span></span>

1. <span data-ttu-id="7c3e0-111">Vyberte **Pridať aktivitu**.</span><span class="sxs-lookup"><span data-stu-id="7c3e0-111">Select **Add activity**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="7c3e0-112">Entita musí mať aspoň jeden atribút typu **Dátum**, aby ste boli zahrnutí do časovej osi zákazníka a bez polí **Dátum** nemôžete pridávať entity.</span><span class="sxs-lookup"><span data-stu-id="7c3e0-112">An entity must have at least one attribute of type **Date** to be included in a customer timeline and you can't add entities without **Date** fields.</span></span> <span data-ttu-id="7c3e0-113">Ovládací prvok **Pridať aktivitu** nie je povolená, ak takáto entita nie je nájdená.</span><span class="sxs-lookup"><span data-stu-id="7c3e0-113">The **Add activity** control is disabled if no such entity is found.</span></span>

1. <span data-ttu-id="7c3e0-114">V table **Pridať aktivitu** nastavte hodnoty pre nasledujúce polia:</span><span class="sxs-lookup"><span data-stu-id="7c3e0-114">In the **Add activity** pane, set the values for the following fields:</span></span>

   - <span data-ttu-id="7c3e0-115">**Entita**: Vyberte entitu, ktorá obsahuje údaje o transakciách alebo aktivitách.</span><span class="sxs-lookup"><span data-stu-id="7c3e0-115">**Entity**: Select an entity that includes transactional or activity data.</span></span>
   - <span data-ttu-id="7c3e0-116">**Primárny kľúč**: Slúži na výber poľa, ktoré jedinečne identifikuje záznam.</span><span class="sxs-lookup"><span data-stu-id="7c3e0-116">**Primary key**: Select the field that uniquely identifies a record.</span></span> <span data-ttu-id="7c3e0-117">Nemalo by obsahovať duplicitné hodnoty, prázdne ani chýbajúce hodnoty.</span><span class="sxs-lookup"><span data-stu-id="7c3e0-117">It shouldn't contain any duplicate values, empty values, or missing values.</span></span>
   - <span data-ttu-id="7c3e0-118">**Časová značka**: Vyberte pole, ktoré predstavuje začiatočný čas vašej aktivity.</span><span class="sxs-lookup"><span data-stu-id="7c3e0-118">**Timestamp**: Select the field that represents the start time of your activity.</span></span>
   - <span data-ttu-id="7c3e0-119">**Udalosť**: Vyberte pole, ktoré je udalosťou aktivity.</span><span class="sxs-lookup"><span data-stu-id="7c3e0-119">**Event**: Select the field that is the event for the activity.</span></span>
   - <span data-ttu-id="7c3e0-120">**Webová adresa**: Vyberte pole, ktoré predstavuje adresu URL a poskytuje ďalšie informácie o tejto aktivite.</span><span class="sxs-lookup"><span data-stu-id="7c3e0-120">**Web address**: Select the field that represents a URL providing additional information about this activity.</span></span> <span data-ttu-id="7c3e0-121">Napríklad transakčný systém, ktorý poskytuje zdroje tejto aktivity.</span><span class="sxs-lookup"><span data-stu-id="7c3e0-121">For example, the transactional system that sources this activity.</span></span> <span data-ttu-id="7c3e0-122">Táto adresa URL môže byť ľubovoľným poľom zo zdroja údajov alebo môže byť vytvorená ako nové pole pomocou transformácie Power Query.</span><span class="sxs-lookup"><span data-stu-id="7c3e0-122">This URL can be any field from the data source, or it can be constructed as a new field using a Power Query transformation.</span></span> <span data-ttu-id="7c3e0-123">Tieto údaje URL sa uložia v entite Unified Activity, ktorú je možné následne konzumovať pomocou rozhraní API.</span><span class="sxs-lookup"><span data-stu-id="7c3e0-123">This URL data will be stored in the Unified Activity entity, which can be consumed downstream using APIs.</span></span>
   - <span data-ttu-id="7c3e0-124">**Podrobnosti**: Voliteľne vyberte pole, ktoré sa pridá pre ďalšie podrobnosti.</span><span class="sxs-lookup"><span data-stu-id="7c3e0-124">**Details**: Optionally, select the field that is added for additional details.</span></span>
   - <span data-ttu-id="7c3e0-125">**Ikona**: Voliteľne, vyberte ikonu, ktorá predstavuje túto aktivitu.</span><span class="sxs-lookup"><span data-stu-id="7c3e0-125">**Icon**: Optionally, select the icon that represents this activity.</span></span>
   - <span data-ttu-id="7c3e0-126">**Typ aktivity**: Definujte odkaz na typ aktivity na Common Data Model, ktorý najlepšie popisuje sémantickú definíciu aktivity.</span><span class="sxs-lookup"><span data-stu-id="7c3e0-126">**Activity Type**: Define the activity type reference to Common Data Model that best describes the semantic definition of the activity.</span></span>

1. <span data-ttu-id="7c3e0-127">V sekcii **Nastavenie vzťahu** nakonfigurujte podrobnosti na pripojenie údajov o vašej aktivite k príslušnému zákazníkovi.</span><span class="sxs-lookup"><span data-stu-id="7c3e0-127">In the **Set up relationship** section, configure the details to connect your activity data to its corresponding customer.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="7c3e0-128">![Definovanie vzťahu entity](media/activities-entities-define.png "Definovanie vzťahu entity")</span><span class="sxs-lookup"><span data-stu-id="7c3e0-128">![Define the entity relationship](media/activities-entities-define.png "Define the entity relationship")</span></span>

    - <span data-ttu-id="7c3e0-129">**Pole entity Aktivita**: Vyberte pole v entite aktivity, ktoré sa použije na nadviazanie vzťahu s inou entitou.</span><span class="sxs-lookup"><span data-stu-id="7c3e0-129">**Activity entity field**: Select the field in your activity entity that will be used to establish a relationship with another entity.</span></span>
    - <span data-ttu-id="7c3e0-130">**Entita Zákazník**: Vyberte zodpovedajúcu zdrojovú entitu zákazníka, s ktorou bude vaša entita aktivity vo vzťahu.</span><span class="sxs-lookup"><span data-stu-id="7c3e0-130">**Customer entity**: Select the corresponding source customer entity with which your activity entity will be in relationship.</span></span> <span data-ttu-id="7c3e0-131">Môžete sa vzťahovať iba na tie zdrojové entity zákazníkov, ktoré sa používajú v procese zjednotenia údajov.</span><span class="sxs-lookup"><span data-stu-id="7c3e0-131">You can relate to only those source customer entities that are used in the data unification process.</span></span>
    - <span data-ttu-id="7c3e0-132">**Pole entity zákazníka**: Toto pole zobrazuje primárny kľúč zdrojovej entity zákazníka vybratý v procese mapovania.</span><span class="sxs-lookup"><span data-stu-id="7c3e0-132">**Customer entity field**: This field shows the primary key of the source customer entity as selected in the map process.</span></span> <span data-ttu-id="7c3e0-133">Toto pole primárneho kľúča v zdrojovej entite zákazníka sa používa na vytvorenie vzťahu s entitou aktivity.</span><span class="sxs-lookup"><span data-stu-id="7c3e0-133">This primary key field in the source customer entity is used to establish a relationship with the activity entity.</span></span>
    - <span data-ttu-id="7c3e0-134">**Názov**: Ak už existuje vzťah medzi touto entitou aktivity a vybranou zdrojovou entitou zákazníka, názov vzťahu bude v režime len na čítanie.</span><span class="sxs-lookup"><span data-stu-id="7c3e0-134">**Name**: If a relationship between this activity entity and the selected source customer entity already exists, the relationship name will be in read-only mode.</span></span> <span data-ttu-id="7c3e0-135">Ak takýto vzťah neexistuje, vytvorí sa nový vzťah s tu uvedeným menom.</span><span class="sxs-lookup"><span data-stu-id="7c3e0-135">If there no such relationship exists, a new relationship will be created with the name provided here.</span></span>

1. <span data-ttu-id="7c3e0-136">Zmeny vykonajte výberom položky **Uložiť**.</span><span class="sxs-lookup"><span data-stu-id="7c3e0-136">Select **Save** to apply your changes.</span></span>

1. <span data-ttu-id="7c3e0-137">Na stránke **Aktivity** vyberte položku **Spustiť**.</span><span class="sxs-lookup"><span data-stu-id="7c3e0-137">On the **Activities** page, select **Run**.</span></span>

> [!TIP]
> <span data-ttu-id="7c3e0-138">Existuje [šesť druhov stavov](system.md#status-types) pre úlohy/procesy.</span><span class="sxs-lookup"><span data-stu-id="7c3e0-138">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="7c3e0-139">Okrem toho väčšina procesov [závisí na ďalších nadväzujúcich procesoch](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="7c3e0-139">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="7c3e0-140">Môžete si vybrať stav procesu a zobraziť podrobnosti o priebehu celej úlohy.</span><span class="sxs-lookup"><span data-stu-id="7c3e0-140">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="7c3e0-141">Po výbere **Pozrieť detaily** pre jednu z úloh úlohy nájdete ďalšie informácie: čas spracovania, posledný dátum spracovania a všetky chyby a varovania spojené s úlohou.</span><span class="sxs-lookup"><span data-stu-id="7c3e0-141">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="edit-an-activity"></a><span data-ttu-id="7c3e0-142">Úprava aktivity</span><span class="sxs-lookup"><span data-stu-id="7c3e0-142">Edit an activity</span></span>

1. <span data-ttu-id="7c3e0-143">V prehľadoch cieľových skupín prejdite na **Údaje** > **Aktivity**.</span><span class="sxs-lookup"><span data-stu-id="7c3e0-143">In audience insights, go to **Data** > **Activities**.</span></span>

2. <span data-ttu-id="7c3e0-144">Vyberte entity aktivity, ktorú chcete upraviť a potom položku **Upraviť**.</span><span class="sxs-lookup"><span data-stu-id="7c3e0-144">Select the activity entity you want to edit and select **Edit**.</span></span> <span data-ttu-id="7c3e0-145">Alebo môžete umiestniť kurzor nad riadok entity a vybrať ikonu **Upraviť**.</span><span class="sxs-lookup"><span data-stu-id="7c3e0-145">Or, you can hover over the entity row and select the **Edit** icon.</span></span>

3. <span data-ttu-id="7c3e0-146">Kliknite na ikonu **Upraviť**.</span><span class="sxs-lookup"><span data-stu-id="7c3e0-146">Click on the **Edit** icon.</span></span>

4. <span data-ttu-id="7c3e0-147">Na table **Upraviť aktivitu** aktualizujte hodnoty a vyberte položku **Uložiť**.</span><span class="sxs-lookup"><span data-stu-id="7c3e0-147">In the **Edit activity** pane, update the values and select **Save**.</span></span>

5. <span data-ttu-id="7c3e0-148">Na stránke **Aktivity** vyberte položku **Spustiť**.</span><span class="sxs-lookup"><span data-stu-id="7c3e0-148">On the **Activities** page, select **Run**.</span></span>

## <a name="delete-an-activity"></a><span data-ttu-id="7c3e0-149">Odstránenie aktivity</span><span class="sxs-lookup"><span data-stu-id="7c3e0-149">Delete an activity</span></span>

1. <span data-ttu-id="7c3e0-150">V prehľadoch cieľových skupín prejdite na **Údaje** > **Aktivity**.</span><span class="sxs-lookup"><span data-stu-id="7c3e0-150">In audience insights, go to **Data** > **Activities**.</span></span>

2. <span data-ttu-id="7c3e0-151">Vyberte entitu aktivity, ktorú chcete odstrániť a potom položku **Odstrániť**.</span><span class="sxs-lookup"><span data-stu-id="7c3e0-151">Select the activity entity you want to remove and select **Delete**.</span></span> <span data-ttu-id="7c3e0-152">Alebo môžete umiestniť kurzor nad riadok entity a vybrať ikonu **Odstrániť**.</span><span class="sxs-lookup"><span data-stu-id="7c3e0-152">Or, you can hover over the entity row and select the **Delete** icon.</span></span> <span data-ttu-id="7c3e0-153">Okrem toho môžete vybrať viac entít aktivity, ktoré sa majú odstrániť naraz.</span><span class="sxs-lookup"><span data-stu-id="7c3e0-153">Additionally, you can select multiple activity entities to be deleted at once.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="7c3e0-154">![Úprava alebo odstránenie vzťahu entity](media/activities-entities-edit-delete.png "Úprava alebo odstránenie vzťahu entity")</span><span class="sxs-lookup"><span data-stu-id="7c3e0-154">![Edit or delete the entity relationship](media/activities-entities-edit-delete.png "Edit or delete the entity relationship")</span></span>

3. <span data-ttu-id="7c3e0-155">Vyberte ikonu **Odstrániť**.</span><span class="sxs-lookup"><span data-stu-id="7c3e0-155">Select on the **Delete** icon.</span></span>

4. <span data-ttu-id="7c3e0-156">Potvrďte odstránenie.</span><span class="sxs-lookup"><span data-stu-id="7c3e0-156">Confirm your deletion.</span></span>
