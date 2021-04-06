---
title: Vzťahy medzi entitami a cestami entít
description: Vytvárajte a spravujte vzťahy medzi entitami z viacerých zdrojov údajov.
ms.date: 04/14/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: c25bfcb8e2a8223498dd1a5e8cfb3712a40ab85e
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 03/15/2021
ms.locfileid: "5595231"
---
# <a name="relationships-between-entities"></a><span data-ttu-id="d153b-103">Vzťahy medzi entitami</span><span class="sxs-lookup"><span data-stu-id="d153b-103">Relationships between entities</span></span>

<span data-ttu-id="d153b-104">Vzťahy vám pomôžu prepojiť entity a vygenerovať graf vašich údajov, keď entity zdieľajú spoločný identifikátor (cudzí kľúč), na ktorý je možné odkazovať z jednej entity na druhú.</span><span class="sxs-lookup"><span data-stu-id="d153b-104">Relationships help you connect entities and generate a graph of your data when entities share a common identifier (foreign key) that can be referenced from one entity to another.</span></span> <span data-ttu-id="d153b-105">Pripojené entity vám umožňujú definovať segmenty a miery na základe viacerých zdrojov údajov.</span><span class="sxs-lookup"><span data-stu-id="d153b-105">Connected entities enable you to define segments and measures based on multiple data sources.</span></span>

<span data-ttu-id="d153b-106">Existujú dva typy vzťahov.</span><span class="sxs-lookup"><span data-stu-id="d153b-106">There are two types of relationships.</span></span> <span data-ttu-id="d153b-107">Neupraviteľné systémové vzťahy, ktoré sa vytvárajú automaticky, a vlastné vzťahy vytvárané a konfigurované používateľmi.</span><span class="sxs-lookup"><span data-stu-id="d153b-107">Non-editable system relationships, which are created automatically, and custom relationships created and configured by users.</span></span>

<span data-ttu-id="d153b-108">Počas procesov zosúlaďovania a zlúčenia sa vytvárajú systémové vzťahy za scénami na základe inteligentného zosúlaďovania.</span><span class="sxs-lookup"><span data-stu-id="d153b-108">During the match and merge processes, system relationships are created behind the scenes based on intelligent matching.</span></span> <span data-ttu-id="d153b-109">Tieto vzťahy pomáhajú priraďovať záznamy profilu zákazníka k záznamom iných zodpovedajúcich entít.</span><span class="sxs-lookup"><span data-stu-id="d153b-109">These relationships help relate the Customer Profile records with other corresponding entities' records.</span></span> <span data-ttu-id="d153b-110">Nasledujúca schéma ilustruje vytvorenie troch systémových vzťahov, keď sa entita zákazníka zosúladí s ďalšími entitami, aby sa vytvorila konečná entita profilu zákazníka.</span><span class="sxs-lookup"><span data-stu-id="d153b-110">The following diagram illustrates the creation of three system relationships when the customer entity is matched with additional entities to produce the final Customer Profile entity.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="d153b-111">![Vytváranie vzťahu](media/relationships-entities-merge.png "Vytváranie vzťahu")</span><span class="sxs-lookup"><span data-stu-id="d153b-111">![Relationship creation](media/relationships-entities-merge.png "Relationship creation")</span></span>

- <span data-ttu-id="d153b-112">**Vzťah *CustomerToContact*** bol vytvorený medzi entitou zákazníka a entitou kontaktu.</span><span class="sxs-lookup"><span data-stu-id="d153b-112">***CustomerToContact* relationship** was created between the Customer entity and the Contact entity.</span></span> <span data-ttu-id="d153b-113">Entita zákazníka získa kľúčové pole **Contact_contactId**, ktoré sa bude vzťahovať na kľúčové pole entity kontaktu **contactID**.</span><span class="sxs-lookup"><span data-stu-id="d153b-113">The Customer entity gets the key field **Contact_contactId** to relate to the Contact entity key field **contactId**.</span></span>
- <span data-ttu-id="d153b-114">**Vzťah *CustomerToAccount*** bol vytvorený medzi entitou zákazníka a entitou obchodného vzťahu.</span><span class="sxs-lookup"><span data-stu-id="d153b-114">***CustomerToAccount* relationship** was created between the Customer entity and the Account entity.</span></span> <span data-ttu-id="d153b-115">Entita zákazníka získa kľúčové pole **ccount_accountId**, ktoré sa bude vzťahovať na kľúčové pole entity obchodného vzťahu **accountId**.</span><span class="sxs-lookup"><span data-stu-id="d153b-115">The Customer entity gets the key field **Account_accountId** to relate to the Account entity key field **accountId**.</span></span>
- <span data-ttu-id="d153b-116">**Vzťah *CustomerToWebAccount*** bol vytvorený medzi entitou zákazníka a entitou WebAccount.</span><span class="sxs-lookup"><span data-stu-id="d153b-116">***CustomerToWebAccount* relationship** was created between the Customer entity and the WebAccount entity.</span></span> <span data-ttu-id="d153b-117">Entita zákazníka získa kľúčové pole **WebAccount_webaccountId**, ktoré sa bude vzťahovať na kľúčové pole entity WebAccount **webaccountId**.</span><span class="sxs-lookup"><span data-stu-id="d153b-117">The Customer entity gets the key field **WebAccount_webaccountId** to relate to the WebAccount entity key field **webaccountId**.</span></span>

