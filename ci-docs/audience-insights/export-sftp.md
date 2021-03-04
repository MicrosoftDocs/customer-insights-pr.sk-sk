---
title: Export údajov služby Customer Insights do hostiteľov protokolu SFTP
description: Prečítajte si, ako nakonfigurovať pripojenie k hostiteľovi SFTP.
ms.date: 01/27/2021
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: ddba55b3ca159c0095371e46385dcf1d3ed4a63d
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268017"
---
# <a name="connector-for-sftp-preview"></a><span data-ttu-id="a64cd-103">Konektor pre SFTP (ukážka)</span><span class="sxs-lookup"><span data-stu-id="a64cd-103">Connector for SFTP (preview)</span></span>

<span data-ttu-id="a64cd-104">Používajte svoje zákaznícke údaje v aplikáciách tretích strán tak, že ich bezpečne exportujete do hostiteľa protokolu SFTP (Secure File Transfer Protocol).</span><span class="sxs-lookup"><span data-stu-id="a64cd-104">Use your customer data in third-party applications by exporting them to a Secure File Transfer Protocol (SFTP) host.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="a64cd-105">Predpoklady</span><span class="sxs-lookup"><span data-stu-id="a64cd-105">Prerequisites</span></span>

- <span data-ttu-id="a64cd-106">Dostupnosť hostiteľa SFTP a zodpovedajúcich poverení.</span><span class="sxs-lookup"><span data-stu-id="a64cd-106">Availability of an SFTP host and corresponding credentials.</span></span>

## <a name="connect-to-sftp"></a><span data-ttu-id="a64cd-107">Pripojenie k SFTP</span><span class="sxs-lookup"><span data-stu-id="a64cd-107">Connect to SFTP</span></span>

1. <span data-ttu-id="a64cd-108">Prejdite do ponuky **Správca** > **Ciele exportu**.</span><span class="sxs-lookup"><span data-stu-id="a64cd-108">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="a64cd-109">Pod **SFTP** vyberte **Nastavenie**.</span><span class="sxs-lookup"><span data-stu-id="a64cd-109">Under **SFTP**, select **Set up**.</span></span>

1. <span data-ttu-id="a64cd-110">Do poľa **Zobrazovaný názov** zadajte rozpoznateľný názov cieľa.</span><span class="sxs-lookup"><span data-stu-id="a64cd-110">Give your destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="a64cd-111">Uveďte **Používateľské meno**, **Heslo**, **Meno hostiteľa** a **Priečinok na export** pre váš účet SFTP.</span><span class="sxs-lookup"><span data-stu-id="a64cd-111">Provide a **Username**, **Password**, **Hostname**, and **Export folder** for your SFTP account.</span></span>

1. <span data-ttu-id="a64cd-112">Na otestovanie pripojenia vyberte **Overiť**.</span><span class="sxs-lookup"><span data-stu-id="a64cd-112">Select **Verify** to test the connection.</span></span>

1. <span data-ttu-id="a64cd-113">Po úspešnom overení vyberte, či chcete exportovať svoje údaje **Komprimované ako gzip** alebo **Dekomprimované** a vyberte **oddeľovač polí** pre exportované súbory.</span><span class="sxs-lookup"><span data-stu-id="a64cd-113">After successful verification, choose if you want to export your data **Gzipped** or **Unzipped**, and select the **field delimiter** for the exported files.</span></span>

1. <span data-ttu-id="a64cd-114">Vyberte **Súhlasím** na potvrdenie **Ochrany osobných údajov a dodržiavanie súladu s nariadeniami**.</span><span class="sxs-lookup"><span data-stu-id="a64cd-114">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="a64cd-115">Vyberte **Ďalej** a začnite konfigurovať export.</span><span class="sxs-lookup"><span data-stu-id="a64cd-115">Select **Next** to start configuring the export.</span></span>

## <a name="configure-the-export"></a><span data-ttu-id="a64cd-116">Konfigurácia exportu</span><span class="sxs-lookup"><span data-stu-id="a64cd-116">Configure the export</span></span>

1. <span data-ttu-id="a64cd-117">Vyberte entity, napríklad segmenty, ktoré chcete exportovať.</span><span class="sxs-lookup"><span data-stu-id="a64cd-117">Select the entities, for example segments, you want to export.</span></span>

   > [!NOTE]
   > <span data-ttu-id="a64cd-118">Každá vybraná entita bude mať pri exporte až päť výstupných súborov.</span><span class="sxs-lookup"><span data-stu-id="a64cd-118">Each selected entity will be up to five output files when exported.</span></span> 

1. <span data-ttu-id="a64cd-119">Vyberte položku **Uložiť**.</span><span class="sxs-lookup"><span data-stu-id="a64cd-119">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="a64cd-120">Export údajov</span><span class="sxs-lookup"><span data-stu-id="a64cd-120">Export the data</span></span>

<span data-ttu-id="a64cd-121">Môžete [exportovať údaje na vyžiadanie](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="a64cd-121">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="a64cd-122">Export sa spustí aj pri každej [plánovanej obnove](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="a64cd-122">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="a64cd-123">Známe obmedzenia</span><span class="sxs-lookup"><span data-stu-id="a64cd-123">Known limitations</span></span>

- <span data-ttu-id="a64cd-124">Čas spustenia exportu závisí od výkonu vášho systému.</span><span class="sxs-lookup"><span data-stu-id="a64cd-124">The runtime of an export depends on your system performance.</span></span> <span data-ttu-id="a64cd-125">Ako minimálna konfigurácia vášho servera odporúčame dve jadrá CPU a 1 GB pamäte.</span><span class="sxs-lookup"><span data-stu-id="a64cd-125">We recommend two CPU cores and 1 Gb of memory as minimal configuration of your server.</span></span> 
- <span data-ttu-id="a64cd-126">Export entít s až 100 miliónmi zákazníckych profilov môže trvať 90 minút pri použití odporúčanej minimálnej konfigurácie dvoch jadier CPU a 1 GB pamäte.</span><span class="sxs-lookup"><span data-stu-id="a64cd-126">Exporting entities with up to 100 million customer profiles can take 90 minutes when using the recommended minimal configuration of two CPU cores and 1 Gb of memory.</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="a64cd-127">Ochrana osobných údajov a dodržiavanie súladu s nariadeniami</span><span class="sxs-lookup"><span data-stu-id="a64cd-127">Data privacy and compliance</span></span>

<span data-ttu-id="a64cd-128">Keď povolíte prenos údajov spoločnosti SFTP v službe Dynamics 365 Customer Insights, povoľujete tým prenos údajov mimo hranice súladu so službou Dynamics 365 Customer Insights vrátane potenciálne citlivých údajov, ako sú napríklad osobné údaje.</span><span class="sxs-lookup"><span data-stu-id="a64cd-128">When you enable Dynamics 365 Customer Insights to transmit data via SFTP, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="a64cd-129">Spoločnosť Microsoft prenesie tieto údaje na váš pokyn, ale vy ste zodpovední za zabezpečenie toho, aby cieľ exportu plnil všetky prípadné povinnosti týkajúce sa ochrany vašich osobných údajov alebo zabezpečenia.</span><span class="sxs-lookup"><span data-stu-id="a64cd-129">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that the export destination meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="a64cd-130">Ďalšie informácie nájdete vo [vyhlásení o ochrane súkromia spoločnosti Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="a64cd-130">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="a64cd-131">Váš správca služby Dynamics 365 Customer Insights môže túto funkciu kedykoľvek prestať používať odstránením tohto cieľového umiestnenia exportu.</span><span class="sxs-lookup"><span data-stu-id="a64cd-131">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]