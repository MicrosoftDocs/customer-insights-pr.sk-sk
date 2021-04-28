---
title: Exportujte údaje Customer Insights do aplikácie Adobe Experience Platform
description: Naučte sa, ako používať segmenty štatistík publika v aplikácii Adobe Experience Platform.
ms.date: 03/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: 884f4d30f354bed29909d57be84dce4c8e46965a
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760120"
---
# <a name="use-customer-insights-segments-in-adobe-experience-platform-preview"></a><span data-ttu-id="51e48-103">Naučte sa, ako používať segmenty Customer Insights v Adobe Experience Platform (ukážka)</span><span class="sxs-lookup"><span data-stu-id="51e48-103">Use Customer Insights segments in Adobe Experience Platform (preview)</span></span>

<span data-ttu-id="51e48-104">Ako používateľ štatistík cieľovej skupiny pre Dynamics 365 Customer Insights ste možno vytvorili segmenty na zefektívnenie svojich marketingových kampaní zacielením na relevantné publikum.</span><span class="sxs-lookup"><span data-stu-id="51e48-104">As a user of audience insights for Dynamics 365 Customer Insights, you may have created segments to make your marketing campaigns more efficient by targeting relevant audiences.</span></span> <span data-ttu-id="51e48-105">Ak chcete použiť segment z prehľadov cieľovej skupiny v platforme Adobe Experience Platform a aplikáciách, ako je Adobe Campaign Standard, musíte postupovať podľa niekoľkých krokov uvedených v tomto článku.</span><span class="sxs-lookup"><span data-stu-id="51e48-105">To use a segment from audience insights in Adobe Experience Platform and applications like Adobe Campaign Standard, you need to follow a few steps outlined in this article.</span></span>

:::image type="content" source="media/AEP-flow.png" alt-text="Schéma postupu krokov uvedených v tomto článku.":::

## <a name="prerequisites"></a><span data-ttu-id="51e48-107">Predpoklady</span><span class="sxs-lookup"><span data-stu-id="51e48-107">Prerequisites</span></span>

-   <span data-ttu-id="51e48-108">Licencia Dynamics 365 Customer Insights</span><span class="sxs-lookup"><span data-stu-id="51e48-108">Dynamics 365 Customer Insights license</span></span>
-   <span data-ttu-id="51e48-109">Licencia platformy Adobe Experience</span><span class="sxs-lookup"><span data-stu-id="51e48-109">Adobe Experience Platform license</span></span>
-   <span data-ttu-id="51e48-110">Licencia Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="51e48-110">Adobe Campaign Standard license</span></span>
-   <span data-ttu-id="51e48-111">Účet úložiska Azure Blob</span><span class="sxs-lookup"><span data-stu-id="51e48-111">Azure Blob Storage account</span></span>

## <a name="campaign-overview"></a><span data-ttu-id="51e48-112">Prehľad kampane</span><span class="sxs-lookup"><span data-stu-id="51e48-112">Campaign Overview</span></span>

<span data-ttu-id="51e48-113">Aby sme lepšie pochopili, ako môžete použiť segmenty z prehľadov publika v platforme Adobe Experience Platform, pozrime sa na fiktívnu ukážkovú kampaň.</span><span class="sxs-lookup"><span data-stu-id="51e48-113">To better understand how you can use segments from audience insights in Adobe Experience Platform, let’s look at a fictitious sample campaign.</span></span>

<span data-ttu-id="51e48-114">Predpokladajme, že vaša spoločnosť ponúka svojim zákazníkom v USA mesačnú službu na základe predplatného.</span><span class="sxs-lookup"><span data-stu-id="51e48-114">Let’s assume that your company offers a monthly, subscription-based service to your customers in the United States.</span></span> <span data-ttu-id="51e48-115">Chcete identifikovať zákazníkov, ktorých predplatné sa má predĺžiť počas nasledujúcich ôsmich dní, ale ešte si ich predplatné neobnovili.</span><span class="sxs-lookup"><span data-stu-id="51e48-115">You want to identify customers whose subscriptions are due for renewal in the next eight days but haven't yet renewed their subscription.</span></span> <span data-ttu-id="51e48-116">Ak si chcete týchto zákazníkov udržať, chcete im poslať propagačnú ponuku e-mailom pomocou programu Adobe Experience Platform.</span><span class="sxs-lookup"><span data-stu-id="51e48-116">To keep these customers, you want to send them a promotional offer via email, using Adobe Experience Platform.</span></span>

