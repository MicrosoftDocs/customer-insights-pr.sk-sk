---
title: Export údajov služby Customer Insights do úložiska Azure Blob Storage
description: Zistite ako nakonfigurovať pripojenie a realizovať exportovanie do úložiska Blob.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 3c19dc6d4956a33a5bd3cea706f8a154198d487f
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976200"
---
# <a name="export-segment-list-and-other-data-to-azure-blob-storage-preview"></a><span data-ttu-id="aeefc-103">Exportujte zoznam segmentov a ďalšie údaje do Azure Blob Storage (ukážka)</span><span class="sxs-lookup"><span data-stu-id="aeefc-103">Export segment list and other data to Azure Blob Storage (preview)</span></span>

<span data-ttu-id="aeefc-104">Uložte si údaje zo služby Customer Insights do služby Blob alebo ju použite na prenos údajov do iných aplikácií.</span><span class="sxs-lookup"><span data-stu-id="aeefc-104">Store your Customer Insights data in a Blob storage or use it to transfer your data to other applications.</span></span>

## <a name="set-up-the-connection-to-blob-storage"></a><span data-ttu-id="aeefc-105">Príprava pripojenia do úložiska Blob</span><span class="sxs-lookup"><span data-stu-id="aeefc-105">Set up the connection to Blob storage</span></span>

1. <span data-ttu-id="aeefc-106">Prejdite do časti **Správca** > **Pripojenia**.</span><span class="sxs-lookup"><span data-stu-id="aeefc-106">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="aeefc-107">Stlačte možnosť **Pridať pripojenie** a stlačením možnosti **úložiska Azure Blob** nakonfigurujte pripojenie.</span><span class="sxs-lookup"><span data-stu-id="aeefc-107">Select **Add connection** and choose **Azure Blob Storage** to configure the connection.</span></span>

1. <span data-ttu-id="aeefc-108">Do poľa **Zobrazovaný názov** zadajte rozpoznateľný názov pripojenia.</span><span class="sxs-lookup"><span data-stu-id="aeefc-108">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="aeefc-109">Zobrazovaný názov a typ spojenia, ktoré popisuje toto spojenie.</span><span class="sxs-lookup"><span data-stu-id="aeefc-109">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="aeefc-110">Odporúčame zvoliť názov, ktorý vysvetľuje účel a cieľ tohto spojenia.</span><span class="sxs-lookup"><span data-stu-id="aeefc-110">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="aeefc-111">Vyberte používateľov, ktorí môžu používať toto pripojenie.</span><span class="sxs-lookup"><span data-stu-id="aeefc-111">Choose who can use this connection.</span></span> <span data-ttu-id="aeefc-112">Ak neurobíte nič, predvolená hodnota bude Správcovia.</span><span class="sxs-lookup"><span data-stu-id="aeefc-112">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="aeefc-113">Viac informácií nájdete v časti [Umožnite prispievateľom použiť pripojenie na export](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="aeefc-113">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="aeefc-114">Zadajte **Názov účtu**, **Kľúč účtu** a **Kontajner** pre váš účet úložiska Blob.</span><span class="sxs-lookup"><span data-stu-id="aeefc-114">Enter **Account name**, **Account key**, and **Container** for your Blob storage account.</span></span>
    - <span data-ttu-id="aeefc-115">Ak sa chcete dozvedieť viac o názve a kľúči účtu úložiska Blob, prečítajte si časť [Správa nastavení účtu v portáli Azure](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="aeefc-115">To learn more about how to find the Blob storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>
    - <span data-ttu-id="aeefc-116">Informácie o tom, ako vytvoriť kontajner, nájdete v časti [Vytvorenie kontajnera](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span><span class="sxs-lookup"><span data-stu-id="aeefc-116">To learn how to create a container, see [Create a container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span></span>

1. <span data-ttu-id="aeefc-117">Stlačte možnosť **Uložiť** a dokončite pripojenie.</span><span class="sxs-lookup"><span data-stu-id="aeefc-117">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="aeefc-118">Nakonfigurujte export</span><span class="sxs-lookup"><span data-stu-id="aeefc-118">Configure an export</span></span>

<span data-ttu-id="aeefc-119">Tento export môžete nakonfigurovať, ak máte prístup k pripojeniu tohto typu.</span><span class="sxs-lookup"><span data-stu-id="aeefc-119">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="aeefc-120">Viac informácií nájdete na stránke [Na konfiguráciu exportu sú potrebné povolenia](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="aeefc-120">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="aeefc-121">Prejdite na **Údaje** > **Exporty**.</span><span class="sxs-lookup"><span data-stu-id="aeefc-121">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="aeefc-122">Na vytvorenie nového exportu stlačte možnosť **Pridať cieľ**.</span><span class="sxs-lookup"><span data-stu-id="aeefc-122">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="aeefc-123">V poli **Pripojenie na export** vyberte pripojenie v časti úložiska Azure Blob.</span><span class="sxs-lookup"><span data-stu-id="aeefc-123">In the **Connection for export** field, choose a connection from the Azure Blob Storage section.</span></span> <span data-ttu-id="aeefc-124">Ak nevidíte názov tejto sekcie, nemáte k dispozícii žiadne spojenia tohto typu.</span><span class="sxs-lookup"><span data-stu-id="aeefc-124">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="aeefc-125">Vyberte si políčko vedľa každej entity, ktorú chcete exportovať do tohto cieľa.</span><span class="sxs-lookup"><span data-stu-id="aeefc-125">Select the box next to each of the entities you want to export to this destination.</span></span>

1. <span data-ttu-id="aeefc-126">Vyberte položku **Uložiť**.</span><span class="sxs-lookup"><span data-stu-id="aeefc-126">Select **Save**.</span></span>

<span data-ttu-id="aeefc-127">Uloženie exportu nespustí export okamžite.</span><span class="sxs-lookup"><span data-stu-id="aeefc-127">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="aeefc-128">Export prebieha s každým [plánovaným obnovením](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="aeefc-128">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span>     
<span data-ttu-id="aeefc-129">Môžete tiež [exportovať údaje na požiadanie](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="aeefc-129">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

<span data-ttu-id="aeefc-130">Exportované údaje sú uložené v kontajneri úložiska Blob, ktorý ste nakonfigurovali.</span><span class="sxs-lookup"><span data-stu-id="aeefc-130">Exported data is stored in the Blob storage container you configured.</span></span> <span data-ttu-id="aeefc-131">Vo vašom kontajneri sa automaticky vytvoria nasledujúce cesty k priečinkom:</span><span class="sxs-lookup"><span data-stu-id="aeefc-131">The following folder paths are automatically created in your container:</span></span>

- <span data-ttu-id="aeefc-132">Pre zdrojové entity a entity generované systémom: `%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv`</span><span class="sxs-lookup"><span data-stu-id="aeefc-132">For source entities and entities generated by the system: `%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv`</span></span>
  - <span data-ttu-id="aeefc-133">Príklad: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv`</span><span class="sxs-lookup"><span data-stu-id="aeefc-133">Example: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv`</span></span>
- <span data-ttu-id="aeefc-134">Model.json pre exportované entity bude na úrovni %ExportDestinationName%</span><span class="sxs-lookup"><span data-stu-id="aeefc-134">The model.json for the exported entities will be at the %ExportDestinationName% level</span></span>
  - <span data-ttu-id="aeefc-135">Príklad: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json`</span><span class="sxs-lookup"><span data-stu-id="aeefc-135">Example: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json`</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
