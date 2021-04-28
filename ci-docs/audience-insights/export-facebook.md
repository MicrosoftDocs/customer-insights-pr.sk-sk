---
title: Export údajov služby Customer Insights do Správcu reklám Facebook
description: Zistite ako nakonfigurovať pripojenie a realizovať exportovanie do Facebook Ads Manager.
ms.date: 04/15/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: ca32906a98bc734639fb369d6f5a92e8888fd850
ms.sourcegitcommit: 6d5dd572f75ba4c0303ec77c3b74e4318d52705c
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 04/16/2021
ms.locfileid: "5906829"
---
# <a name="export-segments-list-to-facebook-ads-manager-preview"></a><span data-ttu-id="d1760-103">Export zoznamu segmentov do Facebook Ads Manager (verzia Preview)</span><span class="sxs-lookup"><span data-stu-id="d1760-103">Export segments list to Facebook Ads Manager (preview)</span></span>

<span data-ttu-id="d1760-104">Export segmentov zjednotených zákazníckych profilov do Správcu reklám Facebook, na ktorom chcete vytvárať kampane na Facebook a Instagram.</span><span class="sxs-lookup"><span data-stu-id="d1760-104">Export segments of unified customer profiles to Facebook Ads Manager to create campaigns on Facebook and Instagram.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="d1760-105">Predpoklad na pripojenie</span><span class="sxs-lookup"><span data-stu-id="d1760-105">Prerequisites for connection</span></span>

