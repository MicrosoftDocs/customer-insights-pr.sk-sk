---
title: Exportujte údaje z Customer Insights
description: Spravujte exporty do zdieľania údajov.
ms.date: 06/14/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 28563e3a76535cb0c92bfcda4ef5037430d00cfa
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305497"
---
# <a name="exports-preview-overview"></a><span data-ttu-id="54f43-103">Prehľad exportov (verzia Preview)</span><span class="sxs-lookup"><span data-stu-id="54f43-103">Exports (preview) overview</span></span>

<span data-ttu-id="54f43-104">Stránka **Exporty** zobrazuje všetky nakonfigurované exporty.</span><span class="sxs-lookup"><span data-stu-id="54f43-104">The **Exports** page shows you all configured exports.</span></span> <span data-ttu-id="54f43-105">Exporty zdieľajú konkrétne údaje s rôznymi aplikáciami.</span><span class="sxs-lookup"><span data-stu-id="54f43-105">Exports share specific data with various applications.</span></span> <span data-ttu-id="54f43-106">Môžu obsahovať zákaznícke profily alebo entity, schémy a podrobnosti mapovania.</span><span class="sxs-lookup"><span data-stu-id="54f43-106">They can include customer profiles or entities, schemas, and mapping details.</span></span> <span data-ttu-id="54f43-107">Každý export vyžaduje [pripojenie, nastavenie zo strany správcu na správu autentifikácie a prístupu](connections.md).</span><span class="sxs-lookup"><span data-stu-id="54f43-107">Each export requires a [connection, set up by an administrator, to manage authentication and access](connections.md).</span></span>

<span data-ttu-id="54f43-108">Prejdite do ponuky **Údaje** > **Exporty** a zobrazte si stránku s exportmi.</span><span class="sxs-lookup"><span data-stu-id="54f43-108">Go to **Data** > **Exports** to view the exports page.</span></span> <span data-ttu-id="54f43-109">Všetky roly používateľov môžu zobrazovať nakonfigurované exporty.</span><span class="sxs-lookup"><span data-stu-id="54f43-109">All user roles can view configured exports.</span></span> <span data-ttu-id="54f43-110">Pomocou vyhľadávacieho poľa na paneli príkazov vyhľadajte exporty podľa názvu, názvu pripojenia alebo typu pripojenia.</span><span class="sxs-lookup"><span data-stu-id="54f43-110">Use the search field in the command bar to find exports by their name, connection name, or connection type.</span></span>

## <a name="set-up-a-new-export"></a><span data-ttu-id="54f43-111">Nastavenie nového exportu</span><span class="sxs-lookup"><span data-stu-id="54f43-111">Set up a new export</span></span>

