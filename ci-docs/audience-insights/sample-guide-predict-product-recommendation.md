---
title: Predikcia odporúčania produktov – vzorový sprievodca
description: V tomto vzorovom sprievodcovi môžete vyskúšať vopred pripravený model predikcie odporúčaní produktov.
ms.date: 02/10/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: diegogranados117
ms.author: digranad
manager: shellyha
ms.openlocfilehash: a85ee598ec747d0594755314e83a127ce0f2af95
ms.sourcegitcommit: 0b754d194d765afef70d1008db7b347dd1f0ee40
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 06/24/2021
ms.locfileid: "6306185"
---
# <a name="product-recommendation-prediction-preview-sample-guide"></a><span data-ttu-id="9392b-103">Predikcia odporúčaní produktov (ukážka) – vzorový sprievodca</span><span class="sxs-lookup"><span data-stu-id="9392b-103">Product recommendation prediction (preview) sample guide</span></span>

<span data-ttu-id="9392b-104">Prejdeme si podrobný príklad predikcie odporúčaní produktov pomocou nižšie uvedených ukážkových údajov.</span><span class="sxs-lookup"><span data-stu-id="9392b-104">We'll walk you through an end to end example of product recommendation prediction using the sample data provided below.</span></span>

## <a name="scenario"></a><span data-ttu-id="9392b-105">Scenár</span><span class="sxs-lookup"><span data-stu-id="9392b-105">Scenario</span></span>

<span data-ttu-id="9392b-106">Contoso je spoločnosť, ktorá vyrába vysoko kvalitnú kávu a kávovary, ktoré predávajú prostredníctvom svojej webovej stránky Contoso Coffee.</span><span class="sxs-lookup"><span data-stu-id="9392b-106">Contoso is a company that produces high-quality coffee and coffee machines, which they sell through their Contoso Coffee website.</span></span> <span data-ttu-id="9392b-107">Ich cieľom je pochopiť, ktoré produkty by mali odporúčať svojim opakujúcim sa zákazníkom.</span><span class="sxs-lookup"><span data-stu-id="9392b-107">Their goal is to understand which products should they recommend to their recurring customers.</span></span> <span data-ttu-id="9392b-108">Ak budete vedieť, čo si zákazníci s **väčšou pravdepodobnosťou kúpia**, môže vám to pomôcť ušetriť marketingové úsilie zameraním na konkrétne položky.</span><span class="sxs-lookup"><span data-stu-id="9392b-108">Knowing what customers are more **likely to purchase**, can help them save marketing efforts by focusing on specific items.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="9392b-109">Predpoklady</span><span class="sxs-lookup"><span data-stu-id="9392b-109">Prerequisites</span></span>

- <span data-ttu-id="9392b-110">Minimálne [povolenia prispievateľa](permissions.md) v Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="9392b-110">At least [Contributor permissions](permissions.md) in Customer Insights.</span></span>
- <span data-ttu-id="9392b-111">Odporúčame vám vykonať nasledujúce kroky [v novom prostredí](manage-environments.md).</span><span class="sxs-lookup"><span data-stu-id="9392b-111">We recommend that you implement the following steps [in a new environment](manage-environments.md).</span></span>

## <a name="task-1---ingest-data"></a><span data-ttu-id="9392b-112">Úloha 1 – Príjem údajov</span><span class="sxs-lookup"><span data-stu-id="9392b-112">Task 1 - Ingest data</span></span>

