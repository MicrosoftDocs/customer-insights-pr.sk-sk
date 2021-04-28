---
title: Exportujte údaje z Customer Insights
description: Spravujte exporty do zdieľania údajov.
ms.date: 03/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 354ce9ef30fe918975d06290430996c84f8bd3f7
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896162"
---
# <a name="exports-preview-overview"></a><span data-ttu-id="d757d-103">Prehľad exportov (verzia Preview)</span><span class="sxs-lookup"><span data-stu-id="d757d-103">Exports (preview) overview</span></span>

<span data-ttu-id="d757d-104">Stránka **Exporty** zobrazuje všetky nakonfigurované exporty.</span><span class="sxs-lookup"><span data-stu-id="d757d-104">The **Exports** page shows you all configured exports.</span></span> <span data-ttu-id="d757d-105">Exporty zdieľajú konkrétne údaje s rôznymi aplikáciami.</span><span class="sxs-lookup"><span data-stu-id="d757d-105">Exports share specific data with various applications.</span></span> <span data-ttu-id="d757d-106">Môžu obsahovať zákaznícke profily alebo entity, schémy a podrobnosti mapovania.</span><span class="sxs-lookup"><span data-stu-id="d757d-106">They can include customer profiles or entities, schemas, and mapping details.</span></span> <span data-ttu-id="d757d-107">Každý export vyžaduje [pripojenie, nastavenie zo strany správcu na správu autentifikácie a prístupu](connections.md).</span><span class="sxs-lookup"><span data-stu-id="d757d-107">Each export requires a [connection, set up by an administrator, to manage authentication and access](connections.md).</span></span>

> [!NOTE]
> <span data-ttu-id="d757d-108">Až do marca 2021 vytvoril export pripojenie k príslušnej službe automaticky.</span><span class="sxs-lookup"><span data-stu-id="d757d-108">Until March 2021, exports created a connection to the corresponding service automatically.</span></span> <span data-ttu-id="d757d-109">Export teraz vyžaduje [pripojenie, vytvorené a zdieľané správcom](connections.md) skôr ako ich vytvoríte.</span><span class="sxs-lookup"><span data-stu-id="d757d-109">Exports now require a [connection, created and shared by an administrator](connections.md) before you can create them.</span></span>

<span data-ttu-id="d757d-110">Prejdite do ponuky **Údaje** > **Exporty** a zobrazte si stránku s exportmi.</span><span class="sxs-lookup"><span data-stu-id="d757d-110">Go to **Data** > **Exports** to view the exports page.</span></span> <span data-ttu-id="d757d-111">Všetky používateľské roly majú prístup na zobrazenie nakonfigurovaných exportov.</span><span class="sxs-lookup"><span data-stu-id="d757d-111">All user roles have access to view configured exports.</span></span> <span data-ttu-id="d757d-112">Pomocou vyhľadávacieho poľa na paneli príkazov môžete vyhľadať exporty podľa ich názvu, názvu pripojenia alebo typu pripojenia.</span><span class="sxs-lookup"><span data-stu-id="d757d-112">Use of the search field in the command bar to find exports by their name, connection name, or connection type.</span></span>

## <a name="set-up-a-new-export"></a><span data-ttu-id="d757d-113">Nastavenie nového exportu</span><span class="sxs-lookup"><span data-stu-id="d757d-113">Set up a new export</span></span>

