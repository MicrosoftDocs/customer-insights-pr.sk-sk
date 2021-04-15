---
title: Segmenty navrhované na základe strojového učenia
description: Nechajte strojové učenie pomôcť vám nájsť nové a zaujímavé segmenty založené na atribútoch zákazníka.
ms.date: 02/01/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
manager: shellyha
ms.openlocfilehash: bbc22adcd7b6e756fa6128abd855795de7480f2d
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597116"
---
# <a name="suggested-segments-preview"></a><span data-ttu-id="a2fa9-103">Navrhované segmenty (ukážka)</span><span class="sxs-lookup"><span data-stu-id="a2fa9-103">Suggested segments (preview)</span></span>

<span data-ttu-id="a2fa9-104">Objavte zaujímavé segmenty svojich zákazníkov pomocou modelu AI.</span><span class="sxs-lookup"><span data-stu-id="a2fa9-104">Discover interesting segments of your customers with the help of an AI model.</span></span> <span data-ttu-id="a2fa9-105">Táto funkcia strojového učenia navrhuje segmenty na základe mier alebo atribútov zákazníka.</span><span class="sxs-lookup"><span data-stu-id="a2fa9-105">This machine learning powered feature suggests segments based on measures or customer attributes.</span></span> <span data-ttu-id="a2fa9-106">Môže vám pomôcť vylepšiť vaše KPI alebo lepšie pochopiť vplyv atribútov v kontexte s inými atribútmi.</span><span class="sxs-lookup"><span data-stu-id="a2fa9-106">It can help improve your KPIs or better understand the influence of attributes in context of other attributes.</span></span> 

> [!NOTE]
> <span data-ttu-id="a2fa9-107">Funkcia navrhovaných segmentov používa automatizované prostriedky na vyhodnotenie údajov a na vytváranie predikcií na základe týchto údajov, a preto je možné ju použiť ako metódu profilovania, pretože tento pojem je definovaný všeobecným nariadením o ochrane údajov („GDPR“).</span><span class="sxs-lookup"><span data-stu-id="a2fa9-107">The suggested segments feature uses automated means to evaluate data and make predictions based on that data, and therefore has the capability to be used as a method of profiling, as that term is defined by the General Data Protection Regulation ("GDPR").</span></span> <span data-ttu-id="a2fa9-108">Vaše použitie tejto funkcie na spracovanie údajov môže podliehať GDPR alebo iným zákonom alebo predpisom.</span><span class="sxs-lookup"><span data-stu-id="a2fa9-108">Your use of this feature to process data may be subject to GDPR or other laws or regulations.</span></span> <span data-ttu-id="a2fa9-109">Ste zodpovední za zabezpečenie toho, že vaše používanie služby Dynamics 365 Customer Insights vrátane tejto funkcie bude v súlade so všetkými platnými zákonmi a nariadeniami vrátane zákonov týkajúcich sa ochrany súkromia, osobných údajov, biometrických údajov, ochrany údajov a dôvernosti komunikácií.</span><span class="sxs-lookup"><span data-stu-id="a2fa9-109">You are responsible for ensuring that your use of Dynamics 365 Customer Insights, including this feature, complies with all applicable laws and regulations, including laws related to privacy, personal data, biometric data, data protection, and confidentiality of communications.</span></span>

:::image type="content" source="media/suggested-segments-details.png" alt-text="Stránka Navrhované segmenty v nástroji Customer Insights, ktorá zobrazuje podrobnosti návrhu na bočnej table.":::

## <a name="suggested-segments-to-improve-your-kpis"></a><span data-ttu-id="a2fa9-111">Navrhované segmenty na zlepšenie vašich KPI</span><span class="sxs-lookup"><span data-stu-id="a2fa9-111">Suggested segments to improve your KPIs</span></span>

