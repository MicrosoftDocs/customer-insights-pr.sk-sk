---
title: Export údajov Customer Insights do Azure Synapse Analytics
description: Zistite ako nakonfigurovať pripojenie a realizovať exportovanie do Azure Synapse Analytics.
ms.date: 04/12/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 822082d661863e737ea3d3a749a6c878db766967
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 05/04/2021
ms.locfileid: "5977396"
---
# <a name="export-data-to-azure-synapse-analytics-preview"></a><span data-ttu-id="dbaf1-103">Exportovanie údajov do Azure Synapse Analytics (verzia Preview)</span><span class="sxs-lookup"><span data-stu-id="dbaf1-103">Export data to Azure Synapse Analytics (Preview)</span></span>

<span data-ttu-id="dbaf1-104">Azure Synapse je analytická služba, ktorá urýchľuje čas na získanie prehľadu o dátových skladoch a systémoch veľkých údajov.</span><span class="sxs-lookup"><span data-stu-id="dbaf1-104">Azure Synapse is an analytics service that accelerates time to insight across data warehouses and big data systems.</span></span> <span data-ttu-id="dbaf1-105">Údaje služby Customer Insights môžete prijímať a používať v aplikácii [Azure Synapse](/azure/synapse-analytics/overview-what-is).</span><span class="sxs-lookup"><span data-stu-id="dbaf1-105">You can ingest and use your Customer Insights data in [Azure Synapse](/azure/synapse-analytics/overview-what-is).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="dbaf1-106">Predpoklady</span><span class="sxs-lookup"><span data-stu-id="dbaf1-106">Prerequisites</span></span>

<span data-ttu-id="dbaf1-107">Nasledujúce predpoklady musia byť splnené, aby bolo možné nakonfigurovať pripojenie od Customer Insights k Azure Synapse.</span><span class="sxs-lookup"><span data-stu-id="dbaf1-107">The following prerequisites must be met to configure the connection from Customer Insights to Azure Synapse.</span></span>

> [!NOTE]
> <span data-ttu-id="dbaf1-108">Nezabudnite nastaviť všetky **priradenia rolí**, ako je opísané.</span><span class="sxs-lookup"><span data-stu-id="dbaf1-108">Make sure to set all **role assignments** as described.</span></span>  

## <a name="prerequisites-in-customer-insights"></a><span data-ttu-id="dbaf1-109">Požiadavky v Customer Insights</span><span class="sxs-lookup"><span data-stu-id="dbaf1-109">Prerequisites in Customer Insights</span></span>

