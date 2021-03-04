---
title: Predikcia odporúčania produktov
description: Predikujte produkty, ktoré si zákazník pravdepodobne kúpi alebo ktoré bude chcieť použiť.
ms.date: 02/15/2021
ms.reviewer: zacook
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 5a2eb2b4697e51a0abb933b654a9b0b150dfa6a3
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 02/15/2021
ms.locfileid: "5270533"
---
# <a name="product-recommendation-prediction-preview"></a><span data-ttu-id="0b3ac-103">Predikcia odporúčania produktov (verzia Preview)</span><span class="sxs-lookup"><span data-stu-id="0b3ac-103">Product recommendation prediction (preview)</span></span>

<span data-ttu-id="0b3ac-104">Model odporúčaní produktov vytvára súbory prediktívnych odporúčaní produktov.</span><span class="sxs-lookup"><span data-stu-id="0b3ac-104">The product recommendation model creates sets of predictive product recommendations.</span></span> <span data-ttu-id="0b3ac-105">Odporúčania vychádzajú z predchádzajúceho nákupného správania a zákazníkov s podobnými vzormi nákupov.</span><span class="sxs-lookup"><span data-stu-id="0b3ac-105">Recommendations are based on previous purchase behavior and customers with similar purchase patterns.</span></span> <span data-ttu-id="0b3ac-106">Na stránke **Analýza** > **Predikcie** môžete vytvoriť nové predikcie odporúčaní produktov.</span><span class="sxs-lookup"><span data-stu-id="0b3ac-106">You can create new product recommendation predictions on the **Intelligence** > **Predictions** page.</span></span> <span data-ttu-id="0b3ac-107">Vyberte **Moje predikcie**, aby ste videli ďalšie predikcie, ktoré ste vytvorili.</span><span class="sxs-lookup"><span data-stu-id="0b3ac-107">Select **My predictions** to see other predictions that you've created.</span></span>

<span data-ttu-id="0b3ac-108">Na odporúčania produktov sa môžu vzťahovať miestne zákony a nariadenia, ako aj očakávania zákazníkov, ktoré model nemusí vedieť zohľadniť.</span><span class="sxs-lookup"><span data-stu-id="0b3ac-108">Product recommendations may be subject to local laws and regulations as well as customer expectations, which the model is not built to specifically take into account.</span></span>  <span data-ttu-id="0b3ac-109">Ako používateľ tejto prediktívnej funkcie **musíte skontrolovať odporúčania ešte predtým, ako ich doručíte zákazníkom**, aby ste sa ubezpečili, že dodržiavate všetky príslušné zákony alebo nariadenia, ako aj očakávania zákazníkov týkajúce sa toho, čo môžete odporučiť.</span><span class="sxs-lookup"><span data-stu-id="0b3ac-109">As a user of this predictive capability, **you must review the recommendations prior to delivering them to your customers** to ensure you are complying with any applicable laws or regulations, as well as customer expectations for what you may recommend.</span></span> 

<span data-ttu-id="0b3ac-110">Výstup tohto modelu vám navyše poskytne odporúčania založené na ID produktu.</span><span class="sxs-lookup"><span data-stu-id="0b3ac-110">Additionally, the output of this model will give you recommendations based on the product ID.</span></span> <span data-ttu-id="0b3ac-111">Váš mechanizmus doručovania bude musieť zobať predikované ID produktov a mapovať ich na vhodný obsah pre vašich zákazníkov, aby zohľadnil lokalizáciu, obsah obrázkov a ďalší obsah alebo správanie špecifické pre podnikanie.</span><span class="sxs-lookup"><span data-stu-id="0b3ac-111">Your delivery mechanism will need to take predicted product IDs and map them to appropriate content for your customers to account for localization, image content, and other business specific content or behavior.</span></span>

## <a name="sample-guide"></a><span data-ttu-id="0b3ac-112">Ukážkový sprievodca</span><span class="sxs-lookup"><span data-stu-id="0b3ac-112">Sample Guide</span></span>