<span data-ttu-id="d757d-114">Ak chcete nastaviť alebo upraviť export, musíte mať k dispozícii pripojenia.</span><span class="sxs-lookup"><span data-stu-id="d757d-114">To set up or edit an export, you need to have connections available to you.</span></span> <span data-ttu-id="d757d-115">Pripojenia závisia od vašej [roly používateľa](permissions.md):</span><span class="sxs-lookup"><span data-stu-id="d757d-115">Connections depend on your [user role](permissions.md):</span></span>
- <span data-ttu-id="d757d-116">Správcovia majú prístup ku všetkým pripojeniam.</span><span class="sxs-lookup"><span data-stu-id="d757d-116">Administrators have access to all connections.</span></span> <span data-ttu-id="d757d-117">Môžu tiež vytvárať nové pripojenia pri nastavovaní exportu.</span><span class="sxs-lookup"><span data-stu-id="d757d-117">They can also create new connections when setting up an export.</span></span>
- <span data-ttu-id="d757d-118">Prispievatelia môžu mať prístup ku konkrétnym pripojeniam.</span><span class="sxs-lookup"><span data-stu-id="d757d-118">Contributors can have access to specific connections.</span></span> <span data-ttu-id="d757d-119">Závisia od správcov, ktorí konfigurujú a zdieľajú pripojenia.</span><span class="sxs-lookup"><span data-stu-id="d757d-119">They depend on administrators to configure and share connections.</span></span> <span data-ttu-id="d757d-120">Viac informácií nájdete v časti [Umožnite prispievateľom použiť pripojenie na export](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="d757d-120">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>
- <span data-ttu-id="d757d-121">Diváci môžu iba prezerať existujúce exporty, ale nemôžu ich vytvárať.</span><span class="sxs-lookup"><span data-stu-id="d757d-121">Viewers can only view existing exports but not create them.</span></span>

1. <span data-ttu-id="d757d-122">Prejdite na **Údaje** > **Exporty**.</span><span class="sxs-lookup"><span data-stu-id="d757d-122">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="d757d-123">Stlačte možnosť **Pridať export** na vytvorenie nového cieľového umiestnenia exportu.</span><span class="sxs-lookup"><span data-stu-id="d757d-123">Select **Add export** to create a new export destination.</span></span>

1. <span data-ttu-id="d757d-124">V table **Nastaviť export** zvoľte, ktoré pripojenie sa má použiť.</span><span class="sxs-lookup"><span data-stu-id="d757d-124">In the **Set up export** pane, select which connection to use.</span></span> <span data-ttu-id="d757d-125">[Pripojenia](connections.md) sú spravované správcami.</span><span class="sxs-lookup"><span data-stu-id="d757d-125">[Connections](connections.md) are managed by administrators.</span></span> 

1. <span data-ttu-id="d757d-126">Zadajte požadované podrobnosti a stlačte možnosť **Uložiť**, čím si vytvoríte export.</span><span class="sxs-lookup"><span data-stu-id="d757d-126">Provide the required details and select **Save** to create the export.</span></span>

### <a name="edit-an-export"></a><span data-ttu-id="d757d-127">Upraviť export</span><span class="sxs-lookup"><span data-stu-id="d757d-127">Edit an export</span></span>

1. <span data-ttu-id="d757d-128">Vyberte zvislé tri bodky pri cieli exportu, ktorý chcete upraviť.</span><span class="sxs-lookup"><span data-stu-id="d757d-128">Select the vertical ellipsis for the export destination you want to edit.</span></span>

1. <span data-ttu-id="d757d-129">V rozbaľovacej ponuke stlačte možnosť **Upraviť**.</span><span class="sxs-lookup"><span data-stu-id="d757d-129">Select **Edit** from the drop-down menu.</span></span>

1. <span data-ttu-id="d757d-130">Zmeňte hodnoty, ktoré chcete aktualizovať, a stlačte možnosť **Uložiť**.</span><span class="sxs-lookup"><span data-stu-id="d757d-130">Change the values you want to update and select **Save**.</span></span>

## <a name="view-exports-and-export-details"></a><span data-ttu-id="d757d-131">Zobraziť exporty a podrobnosti exportu</span><span class="sxs-lookup"><span data-stu-id="d757d-131">View Exports and export details</span></span>

<span data-ttu-id="d757d-132">Po vytvorení exportných cieľov sa uvedú v časti **Údaje** > **Exporty**.</span><span class="sxs-lookup"><span data-stu-id="d757d-132">After creating export destinations, they are listed on **Data** > **Exports**.</span></span> <span data-ttu-id="d757d-133">Všetci používatelia môžu vidieť, ktoré údaje sú zdieľané, a ich najnovší stav.</span><span class="sxs-lookup"><span data-stu-id="d757d-133">All users can see which data is shared and its latest status.</span></span>

1. <span data-ttu-id="d757d-134">Prejdite na **Údaje** > **Exporty**.</span><span class="sxs-lookup"><span data-stu-id="d757d-134">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="d757d-135">Používatelia bez oprávnení na úpravy zvoľte možnosť **Zobraziť** namiesto **Upraviť** a zobrazte si podrobnosti exportu.</span><span class="sxs-lookup"><span data-stu-id="d757d-135">Users without edit permissions select **View** instead of **Edit** see the export details.</span></span>

1. <span data-ttu-id="d757d-136">Táto bočná tabla zobrazuje nastavenie tohto exportu.</span><span class="sxs-lookup"><span data-stu-id="d757d-136">This side pane shows the set up of this export.</span></span> <span data-ttu-id="d757d-137">Bez povolení na úpravy nemôžete hodnoty meniť.</span><span class="sxs-lookup"><span data-stu-id="d757d-137">Without edit permissions, you can't change values.</span></span> <span data-ttu-id="d757d-138">Stlačte možnosť **Zavrieť** pre návrat na stránku exportu.</span><span class="sxs-lookup"><span data-stu-id="d757d-138">Select **Close** to return to the exports page.</span></span>

## <a name="run-exports-on-demand"></a><span data-ttu-id="d757d-139">Spúšťanie exportov na požiadanie</span><span class="sxs-lookup"><span data-stu-id="d757d-139">Run exports on demand</span></span>

<span data-ttu-id="d757d-140">Po nakonfigurovaní exportu bude prebiehať s každým [plánované obnovenie](system.md#schedule-tab) pokiaľ má funkčné spojenie.</span><span class="sxs-lookup"><span data-stu-id="d757d-140">After configuring an export, it will run with every [scheduled refresh](system.md#schedule-tab) as long as it has a working connection.</span></span>

<span data-ttu-id="d757d-141">Ak chcete exportovať údaje bez čakania na plánované obnovenie, prejdite na **Údaje** > **Exporty**.</span><span class="sxs-lookup"><span data-stu-id="d757d-141">To export data without waiting for a scheduled refresh, go to **Data** > **Exports**.</span></span> <span data-ttu-id="d757d-142">Máte dve možnosti:</span><span class="sxs-lookup"><span data-stu-id="d757d-142">You have two options:</span></span>

- <span data-ttu-id="d757d-143">Ak chcete spustiť všetky exporty, stlačte možnosť **Spustiť všetko** na paneli príkazov.</span><span class="sxs-lookup"><span data-stu-id="d757d-143">To run all exports, select **Run all** in the command bar.</span></span> 
- <span data-ttu-id="d757d-144">Ak chcete spustiť jeden export, stlačte tri bodky (...) v položke zoznamu a potom stlačte možnosť **Spustiť**.</span><span class="sxs-lookup"><span data-stu-id="d757d-144">To run a single export, select the ellipsis (...) on a list item and then choose **Run**.</span></span>

## <a name="remove-an-export"></a><span data-ttu-id="d757d-145">Odstránenie exportu</span><span class="sxs-lookup"><span data-stu-id="d757d-145">Remove an Export</span></span>

1. <span data-ttu-id="d757d-146">Prejdite na **Údaje** > **Exporty**.</span><span class="sxs-lookup"><span data-stu-id="d757d-146">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="d757d-147">Vyberte zvislé tri bodky pri exporte, ktorý chcete odstrániť.</span><span class="sxs-lookup"><span data-stu-id="d757d-147">Select the vertical ellipsis for the Export you want to remove.</span></span>

1. <span data-ttu-id="d757d-148">Vyberte položku **Odstrániť** z rozbaľovacej ponuky.</span><span class="sxs-lookup"><span data-stu-id="d757d-148">Select **Remove** from the dropdown menu.</span></span>

1. <span data-ttu-id="d757d-149">Odstránenie potvrďte výberom položky **Odstrániť** na obrazovke s potvrdením.</span><span class="sxs-lookup"><span data-stu-id="d757d-149">Confirm the removal by selecting **Remove** on the confirmation screen.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