<span data-ttu-id="54f43-112">Ak chcete nastaviť alebo upraviť export, musíte mať k dispozícii pripojenia.</span><span class="sxs-lookup"><span data-stu-id="54f43-112">To set up or edit an export, you need to have connections available to you.</span></span> <span data-ttu-id="54f43-113">Pripojenia závisia od vašej [roly používateľa](permissions.md):</span><span class="sxs-lookup"><span data-stu-id="54f43-113">Connections depend on your [user role](permissions.md):</span></span>
- <span data-ttu-id="54f43-114">Správcovia majú prístup ku všetkým pripojeniam.</span><span class="sxs-lookup"><span data-stu-id="54f43-114">Administrators have access to all connections.</span></span> <span data-ttu-id="54f43-115">Môžu tiež vytvárať nové pripojenia pri nastavovaní exportu.</span><span class="sxs-lookup"><span data-stu-id="54f43-115">They can also create new connections when setting up an export.</span></span>
- <span data-ttu-id="54f43-116">Prispievatelia môžu mať prístup ku konkrétnym pripojeniam.</span><span class="sxs-lookup"><span data-stu-id="54f43-116">Contributors can have access to specific connections.</span></span> <span data-ttu-id="54f43-117">Závisia od správcov, ktorí konfigurujú a zdieľajú pripojenia.</span><span class="sxs-lookup"><span data-stu-id="54f43-117">They depend on administrators to configure and share connections.</span></span> <span data-ttu-id="54f43-118">Zoznam exportov zobrazuje prispievateľov, či môžu upravovať alebo len zobraziť export v stĺpci **Vaše povolenia**.</span><span class="sxs-lookup"><span data-stu-id="54f43-118">The exports list shows contributors whether they can edit or only view an export in the **Your permissions** column.</span></span> <span data-ttu-id="54f43-119">Viac informácií nájdete v časti [Umožnite prispievateľom použiť pripojenie na export](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="54f43-119">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>
- <span data-ttu-id="54f43-120">Diváci môžu iba prezerať existujúce exporty, ale nemôžu ich vytvárať.</span><span class="sxs-lookup"><span data-stu-id="54f43-120">Viewers can only view existing exports but not create them.</span></span>

### <a name="define-a-new-export"></a><span data-ttu-id="54f43-121">Definovanie nového exportu</span><span class="sxs-lookup"><span data-stu-id="54f43-121">Define a new export</span></span>

1. <span data-ttu-id="54f43-122">Prejdite na **Údaje** > **Exporty**.</span><span class="sxs-lookup"><span data-stu-id="54f43-122">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="54f43-123">Vyberte **Pridať export** na vytvorenie nového exportu.</span><span class="sxs-lookup"><span data-stu-id="54f43-123">Select **Add export** to create a new export.</span></span>

1. <span data-ttu-id="54f43-124">V table **Nastaviť export** zvoľte, ktoré pripojenie sa má použiť.</span><span class="sxs-lookup"><span data-stu-id="54f43-124">In the **Set up export** pane, select which connection to use.</span></span> <span data-ttu-id="54f43-125">[Pripojenia](connections.md) sú spravované správcami.</span><span class="sxs-lookup"><span data-stu-id="54f43-125">[Connections](connections.md) are managed by administrators.</span></span> 

1. <span data-ttu-id="54f43-126">Zadajte požadované podrobnosti a stlačte možnosť **Uložiť**, čím si vytvoríte export.</span><span class="sxs-lookup"><span data-stu-id="54f43-126">Provide the required details and select **Save** to create the export.</span></span>

### <a name="define-a-new-export-based-on-an-existing-export"></a><span data-ttu-id="54f43-127">Definujte nový export na základe existujúceho exportu</span><span class="sxs-lookup"><span data-stu-id="54f43-127">Define a new export based on an existing export</span></span>

1. <span data-ttu-id="54f43-128">Prejdite na **Údaje** > **Exporty**.</span><span class="sxs-lookup"><span data-stu-id="54f43-128">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="54f43-129">V zozname exportov vyberte export, ktorý chcete duplikovať.</span><span class="sxs-lookup"><span data-stu-id="54f43-129">In the list of exports, select the export you want to duplicate.</span></span>

1. <span data-ttu-id="54f43-130">Vyberte **Vytvoriť duplikát** na paneli príkazov na otvorenie tably **Nastaviť export** s podrobnosťami vybratého exportu.</span><span class="sxs-lookup"><span data-stu-id="54f43-130">Select **Create duplicate** in the command bar to open the **Set up export** pane with the details of the selected export.</span></span>

1. <span data-ttu-id="54f43-131">Skontrolujte a prispôsobte export a vyberte **Uložiť** na vytvorenie nového exportu.</span><span class="sxs-lookup"><span data-stu-id="54f43-131">Review and adapt the export and select **Save** to create a new export.</span></span>

### <a name="edit-an-export"></a><span data-ttu-id="54f43-132">Upraviť export</span><span class="sxs-lookup"><span data-stu-id="54f43-132">Edit an export</span></span>

1. <span data-ttu-id="54f43-133">Prejdite na **Údaje** > **Exporty**.</span><span class="sxs-lookup"><span data-stu-id="54f43-133">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="54f43-134">V zozname exportov vyberte export, ktorý chcete upraviť.</span><span class="sxs-lookup"><span data-stu-id="54f43-134">In the list of exports, select the export you want to edit.</span></span>

1. <span data-ttu-id="54f43-135">Na paneli príkazov vyberte **Upraviť**.</span><span class="sxs-lookup"><span data-stu-id="54f43-135">Select **Edit** in the command bar.</span></span>

1. <span data-ttu-id="54f43-136">Zmeňte hodnoty, ktoré chcete aktualizovať, a stlačte možnosť **Uložiť**.</span><span class="sxs-lookup"><span data-stu-id="54f43-136">Change the values you want to update and select **Save**.</span></span>

## <a name="view-exports-and-export-details"></a><span data-ttu-id="54f43-137">Zobrazenie exportov a podrobností exportu</span><span class="sxs-lookup"><span data-stu-id="54f43-137">View exports and export details</span></span>

<span data-ttu-id="54f43-138">Po vytvorení cieľov exportu sa tieto uvedú v časti **Údaje** > **Exporty**.</span><span class="sxs-lookup"><span data-stu-id="54f43-138">After creating export destinations, they're listed on **Data** > **Exports**.</span></span> <span data-ttu-id="54f43-139">Všetci používatelia môžu vidieť, ktoré údaje sú zdieľané, a ich najnovší stav.</span><span class="sxs-lookup"><span data-stu-id="54f43-139">All users can see which data is shared and its latest status.</span></span>

1. <span data-ttu-id="54f43-140">Prejdite na **Údaje** > **Exporty**.</span><span class="sxs-lookup"><span data-stu-id="54f43-140">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="54f43-141">Používatelia bez povolení na úpravy vyberú možnosť **Zobraziť** namiesto možnosti **Upraviť** na zobrazenie podrobností o exporte.</span><span class="sxs-lookup"><span data-stu-id="54f43-141">Users without edit permissions select **View** instead of **Edit** to see the export details.</span></span>

1. <span data-ttu-id="54f43-142">Bočná tabla zobrazuje konfiguráciu exportu.</span><span class="sxs-lookup"><span data-stu-id="54f43-142">The side pane shows the configuration of an export.</span></span> <span data-ttu-id="54f43-143">Bez povolení na úpravy nemôžete hodnoty meniť.</span><span class="sxs-lookup"><span data-stu-id="54f43-143">Without edit permissions, you can't change values.</span></span> <span data-ttu-id="54f43-144">Stlačte možnosť **Zavrieť** pre návrat na stránku exportu.</span><span class="sxs-lookup"><span data-stu-id="54f43-144">Select **Close** to return to the exports page.</span></span>

## <a name="schedule-and-run-exports"></a><span data-ttu-id="54f43-145">Plánovanie a spustenie exportov</span><span class="sxs-lookup"><span data-stu-id="54f43-145">Schedule and run exports</span></span>

<span data-ttu-id="54f43-146">Každý export, ktorý nakonfigurujete, má plán obnovenia.</span><span class="sxs-lookup"><span data-stu-id="54f43-146">Each export you configure has a refresh schedule.</span></span> <span data-ttu-id="54f43-147">Počas obnovenia systém vyhľadá nové alebo aktualizované údaje, ktoré by zahrnul do exportu.</span><span class="sxs-lookup"><span data-stu-id="54f43-147">During a refresh, the system looks for new or updated data to include in an export.</span></span> <span data-ttu-id="54f43-148">Export sa štandardne spúšťa ako súčasť každého [plánovaného obnovenia systému](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="54f43-148">By default, exports are run as part of every [scheduled system refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="54f43-149">Môžete prispôsobiť plán obnovenia alebo ho vypnúť, aby sa exporty spúšťali manuálne.</span><span class="sxs-lookup"><span data-stu-id="54f43-149">You can customize the refresh schedule or turn it off to run exports manually.</span></span>

<span data-ttu-id="54f43-150">Plány exportu závisia od stavu vášho prostredia.</span><span class="sxs-lookup"><span data-stu-id="54f43-150">Export schedules depend on the state of your environment.</span></span> <span data-ttu-id="54f43-151">Ak prebiehajú aktualizácie v rámci [závislostí](system.md#refresh-policies), keď sa má spustiť plánovaný export, systém najskôr dokončí aktualizácie a potom spustí export.</span><span class="sxs-lookup"><span data-stu-id="54f43-151">If there are updates in progress on [dependencies](system.md#refresh-policies) when a scheduled export should start, the system will first complete the updates and then run the export.</span></span> <span data-ttu-id="54f43-152">V stĺpci môžete vidieť, kedy sa export naposledy obnovil v stĺpci **Obnovené**.</span><span class="sxs-lookup"><span data-stu-id="54f43-152">You can see when an export was last refreshed in column **Refreshed**.</span></span>

### <a name="schedule-exports"></a><span data-ttu-id="54f43-153">Plánovanie exportov</span><span class="sxs-lookup"><span data-stu-id="54f43-153">Schedule exports</span></span>

<span data-ttu-id="54f43-154">Môžete definovať vlastné plány obnovenia pre jednotlivé exporty alebo niekoľko exportov naraz.</span><span class="sxs-lookup"><span data-stu-id="54f43-154">You can define custom refresh schedules for individual exports or several exports at once.</span></span> <span data-ttu-id="54f43-155">Aktuálne definovaný plán je uvedený v stĺpci **Plán** exportného zoznamu.</span><span class="sxs-lookup"><span data-stu-id="54f43-155">The currently defined schedule is listed in the **Schedule** column of the export list.</span></span> <span data-ttu-id="54f43-156">Povolenie na zmenu plánu je rovnaké ako pre [úpravy a definovanie exportov](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="54f43-156">The permission to change the schedule is the same as for [editing and defining exports](export-destinations.md#set-up-a-new-export).</span></span> 

1. <span data-ttu-id="54f43-157">Prejdite na **Údaje** > **Exporty**.</span><span class="sxs-lookup"><span data-stu-id="54f43-157">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="54f43-158">Vyberte export, ktorý chcete naplánovať.</span><span class="sxs-lookup"><span data-stu-id="54f43-158">Select the export you want to schedule.</span></span>

1. <span data-ttu-id="54f43-159">Na paneli príkazov vyberte **Plán**.</span><span class="sxs-lookup"><span data-stu-id="54f43-159">Select **Schedule** in the command bar.</span></span>

1. <span data-ttu-id="54f43-160">Na table **Plán exportu** nastavte **Naplánovať spustenie** na **Zap** na spustenie exportu automaticky.</span><span class="sxs-lookup"><span data-stu-id="54f43-160">In the **Schedule export** pane, set the **Schedule run** to **On** to run the export automatically.</span></span> <span data-ttu-id="54f43-161">Nastavte ho na **Vyp**, ak ho chcete obnovovať ručne.</span><span class="sxs-lookup"><span data-stu-id="54f43-161">Set it to **Off** to refresh it manually.</span></span>

1. <span data-ttu-id="54f43-162">Pre automaticky obnovované exporty zvoľte hodnotu **Opakovanie** a uveďte jej podrobnosti.</span><span class="sxs-lookup"><span data-stu-id="54f43-162">For automatically refreshed exports, choose a **Recurrence** value and specify the details for it.</span></span> <span data-ttu-id="54f43-163">Definovaný čas platí pre všetky prípady opakovania.</span><span class="sxs-lookup"><span data-stu-id="54f43-163">The time defined applies to all instances of a recurrence.</span></span> <span data-ttu-id="54f43-164">Je to čas, kedy by sa mal export začať obnovovať.</span><span class="sxs-lookup"><span data-stu-id="54f43-164">It's the time when an export should start refreshing.</span></span>

1. <span data-ttu-id="54f43-165">Použite a aktivujte svoje zmeny výberom možnosti **Uložiť**.</span><span class="sxs-lookup"><span data-stu-id="54f43-165">Apply and activate your changes by selecting **Save**.</span></span>

<span data-ttu-id="54f43-166">Pri úprave plánu pre niekoľko exportov musíte urobiť výber pod **Ponechať alebo prepísať plány**:</span><span class="sxs-lookup"><span data-stu-id="54f43-166">When editing the schedule for several exports, you need to make a selection under **Keep or override schedules**:</span></span>
- <span data-ttu-id="54f43-167">**Ponechať jednotlivé plány**: Zachovanie predtým definovaného plánu pre vybrané exporty a iba ich zakázanie alebo povolenie.</span><span class="sxs-lookup"><span data-stu-id="54f43-167">**Keep individual schedules**: Persist the previously defined schedule for the selected exports and only disable or enable them.</span></span>
- <span data-ttu-id="54f43-168">**Definovať nový plán pre všetky vybraté exporty**: Prepísanie existujúcich plánov vybratých exportov.</span><span class="sxs-lookup"><span data-stu-id="54f43-168">**Define new schedule for all selected exports**: Override the existing schedules of the selected exports.</span></span>

### <a name="run-exports-on-demand"></a><span data-ttu-id="54f43-169">Spúšťanie exportov na požiadanie</span><span class="sxs-lookup"><span data-stu-id="54f43-169">Run exports on demand</span></span>

<span data-ttu-id="54f43-170">Ak chcete exportovať údaje bez čakania na plánované obnovenie, prejdite na **Údaje** > **Exporty**.</span><span class="sxs-lookup"><span data-stu-id="54f43-170">To export data without waiting for a scheduled refresh, go to **Data** > **Exports**.</span></span>

- <span data-ttu-id="54f43-171">Ak chcete spustiť všetky exporty, stlačte možnosť **Spustiť všetko** na paneli príkazov.</span><span class="sxs-lookup"><span data-stu-id="54f43-171">To run all exports, select **Run all** in the command bar.</span></span> <span data-ttu-id="54f43-172">Táto akcia spustí iba exporty, ktoré majú aktívny plán.</span><span class="sxs-lookup"><span data-stu-id="54f43-172">This action will only run exports that have an active schedule.</span></span>
- <span data-ttu-id="54f43-173">Ak chcete spustiť jeden export, vyberte ho v zozname a vyberte **Spustiť** na paneli príkazov.</span><span class="sxs-lookup"><span data-stu-id="54f43-173">To run a single export, select it in the list and select **Run** in the command bar.</span></span> <span data-ttu-id="54f43-174">Takto spustíte exporty bez aktívneho plánu.</span><span class="sxs-lookup"><span data-stu-id="54f43-174">That's how you run exports with no active schedule.</span></span> 

## <a name="remove-an-export"></a><span data-ttu-id="54f43-175">Odstránenie exportu</span><span class="sxs-lookup"><span data-stu-id="54f43-175">Remove an Export</span></span>

1. <span data-ttu-id="54f43-176">Prejdite na **Údaje** > **Exporty**.</span><span class="sxs-lookup"><span data-stu-id="54f43-176">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="54f43-177">Vyberte export, ktorý chcete odstrániť.</span><span class="sxs-lookup"><span data-stu-id="54f43-177">Select the export you want to remove.</span></span>

1. <span data-ttu-id="54f43-178">Na paneli príkazov vyberte možnosť **Odstrániť**.</span><span class="sxs-lookup"><span data-stu-id="54f43-178">Select **Remove** in the command bar.</span></span>

1. <span data-ttu-id="54f43-179">Odstránenie potvrďte výberom položky **Odstrániť** na obrazovke s potvrdením.</span><span class="sxs-lookup"><span data-stu-id="54f43-179">Confirm the removal by selecting **Remove** on the confirmation screen.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
