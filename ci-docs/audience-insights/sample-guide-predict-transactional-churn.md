---
title: Predikcia odchodov založená na transakciách – vzorový sprievodca
description: V tomto vzorovom sprievodcovi môžete vyskúšať vopred pripravený model predikcie odchodov založený na transakciách.
ms.date: 11/19/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: diegogranados117
ms.author: digranad
manager: shellyha
ms.openlocfilehash: 251bc26246cee16952e8e4cb08e2ed7aa4d18488
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 03/15/2021
ms.locfileid: "5595445"
---
# <a name="transactional-churn-prediction-preview-sample-guide"></a><span data-ttu-id="f65fa-103">Predikcia odchodov založená na transakciách (ukážka) – vzorový sprievodca</span><span class="sxs-lookup"><span data-stu-id="f65fa-103">Transactional churn prediction (preview) sample guide</span></span>

<span data-ttu-id="f65fa-104">Táto príručka vám vysvetlí podrobný príklad predikcie odchodov založených na transakciách v nástroji Customer Insights pomocou nižšie uvedených údajov.</span><span class="sxs-lookup"><span data-stu-id="f65fa-104">This guide will walk you through an end to end example of Transactional Churn prediction in Customer Insights using the data provided below.</span></span> <span data-ttu-id="f65fa-105">Všetky údaje použité v tejto príručke nie sú skutočnými údajmi o zákazníkoch. Sú súčasťou súboru údajov Contoso, ktorý sa nachádza v *ukážkovom* prostredí v rámci vášho predplatného Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="f65fa-105">All data used in this guide is not real customer data and is part of the Contoso dataset found in the *Demo* environment within your Customer Insights Subscription.</span></span>

## <a name="scenario"></a><span data-ttu-id="f65fa-106">Scenár</span><span class="sxs-lookup"><span data-stu-id="f65fa-106">Scenario</span></span>

<span data-ttu-id="f65fa-107">Contoso je spoločnosť, ktorá vyrába vysokokvalitnú kávu a kávovary, ktoré predávajú prostredníctvom svojich webových stránok Contoso Coffee.</span><span class="sxs-lookup"><span data-stu-id="f65fa-107">Contoso is a company that produces high-quality coffee and coffee machines, which they sell through their Contoso Coffee website.</span></span> <span data-ttu-id="f65fa-108">Ich cieľom je zistiť, ktorí zákazníci, ktorí si zvyčajne nakupujú svoje produkty pravidelne, prestanú byť aktívnymi zákazníkmi v nasledujúcich 60 dňoch.</span><span class="sxs-lookup"><span data-stu-id="f65fa-108">Their goal is to know which customers who typically purchase their products on a regular basis, will stop being active customers in the next 60 days.</span></span> <span data-ttu-id="f65fa-109">Poznatok, ktorý z ich zákazníkov **pravdepodobne odíde**, im môže im pomôcť ušetriť marketingové úsilie zameraním na ich udržanie.</span><span class="sxs-lookup"><span data-stu-id="f65fa-109">Knowing which of their customers is **likely to churn**, can help them save marketing efforts by focusing on keeping them.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="f65fa-110">Predpoklady</span><span class="sxs-lookup"><span data-stu-id="f65fa-110">Prerequisites</span></span>

- <span data-ttu-id="f65fa-111">Minimálne [povolenia prispievateľa](permissions.md) v Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="f65fa-111">At least [Contributor permissions](permissions.md) in Customer Insights.</span></span>
- <span data-ttu-id="f65fa-112">Odporúčame vám vykonať nasledujúce kroky [v novom prostredí](manage-environments.md).</span><span class="sxs-lookup"><span data-stu-id="f65fa-112">We recommend that you implement the following steps [in a new environment](manage-environments.md).</span></span>

## <a name="task-1---ingest-data"></a><span data-ttu-id="f65fa-113">Úloha 1 – Príjem údajov</span><span class="sxs-lookup"><span data-stu-id="f65fa-113">Task 1 - Ingest data</span></span>

