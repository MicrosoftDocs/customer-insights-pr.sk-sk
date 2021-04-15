---
title: Export údajov služby Customer Insights Azure Data Lake Storage Gen2
description: Zistite, ako môžete nakonfigurovať pripojenie k Azure Data Lake Storage Gen2.
ms.date: 02/04/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 7c0eef575f745efa6312d7141a6dd96607f9797e
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596658"
---
# <a name="connector-for-azure-data-lake-storage-gen2-preview"></a><span data-ttu-id="54060-103">Konektor pre Azure Data Lake Storage Gen2 (ukážka)</span><span class="sxs-lookup"><span data-stu-id="54060-103">Connector for Azure Data Lake Storage Gen2 (preview)</span></span>

<span data-ttu-id="54060-104">Uložte si údaje zo služby Customer Insights do služby Azure Data Lake Storage Gen2 alebo ju použite na prenos údajov do iných aplikácií.</span><span class="sxs-lookup"><span data-stu-id="54060-104">Store your Customer Insights data in Azure Data Lake Storage Gen2 or use it to transfer your data to other applications.</span></span>

## <a name="configure-the-connector-for-azure-data-lake-storage-gen2"></a><span data-ttu-id="54060-105">Nakonfigurujte konektor pre Azure Data Lake Storage Gen2</span><span class="sxs-lookup"><span data-stu-id="54060-105">Configure the connector for Azure Data Lake Storage Gen2</span></span>

1. <span data-ttu-id="54060-106">V prehľadoch cieľových skupín prejdite na **Správca** > **Ciele exportu**.</span><span class="sxs-lookup"><span data-stu-id="54060-106">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="54060-107">V časti **Azure Data Lake Storage Gen2** vyberte položku **Nastaviť**.</span><span class="sxs-lookup"><span data-stu-id="54060-107">Under **Azure Data Lake Storage Gen2**, select **Set up**.</span></span>

1. <span data-ttu-id="54060-108">Do poľa **Zobrazovaný názov** zadajte rozpoznateľný názov cieľa.</span><span class="sxs-lookup"><span data-stu-id="54060-108">Give your destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="54060-109">Zadajte **Názov účtu**, **Kľúč účtu** a **Kontajner** pre svoje Azure Data Lake Storage Gen2.</span><span class="sxs-lookup"><span data-stu-id="54060-109">Enter **Account name**, **Account key**, and **Container** for your Azure Data Lake Storage Gen2.</span></span>
    - <span data-ttu-id="54060-110">Naučte sa, ako vytvoriť účet úložiska na použitie s Azure Data Lake Storage Gen2, pozri [Vytvorte si účet úložiska](/azure/storage/blobs/create-data-lake-storage-account).</span><span class="sxs-lookup"><span data-stu-id="54060-110">To learn how to create a storage account to use with Azure Data Lake Storage Gen2, see [Create storage account](/azure/storage/blobs/create-data-lake-storage-account).</span></span> 
    - <span data-ttu-id="54060-111">Ak sa chcete dozvedieť viac o tom, ako nájsť názov a kľúč účtu úložiska Azure Data Lake Gen2, prečítajte si [Spravujte nastavenia účtu úložiska na portáli Azure](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="54060-111">To learn more about how to find the Azure Data Lake Gen2 storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>

1. <span data-ttu-id="54060-112">Vyberte **Ďalej**.</span><span class="sxs-lookup"><span data-stu-id="54060-112">Select **Next**.</span></span>

1. <span data-ttu-id="54060-113">Vyberte si políčko vedľa každej entity, ktorú chcete exportovať do tohto cieľa.</span><span class="sxs-lookup"><span data-stu-id="54060-113">Select the box next to each of the entities you want to export to this destination.</span></span>

1. <span data-ttu-id="54060-114">Vyberte položku **Uložiť**.</span><span class="sxs-lookup"><span data-stu-id="54060-114">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="54060-115">Export údajov</span><span class="sxs-lookup"><span data-stu-id="54060-115">Export the data</span></span>

<span data-ttu-id="54060-116">Môžete [exportovať údaje na vyžiadanie](export-destinations.md#export-data-on-demand).</span><span class="sxs-lookup"><span data-stu-id="54060-116">You can [export data on demand](export-destinations.md#export-data-on-demand).</span></span> <span data-ttu-id="54060-117">Export sa spustí aj pri každej [plánovanej obnove](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="54060-117">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>