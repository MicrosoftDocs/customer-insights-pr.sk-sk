---
title: Export údajov z Customer Insights do služby Salesforce Marketing Cloud
description: Zistite, ako nakonfigurovať pripojenie a exportovať do služby Salesforce Marketing Cloud.
ms.date: 06/24/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 123f8b2dbb6140785dec6c1b4164d2f513f66a53
ms.sourcegitcommit: 057079532e31c12bac36f374857ba3dc847d6ad0
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 06/29/2021
ms.locfileid: "6314672"
---
# <a name="export-segments-and-other-data-to-salesforce-marketing-cloud-preview"></a><span data-ttu-id="f4b4c-103">Export segmentov a ďalších údajov do služby Salesforce Marketing Cloud (verzia Preview)</span><span class="sxs-lookup"><span data-stu-id="f4b4c-103">Export segments and other data to Salesforce Marketing Cloud (preview)</span></span>

<span data-ttu-id="f4b4c-104">Použite svoje údaje o zákazníkoch v službe Salesforce Marketing Cloud tým, že ich exportujete prostredníctvom umiestnenia Secure File Transfer Protocol (SFTP).</span><span class="sxs-lookup"><span data-stu-id="f4b4c-104">Use your customer data in Salesforce Marketing Cloud by exporting them through a Secure File Transfer Protocol (SFTP) location.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="f4b4c-105">Predpoklad na pripojenie</span><span class="sxs-lookup"><span data-stu-id="f4b4c-105">Prerequisites for connection</span></span>

