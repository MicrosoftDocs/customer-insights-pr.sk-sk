---
title: Vzťahy medzi entitami a cestami entít
description: Vytvárajte a spravujte vzťahy medzi entitami z viacerých zdrojov údajov.
ms.date: 06/01/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.openlocfilehash: d5b9566ec88096fec31d8e164a51598159ec26d4
ms.sourcegitcommit: ece48f80a7b470fb33cd36e3096b4f1e9190433a
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 06/03/2021
ms.locfileid: "6171183"
---
# <a name="relationships-between-entities"></a><span data-ttu-id="39976-103">Vzťahy medzi entitami</span><span class="sxs-lookup"><span data-stu-id="39976-103">Relationships between entities</span></span>

<span data-ttu-id="39976-104">Vzťahy spájajú entity a definujú graf vašich údajov, keď entity zdieľajú spoločný identifikátor, cudzí kľúč.</span><span class="sxs-lookup"><span data-stu-id="39976-104">Relationships connect entities and define a graph of your data when entities share a common identifier, a foreign key.</span></span> <span data-ttu-id="39976-105">Tento cudzí kľúč je možné odkazovať z jednej entity na druhú.</span><span class="sxs-lookup"><span data-stu-id="39976-105">This foreign key can be referenced from one entity to another.</span></span> <span data-ttu-id="39976-106">Pripojené entity vám umožňujú definovať segmenty a miery na základe viacerých zdrojov údajov.</span><span class="sxs-lookup"><span data-stu-id="39976-106">Connected entities enable the definition of segments and measures based on multiple data sources.</span></span>

<span data-ttu-id="39976-107">Existujú tri typy vzťahov:</span><span class="sxs-lookup"><span data-stu-id="39976-107">There are three types of relationships:</span></span> 
- <span data-ttu-id="39976-108">Needitovateľné systémové vzťahy, ktoré vytvoril systém ako súčasť procesu zjednotenia údajov</span><span class="sxs-lookup"><span data-stu-id="39976-108">Non-editable system relationships, created by the system as part of the data unification process</span></span>
- <span data-ttu-id="39976-109">Needitovateľné zdedené vzťahy, ktoré sa vytvárajú automaticky z prijímania zdrojov údajov</span><span class="sxs-lookup"><span data-stu-id="39976-109">Non-editable inherited relationships, which are created automatically from ingesting data sources</span></span> 
- <span data-ttu-id="39976-110">Editovateľné vlastné vzťahy, vytvorené a nakonfigurované používateľmi</span><span class="sxs-lookup"><span data-stu-id="39976-110">Editable custom relationships, created and configured by users</span></span>

## <a name="non-editable-system-relationships"></a><span data-ttu-id="39976-111">Needitovateľné systémové vzťahy</span><span class="sxs-lookup"><span data-stu-id="39976-111">Non-editable system relationships</span></span>

<span data-ttu-id="39976-112">Počas zjednotenia údajov sa systémové vzťahy vytvárajú automaticky na základe inteligentného párovania.</span><span class="sxs-lookup"><span data-stu-id="39976-112">During data unification, system relationships are created automatically based on intelligent matching.</span></span> <span data-ttu-id="39976-113">Tieto vzťahy pomáhajú priraďovať záznamy profilu zákazníka k zodpovedajúcim záznamom.</span><span class="sxs-lookup"><span data-stu-id="39976-113">These relationships help relate the customer profile records with corresponding records.</span></span> <span data-ttu-id="39976-114">Nasledujúci diagram ilustruje vytvorenie troch systémových vzťahov.</span><span class="sxs-lookup"><span data-stu-id="39976-114">The following diagram illustrates the creation of three system-based relationships.</span></span> <span data-ttu-id="39976-115">Entita zákazníka sa páruje s inými entitami, aby sa vytvorila zjednotená entita *Zákazník*.</span><span class="sxs-lookup"><span data-stu-id="39976-115">The customer entity is matched with other entities to produce the unified *Customer* entity.</span></span>

:::image type="content" source="media/relationships-entities-merge.png" alt-text="Diagram s cestami vzťahov pre entitu zákazníka s troma vzťahmi 1-n.":::

