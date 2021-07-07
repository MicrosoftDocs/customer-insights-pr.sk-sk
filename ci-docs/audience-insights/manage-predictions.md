---
title: Zdieľané úlohy pre scenáre predikcia
description: Naučte sa, ako spravovať, riešiť problémy a vylepšovať predikcie.
ms.date: 05/17/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: diegogranados117
ms.author: digranad
manager: shellyha
ms.openlocfilehash: dccb8dcca8f65f64973e46fed9d83034d58282e2
ms.sourcegitcommit: bcc47d15d4f0eacf008e4dbc09baac7f062b3ca8
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 06/29/2021
ms.locfileid: "6315897"
---
# <a name="manage-predictions"></a><span data-ttu-id="e1a00-103">Spravovanie predikcií</span><span class="sxs-lookup"><span data-stu-id="e1a00-103">Manage predictions</span></span>

<span data-ttu-id="e1a00-104">Tento článok píše o úlohách, ktoré zdieľa väčšina scenárov predikcií.</span><span class="sxs-lookup"><span data-stu-id="e1a00-104">This article discusses some tasks that most prediction scenarios share.</span></span>

## <a name="troubleshoot-a-failed-prediction"></a><span data-ttu-id="e1a00-105">Riešenie problémov so zlyhaním predikcie</span><span class="sxs-lookup"><span data-stu-id="e1a00-105">Troubleshoot a failed prediction</span></span>

1. <span data-ttu-id="e1a00-106">Prejdite do ponuky **Analýza** > **Predikcie** a vyberte kartu **Moje predikcie**.</span><span class="sxs-lookup"><span data-stu-id="e1a00-106">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="e1a00-107">Vyberte zvislé tri bodky vedľa predikcie, pre ktorú chcete zobraziť protokoly chýb.</span><span class="sxs-lookup"><span data-stu-id="e1a00-107">Select the vertical ellipses next to the prediction you want to view error logs for.</span></span>

1. <span data-ttu-id="e1a00-108">Vyberte **Záznamy**.</span><span class="sxs-lookup"><span data-stu-id="e1a00-108">Select **Logs**.</span></span>

1. <span data-ttu-id="e1a00-109">Skontrolujte všetky chyby.</span><span class="sxs-lookup"><span data-stu-id="e1a00-109">Review all the errors.</span></span> <span data-ttu-id="e1a00-110">Môže sa vyskytnúť niekoľko typov chýb, ktoré popisujú, ktorý stav chybu spôsobil.</span><span class="sxs-lookup"><span data-stu-id="e1a00-110">There are several types of errors that can occur, and they describe what condition caused the error.</span></span> <span data-ttu-id="e1a00-111">Napríklad chyba, že nie je dostatok údajov na presnú predikciu, sa zvyčajne vyrieši načítaním ďalších údajov do Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="e1a00-111">For example, an error that there's not enough data to accurately predict is typically resolved by loading additional data into Customer Insights.</span></span>

## <a name="input-data-usability-report"></a><span data-ttu-id="e1a00-112">Zostava použiteľnosti vstupných údajov</span><span class="sxs-lookup"><span data-stu-id="e1a00-112">Input data usability report</span></span>

<span data-ttu-id="e1a00-113">Zostava o použiteľnosti vstupných údajov poskytuje konsolidovaný prehľad o chybách a varovaniach, ktoré môžu generovať vaše vopred pripravené predikcie.</span><span class="sxs-lookup"><span data-stu-id="e1a00-113">The input data usability report provides a consolidated view of the errors and warnings that your out-of-box predictions may be generating.</span></span> <span data-ttu-id="e1a00-114">Poskytuje tiež odporúčania, ako zlepšiť výkon modelu.</span><span class="sxs-lookup"><span data-stu-id="e1a00-114">It also gives recommendations how to improve the model performance.</span></span>

<span data-ttu-id="e1a00-115">Zostava je k dispozícii po dokončení tréningového procesu modelu.</span><span class="sxs-lookup"><span data-stu-id="e1a00-115">The report is available after a model has completed its training process.</span></span> <span data-ttu-id="e1a00-116">Je vytvorená pre každý model zvlášť, bez ohľadu na to, či bol úspešne dokončený alebo nie.</span><span class="sxs-lookup"><span data-stu-id="e1a00-116">It's created for each model separately, regardless if it completed successfully or not.</span></span>

### <a name="view-the-input-data-usability-report"></a><span data-ttu-id="e1a00-117">Prezeranie zostavy použiteľnosti vstupných údajov</span><span class="sxs-lookup"><span data-stu-id="e1a00-117">View the input data usability report</span></span>

<span data-ttu-id="e1a00-118">Keď vopred pripravený model dokončil krok výuky, pozrite si zostavu:</span><span class="sxs-lookup"><span data-stu-id="e1a00-118">After an out-of-box model has completed its training step, view the report:</span></span>
- <span data-ttu-id="e1a00-119">Vyberte tri bodky vedľa názvu modelu a zvoľte **Zostava použiteľnosti vstupných údajov**.</span><span class="sxs-lookup"><span data-stu-id="e1a00-119">Select the ellipses next to the model name and choose **Input data usability report**.</span></span>
- <span data-ttu-id="e1a00-120">Vyberte stav modelu a **Pozrite si zostavu použiteľnosti vstupných údajov** na bočnej table.</span><span class="sxs-lookup"><span data-stu-id="e1a00-120">Select the status of a model select **See Input data usability report** in the side pane.</span></span>
- <span data-ttu-id="e1a00-121">Vyberte jeden z modelov v zozname a vyberte **Zostava použiteľnosti vstupných údajov** na paneli príkazov.</span><span class="sxs-lookup"><span data-stu-id="e1a00-121">Selecting one of the models in the list and select **Input data usability report** in the command bar.</span></span>
- <span data-ttu-id="e1a00-122">Otvorte stránku s výsledkami modelu a vyberte **Zostava použiteľnosti vstupných údajov** na paneli príkazov.</span><span class="sxs-lookup"><span data-stu-id="e1a00-122">Open the model results page and select **Input data usability report** in the command bar.</span></span>

