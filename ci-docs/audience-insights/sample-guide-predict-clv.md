---
title: Predikcie hodnoty životnosti zákazníka – vzorový sprievodca
description: V tomto vzorovom sprievodcovi si môžete vyskúšať model predikcie hodnoty životnosti zákazníka.
ms.date: 05/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: yashlundia
ms.author: yalundia
manager: shellyha
ms.openlocfilehash: 19c1fbadb79ba22c0dc11aa7c3b5b2415add70a7
ms.sourcegitcommit: 0b754d194d765afef70d1008db7b347dd1f0ee40
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 06/24/2021
ms.locfileid: "6306368"
---
# <a name="customer-lifetime-value-clv-prediction-sample-guide"></a><span data-ttu-id="63bf6-103">Predikcie hodnoty životnosti zákazníka (CLV) – vzorový sprievodca</span><span class="sxs-lookup"><span data-stu-id="63bf6-103">Customer lifetime value (CLV) prediction sample guide</span></span>

<span data-ttu-id="63bf6-104">Táto príručka vám podrobne vysvetlí príklad predikcie hodnoty životnosti zákazníka (CLV) v nástroji Customer Insights pomocou vzorových údajov.</span><span class="sxs-lookup"><span data-stu-id="63bf6-104">This guide will walk you through an end to end example of Customer lifetime value (CLV) prediction in Customer Insights using sample data.</span></span>

## <a name="scenario"></a><span data-ttu-id="63bf6-105">Scenár</span><span class="sxs-lookup"><span data-stu-id="63bf6-105">Scenario</span></span>

<span data-ttu-id="63bf6-106">Contoso je spoločnosť, ktorá vyrába vysokokvalitnú kávu a kávovary.</span><span class="sxs-lookup"><span data-stu-id="63bf6-106">Contoso is a company that produces high-quality coffee and coffee machines.</span></span> <span data-ttu-id="63bf6-107">Výrobky predávajú prostredníctvom svojej webovej stránky Contoso Coffee.</span><span class="sxs-lookup"><span data-stu-id="63bf6-107">They sell the products through their Contoso Coffee website.</span></span> <span data-ttu-id="63bf6-108">Spoločnosť chce porozumieť hodnote (výnosom), ktorú môžu jej zákazníci vygenerovať počas nasledujúcich 12 mesiacov.</span><span class="sxs-lookup"><span data-stu-id="63bf6-108">The company wants to understand the value (revenue) that their customers can generate in the next 12 months.</span></span> <span data-ttu-id="63bf6-109">Znalosť očakávanej hodnoty ich zákazníkov počas nasledujúcich 12 mesiacoch im pomôže nasmerovať ich marketingové úsilie na vysoko hodnotných zákazníkov.</span><span class="sxs-lookup"><span data-stu-id="63bf6-109">Knowing the expected value of their customers in the next 12 months will help them steer their marketing efforts on high value customers.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="63bf6-110">Predpoklady</span><span class="sxs-lookup"><span data-stu-id="63bf6-110">Prerequisites</span></span>

- <span data-ttu-id="63bf6-111">Minimálne [povolenia prispievateľa](permissions.md) v prehľadoch cieľovej skupiny.</span><span class="sxs-lookup"><span data-stu-id="63bf6-111">At least [Contributor permissions](permissions.md) in audience insights.</span></span>
- <span data-ttu-id="63bf6-112">Odporúčame vám vykonať nasledujúce kroky [v novom prostredí](manage-environments.md).</span><span class="sxs-lookup"><span data-stu-id="63bf6-112">We recommend that you implement the following steps [in a new environment](manage-environments.md).</span></span>

## <a name="task-1---ingest-data"></a><span data-ttu-id="63bf6-113">Úloha 1 – Príjem údajov</span><span class="sxs-lookup"><span data-stu-id="63bf6-113">Task 1 - Ingest data</span></span>