- <span data-ttu-id="39976-117">**Vzťah *CustomerToContact*** bol vytvorený medzi entitou *Zákazník* a entitou *Kontakt*.</span><span class="sxs-lookup"><span data-stu-id="39976-117">***CustomerToContact* relationship** was created between the *Customer* entity and the *Contact* entity.</span></span> <span data-ttu-id="39976-118">Entita *Zákazník* získa kľúčové pole **Contact_contactID**, ktoré sa bude vzťahovať na kľúčové pole entity *Kontakt* **contactID**.</span><span class="sxs-lookup"><span data-stu-id="39976-118">The *Customer* entity gets the key field **Contact_contactID** to relate to the *Contact* entity key field **contactID**.</span></span>
- <span data-ttu-id="39976-119">**Vzťah *CustomerToAccount*** bol vytvorený medzi entitou *Zákazník* a entitou *Obchodný vzťah*.</span><span class="sxs-lookup"><span data-stu-id="39976-119">***CustomerToAccount* relationship** was created between the *Customer* entity and the *Account* entity.</span></span> <span data-ttu-id="39976-120">Entita *Zákazník* získa kľúčové pole **Account_accountID**, ktoré sa bude vzťahovať na kľúčové pole entity *Obchodný vzťah* **accountId**.</span><span class="sxs-lookup"><span data-stu-id="39976-120">The *Customer* entity gets the key field **Account_accountID** to relate to the *Account* entity key field **accountID**.</span></span>
- <span data-ttu-id="39976-121">**Vzťah *CustomerToWebAccount*** bol vytvorený medzi entitou *Zákazník* a entitou *WebAccount*.</span><span class="sxs-lookup"><span data-stu-id="39976-121">***CustomerToWebAccount* relationship** was created between the *Customer* entity and the *WebAccount* entity.</span></span> <span data-ttu-id="39976-122">Entita *Zákazník* získa kľúčové pole **WebAccount_webaccountID**, ktoré sa bude vzťahovať na kľúčové pole entity *WebAccount* **webaccountId**.</span><span class="sxs-lookup"><span data-stu-id="39976-122">The *Customer* entity gets the key field **WebAccount_webaccountID** to relate to the *WebAccount* entity key field **webaccountID**.</span></span>

## <a name="non-editable-inherited-relationships"></a><span data-ttu-id="39976-123">Needitovateľné zdedené vzťahy</span><span class="sxs-lookup"><span data-stu-id="39976-123">Non-editable inherited relationships</span></span>

<span data-ttu-id="39976-124">Počas procesu prijímania údajov systém kontroluje existujúce vzťahy v zdrojoch údajov.</span><span class="sxs-lookup"><span data-stu-id="39976-124">During the data ingestion process, the system checks data sources for existing relationships.</span></span> <span data-ttu-id="39976-125">Ak neexistuje žiadny vzťah, systém ich automaticky vytvorí.</span><span class="sxs-lookup"><span data-stu-id="39976-125">If no relationship exists, the system automatically creates them.</span></span> <span data-ttu-id="39976-126">Tieto vzťahy sa tiež používajú v následných procesoch.</span><span class="sxs-lookup"><span data-stu-id="39976-126">These relationships are also used in downstream processes.</span></span>

## <a name="create-a-custom-relationship"></a><span data-ttu-id="39976-127">Vytvorenie vlastného vzťahu</span><span class="sxs-lookup"><span data-stu-id="39976-127">Create a custom relationship</span></span>

<span data-ttu-id="39976-128">Vzťah pozostáva zo *zdrojovej entity*, ktorá obsahuje cudzí kľúč a z *cieľovej entity*, na ktorú cudzí kľúč zdrojovej entity ukazuje.</span><span class="sxs-lookup"><span data-stu-id="39976-128">Relationship consists of a *source entity* containing the foreign key and a *target entity* that the source entity's foreign key points to.</span></span> 

1. <span data-ttu-id="39976-129">V prehľadoch cieľových skupín prejdite na **Údaje** > **Vzťahy**.</span><span class="sxs-lookup"><span data-stu-id="39976-129">In audience insights, go to **Data** > **Relationships**.</span></span>

2. <span data-ttu-id="39976-130">Vyberte **Nový vzťah**.</span><span class="sxs-lookup"><span data-stu-id="39976-130">Select **New relationship**.</span></span>

