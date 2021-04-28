---
title: Export údajov služby Customer Insights do hostiteľov protokolu SFTP
description: Zistite ako nakonfigurovať pripojenie a realizovať exportovanie do umiestnenia SFTP.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 96c6026aded315008439740646827ca910cead90
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760438"
---
# <a name="export-segment-lists-and-other-data-to-sftp-preview"></a><span data-ttu-id="8d208-103">Exportujte zoznamy segmentov a ďalšie údaje do SFTP (ukážka)</span><span class="sxs-lookup"><span data-stu-id="8d208-103">Export segment lists and other data to SFTP (preview)</span></span>

<span data-ttu-id="8d208-104">Použite svoje údaje o zákazníkoch v aplikáciách tretích strán tak, že ich exportujete do umiestnenia Secure File Transfer Protocol (SFTP).</span><span class="sxs-lookup"><span data-stu-id="8d208-104">Use your customer data in third-party applications by exporting them to a Secure File Transfer Protocol (SFTP) location.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="8d208-105">Predpoklad na pripojenie</span><span class="sxs-lookup"><span data-stu-id="8d208-105">Prerequisites for connection</span></span>

- <span data-ttu-id="8d208-106">Dostupnosť hostiteľa SFTP a zodpovedajúcich poverení.</span><span class="sxs-lookup"><span data-stu-id="8d208-106">Availability of an SFTP host and corresponding credentials.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="8d208-107">Známe obmedzenia</span><span class="sxs-lookup"><span data-stu-id="8d208-107">Known limitations</span></span>

- <span data-ttu-id="8d208-108">Čas spustenia exportu závisí od výkonu vášho systému.</span><span class="sxs-lookup"><span data-stu-id="8d208-108">The runtime of an export depends on your system performance.</span></span> <span data-ttu-id="8d208-109">Ako minimálna konfigurácia vášho servera odporúčame dve jadrá CPU a 1 GB pamäte.</span><span class="sxs-lookup"><span data-stu-id="8d208-109">We recommend two CPU cores and 1 Gb of memory as minimal configuration of your server.</span></span> 
- <span data-ttu-id="8d208-110">Export entít s až 100 miliónmi zákazníckych profilov môže trvať 90 minút pri použití odporúčanej minimálnej konfigurácie dvoch jadier CPU a 1 GB pamäte.</span><span class="sxs-lookup"><span data-stu-id="8d208-110">Exporting entities with up to 100 million customer profiles can take 90 minutes when using the recommended minimal configuration of two CPU cores and 1 Gb of memory.</span></span> 

## <a name="set-up-connection-to-sftp"></a><span data-ttu-id="8d208-111">Nastavenie pripojenia k SFTP</span><span class="sxs-lookup"><span data-stu-id="8d208-111">Set up connection to SFTP</span></span>

1. <span data-ttu-id="8d208-112">Prejdite do časti **Správca** > **Pripojenia**.</span><span class="sxs-lookup"><span data-stu-id="8d208-112">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="8d208-113">Stlačte možnosť **Pridať pripojenie** a stlačením možnosti **SFTP** nakonfigurujte pripojenie.</span><span class="sxs-lookup"><span data-stu-id="8d208-113">Select **Add connection** and choose **SFTP** to configure the connection.</span></span>