<span data-ttu-id="a2fa9-112">Ako používateľ prehľadov cieľových skupín pravdepodobne máte sériu [vytvorených opatrení](measures.md), ktoré pomáhajú sledovať vaše kľúčové ukazovatele výkonu (KPI).</span><span class="sxs-lookup"><span data-stu-id="a2fa9-112">As a user of audience insights, you likely have a series of [measures created](measures.md) that help track your Key Performance Indicators (KPIs).</span></span> <span data-ttu-id="a2fa9-113">Je dôležité pochopiť, ako určité atribúty ovplyvňujú tento KPI pri vytváraní segmentov a pri vedení vysoko cielenej kampane.</span><span class="sxs-lookup"><span data-stu-id="a2fa9-113">It's important to understand how certain attributes influence this KPI to create segments and run a highly targeted campaign.</span></span>   
<span data-ttu-id="a2fa9-114">Napríklad sledujete mieru s názvom *TotalSpendPerCustomer*.</span><span class="sxs-lookup"><span data-stu-id="a2fa9-114">For example, you track a measure called *TotalSpendPerCustomer*.</span></span> <span data-ttu-id="a2fa9-115">Ako firma by ste chceli, aby toto číslo rástlo.</span><span class="sxs-lookup"><span data-stu-id="a2fa9-115">As a business, you’d like to see this number grow.</span></span> <span data-ttu-id="a2fa9-116">Výber miery ako primárneho atribútu vám umožní vybrať atribúty, ktoré chcete posúdiť z hľadiska vplyvu.</span><span class="sxs-lookup"><span data-stu-id="a2fa9-116">Choosing a measure as primary attribute, lets you select the attributes that you want to assess for influence.</span></span> <span data-ttu-id="a2fa9-117">Povedzme *stupeň členstva*, *členské obdobie* a *povolanie*.</span><span class="sxs-lookup"><span data-stu-id="a2fa9-117">Let's say *membership tier*, *membership period*, and *occupation*.</span></span> <span data-ttu-id="a2fa9-118">Customer Insights potom môžu navrhnúť segment, ktorý vám povie, kto má na toto opatrenie najväčší vplyv.</span><span class="sxs-lookup"><span data-stu-id="a2fa9-118">Customer Insights can then suggest a segment that tells you who are the biggest influence of that measure.</span></span> <span data-ttu-id="a2fa9-119">Napríklad *Účtovníci*, ktorí sú *zlatými* členmi a ktorí pracujú vo vašej firme *najmenej päť rokov* najviac ovplyvňujú *TotalSpendPerCustomer*.</span><span class="sxs-lookup"><span data-stu-id="a2fa9-119">For example, *Accountants* who are *Gold* members, and who have been with your business for *at least five years* are the biggest influencer of *TotalSpendPerCustomer*.</span></span> <span data-ttu-id="a2fa9-120">Pre každý návrh získate odhadovanú veľkosť segmentu.</span><span class="sxs-lookup"><span data-stu-id="a2fa9-120">You’ll get an estimated segment size for every suggestion.</span></span> <span data-ttu-id="a2fa9-121">Tieto informácie môžete použiť na vytvorenie kampaní pre cieľové publikum.</span><span class="sxs-lookup"><span data-stu-id="a2fa9-121">You can use this information to create campaigns for the targeted audiences.</span></span>

## <a name="understand-what-influences-a-customer-attribute"></a><span data-ttu-id="a2fa9-122">Pochopenie, čo ovplyvňuje atribút zákazníka</span><span class="sxs-lookup"><span data-stu-id="a2fa9-122">Understand what influences a customer attribute</span></span>