### <a name="information-in-the-input-data-usability-report"></a><span data-ttu-id="e1a00-123">Informácie v zostave o použiteľnosti vstupných údajov</span><span class="sxs-lookup"><span data-stu-id="e1a00-123">Information in the input data usability report</span></span>

<span data-ttu-id="e1a00-124">Nasledujúce stĺpce v zostave obsahujú užitočné informácie na vylepšenie údajov pre model.</span><span class="sxs-lookup"><span data-stu-id="e1a00-124">The following columns in the report contain helpful information to improve the data for the model.</span></span>

:::image type="content" source="media/input-data-usability-report.png" alt-text="Príklad správy o použiteľnosti vstupných údajov, ktorá zobrazuje tabuľku s chybami, varovaniami a odporúčaniami.":::

- <span data-ttu-id="e1a00-126">Názov: Popisný názov chyby, varovania alebo odporúčania.</span><span class="sxs-lookup"><span data-stu-id="e1a00-126">Name: Descriptive name of the error, warning, or recommendation.</span></span>
- <span data-ttu-id="e1a00-127">Krok: Fáza, trénovanie alebo skóre modelu, ktorého sa informácie sa týkajú.</span><span class="sxs-lookup"><span data-stu-id="e1a00-127">Step: Model phase, train or score, the information refers to.</span></span>
- <span data-ttu-id="e1a00-128">Stav: Závažnosť informácií (chyba, varovanie, odporúčanie).</span><span class="sxs-lookup"><span data-stu-id="e1a00-128">State: Severity of the information (error, warning, recommendation).</span></span>
- <span data-ttu-id="e1a00-129">Názov stĺpca: Stĺpec v entite, ktorý je potrebné upraviť, aby sa zlepšil výkon modelu.</span><span class="sxs-lookup"><span data-stu-id="e1a00-129">Column name: Column in an entity that needs to be modified to improve the model performance.</span></span>
- <span data-ttu-id="e1a00-130">Názov entity: Názov entity, ktorú je potrebné upraviť, aby sa zlepšil výkon modelu.</span><span class="sxs-lookup"><span data-stu-id="e1a00-130">Entity name: Name of the entity that needs to be modified to improve the model performance.</span></span>
- <span data-ttu-id="e1a00-131">Podrobnosti: Podrobnosti o chybe, varovaní alebo odporúčaní.</span><span class="sxs-lookup"><span data-stu-id="e1a00-131">Details: Details about the error, warning, or recommendation.</span></span>

## <a name="refresh-a-prediction"></a><span data-ttu-id="e1a00-132">Obnovenie predikcie</span><span class="sxs-lookup"><span data-stu-id="e1a00-132">Refresh a prediction</span></span>

<span data-ttu-id="e1a00-133">Predikcie sa automaticky obnovujú v rovnakom [harmonogram, ako vaše údaje](system.md#schedule-tab), ako je nakonfigurované v nastaveniach.</span><span class="sxs-lookup"><span data-stu-id="e1a00-133">Predictions will automatically refresh on the same [schedule your data refreshes](system.md#schedule-tab) as configured in settings.</span></span> <span data-ttu-id="e1a00-134">Môžete ich tiež obnoviť ručne.</span><span class="sxs-lookup"><span data-stu-id="e1a00-134">You can refresh them manually too.</span></span>

1. <span data-ttu-id="e1a00-135">Prejdite do ponuky **Analýza** > **Predikcie** a vyberte kartu **Moje predikcie**.</span><span class="sxs-lookup"><span data-stu-id="e1a00-135">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="e1a00-136">Vyberte zvislé tri bodky vedľa predikcie, ktorú chcete obnoviť.</span><span class="sxs-lookup"><span data-stu-id="e1a00-136">Select the vertical ellipses next to the prediction you want to refresh.</span></span>

1. <span data-ttu-id="e1a00-137">Vyberte **Obnoviť**.</span><span class="sxs-lookup"><span data-stu-id="e1a00-137">Select **Refresh**.</span></span>

## <a name="delete-a-prediction"></a><span data-ttu-id="e1a00-138">Odstránenie predikcie</span><span class="sxs-lookup"><span data-stu-id="e1a00-138">Delete a prediction</span></span>

<span data-ttu-id="e1a00-139">Odstránenie predikcie tiež odstráni jeho výstupnú entitu.</span><span class="sxs-lookup"><span data-stu-id="e1a00-139">Deleting a prediction also removes its output entity.</span></span>

1. <span data-ttu-id="e1a00-140">Prejdite do ponuky **Analýza** > **Predikcie** a vyberte kartu **Moje predikcie**.</span><span class="sxs-lookup"><span data-stu-id="e1a00-140">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="e1a00-141">Vyberte zvislé tri bodky vedľa predikcie, ktorú chcete odstrániť.</span><span class="sxs-lookup"><span data-stu-id="e1a00-141">Select the vertical ellipses next to the prediction you want to delete.</span></span>

1. <span data-ttu-id="e1a00-142">Vyberte **Odstrániť**.</span><span class="sxs-lookup"><span data-stu-id="e1a00-142">Select **Delete**.</span></span>