<span data-ttu-id="51e48-117">V tomto príklade chceme propagačnú e-mailovú kampaň spustiť raz.</span><span class="sxs-lookup"><span data-stu-id="51e48-117">In this example, we want to run the promotional email campaign once.</span></span> <span data-ttu-id="51e48-118">Tento článok sa nevzťahuje na prípady použitia kampane viac ako raz.</span><span class="sxs-lookup"><span data-stu-id="51e48-118">This article doesn’t cover the use-case of running the campaign more than once.</span></span>

## <a name="identify-your-target-audience"></a><span data-ttu-id="51e48-119">Identifikujte svoje cieľové publikum</span><span class="sxs-lookup"><span data-stu-id="51e48-119">Identify your target audience</span></span>

<span data-ttu-id="51e48-120">V našom scenári predpokladáme, že e-mailové adresy zákazníkov sú k dispozícii v štatistikách publika a ich propagačné preferencie boli analyzované s cieľom identifikovať členov segmentu.</span><span class="sxs-lookup"><span data-stu-id="51e48-120">In our scenario, we assume that the email addresses of the customers are available in audience insights and their promotional preferences were analyzed to identify members of the segment.</span></span>

<span data-ttu-id="51e48-121">[Segment, ktorý ste definovali v štatistikách cieľovej skupiny](segments.md) sa volá **ChurnProneCustomers** a týmto zákazníkom plánujete poslať e-mailovú propagáciu.</span><span class="sxs-lookup"><span data-stu-id="51e48-121">The [segment you defined in audience insights](segments.md) is called **ChurnProneCustomers** and you plan to send these customers the email promotion.</span></span>

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Snímka obrazovky stránky segmentov s vytvoreným segmentom ChurnProneCustomers.":::

<span data-ttu-id="51e48-123">E-mail s ponukou, ktorý chcete poslať, bude obsahovať krstné meno, priezvisko, a dátum ukončenia predplatného zákazníka.</span><span class="sxs-lookup"><span data-stu-id="51e48-123">The offer email that you want to send out will contain the first name, last name, and the subscription end date of the customer.</span></span> <span data-ttu-id="51e48-124">Informuje zákazníkov o zľave, ktorú dostanú, ak si obnovia predplatné skôr, ako skončí.</span><span class="sxs-lookup"><span data-stu-id="51e48-124">It informs the customers about the discount they’ll get if they renew their subscription before it ends.</span></span>

## <a name="export-your-target-audience"></a><span data-ttu-id="51e48-125">Exportujte svoje cieľové publikum</span><span class="sxs-lookup"><span data-stu-id="51e48-125">Export your target audience</span></span>

<span data-ttu-id="51e48-126">Po identifikácii nášho cieľového publika môžeme nakonfigurovať export z prehľadov cieľovej skupiny do účtu úložiska Azure Blob.</span><span class="sxs-lookup"><span data-stu-id="51e48-126">With our target audience identified, we can configure the export from audience insights to an Azure Blob Storage account.</span></span>

### <a name="configure-a-connection"></a><span data-ttu-id="51e48-127">Konfigurácia a pripojenie</span><span class="sxs-lookup"><span data-stu-id="51e48-127">Configure a connection</span></span>

