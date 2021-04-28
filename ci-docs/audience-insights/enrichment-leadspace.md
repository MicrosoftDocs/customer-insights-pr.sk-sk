---
title: Obohatenie profilov spoločností pomocou obohatenia tretej strany Leadspace
description: Všeobecné informácie o obohatení pomocou obohatenia tretej stranou Leadspace.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: ccf4f661ecffb281556a4545b1f26ee809c697cd
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 04/14/2021
ms.locfileid: "5895932"
---
# <a name="enrichment-of-company-profiles-with-leadspace-preview"></a><span data-ttu-id="b9ebb-103">Obohatenie profilov spoločnosti pomocou Leadspace (náhľad)</span><span class="sxs-lookup"><span data-stu-id="b9ebb-103">Enrichment of company profiles with Leadspace (preview)</span></span>

<span data-ttu-id="b9ebb-104">Leadspace je spoločnosť zaoberajúca dátovou vedou, ktorá poskytuje platformu B2B Customer Data.</span><span class="sxs-lookup"><span data-stu-id="b9ebb-104">Leadspace is a data science company that provides a B2B Customer Data Platform.</span></span> <span data-ttu-id="b9ebb-105">Umožňuje zákazníkom so zjednotenými zákazníckymi profilmi pre spoločnosti obohacovať svoje údaje.</span><span class="sxs-lookup"><span data-stu-id="b9ebb-105">It enables customers with unified customer profiles for companies to enrich their data.</span></span> <span data-ttu-id="b9ebb-106">Obohatenia zahŕňajú viaceré atribúty, ako sú veľkosť spoločnosti, umiestnenie, priemysel a ďalšie možnosti.</span><span class="sxs-lookup"><span data-stu-id="b9ebb-106">Enrichments include more attributes such as company size, location, industry, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="b9ebb-107">Predpoklady</span><span class="sxs-lookup"><span data-stu-id="b9ebb-107">Prerequisites</span></span>

<span data-ttu-id="b9ebb-108">Na konfiguráciu Leadspace musia byť splnené nasledujúce predpoklady:</span><span class="sxs-lookup"><span data-stu-id="b9ebb-108">To configure Leadspace, the following prerequisites must be met:</span></span>

