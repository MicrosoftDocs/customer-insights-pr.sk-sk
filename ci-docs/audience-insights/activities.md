---
title: Aktivity zákazníkov
description: Definujte aktivity zákazníkov a zobrazte ich na časovej osi zákazníkov.
ms.date: 04/07/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.openlocfilehash: 342aeb33f652d5d60cd25e13969766954bf56370
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 06/24/2021
ms.locfileid: "6304945"
---
# <a name="customer-activities"></a><span data-ttu-id="6c76f-103">Aktivity zákazníkov</span><span class="sxs-lookup"><span data-stu-id="6c76f-103">Customer activities</span></span>

<span data-ttu-id="6c76f-104">Spojte aktivity zákazníkov z [rôznych zdrojov údajov](data-sources.md) v Dynamics 365 Customer Insights a vytvorte časovú os s chronologickým zoznamom aktivít.</span><span class="sxs-lookup"><span data-stu-id="6c76f-104">Combine customer activities from [various data sources](data-sources.md) in Dynamics 365 Customer Insights to create a timeline that lists the activities chronologically.</span></span> <span data-ttu-id="6c76f-105">Zahrňte časovú os do aplikácií Dynamics 365 pomocou [doplnku Zákaznícka karta](customer-card-add-in.md) riešenie, alebo na tabuľu Power BI.</span><span class="sxs-lookup"><span data-stu-id="6c76f-105">Include the timeline in Dynamics 365 apps with the [Customer Card add-in](customer-card-add-in.md) solution, or in a Power BI dashboard.</span></span>

## <a name="define-an-activity"></a><span data-ttu-id="6c76f-106">Definícia aktivity</span><span class="sxs-lookup"><span data-stu-id="6c76f-106">Define an activity</span></span>

<span data-ttu-id="6c76f-107">Vaše zdroje údajov môžu zahŕňať entity s údajmi o transakciách a aktivitách z viacerých zdrojov údajov.</span><span class="sxs-lookup"><span data-stu-id="6c76f-107">Your data sources can include entities with transactional and activity data from multiple data sources.</span></span> <span data-ttu-id="6c76f-108">Identifikujte tieto entity a vyberte aktivity, ktoré chcete zobraziť na časovej osi zákazníka.</span><span class="sxs-lookup"><span data-stu-id="6c76f-108">Identify these entities and select the activities you want to view on the customer's timeline.</span></span> <span data-ttu-id="6c76f-109">Vyberte entitu, ktorá obsahuje vašu cieľovú aktivitu alebo aktivity.</span><span class="sxs-lookup"><span data-stu-id="6c76f-109">Choose the entity that includes your target activity or activities.</span></span>

> [!NOTE]
> <span data-ttu-id="6c76f-110">Entita musí mať aspoň jeden atribút typu **Dátum**, aby ste boli zahrnutí do časovej osi zákazníka a bez polí **Dátum** nemôžete pridávať entity.</span><span class="sxs-lookup"><span data-stu-id="6c76f-110">An entity must have at least one attribute of type **Date** to be included in a customer timeline and you can't add entities without **Date** fields.</span></span> <span data-ttu-id="6c76f-111">Ovládací prvok **Pridať aktivitu** nie je povolená, ak takáto entita nie je nájdená.</span><span class="sxs-lookup"><span data-stu-id="6c76f-111">The **Add activity** control is disabled if no such entity is found.</span></span>

1. <span data-ttu-id="6c76f-112">V prehľadoch cieľových skupín prejdite na **Údaje** > **Aktivity**.</span><span class="sxs-lookup"><span data-stu-id="6c76f-112">In audience insights, go to **Data** > **Activities**.</span></span>

1. <span data-ttu-id="6c76f-113">Stlačte možnosť **Pridať aktivitu** na spustenie riadeného zážitku pre proces nastavenia aktivity.</span><span class="sxs-lookup"><span data-stu-id="6c76f-113">Select **Add activity** to start the guided experience for the activity setup process.</span></span>

