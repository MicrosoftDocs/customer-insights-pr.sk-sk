---
title: Export údajov služby Customer Insights do Správcu reklám Facebook
description: Prečítajte si, ako nakonfigurovať pripojenie s Správcovi reklám Facebook.
ms.date: 06/05/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: c839f9dc7e403412c0e3d936392d45a43bc63545
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269993"
---
# <a name="connector-for-facebook-ads-manager-preview"></a><span data-ttu-id="aa26e-103">Konektor pre Správcu reklám Facebook (ukážka)</span><span class="sxs-lookup"><span data-stu-id="aa26e-103">Connector for Facebook Ads Manager (preview)</span></span>

<span data-ttu-id="aa26e-104">Export segmentov zjednotených zákazníckych profilov do Správcu reklám Facebook, na ktorom chcete vytvárať kampane na Facebook a Instagram.</span><span class="sxs-lookup"><span data-stu-id="aa26e-104">Export segments of unified customer profiles to Facebook Ads Manager to create campaigns on Facebook and Instagram.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="aa26e-105">Predpoklady</span><span class="sxs-lookup"><span data-stu-id="aa26e-105">Prerequisites</span></span>

- <span data-ttu-id="aa26e-106">Musíte mať [**Reklamný účet Facebook**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account), ktorý zahŕňa [**Firemný účet Facebook**](https://business.facebook.com/) .</span><span class="sxs-lookup"><span data-stu-id="aa26e-106">You need to have a [**Facebook Ad Account**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) which includes a [**Facebook Business Account**](https://business.facebook.com/).</span></span>
- <span data-ttu-id="aa26e-107">Na počítači musíte byť správcom [**Reklamného účtu Facebook**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).</span><span class="sxs-lookup"><span data-stu-id="aa26e-107">You need to be an administrator on the [**Facebook Ad Account**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).</span></span>

## <a name="connect-to-facebook-ads-manager"></a><span data-ttu-id="aa26e-108">Pripojenie k Správcovi reklám Facebook</span><span class="sxs-lookup"><span data-stu-id="aa26e-108">Connect to Facebook Ads Manager</span></span>

1. <span data-ttu-id="aa26e-109">Prejdite do ponuky **Správca** > **Ciele exportu**.</span><span class="sxs-lookup"><span data-stu-id="aa26e-109">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="aa26e-110">Pod Správca reklám **Facebook** vyberte **Nastavenie**.</span><span class="sxs-lookup"><span data-stu-id="aa26e-110">Under **Facebook Ads Manager**, select **Set up**.</span></span>

1. <span data-ttu-id="aa26e-111">Do poľa **Zobrazovaný názov** zadajte rozpoznateľný názov cieľa exportu.</span><span class="sxs-lookup"><span data-stu-id="aa26e-111">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="aa26e-112">Vyberte **Pokračovať s Facebook** a prihláste sa do svojho reklamného účtu Facebook.</span><span class="sxs-lookup"><span data-stu-id="aa26e-112">Select **Continue with Facebook** to sign in to your Facebook Ad Account.</span></span>

1. <span data-ttu-id="aa26e-113">Povoľte povolenie **ads_management** po vykonaní overenia cez Facebook.</span><span class="sxs-lookup"><span data-stu-id="aa26e-113">Allow the **ads_management** permission after authenticating with Facebook.</span></span>

1. <span data-ttu-id="aa26e-114">Zvoľte **Reklamný účet Facebook**, s ktorým chcete pracovať.</span><span class="sxs-lookup"><span data-stu-id="aa26e-114">Select the **Facebook Ads Account** that you want to work with.</span></span>

1. <span data-ttu-id="aa26e-115">Vyberte ikonu **Existujúce vlastné publikum** z rozbaľovacieho zoznamu alebo vytvorte a **Nové vlastné publikum**.</span><span class="sxs-lookup"><span data-stu-id="aa26e-115">Select an **Existing custom audience** from the drop-down list or create a **New custom audience**.</span></span> <span data-ttu-id="aa26e-116">Viac informácií nájdete v časti [**Publiká v Správcovi reklám Facebook**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).</span><span class="sxs-lookup"><span data-stu-id="aa26e-116">For more information, see [**Audiences in Facebook Ads Manager**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).</span></span>

1. <span data-ttu-id="aa26e-117">Vyberte **Súhlasím** na potvrdenie **Ochrany osobných údajov a dodržiavanie súladu s nariadeniami**.</span><span class="sxs-lookup"><span data-stu-id="aa26e-117">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="aa26e-118">Vyberte **Ďalej** a nakonfigurujte export.</span><span class="sxs-lookup"><span data-stu-id="aa26e-118">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="aa26e-119">Nakonfigurujte konektor</span><span class="sxs-lookup"><span data-stu-id="aa26e-119">Configure the connector</span></span>

1. <span data-ttu-id="aa26e-120">V časti **Vyberte pole identifikátora kľúča** vyberte **E-mail**, **Meno a adresa** alebo **Telefón** na odoslanie so Správcu reklám Facebook.</span><span class="sxs-lookup"><span data-stu-id="aa26e-120">In the **Choose your key identifier field**, select **Email**, **Name and address**, or **Phone** to send to Facebook Ads Manager.</span></span>

1. <span data-ttu-id="aa26e-121">Priraďte zodpovedajúce atribúty z vašej zjednotenej entity zákazníka na vybratý identifikátor kľúča.</span><span class="sxs-lookup"><span data-stu-id="aa26e-121">Map the corresponding attributes from your unified customer entity for the selected key identifier.</span></span>
   > <span data-ttu-id="aa26e-122">[TIP] Najlepšie šance na zabezpečenie súladu nastanú, ak vyberiete ako kľúčový identifikátor **E-mail**.</span><span class="sxs-lookup"><span data-stu-id="aa26e-122">[TIP] The best chances for a match occur if you select **Email** as key identifier.</span></span> <span data-ttu-id="aa26e-123">Pridanie ďalších identifikátorov môže zlepšiť zosúladenie.</span><span class="sxs-lookup"><span data-stu-id="aa26e-123">Adding additional identifiers may improve the matching.</span></span>

1. <span data-ttu-id="aa26e-124">Vyberte **Pridať atribút** na mapovanie ďalších atribútov, ktoré sa majú odoslať do Správcu reklám Facebook.</span><span class="sxs-lookup"><span data-stu-id="aa26e-124">Select **Add attribute** to map additional attributes to send to Facebook Ads Manager.</span></span> <span data-ttu-id="aa26e-125">Atribúty zo Správcu reklám Facebook mapujú nasledujúce používateľsky prívetivé mená: **FN** = **Krstné meno**, **LN** = **Priezvisko**, **FI** = **Iniciála krstného mena**, **TELEFÓN** = **Telefón**, **GEN** = **Pohlavie**, **DOB** = **Dátum narodenia**, **ST** = **Štát**, **CT** = **Mesto**, **ZIP** = **PSČ**, **COUNTRY** = **Krajina/región**</span><span class="sxs-lookup"><span data-stu-id="aa26e-125">Attributes from Facebook Ads Manager are mapping to the following user friendly names: **FN** = **First Name**, **LN** = **Last Name**, **FI** = **First Initial**, **PHONE** = **Phone**, **GEN** = **Gender**, **DOB** = **Date of birth**, **ST** = **State**, **CT** = **City**, **ZIP** = **Postal code / Zip code**, **COUNTRY** = **Country / Region**</span></span>

1. <span data-ttu-id="aa26e-126">Vyberte segmenty, ktoré chcete exportovať.</span><span class="sxs-lookup"><span data-stu-id="aa26e-126">Select the segments you want to export.</span></span>

1. <span data-ttu-id="aa26e-127">Vyberte položku **Uložiť**.</span><span class="sxs-lookup"><span data-stu-id="aa26e-127">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="aa26e-128">Export údajov</span><span class="sxs-lookup"><span data-stu-id="aa26e-128">Export the data</span></span>

<span data-ttu-id="aa26e-129">Môžete [exportovať údaje na vyžiadanie](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="aa26e-129">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="aa26e-130">Export sa spustí aj pri každej [plánovanej obnove](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="aa26e-130">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="aa26e-131">Známe obmedzenia</span><span class="sxs-lookup"><span data-stu-id="aa26e-131">Known limitations</span></span>

- <span data-ttu-id="aa26e-132">Až 10 miliónov profilov zákazníkov na jeden export do Správcu reklám Facebook</span><span class="sxs-lookup"><span data-stu-id="aa26e-132">Up to 10 million customer profile per export to Facebook Ads Manager</span></span> 
- <span data-ttu-id="aa26e-133">Export do Správcu reklám Facebook je obmedzený na segmenty</span><span class="sxs-lookup"><span data-stu-id="aa26e-133">Export to Facebook Ads Manager is limited to segments</span></span>
- <span data-ttu-id="aa26e-134">Export segmentov s celkovým počtom 10 miliónov profilov môže trvať až 90 minút</span><span class="sxs-lookup"><span data-stu-id="aa26e-134">Exporting segments with a total of 10 million profiles can take up to 90 minutes to complete</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="aa26e-135">Ochrana osobných údajov a dodržiavanie súladu s nariadeniami</span><span class="sxs-lookup"><span data-stu-id="aa26e-135">Data privacy and compliance</span></span>

<span data-ttu-id="aa26e-136">Keď povolíte prenos údajov do Správcu reklám Facebook v službe Dynamics 365 Customer Insights, povoľujete tým prenos údajov mimo hranice súladu so službou Dynamics 365 Customer Insights vrátane potenciálne citlivých údajov, ako sú napríklad osobné údaje.</span><span class="sxs-lookup"><span data-stu-id="aa26e-136">When you enable Dynamics 365 Customer Insights to transmit data to Facebook Ads Manager, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="aa26e-137">Spoločnosť Microsoft prenesie tieto údaje na váš pokyn, ale vy ste zodpovední za zabezpečenie toho, aby Reklamy Facebook plnili všetky prípadné povinnosti týkajúce sa ochrany vašich osobných údajov alebo zabezpečenia.</span><span class="sxs-lookup"><span data-stu-id="aa26e-137">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Facebook Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="aa26e-138">Ďalšie informácie nájdete vo [vyhlásení o ochrane súkromia spoločnosti Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="aa26e-138">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="aa26e-139">Váš správca služby Dynamics 365 Customer Insights môže túto funkciu kedykoľvek prestať používať odstránením tohto cieľového umiestnenia exportu.</span><span class="sxs-lookup"><span data-stu-id="aa26e-139">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]