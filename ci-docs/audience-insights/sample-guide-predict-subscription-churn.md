---
title: Predikcia odchodu predplatiteľov – vzorový sprievodca
description: V tomto vzorovom sprievodcovi môžete vyskúšať vopred pripravený model predikcie odchodu predplatiteľov.
ms.date: 11/19/2020
ms.reviewer: digranad
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 2537cfb5dde0d1ce1af16f585f0bf91d15ea1870
ms.sourcegitcommit: a6e7df90d61450e00886753eb5db116f2f35bb6c
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 12/01/2020
ms.locfileid: "4653999"
---
# <a name="subscription-churn-prediction-preview-sample-guide"></a><span data-ttu-id="ba9ed-103">Predikcia odchodu predplatiteľov (ukážka) – vzorový sprievodca</span><span class="sxs-lookup"><span data-stu-id="ba9ed-103">Subscription churn prediction (preview) sample guide</span></span>

<span data-ttu-id="ba9ed-104">Prejdeme si podrobný príklad predikcie odchodov predplatiteľov pomocou nižšie uvedených údajov.</span><span class="sxs-lookup"><span data-stu-id="ba9ed-104">We'll walk you through an end to end example of subscription churn prediction using the sample data provided below.</span></span> 

## <a name="scenario"></a><span data-ttu-id="ba9ed-105">Scenár</span><span class="sxs-lookup"><span data-stu-id="ba9ed-105">Scenario</span></span>

<span data-ttu-id="ba9ed-106">Contoso je spoločnosť, ktorá vyrába vysokokvalitnú kávu a kávovary, ktoré predávajú prostredníctvom svojich webových stránok Contoso Coffee.</span><span class="sxs-lookup"><span data-stu-id="ba9ed-106">Contoso is a company that produces high-quality coffee and coffee machines, which they sell through their Contoso Coffee website.</span></span> <span data-ttu-id="ba9ed-107">Nedávno začali ponúkať pre svojich zákazníkov možnosť predplatného, aby mohli pravidelne dostávať kávu.</span><span class="sxs-lookup"><span data-stu-id="ba9ed-107">They recently started a subscription business for their customers to get coffee on a regular basis.</span></span> <span data-ttu-id="ba9ed-108">Ich cieľom je pochopiť, ktorí zákazníci s predplatným môžu predplatné v najbližších mesiacoch zrušiť.</span><span class="sxs-lookup"><span data-stu-id="ba9ed-108">Their goal is to understand, which subscribed customers might cancel their subscription in the next few months.</span></span> <span data-ttu-id="ba9ed-109">Poznatok, ktorý z ich zákazníkov **pravdepodobne odíde**, im môže im pomôcť ušetriť marketingové úsilie zameraním na ich udržanie.</span><span class="sxs-lookup"><span data-stu-id="ba9ed-109">Knowing which of their customers is **likely to churn**, can help them save marketing efforts by focusing on keeping them.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="ba9ed-110">Predpoklady</span><span class="sxs-lookup"><span data-stu-id="ba9ed-110">Prerequisites</span></span>

- <span data-ttu-id="ba9ed-111">Minimálne [povolenia prispievateľa](permissions.md) v Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="ba9ed-111">At least [Contributor permissions](permissions.md) in Customer Insights.</span></span>
- <span data-ttu-id="ba9ed-112">Odporúčame vám vykonať nasledujúce kroky [v novom prostredí](manage-environments.md).</span><span class="sxs-lookup"><span data-stu-id="ba9ed-112">We recommend that you implement the following steps [in a new environment](manage-environments.md).</span></span>

## <a name="task-1---ingest-data"></a><span data-ttu-id="ba9ed-113">Úloha 1 – Príjem údajov</span><span class="sxs-lookup"><span data-stu-id="ba9ed-113">Task 1 - Ingest Data</span></span>