1. <span data-ttu-id="6c76f-114">V kroku **Údaje o aktivite** nastavte hodnoty pre nasledujúce polia:</span><span class="sxs-lookup"><span data-stu-id="6c76f-114">In the **Activity data** step, set the values for the following fields:</span></span>

   - <span data-ttu-id="6c76f-115">**Názov aktivity**: Vyberte názov svojej aktivity.</span><span class="sxs-lookup"><span data-stu-id="6c76f-115">**Activity name**: Select a name for your activity.</span></span>
   - <span data-ttu-id="6c76f-116">**Entita**: Vyberte entitu, ktorá obsahuje údaje o transakciách alebo aktivitách.</span><span class="sxs-lookup"><span data-stu-id="6c76f-116">**Entity**: Select an entity that includes transactional or activity data.</span></span>
   - <span data-ttu-id="6c76f-117">**Primárny kľúč**: Slúži na výber poľa, ktoré jedinečne identifikuje záznam.</span><span class="sxs-lookup"><span data-stu-id="6c76f-117">**Primary key**: Select the field that uniquely identifies a record.</span></span> <span data-ttu-id="6c76f-118">Nemalo by obsahovať duplicitné hodnoty, prázdne ani chýbajúce hodnoty.</span><span class="sxs-lookup"><span data-stu-id="6c76f-118">It shouldn't contain any duplicate values, empty values, or missing values.</span></span>

   :::image type="content" source="media/Activity_Wizard1.PNG" alt-text="Nastavte údaje o činnosti pomocou názvu, entity a primárneho kľúča.":::

1. <span data-ttu-id="6c76f-120">Stlačte možnosť **Ďalej** a prejdite na ďalší krok.</span><span class="sxs-lookup"><span data-stu-id="6c76f-120">Select **Next** to go to the next step.</span></span>

1. <span data-ttu-id="6c76f-121">V kroku **Vzťah** nakonfigurujte podrobnosti na pripojenie údajov o svojej aktivite k príslušnému zákazníkovi.</span><span class="sxs-lookup"><span data-stu-id="6c76f-121">In the **Relationship** step, configure the details to connect your activity data to its corresponding customer.</span></span> <span data-ttu-id="6c76f-122">Tento krok vizualizuje spojenie medzi entitami.</span><span class="sxs-lookup"><span data-stu-id="6c76f-122">This step visualizes the connection between entities.</span></span>  

   - <span data-ttu-id="6c76f-123">**Prvé**: Cudzie pole vo vašej entite aktivity, ktoré sa použije na nadviazanie vzťahu s inou entitou.</span><span class="sxs-lookup"><span data-stu-id="6c76f-123">**First**: Foreign field in your activity entity that will be used to establish a relationship with another entity.</span></span>
   - <span data-ttu-id="6c76f-124">**Druhé**: Zodpovedajúca zdrojová entita zákazníka, s ktorou bude vaša entita aktivity vo vzťahu.</span><span class="sxs-lookup"><span data-stu-id="6c76f-124">**Second**: Corresponding source customer entity with which your activity entity will be in relationship.</span></span> <span data-ttu-id="6c76f-125">Môžete sa týkať iba zdrojových entít zákazníka, ktoré sa používajú v procese zjednotenia údajov.</span><span class="sxs-lookup"><span data-stu-id="6c76f-125">You can only relate to source customer entities that are used in the data unification process.</span></span>
   - <span data-ttu-id="6c76f-126">**Tretie**: Ak vzťah medzi touto entitou aktivity a vybranou entitou zdrojového zákazníka už existuje, názov vzťahu bude v režime iba na čítanie.</span><span class="sxs-lookup"><span data-stu-id="6c76f-126">**Third**: If a relationship between this activity entity and the selected source customer entity already exists, the relationship name will be in read-only mode.</span></span> <span data-ttu-id="6c76f-127">Ak taký vzťah neexistuje, vytvorí sa nový vzťah s menom, ktoré uvediete v tomto poli.</span><span class="sxs-lookup"><span data-stu-id="6c76f-127">If no such relationship exists, a new relationship will be created with the name you provide in this box.</span></span>

   :::image type="content" source="media/Activity_Wizard2.PNG" alt-text="Definovanie vzťahu entity.":::