<span data-ttu-id="f65fa-114">Prečítajte si články [o príjme údajov](data-sources.md) a konkrétne o [importe zdrojov údajov pomocou konektorov Power Query](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="f65fa-114">Review the articles [about data ingestion](data-sources.md) and [importing data sources using Power Query connectors](connect-power-query.md) specifically.</span></span> <span data-ttu-id="f65fa-115">Nasledujúce informácie predpokladajú, že ste sa oboznámili s prijímaním údajov vo všeobecnosti.</span><span class="sxs-lookup"><span data-stu-id="f65fa-115">The following information assumes you familiarized with ingesting data in general.</span></span> 

### <a name="ingest-customer-data-from-ecommerce-platform"></a><span data-ttu-id="f65fa-116">Príjem údajov o zákazníkoch z platformy eCommerce</span><span class="sxs-lookup"><span data-stu-id="f65fa-116">Ingest customer data from eCommerce platform</span></span>

1. <span data-ttu-id="f65fa-117">Vytvorte zdroj údajov s názvom **eCommerce**, vyberte možnosť importu a vyberte konektor **Text/CSV**.</span><span class="sxs-lookup"><span data-stu-id="f65fa-117">Create a data source named **eCommerce**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="f65fa-118">Zadajte adresu URL kontaktov pre eCommerce https://aka.ms/ciadclasscontacts.</span><span class="sxs-lookup"><span data-stu-id="f65fa-118">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscontacts.</span></span>

1. <span data-ttu-id="f65fa-119">Počas úpravy údajov vyberte **Transformovať** a potom **Použiť prvý riadok ako hlavičky**.</span><span class="sxs-lookup"><span data-stu-id="f65fa-119">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="f65fa-120">Aktualizujte typ údajov pre stĺpce uvedené nižšie:</span><span class="sxs-lookup"><span data-stu-id="f65fa-120">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="f65fa-121">**DateOfBirth**: Dátum</span><span class="sxs-lookup"><span data-stu-id="f65fa-121">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="f65fa-122">**CreatedOn**: Dátum/Čas/Pásmo</span><span class="sxs-lookup"><span data-stu-id="f65fa-122">**CreatedOn**: Date/Time/Zone</span></span>

   [!div class="mx-imgBorder"]
   <span data-ttu-id="f65fa-123">![Transformovať dátum narodenia na dátum](media/ecommerce-dob-date.PNG "transformovať dátum narodenia na dátum")</span><span class="sxs-lookup"><span data-stu-id="f65fa-123">![Transform DoB to Date](media/ecommerce-dob-date.PNG "transform date of birth to date")</span></span>

1. <span data-ttu-id="f65fa-124">V poli **Názov** na pravej table premenujte svoj zdroj údajov z **Dotaz** na **eCommerceContacts**</span><span class="sxs-lookup"><span data-stu-id="f65fa-124">In the **Name** field on the right-hand pane, rename your data source from **Query** to **eCommerceContacts**</span></span>

1. <span data-ttu-id="f65fa-125">Uložte zdroj údajov.</span><span class="sxs-lookup"><span data-stu-id="f65fa-125">Save the data source.</span></span>

### <a name="ingest-online-purchase-data"></a><span data-ttu-id="f65fa-126">Prijmite údaje o online nákupe</span><span class="sxs-lookup"><span data-stu-id="f65fa-126">Ingest online purchase data</span></span>

1. <span data-ttu-id="f65fa-127">K tomu istému zdroju údajov **eCommerce** pridajte ďalšiu množinu údajov.</span><span class="sxs-lookup"><span data-stu-id="f65fa-127">Add another data set to the same **eCommerce** data source.</span></span> <span data-ttu-id="f65fa-128">Znova vyberte konektor **Text/CSV**.</span><span class="sxs-lookup"><span data-stu-id="f65fa-128">Choose the **Text/CSV** connector again.</span></span>

1. <span data-ttu-id="f65fa-129">Zadajte adresu URL pre údaje **Online nákupy** https://aka.ms/ciadclassonline.</span><span class="sxs-lookup"><span data-stu-id="f65fa-129">Enter the URL for **Online Purchases** data https://aka.ms/ciadclassonline.</span></span>

1. <span data-ttu-id="f65fa-130">Počas úpravy údajov vyberte **Transformovať** a potom **Použiť prvý riadok ako hlavičky**.</span><span class="sxs-lookup"><span data-stu-id="f65fa-130">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="f65fa-131">Aktualizujte typ údajov pre stĺpce uvedené nižšie:</span><span class="sxs-lookup"><span data-stu-id="f65fa-131">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="f65fa-132">**PurchasedOn**: Dátum/Čas</span><span class="sxs-lookup"><span data-stu-id="f65fa-132">**PurchasedOn**: Date/Time</span></span>
   - <span data-ttu-id="f65fa-133">**TotalPrice**: Mena</span><span class="sxs-lookup"><span data-stu-id="f65fa-133">**TotalPrice**: Currency</span></span>
   
1. <span data-ttu-id="f65fa-134">V poli **Názov** na pravej table premenujte svoj zdroj údajov z **Dotaz** na **eCommercePurchases**.</span><span class="sxs-lookup"><span data-stu-id="f65fa-134">In the **Name** field on the right-hand pane, rename your data source from **Query** to **eCommercePurchases**.</span></span>

1. <span data-ttu-id="f65fa-135">Uložte zdroj údajov.</span><span class="sxs-lookup"><span data-stu-id="f65fa-135">Save the data source.</span></span>

### <a name="ingest-customer-data-from-loyalty-schema"></a><span data-ttu-id="f65fa-136">Príjem údaje o zákazníkoch z vernostnej schémy</span><span class="sxs-lookup"><span data-stu-id="f65fa-136">Ingest customer data from loyalty schema</span></span>

1. <span data-ttu-id="f65fa-137">Vytvorte zdroj údajov s názvom **LoyaltyScheme**, vyberte možnosť importu a vyberte konektor **Text/CSV**.</span><span class="sxs-lookup"><span data-stu-id="f65fa-137">Create a data source named **LoyaltyScheme**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="f65fa-138">Zadajte adresu URL kontaktov pre eCommerce https://aka.ms/ciadclasscustomerloyalty.</span><span class="sxs-lookup"><span data-stu-id="f65fa-138">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscustomerloyalty.</span></span>

1. <span data-ttu-id="f65fa-139">Počas úpravy údajov vyberte **Transformovať** a potom **Použiť prvý riadok ako hlavičky**.</span><span class="sxs-lookup"><span data-stu-id="f65fa-139">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="f65fa-140">Aktualizujte typ údajov pre stĺpce uvedené nižšie:</span><span class="sxs-lookup"><span data-stu-id="f65fa-140">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="f65fa-141">**DateOfBirth**: Dátum</span><span class="sxs-lookup"><span data-stu-id="f65fa-141">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="f65fa-142">**RewardsPoints**: Celé číslo</span><span class="sxs-lookup"><span data-stu-id="f65fa-142">**RewardsPoints**: Whole Number</span></span>
   - <span data-ttu-id="f65fa-143">**CreatedOn**: Dátum/Čas</span><span class="sxs-lookup"><span data-stu-id="f65fa-143">**CreatedOn**: Date/Time</span></span>

1. <span data-ttu-id="f65fa-144">V poli **Názov** na pravej table premenujte svoj zdroj údajov z **Dotaz** na **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="f65fa-144">In the **Name** field on the right-hand pane, rename your data source from **Query** to **loyCustomers**.</span></span>

1. <span data-ttu-id="f65fa-145">Uložte zdroj údajov.</span><span class="sxs-lookup"><span data-stu-id="f65fa-145">Save the data source.</span></span>


## <a name="task-2---data-unification"></a><span data-ttu-id="f65fa-146">Úloha 2 – Zjednotenie údajov</span><span class="sxs-lookup"><span data-stu-id="f65fa-146">Task 2 - Data unification</span></span>

<span data-ttu-id="f65fa-147">Po prijatí údajov teraz začíname proces **Mapovanie, párovanie, zlúčenie** na vytvorenie zjednoteného profilu zákazníka.</span><span class="sxs-lookup"><span data-stu-id="f65fa-147">After ingesting the data we now begin the **Map, Match, Merge** process to create a unified customer profile.</span></span> <span data-ttu-id="f65fa-148">Ďalšie informácie nájdete v téme [Zjednotenie údajov](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="f65fa-148">For more information, see [Data unification](data-unification.md).</span></span>

### <a name="map"></a><span data-ttu-id="f65fa-149">Priradenie</span><span class="sxs-lookup"><span data-stu-id="f65fa-149">Map</span></span>

1. <span data-ttu-id="f65fa-150">Po prijatí údajov namapujte kontakty z údajov eCommerce a Loyalty na bežné typy údajov.</span><span class="sxs-lookup"><span data-stu-id="f65fa-150">After ingesting the data, map contacts from eCommerce and Loyalty data to common data types.</span></span> <span data-ttu-id="f65fa-151">Prejdite na **Údaje** > **Zjednotenie** > **Mapovanie**.</span><span class="sxs-lookup"><span data-stu-id="f65fa-151">Go to **Data** > **Unify** > **Map**.</span></span>

1. <span data-ttu-id="f65fa-152">Vyberte entity, ktoré zastupujú profil zákazníka – **eCommerceContacts** a **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="f65fa-152">Select the entities that represent the customer profile – **eCommerceContacts** and **loyCustomers**.</span></span> 

   :::image type="content" source="media/unify-ecommerce-loyalty.PNG" alt-text="Zjednotenie zdrojov údajov elektronického obchodu a vernostných údajov.":::

1. <span data-ttu-id="f65fa-154">Vyberte **ContactId** ako primárny kľúč pre **eCommerceContacts** a **LoyaltyID** ako primárny kľúč pre **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="f65fa-154">Select **ContactId** as the primary key for **eCommerceContacts** and **LoyaltyID** as the primary key for **loyCustomers**.</span></span>

   :::image type="content" source="media/unify-loyaltyid.PNG" alt-text="Zjednotenie LoyaltyId ako primárny kľúč.":::

### <a name="match"></a><span data-ttu-id="f65fa-156">Spárovanie</span><span class="sxs-lookup"><span data-stu-id="f65fa-156">Match</span></span>

1. <span data-ttu-id="f65fa-157">Prejdite na kartu **Spárovanie** a vyberte **Nastaviť poradie**.</span><span class="sxs-lookup"><span data-stu-id="f65fa-157">Go to the **Match** tab and select **Set Order**.</span></span>

1. <span data-ttu-id="f65fa-158">V rozbaľovacom zozname **Primárny** vyberte **eCommerceContacts: eCommerce** ako primárny zdroj a zahrňte všetky záznamy.</span><span class="sxs-lookup"><span data-stu-id="f65fa-158">In the **Primary** drop-down list, choose **eCommerceContacts : eCommerce** as the primary source and include all records.</span></span>

1. <span data-ttu-id="f65fa-159">V rozbaľovacom zozname **Entita 2** vyberte **loyCustomers: LoyaltyScheme** a zahrňte všetky záznamy.</span><span class="sxs-lookup"><span data-stu-id="f65fa-159">In the **Entity 2** drop-down list, choose **loyCustomers : LoyaltyScheme** and include all records.</span></span>

   :::image type="content" source="media/unify-match-order.PNG" alt-text="Zjednotenie zosúladenia eCommerce a Loyalty.":::

1. <span data-ttu-id="f65fa-161">Vyberte **Vytvoriť nové pravidlo**</span><span class="sxs-lookup"><span data-stu-id="f65fa-161">Select **Create a new rule**</span></span>

1. <span data-ttu-id="f65fa-162">Pridajte svoju prvú podmienku pomocou FullName.</span><span class="sxs-lookup"><span data-stu-id="f65fa-162">Add your first condition using FullName.</span></span>

   * <span data-ttu-id="f65fa-163">Pre eCommerceContacts vyberte v rozbaľovacej ponuke **FullName**.</span><span class="sxs-lookup"><span data-stu-id="f65fa-163">For eCommerceContacts select **FullName** in the drop-down.</span></span>
   * <span data-ttu-id="f65fa-164">Pre loyCustomers vyberte v rozbaľovacej ponuke **FullName**.</span><span class="sxs-lookup"><span data-stu-id="f65fa-164">For loyCustomers select **FullName** in the drop-down.</span></span>
   * <span data-ttu-id="f65fa-165">Vyberte rozbaľovací zoznam **Normalizovať** a vyberte **Typ (Telefón, Meno, Adresa, ...)**.</span><span class="sxs-lookup"><span data-stu-id="f65fa-165">Select the **Normalize** drop down and choose **Type (Phone, Name, Address, ...)**.</span></span>
   * <span data-ttu-id="f65fa-166">Nastavte **Úroveň presnosti**: **Základná** a **Hodnota**: **Vysoká**.</span><span class="sxs-lookup"><span data-stu-id="f65fa-166">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

1. <span data-ttu-id="f65fa-167">Zadajte meno **FullName, E-mail** pre nové pravidlo.</span><span class="sxs-lookup"><span data-stu-id="f65fa-167">Enter the name **FullName, Email** for the new rule.</span></span>

   * <span data-ttu-id="f65fa-168">Vyberte druhú podmienku pre e-mailovú adresu výberom možnosti **Pridať podmienku**</span><span class="sxs-lookup"><span data-stu-id="f65fa-168">Add a second condition for email address by selecting **Add Condition**</span></span>
   * <span data-ttu-id="f65fa-169">Pre entitu eCommerceContacts vyberte v rozbaľovacej ponuke **E-mail**.</span><span class="sxs-lookup"><span data-stu-id="f65fa-169">For entity eCommerceContacts, choose **EMail** in drop-down.</span></span>
   * <span data-ttu-id="f65fa-170">Pre entitu loyCustomers vyberte v rozbaľovacej ponuke **E-mail**.</span><span class="sxs-lookup"><span data-stu-id="f65fa-170">For entity loyCustomers, choose **EMail** in the drop-down.</span></span> 
   * <span data-ttu-id="f65fa-171">Pole Normalizovať nechajte prázdne.</span><span class="sxs-lookup"><span data-stu-id="f65fa-171">Leave Normalize blank.</span></span> 
   * <span data-ttu-id="f65fa-172">Nastavte **Úroveň presnosti**: **Základná** a **Hodnota**: **Vysoká**.</span><span class="sxs-lookup"><span data-stu-id="f65fa-172">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

   :::image type="content" source="media/unify-match-rule.PNG" alt-text="Pravidlo zjednotenia zhody pre meno a e-mail.":::

7. <span data-ttu-id="f65fa-174">Vyberte položku **Uložiť** a **Spustiť**.</span><span class="sxs-lookup"><span data-stu-id="f65fa-174">Select **Save** and **Run**.</span></span>

### <a name="merge"></a><span data-ttu-id="f65fa-175">Zlúčenie</span><span class="sxs-lookup"><span data-stu-id="f65fa-175">Merge</span></span>

1. <span data-ttu-id="f65fa-176">Prejdite na kartu **Zlúčiť**.</span><span class="sxs-lookup"><span data-stu-id="f65fa-176">Go to the **Merge** tab.</span></span>

1. <span data-ttu-id="f65fa-177">V entite **ContactId** pre **loyCustomers** zmeňte zobrazovaný názov na **ContactIdLOYALTY** na odlíšenie od ostatných prijatých ID.</span><span class="sxs-lookup"><span data-stu-id="f65fa-177">On the **ContactId** for **loyCustomers** entity, change the display name to **ContactIdLOYALTY** to differentiate it from the other IDs ingested.</span></span>

   :::image type="content" source="media/unify-merge-contactid.PNG" alt-text="premenovanie contactid z loyaltyid.":::

1. <span data-ttu-id="f65fa-179">Vyberte **Uložiť** a **Spustiť** na začatie procesu zlúčenia.</span><span class="sxs-lookup"><span data-stu-id="f65fa-179">Select **Save** and **Run** to start the Merge Process.</span></span>



## <a name="task-3---configure-transaction-churn-prediction"></a><span data-ttu-id="f65fa-180">Úloha 3 - Konfigurácia predikcie odchodov založených na transakciách</span><span class="sxs-lookup"><span data-stu-id="f65fa-180">Task 3 - Configure transaction churn prediction</span></span>

<span data-ttu-id="f65fa-181">Po zavedení zjednotených profilov zákazníkov môžeme teraz spustiť predikciu odchodu predplatiteľov.</span><span class="sxs-lookup"><span data-stu-id="f65fa-181">With the unified customer profiles in place, we can now run the subscription churn prediction.</span></span> <span data-ttu-id="f65fa-182">Podrobné kroky nájdete v článku [Predikcia odchodu predplatiteľov (ukážka)](predict-subscription-churn.md).</span><span class="sxs-lookup"><span data-stu-id="f65fa-182">For detailed steps, see the [Subscription churn prediction (preview)](predict-subscription-churn.md) article.</span></span> 

1. <span data-ttu-id="f65fa-183">Prejdite na **Analýza** > **Objavovať** a vyberte použitie **Model odchodu zákazníkov**.</span><span class="sxs-lookup"><span data-stu-id="f65fa-183">Go to **Intelligence** > **Discover** and select to use the **Customer churn model**.</span></span>

1. <span data-ttu-id="f65fa-184">Vyberte možnosť **Transakčné** a vyberte **Začíname**.</span><span class="sxs-lookup"><span data-stu-id="f65fa-184">Select the **Transactional** option and select **Get started**.</span></span>

1. <span data-ttu-id="f65fa-185">Pomenujte model **Predikcia odchodov založených na transakciách OOB** a výstupnú entitu **OOBeCommerceChurnPrediction**.</span><span class="sxs-lookup"><span data-stu-id="f65fa-185">Name the model **OOB eCommerce Transaction Churn Prediction** and the output entity **OOBeCommerceChurnPrediction**.</span></span>

1. <span data-ttu-id="f65fa-186">Definujte dve podmienky pre model odchodu:</span><span class="sxs-lookup"><span data-stu-id="f65fa-186">Define two conditions for the churn model:</span></span>

   * <span data-ttu-id="f65fa-187">**Okno predikcie**: **najmenej 60** dní.</span><span class="sxs-lookup"><span data-stu-id="f65fa-187">**Prediction window**: **at least 60** days.</span></span> <span data-ttu-id="f65fa-188">Toto nastavenie definuje, ako ďaleko do budúcnosti chceme predpovedať odchod zákazníkov.</span><span class="sxs-lookup"><span data-stu-id="f65fa-188">This setting defines how far into the future do we want to predict customer churn.</span></span>

   * <span data-ttu-id="f65fa-189">**Definícia odchodu**: **najmenej 60** dní.</span><span class="sxs-lookup"><span data-stu-id="f65fa-189">**Churn definition**: **at least 60** days.</span></span> <span data-ttu-id="f65fa-190">Doba bez nákupu, po ktorej sa zákazník považuje za odídeného.</span><span class="sxs-lookup"><span data-stu-id="f65fa-190">The duration without purchase after which a customer is considered churned.</span></span>

     :::image type="content" source="media/model-levers.PNG" alt-text="Vyberte úrovne modelov Okno predikcie a Definícia odchodu.":::

1. <span data-ttu-id="f65fa-192">Vyberte **História nákupov (povinné)** a **Pridať údaje** pre históriu nákupov.</span><span class="sxs-lookup"><span data-stu-id="f65fa-192">Select **Purchase History (required)** and select **Add data** for purchase history.</span></span>

1. <span data-ttu-id="f65fa-193">Pridajte entitu **eCommercePurchases: eCommerce** a mapujte polia z eCommerce na zodpovedajúce polia požadované modelom.</span><span class="sxs-lookup"><span data-stu-id="f65fa-193">Add the **eCommercePurchases : eCommerce** entity and map the fields from eCommerce to the corresponding fields required by the model.</span></span>

1. <span data-ttu-id="f65fa-194">Spojte entitu **eCommercePurchases: eCommerce** s **eCommerceContacts: eCommerce**.</span><span class="sxs-lookup"><span data-stu-id="f65fa-194">Join the **eCommercePurchases : eCommerce** entity with **eCommerceContacts : eCommerce**.</span></span>

   :::image type="content" source="media/model-purchase-join.PNG" alt-text="Spojenie entít eCommerce.":::

1. <span data-ttu-id="f65fa-196">Vyberte **Ďalej** na nastavenie plánu modelu.</span><span class="sxs-lookup"><span data-stu-id="f65fa-196">Select **Next** to set the model schedule.</span></span>

   <span data-ttu-id="f65fa-197">Model sa musí pravidelne trénovať, aby sa naučil nové vzorce, keď dôjde k prijatiu nových údajov.</span><span class="sxs-lookup"><span data-stu-id="f65fa-197">The model needs to train regularly to learn new patterns when there is new data ingested.</span></span> <span data-ttu-id="f65fa-198">Pre tento príklad vyberte **Mesačne**.</span><span class="sxs-lookup"><span data-stu-id="f65fa-198">For this example, select **Monthly**.</span></span>

1. <span data-ttu-id="f65fa-199">Po skontrolovaní všetkých podrobností vyberte možnosť **Uložiť a spustiť**.</span><span class="sxs-lookup"><span data-stu-id="f65fa-199">After reviewing all the details, select **Save and Run**.</span></span>

## <a name="task-4---review-model-results-and-explanations"></a><span data-ttu-id="f65fa-200">Úloha 4 – Skontrolujte výsledky modelu a vysvetlenia</span><span class="sxs-lookup"><span data-stu-id="f65fa-200">Task 4 - Review model results and explanations</span></span>

<span data-ttu-id="f65fa-201">Nechajte model absolvovať školenie a skórovanie údajov.</span><span class="sxs-lookup"><span data-stu-id="f65fa-201">Let the model complete the training and scoring of the data.</span></span> <span data-ttu-id="f65fa-202">Teraz si môžete vysvetlenie modelu odchodu predplatiteľov.</span><span class="sxs-lookup"><span data-stu-id="f65fa-202">You can now review the subscription churn model explanations.</span></span> <span data-ttu-id="f65fa-203">Viac informácií nájdete v článku [Kontrola stavu predikcie a výsledkov](predict-subscription-churn.md#review-a-prediction-status-and-results).</span><span class="sxs-lookup"><span data-stu-id="f65fa-203">For more information, see [Review a prediction status and results](predict-subscription-churn.md#review-a-prediction-status-and-results).</span></span>

## <a name="task-5---create-a-segment-of-high-churn-risk-customers"></a><span data-ttu-id="f65fa-204">Úloha 5 – Vytvorenie segmentu zákazníkov s vysokým rizikom odchodu</span><span class="sxs-lookup"><span data-stu-id="f65fa-204">Task 5 - Create a segment of high churn-risk customers</span></span>

<span data-ttu-id="f65fa-205">Spustením produkčného modelu sa vytvorí nová entita, ktorú môžete vidieť v ponuke **Údaje** > **Entity**.</span><span class="sxs-lookup"><span data-stu-id="f65fa-205">Running the production model creates a new entity that you can see in **Data** > **Entities**.</span></span>   

<span data-ttu-id="f65fa-206">Nový segment môžete vytvoriť na základe entity vytvorenej modelom.</span><span class="sxs-lookup"><span data-stu-id="f65fa-206">You can create a new segment based on the entity created by the model.</span></span>

1.  <span data-ttu-id="f65fa-207">Prejdite na **Segmenty**.</span><span class="sxs-lookup"><span data-stu-id="f65fa-207">Go to **Segments**.</span></span> <span data-ttu-id="f65fa-208">Vyberte **Nový** následne **Vytvoriť z** > **Analýza**.</span><span class="sxs-lookup"><span data-stu-id="f65fa-208">Select **New** and choose **Create from** > **Intelligence**.</span></span> 

   :::image type="content" source="media/segment-intelligence.PNG" alt-text="Vytvorenie segmentu s výstupom modelu.":::

1. <span data-ttu-id="f65fa-210">Vyberte koncový bod **OOBSubscriptionChurnPrediction** a definujte segment:</span><span class="sxs-lookup"><span data-stu-id="f65fa-210">Select the **OOBSubscriptionChurnPrediction** endpoint and define the segment:</span></span> 
   - <span data-ttu-id="f65fa-211">Pole: ChurnScore</span><span class="sxs-lookup"><span data-stu-id="f65fa-211">Field: ChurnScore</span></span>
   - <span data-ttu-id="f65fa-212">Operátor: je väčšie ako</span><span class="sxs-lookup"><span data-stu-id="f65fa-212">Operator: greater than</span></span>
   - <span data-ttu-id="f65fa-213">Hodnota: 0,6</span><span class="sxs-lookup"><span data-stu-id="f65fa-213">Value: 0.6</span></span>
   
   :::image type="content" source="media/segment-setup-subs.PNG" alt-text="Nastavenie segmentu odchodu predplatiteľov.":::

<span data-ttu-id="f65fa-215">Teraz máte segment, ktorý sa dynamicky aktualizuje a ktorý identifikuje vysoko rizikových zákazníkov pre toto predplatné.</span><span class="sxs-lookup"><span data-stu-id="f65fa-215">You now have a segment that is dynamically updated which identifies high churn-risk customers for this subscription business.</span></span>

<span data-ttu-id="f65fa-216">Ďalšie informácie nájdete v téme [Tvorba a správa segmentov](segments.md).</span><span class="sxs-lookup"><span data-stu-id="f65fa-216">For more information, see [Create and manage segments](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]