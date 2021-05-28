---
title: Exportujte údaje z Customer Insights
description: Spravujte exporty do zdieľania údajov.
ms.date: 03/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: c1078ed0ba259a6e9cde3c7ede3570890ae48e67
ms.sourcegitcommit: 33a8e21b3bf6521bdb8346f81f79fce88091ddfd
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 05/10/2021
ms.locfileid: "6016655"
---
# <a name="exports-preview-overview"></a><span data-ttu-id="e1a1b-103">Prehľad exportov (verzia Preview)</span><span class="sxs-lookup"><span data-stu-id="e1a1b-103">Exports (preview) overview</span></span>

<span data-ttu-id="e1a1b-104">Stránka **Exporty** zobrazuje všetky nakonfigurované exporty.</span><span class="sxs-lookup"><span data-stu-id="e1a1b-104">The **Exports** page shows you all configured exports.</span></span> <span data-ttu-id="e1a1b-105">Exporty zdieľajú konkrétne údaje s rôznymi aplikáciami.</span><span class="sxs-lookup"><span data-stu-id="e1a1b-105">Exports share specific data with various applications.</span></span> <span data-ttu-id="e1a1b-106">Môžu obsahovať zákaznícke profily alebo entity, schémy a podrobnosti mapovania.</span><span class="sxs-lookup"><span data-stu-id="e1a1b-106">They can include customer profiles or entities, schemas, and mapping details.</span></span> <span data-ttu-id="e1a1b-107">Každý export vyžaduje [pripojenie, nastavenie zo strany správcu na správu autentifikácie a prístupu](connections.md).</span><span class="sxs-lookup"><span data-stu-id="e1a1b-107">Each export requires a [connection, set up by an administrator, to manage authentication and access](connections.md).</span></span>

<span data-ttu-id="e1a1b-108">Prejdite do ponuky **Údaje** > **Exporty** a zobrazte si stránku s exportmi.</span><span class="sxs-lookup"><span data-stu-id="e1a1b-108">Go to **Data** > **Exports** to view the exports page.</span></span> <span data-ttu-id="e1a1b-109">Všetky používateľské roly majú prístup na zobrazenie nakonfigurovaných exportov.</span><span class="sxs-lookup"><span data-stu-id="e1a1b-109">All user roles have access to view configured exports.</span></span> <span data-ttu-id="e1a1b-110">Pomocou vyhľadávacieho poľa na paneli príkazov môžete vyhľadať exporty podľa ich názvu, názvu pripojenia alebo typu pripojenia.</span><span class="sxs-lookup"><span data-stu-id="e1a1b-110">Use of the search field in the command bar to find exports by their name, connection name, or connection type.</span></span>

## <a name="set-up-a-new-export"></a><span data-ttu-id="e1a1b-111">Nastavenie nového exportu</span><span class="sxs-lookup"><span data-stu-id="e1a1b-111">Set up a new export</span></span>