3. <span data-ttu-id="39976-131">Na table **Nový vzťah** zadajte nasledovné informácie:</span><span class="sxs-lookup"><span data-stu-id="39976-131">In the **New relationship** pane, provide the following information:</span></span>

   :::image type="content" source="media/relationship-add.png" alt-text="Bočná tabla nového vzťahu s prázdnymi vstupnými poľami.":::

   - <span data-ttu-id="39976-133">**Názov vzťahu**: Názov, ktorý odráža účel vzťahu.</span><span class="sxs-lookup"><span data-stu-id="39976-133">**Relationship name**: Name that reflects the purpose of the relationship.</span></span> <span data-ttu-id="39976-134">Príklad: CustomerToSupportCase.</span><span class="sxs-lookup"><span data-stu-id="39976-134">Example: CustomerToSupportCase.</span></span>
   - <span data-ttu-id="39976-135">**Popis**: Popis vzťahu.</span><span class="sxs-lookup"><span data-stu-id="39976-135">**Description**: Description of the relationship.</span></span>
   - <span data-ttu-id="39976-136">**Zdrojová entita**: Entita, ktorá sa vo vzťahu používa ako zdroj.</span><span class="sxs-lookup"><span data-stu-id="39976-136">**Source entity**: Entity that is used as a source in the relationship.</span></span> <span data-ttu-id="39976-137">Príklad: SupportCase.</span><span class="sxs-lookup"><span data-stu-id="39976-137">Example: SupportCase.</span></span>
   - <span data-ttu-id="39976-138">**Cieľová entita**: Entita, ktorá sa vo vzťahu používa ako cieľ.</span><span class="sxs-lookup"><span data-stu-id="39976-138">**Target entity**: Entity that is used as a target in the relationship.</span></span> <span data-ttu-id="39976-139">Príklad: Zákazník.</span><span class="sxs-lookup"><span data-stu-id="39976-139">Example: Customer.</span></span>
   - <span data-ttu-id="39976-140">**Kardinalita zdroja**: Zadajte kardinalitu zdrojovej entity.</span><span class="sxs-lookup"><span data-stu-id="39976-140">**Source cardinality**: Specify the cardinality of the source entity.</span></span> <span data-ttu-id="39976-141">Kardinalita popisuje počet možných prvkov v množine.</span><span class="sxs-lookup"><span data-stu-id="39976-141">Cardinality describes the number of possible elements in a set.</span></span> <span data-ttu-id="39976-142">Vždy súvisí s cieľovou kardinalitou.</span><span class="sxs-lookup"><span data-stu-id="39976-142">It always relates to the target cardinality.</span></span> <span data-ttu-id="39976-143">Môžete si vybrať **Jeden** a **Mnoho**.</span><span class="sxs-lookup"><span data-stu-id="39976-143">You can choose between **One** and **Many**.</span></span> <span data-ttu-id="39976-144">Podporované sú iba vzťahy „mnoho k jednému“ a „jeden k jednému“.</span><span class="sxs-lookup"><span data-stu-id="39976-144">Only many-to-one and one-to-one relationships are supported.</span></span>  
     - <span data-ttu-id="39976-145">Mnohé k jednému: Na jeden cieľový záznam sa môže vzťahovať viac zdrojových záznamov.</span><span class="sxs-lookup"><span data-stu-id="39976-145">Many-to-one: Multiple source records can relate to one target record.</span></span> <span data-ttu-id="39976-146">Príklad: Viaceré prípady podpory od jedného zákazníka.</span><span class="sxs-lookup"><span data-stu-id="39976-146">Example: Multiple support cases from a single customer.</span></span>
     - <span data-ttu-id="39976-147">Jeden k jednému: Jeden zdrojový záznam sa týka jedného cieľového záznamu.</span><span class="sxs-lookup"><span data-stu-id="39976-147">One-to-one: A single source record relates to a one target record.</span></span> <span data-ttu-id="39976-148">Príklad: Jedno vernostné ID pre jedného zákazníka.</span><span class="sxs-lookup"><span data-stu-id="39976-148">Example: One loyalty ID for a single customer.</span></span>

     > [!NOTE]
     > <span data-ttu-id="39976-149">Vzťahy typu mnohé k mnohým je možné vytvoriť pomocou dvoch vzťahov typu mnohé k jednému a prepojovacej entity, ktorá spája zdrojovú entitu a cieľovú entitu.</span><span class="sxs-lookup"><span data-stu-id="39976-149">Many-to-many relationships can be created using two many-to-one relationships and a linking entity, which connects the source entity and the target entity.</span></span>

   - <span data-ttu-id="39976-150">**Kardinalita cieľa**: Vyberte kardinalitu záznamov cieľovej entity.</span><span class="sxs-lookup"><span data-stu-id="39976-150">**Target cardinality**: Select the cardinality of the target entity records.</span></span> 
   - <span data-ttu-id="39976-151">**Pole zdrojového kľúča**: Pole cudzieho kľúča v zdrojovej entite.</span><span class="sxs-lookup"><span data-stu-id="39976-151">**Source key field**: The foreign key field in the source entity.</span></span> <span data-ttu-id="39976-152">Príklad: SupportCase môže používať CaseID ako pole cudzieho kľúča.</span><span class="sxs-lookup"><span data-stu-id="39976-152">Example: SupportCase could use CaseID as a foreign key field.</span></span>
   - <span data-ttu-id="39976-153">**Pole cieľového kľúča**: Pole kľúča cieľovej entity.</span><span class="sxs-lookup"><span data-stu-id="39976-153">**Target key field**: The key field of the target entity.</span></span> <span data-ttu-id="39976-154">Príklad Zákazník môže použiť kľúčové pole **CustomerID**.</span><span class="sxs-lookup"><span data-stu-id="39976-154">Example Customer could use the **CustomerID** key field.</span></span>

