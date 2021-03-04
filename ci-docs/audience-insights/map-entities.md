---
title: Mapovanie entít na účely zjednotenia údajov
description: Namapujte údaje na účely vytvorenia jednotných profilov zákazníkov.
ms.date: 09/25/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: 0088daae0be0cb3e71f87387648430d2353081c9
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267054"
---
# <a name="map-entities-and-attributes"></a><span data-ttu-id="a703d-103">Mapovanie entít a atribútov</span><span class="sxs-lookup"><span data-stu-id="a703d-103">Map entities and attributes</span></span>

<span data-ttu-id="a703d-104">**Mapovanie** je prvou fázou procesu zjednotenia údajov o prehľadoch cieľových skupín.</span><span class="sxs-lookup"><span data-stu-id="a703d-104">**Map** is the first stage in the data unification process of audience insights.</span></span> <span data-ttu-id="a703d-105">Mapovanie pozostáva z troch fáz:</span><span class="sxs-lookup"><span data-stu-id="a703d-105">Mapping consists of three phases:</span></span>

- <span data-ttu-id="a703d-106">*Výber entity*: Identifikujte kombinovateľné entity, ktoré vedú k množine údajov s úplnejšími informáciami o vašich zákazníkoch.</span><span class="sxs-lookup"><span data-stu-id="a703d-106">*Entity selection*: Identify the combinable entities that lead to a dataset with more complete information about your customers.</span></span>
- <span data-ttu-id="a703d-107">*Výber atribútov*: Pre každú entitu identifikujte stĺpce, ktoré chcete kombinovať a zrovnať vo fázach *zosúladenia* a *zlúčenia*.</span><span class="sxs-lookup"><span data-stu-id="a703d-107">*Attribute selection*: For each entity, identify the columns you want to combine and reconcile in the *match* and *merge* phases.</span></span> <span data-ttu-id="a703d-108">Tieto stĺpce sa nazývajú *Atribúty*.</span><span class="sxs-lookup"><span data-stu-id="a703d-108">These columns are called *Attributes*.</span></span>
- <span data-ttu-id="a703d-109">*Výber primárneho kľúča a sémantického typu*: Pre každú entitu identifikujte atribút, ktorý chcete definovať ako primárny kľúč pre túto entitu. Pre každý atribút identifikujte sémantický typ, ktorý tento atribút najlepšie charakterizuje.</span><span class="sxs-lookup"><span data-stu-id="a703d-109">*Primary key and semantic type selection*: For each entity, identify an attribute you want to define as the primary key for that entity, and for each attribute, identify a semantic type that best describes that attribute.</span></span>