<span data-ttu-id="a2fa9-123">Namiesto miery môžete ako primárny atribút zvoliť atribút zákazníka.</span><span class="sxs-lookup"><span data-stu-id="a2fa9-123">You can choose a customer attribute instead of a measure as the primary attribute.</span></span> <span data-ttu-id="a2fa9-124">Na základe vášho výberu ovplyvňujúcich atribútov model AI vytvára sériu návrhov, ktoré ukazujú, ako vybrané atribúty ovplyvňujú primárny atribút.</span><span class="sxs-lookup"><span data-stu-id="a2fa9-124">Based on your choice of influencing attributes, the AI model creates a series of suggestions that show how the selected attributes influence the primary attribute.</span></span>   
<span data-ttu-id="a2fa9-125">Napríklad si vyberiete ako primárny atribút *Člen vernostného programu (áno/nie)*.</span><span class="sxs-lookup"><span data-stu-id="a2fa9-125">For example, you choose *Rewards Member (Yes/No)* as the primary attribute.</span></span> <span data-ttu-id="a2fa9-126">*Funkčné obdobie*, *Povolanie* a *Počet žiadostí o podporu* sú nastavené ako ďalšie ovplyvňujúce atribúty.</span><span class="sxs-lookup"><span data-stu-id="a2fa9-126">*Tenure*, *Occupation*, and *Number of Support Tickets* are set as other influencing attributes.</span></span> <span data-ttu-id="a2fa9-127">Model AI by mohol navrhnúť segmenty, ktoré naznačujú, že členmi odmien sú väčšinou IT profesionáli s funkčným obdobím dva roky.</span><span class="sxs-lookup"><span data-stu-id="a2fa9-127">The AI model could suggest segments indicating mostly IT professionals with tenure over two years are rewards members.</span></span> <span data-ttu-id="a2fa9-128">Ďalším návrhom by sa mohlo zdôrazniť, že účtovníci s funkčným obdobím nad jeden rok a menej ako troma žiadosťami o podporu sú členmi vernostného programu.</span><span class="sxs-lookup"><span data-stu-id="a2fa9-128">Another suggestion could highlight that accountants with tenure over one year and fewer than three support tickets are rewards members.</span></span> 

## <a name="artificial-intelligence-usage"></a><span data-ttu-id="a2fa9-129">Použitie umelej inteligencie</span><span class="sxs-lookup"><span data-stu-id="a2fa9-129">Artificial intelligence usage</span></span>

<span data-ttu-id="a2fa9-130">Pomocou primárneho atribútu a ovplyvňujúcich atribútov navrhuje algoritmus rozhodovacieho stromu zaujímavé segmenty.</span><span class="sxs-lookup"><span data-stu-id="a2fa9-130">Using the primary attribute and influencing attributes, a decision tree algorithm suggests interesting segments.</span></span> <span data-ttu-id="a2fa9-131">Návrhy vychádzajú z pravidiel alebo vzorov, ktoré zachytil algoritmus AI.</span><span class="sxs-lookup"><span data-stu-id="a2fa9-131">The suggestions are based on rules or patterns that were picked up by the AI algorithm.</span></span> <span data-ttu-id="a2fa9-132">Ako návrhy sa zobrazia iba segmenty, ktoré sa výrazne líšia od priemernej populácie.</span><span class="sxs-lookup"><span data-stu-id="a2fa9-132">Only segments that significantly differ from the average population are shown as suggestions.</span></span> <span data-ttu-id="a2fa9-133">Porovnanie s priemernou populáciou je založené na vybranej miere alebo primárnom atribúte.</span><span class="sxs-lookup"><span data-stu-id="a2fa9-133">The comparison to the average population is based on the selected measure or primary attribute.</span></span>

### <a name="responsible-ai"></a><span data-ttu-id="a2fa9-134">Zodpovedná AI</span><span class="sxs-lookup"><span data-stu-id="a2fa9-134">Responsible AI</span></span>

<span data-ttu-id="a2fa9-135">Navrhované segmenty vám umožňujú výber atribútov na vytvorenie nových segmentov a spracovanie vybratých údajov.</span><span class="sxs-lookup"><span data-stu-id="a2fa9-135">Suggested segments lets you select attributes to create new segments and process the data you select.</span></span> <span data-ttu-id="a2fa9-136">Pri výbere atribútov vrátane citlivých atribútov ako rasa, sexuálna orientácia alebo pohlavie musíte zabezpečiť, aby ste tieto údaje mohli a mali spracovávať.</span><span class="sxs-lookup"><span data-stu-id="a2fa9-136">When choosing attributes, including sensitive attributes like race, sexual orientation, or gender, you must ensure that you can and should process that data.</span></span> <span data-ttu-id="a2fa9-137">Ste zodpovední za dodržiavanie všetkých zákonov platných pre vašu organizáciu a za dodržiavanie zásad a ochrany osobných údajov vašej organizácie.</span><span class="sxs-lookup"><span data-stu-id="a2fa9-137">You are responsible to comply with any laws applicable to your organization and adhere to your organization’s principles and privacy policies.</span></span>