4. <span data-ttu-id="39976-155">Výberom položky **Uložiť** vytvorte vlastný vzťah.</span><span class="sxs-lookup"><span data-stu-id="39976-155">Select **Save** to create the custom relationship.</span></span>

## <a name="view-relationships"></a><span data-ttu-id="39976-156">Zobrazenie vzťahov</span><span class="sxs-lookup"><span data-stu-id="39976-156">View relationships</span></span>

<span data-ttu-id="39976-157">Na stránke Vzťahy sú uvedené všetky vzťahy, ktoré boli vytvorené.</span><span class="sxs-lookup"><span data-stu-id="39976-157">The Relationships page lists all the relationships that have been created.</span></span> <span data-ttu-id="39976-158">Každý riadok predstavuje vzťah, ktorý obsahuje aj podrobnosti o zdrojovej entite, cieľovej entite a kardinalite.</span><span class="sxs-lookup"><span data-stu-id="39976-158">Each row represents a relationship, which also includes details about the source entity, the target entity, and the cardinality.</span></span> 

:::image type="content" source="media/relationships-list.png" alt-text="Zoznam vzťahov a možností na paneli akcií na stránke Vzťahy.":::

<span data-ttu-id="39976-160">Táto stránka ponúka súbor možností pre existujúce a nové vzťahy:</span><span class="sxs-lookup"><span data-stu-id="39976-160">This page offers a set of options for existing and new relationships:</span></span> 
- <span data-ttu-id="39976-161">**Nový vzťah**: [Vytvorenie vlastného vzťahu](#create-a-custom-relationship).</span><span class="sxs-lookup"><span data-stu-id="39976-161">**New Relationship**: [Create a custom relationship](#create-a-custom-relationship).</span></span>
- <span data-ttu-id="39976-162">**Vizualizér**: [Preskúmajte vizualizér vzťahov](#explore-the-relationship-visualizer), aby ste videli sieťový diagram existujúcich vzťahov a ich kardinalitu.</span><span class="sxs-lookup"><span data-stu-id="39976-162">**Visualizer**: [Explore the relationship visualizer](#explore-the-relationship-visualizer) to see a network diagram of the existing relationships and their cardinality.</span></span>
- <span data-ttu-id="39976-163">**Spôsob filtrovania**: Vyberte typ vzťahov, ktoré sa majú zobraziť v zozname.</span><span class="sxs-lookup"><span data-stu-id="39976-163">**Filter by**: Choose the type of relationships to show in the list.</span></span>
- <span data-ttu-id="39976-164">**Hľadať vzťahy**: Použite textové vyhľadávanie vlastností vzťahov.</span><span class="sxs-lookup"><span data-stu-id="39976-164">**Search relationships**: Use a text-based search on properties of the relationships.</span></span>

### <a name="explore-the-relationship-visualizer"></a><span data-ttu-id="39976-165">Preskúmanie vizualizéra vzťahov</span><span class="sxs-lookup"><span data-stu-id="39976-165">Explore the relationship visualizer</span></span>

<span data-ttu-id="39976-166">Vizualizér vzťahov zobrazuje sieťový diagram existujúcich vzťahov medzi prepojenými entitami a ich kardinalitou.</span><span class="sxs-lookup"><span data-stu-id="39976-166">The relationship visualizer shows a network diagram of the existing relationships between connected entities and their cardinality.</span></span>

<span data-ttu-id="39976-167">Ak chcete prispôsobiť zobrazenie, môžete zmeniť polohu políčok ich presunutím na plátno.</span><span class="sxs-lookup"><span data-stu-id="39976-167">To customize the view, you can change the position of the boxes by dragging them on the canvas.</span></span>

:::image type="content" source="media/relationship-visualizer.png" alt-text="Snímka obrazovky sieťového diagramu vizualizátora vzťahov s prepojeniami medzi súvisiacimi entitami.":::

<span data-ttu-id="39976-169">Dostupné možnosti:</span><span class="sxs-lookup"><span data-stu-id="39976-169">Available options:</span></span> 
- <span data-ttu-id="39976-170">**Exportovať ako obrázok**: Uložiť aktuálne zobrazenie ako obrazový súbor.</span><span class="sxs-lookup"><span data-stu-id="39976-170">**Export as image**: Save the current view as an image file.</span></span>
- <span data-ttu-id="39976-171">**Zmena na vodorovné/zvislé rozloženie**: Zmena zarovnania entít a vzťahov.</span><span class="sxs-lookup"><span data-stu-id="39976-171">**Change to horizontal/vertical layout**: Change the alignment of the entities and relationships.</span></span>
- <span data-ttu-id="39976-172">**Úprava**: Aktualizujte vlastnosti vlastných vzťahov na paneli úprav a uložte zmeny.</span><span class="sxs-lookup"><span data-stu-id="39976-172">**Edit**: Update properties of custom relationships in the edit pane and save changes.</span></span>

## <a name="manage-existing-relationships"></a><span data-ttu-id="39976-173">Spravovanie existujúcich vzťahov</span><span class="sxs-lookup"><span data-stu-id="39976-173">Manage existing relationships</span></span> 

<span data-ttu-id="39976-174">Na stránke Vzťahy je každý vzťah predstavovaný riadkom.</span><span class="sxs-lookup"><span data-stu-id="39976-174">On the Relationships page, each relationship is represented by a row.</span></span> 

<span data-ttu-id="39976-175">Vyberte vzťah a jednu z nasledujúcich možností:</span><span class="sxs-lookup"><span data-stu-id="39976-175">Select a relationship and choose one of the following options:</span></span> 
 
- <span data-ttu-id="39976-176">**Úprava**: Aktualizujte vlastnosti vlastných vzťahov na paneli úprav a uložte zmeny.</span><span class="sxs-lookup"><span data-stu-id="39976-176">**Edit**: Update properties of custom relationships in the edit pane and save changes.</span></span>
- <span data-ttu-id="39976-177">**Odstrániť**: Odstrániť vlastné vzťahy.</span><span class="sxs-lookup"><span data-stu-id="39976-177">**Delete**: Delete custom relationships.</span></span>
- <span data-ttu-id="39976-178">**Zobraziť**: Zobraziť vzťahy vytvorené systémom a zdedené.</span><span class="sxs-lookup"><span data-stu-id="39976-178">**View**: View system-created and inherited relationships.</span></span> 

## <a name="next-step"></a><span data-ttu-id="39976-179">Nasledujúci krok</span><span class="sxs-lookup"><span data-stu-id="39976-179">Next step</span></span>

<span data-ttu-id="39976-180">Systémové a vlastné vzťahy sa používajú na [vytváranie segmentov](segments.md) založených na viacerých zdrojoch údajov, ktoré už nie sú v silách.</span><span class="sxs-lookup"><span data-stu-id="39976-180">System and custom relationships are used to [create segments](segments.md) based on multiple data sources that are no longer siloed.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