1. <span data-ttu-id="6c76f-129">Stlačte možnosť **Ďalej** a prejdite na ďalší krok.</span><span class="sxs-lookup"><span data-stu-id="6c76f-129">Select **Next** to go to the next step.</span></span> 

1. <span data-ttu-id="6c76f-130">V kroku **Zjednotenie činnosti** vyberte udalosť aktivity a čas začiatku vašej aktivity.</span><span class="sxs-lookup"><span data-stu-id="6c76f-130">In the **Activity unification** step, choose the activity event and the start time of your activity.</span></span> 
   - <span data-ttu-id="6c76f-131">**Povinné polia**</span><span class="sxs-lookup"><span data-stu-id="6c76f-131">**Required fields**</span></span>
      - <span data-ttu-id="6c76f-132">**Aktivita udalosti**: Pole, ktoré je udalosťou pre túto aktivitu.</span><span class="sxs-lookup"><span data-stu-id="6c76f-132">**Event activity**: Field that is the event for this activity.</span></span>
      - <span data-ttu-id="6c76f-133">**Časová značka**: Pole, ktoré predstavuje začiatočný čas vašej aktivity.</span><span class="sxs-lookup"><span data-stu-id="6c76f-133">**Timestamp**: Field that represents the start time of your activity.</span></span>

   - <span data-ttu-id="6c76f-134">**Voliteľné polia**</span><span class="sxs-lookup"><span data-stu-id="6c76f-134">**Optional fields**</span></span>
      - <span data-ttu-id="6c76f-135">**Ďalšie podrobnosti**: Pole s relevantnými informáciami pre túto aktivitu.</span><span class="sxs-lookup"><span data-stu-id="6c76f-135">**Additional detail**: Field with relevant information for this activity.</span></span>
      - <span data-ttu-id="6c76f-136">**Ikona**: Ikona, ktorá najlepšie vystihuje tento typ aktivity.</span><span class="sxs-lookup"><span data-stu-id="6c76f-136">**Icon**: Icon that best represents this activity type.</span></span>
      - <span data-ttu-id="6c76f-137">**Webová adresa**: Pole obsahujúce adresu URL s informáciami o tejto aktivite.</span><span class="sxs-lookup"><span data-stu-id="6c76f-137">**Web address**: Field containing a URL with information about this activity.</span></span> <span data-ttu-id="6c76f-138">Napríklad transakčný systém, ktorý poskytuje zdroje tejto aktivity.</span><span class="sxs-lookup"><span data-stu-id="6c76f-138">For example, the transactional system that sources this activity.</span></span> <span data-ttu-id="6c76f-139">Táto adresa URL môže byť ľubovoľným poľom zo zdroja údajov alebo môže byť vytvorená ako nové pole pomocou transformácie Power Query.</span><span class="sxs-lookup"><span data-stu-id="6c76f-139">This URL can be any field from the data source, or it can be constructed as a new field using a Power Query transformation.</span></span> <span data-ttu-id="6c76f-140">Údaje adresy URL budú uložené v entite *Zjednotená aktivita*, ktorú je možné spotrebovať v následnom použití [API](apis.md).</span><span class="sxs-lookup"><span data-stu-id="6c76f-140">The URL data will be stored in the *Unified Activity* entity, which can be consumed downstream using [APIs](apis.md).</span></span>
   
   :::image type="content" source="media/Activity_Wizard3.PNG" alt-text="Zadajte údaje o aktivite zákazníka v entite zjednotenej aktivity.":::