<span data-ttu-id="ba9ed-114">Prečítajte si články [o príjme údajov](data-sources.md) a konkrétne o [importe zdrojov údajov pomocou konektorov Power Query](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="ba9ed-114">Review the articles [about data ingestion](data-sources.md) and [importing data sources using Power Query connectors](connect-power-query.md) specifically.</span></span> <span data-ttu-id="ba9ed-115">Nasledujúce informácie predpokladajú, že ste sa oboznámili s prijímaním údajov vo všeobecnosti.</span><span class="sxs-lookup"><span data-stu-id="ba9ed-115">The following information assumes you familiarized with ingesting data in general.</span></span> 

### <a name="ingest-customer-data-from-ecommerce-platform"></a><span data-ttu-id="ba9ed-116">Príjem údajov o zákazníkoch z platformy eCommerce</span><span class="sxs-lookup"><span data-stu-id="ba9ed-116">Ingest customer data from eCommerce platform</span></span>

1. <span data-ttu-id="ba9ed-117">Vytvorte zdroj údajov s názvom **eCommerce**, vyberte možnosť importu a vyberte konektor **Text/CSV**.</span><span class="sxs-lookup"><span data-stu-id="ba9ed-117">Create a data source named **eCommerce**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="ba9ed-118">Zadajte adresu URL kontaktov pre eCommerce https://aka.ms/ciadclasscontacts.</span><span class="sxs-lookup"><span data-stu-id="ba9ed-118">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscontacts.</span></span>

1. <span data-ttu-id="ba9ed-119">Počas úpravy údajov vyberte **Transformovať** a potom **Použiť prvý riadok ako hlavičky**.</span><span class="sxs-lookup"><span data-stu-id="ba9ed-119">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="ba9ed-120">Aktualizujte typ údajov pre stĺpce uvedené nižšie:</span><span class="sxs-lookup"><span data-stu-id="ba9ed-120">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="ba9ed-121">**DateOfBirth**: Dátum</span><span class="sxs-lookup"><span data-stu-id="ba9ed-121">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="ba9ed-122">**CreatedOn**: Dátum/Čas/Pásmo</span><span class="sxs-lookup"><span data-stu-id="ba9ed-122">**CreatedOn**: Date/Time/Zone</span></span>

   [!div class="mx-imgBorder"]
   <span data-ttu-id="ba9ed-123">![Transformovať dátum narodenia na dátum](media/ecommerce-dob-date.PNG "transformovať dátum narodenia na dátum")</span><span class="sxs-lookup"><span data-stu-id="ba9ed-123">![Transform DoB to Date](media/ecommerce-dob-date.PNG "transform date of birth to date")</span></span>

1. <span data-ttu-id="ba9ed-124">V poli „Názov“ na pravej table premenujte svoj zdroj údajov z **Dotaz** na **eCommerceContacts**</span><span class="sxs-lookup"><span data-stu-id="ba9ed-124">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **eCommerceContacts**</span></span>

1. <span data-ttu-id="ba9ed-125">Uložte zdroj údajov.</span><span class="sxs-lookup"><span data-stu-id="ba9ed-125">Save the data source.</span></span>

### <a name="ingest-customer-data-from-loyalty-schema"></a><span data-ttu-id="ba9ed-126">Príjem údaje o zákazníkoch z vernostnej schémy</span><span class="sxs-lookup"><span data-stu-id="ba9ed-126">Ingest customer data from loyalty schema</span></span>

1. <span data-ttu-id="ba9ed-127">Vytvorte zdroj údajov s názvom **LoyaltyScheme**, vyberte možnosť importu a vyberte konektor **Text/CSV**.</span><span class="sxs-lookup"><span data-stu-id="ba9ed-127">Create a data source named **LoyaltyScheme**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="ba9ed-128">Zadajte adresu URL kontaktov pre eCommerce https://aka.ms/ciadclasscustomerloyalty.</span><span class="sxs-lookup"><span data-stu-id="ba9ed-128">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscustomerloyalty.</span></span>

1. <span data-ttu-id="ba9ed-129">Počas úpravy údajov vyberte **Transformovať** a potom **Použiť prvý riadok ako hlavičky**.</span><span class="sxs-lookup"><span data-stu-id="ba9ed-129">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="ba9ed-130">Aktualizujte typ údajov pre stĺpce uvedené nižšie:</span><span class="sxs-lookup"><span data-stu-id="ba9ed-130">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="ba9ed-131">**DateOfBirth**: Dátum</span><span class="sxs-lookup"><span data-stu-id="ba9ed-131">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="ba9ed-132">**RewardsPoints**: Celé číslo</span><span class="sxs-lookup"><span data-stu-id="ba9ed-132">**RewardsPoints**: Whole Number</span></span>
   - <span data-ttu-id="ba9ed-133">**CreatedOn**: Dátum/Čas</span><span class="sxs-lookup"><span data-stu-id="ba9ed-133">**CreatedOn**: Date/Time</span></span>

1. <span data-ttu-id="ba9ed-134">V poli „Názov“ na pravej table premenujte svoj zdroj údajov z **Dotaz** na **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="ba9ed-134">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **loyCustomers**.</span></span>

1. <span data-ttu-id="ba9ed-135">Uložte zdroj údajov.</span><span class="sxs-lookup"><span data-stu-id="ba9ed-135">Save the data source.</span></span>

### <a name="ingest-subscription-information"></a><span data-ttu-id="ba9ed-136">Príjem informácií o predplatnom</span><span class="sxs-lookup"><span data-stu-id="ba9ed-136">Ingest subscription information</span></span>

1. <span data-ttu-id="ba9ed-137">Vytvorte zdroj údajov s názvom **SubscriptionHistory**, vyberte možnosť importu a vyberte konektor **Text/CSV**.</span><span class="sxs-lookup"><span data-stu-id="ba9ed-137">Create a data source named **SubscriptionHistory**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="ba9ed-138">Zadajte adresu URL kontaktov pre eCommerce https://aka.ms/ciadchurnsubscriptionhistory.</span><span class="sxs-lookup"><span data-stu-id="ba9ed-138">Enter the URL for eCommerce contacts https://aka.ms/ciadchurnsubscriptionhistory.</span></span>

1. <span data-ttu-id="ba9ed-139">Počas úpravy údajov vyberte **Transformovať** a potom **Použiť prvý riadok ako hlavičky**.</span><span class="sxs-lookup"><span data-stu-id="ba9ed-139">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="ba9ed-140">Aktualizujte typ údajov pre stĺpce uvedené nižšie:</span><span class="sxs-lookup"><span data-stu-id="ba9ed-140">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="ba9ed-141">**SubscriptioID**: Celé číslo</span><span class="sxs-lookup"><span data-stu-id="ba9ed-141">**SubscriptioID**: Whole Number</span></span>
   - <span data-ttu-id="ba9ed-142">**SubscriptionAmount**: Mena</span><span class="sxs-lookup"><span data-stu-id="ba9ed-142">**SubscriptionAmount**: Currency</span></span>
   - <span data-ttu-id="ba9ed-143">**SubscriptionEndDate**: Dátum/Čas</span><span class="sxs-lookup"><span data-stu-id="ba9ed-143">**SubscriptionEndDate**: Date/Time</span></span>
   - <span data-ttu-id="ba9ed-144">**SubscriptionStartDate**: Dátum/Čas</span><span class="sxs-lookup"><span data-stu-id="ba9ed-144">**SubscriptionStartDate**: Date/Time</span></span>
   - <span data-ttu-id="ba9ed-145">**TransactionDate**: Dátum/Čas</span><span class="sxs-lookup"><span data-stu-id="ba9ed-145">**TransactionDate**: Date/Time</span></span>
   - <span data-ttu-id="ba9ed-146">**IsRecurring**: Pravda/Nepravda</span><span class="sxs-lookup"><span data-stu-id="ba9ed-146">**IsRecurring**: True/False</span></span>
   - <span data-ttu-id="ba9ed-147">**Is_auto_renew**: Pravda/Nepravda</span><span class="sxs-lookup"><span data-stu-id="ba9ed-147">**Is_auto_renew**: True/False</span></span>
   - <span data-ttu-id="ba9ed-148">**RecurringFrequencyInMonths**: Celé číslo</span><span class="sxs-lookup"><span data-stu-id="ba9ed-148">**RecurringFrequencyInMonths**: Whole Number</span></span>

1. <span data-ttu-id="ba9ed-149">V poli „Názov“ na pravej table premenujte svoj zdroj údajov z **Query** na **SubscriptionHistory**.</span><span class="sxs-lookup"><span data-stu-id="ba9ed-149">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **SubscriptionHistory**.</span></span>

1. <span data-ttu-id="ba9ed-150">Uložte zdroj údajov.</span><span class="sxs-lookup"><span data-stu-id="ba9ed-150">Save the data source.</span></span>

### <a name="ingest-customer-data-from-website-reviews"></a><span data-ttu-id="ba9ed-151">Príjem údajov o zákazníkoch z recenzií na webe</span><span class="sxs-lookup"><span data-stu-id="ba9ed-151">Ingest customer data from website reviews</span></span>

1. <span data-ttu-id="ba9ed-152">Vytvorte zdroj údajov s názvom **Website**, vyberte možnosť importu a vyberte konektor **Text/CSV**.</span><span class="sxs-lookup"><span data-stu-id="ba9ed-152">Create a data source named **Website**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="ba9ed-153">Zadajte adresu URL kontaktov pre eCommerce https://aka.ms/ciadclasswebsite.</span><span class="sxs-lookup"><span data-stu-id="ba9ed-153">Enter the URL for eCommerce contacts https://aka.ms/ciadclasswebsite.</span></span>

1. <span data-ttu-id="ba9ed-154">Počas úpravy údajov vyberte **Transformovať** a potom **Použiť prvý riadok ako hlavičky**.</span><span class="sxs-lookup"><span data-stu-id="ba9ed-154">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="ba9ed-155">Aktualizujte typ údajov pre stĺpce uvedené nižšie:</span><span class="sxs-lookup"><span data-stu-id="ba9ed-155">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="ba9ed-156">**ReviewRating**: Celé číslo</span><span class="sxs-lookup"><span data-stu-id="ba9ed-156">**ReviewRating**: Whole Number</span></span>
   - <span data-ttu-id="ba9ed-157">**ReviewDate**: Dátum</span><span class="sxs-lookup"><span data-stu-id="ba9ed-157">**ReviewDate**: Date</span></span>

1. <span data-ttu-id="ba9ed-158">V poli „Názov“ na pravej table premenujte svoj zdroj údajov z **Query** na **webReviews**.</span><span class="sxs-lookup"><span data-stu-id="ba9ed-158">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **webReviews**.</span></span>

## <a name="task-2---data-unification"></a><span data-ttu-id="ba9ed-159">Úloha 2 – Zjednotenie údajov</span><span class="sxs-lookup"><span data-stu-id="ba9ed-159">Task 2 - Data unification</span></span>

<span data-ttu-id="ba9ed-160">Po prijatí údajov teraz začíname proces **Mapovanie, párovanie, zlúčenie** na vytvorenie zjednoteného profilu zákazníka.</span><span class="sxs-lookup"><span data-stu-id="ba9ed-160">After ingesting the data we now begin the **Map, Match, Merge** process to create a unified customer profile.</span></span> <span data-ttu-id="ba9ed-161">Ďalšie informácie nájdete v téme [Zjednotenie údajov](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="ba9ed-161">For more information, see [Data unification](data-unification.md).</span></span>

### <a name="map"></a><span data-ttu-id="ba9ed-162">Priradenie</span><span class="sxs-lookup"><span data-stu-id="ba9ed-162">Map</span></span>

1. <span data-ttu-id="ba9ed-163">Po prijatí údajov namapujte kontakty z údajov eCommerce a Loyalty na bežné typy údajov.</span><span class="sxs-lookup"><span data-stu-id="ba9ed-163">After ingesting the data, map contacts from eCommerce and Loyalty data to common data types.</span></span> <span data-ttu-id="ba9ed-164">Prejdite na **Údaje** > **Zjednotenie** > **Mapovanie**.</span><span class="sxs-lookup"><span data-stu-id="ba9ed-164">Go to **Data** > **Unify** > **Map**.</span></span>

1. <span data-ttu-id="ba9ed-165">Vyberte entity, ktoré zastupujú profil zákazníka – **eCommerceContacts** a **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="ba9ed-165">Select the entities that represent the customer profile – **eCommerceContacts** and **loyCustomers**.</span></span> 

   :::image type="content" source="media/unify-ecommerce-loyalty.PNG" alt-text="Zjednotenie zdrojov údajov elektronického obchodu a vernostných údajov.":::

1. <span data-ttu-id="ba9ed-167">Vyberte **ContactId** ako primárny kľúč pre **eCommerceContacts** a **LoyaltyID** ako primárny kľúč pre **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="ba9ed-167">Select **ContactId** as the primary key for **eCommerceContacts** and **LoyaltyID** as the primary key for **loyCustomers**.</span></span>

   :::image type="content" source="media/unify-loyaltyid.PNG" alt-text="Zjednotenie LoyaltyId ako primárny kľúč.":::

### <a name="match"></a><span data-ttu-id="ba9ed-169">Spárovanie</span><span class="sxs-lookup"><span data-stu-id="ba9ed-169">Match</span></span>

1. <span data-ttu-id="ba9ed-170">Prejdite na kartu **Spárovanie** a vyberte **Nastaviť poradie**.</span><span class="sxs-lookup"><span data-stu-id="ba9ed-170">Go to the **Match** tab and select **Set Order**.</span></span>

1. <span data-ttu-id="ba9ed-171">V rozbaľovacom zozname **Primárny** vyberte **eCommerceContacts: eCommerce** ako primárny zdroj a zahrňte všetky záznamy.</span><span class="sxs-lookup"><span data-stu-id="ba9ed-171">In the **Primary** drop-down list, choose **eCommerceContacts : eCommerce** as the primary source and include all records.</span></span>

1. <span data-ttu-id="ba9ed-172">V rozbaľovacom zozname **Entita 2** vyberte **loyCustomers: LoyaltyScheme** a zahrňte všetky záznamy.</span><span class="sxs-lookup"><span data-stu-id="ba9ed-172">In the **Entity 2** drop-down list, choose **loyCustomers : LoyaltyScheme** and include all records.</span></span>

   :::image type="content" source="media/unify-match-order.PNG" alt-text="Zjednotenie zosúladenia eCommerce a Loyalty.":::

1. <span data-ttu-id="ba9ed-174">Vyberte **Vytvoriť nové pravidlo**</span><span class="sxs-lookup"><span data-stu-id="ba9ed-174">Select **Create a new rule**</span></span>

1. <span data-ttu-id="ba9ed-175">Pridajte svoju prvú podmienku pomocou FullName.</span><span class="sxs-lookup"><span data-stu-id="ba9ed-175">Add your first condition using FullName.</span></span>

   * <span data-ttu-id="ba9ed-176">Pre eCommerceContacts vyberte v rozbaľovacej ponuke **FullName**.</span><span class="sxs-lookup"><span data-stu-id="ba9ed-176">For eCommerceContacts select **FullName** in the drop-down.</span></span>
   * <span data-ttu-id="ba9ed-177">Pre loyCustomers vyberte v rozbaľovacej ponuke **FullName**.</span><span class="sxs-lookup"><span data-stu-id="ba9ed-177">For loyCustomers select **FullName** in the drop-down.</span></span>
   * <span data-ttu-id="ba9ed-178">Vyberte rozbaľovací zoznam **Normalizovať** a vyberte **Typ (Telefón, Meno, Adresa, ...)**.</span><span class="sxs-lookup"><span data-stu-id="ba9ed-178">Select the **Normalize** drop down and choose **Type (Phone, Name, Address, ...)**.</span></span>
   * <span data-ttu-id="ba9ed-179">Nastavte **Úroveň presnosti**: **Základná** a **Hodnota**: **Vysoká**.</span><span class="sxs-lookup"><span data-stu-id="ba9ed-179">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

1. <span data-ttu-id="ba9ed-180">Zadajte meno **FullName, E-mail** pre nové pravidlo.</span><span class="sxs-lookup"><span data-stu-id="ba9ed-180">Enter the name **FullName, Email** for the new rule.</span></span>

   * <span data-ttu-id="ba9ed-181">Vyberte druhú podmienku pre e-mailovú adresu výberom možnosti **Pridať podmienku**</span><span class="sxs-lookup"><span data-stu-id="ba9ed-181">Add a second condition for email address by selecting **Add Condition**</span></span>
   * <span data-ttu-id="ba9ed-182">Pre entitu eCommerceContacts vyberte v rozbaľovacej ponuke **E-mail**.</span><span class="sxs-lookup"><span data-stu-id="ba9ed-182">For entity eCommerceContacts, choose **EMail** in drop-down.</span></span>
   * <span data-ttu-id="ba9ed-183">Pre entitu loyCustomers vyberte v rozbaľovacej ponuke **E-mail**.</span><span class="sxs-lookup"><span data-stu-id="ba9ed-183">For entity loyCustomers, choose **EMail** in the drop-down.</span></span> 
   * <span data-ttu-id="ba9ed-184">Pole Normalizovať nechajte prázdne.</span><span class="sxs-lookup"><span data-stu-id="ba9ed-184">Leave Normalize blank.</span></span> 
   * <span data-ttu-id="ba9ed-185">Nastavte **Úroveň presnosti**: **Základná** a **Hodnota**: **Vysoká**.</span><span class="sxs-lookup"><span data-stu-id="ba9ed-185">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

   :::image type="content" source="media/unify-match-rule.PNG" alt-text="Pravidlo zjednotenia zhody pre meno a e-mail.":::

7. <span data-ttu-id="ba9ed-187">Vyberte položku **Uložiť** a **Spustiť**.</span><span class="sxs-lookup"><span data-stu-id="ba9ed-187">Select **Save** and **Run**.</span></span>

### <a name="merge"></a><span data-ttu-id="ba9ed-188">Zlúčenie</span><span class="sxs-lookup"><span data-stu-id="ba9ed-188">Merge</span></span>

1. <span data-ttu-id="ba9ed-189">Prejdite na kartu **Zlúčiť**.</span><span class="sxs-lookup"><span data-stu-id="ba9ed-189">Go to the **Merge** tab.</span></span>

1. <span data-ttu-id="ba9ed-190">V entite **ContactId** pre **loyCustomers** zmeňte zobrazovaný názov na **ContactIdLOYALTY** na odlíšenie od ostatných prijatých ID.</span><span class="sxs-lookup"><span data-stu-id="ba9ed-190">On the **ContactId** for **loyCustomers** entity, change the display name to **ContactIdLOYALTY** to differentiate it from the other IDs ingested.</span></span>

   :::image type="content" source="media/unify-merge-contactid.PNG" alt-text="premenovanie contactid z loyaltyid.":::

1. <span data-ttu-id="ba9ed-192">Vyberte **Uložiť** a **Spustiť** na začatie procesu zlúčenia.</span><span class="sxs-lookup"><span data-stu-id="ba9ed-192">Select **Save** and **Run** to start the Merge Process.</span></span>


## <a name="task-3---configure-the-subscription-churn-prediction"></a><span data-ttu-id="ba9ed-193">Úloha 3 – Konfigurácia predikcie odchodov predplatiteľov</span><span class="sxs-lookup"><span data-stu-id="ba9ed-193">Task 3 - Configure the subscription churn prediction</span></span>

<span data-ttu-id="ba9ed-194">Po zavedení zjednotených profilov zákazníkov môžeme teraz spustiť predikciu odchodu predplatiteľov.</span><span class="sxs-lookup"><span data-stu-id="ba9ed-194">With the unified customer profiles in place, we can now run the subscription churn prediction.</span></span> <span data-ttu-id="ba9ed-195">Podrobné kroky nájdete v článku [Predikcia odchodu predplatiteľov (ukážka)](predict-subscription-churn.md).</span><span class="sxs-lookup"><span data-stu-id="ba9ed-195">For detailed steps, see the [Subscription churn prediction (preview)](predict-subscription-churn.md) article.</span></span> 

1. <span data-ttu-id="ba9ed-196">Prejdite na **Analýza** > **Objavovať** a vyberte použitie **Model odchodu zákazníkov**.</span><span class="sxs-lookup"><span data-stu-id="ba9ed-196">Go to **Intelligence** > **Discover** and select to use the **Customer churn model**.</span></span>

1. <span data-ttu-id="ba9ed-197">Vyberte možnosť **Predplatné** a vyberte **Začíname**.</span><span class="sxs-lookup"><span data-stu-id="ba9ed-197">Select the **Subscription** option and select **Get started**.</span></span>

1. <span data-ttu-id="ba9ed-198">Pomenujte model **Predikcia odchodov predplatiteľov OOB** a výstupnú entitu **OOBSubscriptionChurnPrediction**.</span><span class="sxs-lookup"><span data-stu-id="ba9ed-198">Name the model **OOB Subscription Churn Prediction** and the output entity **OOBSubscriptionChurnPrediction**.</span></span>

1. <span data-ttu-id="ba9ed-199">Definujte dve podmienky pre model odchodu:</span><span class="sxs-lookup"><span data-stu-id="ba9ed-199">Define two conditions for the churn model:</span></span>

   * <span data-ttu-id="ba9ed-200">**Dni od ukončenia predplatného**: **najmenej 60** dní.</span><span class="sxs-lookup"><span data-stu-id="ba9ed-200">**Days since subscription ended**: **at least 60** days.</span></span> <span data-ttu-id="ba9ed-201">Ak zákazník neobnoví svoje predplatné v tomto období po skončení predplatného, považuje sa za odídeného.</span><span class="sxs-lookup"><span data-stu-id="ba9ed-201">If a customer doesn't renew the subscription in this period after their subscription ended, they are considered churned.</span></span> 

   * <span data-ttu-id="ba9ed-202">**Definícia odchodu**: **najmenej 93** dní.</span><span class="sxs-lookup"><span data-stu-id="ba9ed-202">**Churn definition**: **at least 93** days.</span></span> <span data-ttu-id="ba9ed-203">Doba, počas ktorej model predikuje, ktorí zákazníci by mohli odísť.</span><span class="sxs-lookup"><span data-stu-id="ba9ed-203">The duration the model predict which customers might churn.</span></span> <span data-ttu-id="ba9ed-204">Čím ďalej do budúcnosti budete pozerať, tým budú výsledky menej presné.</span><span class="sxs-lookup"><span data-stu-id="ba9ed-204">The further in the future you look, the less precise the results.</span></span>

     :::image type="content" source="media/model-subs-levers.PNG" alt-text="Vyberte úrovne modelov Okno predikcie a Definícia odchodu.":::

1. <span data-ttu-id="ba9ed-206">Vyberte **Pridať požadované údaje** a **Pridať údaje** pre históriu predplatného.</span><span class="sxs-lookup"><span data-stu-id="ba9ed-206">Select **Add required data** and select **Add data** for subscription history.</span></span>

1. <span data-ttu-id="ba9ed-207">Pridajte entitu **Subscription : SubscriptionHistory** a mapujte polia z eCommerce na zodpovedajúce polia požadované modelom.</span><span class="sxs-lookup"><span data-stu-id="ba9ed-207">Add the **Subscription : SubscriptionHistory** entity and map the fields from eCommerce to the corresponding fields required by the model.</span></span>

1. <span data-ttu-id="ba9ed-208">Spojte entitu **Subscription : SubscriptionHistory** s **eCommerceContacts : eCommerce**, pomenujte vzťah **eCommerceSubscription**.</span><span class="sxs-lookup"><span data-stu-id="ba9ed-208">Join the **Subscription : SubscriptionHistory** entity with **eCommerceContacts : eCommerce**, name the relationship **eCommerceSubscription**.</span></span>

   :::image type="content" source="media/model-subscription-join.PNG" alt-text="Spojenie entít eCommerce.":::

1. <span data-ttu-id="ba9ed-210">V časti Aktivity zákazníkov pridajte entitu **webReviews : Website** a mapujte polia z webReviews na zodpovedajúce polia požadované modelom.</span><span class="sxs-lookup"><span data-stu-id="ba9ed-210">Under Customer Activities, add the **webReviews : Website** entity and map the fields from webReviews to the corresponding fields required by the model.</span></span> 
   - <span data-ttu-id="ba9ed-211">Primárny kľúč: ReviewId</span><span class="sxs-lookup"><span data-stu-id="ba9ed-211">Primary key: ReviewId</span></span>
   - <span data-ttu-id="ba9ed-212">Časová pečiatka: ReviewDate</span><span class="sxs-lookup"><span data-stu-id="ba9ed-212">Timestamp: ReviewDate</span></span>
   - <span data-ttu-id="ba9ed-213">Udalosť: ReviewRating</span><span class="sxs-lookup"><span data-stu-id="ba9ed-213">Event: ReviewRating</span></span>

1. <span data-ttu-id="ba9ed-214">Nakonfigurujte aktivitu pre recenzie na webových stránkach.</span><span class="sxs-lookup"><span data-stu-id="ba9ed-214">Configure an activity for website reviews.</span></span> <span data-ttu-id="ba9ed-215">Vyberte aktivitu **Recenzia** a spojte entitu **webReviews : Website** s **eCommerceContacts : eCommerce**.</span><span class="sxs-lookup"><span data-stu-id="ba9ed-215">Select the activity **Review** and join the **webReviews : Website** entity with **eCommerceContacts : eCommerce**.</span></span>

1. <span data-ttu-id="ba9ed-216">Vyberte **Ďalej** na nastavenie plánu modelu.</span><span class="sxs-lookup"><span data-stu-id="ba9ed-216">Select **Next** to set the model schedule.</span></span>

   <span data-ttu-id="ba9ed-217">Model sa musí pravidelne trénovať, aby sa naučil nové vzorce, keď dôjde k prijatiu nových údajov.</span><span class="sxs-lookup"><span data-stu-id="ba9ed-217">The model needs to train regularly to learn new patterns when there is new data ingested.</span></span> <span data-ttu-id="ba9ed-218">Pre tento príklad vyberte **Mesačne**.</span><span class="sxs-lookup"><span data-stu-id="ba9ed-218">For this example, select **Monthly**.</span></span>

1. <span data-ttu-id="ba9ed-219">Po skontrolovaní všetkých podrobností vyberte možnosť **Uložiť a spustiť**.</span><span class="sxs-lookup"><span data-stu-id="ba9ed-219">After reviewing all the details, select **Save and Run**.</span></span>

## <a name="task-4---review-model-results-and-explanations"></a><span data-ttu-id="ba9ed-220">Úloha 4 – Skontrolujte výsledky modelu a vysvetlenia</span><span class="sxs-lookup"><span data-stu-id="ba9ed-220">Task 4 - Review model results and explanations</span></span>

<span data-ttu-id="ba9ed-221">Nechajte model absolvovať školenie a skórovanie údajov.</span><span class="sxs-lookup"><span data-stu-id="ba9ed-221">Let the model complete the training and scoring of the data.</span></span> <span data-ttu-id="ba9ed-222">Teraz si môžete vysvetlenie modelu odchodu predplatiteľov.</span><span class="sxs-lookup"><span data-stu-id="ba9ed-222">You can now review the subscription churn model explanations.</span></span> <span data-ttu-id="ba9ed-223">Viac informácií nájdete v článku [Kontrola stavu predikcie a výsledkov](predict-subscription-churn.md#review-a-prediction-status-and-results).</span><span class="sxs-lookup"><span data-stu-id="ba9ed-223">For more information, see [Review a prediction status and results](predict-subscription-churn.md#review-a-prediction-status-and-results).</span></span>

## <a name="task-5---create-a-segment-of-high-churn-risk-customers"></a><span data-ttu-id="ba9ed-224">Úloha 5 – Vytvorenie segmentu zákazníkov s vysokým rizikom odchodu</span><span class="sxs-lookup"><span data-stu-id="ba9ed-224">Task 5 - Create a segment of high churn-risk customers</span></span>

<span data-ttu-id="ba9ed-225">Spustením produkčného modelu sa vytvorí nová entita, ktorú môžete vidieť v ponuke **Údaje** > **Entity**.</span><span class="sxs-lookup"><span data-stu-id="ba9ed-225">Running the production model creates a new entity that you can see in **Data** > **Entities**.</span></span>   

<span data-ttu-id="ba9ed-226">Nový segment môžete vytvoriť na základe entity vytvorenej modelom.</span><span class="sxs-lookup"><span data-stu-id="ba9ed-226">You can create a new segment based on the entity created by the model.</span></span>

1.  <span data-ttu-id="ba9ed-227">Prejdite na **Segmenty**.</span><span class="sxs-lookup"><span data-stu-id="ba9ed-227">Go to **Segments**.</span></span> <span data-ttu-id="ba9ed-228">Vyberte **Nový** následne **Vytvoriť z** > **Analýza**.</span><span class="sxs-lookup"><span data-stu-id="ba9ed-228">Select **New** and choose **Create from** > **Intelligence**.</span></span> 

   :::image type="content" source="media/segment-intelligence.PNG" alt-text="Vytvorenie segmentu s výstupom modelu.":::

1. <span data-ttu-id="ba9ed-230">Vyberte koncový bod **OOBSubscriptionChurnPrediction** a definujte segment:</span><span class="sxs-lookup"><span data-stu-id="ba9ed-230">Select the **OOBSubscriptionChurnPrediction** endpoint and define the segment:</span></span> 
   - <span data-ttu-id="ba9ed-231">Pole: ChurnScore</span><span class="sxs-lookup"><span data-stu-id="ba9ed-231">Field: ChurnScore</span></span>
   - <span data-ttu-id="ba9ed-232">Operátor: je väčšie ako</span><span class="sxs-lookup"><span data-stu-id="ba9ed-232">Operator: greater than</span></span>
   - <span data-ttu-id="ba9ed-233">Hodnota: 0,6</span><span class="sxs-lookup"><span data-stu-id="ba9ed-233">Value: 0.6</span></span>
   
   :::image type="content" source="media/segment-setup-subs.PNG" alt-text="Nastavenie segmentu odchodu predplatiteľov.":::

<span data-ttu-id="ba9ed-235">Teraz máte segment, ktorý sa dynamicky aktualizuje a ktorý identifikuje vysoko rizikových zákazníkov pre toto predplatné.</span><span class="sxs-lookup"><span data-stu-id="ba9ed-235">You now have a segment that is dynamically updated which identifies high churn-risk customers for this subscription business.</span></span>

<span data-ttu-id="ba9ed-236">Ďalšie informácie nájdete v téme [Tvorba a správa segmentov](segments.md).</span><span class="sxs-lookup"><span data-stu-id="ba9ed-236">For more information, see [Create and manage segments](segments.md).</span></span>