<span data-ttu-id="a703d-110">Ďalšie informácie o všeobecnom toku zjednotenia údajov nájdete v téme [Zjednotenie](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="a703d-110">For more information about the general flow of data unification, see [Unify](data-unification.md).</span></span>

## <a name="select-the-first-entities"></a><span data-ttu-id="a703d-111">Vyberte prvé entity</span><span class="sxs-lookup"><span data-stu-id="a703d-111">Select the first entities</span></span>

1. <span data-ttu-id="a703d-112">V prehľadoch cieľových skupín prejdite na **Údaje** > **Zjednotiť** > **Namapovať**.</span><span class="sxs-lookup"><span data-stu-id="a703d-112">In audience insights, go to **Data** > **Unify** > **Map**.</span></span>

2. <span data-ttu-id="a703d-113">Ak chcete spustiť fázu mapovania, vyberte položku **Vybrať entity**.</span><span class="sxs-lookup"><span data-stu-id="a703d-113">Start the map phase by selecting **Select entities**.</span></span>

3. <span data-ttu-id="a703d-114">Vyberte entity a atribúty, ktoré chcete použiť vo fázach *mapovania* a *zlúčenia*.</span><span class="sxs-lookup"><span data-stu-id="a703d-114">Select the entities and attributes you want to use in the *match* and *merge* phases.</span></span> <span data-ttu-id="a703d-115">Požadované atribúty môžete vybrať jednotlivo z entity alebo zahrnúť všetky atribúty z entity výberom začiarkavacieho políčka **Zahrnúť všetky polia** na úrovni entity.</span><span class="sxs-lookup"><span data-stu-id="a703d-115">You can select the required attributes individually from an entity or include all attributes from an entity by selecting the **Include all fields** checkbox on the entity level.</span></span> <span data-ttu-id="a703d-116">Odporúčame vybrať aspoň dve entity, ktoré majú ťažiť z procesu zjednotenia údajov.</span><span class="sxs-lookup"><span data-stu-id="a703d-116">We recommend selecting at least two entities to benefit from the data unification process.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="a703d-117">![Príklad pridania entít](media/data-manager-configure-map-add-entities-example.png "Príklad pridania entít")</span><span class="sxs-lookup"><span data-stu-id="a703d-117">![Add entities example](media/data-manager-configure-map-add-entities-example.png "Add entities example")</span></span>

   <span data-ttu-id="a703d-118">V tomto príklade pridávame entity **eCommerceContacts** a **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="a703d-118">In this example, we're adding the **eCommerceContacts** and **loyCustomers** entities.</span></span> <span data-ttu-id="a703d-119">Výberom týchto entít môžete získať informácie o tom, ktorí z online zákazníkov obchodu sú členmi vernostného programu.</span><span class="sxs-lookup"><span data-stu-id="a703d-119">By choosing these entities, you can derive insights on which of the online business customers are loyalty program members.</span></span>
   
   <span data-ttu-id="a703d-120">Môžete vyhľadávať kľúčové slová vo všetkých atribútoch a entitách a vybrať požadované atribúty, ktoré chcete mapovať.</span><span class="sxs-lookup"><span data-stu-id="a703d-120">You can search on keywords across all attributes and entities to select the required attributes you want to map.</span></span>
   
     > [!div class="mx-imgBorder"]
   > <span data-ttu-id="a703d-121">![Príklad vyhľadávacích polí](media/data-manager-configure-map-search-fields-example.png "Príklad vyhľadávacích polí")</span><span class="sxs-lookup"><span data-stu-id="a703d-121">![Search fields example](media/data-manager-configure-map-search-fields-example.png "Search fields example")</span></span>

4. <span data-ttu-id="a703d-122">Svoje výbery potvrďte výberom položky **Použiť**.</span><span class="sxs-lookup"><span data-stu-id="a703d-122">Select **Apply** to confirm your selections.</span></span>

## <a name="select-primary-key-and-semantic-type-for-attributes"></a><span data-ttu-id="a703d-123">Pre atribúty vyberte primárny kľúč a sémantický typ</span><span class="sxs-lookup"><span data-stu-id="a703d-123">Select primary key and semantic type for attributes</span></span>

<span data-ttu-id="a703d-124">Po výbere entít zobrazí stránka **Mapovať** vybrané entity na kontrolu.</span><span class="sxs-lookup"><span data-stu-id="a703d-124">After selecting your entities, the **Map** page lists the selected entities for your review.</span></span> <span data-ttu-id="a703d-125">Definujte primárny kľúč pre entitu a identifikujte sémantický typ pre atribút v entite.</span><span class="sxs-lookup"><span data-stu-id="a703d-125">Define the primary key for an entity and identify the semantic type for an attribute in the entity.</span></span>

- <span data-ttu-id="a703d-126">**Primárny kľúč**: Vyberte jeden atribút ako primárny kľúč pre každú z vašich entít.</span><span class="sxs-lookup"><span data-stu-id="a703d-126">**Primary key**: Select one attribute as a primary key for each of your entities.</span></span> <span data-ttu-id="a703d-127">Ak má byť atribút platným primárnym kľúčom, nemal by obsahovať duplicitné hodnoty, chýbajúce hodnoty ani nulové hodnoty.</span><span class="sxs-lookup"><span data-stu-id="a703d-127">For an attribute to be a valid primary key, it shouldn't include duplicate values, missing values, or null values.</span></span> <span data-ttu-id="a703d-128">Atribúty reťazcov, celého čísla a údajových typov GUID sú podporované ako primárne kľúče a budú sa zobrazovať v poli, z ktorého si môžete vybrať.</span><span class="sxs-lookup"><span data-stu-id="a703d-128">String, integer, and GUID data type attributes are supported as primary keys and will be displayed in a field for you to select from.</span></span>

- <span data-ttu-id="a703d-129">**Atribút sémantického typu**: Kategórie atribútov, napríklad e-mailová adresa alebo názov.</span><span class="sxs-lookup"><span data-stu-id="a703d-129">**Attribute semantic type**: Categories of your attributes, such as email address or name.</span></span> <span data-ttu-id="a703d-130">Ak chcete používať modely umelej inteligencie pre inteligentnú predikciu sémantiky, ušetriť čas a zlepšiť presnosť, nastavte **Inteligentné mapovanie** na **ZAP.**</span><span class="sxs-lookup"><span data-stu-id="a703d-130">To use AI models for smart prediction of semantics, save time and improve accuracy, set **Intelligent mapping** to **ON**.</span></span> <span data-ttu-id="a703d-131">Inteligentné mapovanie zdôrazňuje odporúčanie sémantiky založené na AI v poli **Typ**.</span><span class="sxs-lookup"><span data-stu-id="a703d-131">Intelligent mapping highlights AI-based semantics recommendation in the **Type** field.</span></span> <span data-ttu-id="a703d-132">Ak nastavíte na **VYP.**, uvidíte naše pravidelné odporúčania týkajúce sa mapovania.</span><span class="sxs-lookup"><span data-stu-id="a703d-132">If you set it to **OFF**, you will see our regular mapping recommendations.</span></span> <span data-ttu-id="a703d-133">Z dostupného zoznamu možností môžete vybrať ľubovoľný sémantický typ a navrhovaný výber prepísať.</span><span class="sxs-lookup"><span data-stu-id="a703d-133">You can select any semantic type from the available list of options and override the suggested selection.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="a703d-134">![Typ atribútu a sémantické predikcia](media/data-manager-configure-map-add-attributes-semantic-prediction.png "Typ atribútu a sémantická predikcia")</span><span class="sxs-lookup"><span data-stu-id="a703d-134">![Attribute type and semantic prediction](media/data-manager-configure-map-add-attributes-semantic-prediction.png "Attribute type and semantic prediction")</span></span>

<span data-ttu-id="a703d-135">Pridanie vlastného sémantického typu je tiež možné.</span><span class="sxs-lookup"><span data-stu-id="a703d-135">Adding a custom semantic type is also possible.</span></span> <span data-ttu-id="a703d-136">Vyberte pole Typ pre atribút a zadajte názov vlastného sémantického typu.</span><span class="sxs-lookup"><span data-stu-id="a703d-136">Select the type field for an attribute, and type your custom semantic type name.</span></span> <span data-ttu-id="a703d-137">Takýmto spôsobom môžete tiež zmeniť typy atribútov, ktoré identifikoval systém.</span><span class="sxs-lookup"><span data-stu-id="a703d-137">This way, you can also change the attribute types that were identified by the system.</span></span>

<span data-ttu-id="a703d-138">Všetky atribúty, pre ktoré sa sémantický typ identifikoval automaticky, sú zoskupené v sekcii **Kontrola mapovaných polí**.</span><span class="sxs-lookup"><span data-stu-id="a703d-138">All attributes for which a semantic type is automatically identified are grouped in the **Review mapped fields** section.</span></span> <span data-ttu-id="a703d-139">Skontrolujte tieto atribúty a ich sémantické typy, pretože sa budú používať na kombináciu vašich entít v kroku zlúčenia zjednotenia údajov.</span><span class="sxs-lookup"><span data-stu-id="a703d-139">Review these attributes and their semantic types because they'll be used to combine your entities in the merge step of data unification.</span></span>

<span data-ttu-id="a703d-140">Atribúty, ktoré nie sú automaticky mapované na sémantický typ, sú zoskupené v sekcii **Definícia údajov v nemapovaných poliach**.</span><span class="sxs-lookup"><span data-stu-id="a703d-140">Attributes that aren't automatically mapped to a semantic type are grouped in the **Define the data in the unmapped fields** section.</span></span> <span data-ttu-id="a703d-141">Vyberte pole sémantického typu pre nemapované atribúty alebo zadajte vlastný názov typu atribútu.</span><span class="sxs-lookup"><span data-stu-id="a703d-141">Select the semantic type field for the unmapped attributes, or enter your custom attribute-type name.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="a703d-142">![Primárny kľúč a typ atribútu](media/data-manager-configure-map-add-attributes.png "Primárny kľúč a typ atribútu")</span><span class="sxs-lookup"><span data-stu-id="a703d-142">![Primary key and attribute type](media/data-manager-configure-map-add-attributes.png "Primary key and attribute type")</span></span>

> [!NOTE]
> <span data-ttu-id="a703d-143">Jedno pole by sa malo namapovať na sémantický typ Person.FullName, aby sa vyplnilo meno zákazníka na karte zákazníka.</span><span class="sxs-lookup"><span data-stu-id="a703d-143">One field should map to the semantic type Person.FullName to populate the customer name in customer card.</span></span> <span data-ttu-id="a703d-144">V opačnom prípade sa zákaznícke karty zobrazia bez mena.</span><span class="sxs-lookup"><span data-stu-id="a703d-144">Otherwise, the customer cards will appear nameless.</span></span> 

## <a name="add-and-remove-attributes-and-entities"></a><span data-ttu-id="a703d-145">Pridanie a odstránenie atribútov a entít</span><span class="sxs-lookup"><span data-stu-id="a703d-145">Add and remove attributes and entities</span></span>

1. <span data-ttu-id="a703d-146">V ponuke **Zjednotiť** > **Mapovať** vyberte **Upraviť polia**.</span><span class="sxs-lookup"><span data-stu-id="a703d-146">On **Unify** > **Map**, select **Edit fields**.</span></span>

2. <span data-ttu-id="a703d-147">Na table **Upraviť polia** môžete pridať alebo odstrániť atribúty a entity.</span><span class="sxs-lookup"><span data-stu-id="a703d-147">In the **Edit fields** pane, add or remove attributes and entities.</span></span> <span data-ttu-id="a703d-148">Pomocou vyhľadávania alebo posúvania nájdite a vyberte atribúty a entity, ktoré vás zaujímajú.</span><span class="sxs-lookup"><span data-stu-id="a703d-148">Use the search or scroll to find and select your attributes and entities of interest.</span></span> <span data-ttu-id="a703d-149">Atribút alebo entitu nemôžete odstrániť, ak už boli spárované.</span><span class="sxs-lookup"><span data-stu-id="a703d-149">You can't remove an attribute or an entity if they've already been matched.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="a703d-150">![Pridanie alebo odstránenie atribútov](media/configure-data-map-edit.png "Pridanie alebo odstránenie atribútov")</span><span class="sxs-lookup"><span data-stu-id="a703d-150">![Add or remove attributes](media/configure-data-map-edit.png "Add or remove attributes")</span></span>

3. <span data-ttu-id="a703d-151">Vyberte **Použiť**.</span><span class="sxs-lookup"><span data-stu-id="a703d-151">Select **Apply**.</span></span>

## <a name="add-images-to-profiles"></a><span data-ttu-id="a703d-152">Pridajte obrázky do profilov</span><span class="sxs-lookup"><span data-stu-id="a703d-152">Add images to profiles</span></span>

<span data-ttu-id="a703d-153">Ak entita obsahuje adresy URL na verejne dostupné profilové obrázky alebo logá, môžete ich pridať do zjednoteného profilu zákazníka.</span><span class="sxs-lookup"><span data-stu-id="a703d-153">If an entity contains URLs to publicly available profile images or logos, you can add them to the unified customer profile.</span></span>

<span data-ttu-id="a703d-154">Vyberte entitu a vyhľadajte pole, ktoré obsahuje webovú adresu URL pre obrázok profilu.</span><span class="sxs-lookup"><span data-stu-id="a703d-154">Select the entity and find the field that contains the URL to the profile image.</span></span> <span data-ttu-id="a703d-155">Vo vstupnom poli **Typ** zadajte manuálne niektorú z nasledujúcich hodnôt:</span><span class="sxs-lookup"><span data-stu-id="a703d-155">In the **Type** input field, manually enter the following value:</span></span> 
- <span data-ttu-id="a703d-156">Pre osobu: Person.ProfileImage</span><span class="sxs-lookup"><span data-stu-id="a703d-156">For a person: Person.ProfileImage</span></span>
- <span data-ttu-id="a703d-157">Pre organizáciu: Organization.LogoImage</span><span class="sxs-lookup"><span data-stu-id="a703d-157">For an organization: Organization.LogoImage</span></span>

<span data-ttu-id="a703d-158">Pokračujte v krokoch zjednotenia a zaistite, aby bol atribút, ktorý obsahuje adresu URL obrázka, tiež pridaný v kroku [Zlúčiť](merge-entities.md).</span><span class="sxs-lookup"><span data-stu-id="a703d-158">Continue with the unification steps and ensure the attribute that contains the image URL is also added in the [Merge](merge-entities.md) step.</span></span>

## <a name="set-attributes-for-organizations"></a><span data-ttu-id="a703d-159">Nastavenie atribútov pre organizácie</span><span class="sxs-lookup"><span data-stu-id="a703d-159">Set attributes for organizations</span></span>

<span data-ttu-id="a703d-160">Pre organizácie (ukážka) by mal byť typ atribútu mapovaný k položke „Organization.Name“.</span><span class="sxs-lookup"><span data-stu-id="a703d-160">For organizations (Preview), the attribute type should be mapped to "Organization.Name"</span></span>
> [!div class="mx-imgBorder"]
> <span data-ttu-id="a703d-161">![Primárny kľúč a typ atribútu B2B](media/configure-data-map-edit-b2b.png "Primárny kľúč a typ atribútu B2B")</span><span class="sxs-lookup"><span data-stu-id="a703d-161">![Primary key and attribute type B2B](media/configure-data-map-edit-b2b.png "Primary key and attribute type B2B")</span></span>

## <a name="next-step"></a><span data-ttu-id="a703d-162">Nasledujúci krok</span><span class="sxs-lookup"><span data-stu-id="a703d-162">Next step</span></span>

<span data-ttu-id="a703d-163">Ako súčasť procesu zjednotenia údajov prejdite na stránku **Zosúladenie**.</span><span class="sxs-lookup"><span data-stu-id="a703d-163">As part of the data unification process, go to the **Match** page.</span></span> <span data-ttu-id="a703d-164">Navštívte [**Zosúladenie**](match-entities.md), ak sa chcete dozvedieť o tejto fáze.</span><span class="sxs-lookup"><span data-stu-id="a703d-164">Visit [**Match**](match-entities.md) to learn about this phase.</span></span>

> [!TIP]
> <span data-ttu-id="a703d-165">Pozrite si nasledujúce video: [Začíname: Vytvorenie zjednoteného profilu zákazníka](https://youtu.be/oBfGEhucAxs).</span><span class="sxs-lookup"><span data-stu-id="a703d-165">Check out the following video: [Getting Started: Creating a Unified Customer Profile](https://youtu.be/oBfGEhucAxs).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]