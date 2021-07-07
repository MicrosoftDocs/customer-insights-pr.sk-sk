---
title: Predikcia odchodu predplatiteľov – vzorový sprievodca
description: V tomto vzorovom sprievodcovi môžete vyskúšať vopred pripravený model predikcie odchodu predplatiteľov.
ms.date: 11/19/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: diegogranados117
ms.author: digranad
manager: shellyha
ms.openlocfilehash: fa460fa5c79bc8a356ec5e90050ec85e05c55be8
ms.sourcegitcommit: 0b754d194d765afef70d1008db7b347dd1f0ee40
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 06/24/2021
ms.locfileid: "6306322"
---
# <a name="subscription-churn-prediction-preview-sample-guide"></a><span data-ttu-id="00f43-103">Predikcia odchodu predplatiteľov (ukážka) – vzorový sprievodca</span><span class="sxs-lookup"><span data-stu-id="00f43-103">Subscription churn prediction (preview) sample guide</span></span>

<span data-ttu-id="00f43-104">Prejdeme si podrobný príklad predikcie odchodov predplatiteľov pomocou nižšie uvedených údajov.</span><span class="sxs-lookup"><span data-stu-id="00f43-104">We'll walk you through an end to end example of subscription churn prediction using the sample data provided below.</span></span> 

## <a name="scenario"></a><span data-ttu-id="00f43-105">Scenár</span><span class="sxs-lookup"><span data-stu-id="00f43-105">Scenario</span></span>

<span data-ttu-id="00f43-106">Contoso je spoločnosť, ktorá vyrába vysoko kvalitnú kávu a kávovary, ktoré predávajú prostredníctvom svojej webovej stránky Contoso Coffee.</span><span class="sxs-lookup"><span data-stu-id="00f43-106">Contoso is a company that produces high-quality coffee and coffee machines, which they sell through their Contoso Coffee website.</span></span> <span data-ttu-id="00f43-107">Nedávno začali ponúkať pre svojich zákazníkov možnosť predplatného, aby mohli pravidelne dostávať kávu.</span><span class="sxs-lookup"><span data-stu-id="00f43-107">They recently started a subscription business for their customers to get coffee on a regular basis.</span></span> <span data-ttu-id="00f43-108">Ich cieľom je pochopiť, ktorí zákazníci s predplatným môžu predplatné v najbližších mesiacoch zrušiť.</span><span class="sxs-lookup"><span data-stu-id="00f43-108">Their goal is to understand, which subscribed customers might cancel their subscription in the next few months.</span></span> <span data-ttu-id="00f43-109">Poznatok, ktorý z ich zákazníkov **pravdepodobne odíde**, im môže im pomôcť ušetriť marketingové úsilie zameraním na ich udržanie.</span><span class="sxs-lookup"><span data-stu-id="00f43-109">Knowing which of their customers is **likely to churn**, can help them save marketing efforts by focusing on keeping them.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="00f43-110">Predpoklady</span><span class="sxs-lookup"><span data-stu-id="00f43-110">Prerequisites</span></span>

- <span data-ttu-id="00f43-111">Minimálne [povolenia prispievateľa](permissions.md) v Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="00f43-111">At least [Contributor permissions](permissions.md) in Customer Insights.</span></span>
- <span data-ttu-id="00f43-112">Odporúčame vám vykonať nasledujúce kroky [v novom prostredí](manage-environments.md).</span><span class="sxs-lookup"><span data-stu-id="00f43-112">We recommend that you implement the following steps [in a new environment](manage-environments.md).</span></span>

## <a name="task-1---ingest-data"></a><span data-ttu-id="00f43-113">Úloha 1 – Príjem údajov</span><span class="sxs-lookup"><span data-stu-id="00f43-113">Task 1 - Ingest data</span></span>