1. <span data-ttu-id="6c76f-142">Výberom tlačidla **Ďalej** prejdete na ďalší krok.</span><span class="sxs-lookup"><span data-stu-id="6c76f-142">Select **Next** to move to the next step.</span></span> <span data-ttu-id="6c76f-143">Môžete stlačiť možnosť **Dokončiť a skontrolovať** a uložiť aktivitu teraz s typom aktivity nastaveným na **Iné**.</span><span class="sxs-lookup"><span data-stu-id="6c76f-143">You can select **Finish and review** to save the activity now with the activity type set to **Other**.</span></span> 

1. <span data-ttu-id="6c76f-144">V kroku **Typ aktivity** vyberte typ aktivity a prípadne vyberte, či chcete sémanticky mapovať niektoré typy aktivít pre použitie v iných oblastiach Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="6c76f-144">In the **Activity Type** step, choose the activity type and optionally select if you want to semantically map some of the activity types for use in other areas of Customer Insights.</span></span> <span data-ttu-id="6c76f-145">V súčasnosti typy aktivít *Subscription* a *SalesOrderLine* možno sémanticky mapovať po odsúhlasení mapovania polí.</span><span class="sxs-lookup"><span data-stu-id="6c76f-145">Currently, *Subscription* and *SalesOrderLine* activity types can be semantically mapped after agreeing to map the fields.</span></span> <span data-ttu-id="6c76f-146">Ak typ aktivity nie je pre novú aktivitu relevantný, môžete stlačiť možnosť *Iné* alebo *Vytvoriť nový* pre vlastný typ aktivity.</span><span class="sxs-lookup"><span data-stu-id="6c76f-146">If an activity type isn't relevant for the new activity, you can choose *Other* or *Create new* for a custom activity type.</span></span>

1. <span data-ttu-id="6c76f-147">Výberom tlačidla **Ďalej** prejdete na ďalší krok.</span><span class="sxs-lookup"><span data-stu-id="6c76f-147">Select **Next** to move to the next step.</span></span> 

1. <span data-ttu-id="6c76f-148">V kroku **Revízia** overte svoje výbery.</span><span class="sxs-lookup"><span data-stu-id="6c76f-148">In the **Review** step, verify your selections.</span></span> <span data-ttu-id="6c76f-149">Vráťte sa k niektorému z predchádzajúcich krokov a v prípade potreby aktualizujte informácie.</span><span class="sxs-lookup"><span data-stu-id="6c76f-149">Go back to any of the previous steps and update the information if necessary.</span></span>

   :::image type="content" source="media/Activity_Wizard5.PNG" alt-text="Skontrolujte aktivitu v zadaných poliach.":::
   
1. <span data-ttu-id="6c76f-151">Stlačte možnosť **Uložiť aktivitu** a použite svoje zmeny a stlačením možnosti **Hotovo** sa vráťte späť do časti **Údaje** > **Činnosti**.</span><span class="sxs-lookup"><span data-stu-id="6c76f-151">Select **Save activity** to apply your changes and select **Done** to go back to **Data** > **Activities**.</span></span> <span data-ttu-id="6c76f-152">Tu uvidíte, ktoré aktivity sú nastavené na zobrazenie na časovej osi.</span><span class="sxs-lookup"><span data-stu-id="6c76f-152">Here you see which activities are set to show in the timeline.</span></span> 

1. <span data-ttu-id="6c76f-153">Na stránke **Činnosti** stlačte možnosť **Spustiť** na spracovanie činnosti.</span><span class="sxs-lookup"><span data-stu-id="6c76f-153">On the **Activities** page, select **Run** to process the activity.</span></span> 

