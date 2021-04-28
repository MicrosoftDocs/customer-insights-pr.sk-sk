---
title: Prepojenia s inými službami zo služby Customer Insights.
description: Zdieľajte údaje s inými službami.
ms.date: 04/09/2021
ms.reviewer: nikeller
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 106dbc26f95b309821d738e1484b1eaa79dd225b
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896116"
---
# <a name="connections-preview-overview"></a><span data-ttu-id="829a9-103">Prehľad pripojení (ukážka)</span><span class="sxs-lookup"><span data-stu-id="829a9-103">Connections (preview) overview</span></span>

<span data-ttu-id="829a9-104">Pripojenia sú kľúčom na umožnenie zdieľania údajov smerom do a z Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="829a9-104">Connections are the key to enable data sharing to and from Customer Insights.</span></span> <span data-ttu-id="829a9-105">Každé pripojenie ustanovuje zdieľanie údajov s konkrétnou službou.</span><span class="sxs-lookup"><span data-stu-id="829a9-105">Each connection establishes data sharing with a specific service.</span></span> <span data-ttu-id="829a9-106">Spojenia sú základom pre [konfiguráciu obohatenia tretích strán](enrichment-hub.md) a [konfiguráciu exportov](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="829a9-106">Connections are the foundation to [configure third-party enrichments](enrichment-hub.md) and [configure exports](export-destinations.md).</span></span> <span data-ttu-id="829a9-107">Rovnaké pripojenie je možné použiť viackrát.</span><span class="sxs-lookup"><span data-stu-id="829a9-107">The same connection can be used multiple times.</span></span> <span data-ttu-id="829a9-108">Napríklad jedno pripojenie k Dynamics 365 Marketing funguje pre viac exportov a jedno pripojenie Leadspace je možné použiť pre niekoľko obohatení.</span><span class="sxs-lookup"><span data-stu-id="829a9-108">For example, one connection to Dynamics 365 Marketing works for multiple exports and one Leadspace connection can be used for several enrichments.</span></span>

<span data-ttu-id="829a9-109">Prejdite na **Správca** > **Pripojenia** na vytváranie a prezeranie pripojení.</span><span class="sxs-lookup"><span data-stu-id="829a9-109">Go to **Admin** > **Connections** to create and view connections.</span></span>

<span data-ttu-id="829a9-110">Karta **Pripojenia** zobrazuje všetky aktívne pripojenia.</span><span class="sxs-lookup"><span data-stu-id="829a9-110">The **Connections** tab shows you all active connections.</span></span> <span data-ttu-id="829a9-111">Zoznam zobrazuje riadok pre každé pripojenie.</span><span class="sxs-lookup"><span data-stu-id="829a9-111">The list shows a row for each connection.</span></span> 

<span data-ttu-id="829a9-112">Získajte rýchly prehľad, popis a zistite, čo môžete robiť s každou možnosťou rozšíriteľnosti na karte **Objavovať**.</span><span class="sxs-lookup"><span data-stu-id="829a9-112">Get a quick overview, description, and find out what you can do with each extensibility option on the **Discover** tab.</span></span>

### <a name="exports"></a><span data-ttu-id="829a9-113">Exporty</span><span class="sxs-lookup"><span data-stu-id="829a9-113">Exports</span></span>

<span data-ttu-id="829a9-114">Iba správcovia môžu konfigurovať nové pripojenia, môžu však prispievateľom udeliť prístup k použitiu existujúcich pripojení.</span><span class="sxs-lookup"><span data-stu-id="829a9-114">Only administrators can configure new connections but they can grant access to contributors to use existing connections.</span></span> <span data-ttu-id="829a9-115">Správcovia kontrolujú, kam môžu údaje smerovať, prispievatelia definujú užitočné zaťaženie a frekvenciu zodpovedajúcu ich potrebám.</span><span class="sxs-lookup"><span data-stu-id="829a9-115">Administrators control where data can go, contributors define the payload and frequency fitting their needs.</span></span> <span data-ttu-id="829a9-116">Viac informácií nájdete v časti [Umožnite prispievateľom použiť pripojenie na export](#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="829a9-116">For more information, see [Allow contributors to use a connection for exports](#allow-contributors-to-use-a-connection-for-exports).</span></span>

### <a name="enrichments"></a><span data-ttu-id="829a9-117">Obohatenia</span><span class="sxs-lookup"><span data-stu-id="829a9-117">Enrichments</span></span>

<span data-ttu-id="829a9-118">Iba správcovia môžu konfigurovať nové pripojenia, ale vytvorené pripojenia sú vždy k dispozícii správcom aj prispievateľom.</span><span class="sxs-lookup"><span data-stu-id="829a9-118">Only administrators can configure new connections but the created connections are always available to both administrators and contributors.</span></span> <span data-ttu-id="829a9-119">Správcovia spravujú poverenia a udeľujú súhlas s prenosmi údajov.</span><span class="sxs-lookup"><span data-stu-id="829a9-119">Administrators manage credentials and give consent to data transfers.</span></span> <span data-ttu-id="829a9-120">Pripojenia možno použiť na obohatenie správcov aj prispievateľov.</span><span class="sxs-lookup"><span data-stu-id="829a9-120">The connections can then be used for enrichments by both administrators and contributors.</span></span>

## <a name="add-a-new-connection"></a><span data-ttu-id="829a9-121">Pridať nové pripojenie</span><span class="sxs-lookup"><span data-stu-id="829a9-121">Add a new connection</span></span>

<span data-ttu-id="829a9-122">Ak chcete pridať pripojenia, musíte mať [oprávnenia správcu](permissions.md).</span><span class="sxs-lookup"><span data-stu-id="829a9-122">To add connections, you need to have [administrator permissions](permissions.md).</span></span> <span data-ttu-id="829a9-123">Ak sa pripájate k iným službám spoločnosti Microsoft, predpokladáme, že obe služby sú v rovnakej organizácii.</span><span class="sxs-lookup"><span data-stu-id="829a9-123">If you connect to other Microsoft services, we assume both services are in the same organization.</span></span>

1. <span data-ttu-id="829a9-124">Prejdite do časti **Správca** > **Pripojenia (ukážka)**.</span><span class="sxs-lookup"><span data-stu-id="829a9-124">Go to **Admin** > **Connections (preview)**.</span></span>

1. <span data-ttu-id="829a9-125">Prejdite na kartu **Pripojenia**.</span><span class="sxs-lookup"><span data-stu-id="829a9-125">Go to the **Connections** tab.</span></span>

1. <span data-ttu-id="829a9-126">Ak chcete vytvoriť nové pripojenie, vyberte **Pridať pripojenie**.</span><span class="sxs-lookup"><span data-stu-id="829a9-126">Select **Add connection** to create a new connection.</span></span> <span data-ttu-id="829a9-127">Z rozbaľovacej ponuky vyberte, aký typ pripojenia chcete vytvoriť.</span><span class="sxs-lookup"><span data-stu-id="829a9-127">Choose from the drop-down menu what type of connection you want to create.</span></span>

1. <span data-ttu-id="829a9-128">V table **Nastaviť pripojenie** zadajte požadované podrobnosti.</span><span class="sxs-lookup"><span data-stu-id="829a9-128">In the **Set up connection** pane, provide the required details.</span></span> 
   1. <span data-ttu-id="829a9-129">**Zobrazovaný názov** a typ spojenia popisujú spojenie.</span><span class="sxs-lookup"><span data-stu-id="829a9-129">The **Display name** and the type of the connection describe a connection.</span></span> <span data-ttu-id="829a9-130">Odporúčame zvoliť názov, ktorý vysvetľuje účel a cieľ tohto spojenia.</span><span class="sxs-lookup"><span data-stu-id="829a9-130">We recommend choosing a name that explains the purpose and target of this connection.</span></span>
   1. <span data-ttu-id="829a9-131">Presné polia závisia od toho, ku ktorej službe sa pripájate.</span><span class="sxs-lookup"><span data-stu-id="829a9-131">The exact fields depend on what service you are connecting to.</span></span> <span data-ttu-id="829a9-132">V článku o cieľovej službe sa môžete dozvedieť viac podrobností o konkrétnom type pripojenia.</span><span class="sxs-lookup"><span data-stu-id="829a9-132">You can learn about details of a specific connection type in the article about the target service.</span></span>

1. <span data-ttu-id="829a9-133">Na vytvorenie pripojenia stlačte možnosť **Uložiť**.</span><span class="sxs-lookup"><span data-stu-id="829a9-133">To create the connection, select **Save**.</span></span>

<span data-ttu-id="829a9-134">Môžete tiež vybrať **Nastaviť** na dlaždici na karte **Objavovať**.</span><span class="sxs-lookup"><span data-stu-id="829a9-134">You can also select **Set up** on a tile on the **Discover** tab.</span></span>

### <a name="allow-contributors-to-use-a-connection-for-exports"></a><span data-ttu-id="829a9-135">Umožnite prispievateľom použiť pripojenie na exportovania</span><span class="sxs-lookup"><span data-stu-id="829a9-135">Allow contributors to use a connection for exports</span></span>

<span data-ttu-id="829a9-136">Pri nastavovaní alebo úprave exportného pripojenia si vyberáte, ktorí používatelia majú povolené toto konkrétne pripojenie na definovanie [exportov](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="829a9-136">When setting up or editing an export connection, you choose which users are allowed to use this specific connection to define [exports](export-destinations.md).</span></span> <span data-ttu-id="829a9-137">V predvolenom nastavení je pripojenie k dispozícii používateľom s rolou správcu.</span><span class="sxs-lookup"><span data-stu-id="829a9-137">By default a connection is available to users with an administrator role.</span></span> <span data-ttu-id="829a9-138">Toto nastavenie môžete zmeniť v časti **Vyberte používateľov, ktorí môžu používať toto pripojenie** a umožniť používateľom s rolou prispievateľa používať toto pripojenie.</span><span class="sxs-lookup"><span data-stu-id="829a9-138">You can change this setting under **Choose who can use this connection** and allow users with contributor role to use this connection.</span></span>

- <span data-ttu-id="829a9-139">Prispievatelia nebudú môcť zobraziť ani upraviť pripojenie.</span><span class="sxs-lookup"><span data-stu-id="829a9-139">Contributors won't be able to view or edit the connection.</span></span> <span data-ttu-id="829a9-140">Zobrazený názov a jeho typ sa im zobrazí iba pri vytváraní exportu.</span><span class="sxs-lookup"><span data-stu-id="829a9-140">They will only see the display name and its type when creating an export.</span></span>
- <span data-ttu-id="829a9-141">Zdieľaním pripojenia umožňujete prispievateľom používať pripojenie.</span><span class="sxs-lookup"><span data-stu-id="829a9-141">By sharing a connection, you allow contributors to use a connection.</span></span> <span data-ttu-id="829a9-142">Prispievateľom sa po nastavení exportu zobrazia zdieľané pripojenia.</span><span class="sxs-lookup"><span data-stu-id="829a9-142">Contributors will see shared connections when they set up exports.</span></span> <span data-ttu-id="829a9-143">Môžu spravovať každý export, ktorý používa toto konkrétne pripojenie.</span><span class="sxs-lookup"><span data-stu-id="829a9-143">They can manage every export that uses this specific connection.</span></span>
- <span data-ttu-id="829a9-144">Toto nastavenie môžete zmeniť pri zachovaní exportov, ktoré už boli definované prispievateľmi.</span><span class="sxs-lookup"><span data-stu-id="829a9-144">You can change this setting while keeping the exports that have already been defined by contributors.</span></span>

## <a name="edit-a-connection"></a><span data-ttu-id="829a9-145">Upraviť pripojenie</span><span class="sxs-lookup"><span data-stu-id="829a9-145">Edit a connection</span></span>

1. <span data-ttu-id="829a9-146">Prejdite do časti **Správca** > **Pripojenia (ukážka)**.</span><span class="sxs-lookup"><span data-stu-id="829a9-146">Go to **Admin** > **Connections (preview)**.</span></span>

1. <span data-ttu-id="829a9-147">Prejdite na kartu **Pripojenia**.</span><span class="sxs-lookup"><span data-stu-id="829a9-147">Go to the **Connections** tab.</span></span>

1. <span data-ttu-id="829a9-148">Vyberte zvislé tri bodky pri pripojení, ktoré chcete upraviť.</span><span class="sxs-lookup"><span data-stu-id="829a9-148">Select the vertical ellipsis for the connection you want to edit.</span></span>

1. <span data-ttu-id="829a9-149">Vyberte **Upraviť**.</span><span class="sxs-lookup"><span data-stu-id="829a9-149">Select **Edit**.</span></span>

1. <span data-ttu-id="829a9-150">Zmeňte hodnoty, ktoré chcete aktualizovať, a stlačte možnosť **Uložiť**.</span><span class="sxs-lookup"><span data-stu-id="829a9-150">Change the values you want to update and select **Save**.</span></span>

## <a name="remove-a-connection"></a><span data-ttu-id="829a9-151">Odstrániť pripojenie</span><span class="sxs-lookup"><span data-stu-id="829a9-151">Remove a connection</span></span>

<span data-ttu-id="829a9-152">Ak je pripojenie, ktoré odstraňujete, obohatené alebo exportované, musíte ich najskôr odpojiť alebo odstrániť.</span><span class="sxs-lookup"><span data-stu-id="829a9-152">If the connection you are removing is used by enrichments or exports, you first need to detach or remove them.</span></span> <span data-ttu-id="829a9-153">Dialógové okno odstránenia vás prevedie príslušným obohatením alebo exportom.</span><span class="sxs-lookup"><span data-stu-id="829a9-153">The remove dialog will guide you to the relevant enrichments or exports.</span></span> <span data-ttu-id="829a9-154">Oddelené obohatenia a exporty sa stanú neaktívnymi.</span><span class="sxs-lookup"><span data-stu-id="829a9-154">Detached enrichments and exports become inactive.</span></span> <span data-ttu-id="829a9-155">Znova ich aktivujete pridaním ďalšieho spojenia na ne na stránke [Obohatenia](enrichment-hub.md) alebo[Exporty](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="829a9-155">You reactivate them by adding another connection to them on the [Enrichments](enrichment-hub.md) or [Exports](export-destinations.md) page.</span></span>

1. <span data-ttu-id="829a9-156">Prejdite do časti **Správca** > **Pripojenia (ukážka)**.</span><span class="sxs-lookup"><span data-stu-id="829a9-156">Go to **Admin** > **Connections (preview)**.</span></span>

1. <span data-ttu-id="829a9-157">Prejdite na kartu **Pripojenia**.</span><span class="sxs-lookup"><span data-stu-id="829a9-157">Go to the **Connections** tab.</span></span>

1. <span data-ttu-id="829a9-158">Vyberte zvislé tri bodky pri pripojení, ktoré chcete odstrániť.</span><span class="sxs-lookup"><span data-stu-id="829a9-158">Select the vertical ellipsis for the connection you want to remove.</span></span>

1. <span data-ttu-id="829a9-159">Vyberte položku **Odstrániť** z rozbaľovacej ponuky.</span><span class="sxs-lookup"><span data-stu-id="829a9-159">Select **Remove** from the dropdown menu.</span></span> <span data-ttu-id="829a9-160">Zobrazí sa dialógové okno s potvrdením.</span><span class="sxs-lookup"><span data-stu-id="829a9-160">A confirmation dialog appears.</span></span>

   1. <span data-ttu-id="829a9-161">Ak pomocou tohto pripojenia existujú obohatenia alebo exporty, kliknutím na toto tlačidlo zobrazíte informácie o tom, čo toto pripojenie využíva.</span><span class="sxs-lookup"><span data-stu-id="829a9-161">If there are enrichments or exports using this connection, select the button to see what's using the connection.</span></span>
      - <span data-ttu-id="829a9-162">**Exporty:** Môžete si vybrať, či chcete odstrániť alebo odpojiť exporty, aby ste mohli pripojenie odstrániť.</span><span class="sxs-lookup"><span data-stu-id="829a9-162">**Exports:** You can choose to either remove or disconnect the exports to be able to remove the connection.</span></span> <span data-ttu-id="829a9-163">Na odpojenie exportu môžu správcovia použiť akciu **Odpojiť**.</span><span class="sxs-lookup"><span data-stu-id="829a9-163">To disconnect an export, administrators can use the **Disconnect** action.</span></span> <span data-ttu-id="829a9-164">Táto akcia je k dispozícii pre jednotlivé a viaceré vybrané exporty.</span><span class="sxs-lookup"><span data-stu-id="829a9-164">This action is available for individual and multiple selected exports.</span></span> <span data-ttu-id="829a9-165">Odpojením si ponecháte konfiguráciu exportu, ale nespustí sa, kým k nej nepridáte ďalšie pripojenie.</span><span class="sxs-lookup"><span data-stu-id="829a9-165">By disconnecting you keep the export config, but it won't be run until another connection is added to it.</span></span>
      - <span data-ttu-id="829a9-166">**Obohatenia:** Môžete si vybrať, či chcete odstrániť alebo deaktivovať obohatenia, aby ste mohli pripojenie odstrániť.</span><span class="sxs-lookup"><span data-stu-id="829a9-166">**Enrichments:** You can choose to either remove or deactivate the enrichments to be able to remove the connection.</span></span> 
   1. <span data-ttu-id="829a9-167">Keď už pripojenie nemá žiadne ďalšie závislosti, vráťte sa späť na časť **Správca** > **Pripojenia** a skúste pripojenie znova odstrániť.</span><span class="sxs-lookup"><span data-stu-id="829a9-167">Once the connection has no more dependencies, go back to **Admin** > **Connections** and try removing the connection again.</span></span>

1. <span data-ttu-id="829a9-168">Na potvrdenie odstránenia stlačte možnosť **Odstrániť**.</span><span class="sxs-lookup"><span data-stu-id="829a9-168">To confirm the deletion select **Remove**.</span></span>