- <span data-ttu-id="d1760-106">Musíte mať [konto **Facebook Ad**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account), ktoré zahŕňa [Obchodné konto **Facebook**](https://business.facebook.com/).</span><span class="sxs-lookup"><span data-stu-id="d1760-106">You need to have a [**Facebook Ad Account**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) that includes a [**Facebook Business Account**](https://business.facebook.com/).</span></span>
- <span data-ttu-id="d1760-107">Na počítači musíte byť správcom [**Reklamného účtu Facebook**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).</span><span class="sxs-lookup"><span data-stu-id="d1760-107">You need to be an administrator on the [**Facebook Ad Account**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="d1760-108">Známe obmedzenia</span><span class="sxs-lookup"><span data-stu-id="d1760-108">Known limitations</span></span>

- <span data-ttu-id="d1760-109">Až 10 miliónov profilov zákazníkov na jeden export do Facebook Ads Manager.</span><span class="sxs-lookup"><span data-stu-id="d1760-109">Up to 10 million customer profile per export to Facebook Ads Manager.</span></span>
- <span data-ttu-id="d1760-110">Export do Facebook Ads Manager je obmedzený na segmenty.</span><span class="sxs-lookup"><span data-stu-id="d1760-110">Export to Facebook Ads Manager is limited to segments.</span></span>
- <span data-ttu-id="d1760-111">Vytvárajte alebo aktualizujte iba vlastné cieľové skupiny v službe Facebook typu *zoznam zákazníkov*.</span><span class="sxs-lookup"><span data-stu-id="d1760-111">Create or update custom audiences in Facebook of type *customer list* only.</span></span>
- <span data-ttu-id="d1760-112">Export segmentov s celkovým počtom 10 miliónov profilov môže trvať až 90 minút.</span><span class="sxs-lookup"><span data-stu-id="d1760-112">Exporting segments with a total of 10 million profiles can take up to 90 minutes to complete.</span></span>

## <a name="set-up-connection-to-facebook-ads-manager"></a><span data-ttu-id="d1760-113">Nastavenie pripojenia do Facebook Ads Manager</span><span class="sxs-lookup"><span data-stu-id="d1760-113">Set up connection to Facebook Ads Manager</span></span>

<span data-ttu-id="d1760-114">Predtým, ako budú môcť používatelia vytvoriť export, musí správca nakonfigurovať pripojenie k službe a umožniť prispievateľom používať pripojenie.</span><span class="sxs-lookup"><span data-stu-id="d1760-114">Before users can create an export, an administrator must configure the connection to the service and allow contributors to use the connection.</span></span>

1. <span data-ttu-id="d1760-115">Prejdite do časti **Správca** > **Pripojenia**.</span><span class="sxs-lookup"><span data-stu-id="d1760-115">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="d1760-116">Stlačte možnosť **Pridať pripojenie** a stlačením možnosti **Facebook Google Ads** nakonfigurujte pripojenie.</span><span class="sxs-lookup"><span data-stu-id="d1760-116">Select **Add connection** and choose **Facebook Ads Manager** to configure the connection.</span></span>

1. <span data-ttu-id="d1760-117">Do poľa **Zobrazovaný názov** zadajte rozpoznateľný názov pripojenia.</span><span class="sxs-lookup"><span data-stu-id="d1760-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="d1760-118">Zobrazovaný názov a typ spojenia, ktoré popisuje toto spojenie.</span><span class="sxs-lookup"><span data-stu-id="d1760-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="d1760-119">Odporúčame zvoliť názov, ktorý vysvetľuje účel a cieľ tohto spojenia.</span><span class="sxs-lookup"><span data-stu-id="d1760-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="d1760-120">Vyberte používateľov, ktorí môžu používať toto pripojenie.</span><span class="sxs-lookup"><span data-stu-id="d1760-120">Choose who can use this connection.</span></span> <span data-ttu-id="d1760-121">Ak neurobíte nič, predvolená hodnota bude **Správcovia**.</span><span class="sxs-lookup"><span data-stu-id="d1760-121">If you take no action, the default will be **Administrators**.</span></span> <span data-ttu-id="d1760-122">Viac informácií nájdete v časti [Umožnite prispievateľom použiť pripojenie na export](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="d1760-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="d1760-123">Overenie pomocou služby Facebook Ads:</span><span class="sxs-lookup"><span data-stu-id="d1760-123">Authenticate with Facebook Ads:</span></span> 

   1. <span data-ttu-id="d1760-124">Vyberte **Pokračovať s Facebook** a prihláste sa do svojho reklamného účtu Facebook.</span><span class="sxs-lookup"><span data-stu-id="d1760-124">Select **Continue with Facebook** to sign in to your Facebook Ad Account.</span></span>

   1. <span data-ttu-id="d1760-125">Povoľte povolenie **ads_management** po vykonaní overenia cez Facebook.</span><span class="sxs-lookup"><span data-stu-id="d1760-125">Allow the **ads_management** permission after authenticating with Facebook.</span></span>

   1. <span data-ttu-id="d1760-126">Zvoľte **Reklamný účet Facebook**, s ktorým chcete pracovať.</span><span class="sxs-lookup"><span data-stu-id="d1760-126">Select the **Facebook Ads Account** that you want to work with.</span></span>

   1. <span data-ttu-id="d1760-127">Vyberte ikonu **Existujúce vlastné publikum** z rozbaľovacieho zoznamu alebo vytvorte a **Nové vlastné publikum**.</span><span class="sxs-lookup"><span data-stu-id="d1760-127">Select an **Existing custom audience** from the drop-down list or create a **New custom audience**.</span></span> <span data-ttu-id="d1760-128">Viac informácií nájdete v časti [**Publiká v Správcovi reklám Facebook**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).</span><span class="sxs-lookup"><span data-stu-id="d1760-128">For more information, see [**Audiences in Facebook Ads Manager**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).</span></span>
      > [!NOTE]
      > <span data-ttu-id="d1760-129">Vlastné publiká môžete vytvárať alebo aktualizovať iba v službe Facebook typu *zoznam zákazníkov* s týmto exportom.</span><span class="sxs-lookup"><span data-stu-id="d1760-129">You can only create or update custom audiences on Facebook of the type *customer list* with this export.</span></span> <span data-ttu-id="d1760-130">V niektorých prípadoch sa v rozbaľovacom zozname zobrazia cieľové skupiny rôznych typov.</span><span class="sxs-lookup"><span data-stu-id="d1760-130">In some cases, you see custom audiences of different types in the drop-down list.</span></span> <span data-ttu-id="d1760-131">Výber iného typu *zoznamu zákazníkov* bude mať za následok zlyhanie exportu.</span><span class="sxs-lookup"><span data-stu-id="d1760-131">Selecting a different type than *customer list* will result in a failing export.</span></span> 

1. <span data-ttu-id="d1760-132">Prečítajte si časť **Ochrana osobných údajov a ich dodržiavanie** a stlačte možnosť **Súhlasím**.</span><span class="sxs-lookup"><span data-stu-id="d1760-132">Review the **Data privacy and compliance** and select **I agree**.</span></span>

1. <span data-ttu-id="d1760-133">Stlačte možnosť **Uložiť** a dokončite pripojenie.</span><span class="sxs-lookup"><span data-stu-id="d1760-133">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="d1760-134">Nakonfigurujte export</span><span class="sxs-lookup"><span data-stu-id="d1760-134">Configure an export</span></span>

<span data-ttu-id="d1760-135">Tento export môžete nakonfigurovať, ak máte prístup k pripojeniu tohto typu.</span><span class="sxs-lookup"><span data-stu-id="d1760-135">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="d1760-136">Viac informácií nájdete na stránke [Na konfiguráciu exportu sú potrebné povolenia](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="d1760-136">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="d1760-137">Prejdite na **Údaje** > **Exporty**.</span><span class="sxs-lookup"><span data-stu-id="d1760-137">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="d1760-138">Na vytvorenie nového exportu stlačte možnosť **Pridať cieľ**.</span><span class="sxs-lookup"><span data-stu-id="d1760-138">To create a new export, select **Add destination**.</span></span> 

1. <span data-ttu-id="d1760-139">V poli **Pripojenie na export** vyberte pripojenie v časti **Facebook Ads Manager**.</span><span class="sxs-lookup"><span data-stu-id="d1760-139">In **Connection for export** choose a connection from the **Facebook Ads Manager** section.</span></span> <span data-ttu-id="d1760-140">Ak nevidíte názov tejto sekcie, nemáte k dispozícii žiadne spojenia tohto typu.</span><span class="sxs-lookup"><span data-stu-id="d1760-140">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="d1760-141">V časti **Vyberte pole identifikátora kľúča** vyberte **E-mail**, **Meno a adresa** alebo **Telefón** na odoslanie so Správcu reklám Facebook.</span><span class="sxs-lookup"><span data-stu-id="d1760-141">In the **Choose your key identifier field**, select **Email**, **Name and address**, or **Phone** to send to Facebook Ads Manager.</span></span> 

1. <span data-ttu-id="d1760-142">Do poľa **Zobrazovaný názov** zadajte rozpoznateľný názov pripojenia.</span><span class="sxs-lookup"><span data-stu-id="d1760-142">Give your connection a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="d1760-143">Priraďte zodpovedajúce atribúty z vašej zjednotenej entity zákazníka na vybratý identifikátor kľúča.</span><span class="sxs-lookup"><span data-stu-id="d1760-143">Map the corresponding attributes from your unified customer entity for the selected key identifier.</span></span>
   > <span data-ttu-id="d1760-144">[TIP] Najlepšie šance na zabezpečenie súladu nastanú, ak vyberiete ako kľúčový identifikátor **E-mail**.</span><span class="sxs-lookup"><span data-stu-id="d1760-144">[TIP] The best chances for a match occur if you select **Email** as key identifier.</span></span> <span data-ttu-id="d1760-145">Pridanie ďalších identifikátorov môže zlepšiť zosúladenie.</span><span class="sxs-lookup"><span data-stu-id="d1760-145">Adding additional identifiers may improve the matching.</span></span>

1. <span data-ttu-id="d1760-146">Vyberte **Pridať atribút** na mapovanie ďalších atribútov na odoslanie do Facebook Ads Manager.</span><span class="sxs-lookup"><span data-stu-id="d1760-146">Select **Add attribute** to map more attributes to send to Facebook Ads Manager.</span></span> <span data-ttu-id="d1760-147">Atribúty z Facebook Ads Manager sú mapované pomocou nasledovných používateľských názvov: **FN** = **Krstné meno**, **LN** = **Priezvisko**, **FI** = **Prvé písmeno**, **PHONE** = **Telefón**, **GEN** = **Pohlavie**, **DOB** = **Dátum narodenia**, **ST** = **Stav**, **CT** = **Mesto**, **ZIP** = **PSČ**, **COUNTRY** = **Krajina/oblasť**</span><span class="sxs-lookup"><span data-stu-id="d1760-147">Attributes from Facebook Ads Manager are mapping to the following user-friendly names: **FN** = **First Name**, **LN** = **Last Name**, **FI** = **First Initial**, **PHONE** = **Phone**, **GEN** = **Gender**, **DOB** = **Date of birth**, **ST** = **State**, **CT** = **City**, **ZIP** = **Postal code / Zip code**, **COUNTRY** = **Country / Region**</span></span>

1. <span data-ttu-id="d1760-148">Vyberte segmenty, ktoré chcete exportovať.</span><span class="sxs-lookup"><span data-stu-id="d1760-148">Select the segments you want to export.</span></span>

1. <span data-ttu-id="d1760-149">Vyberte položku **Uložiť**.</span><span class="sxs-lookup"><span data-stu-id="d1760-149">Select **Save**.</span></span>

<span data-ttu-id="d1760-150">Uloženie exportu nespustí export okamžite.</span><span class="sxs-lookup"><span data-stu-id="d1760-150">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="d1760-151">Export prebieha s každým [plánovaným obnovením](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="d1760-151">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="d1760-152">Môžete tiež [exportovať údaje na požiadanie](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="d1760-152">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="d1760-153">Ochrana osobných údajov a dodržiavanie súladu s nariadeniami</span><span class="sxs-lookup"><span data-stu-id="d1760-153">Data privacy and compliance</span></span>

<span data-ttu-id="d1760-154">Keď povolíte prenos údajov do Správcu reklám Facebook v službe Dynamics 365 Customer Insights, povoľujete tým prenos údajov mimo hranice súladu so službou Dynamics 365 Customer Insights vrátane potenciálne citlivých údajov, ako sú napríklad osobné údaje.</span><span class="sxs-lookup"><span data-stu-id="d1760-154">When you enable Dynamics 365 Customer Insights to transmit data to Facebook Ads Manager, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="d1760-155">Spoločnosť Microsoft prenesie tieto údaje na váš pokyn, ale vy ste zodpovední za zabezpečenie toho, aby Reklamy Facebook plnili všetky prípadné povinnosti týkajúce sa ochrany vašich osobných údajov alebo zabezpečenia.</span><span class="sxs-lookup"><span data-stu-id="d1760-155">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Facebook Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="d1760-156">Ďalšie informácie nájdete vo [vyhlásení o ochrane súkromia spoločnosti Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="d1760-156">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="d1760-157">Váš správca služby Dynamics 365 Customer Insights môže túto funkciu kedykoľvek prestať používať odstránením tohto cieľového umiestnenia exportu.</span><span class="sxs-lookup"><span data-stu-id="d1760-157">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