### <a name="different-results-for-primary-attributes-with-categorical-and-numeric-values"></a><span data-ttu-id="a2fa9-138">Odlišné výsledky pre primárne atribúty s kategorickými a číselnými hodnotami</span><span class="sxs-lookup"><span data-stu-id="a2fa9-138">Different results for primary attributes with categorical and numeric values</span></span>

<span data-ttu-id="a2fa9-139">Návrhy segmentov sa líšia, ak ako primárny atribút vyberiete číselný atribút alebo kategorický atribút.</span><span class="sxs-lookup"><span data-stu-id="a2fa9-139">Segment suggestions are different if you choose a numeric attribute or a categorical attribute as the primary attribute.</span></span> <span data-ttu-id="a2fa9-140">Hodnoty v kategorickom atribúte obsahujú dve alebo viac kategórií alebo typov.</span><span class="sxs-lookup"><span data-stu-id="a2fa9-140">Values in a categorical attribute contain two or more categories or types.</span></span> <span data-ttu-id="a2fa9-141">Číselný atribút obsahuje kvantitatívne údaje a je s ním spojený zmysel pre meranie.</span><span class="sxs-lookup"><span data-stu-id="a2fa9-141">A numeric attribute contains quantitative data and has a sense of measurement associated with it.</span></span>

<span data-ttu-id="a2fa9-142">S číselným atribútom ako *ročný príjem* alebo *členské obdobie* ako primárnym atribútom systém navrhuje segmenty, ktoré majú vyššiu alebo nižšiu priemernú hodnotu číselného atribútu v porovnaní so všetkými zákazníkmi.</span><span class="sxs-lookup"><span data-stu-id="a2fa9-142">With a numeric attribute like *annual income* or *membership period* as the primary attribute, the system suggests segments that have a higher or lower average value of the numeric attribute when compared to all customers.</span></span>

<span data-ttu-id="a2fa9-143">Kategorický atribút ako *spokojnosť zákazníkov* ako primárny atribút vedie k navrhovaným segmentom, ktoré majú vyššie alebo nižšie percento zákazníkov patriacich do konkrétnej kategórie v porovnaní s percentom všetkých zákazníkov patriacich do tej istej kategórie.</span><span class="sxs-lookup"><span data-stu-id="a2fa9-143">A categorical attribute like *customer satisfaction* as the primary attribute results in suggested segments that have a higher or lower percentage of customers belonging to a particular category when compared to the percentage of all customers belonging to that same category.</span></span> <span data-ttu-id="a2fa9-144">Napríklad *spokojnosť zákazníkov* je vybraná ako primárny atribút a skladá sa z troch kategórií (*Nízka*, *Stredná* a *Vysoká*).</span><span class="sxs-lookup"><span data-stu-id="a2fa9-144">For example, *customer satisfaction* is chosen as the primary attribute and it consists of three categories (*Low*, *Medium* and *High*).</span></span> <span data-ttu-id="a2fa9-145">Pre každú kategóriu sa navrhnú segmenty, ktoré majú výrazne vyššie alebo nižšie percento zákazníkov patriacich do tejto kategórie v porovnaní s podielom všetkých zákazníkov v rovnakej kategórii.</span><span class="sxs-lookup"><span data-stu-id="a2fa9-145">For each category, segments will be suggested that have a significantly higher or lower percentage of customers belonging to that category as compared to the proportion of all customers in same category.</span></span> <span data-ttu-id="a2fa9-146">Ak má 22 % všetkých zákazníkov *Vysokú* spokojnosť, potom iba segmenty, ktoré majú podstatne vyšší alebo nižší podiel zákazníkov so spokojnosťou *Vysoká* v porovnaní s 22 % budú navrhnuté pre túto kategóriu.</span><span class="sxs-lookup"><span data-stu-id="a2fa9-146">If 22% of all customers have a *High* satisfaction, then, only segments that have a significantly higher or lower proportion of customers with a *High* satisfaction as compared to 22% will be suggested for that category.</span></span> <span data-ttu-id="a2fa9-147">Podobne platí, že budú navrhnuté segmenty pre každú z ďalších kategórií (*Nízka* a *Stredná*), ak sú štatisticky významné.</span><span class="sxs-lookup"><span data-stu-id="a2fa9-147">Similarly, segments will be suggested for each of the other categories (*Low* and *Medium*) if they are statistically significant.</span></span>