> [!TIP]
> <span data-ttu-id="6c76f-154">Existuje [šesť druhov stavov](system.md#status-types) pre úlohy/procesy.</span><span class="sxs-lookup"><span data-stu-id="6c76f-154">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="6c76f-155">Okrem toho väčšina procesov [závisí na ďalších nadväzujúcich procesoch](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="6c76f-155">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="6c76f-156">Môžete si vybrať stav procesu a zobraziť podrobnosti o priebehu celej úlohy.</span><span class="sxs-lookup"><span data-stu-id="6c76f-156">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="6c76f-157">Po výbere **Pozrieť detaily** pre jednu z úloh úlohy nájdete ďalšie informácie: čas spracovania, posledný dátum spracovania a všetky chyby a varovania spojené s úlohou.</span><span class="sxs-lookup"><span data-stu-id="6c76f-157">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>


## <a name="manage-existing-activities"></a><span data-ttu-id="6c76f-158">Spravovanie existujúcich činností</span><span class="sxs-lookup"><span data-stu-id="6c76f-158">Manage existing activities</span></span>

<span data-ttu-id="6c76f-159">V časti **Údaje** > **Činnosti**, môžete zobraziť všetky svoje uložené aktivity a spravovať ich.</span><span class="sxs-lookup"><span data-stu-id="6c76f-159">On **Data** > **Activities**, you can view all your saved activities, and manage them.</span></span> <span data-ttu-id="6c76f-160">Každú aktivitu predstavuje riadok, ktorý obsahuje aj podrobnosti o zdroji, entite a type aktivity.</span><span class="sxs-lookup"><span data-stu-id="6c76f-160">Each activity is represented by a row that also includes details about the source, the entity, and the activity type.</span></span>

<span data-ttu-id="6c76f-161">Po výbere aktivity sú k dispozícii nasledujúce akcie.</span><span class="sxs-lookup"><span data-stu-id="6c76f-161">The following actions are available when you select an activity.</span></span> 

- <span data-ttu-id="6c76f-162">**Upraviť**: Otvorí nastavenie aktivity v kroku kontroly.</span><span class="sxs-lookup"><span data-stu-id="6c76f-162">**Edit**: Opens the activity setup on the review step.</span></span> <span data-ttu-id="6c76f-163">Od tohto kroku môžete zmeniť ktorúkoľvek alebo celú súčasnú konfiguráciu.</span><span class="sxs-lookup"><span data-stu-id="6c76f-163">You can change any or all of the current configuration from this step.</span></span> <span data-ttu-id="6c76f-164">Po zmene konfigurácie stlačte možnosť **Uložiť aktivitu** a potom stlačením možnosti **Spustiť** spracujte zmeny.</span><span class="sxs-lookup"><span data-stu-id="6c76f-164">After changing the configuration, select **Save activity** and then select **Run** to process the changes.</span></span>

- <span data-ttu-id="6c76f-165">**Premenovať**: Otvorí dialógové okno, kde môžete zadať iný názov pre vybratú aktivitu.</span><span class="sxs-lookup"><span data-stu-id="6c76f-165">**Rename**: Opens a dialog where you can enter a different name for the selected activity.</span></span> <span data-ttu-id="6c76f-166">Zmeny vykonajte výberom položky **Uložiť**.</span><span class="sxs-lookup"><span data-stu-id="6c76f-166">Select **Save** to apply your changes.</span></span>

- <span data-ttu-id="6c76f-167">**Odstrániť**: Otvorí sa dialógové okno na potvrdenie odstránenia vybratej aktivity.</span><span class="sxs-lookup"><span data-stu-id="6c76f-167">**Delete**: Opens a dialog to confirm the deletion of the selected activity.</span></span> <span data-ttu-id="6c76f-168">Môžete tiež odstrániť viac ako jednu aktivitu súčasne výberom aktivít a následným výberom ikony odstránenia.</span><span class="sxs-lookup"><span data-stu-id="6c76f-168">You can also delete more than one activity at once by selecting the activities and then selecting the delete icon.</span></span> <span data-ttu-id="6c76f-169">Vyberte možnosť **Odstrániť** a potvrďte odstránenie.</span><span class="sxs-lookup"><span data-stu-id="6c76f-169">Select **Delete** to confirm the deletion.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