<span data-ttu-id="00f43-114">Prečítajte si články [o príjme údajov](data-sources.md) a konkrétne o [importe zdrojov údajov pomocou konektorov Power Query](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="00f43-114">Review the articles [about data ingestion](data-sources.md) and [importing data sources using Power Query connectors](connect-power-query.md) specifically.</span></span> <span data-ttu-id="00f43-115">Nasledujúce informácie predpokladajú, že ste sa oboznámili s prijímaním údajov vo všeobecnosti.</span><span class="sxs-lookup"><span data-stu-id="00f43-115">The following information assumes you familiarized with ingesting data in general.</span></span> 

### <a name="ingest-customer-data-from-ecommerce-platform"></a><span data-ttu-id="00f43-116">Príjem údajov o zákazníkoch z platformy eCommerce</span><span class="sxs-lookup"><span data-stu-id="00f43-116">Ingest customer data from eCommerce platform</span></span>

1. <span data-ttu-id="00f43-117">Vytvorte zdroj údajov s názvom **eCommerce**, vyberte možnosť importu a vyberte konektor **Text/CSV**.</span><span class="sxs-lookup"><span data-stu-id="00f43-117">Create a data source named **eCommerce**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="00f43-118">Zadajte adresu URL kontaktov pre eCommerce https://aka.ms/ciadclasscontacts.</span><span class="sxs-lookup"><span data-stu-id="00f43-118">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscontacts.</span></span>

1. <span data-ttu-id="00f43-119">Počas úpravy údajov vyberte **Transformovať** a potom **Použiť prvý riadok ako hlavičky**.</span><span class="sxs-lookup"><span data-stu-id="00f43-119">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="00f43-120">Aktualizujte typ údajov pre stĺpce uvedené nižšie:</span><span class="sxs-lookup"><span data-stu-id="00f43-120">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="00f43-121">**DateOfBirth**: Dátum</span><span class="sxs-lookup"><span data-stu-id="00f43-121">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="00f43-122">**CreatedOn**: Dátum/Čas/Pásmo</span><span class="sxs-lookup"><span data-stu-id="00f43-122">**CreatedOn**: Date/Time/Zone</span></span>

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Transformácia dátumu narodenia na dátum.":::

1. <span data-ttu-id="00f43-124">V poli **Názov** na pravej table premenujte svoj zdroj údajov z **Dotaz** na **eCommerceContacts**</span><span class="sxs-lookup"><span data-stu-id="00f43-124">In the **Name** field on the right-hand pane, rename your data source from **Query** to **eCommerceContacts**</span></span>

1. <span data-ttu-id="00f43-125">Uložte zdroj údajov.</span><span class="sxs-lookup"><span data-stu-id="00f43-125">Save the data source.</span></span>

### <a name="ingest-customer-data-from-loyalty-schema"></a><span data-ttu-id="00f43-126">Príjem údaje o zákazníkoch z vernostnej schémy</span><span class="sxs-lookup"><span data-stu-id="00f43-126">Ingest customer data from loyalty schema</span></span>

1. <span data-ttu-id="00f43-127">Vytvorte zdroj údajov s názvom **LoyaltyScheme**, vyberte možnosť importu a vyberte konektor **Text/CSV**.</span><span class="sxs-lookup"><span data-stu-id="00f43-127">Create a data source named **LoyaltyScheme**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="00f43-128">Zadajte adresu URL kontaktov pre eCommerce https://aka.ms/ciadclasscustomerloyalty.</span><span class="sxs-lookup"><span data-stu-id="00f43-128">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscustomerloyalty.</span></span>

1. <span data-ttu-id="00f43-129">Počas úpravy údajov vyberte **Transformovať** a potom **Použiť prvý riadok ako hlavičky**.</span><span class="sxs-lookup"><span data-stu-id="00f43-129">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="00f43-130">Aktualizujte typ údajov pre stĺpce uvedené nižšie:</span><span class="sxs-lookup"><span data-stu-id="00f43-130">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="00f43-131">**DateOfBirth**: Dátum</span><span class="sxs-lookup"><span data-stu-id="00f43-131">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="00f43-132">**RewardsPoints**: Celé číslo</span><span class="sxs-lookup"><span data-stu-id="00f43-132">**RewardsPoints**: Whole Number</span></span>
   - <span data-ttu-id="00f43-133">**CreatedOn**: Dátum/Čas</span><span class="sxs-lookup"><span data-stu-id="00f43-133">**CreatedOn**: Date/Time</span></span>

1. <span data-ttu-id="00f43-134">V poli **Názov** na pravej table premenujte svoj zdroj údajov z **Dotaz** na **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="00f43-134">In the **Name** field on the right-hand pane, rename your data source from **Query** to **loyCustomers**.</span></span>

1. <span data-ttu-id="00f43-135">Uložte zdroj údajov.</span><span class="sxs-lookup"><span data-stu-id="00f43-135">Save the data source.</span></span>

### <a name="ingest-subscription-information"></a><span data-ttu-id="00f43-136">Príjem informácií o predplatnom</span><span class="sxs-lookup"><span data-stu-id="00f43-136">Ingest subscription information</span></span>

1. <span data-ttu-id="00f43-137">Vytvorte zdroj údajov s názvom **SubscriptionHistory**, vyberte možnosť importu a vyberte konektor **Text/CSV**.</span><span class="sxs-lookup"><span data-stu-id="00f43-137">Create a data source named **SubscriptionHistory**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="00f43-138">Zadajte adresu URL kontaktov pre eCommerce https://aka.ms/ciadchurnsubscriptionhistory.</span><span class="sxs-lookup"><span data-stu-id="00f43-138">Enter the URL for eCommerce contacts https://aka.ms/ciadchurnsubscriptionhistory.</span></span>

1. <span data-ttu-id="00f43-139">Počas úpravy údajov vyberte **Transformovať** a potom **Použiť prvý riadok ako hlavičky**.</span><span class="sxs-lookup"><span data-stu-id="00f43-139">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="00f43-140">Aktualizujte typ údajov pre stĺpce uvedené nižšie:</span><span class="sxs-lookup"><span data-stu-id="00f43-140">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="00f43-141">**SubscriptioID**: Celé číslo</span><span class="sxs-lookup"><span data-stu-id="00f43-141">**SubscriptioID**: Whole Number</span></span>
   - <span data-ttu-id="00f43-142">**SubscriptionAmount**: Mena</span><span class="sxs-lookup"><span data-stu-id="00f43-142">**SubscriptionAmount**: Currency</span></span>
   - <span data-ttu-id="00f43-143">**SubscriptionEndDate**: Dátum/Čas</span><span class="sxs-lookup"><span data-stu-id="00f43-143">**SubscriptionEndDate**: Date/Time</span></span>
   - <span data-ttu-id="00f43-144">**SubscriptionStartDate**: Dátum/Čas</span><span class="sxs-lookup"><span data-stu-id="00f43-144">**SubscriptionStartDate**: Date/Time</span></span>
   - <span data-ttu-id="00f43-145">**TransactionDate**: Dátum/Čas</span><span class="sxs-lookup"><span data-stu-id="00f43-145">**TransactionDate**: Date/Time</span></span>
   - <span data-ttu-id="00f43-146">**IsRecurring**: Pravda/Nepravda</span><span class="sxs-lookup"><span data-stu-id="00f43-146">**IsRecurring**: True/False</span></span>
   - <span data-ttu-id="00f43-147">**Is_auto_renew**: Pravda/Nepravda</span><span class="sxs-lookup"><span data-stu-id="00f43-147">**Is_auto_renew**: True/False</span></span>
   - <span data-ttu-id="00f43-148">**RecurringFrequencyInMonths**: Celé číslo</span><span class="sxs-lookup"><span data-stu-id="00f43-148">**RecurringFrequencyInMonths**: Whole Number</span></span>

1. <span data-ttu-id="00f43-149">V poli **Názov** na pravej table premenujte svoj zdroj údajov z **Dotaz** na **SubscriptionHistory**.</span><span class="sxs-lookup"><span data-stu-id="00f43-149">In the **Name** field on the right-hand pane, rename your data source from **Query** to **SubscriptionHistory**.</span></span>

1. <span data-ttu-id="00f43-150">Uložte zdroj údajov.</span><span class="sxs-lookup"><span data-stu-id="00f43-150">Save the data source.</span></span>

### <a name="ingest-customer-data-from-website-reviews"></a><span data-ttu-id="00f43-151">Príjem údajov o zákazníkoch z recenzií na webe</span><span class="sxs-lookup"><span data-stu-id="00f43-151">Ingest customer data from website reviews</span></span>

1. <span data-ttu-id="00f43-152">Vytvorte zdroj údajov s názvom **Website**, vyberte možnosť importu a vyberte konektor **Text/CSV**.</span><span class="sxs-lookup"><span data-stu-id="00f43-152">Create a data source named **Website**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="00f43-153">Zadajte adresu URL kontaktov pre eCommerce https://aka.ms/ciadclasswebsite.</span><span class="sxs-lookup"><span data-stu-id="00f43-153">Enter the URL for eCommerce contacts https://aka.ms/ciadclasswebsite.</span></span>

1. <span data-ttu-id="00f43-154">Počas úpravy údajov vyberte **Transformovať** a potom **Použiť prvý riadok ako hlavičky**.</span><span class="sxs-lookup"><span data-stu-id="00f43-154">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="00f43-155">Aktualizujte typ údajov pre stĺpce uvedené nižšie:</span><span class="sxs-lookup"><span data-stu-id="00f43-155">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="00f43-156">**ReviewRating**: Celé číslo</span><span class="sxs-lookup"><span data-stu-id="00f43-156">**ReviewRating**: Whole Number</span></span>
   - <span data-ttu-id="00f43-157">**ReviewDate**: Dátum</span><span class="sxs-lookup"><span data-stu-id="00f43-157">**ReviewDate**: Date</span></span>

1. <span data-ttu-id="00f43-158">V poli „Názov“ na pravej table premenujte svoj zdroj údajov z **Query** na **webReviews**.</span><span class="sxs-lookup"><span data-stu-id="00f43-158">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **webReviews**.</span></span>

## <a name="task-2---data-unification"></a><span data-ttu-id="00f43-159">Úloha 2 – Zjednotenie údajov</span><span class="sxs-lookup"><span data-stu-id="00f43-159">Task 2 - Data unification</span></span>

<span data-ttu-id="00f43-160">Po prijatí údajov teraz začíname proces **Mapovanie, párovanie, zlúčenie** na vytvorenie zjednoteného profilu zákazníka.</span><span class="sxs-lookup"><span data-stu-id="00f43-160">After ingesting the data we now begin the **Map, Match, Merge** process to create a unified customer profile.</span></span> <span data-ttu-id="00f43-161">Ďalšie informácie nájdete v téme [Zjednotenie údajov](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="00f43-161">For more information, see [Data unification](data-unification.md).</span></span>

### <a name="map"></a><span data-ttu-id="00f43-162">Priradenie</span><span class="sxs-lookup"><span data-stu-id="00f43-162">Map</span></span>

1. <span data-ttu-id="00f43-163">Po prijatí údajov namapujte kontakty z údajov eCommerce a Loyalty na bežné typy údajov.</span><span class="sxs-lookup"><span data-stu-id="00f43-163">After ingesting the data, map contacts from eCommerce and Loyalty data to common data types.</span></span> <span data-ttu-id="00f43-164">Prejdite na **Údaje** > **Zjednotenie** > **Mapovanie**.</span><span class="sxs-lookup"><span data-stu-id="00f43-164">Go to **Data** > **Unify** > **Map**.</span></span>

1. <span data-ttu-id="00f43-165">Vyberte entity, ktoré zastupujú profil zákazníka – **eCommerceContacts** a **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="00f43-165">Select the entities that represent the customer profile – **eCommerceContacts** and **loyCustomers**.</span></span> 

   :::image type="content" source="media/unify-ecommerce-loyalty.PNG" alt-text="Zjednotenie zdrojov údajov elektronického obchodu a vernostných údajov.":::

1. <span data-ttu-id="00f43-167">Vyberte **ContactId** ako primárny kľúč pre **eCommerceContacts** a **LoyaltyID** ako primárny kľúč pre **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="00f43-167">Select **ContactId** as the primary key for **eCommerceContacts** and **LoyaltyID** as the primary key for **loyCustomers**.</span></span>

   :::image type="content" source="media/unify-loyaltyid.PNG" alt-text="Zjednotenie LoyaltyId ako primárny kľúč.":::

### <a name="match"></a><span data-ttu-id="00f43-169">Spárovanie</span><span class="sxs-lookup"><span data-stu-id="00f43-169">Match</span></span>

1. <span data-ttu-id="00f43-170">Prejdite na kartu **Spárovanie** a vyberte **Nastaviť poradie**.</span><span class="sxs-lookup"><span data-stu-id="00f43-170">Go to the **Match** tab and select **Set Order**.</span></span>

1. <span data-ttu-id="00f43-171">V **primárnom** rozbaľovacom zozname si vyberte možnosť **eCommerceContacts: eCommerce** ako primárny zdroj a zahrňte do nej všetky záznamy.</span><span class="sxs-lookup"><span data-stu-id="00f43-171">In the **Primary** dropdown list, choose **eCommerceContacts : eCommerce** as the primary source and include all records.</span></span>

1. <span data-ttu-id="00f43-172">V rozbaľovacom zozname **Entita 2** vyberte možnosť **loyCustomers: LoyaltyScheme** a zahrňte do nej všetky záznamy.</span><span class="sxs-lookup"><span data-stu-id="00f43-172">In the **Entity 2** dropdown list, choose **loyCustomers : LoyaltyScheme** and include all records.</span></span>

   :::image type="content" source="media/unify-match-order.PNG" alt-text="Zjednotenie zosúladenia eCommerce a Loyalty.":::

1. <span data-ttu-id="00f43-174">Vyberte **Vytvoriť nové pravidlo**</span><span class="sxs-lookup"><span data-stu-id="00f43-174">Select **Create a new rule**</span></span>

1. <span data-ttu-id="00f43-175">Pridajte svoju prvú podmienku pomocou FullName.</span><span class="sxs-lookup"><span data-stu-id="00f43-175">Add your first condition using FullName.</span></span>

   * <span data-ttu-id="00f43-176">V prípade eCommerceContacts vyberte z rozbaľovacieho zoznamu položku **FullName**.</span><span class="sxs-lookup"><span data-stu-id="00f43-176">For eCommerceContacts select **FullName** in the dropdown.</span></span>
   * <span data-ttu-id="00f43-177">V prípade loyCustomers vyberte z rozbaľovacieho zoznamu položku **FullName**.</span><span class="sxs-lookup"><span data-stu-id="00f43-177">For loyCustomers select **FullName** in the dropdown.</span></span>
   * <span data-ttu-id="00f43-178">Vyberte rozbaľovací zoznam **Normalizovať** a vyberte **Typ (Telefón, Meno, Adresa, ...)**.</span><span class="sxs-lookup"><span data-stu-id="00f43-178">Select the **Normalize** drop down and choose **Type (Phone, Name, Address, ...)**.</span></span>
   * <span data-ttu-id="00f43-179">Nastavte **Úroveň presnosti**: **Základná** a **Hodnota**: **Vysoká**.</span><span class="sxs-lookup"><span data-stu-id="00f43-179">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

1. <span data-ttu-id="00f43-180">Zadajte meno **FullName, E-mail** pre nové pravidlo.</span><span class="sxs-lookup"><span data-stu-id="00f43-180">Enter the name **FullName, Email** for the new rule.</span></span>

   * <span data-ttu-id="00f43-181">Vyberte druhú podmienku pre e-mailovú adresu výberom možnosti **Pridať podmienku**</span><span class="sxs-lookup"><span data-stu-id="00f43-181">Add a second condition for email address by selecting **Add Condition**</span></span>
   * <span data-ttu-id="00f43-182">Pri entite eCommerceContacts vyberte z rozbaľovacieho zoznamu položku **EMail**.</span><span class="sxs-lookup"><span data-stu-id="00f43-182">For entity eCommerceContacts, choose **EMail** in dropdown.</span></span>
   * <span data-ttu-id="00f43-183">Pri entite loyCustomers vyberte z rozbaľovacieho zoznamu položku **EMail**.</span><span class="sxs-lookup"><span data-stu-id="00f43-183">For entity loyCustomers, choose **EMail** in the dropdown.</span></span> 
   * <span data-ttu-id="00f43-184">Pole Normalizovať nechajte prázdne.</span><span class="sxs-lookup"><span data-stu-id="00f43-184">Leave Normalize blank.</span></span> 
   * <span data-ttu-id="00f43-185">Nastavte **Úroveň presnosti**: **Základná** a **Hodnota**: **Vysoká**.</span><span class="sxs-lookup"><span data-stu-id="00f43-185">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

   :::image type="content" source="media/unify-match-rule.PNG" alt-text="Pravidlo zjednotenia zhody pre meno a e-mail.":::

7. <span data-ttu-id="00f43-187">Vyberte položku **Uložiť** a **Spustiť**.</span><span class="sxs-lookup"><span data-stu-id="00f43-187">Select **Save** and **Run**.</span></span>

### <a name="merge"></a><span data-ttu-id="00f43-188">Zlúčenie</span><span class="sxs-lookup"><span data-stu-id="00f43-188">Merge</span></span>

1. <span data-ttu-id="00f43-189">Prejdite na kartu **Zlúčiť**.</span><span class="sxs-lookup"><span data-stu-id="00f43-189">Go to the **Merge** tab.</span></span>

1. <span data-ttu-id="00f43-190">V entite **ContactId** pre **loyCustomers** zmeňte zobrazovaný názov na **ContactIdLOYALTY** na odlíšenie od ostatných prijatých ID.</span><span class="sxs-lookup"><span data-stu-id="00f43-190">On the **ContactId** for **loyCustomers** entity, change the display name to **ContactIdLOYALTY** to differentiate it from the other IDs ingested.</span></span>

   :::image type="content" source="media/unify-merge-contactid.PNG" alt-text="premenovanie contactid z loyaltyid.":::

1. <span data-ttu-id="00f43-192">Vyberte **Uložiť** a **Spustiť** na začatie procesu zlúčenia.</span><span class="sxs-lookup"><span data-stu-id="00f43-192">Select **Save** and **Run** to start the Merge Process.</span></span>


## <a name="task-3---configure-the-subscription-churn-prediction"></a><span data-ttu-id="00f43-193">Úloha 3 – Konfigurácia predikcie odchodov predplatiteľov</span><span class="sxs-lookup"><span data-stu-id="00f43-193">Task 3 - Configure the subscription churn prediction</span></span>

<span data-ttu-id="00f43-194">Po zavedení zjednotených profilov zákazníkov môžeme teraz spustiť predikciu odchodu predplatiteľov.</span><span class="sxs-lookup"><span data-stu-id="00f43-194">With the unified customer profiles in place, we can now run the subscription churn prediction.</span></span> <span data-ttu-id="00f43-195">Podrobné kroky nájdete v článku [Predikcia odchodu predplatiteľov (ukážka)](predict-subscription-churn.md).</span><span class="sxs-lookup"><span data-stu-id="00f43-195">For detailed steps, see the [Subscription churn prediction (preview)](predict-subscription-churn.md) article.</span></span> 

1. <span data-ttu-id="00f43-196">Prejdite na **Analýza** > **Objavovať** a vyberte použitie **Model odchodu zákazníkov**.</span><span class="sxs-lookup"><span data-stu-id="00f43-196">Go to **Intelligence** > **Discover** and select to use the **Customer churn model**.</span></span>

1. <span data-ttu-id="00f43-197">Vyberte možnosť **Predplatné** a vyberte **Začíname**.</span><span class="sxs-lookup"><span data-stu-id="00f43-197">Select the **Subscription** option and select **Get started**.</span></span>

1. <span data-ttu-id="00f43-198">Pomenujte model **Predikcia odchodov predplatiteľov OOB** a výstupnú entitu **OOBSubscriptionChurnPrediction**.</span><span class="sxs-lookup"><span data-stu-id="00f43-198">Name the model **OOB Subscription Churn Prediction** and the output entity **OOBSubscriptionChurnPrediction**.</span></span>

1. <span data-ttu-id="00f43-199">Definujte dve podmienky pre model odchodu:</span><span class="sxs-lookup"><span data-stu-id="00f43-199">Define two conditions for the churn model:</span></span>

   * <span data-ttu-id="00f43-200">**Dni od ukončenia predplatného**: **najmenej 60** dní.</span><span class="sxs-lookup"><span data-stu-id="00f43-200">**Days since subscription ended**: **at least 60** days.</span></span> <span data-ttu-id="00f43-201">Ak zákazník neobnoví svoje predplatné v tomto období po skončení predplatného, považuje sa za odídeného.</span><span class="sxs-lookup"><span data-stu-id="00f43-201">If a customer doesn't renew the subscription in this period after their subscription ended, they are considered churned.</span></span> 

   * <span data-ttu-id="00f43-202">**Definícia odchodu**: **najmenej 93** dní.</span><span class="sxs-lookup"><span data-stu-id="00f43-202">**Churn definition**: **at least 93** days.</span></span> <span data-ttu-id="00f43-203">Doba, počas ktorej model predikuje, ktorí zákazníci by mohli odísť.</span><span class="sxs-lookup"><span data-stu-id="00f43-203">The duration the model predict which customers might churn.</span></span> <span data-ttu-id="00f43-204">Čím ďalej do budúcnosti budete pozerať, tým budú výsledky menej presné.</span><span class="sxs-lookup"><span data-stu-id="00f43-204">The further in the future you look, the less precise the results.</span></span>

     :::image type="content" source="media/model-subs-levers.PNG" alt-text="Vyberte úrovne modelov Okno predikcie a Definícia odchodu.":::

1. <span data-ttu-id="00f43-206">Vyberte **Pridať požadované údaje** a **Pridať údaje** pre históriu predplatného.</span><span class="sxs-lookup"><span data-stu-id="00f43-206">Select **Add required data** and select **Add data** for subscription history.</span></span>

1. <span data-ttu-id="00f43-207">Pridajte entitu **Subscription : SubscriptionHistory** a mapujte polia z eCommerce na zodpovedajúce polia požadované modelom.</span><span class="sxs-lookup"><span data-stu-id="00f43-207">Add the **Subscription : SubscriptionHistory** entity and map the fields from eCommerce to the corresponding fields required by the model.</span></span>

1. <span data-ttu-id="00f43-208">Spojte entitu **Subscription : SubscriptionHistory** s **eCommerceContacts : eCommerce**, pomenujte vzťah **eCommerceSubscription**.</span><span class="sxs-lookup"><span data-stu-id="00f43-208">Join the **Subscription : SubscriptionHistory** entity with **eCommerceContacts : eCommerce**, name the relationship **eCommerceSubscription**.</span></span>

   :::image type="content" source="media/model-subscription-join.PNG" alt-text="Spojenie entít eCommerce.":::

1. <span data-ttu-id="00f43-210">V časti Aktivity zákazníkov pridajte entitu **webReviews : Website** a mapujte polia z webReviews na zodpovedajúce polia požadované modelom.</span><span class="sxs-lookup"><span data-stu-id="00f43-210">Under Customer Activities, add the **webReviews : Website** entity and map the fields from webReviews to the corresponding fields required by the model.</span></span> 
   - <span data-ttu-id="00f43-211">Primárny kľúč: ReviewId</span><span class="sxs-lookup"><span data-stu-id="00f43-211">Primary key: ReviewId</span></span>
   - <span data-ttu-id="00f43-212">Časová pečiatka: ReviewDate</span><span class="sxs-lookup"><span data-stu-id="00f43-212">Timestamp: ReviewDate</span></span>
   - <span data-ttu-id="00f43-213">Udalosť: ReviewRating</span><span class="sxs-lookup"><span data-stu-id="00f43-213">Event: ReviewRating</span></span>

1. <span data-ttu-id="00f43-214">Nakonfigurujte aktivitu pre recenzie na webových stránkach.</span><span class="sxs-lookup"><span data-stu-id="00f43-214">Configure an activity for website reviews.</span></span> <span data-ttu-id="00f43-215">Vyberte aktivitu **Recenzia** a spojte entitu **webReviews : Website** s **eCommerceContacts : eCommerce**.</span><span class="sxs-lookup"><span data-stu-id="00f43-215">Select the activity **Review** and join the **webReviews : Website** entity with **eCommerceContacts : eCommerce**.</span></span>

1. <span data-ttu-id="00f43-216">Vyberte **Ďalej** na nastavenie plánu modelu.</span><span class="sxs-lookup"><span data-stu-id="00f43-216">Select **Next** to set the model schedule.</span></span>

   <span data-ttu-id="00f43-217">Model sa musí pravidelne trénovať, aby sa naučil nové vzorce, keď dôjde k prijatiu nových údajov.</span><span class="sxs-lookup"><span data-stu-id="00f43-217">The model needs to train regularly to learn new patterns when there is new data ingested.</span></span> <span data-ttu-id="00f43-218">Pre tento príklad vyberte **Mesačne**.</span><span class="sxs-lookup"><span data-stu-id="00f43-218">For this example, select **Monthly**.</span></span>

1. <span data-ttu-id="00f43-219">Po skontrolovaní všetkých podrobností vyberte možnosť **Uložiť a spustiť**.</span><span class="sxs-lookup"><span data-stu-id="00f43-219">After reviewing all the details, select **Save and Run**.</span></span>

## <a name="task-4---review-model-results-and-explanations"></a><span data-ttu-id="00f43-220">Úloha 4 – Skontrolujte výsledky modelu a vysvetlenia</span><span class="sxs-lookup"><span data-stu-id="00f43-220">Task 4 - Review model results and explanations</span></span>

<span data-ttu-id="00f43-221">Nechajte model absolvovať školenie a skórovanie údajov.</span><span class="sxs-lookup"><span data-stu-id="00f43-221">Let the model complete the training and scoring of the data.</span></span> <span data-ttu-id="00f43-222">Teraz si môžete vysvetlenie modelu odchodu predplatiteľov.</span><span class="sxs-lookup"><span data-stu-id="00f43-222">You can now review the subscription churn model explanations.</span></span> <span data-ttu-id="00f43-223">Viac informácií nájdete v článku [Kontrola stavu predikcie a výsledkov](predict-subscription-churn.md#review-a-prediction-status-and-results).</span><span class="sxs-lookup"><span data-stu-id="00f43-223">For more information, see [Review a prediction status and results](predict-subscription-churn.md#review-a-prediction-status-and-results).</span></span>

## <a name="task-5---create-a-segment-of-high-churn-risk-customers"></a><span data-ttu-id="00f43-224">Úloha 5 – Vytvorenie segmentu zákazníkov s vysokým rizikom odchodu</span><span class="sxs-lookup"><span data-stu-id="00f43-224">Task 5 - Create a segment of high churn-risk customers</span></span>

<span data-ttu-id="00f43-225">Spustením produkčného modelu sa vytvorí nová entita, ktorú môžete vidieť v ponuke **Údaje** > **Entity**.</span><span class="sxs-lookup"><span data-stu-id="00f43-225">Running the production model creates a new entity that you can see in **Data** > **Entities**.</span></span>   

<span data-ttu-id="00f43-226">Nový segment môžete vytvoriť na základe entity vytvorenej modelom.</span><span class="sxs-lookup"><span data-stu-id="00f43-226">You can create a new segment based on the entity created by the model.</span></span>

1.  <span data-ttu-id="00f43-227">Prejdite na **Segmenty**.</span><span class="sxs-lookup"><span data-stu-id="00f43-227">Go to **Segments**.</span></span> <span data-ttu-id="00f43-228">Vyberte **Nový** následne **Vytvoriť z** > **Analýza**.</span><span class="sxs-lookup"><span data-stu-id="00f43-228">Select **New** and choose **Create from** > **Intelligence**.</span></span> 

   :::image type="content" source="media/segment-intelligence.PNG" alt-text="Vytvorenie segmentu s výstupom modelu.":::

1. <span data-ttu-id="00f43-230">Vyberte koncový bod **OOBSubscriptionChurnPrediction** a definujte segment:</span><span class="sxs-lookup"><span data-stu-id="00f43-230">Select the **OOBSubscriptionChurnPrediction** endpoint and define the segment:</span></span> 
   - <span data-ttu-id="00f43-231">Pole: ChurnScore</span><span class="sxs-lookup"><span data-stu-id="00f43-231">Field: ChurnScore</span></span>
   - <span data-ttu-id="00f43-232">Operátor: je väčšie ako</span><span class="sxs-lookup"><span data-stu-id="00f43-232">Operator: greater than</span></span>
   - <span data-ttu-id="00f43-233">Hodnota: 0,6</span><span class="sxs-lookup"><span data-stu-id="00f43-233">Value: 0.6</span></span>
   
   :::image type="content" source="media/segment-setup-subs.PNG" alt-text="Nastavenie segmentu odchodu predplatiteľov.":::

<span data-ttu-id="00f43-235">Teraz máte segment, ktorý sa dynamicky aktualizuje a ktorý identifikuje vysoko rizikových zákazníkov pre toto predplatné.</span><span class="sxs-lookup"><span data-stu-id="00f43-235">You now have a segment that is dynamically updated which identifies high churn-risk customers for this subscription business.</span></span>

<span data-ttu-id="00f43-236">Ďalšie informácie nájdete v téme [Tvorba a správa segmentov](segments.md).</span><span class="sxs-lookup"><span data-stu-id="00f43-236">For more information, see [Create and manage segments](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]