<span data-ttu-id="63bf6-114">Prečítajte si články [o prijímaní údajov](data-sources.md) a [importe zdrojov údajov pomocou konektorov Power Query](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="63bf6-114">Review the articles [about data ingestion](data-sources.md) and [importing data sources using Power Query connectors](connect-power-query.md).</span></span> <span data-ttu-id="63bf6-115">Nasledujúce informácie predpokladajú, že ste sa oboznámili s prijímaním údajov vo všeobecnosti.</span><span class="sxs-lookup"><span data-stu-id="63bf6-115">The following information assumes you familiarized with ingesting data in general.</span></span>

### <a name="ingest-customer-data-from-ecommerce-platform"></a><span data-ttu-id="63bf6-116">Príjem údajov o zákazníkoch z platformy eCommerce</span><span class="sxs-lookup"><span data-stu-id="63bf6-116">Ingest customer data from eCommerce platform</span></span>

1. <span data-ttu-id="63bf6-117">Vytvorte zdroj údajov s názvom **eCommerce**, vyberte možnosť importu a vyberte konektor **Text/CSV**.</span><span class="sxs-lookup"><span data-stu-id="63bf6-117">Create a data source named  **eCommerce** , choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="63bf6-118">Zadajte adresu URL kontaktov pre eCommerce [https://aka.ms/ciadclasscontacts](https://aka.ms/ciadclasscontacts).</span><span class="sxs-lookup"><span data-stu-id="63bf6-118">Enter the URL for eCommerce contacts [https://aka.ms/ciadclasscontacts](https://aka.ms/ciadclasscontacts).</span></span>

1. <span data-ttu-id="63bf6-119">Počas úpravy údajov vyberte **Transformovať** a potom **Použiť prvý riadok ako hlavičky**.</span><span class="sxs-lookup"><span data-stu-id="63bf6-119">While editing the data, select  **Transform**  and then  **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="63bf6-120">Aktualizujte typ údajov pre stĺpce uvedené nižšie:</span><span class="sxs-lookup"><span data-stu-id="63bf6-120">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="63bf6-121">**DateOfBirth**: Dátum</span><span class="sxs-lookup"><span data-stu-id="63bf6-121">**DateOfBirth** : Date</span></span>
   - <span data-ttu-id="63bf6-122">**CreatedOn**: Dátum/Čas/Pásmo</span><span class="sxs-lookup"><span data-stu-id="63bf6-122">**CreatedOn** : Date/Time/Zone</span></span>

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Transformácia dátumu narodenia na dátum.":::

1. <span data-ttu-id="63bf6-124">V poli „Názov“ na pravej table premenujte svoj zdroj údajov z **Dotaz** na **eCommerceContacts**</span><span class="sxs-lookup"><span data-stu-id="63bf6-124">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **eCommerceContacts**</span></span>

1. <span data-ttu-id="63bf6-125">**Uložte** zdroj údajov.</span><span class="sxs-lookup"><span data-stu-id="63bf6-125">**Save** the data source.</span></span>

### <a name="ingest-online-purchase-data"></a><span data-ttu-id="63bf6-126">Prijmite údaje o online nákupe</span><span class="sxs-lookup"><span data-stu-id="63bf6-126">Ingest online purchase data</span></span>

1. <span data-ttu-id="63bf6-127">K tomu istému zdroju údajov **eCommerce** pridajte ďalšiu množinu údajov.</span><span class="sxs-lookup"><span data-stu-id="63bf6-127">Add another data set to the same **eCommerce** data source.</span></span> <span data-ttu-id="63bf6-128">Znova vyberte konektor **Text/CSV**.</span><span class="sxs-lookup"><span data-stu-id="63bf6-128">Choose the **Text/CSV** connector again.</span></span>

1. <span data-ttu-id="63bf6-129">Zadajte adresu URL pre údaje **Online nákupy** https://aka.ms/ciadclassonline.</span><span class="sxs-lookup"><span data-stu-id="63bf6-129">Enter the URL for **Online Purchases** data https://aka.ms/ciadclassonline.</span></span>

1. <span data-ttu-id="63bf6-130">Počas úpravy údajov vyberte **Transformovať** a potom **Použiť prvý riadok ako hlavičky**.</span><span class="sxs-lookup"><span data-stu-id="63bf6-130">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="63bf6-131">Aktualizujte typ údajov pre stĺpce uvedené nižšie:</span><span class="sxs-lookup"><span data-stu-id="63bf6-131">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="63bf6-132">**PurchasedOn**: Dátum/Čas</span><span class="sxs-lookup"><span data-stu-id="63bf6-132">**PurchasedOn**: Date/Time</span></span>
   - <span data-ttu-id="63bf6-133">**TotalPrice**: Mena</span><span class="sxs-lookup"><span data-stu-id="63bf6-133">**TotalPrice**: Currency</span></span>

1. <span data-ttu-id="63bf6-134">V poli **Názov** na bočnej table premenujte svoj zdroj údajov z **Dotaz** na **eCommercePurchases**.</span><span class="sxs-lookup"><span data-stu-id="63bf6-134">In the **Name** field on the side pane, rename your data source from **Query** to **eCommercePurchases**.</span></span>

1. <span data-ttu-id="63bf6-135">**Uložte** zdroj údajov.</span><span class="sxs-lookup"><span data-stu-id="63bf6-135">**Save** the data source.</span></span>

### <a name="ingest-customer-data-from-loyalty-schema"></a><span data-ttu-id="63bf6-136">Príjem údaje o zákazníkoch z vernostnej schémy</span><span class="sxs-lookup"><span data-stu-id="63bf6-136">Ingest customer data from loyalty schema</span></span>

1. <span data-ttu-id="63bf6-137">Vytvorte zdroj údajov s názvom **LoyaltyScheme**, vyberte možnosť importu a vyberte konektor **Text/CSV**.</span><span class="sxs-lookup"><span data-stu-id="63bf6-137">Create a data source named **LoyaltyScheme**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="63bf6-138">Zadajte adresu URL kontaktov pre eCommerce https://aka.ms/ciadclasscustomerloyalty.</span><span class="sxs-lookup"><span data-stu-id="63bf6-138">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscustomerloyalty.</span></span>

1. <span data-ttu-id="63bf6-139">Počas úpravy údajov vyberte **Transformovať** a potom **Použiť prvý riadok ako hlavičky**.</span><span class="sxs-lookup"><span data-stu-id="63bf6-139">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="63bf6-140">Aktualizujte typ údajov pre stĺpce uvedené nižšie:</span><span class="sxs-lookup"><span data-stu-id="63bf6-140">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="63bf6-141">**DateOfBirth**: Dátum</span><span class="sxs-lookup"><span data-stu-id="63bf6-141">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="63bf6-142">**RewardsPoints**: Celé číslo</span><span class="sxs-lookup"><span data-stu-id="63bf6-142">**RewardsPoints**: Whole Number</span></span>
   - <span data-ttu-id="63bf6-143">**CreatedOn**: Dátum/Čas</span><span class="sxs-lookup"><span data-stu-id="63bf6-143">**CreatedOn**: Date/Time</span></span>

1. <span data-ttu-id="63bf6-144">V poli **Názov** na pravej table premenujte svoj zdroj údajov z **Dotaz** na **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="63bf6-144">In the **Name** field on the right-hand pane, rename your data source from **Query** to **loyCustomers**.</span></span>

1. <span data-ttu-id="63bf6-145">**Uložte** zdroj údajov.</span><span class="sxs-lookup"><span data-stu-id="63bf6-145">**Save** the data source.</span></span>

### <a name="ingest-customer-data-from-website-reviews"></a><span data-ttu-id="63bf6-146">Príjem údajov o zákazníkoch z recenzií na webe</span><span class="sxs-lookup"><span data-stu-id="63bf6-146">Ingest customer data from website reviews</span></span>

1. <span data-ttu-id="63bf6-147">Vytvorte zdroj údajov s názvom **Website**, vyberte možnosť importu a vyberte konektor **Text/CSV**.</span><span class="sxs-lookup"><span data-stu-id="63bf6-147">Create a data source named **Website**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="63bf6-148">Zadajte adresu URL kontaktov pre eCommerce https://aka.ms/CI-ILT/WebReviews.</span><span class="sxs-lookup"><span data-stu-id="63bf6-148">Enter the URL for eCommerce contacts https://aka.ms/CI-ILT/WebReviews.</span></span>

1. <span data-ttu-id="63bf6-149">Počas úpravy údajov vyberte **Transformovať** a potom **Použiť prvý riadok ako hlavičky**.</span><span class="sxs-lookup"><span data-stu-id="63bf6-149">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="63bf6-150">Aktualizujte typ údajov pre stĺpce uvedené nižšie:</span><span class="sxs-lookup"><span data-stu-id="63bf6-150">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="63bf6-151">**ReviewRating**: Desatinné číslo</span><span class="sxs-lookup"><span data-stu-id="63bf6-151">**ReviewRating**: Decimal number</span></span>
   - <span data-ttu-id="63bf6-152">**ReviewDate**: Dátum</span><span class="sxs-lookup"><span data-stu-id="63bf6-152">**ReviewDate**: Date</span></span>

1. <span data-ttu-id="63bf6-153">V poli „Názov“ na pravej table premenujte svoj zdroj údajov z **Dotaz** na **Recenzie**.</span><span class="sxs-lookup"><span data-stu-id="63bf6-153">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **Reviews**.</span></span>

1. <span data-ttu-id="63bf6-154">**Uložte** zdroj údajov.</span><span class="sxs-lookup"><span data-stu-id="63bf6-154">**Save** the data source.</span></span>

## <a name="task-2---data-unification"></a><span data-ttu-id="63bf6-155">Úloha 2 – Zjednotenie údajov</span><span class="sxs-lookup"><span data-stu-id="63bf6-155">Task 2 - Data unification</span></span>

<span data-ttu-id="63bf6-156">Po prijatí údajov teraz začneme proces zjednocovania údajov, aby sme vytvorili jednotný profil zákazníka.</span><span class="sxs-lookup"><span data-stu-id="63bf6-156">After ingesting the data, we now begin the data unification process to create a unified customer profile.</span></span> <span data-ttu-id="63bf6-157">Ďalšie informácie nájdete v téme [Zjednotenie údajov](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="63bf6-157">For more information, see [Data unification](data-unification.md).</span></span>

### <a name="map"></a><span data-ttu-id="63bf6-158">Priradenie</span><span class="sxs-lookup"><span data-stu-id="63bf6-158">Map</span></span>

1. <span data-ttu-id="63bf6-159">Po prijatí údajov namapujte kontakty z údajov eCommerce a Loyalty na bežné typy údajov.</span><span class="sxs-lookup"><span data-stu-id="63bf6-159">After ingesting the data, map contacts from eCommerce and Loyalty data to common data types.</span></span> <span data-ttu-id="63bf6-160">Prejdite na **Údaje** > **Zjednotenie** > **Mapovanie**.</span><span class="sxs-lookup"><span data-stu-id="63bf6-160">Go to **Data** > **Unify** > **Map**.</span></span>

1. <span data-ttu-id="63bf6-161">Vyberte entity, ktoré zastupujú profil zákazníka – **eCommerceContacts** a **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="63bf6-161">Select the entities that represent the customer profile – **eCommerceContacts** and **loyCustomers**.</span></span> <span data-ttu-id="63bf6-162">Potom vyberte položku **Použiť**.</span><span class="sxs-lookup"><span data-stu-id="63bf6-162">Then, select **Apply**.</span></span>

   ![Zjednotenie zdrojov údajov elektronického obchodu a vernostných údajov.](media/unify-ecommerce-loyalty.png)

1. <span data-ttu-id="63bf6-164">Vyberte **ContactId** ako primárny kľúč pre **eCommerceContacts** a **LoyaltyID** ako primárny kľúč pre **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="63bf6-164">Select **ContactId** as the primary key for **eCommerceContacts** and **LoyaltyID** as the primary key for **loyCustomers**.</span></span>

   ![Zjednotenie LoyaltyId ako primárny kľúč.](media/unify-loyaltyid.png)

1. <span data-ttu-id="63bf6-166">Vyberte položku **Uložiť**.</span><span class="sxs-lookup"><span data-stu-id="63bf6-166">Select **Save**.</span></span>

### <a name="match"></a><span data-ttu-id="63bf6-167">Spárovanie</span><span class="sxs-lookup"><span data-stu-id="63bf6-167">Match</span></span>

1. <span data-ttu-id="63bf6-168">Prejdite na kartu **Spárovanie** a vyberte **Nastaviť poradie**.</span><span class="sxs-lookup"><span data-stu-id="63bf6-168">Go to the **Match** tab and select **Set Order**.</span></span>

1. <span data-ttu-id="63bf6-169">V **primárnom** rozbaľovacom zozname si vyberte možnosť **eCommerceContacts: eCommerce** ako primárny zdroj a zahrňte do nej všetky záznamy.</span><span class="sxs-lookup"><span data-stu-id="63bf6-169">In the **Primary** dropdown list, choose **eCommerceContacts : eCommerce** as the primary source and include all records.</span></span>

1. <span data-ttu-id="63bf6-170">V rozbaľovacom zozname **Entita 2** vyberte možnosť **loyCustomers: LoyaltyScheme** a zahrňte do nej všetky záznamy.</span><span class="sxs-lookup"><span data-stu-id="63bf6-170">In the **Entity 2** dropdown list, choose **loyCustomers : LoyaltyScheme** and include all records.</span></span>

   ![Zjednotenie zosúladenia eCommerce a Loyalty.](media/unify-match-order.png)

1. <span data-ttu-id="63bf6-172">Vyberte **Pridať pravidlo**</span><span class="sxs-lookup"><span data-stu-id="63bf6-172">Select **Add rule**</span></span>

1. <span data-ttu-id="63bf6-173">Pridajte svoju prvú podmienku pomocou FullName.</span><span class="sxs-lookup"><span data-stu-id="63bf6-173">Add your first condition using FullName.</span></span>

   - <span data-ttu-id="63bf6-174">V prípade eCommerceContacts vyberte z rozbaľovacieho zoznamu položku **FullName**.</span><span class="sxs-lookup"><span data-stu-id="63bf6-174">For eCommerceContacts select **FullName** in the dropdown.</span></span>
   - <span data-ttu-id="63bf6-175">V prípade loyCustomers vyberte z rozbaľovacieho zoznamu položku **FullName**.</span><span class="sxs-lookup"><span data-stu-id="63bf6-175">For loyCustomers select **FullName** in the dropdown.</span></span>
   - <span data-ttu-id="63bf6-176">Vyberte si položku **Normalizovať** z rozbaľovacieho zoznamu a vyberte možnosť **Typ (telefón, meno, adresa, ...)**.</span><span class="sxs-lookup"><span data-stu-id="63bf6-176">Select the **Normalize** dropdown and choose **Type (Phone, Name, Address, ...)**.</span></span>
   - <span data-ttu-id="63bf6-177">Nastavte **Úroveň presnosti**: **Základná** a **Hodnota**: **Vysoká**.</span><span class="sxs-lookup"><span data-stu-id="63bf6-177">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

1. <span data-ttu-id="63bf6-178">Zadajte meno **FullName, E-mail** pre nové pravidlo.</span><span class="sxs-lookup"><span data-stu-id="63bf6-178">Enter the name **FullName, Email** for the new rule.</span></span>

   - <span data-ttu-id="63bf6-179">Vyberte druhú podmienku pre e-mailovú adresu výberom možnosti **Pridať podmienku**</span><span class="sxs-lookup"><span data-stu-id="63bf6-179">Add a second condition for email address by selecting **Add Condition**</span></span>
   - <span data-ttu-id="63bf6-180">Pri entite eCommerceContacts vyberte z rozbaľovacieho zoznamu položku **EMail**.</span><span class="sxs-lookup"><span data-stu-id="63bf6-180">For entity eCommerceContacts, choose **EMail** in dropdown.</span></span>
   - <span data-ttu-id="63bf6-181">Pri entite loyCustomers vyberte z rozbaľovacieho zoznamu položku **EMail**.</span><span class="sxs-lookup"><span data-stu-id="63bf6-181">For entity loyCustomers, choose **EMail** in the dropdown.</span></span>
   - <span data-ttu-id="63bf6-182">Pole Normalizovať nechajte prázdne.</span><span class="sxs-lookup"><span data-stu-id="63bf6-182">Leave Normalize blank.</span></span>
   - <span data-ttu-id="63bf6-183">Nastavte **Úroveň presnosti**: **Základná** a **Hodnota**: **Vysoká**.</span><span class="sxs-lookup"><span data-stu-id="63bf6-183">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

   ![Pravidlo zjednotenia zhody pre meno a e-mail.](media/unify-match-rule.png)

1. <span data-ttu-id="63bf6-185">Vyberte položku **Hotovo**.</span><span class="sxs-lookup"><span data-stu-id="63bf6-185">Select **Done**.</span></span>

1. <span data-ttu-id="63bf6-186">Vyberte položku **Uložiť** a **Spustiť**.</span><span class="sxs-lookup"><span data-stu-id="63bf6-186">Select **Save** and **Run**.</span></span>

### <a name="merge"></a><span data-ttu-id="63bf6-187">Zlúčenie</span><span class="sxs-lookup"><span data-stu-id="63bf6-187">Merge</span></span>

1. <span data-ttu-id="63bf6-188">Prejdite na kartu **Zlúčiť**.</span><span class="sxs-lookup"><span data-stu-id="63bf6-188">Go to the **Merge** tab.</span></span>

1. <span data-ttu-id="63bf6-189">V entite **ContactId** pre **loyCustomers** zmeňte zobrazovaný názov na **ContactIdLOYALTY** na odlíšenie od ostatných prijatých ID.</span><span class="sxs-lookup"><span data-stu-id="63bf6-189">On the **ContactId** for **loyCustomers** entity, change the display name to **ContactIdLOYALTY** to differentiate it from the other IDs ingested.</span></span>

   ![premenovanie contactid z loyaltyid.](media/unify-merge-contactid.png)

1. <span data-ttu-id="63bf6-191">Vyberte **Uložiť** a **Spustiť procesy zlučovania a tie, ktoré prebiehajú zo servera ku klientovi**.</span><span class="sxs-lookup"><span data-stu-id="63bf6-191">Select **Save** and **Run merge and downstream processes**.</span></span>

## <a name="task-3---configure-customer-lifetime-value-prediction"></a><span data-ttu-id="63bf6-192">Úloha 3 – Konfigurácia predikcie hodnoty životnosti zákazníka</span><span class="sxs-lookup"><span data-stu-id="63bf6-192">Task 3 - Configure customer lifetime value prediction</span></span>

<span data-ttu-id="63bf6-193">Po zavedených zjednotených profiloch zákazníkov môžeme teraz spustiť predikciu hodnoty životnosti zákazníka.</span><span class="sxs-lookup"><span data-stu-id="63bf6-193">With the unified customer profiles in place, we can now run the customer lifetime value prediction.</span></span> <span data-ttu-id="63bf6-194">Podrobné kroky nájdete v časti [Predikcia hodnoty životnosti zákazníka (verzia Preview)](predict-customer-lifetime-value.md).</span><span class="sxs-lookup"><span data-stu-id="63bf6-194">For detailed steps, see [Customer Lifetime Value prediction (preview)](predict-customer-lifetime-value.md).</span></span>

1. <span data-ttu-id="63bf6-195">Prejdite na **Analýza**  > **Predikcie** a vyberte **Model hodnoty životnosti zákazníka**.</span><span class="sxs-lookup"><span data-stu-id="63bf6-195">Go to  **Intelligence**  > **Predictions**  and select the **Customer lifetime value model**.</span></span>

1. <span data-ttu-id="63bf6-196">Prejdite si informácie na bočnom paneli a vyberte **Začíname**.</span><span class="sxs-lookup"><span data-stu-id="63bf6-196">Go through the information in the side pane and select **Get started**.</span></span>

1. <span data-ttu-id="63bf6-197">Pomenujte model **Predikcia OOB eCommerce CLV** a výstupnú entitu **OOBeCommerceCLVPrediction**.</span><span class="sxs-lookup"><span data-stu-id="63bf6-197">Name the model **OOB eCommerce CLV Prediction** and the output entity  **OOBeCommerceCLVPrediction**.</span></span>

1. <span data-ttu-id="63bf6-198">Definujte predvoľby modelu pre model CLV:</span><span class="sxs-lookup"><span data-stu-id="63bf6-198">Define model preferences for the CLV model:</span></span>
   - <span data-ttu-id="63bf6-199">**Časové obdobie predikcie**: **12 mesiacov alebo 1 rok**.</span><span class="sxs-lookup"><span data-stu-id="63bf6-199">**Prediction time period**: **12 months or 1 year**.</span></span> <span data-ttu-id="63bf6-200">Toto nastavenie definuje, ako ďaleko do budúcnosti sa má predikovať hodnota životnosti zákazníka.</span><span class="sxs-lookup"><span data-stu-id="63bf6-200">This setting defines how far into the future to predict customer lifetime value.</span></span>
   - <span data-ttu-id="63bf6-201">**Aktívni zákazníci**: Zadajte, čo pre vašu firmu znamenajú aktívni zákazníci.</span><span class="sxs-lookup"><span data-stu-id="63bf6-201">**Active customers**: Specify what active customers mean for your business.</span></span> <span data-ttu-id="63bf6-202">Nastavte historický časový rámec, v ktorom zákazník musel mať minimálne jednu transakciu, aby mohol byť považovaný za aktívneho.</span><span class="sxs-lookup"><span data-stu-id="63bf6-202">Set the historical time frame in which a customer must have had at least one transaction to be considered active.</span></span> <span data-ttu-id="63bf6-203">Model bude predpovedať CLV iba pre aktívnych zákazníkov.</span><span class="sxs-lookup"><span data-stu-id="63bf6-203">The model will only predict CLV for active customers.</span></span> <span data-ttu-id="63bf6-204">Vyberte si medzi tým, či chcete nechať model vypočítať časové obdobie na základe historických údajov o transakciách, alebo poskytnúť konkrétny časový rámec.</span><span class="sxs-lookup"><span data-stu-id="63bf6-204">Choose between letting the model calculate the time period based on historical transaction data or provide a specific time frame.</span></span> <span data-ttu-id="63bf6-205">V tomto vzorovom sprievodcovi **necháme model vypočítať interval nákupu**, čo je predvolená možnosť.</span><span class="sxs-lookup"><span data-stu-id="63bf6-205">In this sample guide, we **let the model calculate purchase interval**, which is the default option.</span></span>
   - <span data-ttu-id="63bf6-206">**Zákazníci s vysokou hodnotou**: Definujte zákazníkov s vysokou hodnotou ako percentil najlepšie platiacich zákazníkov.</span><span class="sxs-lookup"><span data-stu-id="63bf6-206">**High value customers**: Define high value customers as a percentile of top-paying customers.</span></span> <span data-ttu-id="63bf6-207">Model používa tento vstup na poskytnutie výsledkov, ktoré zodpovedajú vašej obchodnej definícii zákazníkov s vysokou hodnotou.</span><span class="sxs-lookup"><span data-stu-id="63bf6-207">The model uses this input to provide results that fit your business definition of high value customers.</span></span> <span data-ttu-id="63bf6-208">Môžete sa rozhodnúť nechať model definovať zákazníkov s vysokou hodnotou.</span><span class="sxs-lookup"><span data-stu-id="63bf6-208">You can choose to let the model define high value customers.</span></span> <span data-ttu-id="63bf6-209">Používa heuristické pravidlo, ktoré odvodzuje percentil.</span><span class="sxs-lookup"><span data-stu-id="63bf6-209">It uses a heuristic rule that derives the percentile.</span></span> <span data-ttu-id="63bf6-210">Môžete tiež definovať zákazníkov s vysokou hodnotou ako percentil najlepšie platiacich budúcich zákazníkov.</span><span class="sxs-lookup"><span data-stu-id="63bf6-210">You can also define high value customers as a percentile of top future paying customers.</span></span> <span data-ttu-id="63bf6-211">V tomto vzorovom sprievodcovi manuálne definujeme zákazníkov s vysokou hodnotou ako **najlepších 30 % aktívne platiacich zákazníkov** a vyberieme **Ďalej**.</span><span class="sxs-lookup"><span data-stu-id="63bf6-211">In this sample guide, we manually define high value customers as **top 30% of active paying customers** and select **Next**.</span></span>

    :::image type="content" source="media/clv-model-preferences.png" alt-text="Krok predvolieb v prostredí so sprievodcom pre model CLV.":::

1. <span data-ttu-id="63bf6-213">V kroku **Požadované údaje** vyberte **Pridať údaje** na poskytnutie údajov o histórii transakcií.</span><span class="sxs-lookup"><span data-stu-id="63bf6-213">In the **Required Data** step, select **Add data** to provide the transaction history data.</span></span>

1. <span data-ttu-id="63bf6-214">Pridajte entitu **eCommercePurchases: eCommerce** a vykonajte mapovanie atribútov požadovaných modelom:</span><span class="sxs-lookup"><span data-stu-id="63bf6-214">Add the **eCommercePurchases : eCommerce** entity and map the attributes that are required by the model:</span></span>
   - <span data-ttu-id="63bf6-215">ID transakcie: eCommerce.eCommercePurchases.PurchaseId</span><span class="sxs-lookup"><span data-stu-id="63bf6-215">Transaction ID: eCommerce.eCommercePurchases.PurchaseId</span></span>
   - <span data-ttu-id="63bf6-216">Dátum transakcie: eCommerce.eCommercePurchases.PurchasedOn</span><span class="sxs-lookup"><span data-stu-id="63bf6-216">Transaction date: eCommerce.eCommercePurchases.PurchasedOn</span></span>
   - <span data-ttu-id="63bf6-217">Suma transakcie: eCommerce.eCommercePurchases.TotalPrice</span><span class="sxs-lookup"><span data-stu-id="63bf6-217">Transaction amount: eCommerce.eCommercePurchases.TotalPrice</span></span>
   - <span data-ttu-id="63bf6-218">ID produktu: eCommerce.eCommercePurchases.ProductId</span><span class="sxs-lookup"><span data-stu-id="63bf6-218">Product ID: eCommerce.eCommercePurchases.ProductId</span></span>

1. <span data-ttu-id="63bf6-219">Vyberte **Ďalej**.</span><span class="sxs-lookup"><span data-stu-id="63bf6-219">Select **Next**.</span></span>

1. <span data-ttu-id="63bf6-220">Nastavte vzťah medzi entitou **eCommercePurchases : eCommerce** a **eCommerceContacts : eCommerce**.</span><span class="sxs-lookup"><span data-stu-id="63bf6-220">Set up the relationship between the **eCommercePurchases : eCommerce** entity and  **eCommerceContacts : eCommerce**.</span></span>

1. <span data-ttu-id="63bf6-221">Krok **Dodatočné údaje (voliteľné)** umožňuje pridať viac údajov o aktivite zákazníka.</span><span class="sxs-lookup"><span data-stu-id="63bf6-221">The **Additional data (optional)** step allows you to add more customer activity data.</span></span> <span data-ttu-id="63bf6-222">Tieto údaje môžu pomôcť získať viac prehľadov o interakciách zákazníkov s vašou firmou, čo môže prispieť k CLV.</span><span class="sxs-lookup"><span data-stu-id="63bf6-222">This data can help to get more insights for customer interactions with your business, which can contribute to CLV.</span></span> <span data-ttu-id="63bf6-223">Pridaním kľúčových interakcií so zákazníkmi, ako sú webové denníky, denníky služieb pre zákazníkov alebo história programov odmien môžu zvýšiť presnosť predikcií.</span><span class="sxs-lookup"><span data-stu-id="63bf6-223">Adding key customer interactions like web logs, customer service logs, or rewards program history can improve the accuracy of predictions.</span></span> <span data-ttu-id="63bf6-224">Vyberte **Pridať údaje** na zahrnutie ďalších údajov o činnosti zákazníkov.</span><span class="sxs-lookup"><span data-stu-id="63bf6-224">Select **Add data** to include more customer activity data.</span></span>

1. <span data-ttu-id="63bf6-225">Pridajte entitu aktivity zákazníka a vykonajte mapovanie jej názvov polí na príslušné polia požadované modelom:</span><span class="sxs-lookup"><span data-stu-id="63bf6-225">Add the customer activity entity and map its fields names to the corresponding fields required by the model:</span></span>
   - <span data-ttu-id="63bf6-226">Entita aktivity zákazníka: Recenzie: Webová lokalita</span><span class="sxs-lookup"><span data-stu-id="63bf6-226">Customer activity entity: Reviews:Website</span></span>
   - <span data-ttu-id="63bf6-227">Primárny kľúč: Website.Reviews.ReviewId</span><span class="sxs-lookup"><span data-stu-id="63bf6-227">Primary key: Website.Reviews.ReviewId</span></span>
   - <span data-ttu-id="63bf6-228">Časová pečiatka: Website.Reviews.ReviewDate</span><span class="sxs-lookup"><span data-stu-id="63bf6-228">Timestamp: Website.Reviews.ReviewDate</span></span>
   - <span data-ttu-id="63bf6-229">Udalosť (názov aktivity): Website.Reviews.ActivityTypeDisplay</span><span class="sxs-lookup"><span data-stu-id="63bf6-229">Event (activity name): Website.Reviews.ActivityTypeDisplay</span></span>
   - <span data-ttu-id="63bf6-230">Podrobnosti (suma alebo hodnota): Website.Reviews.ReviewRating</span><span class="sxs-lookup"><span data-stu-id="63bf6-230">Details (amount or value): Website.Reviews.ReviewRating</span></span>

1. <span data-ttu-id="63bf6-231">Vyberte **Ďalej** a nakonfigurujte aktivitu a vzťah medzi údajmi o transakciách a údajmi o zákazníkoch:</span><span class="sxs-lookup"><span data-stu-id="63bf6-231">Select **Next** and configure the activity and the relationship between the transaction data and the customer data:</span></span>  
   - <span data-ttu-id="63bf6-232">Typ aktivity: Vybrať existujúcu</span><span class="sxs-lookup"><span data-stu-id="63bf6-232">Activity type: Choose existing</span></span>
   - <span data-ttu-id="63bf6-233">Označenie aktivity: Recenzia</span><span class="sxs-lookup"><span data-stu-id="63bf6-233">Activity label: Review</span></span>
   - <span data-ttu-id="63bf6-234">Zodpovedajúce označenie: Website.Reviews.UserId</span><span class="sxs-lookup"><span data-stu-id="63bf6-234">Corresponding label: Website.Reviews.UserId</span></span>
   - <span data-ttu-id="63bf6-235">Entita zákazníka: eCommerceKontakty:eCommerce</span><span class="sxs-lookup"><span data-stu-id="63bf6-235">Customer entity: eCommerceContacts:eCommerce</span></span>
   - <span data-ttu-id="63bf6-236">Vzťah: WebsiteReviews</span><span class="sxs-lookup"><span data-stu-id="63bf6-236">Relationship: WebsiteReviews</span></span>

1. <span data-ttu-id="63bf6-237">Vyberte **Ďalej** na nastavenie plánu modelu.</span><span class="sxs-lookup"><span data-stu-id="63bf6-237">Select **Next** to set the model schedule.</span></span>

   <span data-ttu-id="63bf6-238">Keď sú prijaté nové údaje, musí model pravidelne trénovať, aby sa naučil nové vzorce.</span><span class="sxs-lookup"><span data-stu-id="63bf6-238">The model needs to train regularly to learn new patterns when there's new data ingested.</span></span> <span data-ttu-id="63bf6-239">Pre tento príklad vyberte **Mesačne**.</span><span class="sxs-lookup"><span data-stu-id="63bf6-239">For this example, choose **Monthly**.</span></span>

1. <span data-ttu-id="63bf6-240">Po skontrolovaní všetkých podrobností vyberte možnosť **Uložiť a spustiť**.</span><span class="sxs-lookup"><span data-stu-id="63bf6-240">After reviewing all the details, select  **Save and Run**.</span></span>

## <a name="task-4---review-model-results-and-explanations"></a><span data-ttu-id="63bf6-241">Úloha 4 – Skontrolujte výsledky modelu a vysvetlenia</span><span class="sxs-lookup"><span data-stu-id="63bf6-241">Task 4 - Review model results and explanations</span></span>

<span data-ttu-id="63bf6-242">Nechajte model absolvovať školenie a skórovanie údajov.</span><span class="sxs-lookup"><span data-stu-id="63bf6-242">Let the model complete the training and scoring of the data.</span></span> <span data-ttu-id="63bf6-243">Ďalej si môžete pozrieť výsledky modelu CLV a vysvetlenia.</span><span class="sxs-lookup"><span data-stu-id="63bf6-243">Next, you can review the CLV model results and explanations.</span></span> <span data-ttu-id="63bf6-244">Viac informácií nájdete v článku [Kontrola stavu predikcie a výsledkov](predict-customer-lifetime-value.md#review-prediction-status-and-results).</span><span class="sxs-lookup"><span data-stu-id="63bf6-244">For more information, see [Review a prediction status and results](predict-customer-lifetime-value.md#review-prediction-status-and-results).</span></span>

## <a name="task-5---create-a-segment-of-high-value-customers"></a><span data-ttu-id="63bf6-245">Úloha 5 – Vytvorte segment zákazníkov s vysokou hodnotou</span><span class="sxs-lookup"><span data-stu-id="63bf6-245">Task 5 - Create a segment of high value customers</span></span>

<span data-ttu-id="63bf6-246">Spustením modelu sa vytvorí nová entita, ktorá je uvedená na zozname **Údaje** > **Entity**.</span><span class="sxs-lookup"><span data-stu-id="63bf6-246">Running the model creates a new entity, which is listed on **Data** > **Entities**.</span></span> <span data-ttu-id="63bf6-247">Nový segment zákazníkov môžete vytvoriť na základe entity vytvorenej modelom.</span><span class="sxs-lookup"><span data-stu-id="63bf6-247">You can create a new customer segment based on the entity created by the model.</span></span>

1. <span data-ttu-id="63bf6-248">Prejdite na **Segmenty**.</span><span class="sxs-lookup"><span data-stu-id="63bf6-248">Go to **Segments**.</span></span> 

1. <span data-ttu-id="63bf6-249">Vyberte **Nový** následne **Vytvoriť z** > **Analýza**.</span><span class="sxs-lookup"><span data-stu-id="63bf6-249">Select  **New** and choose **Create from** > **Intelligence**.</span></span>

   ![Vytvorenie segmentu s výstupom modelu.](media/segment-intelligence.png)

1. <span data-ttu-id="63bf6-251">Vyberte entitu **OOBeCommerceCLVPrediction** a definujte segment:</span><span class="sxs-lookup"><span data-stu-id="63bf6-251">Select the  **OOBeCommerceCLVPrediction** entity and define the segment:</span></span>
  - <span data-ttu-id="63bf6-252">Pole: CLVScore</span><span class="sxs-lookup"><span data-stu-id="63bf6-252">Field: CLVScore</span></span>
  - <span data-ttu-id="63bf6-253">Operátor: je väčšie ako</span><span class="sxs-lookup"><span data-stu-id="63bf6-253">Operator: greater than</span></span>
  - <span data-ttu-id="63bf6-254">Hodnota: 1500</span><span class="sxs-lookup"><span data-stu-id="63bf6-254">Value: 1500</span></span>

1. <span data-ttu-id="63bf6-255">Vyberte **Recenzia** a **Uložte** segment.</span><span class="sxs-lookup"><span data-stu-id="63bf6-255">Select **Review** and **Save** the segment.</span></span>

<span data-ttu-id="63bf6-256">Teraz máte segment, ktorý identifikuje zákazníkov, u ktorých sa predpokladá, že v nasledujúcich 12 mesiacoch vygenerujú viac ako 1500 $ výnosov.</span><span class="sxs-lookup"><span data-stu-id="63bf6-256">You now have a segment that identifies customers who are predicted to generate more than $1500 of revenue in the next 12 months.</span></span> <span data-ttu-id="63bf6-257">Ak sa prijme viac údajov, tento segment sa dynamicky aktualizuje.</span><span class="sxs-lookup"><span data-stu-id="63bf6-257">This segment gets updated dynamically if more data is ingested.</span></span>

<span data-ttu-id="63bf6-258">Ďalšie informácie nájdete v téme [Tvorba a správa segmentov](segments.md).</span><span class="sxs-lookup"><span data-stu-id="63bf6-258">For more information, see [Create and manage segments](segments.md).</span></span>