> [!NOTE]
> <span data-ttu-id="a2fa9-148">V súčasnosti podporujeme iba primárne kategorické atribúty, ktoré majú až 10 kategórií.</span><span class="sxs-lookup"><span data-stu-id="a2fa9-148">Currently, we only support primary categorical attributes that have up to 10 categories.</span></span> <span data-ttu-id="a2fa9-149">Ak chcete vidieť návrhy segmentov založené na primárnom atribúte s viac ako 10 kategóriami, odporúčame vám zoskupiť niektoré z kategórií, aby ste znížili počet kategórií na 10 alebo menej.</span><span class="sxs-lookup"><span data-stu-id="a2fa9-149">If you want to see segment suggestions based on a primary attribute with more than 10 categories, we recommend to group some of the categories to reduce the number of categories to 10 or fewer.</span></span> <span data-ttu-id="a2fa9-150">Toto obmedzenie sa vzťahuje iba na primárne atribúty.</span><span class="sxs-lookup"><span data-stu-id="a2fa9-150">This limitation only applies to primary attributes.</span></span> <span data-ttu-id="a2fa9-151">Na ovplyvnenie kategorických atribútov v súčasnosti podporujeme maximálne 100 kategórií.</span><span class="sxs-lookup"><span data-stu-id="a2fa9-151">For influencing categorical attributes, we currently support a maximum of 100 categories.</span></span>

## <a name="generate-suggested-segments"></a><span data-ttu-id="a2fa9-152">Generovanie navrhovaných segmentov</span><span class="sxs-lookup"><span data-stu-id="a2fa9-152">Generate suggested segments</span></span>

1. <span data-ttu-id="a2fa9-153">Prejdite na **Segmenty**.</span><span class="sxs-lookup"><span data-stu-id="a2fa9-153">Go to **Segments**.</span></span>

1. <span data-ttu-id="a2fa9-154">Vyberte kartu **Návrhy (ukážka)**.</span><span class="sxs-lookup"><span data-stu-id="a2fa9-154">Select the **Suggestions (preview)** tab.</span></span>

1. <span data-ttu-id="a2fa9-155">Vyberte **Získať nové návrhy** na spustenie interaktívneho sprievodcu.</span><span class="sxs-lookup"><span data-stu-id="a2fa9-155">Select **Get new suggestions** to start the guided experience.</span></span>

1. <span data-ttu-id="a2fa9-156">Vyberte mieru alebo atribút zákazníka ako primárny atribút a následne vyberte **Ďalej**.</span><span class="sxs-lookup"><span data-stu-id="a2fa9-156">Choose a measure or a customer attribute as the primary attribute and select **Next**.</span></span>

   :::image type="content" source="media/suggested-segments-primary-attribute.png" alt-text="Výber primárneho atribútu pre návrhy odporúčaných segmentov.":::

