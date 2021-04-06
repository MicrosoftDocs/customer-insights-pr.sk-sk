---
title: Exportujte údaje Customer Insights do aplikácie Adobe Experience Platform
description: Naučte sa, ako používať segmenty štatistík publika v aplikácii Adobe Experience Platform.
ms.date: 02/26/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: d1856861562be55c6d1d051050fe965560fa42f8
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596288"
---
# <a name="use-customer-insights-segments-in-adobe-experience-platform-preview"></a><span data-ttu-id="231b1-103">Naučte sa, ako používať segmenty Customer Insights v Adobe Experience Platform (ukážka)</span><span class="sxs-lookup"><span data-stu-id="231b1-103">Use Customer Insights segments in Adobe Experience Platform (preview)</span></span>

<span data-ttu-id="231b1-104">Ako používateľ štatistík cieľovej skupiny pre Dynamics 365 Customer Insights ste možno vytvorili segmenty na zefektívnenie svojich marketingových kampaní zacielením na relevantné publikum.</span><span class="sxs-lookup"><span data-stu-id="231b1-104">As a user of audience insights for Dynamics 365 Customer Insights, you may have created segments to make your marketing campaigns more efficient by targeting relevant audiences.</span></span> <span data-ttu-id="231b1-105">Ak chcete použiť segment z prehľadov cieľovej skupiny v platforme Adobe Experience Platform a aplikáciách, ako je Adobe Campaign Standard, musíte postupovať podľa niekoľkých krokov uvedených v tomto článku.</span><span class="sxs-lookup"><span data-stu-id="231b1-105">To use a segment from audience insights in Adobe Experience Platform and applications like Adobe Campaign Standard, you need to follow a few steps outlined in this article.</span></span>

:::image type="content" source="media/AEP-flow.png" alt-text="Schéma postupu krokov uvedených v tomto článku.":::

## <a name="prerequisites"></a><span data-ttu-id="231b1-107">Predpoklady</span><span class="sxs-lookup"><span data-stu-id="231b1-107">Prerequisites</span></span>

-   <span data-ttu-id="231b1-108">Licencia Dynamics 365 Customer Insights</span><span class="sxs-lookup"><span data-stu-id="231b1-108">Dynamics 365 Customer Insights license</span></span>
-   <span data-ttu-id="231b1-109">Licencia platformy Adobe Experience</span><span class="sxs-lookup"><span data-stu-id="231b1-109">Adobe Experience Platform license</span></span>
-   <span data-ttu-id="231b1-110">Licencia Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="231b1-110">Adobe Campaign Standard license</span></span>
-   <span data-ttu-id="231b1-111">Účet úložiska Azure Blob</span><span class="sxs-lookup"><span data-stu-id="231b1-111">Azure Blob Storage account</span></span>

## <a name="campaign-overview"></a><span data-ttu-id="231b1-112">Prehľad kampane</span><span class="sxs-lookup"><span data-stu-id="231b1-112">Campaign Overview</span></span>

<span data-ttu-id="231b1-113">Aby sme lepšie pochopili, ako môžete použiť segmenty z prehľadov publika v platforme Adobe Experience Platform, pozrime sa na fiktívnu ukážkovú kampaň.</span><span class="sxs-lookup"><span data-stu-id="231b1-113">To better understand how you can use segments from audience insights in Adobe Experience Platform, let’s look at a fictitious sample campaign.</span></span>

<span data-ttu-id="231b1-114">Predpokladajme, že vaša spoločnosť ponúka svojim zákazníkom v USA mesačnú službu na základe predplatného.</span><span class="sxs-lookup"><span data-stu-id="231b1-114">Let’s assume that your company offers a monthly, subscription-based service to your customers in the United States.</span></span> <span data-ttu-id="231b1-115">Chcete identifikovať zákazníkov, ktorých predplatné sa má predĺžiť počas nasledujúcich ôsmich dní, ale ešte si ich predplatné neobnovili.</span><span class="sxs-lookup"><span data-stu-id="231b1-115">You want to identify customers whose subscriptions are due for renewal in the next eight days but haven't yet renewed their subscription.</span></span> <span data-ttu-id="231b1-116">Ak si chcete týchto zákazníkov udržať, chcete im poslať propagačnú ponuku e-mailom pomocou programu Adobe Experience Platform.</span><span class="sxs-lookup"><span data-stu-id="231b1-116">To keep these customers, you want to send them a promotional offer via email, using Adobe Experience Platform.</span></span>

