---
title: Export údajov služby Customer Insights Azure Data Lake Storage Gen2
description: Zistite, ako môžete nakonfigurovať pripojenie k Azure Data Lake Storage Gen2.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: f431b707e1d65ffe47f8b3aa1c52abaa964e871a
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760070"
---
# <a name="set-up-the-connection-to-azure-data-lake-storage-gen2-preview"></a><span data-ttu-id="e0e56-103">Nastaviť pripojenie k Azure Data Lake Storage Gen2 (ukážka)</span><span class="sxs-lookup"><span data-stu-id="e0e56-103">Set up the connection to Azure Data Lake Storage Gen2 (preview)</span></span>

1. <span data-ttu-id="e0e56-104">Prejdite do časti **Správca** > **Pripojenia**.</span><span class="sxs-lookup"><span data-stu-id="e0e56-104">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="e0e56-105">Stlačte možnosť **Pridať pripojenie** a stlačením možnosti **Azure Data Lake Gen 2** nakonfigurujte pripojenie.</span><span class="sxs-lookup"><span data-stu-id="e0e56-105">Select **Add connection** and choose **Azure Data Lake Gen 2** to configure the connection.</span></span>

1. <span data-ttu-id="e0e56-106">Do poľa **Zobrazovaný názov** zadajte rozpoznateľný názov pripojenia.</span><span class="sxs-lookup"><span data-stu-id="e0e56-106">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="e0e56-107">Zobrazovaný názov a typ spojenia, ktoré popisuje toto spojenie.</span><span class="sxs-lookup"><span data-stu-id="e0e56-107">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="e0e56-108">Odporúčame zvoliť názov, ktorý vysvetľuje účel a cieľ tohto spojenia.</span><span class="sxs-lookup"><span data-stu-id="e0e56-108">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="e0e56-109">Vyberte používateľov, ktorí môžu používať toto pripojenie.</span><span class="sxs-lookup"><span data-stu-id="e0e56-109">Choose who can use this connection.</span></span> <span data-ttu-id="e0e56-110">Ak neurobíte nič, predvolená hodnota bude Správcovia.</span><span class="sxs-lookup"><span data-stu-id="e0e56-110">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="e0e56-111">Viac informácií nájdete v časti [Umožnite prispievateľom použiť pripojenie na export](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="e0e56-111">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="e0e56-112">Zadajte **Názov účtu**, **Kľúč účtu** a **Kontajner** pre svoje Azure Data Lake Storage Gen2.</span><span class="sxs-lookup"><span data-stu-id="e0e56-112">Enter **Account name**, **Account key**, and **Container** for your Azure Data Lake Storage Gen2.</span></span>
    - <span data-ttu-id="e0e56-113">Naučte sa, ako vytvoriť účet úložiska na použitie s Azure Data Lake Storage Gen2, pozri [Vytvorte si účet úložiska](/azure/storage/blobs/create-data-lake-storage-account).</span><span class="sxs-lookup"><span data-stu-id="e0e56-113">To learn how to create a storage account to use with Azure Data Lake Storage Gen2, see [Create storage account](/azure/storage/blobs/create-data-lake-storage-account).</span></span> 
    - <span data-ttu-id="e0e56-114">Ak sa chcete dozvedieť viac o názve a kľúči účtu úložiska Azure Data Lake Gen2, prečítajte si časť [Správa nastavení účtu v portáli Azure](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="e0e56-114">To learn more about Azure Data Lake Gen2 storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>

1. <span data-ttu-id="e0e56-115">Stlačte možnosť **Uložiť** a dokončite pripojenie.</span><span class="sxs-lookup"><span data-stu-id="e0e56-115">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="e0e56-116">Nakonfigurujte export</span><span class="sxs-lookup"><span data-stu-id="e0e56-116">Configure an export</span></span>

<span data-ttu-id="e0e56-117">Tento export môžete nakonfigurovať, ak máte prístup k pripojeniu tohto typu.</span><span class="sxs-lookup"><span data-stu-id="e0e56-117">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="e0e56-118">Viac informácií nájdete na stránke [Na konfiguráciu exportu sú potrebné povolenia](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="e0e56-118">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="e0e56-119">Prejdite na **Údaje** > **Exporty**.</span><span class="sxs-lookup"><span data-stu-id="e0e56-119">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="e0e56-120">Na vytvorenie nového exportu stlačte možnosť **Pridať export**.</span><span class="sxs-lookup"><span data-stu-id="e0e56-120">To create a new export, select **Add export**.</span></span>

1. <span data-ttu-id="e0e56-121">V poli **Pripojenie na export** vyberte pripojenie v časti **Azure Data Lake**.</span><span class="sxs-lookup"><span data-stu-id="e0e56-121">In the **Connection for export** field, choose a connection from the **Azure Data Lake** section.</span></span> <span data-ttu-id="e0e56-122">Ak nevidíte názov tejto sekcie, nemáte k dispozícii žiadne spojenia tohto typu.</span><span class="sxs-lookup"><span data-stu-id="e0e56-122">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="e0e56-123">Vyberte si políčko vedľa každej entity, ktorú chcete exportovať do tohto cieľa.</span><span class="sxs-lookup"><span data-stu-id="e0e56-123">Select the box next to each of the entities you want to export to this destination.</span></span>

1. <span data-ttu-id="e0e56-124">Vyberte položku **Uložiť**.</span><span class="sxs-lookup"><span data-stu-id="e0e56-124">Select **Save**.</span></span>

<span data-ttu-id="e0e56-125">Uloženie exportu nespustí export okamžite.</span><span class="sxs-lookup"><span data-stu-id="e0e56-125">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="e0e56-126">Export prebieha s každým [plánovaným obnovením](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="e0e56-126">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="e0e56-127">Môžete tiež [exportovať údaje na požiadanie](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="e0e56-127">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

<span data-ttu-id="e0e56-128">Exportované údaje sú uložené v kontajneri úložiska Azure Data Lake Gen 2, ktorý ste nakonfigurovali.</span><span class="sxs-lookup"><span data-stu-id="e0e56-128">Exported data is stored in the Azure Data Lake Gen 2 storage container you configured.</span></span> 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