* <span data-ttu-id="dbaf1-110">Máte rolu **Správca** v prehľadoch cieľovej skupiny.</span><span class="sxs-lookup"><span data-stu-id="dbaf1-110">You have an **Administrator** role in audience insights.</span></span> <span data-ttu-id="dbaf1-111">Prečítajte si viac o [nastavení povolení používateľa v prehľadoch cieľovej skupiny](permissions.md#assign-roles-and-permissions)</span><span class="sxs-lookup"><span data-stu-id="dbaf1-111">Learn more about [setting user permissions in audience insights](permissions.md#assign-roles-and-permissions)</span></span>

<span data-ttu-id="dbaf1-112">V Azure:</span><span class="sxs-lookup"><span data-stu-id="dbaf1-112">In Azure:</span></span> 

- <span data-ttu-id="dbaf1-113">Aktívne predplatné služieb Azure.</span><span class="sxs-lookup"><span data-stu-id="dbaf1-113">An active Azure subscription.</span></span>

- <span data-ttu-id="dbaf1-114">Ak používate nový účet Azure Data Lake Storage Gen2, *vedúci služby pre prehľady cieľovej skupiny* potrebuje povolenia **Prispievateľ údajov do objektu BLOB úložiska**.</span><span class="sxs-lookup"><span data-stu-id="dbaf1-114">If using a new Azure Data Lake Storage Gen2 account, the *service principal for audience insights* needs **Storage Blob Data Contributor** permissions.</span></span> <span data-ttu-id="dbaf1-115">Viac informácií nájdete v časti [pripojenie k účtu Azure Data Lake Storage Gen2 s vedúcim služby Azure pre prehľady cieľovej skupiny](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="dbaf1-115">Learn more on [connecting to an Azure Data Lake Storage Gen2 account with Azure service principal for audience insights](connect-service-principal.md).</span></span> <span data-ttu-id="dbaf1-116">Úložisko Data Lake Storage Gen2 **musí mať** povolenú možnosť [hierarchický názov](/azure/storage/blobs/data-lake-storage-namespace).</span><span class="sxs-lookup"><span data-stu-id="dbaf1-116">The Data Lake Storage Gen2 **must have** [hierarchical namespace](/azure/storage/blobs/data-lake-storage-namespace) enabled.</span></span>

- <span data-ttu-id="dbaf1-117">V skupine zdrojov Azure Synapse sa nachádza pracovný priestor, *objekt služby* a *používateľ pre prehľady cieľovej skupiny* musia mať priradené minimálne povolenie **Čitateľ**.</span><span class="sxs-lookup"><span data-stu-id="dbaf1-117">On the resource group the Azure Synapse workspace is located, the *service principal* and the *user for audience insights* needs to be assigned at least **Reader** permissions.</span></span> <span data-ttu-id="dbaf1-118">Viac informácií nájdete v časti [Priradiť roly Azure pomocou portálu Azure Portal](/azure/role-based-access-control/role-assignments-portal).</span><span class="sxs-lookup"><span data-stu-id="dbaf1-118">For more information, see [Assign Azure roles using the Azure portal](/azure/role-based-access-control/role-assignments-portal).</span></span>

- <span data-ttu-id="dbaf1-119">*Používateľ* potrebuje povolenia **Prispievateľ údajov do objektu BLOB úložiska** v účte Azure Data Lake Storage Gen2, kde sa nachádzajú údaje a sú prepojené s účtom pracovného priestoru Azure Synapse.</span><span class="sxs-lookup"><span data-stu-id="dbaf1-119">The *user* needs **Storage Blob Data Contributor** permissions on the Azure Data Lake Storage Gen2 account where the data is located and linked to the Azure Synapse workspace.</span></span> <span data-ttu-id="dbaf1-120">Prečítajte si viac o [používaní portálu Azure Portal na priradenie roly Azure pre prístup k údajom blob a frontu](/azure/storage/common/storage-auth-aad-rbac-portal) a [Povolenia Prispievateľ údajov do objektu BLOB úložiska](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).</span><span class="sxs-lookup"><span data-stu-id="dbaf1-120">Learn more about [using the Azure portal to assign an Azure role for access to blob and queue data](/azure/storage/common/storage-auth-aad-rbac-portal) and [Storage Blob Data Contributor permissions](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).</span></span>

- <span data-ttu-id="dbaf1-121">*[Spravovaná identita pracovného priestoru Azure Synapse](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* potrebuje povolenia **Prispievateľ údajov do objektu BLOB úložiska** v účte Azure Data Lake Storage Gen2, kde sa údaje nachádzajú a sú prepojené na pracovisko Azure Synapse.</span><span class="sxs-lookup"><span data-stu-id="dbaf1-121">The *[Azure Synapse workspace managed identity](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* needs **Storage Blob Data Contributor** permissions on the Azure Data Lake Storage Gen2 account where the data is located and linked to the Azure Synapse workspace.</span></span> <span data-ttu-id="dbaf1-122">Prečítajte si viac o [používaní portálu Azure Portal na priradenie roly Azure pre prístup k údajom blob a frontu](/azure/storage/common/storage-auth-aad-rbac-portal) a [Povolenia Prispievateľ údajov do objektu BLOB úložiska](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).</span><span class="sxs-lookup"><span data-stu-id="dbaf1-122">Learn more on [using the Azure portal to assign an Azure role for access to blob and queue data](/azure/storage/common/storage-auth-aad-rbac-portal) and [Storage Blob Data Contributor permissions](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).</span></span>

- <span data-ttu-id="dbaf1-123">V pracovnom priestore Azure Synapse musí mať *objekt služby pre prehľady cieľových skupín* priradenú rolu **Správca služby Synapse**.</span><span class="sxs-lookup"><span data-stu-id="dbaf1-123">On the Azure Synapse workspace, the *service principal for audience insights* needs **Synapse Administrator** role assigned.</span></span> <span data-ttu-id="dbaf1-124">Viac informácií nájdete v časti [Ako nastaviť riadenie prístupu pre váš pracovný priestor služby Synapse](/azure/synapse-analytics/security/how-to-set-up-access-control).</span><span class="sxs-lookup"><span data-stu-id="dbaf1-124">For more information, see [How to set up access control for your Synapse workspace](/azure/synapse-analytics/security/how-to-set-up-access-control).</span></span>

## <a name="set-up-the-connection-and-export-to-azure-synapse"></a><span data-ttu-id="dbaf1-125">Príprava pripojenia a exportovania do Azure Synapse</span><span class="sxs-lookup"><span data-stu-id="dbaf1-125">Set up the connection and export to Azure Synapse</span></span>

### <a name="configure-a-connection"></a><span data-ttu-id="dbaf1-126">Konfigurácia a pripojenie</span><span class="sxs-lookup"><span data-stu-id="dbaf1-126">Configure a connection</span></span>

1. <span data-ttu-id="dbaf1-127">Prejdite do časti **Správca** > **Pripojenia**.</span><span class="sxs-lookup"><span data-stu-id="dbaf1-127">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="dbaf1-128">Stlačte možnosť **Pridať pripojenie** a stlačte **Azure Synapse Analytics**, prípadne stlačte možnosť **Nastaviť** na dlaždici **Azure Synapse Analytics** na konfiguráciu pripojenia.</span><span class="sxs-lookup"><span data-stu-id="dbaf1-128">Select **Add connection** and choose **Azure Synapse Analytics** or select the **Set up** on the **Azure Synapse Analytics** tile to configure the connection.</span></span>

1. <span data-ttu-id="dbaf1-129">Do poľa Zobrazovaný názov zadajte rozpoznateľný názov pripojenia.</span><span class="sxs-lookup"><span data-stu-id="dbaf1-129">Give your connection a recognizable name in the Display name field.</span></span> <span data-ttu-id="dbaf1-130">Zobrazovaný názov a typ spojenia, ktoré popisuje toto spojenie.</span><span class="sxs-lookup"><span data-stu-id="dbaf1-130">The name and the type of the connection describes this connection.</span></span> <span data-ttu-id="dbaf1-131">Odporúčame zvoliť názov, ktorý vysvetľuje účel a cieľ tohto spojenia.</span><span class="sxs-lookup"><span data-stu-id="dbaf1-131">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="dbaf1-132">Vyberte používateľov, ktorí môžu používať toto pripojenie.</span><span class="sxs-lookup"><span data-stu-id="dbaf1-132">Choose who can use this connection.</span></span> <span data-ttu-id="dbaf1-133">Ak neurobíte nič, predvolená hodnota bude Správcovia.</span><span class="sxs-lookup"><span data-stu-id="dbaf1-133">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="dbaf1-134">Viac informácií nájdete v časti [Umožnite prispievateľom použiť pripojenie na export](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="dbaf1-134">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="dbaf1-135">Vyberte alebo vyhľadajte predplatné, v ktorom chcete použiť údaje Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="dbaf1-135">Select or search for the subscription you want to use the Customer Insights data in.</span></span> <span data-ttu-id="dbaf1-136">Hneď ako vyberiete predplatné, môžete tiež zvoliť **Pracovný priestor**, **Účet úložiska** a **Kontajner**.</span><span class="sxs-lookup"><span data-stu-id="dbaf1-136">As soon as a subscription is selected, you can also select **Workspace**, **Storage account**, and **Container**.</span></span>

1. <span data-ttu-id="dbaf1-137">Stlačením možnosti **Uložiť** uložíte pripojenie.</span><span class="sxs-lookup"><span data-stu-id="dbaf1-137">Select **Save** to save the connection.</span></span>

### <a name="configure-an-export"></a><span data-ttu-id="dbaf1-138">Nakonfigurujte export</span><span class="sxs-lookup"><span data-stu-id="dbaf1-138">Configure an export</span></span>

<span data-ttu-id="dbaf1-139">Tento export môžete nakonfigurovať, ak máte prístup k pripojeniu tohto typu.</span><span class="sxs-lookup"><span data-stu-id="dbaf1-139">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="dbaf1-140">Viac informácií nájdete na stránke [Na konfiguráciu exportu sú potrebné povolenia](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="dbaf1-140">For more information, see [permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="dbaf1-141">Prejdite na **Údaje** > **Exporty**.</span><span class="sxs-lookup"><span data-stu-id="dbaf1-141">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="dbaf1-142">Na vytvorenie nového exportu stlačte možnosť **Pridať export**.</span><span class="sxs-lookup"><span data-stu-id="dbaf1-142">To create a new export, select **Add export**.</span></span>

1. <span data-ttu-id="dbaf1-143">V poli **Pripojenie na export** vyberte pripojenie v časti **Azure Synapse Analytics**.</span><span class="sxs-lookup"><span data-stu-id="dbaf1-143">In the **Connection for export** field, choose a connection from the **Azure Synapse Analytics** section.</span></span> <span data-ttu-id="dbaf1-144">Ak nevidíte názov tejto sekcie, nemáte k dispozícii žiadne [spojenia](connections.md) tohto typu.</span><span class="sxs-lookup"><span data-stu-id="dbaf1-144">If you don't see this section name, there are no [connections](connections.md) of this type available to you.</span></span>

1. <span data-ttu-id="dbaf1-145">Poskytnite rozoznateľný **Zobrazovaný názov** pre váš export a **Názov databázy**.</span><span class="sxs-lookup"><span data-stu-id="dbaf1-145">Provide a recognizable **Display name** for your export and a **Database name**.</span></span>

1. <span data-ttu-id="dbaf1-146">Vyberte entity, do ktorých chcete exportovať Azure Synapse Analytics.</span><span class="sxs-lookup"><span data-stu-id="dbaf1-146">Select which entities you want to export to Azure Synapse Analytics.</span></span>

1. <span data-ttu-id="dbaf1-147">Vyberte položku **Uložiť**.</span><span class="sxs-lookup"><span data-stu-id="dbaf1-147">Select **Save**.</span></span>

<span data-ttu-id="dbaf1-148">Uloženie exportu nespustí export okamžite.</span><span class="sxs-lookup"><span data-stu-id="dbaf1-148">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="dbaf1-149">Export prebieha s každým [plánovaným obnovením](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="dbaf1-149">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="dbaf1-150">Môžete tiež [exportovať údaje na požiadanie](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="dbaf1-150">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span>

### <a name="update-an-export"></a><span data-ttu-id="dbaf1-151">Aktualizujte export</span><span class="sxs-lookup"><span data-stu-id="dbaf1-151">Update an export</span></span>

1. <span data-ttu-id="dbaf1-152">Prejdite na **Údaje** > **Exporty**.</span><span class="sxs-lookup"><span data-stu-id="dbaf1-152">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="dbaf1-153">Pri export, ktorý chcete aktualizovať, stlačte možnosť **Upraviť**.</span><span class="sxs-lookup"><span data-stu-id="dbaf1-153">Select **Edit** on the export you want to update.</span></span>

   - <span data-ttu-id="dbaf1-154">**Pridajte** alebo **Odstráňte** entity z výberu.</span><span class="sxs-lookup"><span data-stu-id="dbaf1-154">**Add** or **Remove** entities from the selection.</span></span> <span data-ttu-id="dbaf1-155">Ak sú entity z výberu odstránené, neodstránia sa z databázy Synapse Analytics.</span><span class="sxs-lookup"><span data-stu-id="dbaf1-155">If entities are removed from the selection, they aren't deleted from the Synapse Analytics database.</span></span> <span data-ttu-id="dbaf1-156">Budúce obnovenie údajov však neaktualizuje odstránené entity v tejto databáze.</span><span class="sxs-lookup"><span data-stu-id="dbaf1-156">However, future data refreshes won't update the removed entities in that database.</span></span>

   - <span data-ttu-id="dbaf1-157">**Zmena názvu databázy** vytvára novú databázu Synapse Analytics.</span><span class="sxs-lookup"><span data-stu-id="dbaf1-157">**Changing the Database Name** creates a new Synapse Analytics database.</span></span> <span data-ttu-id="dbaf1-158">Databáza s názvom, ktorý bol nakonfigurovaný predtým, nebude v budúcich aktualizáciách dostávať žiadne aktualizácie.</span><span class="sxs-lookup"><span data-stu-id="dbaf1-158">The database with the name that was configured before won't receive any updates in future refreshes.</span></span>