1. <span data-ttu-id="a2fa9-158">Vyberte ovplyvňujúce atribúty a následne **Uložiť**.</span><span class="sxs-lookup"><span data-stu-id="a2fa9-158">Select the influencing attributes and select **Save**.</span></span>
   
   > [!TIP]
   > <span data-ttu-id="a2fa9-159">Výber viacerých ovplyvňujúcich atribútov zvyšuje šance na vyhodnotenie toho, ako ovplyvňujú primárny atribút.</span><span class="sxs-lookup"><span data-stu-id="a2fa9-159">Selecting multiple influencing attributes improves the chances of evaluating how they influence the primary attribute.</span></span> <span data-ttu-id="a2fa9-160">Neuvádzajte atribúty, ktoré nemajú žiadny vplyv na primárny atribút.</span><span class="sxs-lookup"><span data-stu-id="a2fa9-160">Don't include attributes that have no influence the primary attribute.</span></span> <span data-ttu-id="a2fa9-161">Napríklad ak sú všetci vaši zákazníci z konkrétnej krajiny, neuvádzajte atribút *krajina*, pretože to nebude mať žiadny vplyv na výstup.</span><span class="sxs-lookup"><span data-stu-id="a2fa9-161">For example, if all your customers are from a specific country, don't include the *country* attribute because it won't have any impact on the output.</span></span>

1. <span data-ttu-id="a2fa9-162">V závislosti od počtu profilov zákazníkov a vybraných atribútov môže spracovanie vybraných atribútov trvať niekoľko minút.</span><span class="sxs-lookup"><span data-stu-id="a2fa9-162">Depending on the number of customer profiles and selected attributes, it can take a few minutes to process the selected attributes.</span></span> 

## <a name="view-details-of-a-suggested-segment"></a><span data-ttu-id="a2fa9-163">Zobrazenie podrobností o navrhovanom segmente</span><span class="sxs-lookup"><span data-stu-id="a2fa9-163">View details of a suggested segment</span></span>

<span data-ttu-id="a2fa9-164">Keď model AI vygeneruje návrhy, nájdete ich uvedené v zozname **Segmenty** > **Návrhy (ukážka)**.</span><span class="sxs-lookup"><span data-stu-id="a2fa9-164">Once the AI model has generated the suggestions, you'll find them listed on **Segments** > **Suggestions (preview)**.</span></span>
 
<span data-ttu-id="a2fa9-165">Vyberte navrhovaný segment a prezrite si podrobnosti tohto návrhu vrátane porovnania priemernej hodnoty a počtu členov segmentu.</span><span class="sxs-lookup"><span data-stu-id="a2fa9-165">Select a suggested segment to review the details of that suggestion including a comparison of the average value and the number of segment members.</span></span> <span data-ttu-id="a2fa9-166">Môžete tiež skontrolovať hodnoty atribútov alebo pravidlá, ktoré sa model AI naučil, aby navrhol vybraný segment.</span><span class="sxs-lookup"><span data-stu-id="a2fa9-166">You can also review the attribute values or rules that the AI model learned to suggest the selected segment.</span></span>

## <a name="save-a-suggestion-as-a-segment"></a><span data-ttu-id="a2fa9-167">Uloženie návrhu ako segmentu</span><span class="sxs-lookup"><span data-stu-id="a2fa9-167">Save a suggestion as a segment</span></span>

1. <span data-ttu-id="a2fa9-168">Prejdite na **Segmenty** > **Návrhy (ukážka)**.</span><span class="sxs-lookup"><span data-stu-id="a2fa9-168">Go to **Segments** > **Suggestions (preview)**.</span></span>

1. <span data-ttu-id="a2fa9-169">Vyberte segment, ktorý chcete uložiť.</span><span class="sxs-lookup"><span data-stu-id="a2fa9-169">Select the segment you want to save.</span></span> 

1. <span data-ttu-id="a2fa9-170">Na bočnej table vyberte možnosť **Uložiť ako segment**.</span><span class="sxs-lookup"><span data-stu-id="a2fa9-170">In the side pane, select **Save as segment**.</span></span> 

1. <span data-ttu-id="a2fa9-171">Po uložení sa segment zobrazí v zozname segmentov na karte **Všetky segmenty**. Teraz ho bude možné [obnoviť, upraviť alebo odstrániť rovnako ako každý iný segment](segments.md).</span><span class="sxs-lookup"><span data-stu-id="a2fa9-171">After saving the segment, it will show in the list of segments on the **All segments** tab. It can now be [refreshed, edited, or deleted like any other segment](segments.md).</span></span>