- <span data-ttu-id="b9ebb-109">Máte aktívnu licenciu Leadspace.</span><span class="sxs-lookup"><span data-stu-id="b9ebb-109">You have an active Leadspace license.</span></span>
- <span data-ttu-id="b9ebb-110">Máte [zjednotené profily zákazníkov](customer-profiles.md) pre spoločnosti.</span><span class="sxs-lookup"><span data-stu-id="b9ebb-110">You have [unified customer profiles](customer-profiles.md) for companies.</span></span>
- <span data-ttu-id="b9ebb-111">Pripojenie Leadspace už nakonfiguroval správca alebo máte povolenia [správcu](permissions.md#administrator) a „trvalý kľúč” (označovaný ako **Token vedúceho priestoru**).</span><span class="sxs-lookup"><span data-stu-id="b9ebb-111">A Leadspace connection has already been configured by an administrator or you have [administrator](permissions.md#administrator) permissions and the “perpetual key” (referred to as **Leadspace token**).</span></span> <span data-ttu-id="b9ebb-112">Kontakt [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) priamo pre podrobnosti o ich produkte.</span><span class="sxs-lookup"><span data-stu-id="b9ebb-112">Contact [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) directly for details about their product.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="b9ebb-113">Konfigurácia obohatenia</span><span class="sxs-lookup"><span data-stu-id="b9ebb-113">Configure the enrichment</span></span>

1. <span data-ttu-id="b9ebb-114">V prehľadoch cieľových skupín prejdite na **Údaje** > **Obohatenie**.</span><span class="sxs-lookup"><span data-stu-id="b9ebb-114">In audience insights, go to **Data** > **Enrichment**.</span></span>

1. <span data-ttu-id="b9ebb-115">Zvoľte možnosť **Obohatiť moje údaje** na dlaždici Leadspace a stlačte možnosť **Začíname**.</span><span class="sxs-lookup"><span data-stu-id="b9ebb-115">Select **Enrich my data** on the Leadspace tile and select **Get started**.</span></span>

   :::image type="content" source="media/leadspace-tile.png" alt-text="Snímka obrazovky dlaždice Leadspace.":::

1. <span data-ttu-id="b9ebb-117">V rozbaľovacej ponuke stlačte možnosť [pripojenie](connections.md).</span><span class="sxs-lookup"><span data-stu-id="b9ebb-117">Select a [connection](connections.md) from the drop-down.</span></span> <span data-ttu-id="b9ebb-118">Ak nie je k dispozícii pripojenie, kontaktujte správcu.</span><span class="sxs-lookup"><span data-stu-id="b9ebb-118">Contact an administrator if no connection is available.</span></span> <span data-ttu-id="b9ebb-119">Ak ste správca, pripojenie môžete vytvoriť výberom možnosti **Pridať pripojenie** a zvoľte možnosť **Leadspace**.</span><span class="sxs-lookup"><span data-stu-id="b9ebb-119">If you are an administrator, you can create a connection by selecting **Add connection** and choosing **Leadspace**.</span></span> 

1. <span data-ttu-id="b9ebb-120">Vyberte **Pripojiť sa k Leadspace** na potvrdenie zvoleného spojenia.</span><span class="sxs-lookup"><span data-stu-id="b9ebb-120">Select **Connect to Leadspace** to confirm the connection.</span></span>

1. <span data-ttu-id="b9ebb-121">Stlačte možnosť **Ďalej** a vyberte **Množina údajov o zákazníkoch** na obohatenie o demografické údaje spoločnosti z Leadspace.</span><span class="sxs-lookup"><span data-stu-id="b9ebb-121">Select **Next** and choose the **Customer data set** you want to enrich with company data from Leadspace.</span></span> <span data-ttu-id="b9ebb-122">Môžete zvoliť entitu **Zákazník**, aby ste obohatili všetky svoje zákaznícke profily, alebo vyberte entitu segmentu, aby ste obohatili iba profily zákazníkov obsiahnuté v danom segmente.</span><span class="sxs-lookup"><span data-stu-id="b9ebb-122">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-Leadspace-configuration-customer-data-set.png" alt-text="Snímka obrazovky pri výbere množiny údajov o zákazníkoch.":::

1. <span data-ttu-id="b9ebb-124">Stlačte možnosť **Ďalej** a definujte, ktorý typ polí z vašich zjednotených profilov sa má použiť na vyhľadanie zodpovedajúcich demografických údajov spoločnosti z Leadspace.</span><span class="sxs-lookup"><span data-stu-id="b9ebb-124">Select **Next** and define which fields from your unified profiles are used to look for matching company data from Leadspace.</span></span> <span data-ttu-id="b9ebb-125">Pole **Názov spoločnosti** je povinné.</span><span class="sxs-lookup"><span data-stu-id="b9ebb-125">The **Name of company** field is required.</span></span> <span data-ttu-id="b9ebb-126">Pre vyššiu presnosť zhody možno pridať až dve ďalšie polia, **Webová lokalita spoločnosti** a **Sídlo spoločnosti**.</span><span class="sxs-lookup"><span data-stu-id="b9ebb-126">For a higher match accuracy, up to two other fields, **Company website** and **Company location**, can be added.</span></span>

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="Tabla mapovania polí Leadspace.":::

1. <span data-ttu-id="b9ebb-128">Stlačte možnosť **Ďalej** na vyplnenie mapovania poľa.</span><span class="sxs-lookup"><span data-stu-id="b9ebb-128">Select **Next** to complete the field mapping.</span></span>

1. <span data-ttu-id="b9ebb-129">Zadajte názov obohatenia a vyberte **Uložiť obohatenie** po preskúmaní vašich možností.</span><span class="sxs-lookup"><span data-stu-id="b9ebb-129">Provide a name for the enrichment and select **Save enrichment** after reviewing your choices.</span></span>


## <a name="configure-the-connection-for-leadspace"></a><span data-ttu-id="b9ebb-130">Nakonfigurujte pripojenie pre Leadspace</span><span class="sxs-lookup"><span data-stu-id="b9ebb-130">Configure the connection for Leadspace</span></span> 

<span data-ttu-id="b9ebb-131">Na konfiguráciu pripojení musíte byť administrátor.</span><span class="sxs-lookup"><span data-stu-id="b9ebb-131">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="b9ebb-132">Stlačte možnosť **Pridať pripojenie** pri konfigurácii obohatenia *alebo* prejdite na **Správca** > **Pripojenia** a vyberte **Nastaviť** na dlaždici Leadspace.</span><span class="sxs-lookup"><span data-stu-id="b9ebb-132">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the Leadspace tile.</span></span>

1. <span data-ttu-id="b9ebb-133">Vyberte položku **Začíname**</span><span class="sxs-lookup"><span data-stu-id="b9ebb-133">Select **Get Started**</span></span> 

1. <span data-ttu-id="b9ebb-134">Zadajte názov pripojenia do boxu **Zobrazovaný názov**.</span><span class="sxs-lookup"><span data-stu-id="b9ebb-134">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="b9ebb-135">Poskytnite platný token Leadspace.</span><span class="sxs-lookup"><span data-stu-id="b9ebb-135">Provide a valid Leadspace token.</span></span>

1. <span data-ttu-id="b9ebb-136">Skontrolujte a poskytnite svoj súhlas pre **Ochrana osobných údajov a dodržiavanie súladu s nariadeniami** označením začiarkavacieho políčka **Súhlasím**.</span><span class="sxs-lookup"><span data-stu-id="b9ebb-136">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox</span></span>

1. <span data-ttu-id="b9ebb-137">Stlačte **Overiť** na overenie konfigurácie.</span><span class="sxs-lookup"><span data-stu-id="b9ebb-137">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="b9ebb-138">Po dokončení overenia stlačte možnosť **Uložiť**.</span><span class="sxs-lookup"><span data-stu-id="b9ebb-138">After completing the verification, select **Save**.</span></span>
   
   :::image type="content" source="media/enrichment-Leadspace-connection.png" alt-text="Konfiguračná stránka pripojenia Leadspace.":::

## <a name="enrichment-results"></a><span data-ttu-id="b9ebb-140">Výsledky obohatenia</span><span class="sxs-lookup"><span data-stu-id="b9ebb-140">Enrichment results</span></span>

<span data-ttu-id="b9ebb-141">Po aktualizácii obohatenia si môžete prezrieť novo obohatené údaje spoločnosti v časti [Moje obohatenia](enrichment-hub.md).</span><span class="sxs-lookup"><span data-stu-id="b9ebb-141">After refreshing the enrichment, you can review the newly enriched company data under [My enrichments](enrichment-hub.md).</span></span> <span data-ttu-id="b9ebb-142">Nájdete čas poslednej aktualizácie a počet obohatených profilov.</span><span class="sxs-lookup"><span data-stu-id="b9ebb-142">You can find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="b9ebb-143">Môžete získať podrobné zobrazenie každého obohateného profilu výberom **Zobraziť obohatené údaje**.</span><span class="sxs-lookup"><span data-stu-id="b9ebb-143">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

<span data-ttu-id="b9ebb-144">Ďalšie informácie sa dozviete v časti [API Leadspace](https://support.leadspace.com/hc/en-us/sections/201997649-API).</span><span class="sxs-lookup"><span data-stu-id="b9ebb-144">For more information, see [Leadspace APIs](https://support.leadspace.com/hc/en-us/sections/201997649-API).</span></span>

## <a name="next-steps"></a><span data-ttu-id="b9ebb-145">Ďalšie kroky</span><span class="sxs-lookup"><span data-stu-id="b9ebb-145">Next steps</span></span>

<span data-ttu-id="b9ebb-146">Stavajte na svojich obohatených údajoch o zákazníkoch.</span><span class="sxs-lookup"><span data-stu-id="b9ebb-146">Build on top of your enriched customer data.</span></span> <span data-ttu-id="b9ebb-147">Vytvárajte [segmenty](segments.md), [miery](measures.md) a dokonca [exportujte údaje](export-destinations.md) na poskytovanie prispôsobenej používateľskej skúsenosti svojim zákazníkom.</span><span class="sxs-lookup"><span data-stu-id="b9ebb-147">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="b9ebb-148">Ochrana osobných údajov a dodržiavanie súladu s nariadeniami</span><span class="sxs-lookup"><span data-stu-id="b9ebb-148">Data privacy and compliance</span></span>

<span data-ttu-id="b9ebb-149">Keď povolíte prenos údajov spoločnosti Leadspace v službe Dynamics 365 Customer Insights, povoľujete tým prenos údajov mimo hranice súladu so službou Dynamics 365 Customer Insights vrátane potenciálne citlivých údajov, ako sú napríklad osobné údaje.</span><span class="sxs-lookup"><span data-stu-id="b9ebb-149">When you enable Dynamics 365 Customer Insights to transmit data to Leadspace, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="b9ebb-150">Spoločnosť Microsoft prenesie tieto údaje na váš pokyn, ale vy ste zodpovední za zabezpečenie toho, aby spoločnosť Leadspace plnila všetky prípadné povinnosti týkajúce sa ochrany vašich osobných údajov alebo zabezpečenia.</span><span class="sxs-lookup"><span data-stu-id="b9ebb-150">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Leadspace meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="b9ebb-151">Ďalšie informácie nájdete vo [vyhlásení o ochrane súkromia spoločnosti Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="b9ebb-151">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="b9ebb-152">Váš správca služby Dynamics 365 Customer Insights môžete kedykoľvek prestať používať odstránením tohto obohatenia.</span><span class="sxs-lookup"><span data-stu-id="b9ebb-152">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