1. <span data-ttu-id="51e48-128">Prejdite do časti **Správca** > **Pripojenia**.</span><span class="sxs-lookup"><span data-stu-id="51e48-128">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="51e48-129">Stlačte možnosť **Pridať pripojenie** a stlačte možnosť **Azure Blob Storage** alebo stlačte **Nastaviť** v dlaždici **Azure Blob Storage**:</span><span class="sxs-lookup"><span data-stu-id="51e48-129">Select **Add connection** and choose **Azure Blob Storage** or select **Set up** in the **Azure Blob Storage** tile:</span></span>

   :::image type="content" source="media/export-azure-blob-storage-tile.png" alt-text="Konfiguračná dlaždica pre úložisko Azure Blob."::: <span data-ttu-id="51e48-131">na konfiguráciu pripojenia.</span><span class="sxs-lookup"><span data-stu-id="51e48-131">to configure the connection.</span></span>

1. <span data-ttu-id="51e48-132">Do poľa **Zobrazovaný názov** zadajte rozpoznateľný názov pripojenia.</span><span class="sxs-lookup"><span data-stu-id="51e48-132">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="51e48-133">Zobrazovaný názov a typ spojenia, ktoré popisuje toto spojenie.</span><span class="sxs-lookup"><span data-stu-id="51e48-133">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="51e48-134">Odporúčame zvoliť názov, ktorý vysvetľuje účel a cieľ tohto spojenia.</span><span class="sxs-lookup"><span data-stu-id="51e48-134">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="51e48-135">Vyberte používateľov, ktorí môžu používať toto pripojenie.</span><span class="sxs-lookup"><span data-stu-id="51e48-135">Choose who can use this connection.</span></span> <span data-ttu-id="51e48-136">Ak neurobíte nič, predvolená hodnota bude Správcovia.</span><span class="sxs-lookup"><span data-stu-id="51e48-136">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="51e48-137">Viac informácií nájdete v časti [Umožnite prispievateľom použiť pripojenie na export](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="51e48-137">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="51e48-138">Zadajte znak **Názov účtu**, **Kľúč účtu** a **Kontajner** pre váš účet úložiska Blob, kam chcete exportovať segment.</span><span class="sxs-lookup"><span data-stu-id="51e48-138">Enter **Account name**, **Account key**, and **Container** for your Blob storage account where you want to export the segment to.</span></span>  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Snímka obrazovky konfigurácií účtu úložiska."::: 
   
    - <span data-ttu-id="51e48-140">Ak sa chcete dozvedieť viac o názve a kľúči účtu úložiska Blob, prečítajte si časť [Správa nastavení účtu v portáli Azure](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="51e48-140">To learn more about how to find the Blob storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>
    - <span data-ttu-id="51e48-141">Informácie o tom, ako vytvoriť kontajner, nájdete v časti [Vytvorenie kontajnera](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span><span class="sxs-lookup"><span data-stu-id="51e48-141">To learn how to create a container, see [Create a container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span></span>

1. <span data-ttu-id="51e48-142">Stlačte možnosť **Uložiť** a dokončite pripojenie.</span><span class="sxs-lookup"><span data-stu-id="51e48-142">Select **Save** to complete the connection.</span></span> 

### <a name="configure-an-export"></a><span data-ttu-id="51e48-143">Nakonfigurujte export</span><span class="sxs-lookup"><span data-stu-id="51e48-143">Configure an export</span></span>

<span data-ttu-id="51e48-144">Tento export môžete nakonfigurovať, ak máte prístup k pripojeniu tohto typu.</span><span class="sxs-lookup"><span data-stu-id="51e48-144">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="51e48-145">Viac informácií nájdete na stránke [Na konfiguráciu exportu sú potrebné povolenia](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="51e48-145">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="51e48-146">Prejdite na **Údaje** > **Exporty**.</span><span class="sxs-lookup"><span data-stu-id="51e48-146">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="51e48-147">Na vytvorenie nového exportu stlačte možnosť **Pridať export**.</span><span class="sxs-lookup"><span data-stu-id="51e48-147">To create a new export, select **Add export**.</span></span>

1. <span data-ttu-id="51e48-148">V poli **Pripojenie na export** vyberte pripojenie v časti úložiska Azure Blob.</span><span class="sxs-lookup"><span data-stu-id="51e48-148">In the **Connection for export** field, choose a connection from the Azure Blob Storage section.</span></span> <span data-ttu-id="51e48-149">Ak nevidíte názov tejto sekcie, nemáte k dispozícii žiadne spojenia tohto typu.</span><span class="sxs-lookup"><span data-stu-id="51e48-149">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="51e48-150">Vyberte segment, ktorý chcete exportovať.</span><span class="sxs-lookup"><span data-stu-id="51e48-150">Choose the segment that you want to export.</span></span> <span data-ttu-id="51e48-151">V tomto príklade ide o **ChurnProneCustomers**.</span><span class="sxs-lookup"><span data-stu-id="51e48-151">In this example, it’s **ChurnProneCustomers**.</span></span>

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Snímka obrazovky používateľského rozhrania výberu segmentu s vybraným segmentom ChurnProneCustomers.":::

1. <span data-ttu-id="51e48-153">Vyberte položku **Uložiť**.</span><span class="sxs-lookup"><span data-stu-id="51e48-153">Select **Save**.</span></span>

<span data-ttu-id="51e48-154">Po uložení cieľu exportu ho nájdete v časti **Údaje** > **Exporty**.</span><span class="sxs-lookup"><span data-stu-id="51e48-154">After saving the export destination, you find it on **Data** > **Exports**.</span></span>

<span data-ttu-id="51e48-155">Teraz môžete [exportovať segment na požiadanie](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="51e48-155">You can now [export the segment on demand](export-destinations.md#run-exports-on-demand).</span></span> <span data-ttu-id="51e48-156">Export sa spustí aj pri každej [plánovanej obnove](system.md).</span><span class="sxs-lookup"><span data-stu-id="51e48-156">The export will also run with every [scheduled refresh](system.md).</span></span>

> [!NOTE]
> <span data-ttu-id="51e48-157">Zaistite, aby počet záznamov v exportovanom segmente bol v rámci povoleného limitu vašej licencie Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="51e48-157">Ensure that the number of records in the exported segment are within the allowed limit of your Adobe Campaign Standard license.</span></span>

<span data-ttu-id="51e48-158">Exportované údaje sú uložené v kontajneri úložiska Azure Blob, ktorý ste nakonfigurovali vyššie.</span><span class="sxs-lookup"><span data-stu-id="51e48-158">Exported data is stored in the Azure Blob storage container you configured above.</span></span> <span data-ttu-id="51e48-159">Vo vašom kontajneri sa automaticky vytvorí nasledujúca cesta k priečinku:</span><span class="sxs-lookup"><span data-stu-id="51e48-159">The following folder path is automatically created in your container:</span></span>

<span data-ttu-id="51e48-160">*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*</span><span class="sxs-lookup"><span data-stu-id="51e48-160">*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*</span></span>

<span data-ttu-id="51e48-161">Príklad: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv</span><span class="sxs-lookup"><span data-stu-id="51e48-161">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv</span></span>

<span data-ttu-id="51e48-162">*Model.json* pre exportované entity bude uložené na úrovni *%ExportDestinationName%*.</span><span class="sxs-lookup"><span data-stu-id="51e48-162">The *model.json* for the exported entities resides at the *%ExportDestinationName%* level.</span></span>

<span data-ttu-id="51e48-163">Príklad: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json</span><span class="sxs-lookup"><span data-stu-id="51e48-163">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json</span></span>

## <a name="define-experience-data-model-xdm-in-adobe-experience-platform"></a><span data-ttu-id="51e48-164">Definujte dátový model Experience (XDM) v platforme Adobe Experience Platform</span><span class="sxs-lookup"><span data-stu-id="51e48-164">Define Experience Data Model (XDM) in Adobe Experience Platform</span></span>

<span data-ttu-id="51e48-165">Predtým, ako je možné exportované údaje z prehľadov cieľovej skupiny použiť v rámci platformy Adobe Experience Platform, musíme definovať schému dátového modelu Experience a [nakonfigurujte údaje pre profil zákazníka v reálnom čase](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).</span><span class="sxs-lookup"><span data-stu-id="51e48-165">Before the exported data from audience insights can be used within Adobe Experience Platform, we need to define the Experience Data Model schema and [configure the data for the Real-time Customer Profile](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).</span></span>

<span data-ttu-id="51e48-166">Zistite, [čo je XDM](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) a oboznámte sa so [základmi kompozície schémy](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).</span><span class="sxs-lookup"><span data-stu-id="51e48-166">Learn [what XDM is](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) and understand the [basics of schema composition](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).</span></span>

## <a name="import-data-into-adobe-experience-platform"></a><span data-ttu-id="51e48-167">Importujte údaje do platformy Adobe Experience Platform</span><span class="sxs-lookup"><span data-stu-id="51e48-167">Import data into Adobe Experience Platform</span></span>

<span data-ttu-id="51e48-168">Teraz, keď je všetko na svojom mieste, musíme na vytvorenie profilov importovať pripravené údaje o publiku z prehľadov publika do štandardu Adobe Experience Platform.</span><span class="sxs-lookup"><span data-stu-id="51e48-168">Now that everything is in place, we need to import the prepared audience data from audience insights into Adobe Experience Platform.</span></span>

<span data-ttu-id="51e48-169">Najprv [vytvorte pripojenie zdroja úložiska Azure Blob](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).</span><span class="sxs-lookup"><span data-stu-id="51e48-169">First, [create an Azure Blob Storage source connection](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).</span></span>    

<span data-ttu-id="51e48-170">Po definovaní zdrojového pripojenia [nakonfigurujte tok údajov](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) pre dávkové pripojenie cloudového úložiska na importovanie segmentového výstupu z prehľadov publika do platformy Adobe Experience Platform.</span><span class="sxs-lookup"><span data-stu-id="51e48-170">After defining the source connection, [configure a dataflow](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) for a cloud storage batch connection to import the segment output from audience insights into Adobe Experience Platform.</span></span>

## <a name="create-an-audience-in-adobe-campaign-standard"></a><span data-ttu-id="51e48-171">Vytvorte cieľovú skupinu v službe Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="51e48-171">Create an audience in Adobe Campaign Standard</span></span>

<span data-ttu-id="51e48-172">Na odoslanie e-mailu s touto kampaňou použijeme program Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="51e48-172">To send the email for this campaign, we will use Adobe Campaign Standard.</span></span> <span data-ttu-id="51e48-173">Po importe údajov do platformy Adobe Experience Platform musíme [vytvoriť cieľovú skupinu](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) v Adobe Campaign Standard s využitím údajov v Adobe Experience Platform.</span><span class="sxs-lookup"><span data-stu-id="51e48-173">After importing the data into Adobe Experience Platform, we need to [create an audience](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) in Adobe Campaign Standard using the data in Adobe Experience Platform.</span></span>

<span data-ttu-id="51e48-174">Zistite, ako [používať nástroj na tvorbu segmentov](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/working-with-adobe-experience-platform/aep-using-segment-builder.html#building-a-segment) v Adobe Campaign Standard na definovanie cieľovej skupiny na základe údajov v Adobe Experience Platform.</span><span class="sxs-lookup"><span data-stu-id="51e48-174">Learn how to [use segment builder](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/working-with-adobe-experience-platform/aep-using-segment-builder.html#building-a-segment) in Adobe Campaign Standard to define an audience based on the data in Adobe Experience Platform.</span></span>

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a><span data-ttu-id="51e48-175">Vytvorte a odošlite e-mail pomocou aplikácie Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="51e48-175">Create and send the email using Adobe Campaign Standard</span></span>

<span data-ttu-id="51e48-176">Vytvorte e-mailový obsah a potom [otestujte a odošlite](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) svoj e-mail.</span><span class="sxs-lookup"><span data-stu-id="51e48-176">Create the email content and then [test and send](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) your email.</span></span>

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Vzorový e-mail s ponukou na obnovenie od spoločnosti Adobe Campaign Standard.":::
