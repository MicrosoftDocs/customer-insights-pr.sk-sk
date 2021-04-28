---
title: Exportujte údaje Customer Insights do aplikácie Adobe Campaign Standard
description: Naučte sa, ako používať segmenty štatistík publika v aplikácii Adobe Campaign Standard.
ms.date: 03/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: b6c010d84119c2fa8b3ef99017c65f9939bf28c4
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760300"
---
# <a name="use-customer-insights-segments-in-adobe-campaign-standard-preview"></a><span data-ttu-id="34366-103">Naučte sa, ako používať segmenty Customer Insights v aplikácii Adobe Campaign Standard (ukážka)</span><span class="sxs-lookup"><span data-stu-id="34366-103">Use Customer Insights segments in Adobe Campaign Standard (preview)</span></span>

<span data-ttu-id="34366-104">Ako používateľ štatistík cieľovej skupiny pre Dynamics 365 Customer Insights ste možno vytvorili segmenty na zefektívnenie svojich marketingových kampaní zacielením na relevantné publikum.</span><span class="sxs-lookup"><span data-stu-id="34366-104">As a user of audience insights for Dynamics 365 Customer Insights, you may have created segments to make your marketing campaigns more efficient by targeting relevant audiences.</span></span> <span data-ttu-id="34366-105">Ak chcete použiť segment z prehľadov cieľovej skupiny v platforme Adobe Experience Platform a aplikáciách, ako je Adobe Campaign Standard, musíte postupovať podľa niekoľkých krokov uvedených v tomto článku.</span><span class="sxs-lookup"><span data-stu-id="34366-105">To use a segment from audience insights in Adobe Experience Platform and applications like Adobe Campaign Standard, you need to follow a few steps outlined in this article.</span></span>

:::image type="content" source="media/ACS-flow.png" alt-text="Schéma postupu krokov uvedených v tomto článku.":::

## <a name="prerequisites"></a><span data-ttu-id="34366-107">Predpoklady</span><span class="sxs-lookup"><span data-stu-id="34366-107">Prerequisites</span></span>

-   <span data-ttu-id="34366-108">Licencia Dynamics 365 Customer Insights</span><span class="sxs-lookup"><span data-stu-id="34366-108">Dynamics 365 Customer Insights license</span></span>
-   <span data-ttu-id="34366-109">Licencia Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="34366-109">Adobe Campaign Standard license</span></span>
-   <span data-ttu-id="34366-110">Účet úložiska Azure Blob</span><span class="sxs-lookup"><span data-stu-id="34366-110">Azure Blob Storage account</span></span>

## <a name="campaign-overview"></a><span data-ttu-id="34366-111">Prehľad kampane</span><span class="sxs-lookup"><span data-stu-id="34366-111">Campaign Overview</span></span>

<span data-ttu-id="34366-112">Aby sme lepšie pochopili, ako môžete použiť segmenty z prehľadov publika v platforme Adobe Experience Platform, pozrime sa na fiktívnu ukážkovú kampaň.</span><span class="sxs-lookup"><span data-stu-id="34366-112">To better understand how you can use segments from audience insights in Adobe Experience Platform, let’s look at a fictitious sample campaign.</span></span>

<span data-ttu-id="34366-113">Predpokladajme, že vaša spoločnosť ponúka svojim zákazníkom v USA mesačnú službu na základe predplatného.</span><span class="sxs-lookup"><span data-stu-id="34366-113">Let’s assume that your company offers a monthly, subscription-based service to your customers in the United States.</span></span> <span data-ttu-id="34366-114">Chcete identifikovať zákazníkov, ktorých predplatné sa má predĺžiť počas nasledujúcich ôsmich dní, ale ešte si ich predplatné neobnovili.</span><span class="sxs-lookup"><span data-stu-id="34366-114">You want to identify customers whose subscriptions are due for renewal in the next eight days but haven't yet renewed their subscription.</span></span> <span data-ttu-id="34366-115">Ak si chcete týchto zákazníkov udržať, chcete im poslať propagačnú ponuku e-mailom pomocou programu Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="34366-115">To keep these customers, you want to send them a promotional offer via email, using Adobe Campaign Standard.</span></span>