<span data-ttu-id="9392b-113">Prečítajte si články [o príjme údajov](data-sources.md) a konkrétne o [importe zdrojov údajov pomocou konektorov Power Query](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="9392b-113">Review the articles [about data ingestion](data-sources.md) and [importing data sources using Power Query connectors](connect-power-query.md) specifically.</span></span> <span data-ttu-id="9392b-114">Nasledujúce informácie predpokladajú, že ste sa oboznámili s prijímaním údajov vo všeobecnosti.</span><span class="sxs-lookup"><span data-stu-id="9392b-114">The following information assumes you familiarized with ingesting data in general.</span></span>

### <a name="ingest-customer-data-from-ecommerce-platform"></a><span data-ttu-id="9392b-115">Príjem údajov o zákazníkoch z platformy eCommerce</span><span class="sxs-lookup"><span data-stu-id="9392b-115">Ingest customer data from eCommerce platform</span></span>

1. <span data-ttu-id="9392b-116">Vytvorte zdroj údajov s názvom **eCommerce**, vyberte možnosť importu a vyberte konektor **Text/CSV**.</span><span class="sxs-lookup"><span data-stu-id="9392b-116">Create a data source named **eCommerce**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="9392b-117">Zadajte adresu URL kontaktov pre eCommerce https://aka.ms/ciadclasscontacts.</span><span class="sxs-lookup"><span data-stu-id="9392b-117">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscontacts.</span></span>

1. <span data-ttu-id="9392b-118">Počas úpravy údajov vyberte **Transformovať** a potom **Použiť prvý riadok ako hlavičky**.</span><span class="sxs-lookup"><span data-stu-id="9392b-118">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="9392b-119">Aktualizujte typ údajov pre stĺpce uvedené nižšie:</span><span class="sxs-lookup"><span data-stu-id="9392b-119">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="9392b-120">**DateOfBirth**: Dátum</span><span class="sxs-lookup"><span data-stu-id="9392b-120">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="9392b-121">**CreatedOn**: Dátum/Čas/Pásmo</span><span class="sxs-lookup"><span data-stu-id="9392b-121">**CreatedOn**: Date/Time/Zone</span></span>

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Transformácia dátumu narodenia na dátum.":::

5. <span data-ttu-id="9392b-123">V poli „Názov“ na pravej table premenujte svoj zdroj údajov z **Dotaz** na **eCommerceContacts**</span><span class="sxs-lookup"><span data-stu-id="9392b-123">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **eCommerceContacts**</span></span>

6. <span data-ttu-id="9392b-124">**Uložte** zdroj údajov.</span><span class="sxs-lookup"><span data-stu-id="9392b-124">**Save** the data source.</span></span>

### <a name="ingest-online-purchase-data"></a><span data-ttu-id="9392b-125">Prijmite údaje o online nákupe</span><span class="sxs-lookup"><span data-stu-id="9392b-125">Ingest online purchase data</span></span>

1. <span data-ttu-id="9392b-126">K tomu istému zdroju údajov **eCommerce** pridajte ďalšiu množinu údajov.</span><span class="sxs-lookup"><span data-stu-id="9392b-126">Add another data set to the same **eCommerce** data source.</span></span> <span data-ttu-id="9392b-127">Znova vyberte konektor **Text/CSV**.</span><span class="sxs-lookup"><span data-stu-id="9392b-127">Choose the **Text/CSV** connector again.</span></span>

1. <span data-ttu-id="9392b-128">Zadajte adresu URL pre údaje **Online nákupy** https://aka.ms/ciadclassonline.</span><span class="sxs-lookup"><span data-stu-id="9392b-128">Enter the URL for **Online Purchases** data https://aka.ms/ciadclassonline.</span></span>

1. <span data-ttu-id="9392b-129">Počas úpravy údajov vyberte **Transformovať** a potom **Použiť prvý riadok ako hlavičky**.</span><span class="sxs-lookup"><span data-stu-id="9392b-129">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="9392b-130">Aktualizujte typ údajov pre stĺpce uvedené nižšie:</span><span class="sxs-lookup"><span data-stu-id="9392b-130">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="9392b-131">**PurchasedOn**: Dátum/Čas</span><span class="sxs-lookup"><span data-stu-id="9392b-131">**PurchasedOn**: Date/Time</span></span>
   - <span data-ttu-id="9392b-132">**TotalPrice**: Mena</span><span class="sxs-lookup"><span data-stu-id="9392b-132">**TotalPrice**: Currency</span></span>

1. <span data-ttu-id="9392b-133">V poli **Názov** na bočnej table premenujte svoj zdroj údajov z **Dotaz** na **eCommercePurchases**.</span><span class="sxs-lookup"><span data-stu-id="9392b-133">In the **Name** field on the side pane, rename your data source from **Query** to **eCommercePurchases**.</span></span>

1. <span data-ttu-id="9392b-134">**Uložte** zdroj údajov.</span><span class="sxs-lookup"><span data-stu-id="9392b-134">**Save** the data source.</span></span>


### <a name="ingest-customer-data-from-loyalty-schema"></a><span data-ttu-id="9392b-135">Príjem údaje o zákazníkoch z vernostnej schémy</span><span class="sxs-lookup"><span data-stu-id="9392b-135">Ingest customer data from loyalty schema</span></span>

1. <span data-ttu-id="9392b-136">Vytvorte zdroj údajov s názvom **LoyaltyScheme**, vyberte možnosť importu a vyberte konektor **Text/CSV**.</span><span class="sxs-lookup"><span data-stu-id="9392b-136">Create a data source named **LoyaltyScheme**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="9392b-137">Zadajte adresu URL kontaktov pre eCommerce https://aka.ms/ciadclasscustomerloyalty.</span><span class="sxs-lookup"><span data-stu-id="9392b-137">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscustomerloyalty.</span></span>

1. <span data-ttu-id="9392b-138">Počas úpravy údajov vyberte **Transformovať** a potom **Použiť prvý riadok ako hlavičky**.</span><span class="sxs-lookup"><span data-stu-id="9392b-138">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="9392b-139">Aktualizujte typ údajov pre stĺpce uvedené nižšie:</span><span class="sxs-lookup"><span data-stu-id="9392b-139">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="9392b-140">**DateOfBirth**: Dátum</span><span class="sxs-lookup"><span data-stu-id="9392b-140">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="9392b-141">**RewardsPoints**: Celé číslo</span><span class="sxs-lookup"><span data-stu-id="9392b-141">**RewardsPoints**: Whole Number</span></span>
   - <span data-ttu-id="9392b-142">**CreatedOn**: Dátum/Čas</span><span class="sxs-lookup"><span data-stu-id="9392b-142">**CreatedOn**: Date/Time</span></span>

1. <span data-ttu-id="9392b-143">V poli **Názov** na pravej table premenujte svoj zdroj údajov z **Dotaz** na **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="9392b-143">In the **Name** field on the right-hand pane, rename your data source from **Query** to **loyCustomers**.</span></span>

1. <span data-ttu-id="9392b-144">**Uložte** zdroj údajov.</span><span class="sxs-lookup"><span data-stu-id="9392b-144">**Save** the data source.</span></span>

## <a name="task-2---data-unification"></a><span data-ttu-id="9392b-145">Úloha 2 – Zjednotenie údajov</span><span class="sxs-lookup"><span data-stu-id="9392b-145">Task 2 - Data unification</span></span>

<span data-ttu-id="9392b-146">Po prijatí údajov teraz začneme proces zjednocovania údajov, aby sme vytvorili jednotný profil zákazníka.</span><span class="sxs-lookup"><span data-stu-id="9392b-146">After ingesting the data, we now begin the data unification process to create a unified customer profile.</span></span> <span data-ttu-id="9392b-147">Ďalšie informácie nájdete v téme [Zjednotenie údajov](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="9392b-147">For more information, see [Data unification](data-unification.md).</span></span>

### <a name="map"></a><span data-ttu-id="9392b-148">Priradenie</span><span class="sxs-lookup"><span data-stu-id="9392b-148">Map</span></span>

1. <span data-ttu-id="9392b-149">Po prijatí údajov namapujte kontakty z údajov eCommerce a Loyalty na bežné typy údajov.</span><span class="sxs-lookup"><span data-stu-id="9392b-149">After ingesting the data, map contacts from eCommerce and Loyalty data to common data types.</span></span> <span data-ttu-id="9392b-150">Prejdite na **Údaje** > **Zjednotenie** > **Mapovanie**.</span><span class="sxs-lookup"><span data-stu-id="9392b-150">Go to **Data** > **Unify** > **Map**.</span></span>

2. <span data-ttu-id="9392b-151">Vyberte entity, ktoré zastupujú profil zákazníka – **eCommerceContacts** a **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="9392b-151">Select the entities that represent the customer profile – **eCommerceContacts** and **loyCustomers**.</span></span>

   ![Zjednotenie zdrojov údajov elektronického obchodu a vernostných údajov.](media/unify-ecommerce-loyalty.png)

3. <span data-ttu-id="9392b-153">Vyberte **ContactId** ako primárny kľúč pre **eCommerceContacts** a **LoyaltyID** ako primárny kľúč pre **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="9392b-153">Select **ContactId** as the primary key for **eCommerceContacts** and **LoyaltyID** as the primary key for **loyCustomers**.</span></span>

   ![Zjednotenie LoyaltyId ako primárny kľúč.](media/unify-loyaltyid.png)

### <a name="match"></a><span data-ttu-id="9392b-155">Spárovanie</span><span class="sxs-lookup"><span data-stu-id="9392b-155">Match</span></span>

1. <span data-ttu-id="9392b-156">Prejdite na kartu **Spárovanie** a vyberte **Nastaviť poradie**.</span><span class="sxs-lookup"><span data-stu-id="9392b-156">Go to the **Match** tab and select **Set Order**.</span></span>

2. <span data-ttu-id="9392b-157">V **primárnom** rozbaľovacom zozname si vyberte možnosť **eCommerceContacts: eCommerce** ako primárny zdroj a zahrňte do nej všetky záznamy.</span><span class="sxs-lookup"><span data-stu-id="9392b-157">In the **Primary** dropdown list, choose **eCommerceContacts : eCommerce** as the primary source and include all records.</span></span>

3. <span data-ttu-id="9392b-158">V rozbaľovacom zozname **Entita 2** vyberte možnosť **loyCustomers: LoyaltyScheme** a zahrňte do nej všetky záznamy.</span><span class="sxs-lookup"><span data-stu-id="9392b-158">In the **Entity 2** dropdown list, choose **loyCustomers : LoyaltyScheme** and include all records.</span></span>

   ![Zjednotenie zosúladenia eCommerce a Loyalty.](media/unify-match-order.png)

4. <span data-ttu-id="9392b-160">Vyberte **Vytvoriť nové pravidlo**</span><span class="sxs-lookup"><span data-stu-id="9392b-160">Select **Create a new rule**</span></span>

5. <span data-ttu-id="9392b-161">Pridajte svoju prvú podmienku pomocou FullName.</span><span class="sxs-lookup"><span data-stu-id="9392b-161">Add your first condition using FullName.</span></span>

   - <span data-ttu-id="9392b-162">V prípade eCommerceContacts vyberte z rozbaľovacieho zoznamu položku **FullName**.</span><span class="sxs-lookup"><span data-stu-id="9392b-162">For eCommerceContacts select **FullName** in the dropdown.</span></span>
   - <span data-ttu-id="9392b-163">V prípade loyCustomers vyberte z rozbaľovacieho zoznamu položku **FullName**.</span><span class="sxs-lookup"><span data-stu-id="9392b-163">For loyCustomers select **FullName** in the dropdown.</span></span>
   - <span data-ttu-id="9392b-164">Vyberte rozbaľovací zoznam **Normalizovať** a vyberte **Typ (Telefón, Meno, Adresa, ...)**.</span><span class="sxs-lookup"><span data-stu-id="9392b-164">Select the **Normalize** drop down and choose **Type (Phone, Name, Address, ...)**.</span></span>
   - <span data-ttu-id="9392b-165">Nastavte **Úroveň presnosti**: **Základná** a **Hodnota**: **Vysoká**.</span><span class="sxs-lookup"><span data-stu-id="9392b-165">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

6. <span data-ttu-id="9392b-166">Zadajte meno **FullName, E-mail** pre nové pravidlo.</span><span class="sxs-lookup"><span data-stu-id="9392b-166">Enter the name **FullName, Email** for the new rule.</span></span>

   - <span data-ttu-id="9392b-167">Vyberte druhú podmienku pre e-mailovú adresu výberom možnosti **Pridať podmienku**</span><span class="sxs-lookup"><span data-stu-id="9392b-167">Add a second condition for email address by selecting **Add Condition**</span></span>
   - <span data-ttu-id="9392b-168">Pri entite eCommerceContacts vyberte z rozbaľovacieho zoznamu položku **EMail**.</span><span class="sxs-lookup"><span data-stu-id="9392b-168">For entity eCommerceContacts, choose **EMail** in dropdown.</span></span>
   - <span data-ttu-id="9392b-169">Pri entite loyCustomers vyberte z rozbaľovacieho zoznamu položku **EMail**.</span><span class="sxs-lookup"><span data-stu-id="9392b-169">For entity loyCustomers, choose **EMail** in the dropdown.</span></span>
   - <span data-ttu-id="9392b-170">Pole Normalizovať nechajte prázdne.</span><span class="sxs-lookup"><span data-stu-id="9392b-170">Leave Normalize blank.</span></span>
   - <span data-ttu-id="9392b-171">Nastavte **Úroveň presnosti**: **Základná** a **Hodnota**: **Vysoká**.</span><span class="sxs-lookup"><span data-stu-id="9392b-171">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

   ![Pravidlo zjednotenia zhody pre meno a e-mail.](media/unify-match-rule.png)

7. <span data-ttu-id="9392b-173">Vyberte položku **Uložiť** a **Spustiť**.</span><span class="sxs-lookup"><span data-stu-id="9392b-173">Select **Save** and **Run**.</span></span>

### <a name="merge"></a><span data-ttu-id="9392b-174">Zlúčenie</span><span class="sxs-lookup"><span data-stu-id="9392b-174">Merge</span></span>

1. <span data-ttu-id="9392b-175">Prejdite na kartu **Zlúčiť**.</span><span class="sxs-lookup"><span data-stu-id="9392b-175">Go to the **Merge** tab.</span></span>

1. <span data-ttu-id="9392b-176">V entite **ContactId** pre **loyCustomers** zmeňte zobrazovaný názov na **ContactIdLOYALTY** na odlíšenie od ostatných prijatých ID.</span><span class="sxs-lookup"><span data-stu-id="9392b-176">On the **ContactId** for **loyCustomers** entity, change the display name to **ContactIdLOYALTY** to differentiate it from the other IDs ingested.</span></span>

   ![premenovanie contactid z loyaltyid.](media/unify-merge-contactid.png)

1. <span data-ttu-id="9392b-178">Vyberte **Uložiť** a **Spustiť** na začatie procesu zlúčenia.</span><span class="sxs-lookup"><span data-stu-id="9392b-178">Select **Save** and **Run** to start the Merge Process.</span></span>

## <a name="task-3---configure-product-recommendation-prediction"></a><span data-ttu-id="9392b-179">Úloha 3 – Konfigurácia predikcie odporúčania produktu</span><span class="sxs-lookup"><span data-stu-id="9392b-179">Task 3 - Configure product recommendation prediction</span></span>

<span data-ttu-id="9392b-180">Po zavedení zjednotených profilov zákazníkov môžeme teraz spustiť predikciu odchodu predplatiteľov.</span><span class="sxs-lookup"><span data-stu-id="9392b-180">With the unified customer profiles in place, we can now run the subscription churn prediction.</span></span>

1. <span data-ttu-id="9392b-181">Prejdite na **Analýza** > **Predikcia** vyberte **Odporúčanie produktu**.</span><span class="sxs-lookup"><span data-stu-id="9392b-181">Go to **Intelligence** > **Prediction** choose **Product recommendation**.</span></span>

1. <span data-ttu-id="9392b-182">Vyberte **Začíname**.</span><span class="sxs-lookup"><span data-stu-id="9392b-182">Select **Get started**.</span></span>

1. <span data-ttu-id="9392b-183">Pomenujte model **Predikcia modelu odporúčania produktu OOB** a výstupnú entitu **OOBProductRecommendationModelPrediction**.</span><span class="sxs-lookup"><span data-stu-id="9392b-183">Name the model **OOB Product Recommendation Model Prediction** and the output entity **OOBProductRecommendationModelPrediction**.</span></span>

1. <span data-ttu-id="9392b-184">Definujte tri podmienky pre model:</span><span class="sxs-lookup"><span data-stu-id="9392b-184">Define three conditions for the model:</span></span>

   - <span data-ttu-id="9392b-185">**Počet produktov**: Nastavte túto hodnotu na **5**.</span><span class="sxs-lookup"><span data-stu-id="9392b-185">**Number of products**: Set this value to **5**.</span></span> <span data-ttu-id="9392b-186">Toto nastavenie definuje, koľko produktov chcete odporučiť zákazníkom.</span><span class="sxs-lookup"><span data-stu-id="9392b-186">This setting defines how many products you want to recommend to your customers.</span></span>

   - <span data-ttu-id="9392b-187">**Očakávané opakované nákupy**: Vyberte **Áno** na označenie, že chcete zahrnúť produkty do odporúčania, ktoré si vaši zákazníci predtým kúpili.</span><span class="sxs-lookup"><span data-stu-id="9392b-187">**Repeat purchases expected**: Select **Yes** to indicate that you want to include products in the recommendation that your customers have purchased before.</span></span>

   - <span data-ttu-id="9392b-188">**Dĺžka spätného zobrazenia:** Vyberte minimálne **365 dní**.</span><span class="sxs-lookup"><span data-stu-id="9392b-188">**Look back window:** Select at least **365 days**.</span></span> <span data-ttu-id="9392b-189">Toto nastavenie definuje, ako ďaleko do minulosti bude model pozerať na aktivitu zákazníka, aby ju použil ako vstup jeho odporúčania.</span><span class="sxs-lookup"><span data-stu-id="9392b-189">This setting defines how far the model will look back at the customer's activity to use it as input to their recommendations.</span></span>
   
   :::image type="content" source="media/product-recommendation-model-preferences.png" alt-text="Predvoľby modelu odporúčaní produktov.":::

1. <span data-ttu-id="9392b-191">Vyberte **Požadované údaje** a **Pridať údaje** pre históriu nákupov.</span><span class="sxs-lookup"><span data-stu-id="9392b-191">Select **Required data** and select **Add data** for purchase history.</span></span>

1. <span data-ttu-id="9392b-192">Pridajte entitu **eCommercePurchases: eCommerce** a mapujte polia z eCommerce na zodpovedajúce polia požadované modelom.</span><span class="sxs-lookup"><span data-stu-id="9392b-192">Add the **eCommercePurchases : eCommerce** entity and map the fields from eCommerce to the corresponding fields required by the model.</span></span>

1. <span data-ttu-id="9392b-193">Spojte entitu **eCommercePurchases: eCommerce** s **eCommerceContacts: eCommerce**.</span><span class="sxs-lookup"><span data-stu-id="9392b-193">Join the **eCommercePurchases : eCommerce** entity with **eCommerceContacts : eCommerce**.</span></span>

   ![Spojenie entít eCommerce.](media/model-purchase-join.png)

1. <span data-ttu-id="9392b-195">Vyberte **Ďalej** na nastavenie plánu modelu.</span><span class="sxs-lookup"><span data-stu-id="9392b-195">Select **Next** to set the model schedule.</span></span>

   <span data-ttu-id="9392b-196">Model sa musí pravidelne trénovať, aby sa naučil nové vzorce, keď dôjde k prijatiu nových údajov.</span><span class="sxs-lookup"><span data-stu-id="9392b-196">The model needs to train regularly to learn new patterns when there is new data ingested.</span></span> <span data-ttu-id="9392b-197">Pre tento príklad vyberte **Mesačne**.</span><span class="sxs-lookup"><span data-stu-id="9392b-197">For this example, select **Monthly**.</span></span>

1. <span data-ttu-id="9392b-198">Po skontrolovaní všetkých podrobností vyberte možnosť **Uložiť a spustiť**.</span><span class="sxs-lookup"><span data-stu-id="9392b-198">After reviewing all the details, select **Save and Run**.</span></span>


## <a name="task-4---review-model-results-and-explanations"></a><span data-ttu-id="9392b-199">Úloha 4 – Skontrolujte výsledky modelu a vysvetlenia</span><span class="sxs-lookup"><span data-stu-id="9392b-199">Task 4 - Review model results and explanations</span></span>

<span data-ttu-id="9392b-200">Nechajte model absolvovať školenie a skórovanie údajov.</span><span class="sxs-lookup"><span data-stu-id="9392b-200">Let the model complete the training and scoring of the data.</span></span> <span data-ttu-id="9392b-201">Teraz si môžete skontrolovať vysvetlenie modelu odporúčaní produktov.</span><span class="sxs-lookup"><span data-stu-id="9392b-201">You can now review the product recommendation model explanations.</span></span> <span data-ttu-id="9392b-202">Viac informácií nájdete v článku [Kontrola stavu predikcie a výsledkov](predict-subscription-churn.md#review-a-prediction-status-and-results).</span><span class="sxs-lookup"><span data-stu-id="9392b-202">For more information, see [Review a prediction status and results](predict-subscription-churn.md#review-a-prediction-status-and-results).</span></span>

## <a name="task-5---create-a-segment-of-high-purchased-products"></a><span data-ttu-id="9392b-203">Úloha 5 – Vytvorte segment najčastejšie kupovaných produktov</span><span class="sxs-lookup"><span data-stu-id="9392b-203">Task 5 - Create a segment of high purchased products</span></span>

<span data-ttu-id="9392b-204">Spustením produkčného modelu sa vytvorí nová entita, ktorú môžete vidieť v ponuke **Údaje** > **Entity**.</span><span class="sxs-lookup"><span data-stu-id="9392b-204">Running the production model creates a new entity that you can see in **Data** > **Entities**.</span></span>

<span data-ttu-id="9392b-205">Nový segment môžete vytvoriť na základe entity vytvorenej modelom.</span><span class="sxs-lookup"><span data-stu-id="9392b-205">You can create a new segment based on the entity created by the model.</span></span>

1. <span data-ttu-id="9392b-206">Prejdite na **Segmenty**.</span><span class="sxs-lookup"><span data-stu-id="9392b-206">Go to **Segments**.</span></span> <span data-ttu-id="9392b-207">Vyberte **Nový** následne **Vytvoriť z** > **Analýza**.</span><span class="sxs-lookup"><span data-stu-id="9392b-207">Select **New** and choose **Create from** > **Intelligence**.</span></span>

   ![Vytvorenie segmentu s výstupom modelu.](media/segment-intelligence.png)

1. <span data-ttu-id="9392b-209">Vyberte koncový bod **OOBProductRecommendationModelPrediction** a definujte segment:</span><span class="sxs-lookup"><span data-stu-id="9392b-209">Select the **OOBProductRecommendationModelPrediction** endpoint and define the segment:</span></span>

   - <span data-ttu-id="9392b-210">Pole: ProductID</span><span class="sxs-lookup"><span data-stu-id="9392b-210">Field: ProductID</span></span>
   - <span data-ttu-id="9392b-211">Operátor: Hodnota</span><span class="sxs-lookup"><span data-stu-id="9392b-211">Operator: Value</span></span>
   - <span data-ttu-id="9392b-212">Hodnota: Vyberte prvé tri ID produktov</span><span class="sxs-lookup"><span data-stu-id="9392b-212">Value: Select the top three product IDs</span></span>

   :::image type="content" source="media/product-recommendation-quick-segment.png" alt-text="Vytvorte segment z výsledkov modelu.":::

<span data-ttu-id="9392b-214">Teraz máte segment, ktorý sa dynamicky aktualizuje a ktorý identifikuje zákazníkov, ktorí sú ochotnejší kúpiť si tri najviac odporúčané produkty</span><span class="sxs-lookup"><span data-stu-id="9392b-214">You now have a segment that is dynamically updated which identifies the customers who are more willing to purchase the three most recommended products</span></span> 

<span data-ttu-id="9392b-215">Ďalšie informácie nájdete v téme [Tvorba a správa segmentov](segments.md).</span><span class="sxs-lookup"><span data-stu-id="9392b-215">For more information, see [Create and manage segments](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