<span data-ttu-id="231b1-117">V tomto príklade chceme propagačnú e-mailovú kampaň spustiť raz.</span><span class="sxs-lookup"><span data-stu-id="231b1-117">In this example, we want to run the promotional email campaign once.</span></span> <span data-ttu-id="231b1-118">Tento článok sa nevzťahuje na prípady použitia kampane viac ako raz.</span><span class="sxs-lookup"><span data-stu-id="231b1-118">This article doesn’t cover the use-case of running the campaign more than once.</span></span>

## <a name="identify-your-target-audience"></a><span data-ttu-id="231b1-119">Identifikujte svoje cieľové publikum</span><span class="sxs-lookup"><span data-stu-id="231b1-119">Identify your target audience</span></span>

<span data-ttu-id="231b1-120">V našom scenári predpokladáme, že e-mailové adresy zákazníkov sú k dispozícii v štatistikách publika a ich propagačné preferencie boli analyzované s cieľom identifikovať členov segmentu.</span><span class="sxs-lookup"><span data-stu-id="231b1-120">In our scenario, we assume that the email addresses of the customers are available in audience insights and their promotional preferences were analyzed to identify members of the segment.</span></span>

<span data-ttu-id="231b1-121">[Segment, ktorý ste definovali v štatistikách cieľovej skupiny](segments.md) sa volá **ChurnProneCustomers** a týmto zákazníkom plánujete poslať e-mailovú propagáciu.</span><span class="sxs-lookup"><span data-stu-id="231b1-121">The [segment you defined in audience insights](segments.md) is called **ChurnProneCustomers** and you plan to send these customers the email promotion.</span></span>

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Snímka obrazovky stránky segmentov s vytvoreným segmentom ChurnProneCustomers.":::

<span data-ttu-id="231b1-123">E-mail s ponukou, ktorý chcete poslať, bude obsahovať krstné meno, priezvisko, a dátum ukončenia predplatného zákazníka.</span><span class="sxs-lookup"><span data-stu-id="231b1-123">The offer email that you want to send out will contain the first name, last name, and the subscription end date of the customer.</span></span> <span data-ttu-id="231b1-124">Informuje zákazníkov o zľave, ktorú dostanú, ak si obnovia predplatné skôr, ako skončí.</span><span class="sxs-lookup"><span data-stu-id="231b1-124">It informs the customers about the discount they’ll get if they renew their subscription before it ends.</span></span>

## <a name="export-your-target-audience"></a><span data-ttu-id="231b1-125">Exportujte svoje cieľové publikum</span><span class="sxs-lookup"><span data-stu-id="231b1-125">Export your target audience</span></span>

<span data-ttu-id="231b1-126">Po identifikácii nášho cieľového publika môžeme nakonfigurovať export z prehľadov cieľovej skupiny do účtu úložiska Azure Blob.</span><span class="sxs-lookup"><span data-stu-id="231b1-126">With our target audience identified, we can configure the export from audience insights to an Azure Blob Storage account.</span></span>

1. <span data-ttu-id="231b1-127">V prehľadoch cieľových skupín prejdite na **Správca** > **Ciele exportu**.</span><span class="sxs-lookup"><span data-stu-id="231b1-127">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="231b1-128">V dlaždici **Úložisko Azure Blob** stlačte možnosť **Nastaviť**.</span><span class="sxs-lookup"><span data-stu-id="231b1-128">In the **Azure Blob Storage** tile, select **Set up**.</span></span>

   :::image type="content" source="media/export-azure-blob-storage-tile.png" alt-text="Konfiguračná dlaždica pre úložisko Azure Blob.":::