<span data-ttu-id="0b3ac-113">Ak máte záujem vyskúšať túto funkciu, ale nemáte údaje na splnenie požiadaviek uvedených nižšie, môžete [vytvoriť ukážkovú implementáciu](sample-guide-predict-product-recommendation.md).</span><span class="sxs-lookup"><span data-stu-id="0b3ac-113">If you're interested in trying this feature but don't have data to complete the requirements below, you can [create a sample implementation](sample-guide-predict-product-recommendation.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="0b3ac-114">Predpoklady</span><span class="sxs-lookup"><span data-stu-id="0b3ac-114">Prerequisites</span></span>

- <span data-ttu-id="0b3ac-115">Minimálne [povolenia prispievateľa](permissions.md) v Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="0b3ac-115">At least [Contributor permissions](permissions.md) in Customer Insights.</span></span>
- <span data-ttu-id="0b3ac-116">Znalosti v oblasti obchodu, aby ste pochopili rôzne typy produktov pre vaše podnikanie a to, ako s nimi vaši zákazníci interagujú.</span><span class="sxs-lookup"><span data-stu-id="0b3ac-116">Business knowledge to understand different types of products for your business and how your customers interact with them.</span></span> <span data-ttu-id="0b3ac-117">Podporujeme odporúčanie produktov, ktoré už vaši zákazníci predtým kúpili, alebo odporúčania pre nové produkty.</span><span class="sxs-lookup"><span data-stu-id="0b3ac-117">We support recommending products that have been previously purchased by your customers or recommendations for new products.</span></span>
- <span data-ttu-id="0b3ac-118">Údaje o transakciách, nákupoch a ich histórii:</span><span class="sxs-lookup"><span data-stu-id="0b3ac-118">Data about transactions, purchases, and their history:</span></span>
    - <span data-ttu-id="0b3ac-119">Identifikátory transakcií na odlíšenie nákupov alebo transakcií.</span><span class="sxs-lookup"><span data-stu-id="0b3ac-119">Transaction identifiers to distinguish purchases or transactions.</span></span>
    - <span data-ttu-id="0b3ac-120">Identifikátory zákazníkov, aby sa transakcie mapovali na vašich zákazníkov.</span><span class="sxs-lookup"><span data-stu-id="0b3ac-120">Customer identifiers to map transactions to your customers.</span></span>
    - <span data-ttu-id="0b3ac-121">Dátumy transakčných udalostí, ktoré určujú dátumy, kedy došlo k transakcii.</span><span class="sxs-lookup"><span data-stu-id="0b3ac-121">Transaction event dates that specify dates the transaction occurred on.</span></span>
    - <span data-ttu-id="0b3ac-122">(Voliteľné) Informácie o ID produktu pre transakciu.</span><span class="sxs-lookup"><span data-stu-id="0b3ac-122">(Optional) Product ID information for the transaction.</span></span>
    - <span data-ttu-id="0b3ac-123">(Voliteľné) Či sa dá transakcia vrátiť alebo nie.</span><span class="sxs-lookup"><span data-stu-id="0b3ac-123">(Optional) If a transaction is a return or not.</span></span>
    - <span data-ttu-id="0b3ac-124">Schéma sémantických údajov vyžaduje nasledujúce informácie:</span><span class="sxs-lookup"><span data-stu-id="0b3ac-124">The semantic data schema requires the following information:</span></span>
        - <span data-ttu-id="0b3ac-125">**ID transakcie:** Jedinečný identifikátor nákupu alebo transakcie.</span><span class="sxs-lookup"><span data-stu-id="0b3ac-125">**Transaction ID:** A unique identifier of a purchase or transaction.</span></span>
        - <span data-ttu-id="0b3ac-126">**Dátum transakcie:** Dátum nákupu alebo transakcie.</span><span class="sxs-lookup"><span data-stu-id="0b3ac-126">**Transaction date:** The date the of the purchase or transaction.</span></span>
        - <span data-ttu-id="0b3ac-127">**Hodnota transakcie:** Číselná hodnota nákupu alebo transakcie.</span><span class="sxs-lookup"><span data-stu-id="0b3ac-127">**Value of the transaction:** The numerical value of the purchase or transaction.</span></span>
        - <span data-ttu-id="0b3ac-128">**Jedinečné ID produktu:** ID zakúpeného produktu alebo služby, ak sú vaše údaje na úrovni riadkovej položky.</span><span class="sxs-lookup"><span data-stu-id="0b3ac-128">**Unique product ID:** The ID of the product or service purchased if your data is at a line item level.</span></span>
        - <span data-ttu-id="0b3ac-129">(Voliteľné) **Nákup alebo vrátanie:** Pole pravda/nepravda, ktoré identifikuje, či transakcia bola vrátením alebo nie.</span><span class="sxs-lookup"><span data-stu-id="0b3ac-129">(Optional) **Purchase or return:** A true/false field that identifies if the transaction was a return or not.</span></span> <span data-ttu-id="0b3ac-130">Ak je **Hodnota transakcie** negatívna, tieto informácie použijeme tiež na odvodenie návratu.</span><span class="sxs-lookup"><span data-stu-id="0b3ac-130">If the **Value of the transaction** is negative, we will also use this information to infer a return.</span></span>


## <a name="create-a-product-recommendation-prediction"></a><span data-ttu-id="0b3ac-131">Vytvorenie predikcie odporúčania produktu</span><span class="sxs-lookup"><span data-stu-id="0b3ac-131">Create a product recommendation prediction</span></span>

1. <span data-ttu-id="0b3ac-132">V Customer Insights prejdite na stránku **Analýza** > **Predikcie**.</span><span class="sxs-lookup"><span data-stu-id="0b3ac-132">In Customer Insights, go to **Intelligence** > **Predictions**.</span></span>

1. <span data-ttu-id="0b3ac-133">Vyberte dlaždicu **Model produktových odporúčaní (verzia Preview)** a vyberte **Použiť tento model**.</span><span class="sxs-lookup"><span data-stu-id="0b3ac-133">Select the **Product recommendations model (preview)** tile and select **Use this model**.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="0b3ac-134">![Dlaždica Model odporúčaní produktov s tlačidlom Použiť tento model](media/product-recommendation-usethismodel.PNG "Dlaždica Model odporúčaní produktov s tlačidlom Použiť tento model")</span><span class="sxs-lookup"><span data-stu-id="0b3ac-134">![Product Recommendation model tile with Use this model button](media/product-recommendation-usethismodel.PNG "Product Recommendation model tile with Use this model button")</span></span>

1. <span data-ttu-id="0b3ac-135">Skontrolujte informácie o požiadavkách na model.</span><span class="sxs-lookup"><span data-stu-id="0b3ac-135">Review the information about the model requirements.</span></span> <span data-ttu-id="0b3ac-136">Ak máte požadované údaje, vyberte **Začíname**.</span><span class="sxs-lookup"><span data-stu-id="0b3ac-136">If you have the required data, select **Get started**.</span></span>

### <a name="name-model"></a><span data-ttu-id="0b3ac-137">Názov modelu</span><span class="sxs-lookup"><span data-stu-id="0b3ac-137">Name model</span></span>

1. <span data-ttu-id="0b3ac-138">Zadajte názov modelu, ktorý ho odlíši od ostatných modelov.</span><span class="sxs-lookup"><span data-stu-id="0b3ac-138">Provide a name for the model to distinguish it from other models.</span></span>

1. <span data-ttu-id="0b3ac-139">Zadajte názov výstupnej entity iba pomocou písmen a číslic, bez medzier.</span><span class="sxs-lookup"><span data-stu-id="0b3ac-139">Enter a name for the output entity using letters and numbers only, without any spaces.</span></span> <span data-ttu-id="0b3ac-140">Toto je názov, ktorý bude používať modelová entita.</span><span class="sxs-lookup"><span data-stu-id="0b3ac-140">That's the name that the model entity will use.</span></span> <span data-ttu-id="0b3ac-141">Potom vyberte položku **Ďalej**.</span><span class="sxs-lookup"><span data-stu-id="0b3ac-141">Then, select **Next**.</span></span>

### <a name="define-product-recommendation-configuration"></a><span data-ttu-id="0b3ac-142">Definujte konfiguráciu odporúčania produktu</span><span class="sxs-lookup"><span data-stu-id="0b3ac-142">Define product recommendation configuration</span></span>

1. <span data-ttu-id="0b3ac-143">Nastavte **Počet produktov**, ktoré chcete odporučiť zákazníkovi.</span><span class="sxs-lookup"><span data-stu-id="0b3ac-143">Set the **Number of products** you want to recommend to a customer.</span></span> <span data-ttu-id="0b3ac-144">Táto hodnota závisí od toho, ako váš spôsob doručenia vyplní údaje.</span><span class="sxs-lookup"><span data-stu-id="0b3ac-144">This value depends on how your delivery method fills data.</span></span> <span data-ttu-id="0b3ac-145">Ak môžete odporučiť tri produkty, nastavte túto hodnotu zodpovedajúcim spôsobom.</span><span class="sxs-lookup"><span data-stu-id="0b3ac-145">If you can recommend three products, set this value accordingly.</span></span>
   
   >[!TIP]
   > <span data-ttu-id="0b3ac-146">Môžete si vybrať **Uložiť a zavrieť** kedykoľvek a predikciu uložiť ako koncept.</span><span class="sxs-lookup"><span data-stu-id="0b3ac-146">You can select **Save and close** at any time to save the prediction as a draft.</span></span> <span data-ttu-id="0b3ac-147">Koncept predikcie nájdete na karte **Moje predikcie**.</span><span class="sxs-lookup"><span data-stu-id="0b3ac-147">You'll find the draft prediction in the **My predictions** tab.</span></span>

1. <span data-ttu-id="0b3ac-148">Vyberte, ak chcete **Navrhnúť produkty, ktoré si zákazníci nedávno zakúpili**.</span><span class="sxs-lookup"><span data-stu-id="0b3ac-148">Choose if you want to **Suggest products customers have recently purchased**.</span></span>

1. <span data-ttu-id="0b3ac-149">Ak ste sa rozhodli *neodporúčať* nedávno zakúpené produkty, nastavte **Dĺžka spätného zobrazenia**.</span><span class="sxs-lookup"><span data-stu-id="0b3ac-149">If you've selected to *not* recommend recently purchased products, set the **Look back window**.</span></span> <span data-ttu-id="0b3ac-150">Toto nastavenie určuje časový rámec, ktorý model zváži pred opätovným odporúčaním produktu používateľovi.</span><span class="sxs-lookup"><span data-stu-id="0b3ac-150">This setting specifies the time frame the model considers before recommending the product to the user again.</span></span> <span data-ttu-id="0b3ac-151">Napríklad uveďte, že zákazník si kúpi notebook každé 2 roky.</span><span class="sxs-lookup"><span data-stu-id="0b3ac-151">For example, indicate a customer purchases a laptop every 2 years.</span></span> <span data-ttu-id="0b3ac-152">Toto okno sa zameriava na históriu nákupov za posledné 2 roky a ak nájde položku, položka sa odfiltruje z odporúčaní.</span><span class="sxs-lookup"><span data-stu-id="0b3ac-152">This window will look at the purchase history for the last 2 years, and if they find an item, the item will be filtered from the recommendations.</span></span>

1. <span data-ttu-id="0b3ac-153">Vyberte **Ďalej**</span><span class="sxs-lookup"><span data-stu-id="0b3ac-153">Select **Next**</span></span>

### <a name="add-required-data"></a><span data-ttu-id="0b3ac-154">Pridanie požadovaných údajov</span><span class="sxs-lookup"><span data-stu-id="0b3ac-154">Add required data</span></span>

1. <span data-ttu-id="0b3ac-155">Vyberte **Pridať údaje** pre **História transakcií zákazníka** a vyberte entitu, ktorá poskytuje informácie o histórii transakcií/nákupov, ako je to opísané v [predpokladoch](#prerequisites).</span><span class="sxs-lookup"><span data-stu-id="0b3ac-155">Select **Add data** for **Customer transaction history** and choose the entity that provides the transaction/purchase history information as described in the [prerequisites](#prerequisites).</span></span>

1. <span data-ttu-id="0b3ac-156">Mapujte sémantické polia na atribúty v entite histórie nákupu a vyberte **Ďalej**.</span><span class="sxs-lookup"><span data-stu-id="0b3ac-156">Map the semantic fields to attributes within your purchase history entity and select **Next**.</span></span> <span data-ttu-id="0b3ac-157">Pre popis polí sa pozrite na [požiadavky](#prerequisites).</span><span class="sxs-lookup"><span data-stu-id="0b3ac-157">For descriptions of the fields, have a look at the [prerequisites](#prerequisites).</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="0b3ac-158">![Definovanie vzťahu entity](media/product-recommendation-purchasehistorymapping.PNG "Stránka História nákupu zobrazujúca sémantické atribúty, ktoré sú mapované na polia vo vybranej entite histórie nákupu")</span><span class="sxs-lookup"><span data-stu-id="0b3ac-158">![Define the entity relationship](media/product-recommendation-purchasehistorymapping.PNG "Purchase history page showing semantic attributes that are mapped to fields in the selected purchase history entity")</span></span>

1. <span data-ttu-id="0b3ac-159">Ak polia nie sú vyplnené, nakonfigurujte vzťah medzi entitou histórie nákupov a entitou *Zákazník*.</span><span class="sxs-lookup"><span data-stu-id="0b3ac-159">If the fields aren't filled in, configure the relationship from your purchase history entity to the *Customer* entity.</span></span>
    1. <span data-ttu-id="0b3ac-160">Vyberte **entitu histórie nákupov**.</span><span class="sxs-lookup"><span data-stu-id="0b3ac-160">Select the **Purchase history entity**.</span></span>
    1. <span data-ttu-id="0b3ac-161">Vyberte **Pole**, ktoré identifikuje zákazníka v entite histórie nákupov.</span><span class="sxs-lookup"><span data-stu-id="0b3ac-161">Select the **Field** that identifies the customer in the purchase history entity.</span></span> <span data-ttu-id="0b3ac-162">Musí sa vzťahovať na ID primárneho zákazníka vašej entity *Zákazník*.</span><span class="sxs-lookup"><span data-stu-id="0b3ac-162">It needs to relate to the primary customer ID of your *Customer* entity.</span></span>
    1. <span data-ttu-id="0b3ac-163">Vyberte **Entitu zákazníka**, ktorá sa zhoduje s vašou primárnou entitou zákazníka.</span><span class="sxs-lookup"><span data-stu-id="0b3ac-163">Select the **Customer entity** that matches your primary customer entity.</span></span>
    1. <span data-ttu-id="0b3ac-164">Zadajte názov, ktoré opisuje vzťah.</span><span class="sxs-lookup"><span data-stu-id="0b3ac-164">Enter a name that describes the relationship.</span></span>
       > [!div class="mx-imgBorder"]
       > <span data-ttu-id="0b3ac-165">![Stránka histórie nákupov zobrazujúca vytvorenie vzťahu so zákazníkom](media/model-purchase-join.png "Stránka histórie nákupov zobrazujúca vytvorenie vzťahu so zákazníkom")</span><span class="sxs-lookup"><span data-stu-id="0b3ac-165">![Purchase history page showing the creation of a relationship to customer](media/model-purchase-join.png "Purchase history page showing the creation of a relationship to customer")</span></span>

1. <span data-ttu-id="0b3ac-166">Vyberte položku **Uložiť**.</span><span class="sxs-lookup"><span data-stu-id="0b3ac-166">Select **Save**.</span></span>

1. <span data-ttu-id="0b3ac-167">Vyberte **Ďalej**.</span><span class="sxs-lookup"><span data-stu-id="0b3ac-167">Select **Next**.</span></span>

### <a name="set-schedule-and-review-configuration"></a><span data-ttu-id="0b3ac-168">Nastavenie plánu a kontrola konfigurácie</span><span class="sxs-lookup"><span data-stu-id="0b3ac-168">Set schedule and review configuration</span></span>

1. <span data-ttu-id="0b3ac-169">Nastavte frekvenciu na preškolenie modelu.</span><span class="sxs-lookup"><span data-stu-id="0b3ac-169">Set a frequency to retrain your model.</span></span> <span data-ttu-id="0b3ac-170">Toto nastavenie je dôležité na aktualizáciu presnosti predikcií, keď sa nové údaje importujú do Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="0b3ac-170">This setting is important to update the accuracy of predictions as new data is imported into Customer Insights.</span></span> <span data-ttu-id="0b3ac-171">Väčšina firiem môže preškoľovať raz mesačne a získať dobrú presnosť pre svoju predikciu.</span><span class="sxs-lookup"><span data-stu-id="0b3ac-171">Most businesses can retrain once per month and get a good accuracy for their prediction.</span></span>

1. <span data-ttu-id="0b3ac-172">Vyberte **Ďalej**.</span><span class="sxs-lookup"><span data-stu-id="0b3ac-172">Select **Next**.</span></span>

1. <span data-ttu-id="0b3ac-173">Skontrolujte konfiguráciu.</span><span class="sxs-lookup"><span data-stu-id="0b3ac-173">Review the configuration.</span></span> <span data-ttu-id="0b3ac-174">Výberom položky **Upraviť** pod zobrazenou hodnotu sa môžete vrátiť späť do ktorejkoľvek časti konfigurácie predikcie.</span><span class="sxs-lookup"><span data-stu-id="0b3ac-174">You can go back to any part of the prediction configuration by selecting **Edit** under the shown value.</span></span> <span data-ttu-id="0b3ac-175">Alebo si môžete vybrať krok konfigurácie z indikátora priebehu.</span><span class="sxs-lookup"><span data-stu-id="0b3ac-175">Or you can select a configuration step from the progress indicator.</span></span>

1. <span data-ttu-id="0b3ac-176">Ak sú všetky hodnoty správne nakonfigurované, vyberte položku **Uložiť a spustiť** a začnite proces predikcie.</span><span class="sxs-lookup"><span data-stu-id="0b3ac-176">If all values are configured correctly, select **Save and run** to begin the prediction process.</span></span> <span data-ttu-id="0b3ac-177">Na karte **Moje predikcie** sa zobrazuje stav vašich predikcií.</span><span class="sxs-lookup"><span data-stu-id="0b3ac-177">On the **My predictions** tab, you can see the status of your predictions.</span></span> <span data-ttu-id="0b3ac-178">Proces môže trvať niekoľko hodín, v závislosti od množstva údajov použitých v predikcii.</span><span class="sxs-lookup"><span data-stu-id="0b3ac-178">The process may take several hours to complete depending on the amount of data used in the prediction.</span></span>

## <a name="review-a-prediction-status-and-results"></a><span data-ttu-id="0b3ac-179">Skontrolujte stav a výsledky predikcie</span><span class="sxs-lookup"><span data-stu-id="0b3ac-179">Review a prediction status and results</span></span>

1. <span data-ttu-id="0b3ac-180">Prejdite na kartu **Moje predikcie** na **Inteligencia** > **Predikcie**.</span><span class="sxs-lookup"><span data-stu-id="0b3ac-180">Go to the **My predictions** tab on **Intelligence** > **Predictions**.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="0b3ac-181">![Zobrazenie stránky Moje predikcie](media/product-recommendation-mypredictions.PNG "Zobrazenie stránky Moje predikcie")</span><span class="sxs-lookup"><span data-stu-id="0b3ac-181">![View of the My Predictions page](media/product-recommendation-mypredictions.PNG "View of the My Predictions page")</span></span>

1. <span data-ttu-id="0b3ac-182">Vyberte predikciu, ktorú chcete skontrolovať.</span><span class="sxs-lookup"><span data-stu-id="0b3ac-182">Select the prediction you want to review.</span></span>
   - <span data-ttu-id="0b3ac-183">**Názov predikcie:** Názov predikcie uvedený pri jej vytváraní.</span><span class="sxs-lookup"><span data-stu-id="0b3ac-183">**Prediction name:** The name of the prediction provided when creating it.</span></span>
   - <span data-ttu-id="0b3ac-184">**Typ predikcie:** Typ modelu použitého na predikciu</span><span class="sxs-lookup"><span data-stu-id="0b3ac-184">**Prediction type:** The type of model used for the prediction</span></span>
   - <span data-ttu-id="0b3ac-185">**Entita Výstup:** Názov entity, do ktorej sa má uložiť výstup predikcie.</span><span class="sxs-lookup"><span data-stu-id="0b3ac-185">**Output entity:** Name of the entity to store the output of the prediction.</span></span> <span data-ttu-id="0b3ac-186">Entitu s týmto názvom nájdete v časti **Údaje** > **Entity**.</span><span class="sxs-lookup"><span data-stu-id="0b3ac-186">You can find an entity with this name on **Data** > **Entities**.</span></span>
   - <span data-ttu-id="0b3ac-187">**Predikované pole:** Toto pole je vyplnené iba pre niektoré typy predikcií a nepoužíva sa v predikcie odchodov.</span><span class="sxs-lookup"><span data-stu-id="0b3ac-187">**Predicted field:** This field is populated only for some types of predictions, and isn't used in churn prediction.</span></span>
   - <span data-ttu-id="0b3ac-188">**Postavenie:** Aktuálny stav spustenia predikcie.</span><span class="sxs-lookup"><span data-stu-id="0b3ac-188">**Status:** The current status of the prediction's run.</span></span>
        - <span data-ttu-id="0b3ac-189">**Vo fronte:** Predikcia momentálne čaká na spustenie ďalších procesov.</span><span class="sxs-lookup"><span data-stu-id="0b3ac-189">**Queued:** The prediction is currently waiting for other processes to run.</span></span>
        - <span data-ttu-id="0b3ac-190">**Obnovuje sa:** Predikcia momentálne beží v etape „skóre“, aby sa dosiahli výsledky, ktoré sa dostanú do výstupnej entity.</span><span class="sxs-lookup"><span data-stu-id="0b3ac-190">**Refreshing:** The prediction is currently running the "score" stage of processing to produce results that will flow into the output entity.</span></span>
        - <span data-ttu-id="0b3ac-191">**Zlyhalo:** predikcia zlyhala.</span><span class="sxs-lookup"><span data-stu-id="0b3ac-191">**Failed:** the prediction has failed.</span></span> <span data-ttu-id="0b3ac-192">Podrobnosti si prečítajte po stlačení možnosti **Záznamy**.</span><span class="sxs-lookup"><span data-stu-id="0b3ac-192">Select **Logs** for more details.</span></span>
        - <span data-ttu-id="0b3ac-193">**Úspešné:** predikcia bola úspešná.</span><span class="sxs-lookup"><span data-stu-id="0b3ac-193">**Succeeded:** the prediction has succeeded.</span></span> <span data-ttu-id="0b3ac-194">Vyberte **Zobrazenie** pod zvislými troma bokami na kontrolu predikcie</span><span class="sxs-lookup"><span data-stu-id="0b3ac-194">Select **View** under the vertical ellipses to review the prediction</span></span>
   - <span data-ttu-id="0b3ac-195">**Upravené:** Dátum zmeny konfigurácie pre predikciu sa zmenil.</span><span class="sxs-lookup"><span data-stu-id="0b3ac-195">**Edited:** The date the configuration for the prediction was changed.</span></span>
   - <span data-ttu-id="0b3ac-196">**Posledná aktualizácia:** Dátum obnovenia výsledkov predikcie vo výstupnej entite.</span><span class="sxs-lookup"><span data-stu-id="0b3ac-196">**Last refreshed:** The date the prediction refreshed results in the output entity.</span></span>

1. <span data-ttu-id="0b3ac-197">Vyberte zvislé tri bodky vedľa predikcie, pre ktorú chcete skontrolovať výsledky, a vyberte **Zobraziť**.</span><span class="sxs-lookup"><span data-stu-id="0b3ac-197">Select the vertical ellipses next to the prediction you want to review results for and select **View**.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="0b3ac-198">![Zobrazenie možností v ponuke vertikálnych troch bodiek pre predikciu vrátane úprav, obnovenia, zobrazenia, protokolov a odstránenia](media/product-recommendation-verticalellipses.PNG "Zobrazenie možností v ponuke vertikálnych troch bodiek pre predikciu vrátane úprav, obnovenia, zobrazenia, protokolov a odstránenia")</span><span class="sxs-lookup"><span data-stu-id="0b3ac-198">![View of options in the vertical ellipses menu for a prediction including edit, refresh, view, logs, and delete](media/product-recommendation-verticalellipses.PNG "View of options in the vertical ellipses menu for a prediction including edit, refresh, view, logs, and delete")</span></span>

1. <span data-ttu-id="0b3ac-199">Na stránke s výsledkami sú tri základné sekcie údajov:</span><span class="sxs-lookup"><span data-stu-id="0b3ac-199">There are three primary sections of data within the results page:</span></span>
    1. <span data-ttu-id="0b3ac-200">**Výkon tréningového modelu:** A, B alebo C sú možné skóre.</span><span class="sxs-lookup"><span data-stu-id="0b3ac-200">**Training model performance:** A, B, or C are possible scores.</span></span> <span data-ttu-id="0b3ac-201">Toto skóre označuje výkon predikcie a môže vám pomôcť pri rozhodovaní o použití výsledkov uložených vo výstupnej entite.</span><span class="sxs-lookup"><span data-stu-id="0b3ac-201">This score indicates the performance of the prediction, and can help you make the decision to use the results stored in the output entity.</span></span>
        - <span data-ttu-id="0b3ac-202">Skóre sa určujú na základe nasledujúcich pravidiel:</span><span class="sxs-lookup"><span data-stu-id="0b3ac-202">Scores are determined based on the following rules:</span></span>
            - <span data-ttu-id="0b3ac-203">**A** Model bude brať do úvahy kvalitu **A**, ak je metrika „Úspech pri K“ minimálne o 10 % vyššia ako základná hodnota.</span><span class="sxs-lookup"><span data-stu-id="0b3ac-203">**A** The model will be considered **A** quality if the "Success @ K" metric is at least 10% more the baseline.</span></span> 
            - <span data-ttu-id="0b3ac-204">**B** Model bude brať do úvahy kvalitu **B**, ak je metrika „Úspech pri K“ o 0 až 10 % vyššia ako základná hodnota.</span><span class="sxs-lookup"><span data-stu-id="0b3ac-204">**B** The model will be considered **B** quality if the "Success @ K" metric is 0 to 10% more than the baseline.</span></span>
            - <span data-ttu-id="0b3ac-205">**C** Model bude brať do úvahy kvalitu **C**, ak je metrika „Úspech pri K“ nižšia ako základná hodnota.</span><span class="sxs-lookup"><span data-stu-id="0b3ac-205">**C** The model will be considered **C** quality if the "Success @ K" metric is less than than the baseline.</span></span>
               
               > [!div class="mx-imgBorder"]
               > <span data-ttu-id="0b3ac-206">![Zobrazenie výsledku výkonnosti modelu](media/product-recommendation-modelperformance.PNG "Zobrazenie výsledku výkonnosti modelu")</span><span class="sxs-lookup"><span data-stu-id="0b3ac-206">![View of the model performance result](media/product-recommendation-modelperformance.PNG "View of the model performance result")</span></span>
            - <span data-ttu-id="0b3ac-207">**Východisková hodnota**: Model preberá najviac odporúčané produkty podľa počtu nákupov u všetkých zákazníkov a na základe naučených pravidiel identifikovaných v modeli vytvára pre zákazníkov skupinu odporúčaní.</span><span class="sxs-lookup"><span data-stu-id="0b3ac-207">**Baseline**: The model takes the top most recommended products by purchase count across all customers, and uses learned rules identified by the model to create a set of recommendations for the customers.</span></span> <span data-ttu-id="0b3ac-208">Predikcie sa potom porovnajú s najlepšími produktmi vypočítanými podľa počtu zákazníkov, ktorí si produkt kúpili.</span><span class="sxs-lookup"><span data-stu-id="0b3ac-208">The predictions are then compared to the top products, as calculated by the number of customers that had purchased the product.</span></span> <span data-ttu-id="0b3ac-209">Ak má zákazník v odporúčaných produktoch aspoň jeden produkt, ktorý sa tiež zobrazil v najpredávanejších produktoch, považuje sa to za súčasť základnej úrovne.</span><span class="sxs-lookup"><span data-stu-id="0b3ac-209">If a customer has at least one product in their recommended products that was also seen in the top purchased products, they're considered a part of the baseline.</span></span> <span data-ttu-id="0b3ac-210">Ak by tu bolo 10 z týchto zákazníkov, ktorí si kúpili odporúčaný produkt z celkovo 100 zákazníkov, základná hodnota by bola 10 %.</span><span class="sxs-lookup"><span data-stu-id="0b3ac-210">If there were 10 of these customers that had a recommended product purchased out of 100 total customers, the baseline would be 10%.</span></span>
            - <span data-ttu-id="0b3ac-211">**Úspech pri K**: Pomocou overovacej množiny časového obdobia transakcií sa vytvoria odporúčania pre všetkých zákazníkov a porovnajú sa s overovacou množinou transakcií.</span><span class="sxs-lookup"><span data-stu-id="0b3ac-211">**Success @ K**: Using a validation set of time period of transactions, recommendations are created for all customers and compared against the validation set of transactions.</span></span> <span data-ttu-id="0b3ac-212">Napríklad v období 12 mesiacov môže byť 12. mesiac vyčlenený ako súbor overovacích údajov.</span><span class="sxs-lookup"><span data-stu-id="0b3ac-212">For example, in a 12 month period, month 12 might be set aside as a validation set of data.</span></span> <span data-ttu-id="0b3ac-213">Ak model predikuje aspoň jednu vec, ktorú by ste si kúpili v 12. mesiaci, na základe toho, čo sa dozvedel z predchádzajúcich 11 mesiacov, zákazník by zvýšil metriku „Úspech pri K“.</span><span class="sxs-lookup"><span data-stu-id="0b3ac-213">If the model predicts at least one thing you would purchase in month 12 based on what it learned from the previous 11 months, the customer would increase the "Success @ K" metric.</span></span>
    
    1. <span data-ttu-id="0b3ac-214">**Najčastejšie odporúčané produkty (s počítadlom):** 5 najlepších produktov, ktoré boli predikované pre vašich zákazníkov.</span><span class="sxs-lookup"><span data-stu-id="0b3ac-214">**Most suggested products (with tally):** The top 5 products that were predicted for your customers.</span></span>
       > [!div class="mx-imgBorder"]
       > <span data-ttu-id="0b3ac-215">![Graf znázorňujúci 5 najdôležitejších produktov](media/product-recommendation-topproducts.PNG "Graf znázorňujúci 5 najdôležitejších produktov")</span><span class="sxs-lookup"><span data-stu-id="0b3ac-215">![Graph showing the top 5 most recommended products](media/product-recommendation-topproducts.PNG "Graph showing the top 5 most recommended products")</span></span>
    
    1. <span data-ttu-id="0b3ac-216">**Vysoko spoľahlivé odporúčania produktu:** Ukážka odporúčaní poskytnutých zákazníkom, o ktorých model verí, že si ich zákazník pravdepodobne kúpi.</span><span class="sxs-lookup"><span data-stu-id="0b3ac-216">**High-confidence product recommendations:** A sample of recommendations provided to your customers that the model believes are likely to be purchased by the customer.</span></span>
       > [!div class="mx-imgBorder"]
       > <span data-ttu-id="0b3ac-217">![Zoznam zobrazujúci návrhy vysokej dôveryhodnosti pre vybranú skupinu individuálnych zákazníkov](media/product-recommendation-highconfidence.PNG "Zoznam zobrazujúci návrhy vysokej dôveryhodnosti pre vybranú skupinu individuálnych zákazníkov")</span><span class="sxs-lookup"><span data-stu-id="0b3ac-217">![List showing high confidence suggestions for a select set of individual customers](media/product-recommendation-highconfidence.PNG "List showing high confidence suggestions for a select set of individual customers")</span></span>

## <a name="fix-a-failed-prediction"></a><span data-ttu-id="0b3ac-218">Oprava neúspešnej predpovede</span><span class="sxs-lookup"><span data-stu-id="0b3ac-218">Fix a failed prediction</span></span>

1. <span data-ttu-id="0b3ac-219">Prejdite na kartu **Moje predikcie** na **Inteligencia** > **Predikcie**.</span><span class="sxs-lookup"><span data-stu-id="0b3ac-219">Go to the **My predictions** tab on **Intelligence** > **Predictions**.</span></span>

1. <span data-ttu-id="0b3ac-220">Vyberte predikciu, pre ktorú chcete zobraziť denníky chýb, a vyberte **Denníky**.</span><span class="sxs-lookup"><span data-stu-id="0b3ac-220">Select the prediction you would like to view error logs for and select **Logs**.</span></span>

1. <span data-ttu-id="0b3ac-221">Skontrolujte všetky chyby.</span><span class="sxs-lookup"><span data-stu-id="0b3ac-221">Review all the errors.</span></span> <span data-ttu-id="0b3ac-222">Môže sa vyskytnúť niekoľko typov chýb, ktoré popisujú, ktorý stav chybu spôsobil.</span><span class="sxs-lookup"><span data-stu-id="0b3ac-222">There are several types of errors that can occur, and they describe what condition caused the error.</span></span> <span data-ttu-id="0b3ac-223">Napríklad chyba, že nie je dostatok údajov na presnú predikciu, sa zvyčajne vyrieši načítaním ďalších údajov do Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="0b3ac-223">For example, an error that there's not enough data to accurately predict is typically resolved by loading additional data into Customer Insights.</span></span>

## <a name="refresh-a-prediction"></a><span data-ttu-id="0b3ac-224">Obnovenie predikcie</span><span class="sxs-lookup"><span data-stu-id="0b3ac-224">Refresh a prediction</span></span>

<span data-ttu-id="0b3ac-225">Predikcie sa automaticky obnovujú podľa rovnakého [plánu, ako sa obnovujú údaje](system.md#schedule-tab), ako je nakonfigurované v nastaveniach.</span><span class="sxs-lookup"><span data-stu-id="0b3ac-225">Predictions automatically refresh on the same [schedule your data refreshes](system.md#schedule-tab) as configured in settings.</span></span>

1. <span data-ttu-id="0b3ac-226">Prejdite na kartu **Moje predikcie** na **Inteligencia** > **Predikcie**.</span><span class="sxs-lookup"><span data-stu-id="0b3ac-226">Go to the **My predictions** tab on **Intelligence** > **Predictions**.</span></span>

1. <span data-ttu-id="0b3ac-227">Vyberte zvislé tri bodky vedľa predikcie, ktorú chcete obnoviť.</span><span class="sxs-lookup"><span data-stu-id="0b3ac-227">Select the vertical ellipses next to the prediction you want to refresh.</span></span>

1. <span data-ttu-id="0b3ac-228">Vyberte **Obnoviť**.</span><span class="sxs-lookup"><span data-stu-id="0b3ac-228">Select **Refresh**.</span></span>

## <a name="delete-a-prediction"></a><span data-ttu-id="0b3ac-229">Odstránenie predikcie</span><span class="sxs-lookup"><span data-stu-id="0b3ac-229">Delete a prediction</span></span>

<span data-ttu-id="0b3ac-230">Odstránenie predikcie tiež odstráni jeho výstupnú entitu.</span><span class="sxs-lookup"><span data-stu-id="0b3ac-230">Deleting a prediction will also remove its output entity.</span></span>

1. <span data-ttu-id="0b3ac-231">Prejdite na kartu **Moje predikcie** na **Inteligencia** > **Predikcie**.</span><span class="sxs-lookup"><span data-stu-id="0b3ac-231">Go to the **My predictions** tab on **Intelligence** > **Predictions**.</span></span>

1. <span data-ttu-id="0b3ac-232">Vyberte zvislé tri bodky vedľa predikcie, ktorú chcete odstrániť.</span><span class="sxs-lookup"><span data-stu-id="0b3ac-232">Select the vertical ellipses next to the prediction you want to delete.</span></span>

1. <span data-ttu-id="0b3ac-233">Vyberte **Odstrániť**.</span><span class="sxs-lookup"><span data-stu-id="0b3ac-233">Select **Delete**.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]