## <a name="refresh-or-edit-a-set-of-suggestions"></a><span data-ttu-id="a2fa9-172">Obnovenie alebo úprava skupiny návrhov</span><span class="sxs-lookup"><span data-stu-id="a2fa9-172">Refresh or edit a set of suggestions</span></span>

1. <span data-ttu-id="a2fa9-173">Prejdite na **Segmenty** > **Návrhy (ukážka)**.</span><span class="sxs-lookup"><span data-stu-id="a2fa9-173">Go to **Segments** > **Suggestions (preview)**.</span></span>

1. <span data-ttu-id="a2fa9-174">Vyberte **Obnoviť návrhy** na obnovenie návrhov pri zachovaní nakonfigurovaných atribútov.</span><span class="sxs-lookup"><span data-stu-id="a2fa9-174">Select **Refresh suggestions** to refresh the suggestions while keeping configured attributes.</span></span> <span data-ttu-id="a2fa9-175">Alebo vyberte **Upraviť atribúty** na úpravu nakonfigurovaných atribútov.</span><span class="sxs-lookup"><span data-stu-id="a2fa9-175">Or select **Edit attributes** to modify the configured attributes.</span></span> <span data-ttu-id="a2fa9-176">Systém znova spustí model AI, vygeneruje návrhy segmentov na základe najnovších údajov a nahradí súčasné návrhy.</span><span class="sxs-lookup"><span data-stu-id="a2fa9-176">The system will rerun the AI model, generate segment suggestions based on the latest data, and replace the current suggestions.</span></span>

## <a name="limitations"></a><span data-ttu-id="a2fa9-177">Obmedzenia</span><span class="sxs-lookup"><span data-stu-id="a2fa9-177">Limitations</span></span>

1. <span data-ttu-id="a2fa9-178">Nesúlad odhadovanej veľkosti segmentu: Ak vyberiete primárny atribút, ktorý obsahuje prázdne hodnoty, môže to mať vplyv na odhadovanú veľkosť segmentu v návrhoch segmentov.</span><span class="sxs-lookup"><span data-stu-id="a2fa9-178">Estimated segment size mismatch: If you choose a primary attribute that contains empty values, it can affect the estimated segment size in the segment suggestions.</span></span> <span data-ttu-id="a2fa9-179">Pri ukladaní takéhoto segmentu sa skutočná veľkosť segmentu môže líšiť od pôvodného odhadu.</span><span class="sxs-lookup"><span data-stu-id="a2fa9-179">When saving such segment, the actual segment size can be different to the original estimation.</span></span>
 
2. <span data-ttu-id="a2fa9-180">Primárne atribúty boolovského typu nefungujú: V súčasnosti podporujeme ako primárny atribút iba reťazcové a číselné typy údajov.</span><span class="sxs-lookup"><span data-stu-id="a2fa9-180">Boolean type primary attributes don't work: Currently, we only support string and numeric types of data as the primary attribute.</span></span>

3. <span data-ttu-id="a2fa9-181">Navrhované segmenty nie sú dostatočne odlišné: Nezabudnite, že vybrané atribúty a rozloženie hodnôt týchto atribútov ovplyvňuje výsledky.</span><span class="sxs-lookup"><span data-stu-id="a2fa9-181">Suggested segments aren't distinct enough: Keep in mind that the selected attributes and the distribution of values of those attributes influences the results.</span></span> <span data-ttu-id="a2fa9-182">Môžete zmeniť svoje ovplyvňujúce atribúty alebo dokonca hlavný atribút, aby ste dosiahli rôzne výsledky.</span><span class="sxs-lookup"><span data-stu-id="a2fa9-182">You can change your influencing attributes or even your primary attribute to get different results.</span></span>



[!INCLUDE[footer-include](../includes/footer-banner.md)]