1. <span data-ttu-id="231b1-130">Zadajte **Zobrazovacie meno** pre tento nový cieľ exportu a potom zadajte **Názov účtu**, **Kľúč účtu** a **Kontajner** účtu úložiska Azure Blob, do ktorého chcete segment exportovať.</span><span class="sxs-lookup"><span data-stu-id="231b1-130">Provide a **Display name** for this new export destination and then enter the **Account name**, **Account key**, and **Container** of the Azure Blob Storage account where you want to export the segment to.</span></span>  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Snímka obrazovky konfigurácií účtu úložiska."::: 

   - <span data-ttu-id="231b1-132">Ďalšie informácie o tom, ako nájsť názov a kľúč účtu úložiska Azure Blob nájdete na stránke [Správa nastavení účtu úložiska na portáli Azure](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="231b1-132">To learn more about how to find the Azure Blob storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>

   - <span data-ttu-id="231b1-133">Informácie o tom, ako vytvoriť kontajner, nájdete v časti [Vytvorenie kontajnera](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span><span class="sxs-lookup"><span data-stu-id="231b1-133">To learn how to create a container, see [Create a container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span></span>

1. <span data-ttu-id="231b1-134">Vyberte **Ďalej**.</span><span class="sxs-lookup"><span data-stu-id="231b1-134">Select **Next**.</span></span>

1. <span data-ttu-id="231b1-135">Vyberte segment, ktorý chcete exportovať.</span><span class="sxs-lookup"><span data-stu-id="231b1-135">Choose the segment that you want to export.</span></span> <span data-ttu-id="231b1-136">V tomto príklade ide o **ChurnProneCustomers**.</span><span class="sxs-lookup"><span data-stu-id="231b1-136">In this example, it’s **ChurnProneCustomers**.</span></span>

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Snímka obrazovky používateľského rozhrania výberu segmentu s vybraným segmentom ChurnProneCustomers.":::

1. <span data-ttu-id="231b1-138">Vyberte položku **Uložiť**.</span><span class="sxs-lookup"><span data-stu-id="231b1-138">Select **Save**.</span></span>

<span data-ttu-id="231b1-139">Po uložení cieľu exportu ho nájdete na v časti **Správca** > **Exporty** > **Moje ciele exportu**.</span><span class="sxs-lookup"><span data-stu-id="231b1-139">After saving the export destination, you find it on **Admin** > **Exports** > **My export destinations**.</span></span>

:::image type="content" source="media/export-destination-azure-blob-storage.png" alt-text="Snímka obrazovky so zvýrazneným zoznamom exportov a ukážkovým segmentom.":::

<span data-ttu-id="231b1-141">Teraz môžete [exportovať segment na požiadanie](export-destinations.md#export-data-on-demand).</span><span class="sxs-lookup"><span data-stu-id="231b1-141">You can now [export the segment on demand](export-destinations.md#export-data-on-demand).</span></span> <span data-ttu-id="231b1-142">Export sa spustí aj pri každej [plánovanej obnove](system.md).</span><span class="sxs-lookup"><span data-stu-id="231b1-142">The export will also run with every [scheduled refresh](system.md).</span></span>

> [!NOTE]
> <span data-ttu-id="231b1-143">Zaistite, aby počet záznamov v exportovanom segmente bol v rámci povoleného limitu vašej licencie Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="231b1-143">Ensure that the number of records in the exported segment are within the allowed limit of your Adobe Campaign Standard license.</span></span>

<span data-ttu-id="231b1-144">Exportované údaje sú uložené v kontajneri úložiska Azure Blob, ktorý ste nakonfigurovali vyššie.</span><span class="sxs-lookup"><span data-stu-id="231b1-144">Exported data is stored in the Azure Blob storage container you configured above.</span></span> <span data-ttu-id="231b1-145">Vo vašom kontajneri sa automaticky vytvorí nasledujúca cesta k priečinku:</span><span class="sxs-lookup"><span data-stu-id="231b1-145">The following folder path is automatically created in your container:</span></span>

<span data-ttu-id="231b1-146">*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*</span><span class="sxs-lookup"><span data-stu-id="231b1-146">*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*</span></span>

<span data-ttu-id="231b1-147">Príklad: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv</span><span class="sxs-lookup"><span data-stu-id="231b1-147">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv</span></span>

<span data-ttu-id="231b1-148">*Model.json* pre exportované entity bude uložené na úrovni *%ExportDestinationName%*.</span><span class="sxs-lookup"><span data-stu-id="231b1-148">The *model.json* for the exported entities resides at the *%ExportDestinationName%* level.</span></span>

<span data-ttu-id="231b1-149">Príklad: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json</span><span class="sxs-lookup"><span data-stu-id="231b1-149">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json</span></span>

## <a name="define-experience-data-model-xdm-in-adobe-experience-platform"></a><span data-ttu-id="231b1-150">Definujte dátový model Experience (XDM) v platforme Adobe Experience Platform</span><span class="sxs-lookup"><span data-stu-id="231b1-150">Define Experience Data Model (XDM) in Adobe Experience Platform</span></span>

<span data-ttu-id="231b1-151">Predtým, ako je možné exportované údaje z prehľadov cieľovej skupiny použiť v rámci platformy Adobe Experience Platform, musíme definovať schému dátového modelu Experience a [nakonfigurujte údaje pre profil zákazníka v reálnom čase](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).</span><span class="sxs-lookup"><span data-stu-id="231b1-151">Before the exported data from audience insights can be used within Adobe Experience Platform, we need to define the Experience Data Model schema and [configure the data for the Real-time Customer Profile](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).</span></span>

<span data-ttu-id="231b1-152">Zistite, [čo je XDM](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) a oboznámte sa so [základmi kompozície schémy](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).</span><span class="sxs-lookup"><span data-stu-id="231b1-152">Learn [what XDM is](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) and understand the [basics of schema composition](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).</span></span>

## <a name="import-data-into-adobe-experience-platform"></a><span data-ttu-id="231b1-153">Importujte údaje do platformy Adobe Experience Platform</span><span class="sxs-lookup"><span data-stu-id="231b1-153">Import data into Adobe Experience Platform</span></span>

<span data-ttu-id="231b1-154">Teraz, keď je všetko na svojom mieste, musíme na vytvorenie profilov importovať pripravené údaje o publiku z prehľadov publika do štandardu Adobe Experience Platform.</span><span class="sxs-lookup"><span data-stu-id="231b1-154">Now that everything is in place, we need to import the prepared audience data from audience insights into Adobe Experience Platform.</span></span>

<span data-ttu-id="231b1-155">Najprv [vytvorte pripojenie zdroja úložiska Azure Blob](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).</span><span class="sxs-lookup"><span data-stu-id="231b1-155">First, [create an Azure Blob Storage source connection](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).</span></span>    

<span data-ttu-id="231b1-156">Po definovaní zdrojového pripojenia [nakonfigurujte tok údajov](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) pre dávkové pripojenie cloudového úložiska na importovanie segmentového výstupu z prehľadov publika do platformy Adobe Experience Platform.</span><span class="sxs-lookup"><span data-stu-id="231b1-156">After defining the source connection, [configure a dataflow](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) for a cloud storage batch connection to import the segment output from audience insights into Adobe Experience Platform.</span></span>

## <a name="create-an-audience-in-adobe-campaign-standard"></a><span data-ttu-id="231b1-157">Vytvorte cieľovú skupinu v službe Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="231b1-157">Create an audience in Adobe Campaign Standard</span></span>

<span data-ttu-id="231b1-158">Na odoslanie e-mailu s touto kampaňou použijeme program Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="231b1-158">To send the email for this campaign, we will use Adobe Campaign Standard.</span></span> <span data-ttu-id="231b1-159">Po importe údajov do platformy Adobe Experience Platform musíme [vytvoriť cieľovú skupinu](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) v Adobe Campaign Standard s využitím údajov v Adobe Experience Platform.</span><span class="sxs-lookup"><span data-stu-id="231b1-159">After importing the data into Adobe Experience Platform, we need to [create an audience](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) in Adobe Campaign Standard using the data in Adobe Experience Platform.</span></span>

<span data-ttu-id="231b1-160">Zistite, ako [používať nástroj na tvorbu segmentov](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/working-with-adobe-experience-platform/aep-using-segment-builder.html#building-a-segment) v Adobe Campaign Standard na definovanie cieľovej skupiny na základe údajov v Adobe Experience Platform.</span><span class="sxs-lookup"><span data-stu-id="231b1-160">Learn how to [use segment builder](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/working-with-adobe-experience-platform/aep-using-segment-builder.html#building-a-segment) in Adobe Campaign Standard to define an audience based on the data in Adobe Experience Platform.</span></span>

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a><span data-ttu-id="231b1-161">Vytvorte a odošlite e-mail pomocou aplikácie Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="231b1-161">Create and send the email using Adobe Campaign Standard</span></span>

<span data-ttu-id="231b1-162">Vytvorte e-mailový obsah a potom [otestujte a odošlite](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) svoj e-mail.</span><span class="sxs-lookup"><span data-stu-id="231b1-162">Create the email content and then [test and send](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) your email.</span></span>

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Vzorový e-mail s ponukou na obnovenie od spoločnosti Adobe Campaign Standard.":::