## <a name="create-a-relationship"></a><span data-ttu-id="d153b-118">Vytvorenie vzťahu</span><span class="sxs-lookup"><span data-stu-id="d153b-118">Create a relationship</span></span>

<span data-ttu-id="d153b-119">Definujte vlastné vzťahy na stránke **Vzťahy**.</span><span class="sxs-lookup"><span data-stu-id="d153b-119">Define custom relationships on the **Relationships** page.</span></span> <span data-ttu-id="d153b-120">Každý vzťah pozostáva zo zdrojovej entity (entity, ktorá má cudzí kľúč) a cieľovej entity (entity, na ktorú cudzí kľúč zdrojovej entity odkazuje).</span><span class="sxs-lookup"><span data-stu-id="d153b-120">Each relationship consists of a Source entity (the entity that holds the foreign key) and a Target entity (the entity that the source entity's foreign key points to).</span></span>

1. <span data-ttu-id="d153b-121">V prehľadoch cieľových skupín prejdite na **Údaje** > **Vzťahy**.</span><span class="sxs-lookup"><span data-stu-id="d153b-121">In audience insights, go to **Data** > **Relationships**.</span></span>

2. <span data-ttu-id="d153b-122">Vyberte **Nový vzťah**.</span><span class="sxs-lookup"><span data-stu-id="d153b-122">Select **New relationship**.</span></span>

3. <span data-ttu-id="d153b-123">Na table **Pridať vzťah** zadajte nasledovné informácie:</span><span class="sxs-lookup"><span data-stu-id="d153b-123">In the **Add relationship** pane, provide the following information:</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="d153b-124">![Zadajte podrobnosti vzťahu](media/relationships-add.png "Zadajte podrobnosti vzťahu")</span><span class="sxs-lookup"><span data-stu-id="d153b-124">![Enter relationship details](media/relationships-add.png "Enter relationship details")</span></span>

   - <span data-ttu-id="d153b-125">**Názov vzťahu**: Názov, ktorý odráža účel vzťahu (napr. **AccountWebLogs**).</span><span class="sxs-lookup"><span data-stu-id="d153b-125">**Relationship name**: Name that reflects the purpose of the relationship (for example, **AccountWebLogs**).</span></span>
   - <span data-ttu-id="d153b-126">**Popis**: Popis vzťahu.</span><span class="sxs-lookup"><span data-stu-id="d153b-126">**Description**: Description of the relationship.</span></span>
   - <span data-ttu-id="d153b-127">**Zdrojová entita**: Vyberte entitu, ktorá sa použije ako zdroj vo vzťahu (napríklad WebLog).</span><span class="sxs-lookup"><span data-stu-id="d153b-127">**Source entity**: Select the entity that is used as a source in the relationship (for example, WebLog).</span></span>
   - <span data-ttu-id="d153b-128">**Kardinalita**: Vyberte kardinalitu záznamov zdrojovej entity.</span><span class="sxs-lookup"><span data-stu-id="d153b-128">**Cardinality**: Select the cardinality of the source entity records.</span></span> <span data-ttu-id="d153b-129">Napríklad „veľa“ znamená, že viac záznamov Weblog súvisí s jedným WebAccount.</span><span class="sxs-lookup"><span data-stu-id="d153b-129">For example, "many" means that multiple Weblog records are related to one WebAccount.</span></span>
   - <span data-ttu-id="d153b-130">**Pole zdrojového kľúča**: Toto predstavuje pole cudzieho kľúča v zdrojovej entite.</span><span class="sxs-lookup"><span data-stu-id="d153b-130">**Source key field**: This represents the foreign key field in the source entity.</span></span> <span data-ttu-id="d153b-131">WebLog má napríklad pole cudzieho kľúča **accountId**.</span><span class="sxs-lookup"><span data-stu-id="d153b-131">For example, WebLog has the **accountId** foreign key field.</span></span>
   - <span data-ttu-id="d153b-132">**Cieľová entita**: Vyberte entitu, ktorá sa použije ako cieľ vo vzťahu (napríklad WebAccount).</span><span class="sxs-lookup"><span data-stu-id="d153b-132">**Target entity**: Select the entity that is used as a target in the relationship (for example, WebAccount).</span></span>
   - <span data-ttu-id="d153b-133">**Kardinalita cieľa**: Vyberte kardinalitu záznamov cieľovej entity.</span><span class="sxs-lookup"><span data-stu-id="d153b-133">**Target cardinality**: Select the cardinality of the target entity records.</span></span> <span data-ttu-id="d153b-134">Napríklad „jeden“ znamená, že viac záznamov Weblog súvisí s jedným WebAccount.</span><span class="sxs-lookup"><span data-stu-id="d153b-134">For example, "one" means that multiple Weblog records are related to one WebAccount.</span></span>
   - <span data-ttu-id="d153b-135">**Pole cieľového kľúča**: Toto pole predstavuje kľúčové pole cieľovej entity.</span><span class="sxs-lookup"><span data-stu-id="d153b-135">**Target key field**: This field represents the key field of target entity.</span></span> <span data-ttu-id="d153b-136">WebAccount má napríklad pole cudzieho kľúča **accountId**.</span><span class="sxs-lookup"><span data-stu-id="d153b-136">For example, WebAccount has the **accountId** key field.</span></span>

> [!NOTE]
> <span data-ttu-id="d153b-137">Podporované sú iba vzťahy „mnoho k jednému“ a „jeden k jednému“.</span><span class="sxs-lookup"><span data-stu-id="d153b-137">Only many-to-one and one-to-one relationships are supported.</span></span> <span data-ttu-id="d153b-138">Vzťahy „mnoho k mnohým“ sa môžu vytvoriť pomocou dvoch vzťahov „mnoho k mnohým“ viacerými a entity prepojenia (entita, ktorá sa používa na prepojenie zdrojovej a cieľovej entity).</span><span class="sxs-lookup"><span data-stu-id="d153b-138">Many-to-many relationships can be created using two many-to-one relationships and a link entity (an entity that is used to connect the source entity and the target entity).</span></span>

## <a name="delete-a-relationship"></a><span data-ttu-id="d153b-139">Odstránenie vzťahu</span><span class="sxs-lookup"><span data-stu-id="d153b-139">Delete a relationship</span></span>

1. <span data-ttu-id="d153b-140">V prehľadoch cieľových skupín prejdite na **Údaje** > **Vzťahy**.</span><span class="sxs-lookup"><span data-stu-id="d153b-140">In audience insights, go to **Data** > **Relationships**.</span></span>

2. <span data-ttu-id="d153b-141">Začiarknite políčka vzťahov, ktoré chcete odstrániť.</span><span class="sxs-lookup"><span data-stu-id="d153b-141">Select check boxes for the relationships you want to delete.</span></span>

3. <span data-ttu-id="d153b-142">Vyberte **Odstrániť** v hornej časti tabuľky **Vzťahy**.</span><span class="sxs-lookup"><span data-stu-id="d153b-142">Select **Delete** at the top of the **Relationships** table.</span></span>

4. <span data-ttu-id="d153b-143">Potvrďte odstránenie.</span><span class="sxs-lookup"><span data-stu-id="d153b-143">Confirm your deletion.</span></span>

## <a name="next-step"></a><span data-ttu-id="d153b-144">Nasledujúci krok</span><span class="sxs-lookup"><span data-stu-id="d153b-144">Next step</span></span>

<span data-ttu-id="d153b-145">Systémové a vlastné vzťahy sa používajú na vytváranie segmentov založených na viacerých zdrojoch údajov, ktoré už nie sú zastrešené.</span><span class="sxs-lookup"><span data-stu-id="d153b-145">System and custom relationships are used to create segments based on multiple data sources that are no longer siloed.</span></span> <span data-ttu-id="d153b-146">Ďalšie informácie nájdete v časti [Segmenty](segments.md).</span><span class="sxs-lookup"><span data-stu-id="d153b-146">For more information, see [Segments](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]