<span data-ttu-id="e1a1b-112">Ak chcete nastaviť alebo upraviť export, musíte mať k dispozícii pripojenia.</span><span class="sxs-lookup"><span data-stu-id="e1a1b-112">To set up or edit an export, you need to have connections available to you.</span></span> <span data-ttu-id="e1a1b-113">Pripojenia závisia od vašej [roly používateľa](permissions.md):</span><span class="sxs-lookup"><span data-stu-id="e1a1b-113">Connections depend on your [user role](permissions.md):</span></span>
- <span data-ttu-id="e1a1b-114">Správcovia majú prístup ku všetkým pripojeniam.</span><span class="sxs-lookup"><span data-stu-id="e1a1b-114">Administrators have access to all connections.</span></span> <span data-ttu-id="e1a1b-115">Môžu tiež vytvárať nové pripojenia pri nastavovaní exportu.</span><span class="sxs-lookup"><span data-stu-id="e1a1b-115">They can also create new connections when setting up an export.</span></span>
- <span data-ttu-id="e1a1b-116">Prispievatelia môžu mať prístup ku konkrétnym pripojeniam.</span><span class="sxs-lookup"><span data-stu-id="e1a1b-116">Contributors can have access to specific connections.</span></span> <span data-ttu-id="e1a1b-117">Závisia od správcov, ktorí konfigurujú a zdieľajú pripojenia.</span><span class="sxs-lookup"><span data-stu-id="e1a1b-117">They depend on administrators to configure and share connections.</span></span> <span data-ttu-id="e1a1b-118">Viac informácií nájdete v časti [Umožnite prispievateľom použiť pripojenie na export](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="e1a1b-118">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>
- <span data-ttu-id="e1a1b-119">Diváci môžu iba prezerať existujúce exporty, ale nemôžu ich vytvárať.</span><span class="sxs-lookup"><span data-stu-id="e1a1b-119">Viewers can only view existing exports but not create them.</span></span>

1. <span data-ttu-id="e1a1b-120">Prejdite na **Údaje** > **Exporty**.</span><span class="sxs-lookup"><span data-stu-id="e1a1b-120">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="e1a1b-121">Stlačte možnosť **Pridať export** na vytvorenie nového cieľového umiestnenia exportu.</span><span class="sxs-lookup"><span data-stu-id="e1a1b-121">Select **Add export** to create a new export destination.</span></span>

1. <span data-ttu-id="e1a1b-122">V table **Nastaviť export** zvoľte, ktoré pripojenie sa má použiť.</span><span class="sxs-lookup"><span data-stu-id="e1a1b-122">In the **Set up export** pane, select which connection to use.</span></span> <span data-ttu-id="e1a1b-123">[Pripojenia](connections.md) sú spravované správcami.</span><span class="sxs-lookup"><span data-stu-id="e1a1b-123">[Connections](connections.md) are managed by administrators.</span></span> 

1. <span data-ttu-id="e1a1b-124">Zadajte požadované podrobnosti a stlačte možnosť **Uložiť**, čím si vytvoríte export.</span><span class="sxs-lookup"><span data-stu-id="e1a1b-124">Provide the required details and select **Save** to create the export.</span></span>

### <a name="edit-an-export"></a><span data-ttu-id="e1a1b-125">Upraviť export</span><span class="sxs-lookup"><span data-stu-id="e1a1b-125">Edit an export</span></span>

1. <span data-ttu-id="e1a1b-126">Vyberte zvislé tri bodky pri cieli exportu, ktorý chcete upraviť.</span><span class="sxs-lookup"><span data-stu-id="e1a1b-126">Select the vertical ellipsis for the export destination you want to edit.</span></span>

1. <span data-ttu-id="e1a1b-127">V rozbaľovacej ponuke stlačte možnosť **Upraviť**.</span><span class="sxs-lookup"><span data-stu-id="e1a1b-127">Select **Edit** from the drop-down menu.</span></span>

1. <span data-ttu-id="e1a1b-128">Zmeňte hodnoty, ktoré chcete aktualizovať, a stlačte možnosť **Uložiť**.</span><span class="sxs-lookup"><span data-stu-id="e1a1b-128">Change the values you want to update and select **Save**.</span></span>

## <a name="view-exports-and-export-details"></a><span data-ttu-id="e1a1b-129">Zobraziť exporty a podrobnosti exportu</span><span class="sxs-lookup"><span data-stu-id="e1a1b-129">View Exports and export details</span></span>

<span data-ttu-id="e1a1b-130">Po vytvorení exportných cieľov sa uvedú v časti **Údaje** > **Exporty**.</span><span class="sxs-lookup"><span data-stu-id="e1a1b-130">After creating export destinations, they are listed on **Data** > **Exports**.</span></span> <span data-ttu-id="e1a1b-131">Všetci používatelia môžu vidieť, ktoré údaje sú zdieľané, a ich najnovší stav.</span><span class="sxs-lookup"><span data-stu-id="e1a1b-131">All users can see which data is shared and its latest status.</span></span>

1. <span data-ttu-id="e1a1b-132">Prejdite na **Údaje** > **Exporty**.</span><span class="sxs-lookup"><span data-stu-id="e1a1b-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="e1a1b-133">Používatelia bez oprávnení na úpravy zvoľte možnosť **Zobraziť** namiesto **Upraviť** a zobrazte si podrobnosti exportu.</span><span class="sxs-lookup"><span data-stu-id="e1a1b-133">Users without edit permissions select **View** instead of **Edit** see the export details.</span></span>

1. <span data-ttu-id="e1a1b-134">Táto bočná tabla zobrazuje nastavenie tohto exportu.</span><span class="sxs-lookup"><span data-stu-id="e1a1b-134">This side pane shows the set up of this export.</span></span> <span data-ttu-id="e1a1b-135">Bez povolení na úpravy nemôžete hodnoty meniť.</span><span class="sxs-lookup"><span data-stu-id="e1a1b-135">Without edit permissions, you can't change values.</span></span> <span data-ttu-id="e1a1b-136">Stlačte možnosť **Zavrieť** pre návrat na stránku exportu.</span><span class="sxs-lookup"><span data-stu-id="e1a1b-136">Select **Close** to return to the exports page.</span></span>

## <a name="run-exports-on-demand"></a><span data-ttu-id="e1a1b-137">Spúšťanie exportov na požiadanie</span><span class="sxs-lookup"><span data-stu-id="e1a1b-137">Run exports on demand</span></span>

<span data-ttu-id="e1a1b-138">Po nakonfigurovaní exportu bude prebiehať s každým [plánované obnovenie](system.md#schedule-tab) pokiaľ má funkčné spojenie.</span><span class="sxs-lookup"><span data-stu-id="e1a1b-138">After configuring an export, it will run with every [scheduled refresh](system.md#schedule-tab) as long as it has a working connection.</span></span>

<span data-ttu-id="e1a1b-139">Ak chcete exportovať údaje bez čakania na plánované obnovenie, prejdite na **Údaje** > **Exporty**.</span><span class="sxs-lookup"><span data-stu-id="e1a1b-139">To export data without waiting for a scheduled refresh, go to **Data** > **Exports**.</span></span> <span data-ttu-id="e1a1b-140">Máte dve možnosti:</span><span class="sxs-lookup"><span data-stu-id="e1a1b-140">You have two options:</span></span>

- <span data-ttu-id="e1a1b-141">Ak chcete spustiť všetky exporty, stlačte možnosť **Spustiť všetko** na paneli príkazov.</span><span class="sxs-lookup"><span data-stu-id="e1a1b-141">To run all exports, select **Run all** in the command bar.</span></span> 
- <span data-ttu-id="e1a1b-142">Ak chcete spustiť jeden export, stlačte tri bodky (...) v položke zoznamu a potom stlačte možnosť **Spustiť**.</span><span class="sxs-lookup"><span data-stu-id="e1a1b-142">To run a single export, select the ellipsis (...) on a list item and then choose **Run**.</span></span>

## <a name="remove-an-export"></a><span data-ttu-id="e1a1b-143">Odstránenie exportu</span><span class="sxs-lookup"><span data-stu-id="e1a1b-143">Remove an Export</span></span>

1. <span data-ttu-id="e1a1b-144">Prejdite na **Údaje** > **Exporty**.</span><span class="sxs-lookup"><span data-stu-id="e1a1b-144">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="e1a1b-145">Vyberte zvislé tri bodky pri exporte, ktorý chcete odstrániť.</span><span class="sxs-lookup"><span data-stu-id="e1a1b-145">Select the vertical ellipsis for the Export you want to remove.</span></span>

1. <span data-ttu-id="e1a1b-146">Vyberte položku **Odstrániť** z rozbaľovacej ponuky.</span><span class="sxs-lookup"><span data-stu-id="e1a1b-146">Select **Remove** from the dropdown menu.</span></span>

1. <span data-ttu-id="e1a1b-147">Odstránenie potvrďte výberom položky **Odstrániť** na obrazovke s potvrdením.</span><span class="sxs-lookup"><span data-stu-id="e1a1b-147">Confirm the removal by selecting **Remove** on the confirmation screen.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
