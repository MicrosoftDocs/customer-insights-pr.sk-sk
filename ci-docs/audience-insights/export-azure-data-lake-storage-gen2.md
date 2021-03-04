---
title: Export údajov služby Customer Insights Azure Data Lake Storage Gen2
description: Zistite, ako môžete nakonfigurovať pripojenie k Azure Data Lake Storage Gen2.
ms.date: 02/04/2021
ms.reviewer: sthe
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: b00c3d6178150cbc93fe800779f094809d4dc67b
ms.sourcegitcommit: 0260ed244b97c2fd0be5e9a084c4c489358e8d4f
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 02/18/2021
ms.locfileid: "5477198"
---
# <a name="connector-for-azure-data-lake-storage-gen2-preview"></a><span data-ttu-id="b44b2-103">Konektor pre Azure Data Lake Storage Gen2 (ukážka)</span><span class="sxs-lookup"><span data-stu-id="b44b2-103">Connector for Azure Data Lake Storage Gen2 (preview)</span></span>

<span data-ttu-id="b44b2-104">Uložte si údaje zo služby Customer Insights do služby Azure Data Lake Storage Gen2 alebo ju použite na prenos údajov do iných aplikácií.</span><span class="sxs-lookup"><span data-stu-id="b44b2-104">Store your Customer Insights data in Azure Data Lake Storage Gen2 or use it to transfer your data to other applications.</span></span>

## <a name="configure-the-connector-for-azure-data-lake-storage-gen2"></a><span data-ttu-id="b44b2-105">Nakonfigurujte konektor pre Azure Data Lake Storage Gen2</span><span class="sxs-lookup"><span data-stu-id="b44b2-105">Configure the connector for Azure Data Lake Storage Gen2</span></span>

1. <span data-ttu-id="b44b2-106">V prehľadoch cieľových skupín prejdite na **Správca** > **Ciele exportu**.</span><span class="sxs-lookup"><span data-stu-id="b44b2-106">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="b44b2-107">V časti **Azure Data Lake Storage Gen2** vyberte položku **Nastaviť**.</span><span class="sxs-lookup"><span data-stu-id="b44b2-107">Under **Azure Data Lake Storage Gen2**, select **Set up**.</span></span>

1. <span data-ttu-id="b44b2-108">Do poľa **Zobrazovaný názov** zadajte rozpoznateľný názov cieľa.</span><span class="sxs-lookup"><span data-stu-id="b44b2-108">Give your destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="b44b2-109">Zadajte **Názov účtu**, **Kľúč účtu** a **Kontajner** pre svoje Azure Data Lake Storage Gen2.</span><span class="sxs-lookup"><span data-stu-id="b44b2-109">Enter **Account name**, **Account key**, and **Container** for your Azure Data Lake Storage Gen2.</span></span>
    - <span data-ttu-id="b44b2-110">Naučte sa, ako vytvoriť účet úložiska na použitie s Azure Data Lake Storage Gen2, pozri [Vytvorte si účet úložiska](https://docs.microsoft.com/azure/storage/blobs/create-data-lake-storage-account).</span><span class="sxs-lookup"><span data-stu-id="b44b2-110">To learn how to create a storage account to use with Azure Data Lake Storage Gen2, see [Create storage account](https://docs.microsoft.com/azure/storage/blobs/create-data-lake-storage-account).</span></span> 
    - <span data-ttu-id="b44b2-111">Ak sa chcete dozvedieť viac o tom, ako nájsť názov a kľúč účtu úložiska Azure Data Lake Gen2, prečítajte si [Spravujte nastavenia účtu úložiska na portáli Azure](https://docs.microsoft.com/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="b44b2-111">To learn more about how to find the Azure Data Lake Gen2 storage account name and account key, see [Manage storage account settings in the Azure portal](https://docs.microsoft.com/azure/storage/common/storage-account-manage).</span></span>

1. <span data-ttu-id="b44b2-112">Vyberte **Ďalej**.</span><span class="sxs-lookup"><span data-stu-id="b44b2-112">Select **Next**.</span></span>

1. <span data-ttu-id="b44b2-113">Vyberte si políčko vedľa každej entity, ktorú chcete exportovať do tohto cieľa.</span><span class="sxs-lookup"><span data-stu-id="b44b2-113">Select the box next to each of the entities you want to export to this destination.</span></span>

1. <span data-ttu-id="b44b2-114">Vyberte položku **Uložiť**.</span><span class="sxs-lookup"><span data-stu-id="b44b2-114">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="b44b2-115">Export údajov</span><span class="sxs-lookup"><span data-stu-id="b44b2-115">Export the data</span></span>

<span data-ttu-id="b44b2-116">Môžete [exportovať údaje na vyžiadanie](export-destinations.md#export-data-on-demand).</span><span class="sxs-lookup"><span data-stu-id="b44b2-116">You can [export data on demand](export-destinations.md#export-data-on-demand).</span></span> <span data-ttu-id="b44b2-117">Export sa spustí aj pri každej [plánovanej obnove](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="b44b2-117">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>