<span data-ttu-id="34366-116">V tomto príklade chceme propagačnú e-mailovú kampaň spustiť raz.</span><span class="sxs-lookup"><span data-stu-id="34366-116">In this example, we want to run the promotional email campaign once.</span></span> <span data-ttu-id="34366-117">Tento článok sa nevzťahuje na prípady použitia kampane viac ako raz.</span><span class="sxs-lookup"><span data-stu-id="34366-117">This article doesn’t cover the use-case of running the campaign more than once.</span></span> <span data-ttu-id="34366-118">Štatistiky publika a Adobe Campaign Standard je však možné nakonfigurovať tak, aby fungovali aj pre scenár opakujúcich sa kampaní.</span><span class="sxs-lookup"><span data-stu-id="34366-118">However, audience insights and Adobe Campaign Standard can be configured to work for a recurring campaign scenario too.</span></span>

## <a name="identify-your-target-audience"></a><span data-ttu-id="34366-119">Identifikujte svoje cieľové publikum</span><span class="sxs-lookup"><span data-stu-id="34366-119">Identify your target audience</span></span>

<span data-ttu-id="34366-120">V našom scenári predpokladáme, že e-mailové adresy zákazníkov sú k dispozícii v štatistikách publika a ich propagačné preferencie boli analyzované s cieľom identifikovať členov segmentu.</span><span class="sxs-lookup"><span data-stu-id="34366-120">In our scenario, we assume that the email addresses of the customers are available in audience insights and their promotional preferences were analyzed to identify members of the segment.</span></span>

<span data-ttu-id="34366-121">[Segment, ktorý ste definovali v štatistikách cieľovej skupiny](segments.md) sa volá **ChurnProneCustomers** a týmto zákazníkom plánujete poslať e-mailovú propagáciu.</span><span class="sxs-lookup"><span data-stu-id="34366-121">The [segment you defined in audience insights](segments.md) is called **ChurnProneCustomers** and you plan to send these customers the email promotion.</span></span>

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Snímka obrazovky stránky segmentov s vytvoreným segmentom ChurnProneCustomers.":::

<span data-ttu-id="34366-123">E-mail s ponukou, ktorý chcete poslať, bude obsahovať krstné meno, priezvisko, a dátum ukončenia predplatného zákazníka.</span><span class="sxs-lookup"><span data-stu-id="34366-123">The offer email that you want to send out will contain the first name, last name, and the subscription end date of the customer.</span></span> <span data-ttu-id="34366-124">Informuje zákazníkov o zľave, ktorú dostanú, ak si obnovia predplatné skôr, ako skončí.</span><span class="sxs-lookup"><span data-stu-id="34366-124">It informs the customers about the discount they’ll get if they renew their subscription before it ends.</span></span>

## <a name="export-your-target-audience"></a><span data-ttu-id="34366-125">Exportujte svoje cieľové publikum</span><span class="sxs-lookup"><span data-stu-id="34366-125">Export your target audience</span></span>

### <a name="configure-a-connection"></a><span data-ttu-id="34366-126">Konfigurácia a pripojenie</span><span class="sxs-lookup"><span data-stu-id="34366-126">Configure a connection</span></span>

<span data-ttu-id="34366-127">Po identifikácii nášho cieľového publika môžeme nakonfigurovať export z prehľadov cieľovej skupiny do účtu úložiska Azure Blob.</span><span class="sxs-lookup"><span data-stu-id="34366-127">With our target audience identified, we can configure the export from audience insights to an Azure Blob Storage account.</span></span>

1. <span data-ttu-id="34366-128">V prehľadoch cieľovej skupiny prejdite na **Správca** > **Pripojenia**.</span><span class="sxs-lookup"><span data-stu-id="34366-128">In audience insights, go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="34366-129">Vyberte **Pridať pripojenie** a zvoľte možnosť **Kampaň Adobe** na konfiguráciu pripojenia alebo vyberte možnosť **Nastaviť** v dlaždici **Kampaň Adobe**</span><span class="sxs-lookup"><span data-stu-id="34366-129">Select **Add connection** and choose **Adobe Campaign** to configure the connection or select **Set up** in the **Adobe Campaign** tile</span></span>

   :::image type="content" source="media/adobe-campaign-standard-tile.png" alt-text="Konfiguračná dlaždica pre Adobe Campaign Standard.":::