1. <span data-ttu-id="8d208-114">Do poľa **Zobrazovaný názov** zadajte rozpoznateľný názov pripojenia.</span><span class="sxs-lookup"><span data-stu-id="8d208-114">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="8d208-115">Zobrazovaný názov a typ spojenia, ktoré popisuje toto spojenie.</span><span class="sxs-lookup"><span data-stu-id="8d208-115">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="8d208-116">Odporúčame zvoliť názov, ktorý vysvetľuje účel a cieľ tohto spojenia.</span><span class="sxs-lookup"><span data-stu-id="8d208-116">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="8d208-117">Vyberte používateľov, ktorí môžu používať toto pripojenie.</span><span class="sxs-lookup"><span data-stu-id="8d208-117">Choose who can use this connection.</span></span> <span data-ttu-id="8d208-118">Ak neurobíte nič, predvolená hodnota bude Správcovia.</span><span class="sxs-lookup"><span data-stu-id="8d208-118">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="8d208-119">Viac informácií nájdete v časti [Umožnite prispievateľom použiť pripojenie na export](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="8d208-119">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="8d208-120">Uveďte **Používateľské meno**, **Heslo**, **Meno hostiteľa** a **Priečinok na export** pre váš účet SFTP.</span><span class="sxs-lookup"><span data-stu-id="8d208-120">Provide a **Username**, **Password**, **Hostname**, and **Export folder** for your SFTP account.</span></span>

1. <span data-ttu-id="8d208-121">Na otestovanie pripojenia vyberte **Overiť**.</span><span class="sxs-lookup"><span data-stu-id="8d208-121">Select **Verify** to test the connection.</span></span>

1. <span data-ttu-id="8d208-122">Vyberte, či chcete exportovať svoje údaje **Zbalené** alebo **Rozbalené** a **oddeľovač polí** pre exportované súbory.</span><span class="sxs-lookup"><span data-stu-id="8d208-122">Choose if you want to export your data **Gzipped** or **Unzipped** and the **field delimiter** for the exported files.</span></span>

1. <span data-ttu-id="8d208-123">Vyberte **Súhlasím** na potvrdenie **Ochrany osobných údajov a dodržiavanie súladu s nariadeniami**.</span><span class="sxs-lookup"><span data-stu-id="8d208-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="8d208-124">Stlačte možnosť **Uložiť** a dokončite pripojenie.</span><span class="sxs-lookup"><span data-stu-id="8d208-124">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="8d208-125">Nakonfigurujte export</span><span class="sxs-lookup"><span data-stu-id="8d208-125">Configure an export</span></span>

<span data-ttu-id="8d208-126">Tento export môžete nakonfigurovať, ak máte prístup k pripojeniu tohto typu.</span><span class="sxs-lookup"><span data-stu-id="8d208-126">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="8d208-127">Viac informácií nájdete na stránke [Na konfiguráciu exportu sú potrebné povolenia](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="8d208-127">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="8d208-128">Prejdite na **Údaje** > **Exporty**.</span><span class="sxs-lookup"><span data-stu-id="8d208-128">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="8d208-129">Na vytvorenie nového exportu stlačte možnosť **Pridať cieľ**.</span><span class="sxs-lookup"><span data-stu-id="8d208-129">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="8d208-130">V poli **Pripojenie na export** vyberte pripojenie v časti SFTP.</span><span class="sxs-lookup"><span data-stu-id="8d208-130">In the **Connection for export** field, choose a connection from the SFTP section.</span></span> <span data-ttu-id="8d208-131">Ak nevidíte názov tejto sekcie, nemáte k dispozícii žiadne spojenia tohto typu.</span><span class="sxs-lookup"><span data-stu-id="8d208-131">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="8d208-132">Vyberte entity, napríklad segmenty, ktoré chcete exportovať.</span><span class="sxs-lookup"><span data-stu-id="8d208-132">Select the entities, for example segments, you want to export.</span></span>

   > [!NOTE]
   > <span data-ttu-id="8d208-133">Každá vybraná entita sa pri exportovaní rozdelí až na päť výstupných súborov.</span><span class="sxs-lookup"><span data-stu-id="8d208-133">Each selected entity will be split up into up to five output files when exported.</span></span> 

1. <span data-ttu-id="8d208-134">Vyberte položku **Uložiť**.</span><span class="sxs-lookup"><span data-stu-id="8d208-134">Select **Save**.</span></span>

<span data-ttu-id="8d208-135">Uloženie exportu nespustí export okamžite.</span><span class="sxs-lookup"><span data-stu-id="8d208-135">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="8d208-136">Export prebieha s každým [plánovaným obnovením](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="8d208-136">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="8d208-137">Môžete tiež [exportovať údaje na požiadanie](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="8d208-137">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="8d208-138">Ochrana osobných údajov a dodržiavanie súladu s nariadeniami</span><span class="sxs-lookup"><span data-stu-id="8d208-138">Data privacy and compliance</span></span>

<span data-ttu-id="8d208-139">Keď povolíte prenos údajov spoločnosti SFTP v službe Dynamics 365 Customer Insights, povoľujete tým prenos údajov mimo hranice súladu so službou Dynamics 365 Customer Insights vrátane potenciálne citlivých údajov, ako sú napríklad osobné údaje.</span><span class="sxs-lookup"><span data-stu-id="8d208-139">When you enable Dynamics 365 Customer Insights to transmit data via SFTP, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="8d208-140">Spoločnosť Microsoft prenesie tieto údaje na váš pokyn, ale vy ste zodpovední za zabezpečenie toho, aby cieľ exportu plnil všetky prípadné povinnosti týkajúce sa ochrany vašich osobných údajov alebo zabezpečenia.</span><span class="sxs-lookup"><span data-stu-id="8d208-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that the export destination meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="8d208-141">Ďalšie informácie nájdete vo [vyhlásení o ochrane súkromia spoločnosti Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="8d208-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="8d208-142">Váš správca služby Dynamics 365 Customer Insights môže túto funkciu kedykoľvek prestať používať odstránením tohto cieľového umiestnenia exportu.</span><span class="sxs-lookup"><span data-stu-id="8d208-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