- <span data-ttu-id="f4b4c-106">Dostupnosť hostiteľa SFTP a zodpovedajúcich poverení správcu.</span><span class="sxs-lookup"><span data-stu-id="f4b4c-106">Availability of an SFTP host and corresponding admin credentials.</span></span> [<span data-ttu-id="f4b4c-107">Ako nastaviť umiestnenia SFTP pre Salesforce Marketing Cloud</span><span class="sxs-lookup"><span data-stu-id="f4b4c-107">How to setup SFTP locations for Salesforce Marketing Cloud</span></span>](https://help.salesforce.com/articleView?id=sf.mc_es_configure_enhanced_ftp.htm&type=5) 

## <a name="known-limitations"></a><span data-ttu-id="f4b4c-108">Známe obmedzenia</span><span class="sxs-lookup"><span data-stu-id="f4b4c-108">Known limitations</span></span>

- <span data-ttu-id="f4b4c-109">Čas spustenia exportu závisí od výkonu vášho systému.</span><span class="sxs-lookup"><span data-stu-id="f4b4c-109">The runtime of an export depends on your system performance.</span></span> <span data-ttu-id="f4b4c-110">Ako minimálna konfigurácia vášho servera odporúčame dve jadrá CPU a 1 GB pamäte.</span><span class="sxs-lookup"><span data-stu-id="f4b4c-110">We recommend two CPU cores and 1 Gb of memory as minimal configuration of your server.</span></span> 
- <span data-ttu-id="f4b4c-111">Export entít s až 100 miliónmi profilov zákazníkov môže v prípade použitia odporúčanej minimálnej konfigurácie trvať 90 minút.</span><span class="sxs-lookup"><span data-stu-id="f4b4c-111">Exporting entities with up to 100 million customer profiles can take 90 minutes when using the recommended minimal configuration.</span></span> 

## <a name="set-up-the-connection-to-salesforce-marketing-cloud"></a><span data-ttu-id="f4b4c-112">Nastavenie pripojenia k službe Salesforce Marketing Cloud</span><span class="sxs-lookup"><span data-stu-id="f4b4c-112">Set up the connection to Salesforce Marketing Cloud</span></span>

1. <span data-ttu-id="f4b4c-113">Prejdite do časti **Správca** > **Pripojenia**.</span><span class="sxs-lookup"><span data-stu-id="f4b4c-113">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="f4b4c-114">Vyberte možnosť **Pridať pripojenie** a výberom položky **Salesforce Marketing Cloud** nakonfigurujte pripojenie.</span><span class="sxs-lookup"><span data-stu-id="f4b4c-114">Select **Add connection** and choose **Salesforce Marketing Cloud** to configure the connection.</span></span>

1. <span data-ttu-id="f4b4c-115">Do poľa **Zobrazovaný názov** zadajte rozpoznateľný názov pripojenia.</span><span class="sxs-lookup"><span data-stu-id="f4b4c-115">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="f4b4c-116">Zobrazovaný názov a typ spojenia, ktoré popisuje toto spojenie.</span><span class="sxs-lookup"><span data-stu-id="f4b4c-116">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="f4b4c-117">Odporúčame zvoliť názov, ktorý vysvetľuje účel a cieľ tohto spojenia.</span><span class="sxs-lookup"><span data-stu-id="f4b4c-117">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="f4b4c-118">Vyberte používateľov, ktorí môžu používať toto pripojenie.</span><span class="sxs-lookup"><span data-stu-id="f4b4c-118">Choose who can use this connection.</span></span> <span data-ttu-id="f4b4c-119">Ak neurobíte nič, predvolená hodnota bude Správcovia.</span><span class="sxs-lookup"><span data-stu-id="f4b4c-119">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="f4b4c-120">Viac informácií nájdete v časti [Umožnite prispievateľom použiť pripojenie na export](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="f4b4c-120">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="f4b4c-121">Uveďte **Používateľské meno**, **Heslo**, **Meno hostiteľa** a **Priečinok na export** pre váš účet SFTP.</span><span class="sxs-lookup"><span data-stu-id="f4b4c-121">Provide a **Username**, **Password**, **Hostname**, and **Export folder** for your SFTP account.</span></span>

1. <span data-ttu-id="f4b4c-122">Na otestovanie pripojenia vyberte **Overiť**.</span><span class="sxs-lookup"><span data-stu-id="f4b4c-122">Select **Verify** to test the connection.</span></span>

1. <span data-ttu-id="f4b4c-123">Vyberte **Súhlasím** na potvrdenie **Ochrany osobných údajov a dodržiavanie súladu s nariadeniami**.</span><span class="sxs-lookup"><span data-stu-id="f4b4c-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="f4b4c-124">Stlačte možnosť **Uložiť** a dokončite pripojenie.</span><span class="sxs-lookup"><span data-stu-id="f4b4c-124">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="f4b4c-125">Nakonfigurujte export</span><span class="sxs-lookup"><span data-stu-id="f4b4c-125">Configure an export</span></span>

<span data-ttu-id="f4b4c-126">Tento export môžete nakonfigurovať, ak máte prístup k pripojeniu tohto typu.</span><span class="sxs-lookup"><span data-stu-id="f4b4c-126">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="f4b4c-127">Viac informácií nájdete na stránke [Na konfiguráciu exportu sú potrebné povolenia](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="f4b4c-127">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="f4b4c-128">Prejdite na **Údaje** > **Exporty**.</span><span class="sxs-lookup"><span data-stu-id="f4b4c-128">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="f4b4c-129">Na vytvorenie nového exportu stlačte možnosť **Pridať cieľ**.</span><span class="sxs-lookup"><span data-stu-id="f4b4c-129">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="f4b4c-130">V poli **Pripojenie na export** vyberte pripojenie v časti SFTP.</span><span class="sxs-lookup"><span data-stu-id="f4b4c-130">In the **Connection for export** field, choose a connection from the SFTP section.</span></span> <span data-ttu-id="f4b4c-131">Ak nevidíte názov tejto sekcie, nemáte k dispozícii žiadne spojenia tohto typu.</span><span class="sxs-lookup"><span data-stu-id="f4b4c-131">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="f4b4c-132">Vyberte, či chcete exportovať svoje údaje **Zbalené** alebo **Rozbalené** a **oddeľovač polí** pre exportované súbory.</span><span class="sxs-lookup"><span data-stu-id="f4b4c-132">Choose if you want to export your data **Gzipped** or **Unzipped** and the **field delimiter** for the exported files.</span></span>

1. <span data-ttu-id="f4b4c-133">Vyberte entity, napríklad segmenty, ktoré chcete exportovať.</span><span class="sxs-lookup"><span data-stu-id="f4b4c-133">Select the entities, for example segments, you want to export.</span></span>

   > [!NOTE]
   > <span data-ttu-id="f4b4c-134">Každá vybraná entita sa pri exportovaní rozdelí až na päť výstupných súborov.</span><span class="sxs-lookup"><span data-stu-id="f4b4c-134">Each selected entity will be split up into up to five output files when exported.</span></span> 

1. <span data-ttu-id="f4b4c-135">Vyberte položku **Uložiť**.</span><span class="sxs-lookup"><span data-stu-id="f4b4c-135">Select **Save**.</span></span>

<span data-ttu-id="f4b4c-136">Uloženie exportu nespustí export okamžite.</span><span class="sxs-lookup"><span data-stu-id="f4b4c-136">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="f4b4c-137">Export prebieha s každým [plánovaným obnovením](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="f4b4c-137">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="f4b4c-138">Môžete tiež [exportovať údaje na požiadanie](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="f4b4c-138">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="import-customer-insights-data-from-sftp-location-to-salesforce-marketing-cloud"></a><span data-ttu-id="f4b4c-139">Import údajov z Customer Insights z umiestnenia SFTP do služby Salesforce Marketing Cloud</span><span class="sxs-lookup"><span data-stu-id="f4b4c-139">Import Customer Insights data from SFTP location to Salesforce Marketing Cloud</span></span>

1. <span data-ttu-id="f4b4c-140">Vytvárajte [dátové rozšírenia v službe Salesforce Marketing Cloud](https://help.salesforce.com/articleView?id=sf.mc_es_create_data_extension.htm&type=5) na import dátového súboru Customer Insights z umiestnenia SFTP.</span><span class="sxs-lookup"><span data-stu-id="f4b4c-140">Create [data extensions in Salesforce Marketing Cloud](https://help.salesforce.com/articleView?id=sf.mc_es_create_data_extension.htm&type=5) to import the Customer Insights data file from the SFTP location.</span></span>

2. <span data-ttu-id="f4b4c-141">[Importujte údaje z umiestnenia SFTP](https://help.salesforce.com/articleView?id=sf.mc_es_import_data_extension_classic.htm&type=5) do dátového rozšírenia Salesforce Marketing Cloud.</span><span class="sxs-lookup"><span data-stu-id="f4b4c-141">[Import the data from the SFTP location](https://help.salesforce.com/articleView?id=sf.mc_es_import_data_extension_classic.htm&type=5) into the Salesforce Marketing Cloud data extension.</span></span> 

3. <span data-ttu-id="f4b4c-142">Nastavte automatizáciu na import údajov do dátových rozšírení.</span><span class="sxs-lookup"><span data-stu-id="f4b4c-142">Set up the automation to import the data into the data extensions.</span></span> <span data-ttu-id="f4b4c-143">Zistite viac o [automatizácii ukladania súborov a plánovaných automatizáciách](https://help.salesforce.com/articleView?id=sf.mc_as_triggered_automations.htm&type=5).</span><span class="sxs-lookup"><span data-stu-id="f4b4c-143">Learn more about [file drop automations and scheduled automations](https://help.salesforce.com/articleView?id=sf.mc_as_triggered_automations.htm&type=5).</span></span>

   <span data-ttu-id="f4b4c-144">Definujte [automatizáciu ukladania súborov](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_triggered_automation.htm&type=5) alebo [plánovanú automatizáciu](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_scheduled_automation.htm&type=5).</span><span class="sxs-lookup"><span data-stu-id="f4b4c-144">Define a [file drop automation](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_triggered_automation.htm&type=5) or a  [scheduled automation](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_scheduled_automation.htm&type=5).</span></span> 

<span data-ttu-id="f4b4c-145">Tu je príklad [automatizácie pomocou SFTP](https://help.salesforce.com/articleView?id=sf.mc_as_ftp_and_triggered_automation_scenario.htm&type=5).</span><span class="sxs-lookup"><span data-stu-id="f4b4c-145">Here's an example of [an automation with SFTP](https://help.salesforce.com/articleView?id=sf.mc_as_ftp_and_triggered_automation_scenario.htm&type=5).</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="f4b4c-146">Ochrana osobných údajov a dodržiavanie súladu s nariadeniami</span><span class="sxs-lookup"><span data-stu-id="f4b4c-146">Data privacy and compliance</span></span>

<span data-ttu-id="f4b4c-147">Keď povolíte prenos údajov spoločnosti SFTP v službe Dynamics 365 Customer Insights, povoľujete tým prenos údajov mimo hranice súladu so službou Dynamics 365 Customer Insights vrátane potenciálne citlivých údajov, ako sú napríklad osobné údaje.</span><span class="sxs-lookup"><span data-stu-id="f4b4c-147">When you enable Dynamics 365 Customer Insights to transmit data via SFTP, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="f4b4c-148">Spoločnosť Microsoft prenesie tieto údaje na váš pokyn, ale vy ste zodpovední za zabezpečenie toho, aby cieľ exportu plnil všetky prípadné povinnosti týkajúce sa ochrany vašich osobných údajov alebo zabezpečenia.</span><span class="sxs-lookup"><span data-stu-id="f4b4c-148">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that the export destination meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="f4b4c-149">Ďalšie informácie nájdete vo [vyhlásení o ochrane súkromia spoločnosti Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="f4b4c-149">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="f4b4c-150">Váš správca služby Dynamics 365 Customer Insights môže túto funkciu kedykoľvek prestať používať odstránením tohto cieľového umiestnenia exportu.</span><span class="sxs-lookup"><span data-stu-id="f4b4c-150">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