1. <span data-ttu-id="34366-131">Do poľa **Zobrazovaný názov** zadajte rozpoznateľný názov pripojenia.</span><span class="sxs-lookup"><span data-stu-id="34366-131">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="34366-132">Zobrazovaný názov a typ spojenia, ktoré popisuje toto spojenie.</span><span class="sxs-lookup"><span data-stu-id="34366-132">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="34366-133">Odporúčame zvoliť názov, ktorý vysvetľuje účel a cieľ tohto spojenia.</span><span class="sxs-lookup"><span data-stu-id="34366-133">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="34366-134">Vyberte používateľov, ktorí môžu používať toto pripojenie.</span><span class="sxs-lookup"><span data-stu-id="34366-134">Choose who can use this connection.</span></span> <span data-ttu-id="34366-135">Ak neurobíte nič, predvolená hodnota bude Správcovia.</span><span class="sxs-lookup"><span data-stu-id="34366-135">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="34366-136">Viac informácií nájdete na stránke [Na konfiguráciu exportu sú potrebné povolenia](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="34366-136">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="34366-137">Zadajte znak **Názov účtu**, **Kľúč účtu** a **Kontajner** účtu Azure Blob Storage, do ktorého chcete segment exportovať.</span><span class="sxs-lookup"><span data-stu-id="34366-137">Enter the **Account name**, **Account key**, and **Container** of the Azure Blob Storage account where you want to export the segment to.</span></span>  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Snímka obrazovky konfigurácií účtu úložiska."::: 

   - <span data-ttu-id="34366-139">Ďalšie informácie o tom, ako nájsť názov a kľúč účtu úložiska Azure Blob nájdete na stránke [Správa nastavení účtu úložiska na portáli Azure](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="34366-139">To learn more about how to find the Azure Blob storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>

   - <span data-ttu-id="34366-140">Informácie o tom, ako vytvoriť kontajner, nájdete v časti [Vytvorenie kontajnera](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span><span class="sxs-lookup"><span data-stu-id="34366-140">To learn how to create a container, see [Create a container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span></span>

1. <span data-ttu-id="34366-141">Stlačte možnosť **Uložiť** a dokončite pripojenie.</span><span class="sxs-lookup"><span data-stu-id="34366-141">Select **Save** to complete the connection.</span></span>

### <a name="configure-an-export"></a><span data-ttu-id="34366-142">Nakonfigurujte export</span><span class="sxs-lookup"><span data-stu-id="34366-142">Configure an export</span></span>

<span data-ttu-id="34366-143">Tento export môžete nakonfigurovať, ak máte prístup k pripojeniu tohto typu.</span><span class="sxs-lookup"><span data-stu-id="34366-143">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="34366-144">Viac informácií nájdete na stránke [Na konfiguráciu exportu sú potrebné povolenia](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="34366-144">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="34366-145">Prejdite na **Údaje** > **Exporty**.</span><span class="sxs-lookup"><span data-stu-id="34366-145">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="34366-146">Na vytvorenie nového exportu stlačte možnosť **Pridať export**.</span><span class="sxs-lookup"><span data-stu-id="34366-146">To create a new export, select **Add export**.</span></span>

1. <span data-ttu-id="34366-147">V poli **Pripojenie na export** vyberte pripojenie v časti Adobe Campaign.</span><span class="sxs-lookup"><span data-stu-id="34366-147">In the **Connection for export** field, choose a connection from the Adobe Campaign section.</span></span> <span data-ttu-id="34366-148">Ak nevidíte názov tejto sekcie, nemáte k dispozícii žiadne spojenia tohto typu.</span><span class="sxs-lookup"><span data-stu-id="34366-148">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="34366-149">Vyberte segment, ktorý chcete exportovať.</span><span class="sxs-lookup"><span data-stu-id="34366-149">Choose the segment that you want to export.</span></span> <span data-ttu-id="34366-150">V tomto príklade ide o **ChurnProneCustomers**.</span><span class="sxs-lookup"><span data-stu-id="34366-150">In this example, it’s **ChurnProneCustomers**.</span></span>

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Snímka obrazovky používateľského rozhrania výberu segmentu s vybraným segmentom ChurnProneCustomers.":::

1. <span data-ttu-id="34366-152">Vyberte **Ďalej**.</span><span class="sxs-lookup"><span data-stu-id="34366-152">Select **Next**.</span></span>

1. <span data-ttu-id="34366-153">Teraz namapujme polia **Zdroj** od segmentu štatistík cieľovej skupiny do poľa **Cieľ** v schéme profilu služby Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="34366-153">Now we map the **Source** fields from the audience insights segment to the **Target** field names in the Adobe Campaign Standard profile schema.</span></span>

   :::image type="content" source="media/ACS-field-mapping.png" alt-text="Mapovanie polí pre konektor Adobe Campaign Standard.":::

   <span data-ttu-id="34366-155">Ak chcete pridať ďalšie atribúty, stlačte možnosť **Pridať atribút**.</span><span class="sxs-lookup"><span data-stu-id="34366-155">If you want to add more attributes, select **Add attribute**.</span></span> <span data-ttu-id="34366-156">Cieľový názov sa môže líšiť od názvu zdrojového poľa, takže výstup segmentov z prehľadov publika môžete aj naďalej mapovať do štandardu Adobe Campaign Standard, ak polia nemajú v týchto dvoch systémoch rovnaký názov.</span><span class="sxs-lookup"><span data-stu-id="34366-156">The target name can be different from the source field name so you can still map segment output from audience insights to Adobe Campaign Standard if the fields don’t have the same name in the two systems.</span></span>

   > [!NOTE]
   > <span data-ttu-id="34366-157">E-mailová adresa sa používa ako pole identity, ale na priradenie údajov k štandardu Adobe Campaign Standard môžete použiť akýkoľvek iný identifikátor z profilu zákazníka s prehľadmi publika.</span><span class="sxs-lookup"><span data-stu-id="34366-157">Email address is used as an identity field but you can use any other identifier from your audience insights customer profile to map data to Adobe Campaign Standard.</span></span>

1. <span data-ttu-id="34366-158">Vyberte položku **Uložiť**.</span><span class="sxs-lookup"><span data-stu-id="34366-158">Select **Save**.</span></span>

<span data-ttu-id="34366-159">Po uložení cieľu exportu ho nájdete v časti **Údaje** > **Exporty**.</span><span class="sxs-lookup"><span data-stu-id="34366-159">After saving the export destination, you find it on **Data** > **Exports**.</span></span>

<span data-ttu-id="34366-160">Teraz môžete [exportovať segment na požiadanie](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="34366-160">You can now [export the segment on demand](export-destinations.md#run-exports-on-demand).</span></span> <span data-ttu-id="34366-161">Export sa spustí aj pri každej [plánovanej obnove](system.md).</span><span class="sxs-lookup"><span data-stu-id="34366-161">The export will also run with every [scheduled refresh](system.md).</span></span>

> [!NOTE]
> <span data-ttu-id="34366-162">Zaistite, aby počet záznamov v exportovanom segmente bol v rámci povoleného limitu vašej licencie Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="34366-162">Ensure that the number of records in the exported segment are within the allowed limit of your Adobe Campaign Standard license.</span></span>

<span data-ttu-id="34366-163">Exportované údaje sú uložené v kontajneri úložiska Azure Blob, ktorý ste nakonfigurovali vyššie.</span><span class="sxs-lookup"><span data-stu-id="34366-163">Exported data is stored in the Azure Blob storage container you configured above.</span></span> <span data-ttu-id="34366-164">Vo vašom kontajneri sa automaticky vytvorí nasledujúca cesta k priečinku:</span><span class="sxs-lookup"><span data-stu-id="34366-164">The following folder path is automatically created in your container:</span></span>

<span data-ttu-id="34366-165">*%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*</span><span class="sxs-lookup"><span data-stu-id="34366-165">*%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*</span></span>

<span data-ttu-id="34366-166">Príklad: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv</span><span class="sxs-lookup"><span data-stu-id="34366-166">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv</span></span>

## <a name="configure-adobe-campaign-standard"></a><span data-ttu-id="34366-167">Konfigurácia Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="34366-167">Configure Adobe Campaign Standard</span></span>

<span data-ttu-id="34366-168">Keď sa exportuje segment z prehľadov publika, obsahuje stĺpce, ktoré ste vybrali pri definovaní cieľa exportu v predchádzajúcom kroku.</span><span class="sxs-lookup"><span data-stu-id="34366-168">When a segment from audience insights is exported, it contains the columns you selected while defining the export destination in the previous step.</span></span> <span data-ttu-id="34366-169">Tieto údaje možno použiť na [vytváranie profilov v aplikácii Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).</span><span class="sxs-lookup"><span data-stu-id="34366-169">This data can be used to [create profiles in Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).</span></span>

<span data-ttu-id="34366-170">Ak chcete použiť segment v aplikácii Adobe Campaign Standard, musíme rozšíriť schému profilu v aplikácii Adobe Campaign Standard tak, aby obsahovala ďalšie dve polia.</span><span class="sxs-lookup"><span data-stu-id="34366-170">To use the segment in Adobe Campaign Standard, we need to extend the profile schema in Adobe Campaign Standard to include two additional fields.</span></span> <span data-ttu-id="34366-171">Zistite, ako [rozšíriť zdroj profilu](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) o nové polia v aplikácii Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="34366-171">Learn how to [extend the profile resource](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) with new fields in Adobe Campaign Standard.</span></span>

<span data-ttu-id="34366-172">V našom príklade sú to tieto polia *Názov segmentu a dátum segmentu (voliteľné).*</span><span class="sxs-lookup"><span data-stu-id="34366-172">In our example, these fields are *Segment Name and Segment Date (optional).*</span></span>

<span data-ttu-id="34366-173">Tieto polia použijeme na identifikáciu profilov v štandarde Adobe Campaign Standard, na ktoré chceme pre túto kampaň zacieliť.</span><span class="sxs-lookup"><span data-stu-id="34366-173">We will use these fields to identify the profiles in Adobe Campaign Standard we want to target for this campaign.</span></span>

<span data-ttu-id="34366-174">Ak v aplikácii Adobe Campaign Standard neexistujú žiadne ďalšie záznamy okrem tých, ktoré sa chystáte importovať, môžete tento krok preskočiť.</span><span class="sxs-lookup"><span data-stu-id="34366-174">If there are no other records in Adobe Campaign Standard, other than what you are going to import, you can skip this step.</span></span>

## <a name="import-data-into-adobe-campaign-standard"></a><span data-ttu-id="34366-175">Importujte údaje do aplikácie Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="34366-175">Import data into Adobe Campaign Standard</span></span>

<span data-ttu-id="34366-176">Teraz, keď je všetko na svojom mieste, musíme na vytvorenie profilov importovať pripravené údaje o publiku z prehľadov publika do štandardu Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="34366-176">Now that everything is in place, we need to import the prepared audience data from audience insights into Adobe Campaign Standard to create profiles.</span></span> <span data-ttu-id="34366-177">Zistite [ako importovať profily v aplikácii Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences) pomocou pracovného postupu.</span><span class="sxs-lookup"><span data-stu-id="34366-177">Learn [how to import profiles in Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences) using a workflow.</span></span>

<span data-ttu-id="34366-178">Pracovný postup importu na obrázku nižšie bol nakonfigurovaný tak, aby sa spúšťal každých 8 hodín, a vyhľadáva exportované segmenty štatistík cieľovej skupiny (súbor .csv v úložisku Azure Blob).</span><span class="sxs-lookup"><span data-stu-id="34366-178">The import workflow in the image below has been configured to run every 8 hours and looks for exported audience insights segments (.csv file in Azure Blob Storage).</span></span> <span data-ttu-id="34366-179">Pracovný postup extrahuje obsah súboru .csv v určenom poradí stĺpcov.</span><span class="sxs-lookup"><span data-stu-id="34366-179">The workflow extracts the .csv file content in a specified column order.</span></span> <span data-ttu-id="34366-180">Tento pracovný postup bol zostavený tak, aby vykonával základné spracovanie chýb a zabezpečil, aby mal každý záznam e-mailovú adresu pred hydratáciou údajov v aplikácii Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="34366-180">This workflow has been built to perform basic error handling and ensure that each record has an email address before hydrating the data in Adobe Campaign Standard.</span></span> <span data-ttu-id="34366-181">Pracovný postup tiež extrahuje názov segmentu z názvu súboru pred aktualizáciou do údajov profilu ACS.</span><span class="sxs-lookup"><span data-stu-id="34366-181">The workflow also extracts the segment name from the filename before upserting into ACS Profile data.</span></span>

:::image type="content" source="media/ACS-import-workflow.png" alt-text="Snímka obrazovky z pracovného postupu importu v používateľskom rozhraní služby Adobe Campaign Standard.":::

## <a name="retrieve-the-audience-in-adobe-campaign-standard"></a><span data-ttu-id="34366-183">Získajte cieľovú skupinu v službe Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="34366-183">Retrieve the audience in Adobe Campaign Standard</span></span>

<span data-ttu-id="34366-184">Po importovaní údajov do aplikácie Adobe Campaign Standard [môžete vytvoriť pracovný postup](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) a [dopyt](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) zákazníkov na základe polí *Názov segmentu* a *Dátum segmentu* na výber profilov, ktoré boli identifikované pre našu vzorovú kampaň.</span><span class="sxs-lookup"><span data-stu-id="34366-184">Once the data is imported into Adobe Campaign Standard, you [can create a workflow](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) and [query](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) the customers based on the *Segment Name* and *Segment Date* to select profiles that were identified for our sample campaign.</span></span>

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a><span data-ttu-id="34366-185">Vytvorte a odošlite e-mail pomocou aplikácie Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="34366-185">Create and send the email using Adobe Campaign Standard</span></span>

<span data-ttu-id="34366-186">Vytvorte e-mailový obsah a potom [otestujte a odošlite](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) svoj e-mail.</span><span class="sxs-lookup"><span data-stu-id="34366-186">Create the email content and then [test and send](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) your email.</span></span>

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Vzorový e-mail s ponukou na obnovenie od spoločnosti Adobe Campaign Standard.":::
