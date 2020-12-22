---
title: Slúži na vytvorenie a spravovanie prostredí
description: Zistite, ako sa môžete zaregistrovať do služby a spravovať prostredia.
ms.date: 11/10/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
ms.reviewer: nimagen
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 010336445d0825a7ff82d1b7a65702fc12245788
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 11/25/2020
ms.locfileid: "4644152"
---
# <a name="manage-environments"></a><span data-ttu-id="a06f4-103">Správa prostredí</span><span class="sxs-lookup"><span data-stu-id="a06f4-103">Manage environments</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="a06f4-104">Tento článok vysvetľuje, ako môžete vytvoriť novú organizáciu a ako zriadiť prostredie.</span><span class="sxs-lookup"><span data-stu-id="a06f4-104">This article explains how to create a new organization and how to provision an environment.</span></span>

## <a name="sign-up-and-create-an-organization"></a><span data-ttu-id="a06f4-105">Zaregistrujte sa a vytvorte organizáciu</span><span class="sxs-lookup"><span data-stu-id="a06f4-105">Sign up and create an organization</span></span>

1. <span data-ttu-id="a06f4-106">Prejsť na webovú lokalitu [Dynamics 365 Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/).</span><span class="sxs-lookup"><span data-stu-id="a06f4-106">Go to the [Dynamics 365 Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/) website.</span></span>

2. <span data-ttu-id="a06f4-107">Vyberte položku **Začíname**.</span><span class="sxs-lookup"><span data-stu-id="a06f4-107">Select **Get Started**.</span></span>

3. <span data-ttu-id="a06f4-108">Vyberte preferovaný scenár registrácie a zodpovedajúci odkaz.</span><span class="sxs-lookup"><span data-stu-id="a06f4-108">Choose your preferred sign-up scenario and select the corresponding link.</span></span>

4. <span data-ttu-id="a06f4-109">Prijmite zmluvné podmienky a výberom možnosti **Pokračovať** začnite vytvárať organizáciu.</span><span class="sxs-lookup"><span data-stu-id="a06f4-109">Accept the terms and conditions and select **Continue** to start creating the organization.</span></span>

5. <span data-ttu-id="a06f4-110">Po vytvorení prostredia budete presmerovaní do [Customer Insights](https://home.ci.ai.dynamics.com).</span><span class="sxs-lookup"><span data-stu-id="a06f4-110">After the environment is created, you'll be redirected to [Customer Insights](https://home.ci.ai.dynamics.com).</span></span>

6. <span data-ttu-id="a06f4-111">Pomocou demonštračného prostredia preskúmajte aplikáciu alebo vytvorte nové prostredie podľa krokov v nasledujúcej sekcii.</span><span class="sxs-lookup"><span data-stu-id="a06f4-111">Use the demo environment to explore the app, or create a new environment by following the steps in the next section.</span></span>

7. <span data-ttu-id="a06f4-112">Po špecifikácii nastavení prostredia vyberte položku **vytvoriť**.</span><span class="sxs-lookup"><span data-stu-id="a06f4-112">After specifying the environment settings, select **Create**.</span></span>

8. <span data-ttu-id="a06f4-113">Po úspešnom vytvorení prostredia budete prihlásení.</span><span class="sxs-lookup"><span data-stu-id="a06f4-113">You'll be signed in after the environment was created successfully.</span></span>

## <a name="create-an-environment-in-an-existing-organization"></a><span data-ttu-id="a06f4-114">Vytvorenie prostredia v existujúcej organizácii</span><span class="sxs-lookup"><span data-stu-id="a06f4-114">Create an environment in an existing organization</span></span>

<span data-ttu-id="a06f4-115">Existujú dva spôsoby vytvorenia nového prostredia.</span><span class="sxs-lookup"><span data-stu-id="a06f4-115">There are two ways to create a new environment.</span></span> <span data-ttu-id="a06f4-116">Môžete buď špecifikovať úplne novú konfiguráciu alebo môžete skopírovať niektoré nastavenia konfigurácie z existujúceho prostredia.</span><span class="sxs-lookup"><span data-stu-id="a06f4-116">You can either specify an entirely new configuration, or you can copy some configuration settings from an existing environment.</span></span>

<span data-ttu-id="a06f4-117">Vytvorenie prostredia:</span><span class="sxs-lookup"><span data-stu-id="a06f4-117">To create an environment:</span></span>

1. <span data-ttu-id="a06f4-118">Vyberte symbol **Nastavenia** v záhlaví aplikácie.</span><span class="sxs-lookup"><span data-stu-id="a06f4-118">Select the **Settings** symbol in the header of the app.</span></span>

1. <span data-ttu-id="a06f4-119">Vyberte **Nové prostredie**.</span><span class="sxs-lookup"><span data-stu-id="a06f4-119">Select **New environment**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="a06f4-120">![Nastavenia prostredia](media/environment-settings-dialog.png)</span><span class="sxs-lookup"><span data-stu-id="a06f4-120">![Environment settings](media/environment-settings-dialog.png)</span></span>

1. <span data-ttu-id="a06f4-121">V dialógovom okne **Vytvoriť nové prostredie** vyberte **Nové prostredie**.</span><span class="sxs-lookup"><span data-stu-id="a06f4-121">In the **Create new environment** dialog, select **New environment**.</span></span>

   <span data-ttu-id="a06f4-122">Ak chcete [kopírovať údaje z aktuálneho prostredia](#additional-considerations-for-copy-configuration-preview), vyberte **Kopírovať z existujúceho prostredia**.</span><span class="sxs-lookup"><span data-stu-id="a06f4-122">If you want to [copy data from the current environment](#additional-considerations-for-copy-configuration-preview), select **Copy from existing environment**.</span></span> <span data-ttu-id="a06f4-123">Zobrazí sa zoznam všetkých dostupných prostredí vo vašej organizácii, z ktorých môžete kopírovať údaje.</span><span class="sxs-lookup"><span data-stu-id="a06f4-123">You'll see a list of all available environments in your organization where you can copy data from.</span></span>

1. <span data-ttu-id="a06f4-124">Uveďte nasledujúce podrobnosti:</span><span class="sxs-lookup"><span data-stu-id="a06f4-124">Provide the following details:</span></span>
   - <span data-ttu-id="a06f4-125">**Názov**: Názov tohto prostredia.</span><span class="sxs-lookup"><span data-stu-id="a06f4-125">**Name**: The name for this environment.</span></span> <span data-ttu-id="a06f4-126">Toto pole je už vyplnené, ak ste skopírovali existujúce prostredie, ale môžete ho zmeniť.</span><span class="sxs-lookup"><span data-stu-id="a06f4-126">This field is already filled in if you've copied an existing environment, but you can change it.</span></span>
   - <span data-ttu-id="a06f4-127">**Región**: Región, v ktorom je služba nasadená a hosťovaná.</span><span class="sxs-lookup"><span data-stu-id="a06f4-127">**Region**: The region into which the service is deployed and hosted.</span></span>
   - <span data-ttu-id="a06f4-128">**Typ**: Vyberte, či chcete vytvoriť výrobné alebo izolované prostredie.</span><span class="sxs-lookup"><span data-stu-id="a06f4-128">**Type**: Select whether you want to create a Production or Sandbox environment.</span></span>

2. <span data-ttu-id="a06f4-129">Voliteľne môžete vybrať **Rozšírené nastavenia**:</span><span class="sxs-lookup"><span data-stu-id="a06f4-129">Optionally, you can select **Advanced settings**:</span></span>

   - <span data-ttu-id="a06f4-130">**Uložiť všetky údaje do**: Určuje, kam sa majú ukladať výstupné údaje vygenerované z Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="a06f4-130">**Save all data to**: Specifies where you want to store the output data generated from Customer Insights.</span></span> <span data-ttu-id="a06f4-131">Budete mať dve možnosti: **Úložisko Customer Insights** (Azure Data Lake spravované tímom Customer Insights) a **Azure Data Lake Storage** Gen2 (vaše vlastné úložisko Azure Data Lake Storage).</span><span class="sxs-lookup"><span data-stu-id="a06f4-131">You'll have two options: **Customer Insights storage** (an Azure Data Lake managed by the Customer Insights team) and **Azure Data Lake Storage Gen2** (your own Azure Data Lake Storage).</span></span> <span data-ttu-id="a06f4-132">V predvolenom nastavení je vybraná možnosť úložiska Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="a06f4-132">By default, the Customer Insights storage option is selected.</span></span>

   > [!NOTE]
   > <span data-ttu-id="a06f4-133">Uložením údajov do Azure Data Lake Storage súhlasíte s tým, že údaje budú prenesené a uložené v príslušnom geografickom umiestnení pre dané konto ukladacieho priestoru v službe Azure, ktoré sa môže líšiť od umiestnenia, v ktorom sú údaje uložené v aplikácii Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="a06f4-133">By saving data to Azure Data Lake Storage, you agree that data will be transferred to and stored in the appropriate geographic location for that Azure storage account, which may differ from where data is stored in Dynamics 365 Customer Insights.</span></span> [<span data-ttu-id="a06f4-134">Ďalšie informácie nájdete v centre dôveryhodnosti spoločnosti Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a06f4-134">Learn more at the Microsoft Trust Center.</span></span>](https://www.microsoft.com/trust-center)
   >
   > <span data-ttu-id="a06f4-135">V súčasnosti sú prijaté entity vždy uložené v dátovom jazere spravovanom službou Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="a06f4-135">Currently, ingested entities are always stored in the Customer Insights managed data lake.</span></span>
   > <span data-ttu-id="a06f4-136">Podporujeme iba účty ukladacieho priestoru Azure Data Lake Gen2 z rovnakej oblasti Azure, ktorú ste vybrali pri vytváraní prostredia.</span><span class="sxs-lookup"><span data-stu-id="a06f4-136">We support only Azure Data Lake Gen2 storage accounts from the same Azure region you selected when creating the environment.</span></span>
   > <span data-ttu-id="a06f4-137">Podporujeme iba účty úložísk s povoleným hierarchickým názvom priestoru (HNS) Azure Data Lake Gen2.</span><span class="sxs-lookup"><span data-stu-id="a06f4-137">We support only Azure Data Lake Gen2 Hierarchical Name Space (HNS) enabled storage accounts.</span></span>

   - <span data-ttu-id="a06f4-138">V prípade možnosti Azure Data Lake Storage Gen2 si môžete vybrať medzi použitím možnosti založenej na zdrojoch a možnosti založenej na predplatnom.</span><span class="sxs-lookup"><span data-stu-id="a06f4-138">For the Azure Data Lake Storage Gen2 option, you can choose between a resource-based option and a subscription-based option for authentication.</span></span> <span data-ttu-id="a06f4-139">Ďalšie informácie sa dozviete v článku [Pripojenie prehľadov cieľových skupín k účtu Azure Data Lake Storage Gen2 pomocou objektu služby Azure](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="a06f4-139">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="a06f4-140">Názov **kontajnera** sa nedá zmeniť a bude znieť „customerinsights“.</span><span class="sxs-lookup"><span data-stu-id="a06f4-140">The **Container** name can't be changed and will be "customerinsights".</span></span>
   
   - <span data-ttu-id="a06f4-141">Ak chcete použiť [predikcie](predictions.md), navštívte adresu URL inštancie služby Common Data Service v poli **Adresa servera** v sekcii **Používanie predikcií**.</span><span class="sxs-lookup"><span data-stu-id="a06f4-141">If you want to use [predictions](predictions.md), enter the Common Data Service instance URL in the **Server address** field under **Use predictions**.</span></span>

   <span data-ttu-id="a06f4-142">Keď spustíte procesy, ako je napríklad príjem údajov alebo vytváranie segmentov, vo vyššie uvedenom účte úložiska sa vytvoria zodpovedajúce priečinky.</span><span class="sxs-lookup"><span data-stu-id="a06f4-142">When you run processes, such as data ingestion or segment creation, corresponding folders will be created in the storage account you specified above.</span></span> <span data-ttu-id="a06f4-143">Dátové súbory a súbory model.json sa vytvoria a pridajú do príslušných podpriečinkov na základe spusteného procesu.</span><span class="sxs-lookup"><span data-stu-id="a06f4-143">Data files and model.json files will be created and added to the respective subfolders based on the process you run.</span></span>

   <span data-ttu-id="a06f4-144">Ak vytvoríte viac prostredí služby Customer Insights a rozhodnete sa uložiť výstupné entity z týchto prostredí do svojho účtu úložiska, pre každé prostredie sa vytvoria samostatné priečinky s výrazom ci_<environmentid> v kontajneri.</span><span class="sxs-lookup"><span data-stu-id="a06f4-144">If you create multiple environments of Customer Insights and choose to save the output entities from those environments in your storage account, separate folders will be created for each environment with ci_<environmentid> in the container.</span></span>

### <a name="additional-considerations-for-copy-configuration-preview"></a><span data-ttu-id="a06f4-145">Ďalšie informácie o konfigurácii kopírovania (ukážka)</span><span class="sxs-lookup"><span data-stu-id="a06f4-145">Additional considerations for copy configuration (preview)</span></span>

<span data-ttu-id="a06f4-146">Skopírujú sa nasledujúce konfiguračné nastavenia:</span><span class="sxs-lookup"><span data-stu-id="a06f4-146">The following configuration settings are copied:</span></span>

- <span data-ttu-id="a06f4-147">Konfigurácie funkcií</span><span class="sxs-lookup"><span data-stu-id="a06f4-147">Feature configurations</span></span>
- <span data-ttu-id="a06f4-148">Prijaté/importované zdroje údajov</span><span class="sxs-lookup"><span data-stu-id="a06f4-148">Inegsted/imported data sources</span></span>
- <span data-ttu-id="a06f4-149">Zjednotenie údajov (Mapovanie, Zosúladenie, Zlúčenie)</span><span class="sxs-lookup"><span data-stu-id="a06f4-149">Data unification (Map, Match, Merge) configuration</span></span>
- <span data-ttu-id="a06f4-150">Segmenty</span><span class="sxs-lookup"><span data-stu-id="a06f4-150">Segments</span></span>
- <span data-ttu-id="a06f4-151">Miery</span><span class="sxs-lookup"><span data-stu-id="a06f4-151">Measures</span></span>
- <span data-ttu-id="a06f4-152">Vzťahy</span><span class="sxs-lookup"><span data-stu-id="a06f4-152">Relationships</span></span>
- <span data-ttu-id="a06f4-153">Aktivity</span><span class="sxs-lookup"><span data-stu-id="a06f4-153">Activities</span></span>
- <span data-ttu-id="a06f4-154">Index vyhľadávania a filtrovania</span><span class="sxs-lookup"><span data-stu-id="a06f4-154">Search & filter Index</span></span>
- <span data-ttu-id="a06f4-155">Ciele exportu</span><span class="sxs-lookup"><span data-stu-id="a06f4-155">Export destinations</span></span>
- <span data-ttu-id="a06f4-156">Plánovaná obnova</span><span class="sxs-lookup"><span data-stu-id="a06f4-156">Scheduled refresh</span></span>
- <span data-ttu-id="a06f4-157">Obohatenia</span><span class="sxs-lookup"><span data-stu-id="a06f4-157">Enrichments</span></span>
- <span data-ttu-id="a06f4-158">Spravovanie modelov</span><span class="sxs-lookup"><span data-stu-id="a06f4-158">Model management</span></span>
- <span data-ttu-id="a06f4-159">Priradenia roly</span><span class="sxs-lookup"><span data-stu-id="a06f4-159">Role assignments</span></span>

<span data-ttu-id="a06f4-160">Nasledujúce nastavenia sa *neskopírujú*:</span><span class="sxs-lookup"><span data-stu-id="a06f4-160">The following settings are *not* copied:</span></span>

- <span data-ttu-id="a06f4-161">Profily zákazníkov.</span><span class="sxs-lookup"><span data-stu-id="a06f4-161">Customer profiles.</span></span>
- <span data-ttu-id="a06f4-162">Poverenia zdroja údajov.</span><span class="sxs-lookup"><span data-stu-id="a06f4-162">Data source credentials.</span></span> <span data-ttu-id="a06f4-163">Budete musieť poskytnúť poverenia pre každý zdroj údajov a ručne obnoviť zdroje údajov.</span><span class="sxs-lookup"><span data-stu-id="a06f4-163">You'll have to provide the credentials for every data source and refresh the data sources manually.</span></span>
- <span data-ttu-id="a06f4-164">Zdroje údajov zo zložky Common Data Model a spravovaného fondu Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="a06f4-164">Data sources from Common Data Model folder and Common Data Service managed lake.</span></span> <span data-ttu-id="a06f4-165">Tieto zdroje údajov budete musieť vytvoriť ručne s rovnakým názvom ako v zdrojovom prostredí.</span><span class="sxs-lookup"><span data-stu-id="a06f4-165">You'll have to create those data sources manually with the same name as in the source environment.</span></span>

<span data-ttu-id="a06f4-166">Po skopírovaní prostredia sa zobrazí potvrdzovacia správa o vytvorení nového prostredia.</span><span class="sxs-lookup"><span data-stu-id="a06f4-166">When you copy an environment, you'll see a confirmation message that the new environment has been created.</span></span> <span data-ttu-id="a06f4-167">Stlačte možnosť **Prejsť na zdroje údajov**, čím si zobrazíte zoznam zdrojov údajov.</span><span class="sxs-lookup"><span data-stu-id="a06f4-167">Select **Go to data sources** to see the list of data sources.</span></span>

<span data-ttu-id="a06f4-168">Všetky zdroje údajov sa zobrazia so stavom **Vyžadované poverenia**.</span><span class="sxs-lookup"><span data-stu-id="a06f4-168">All the data sources will show a **Credentials Required** status.</span></span> <span data-ttu-id="a06f4-169">Upravte zdroje údajov a zadaním poverení ich obnovte.</span><span class="sxs-lookup"><span data-stu-id="a06f4-169">Edit the data sources and enter the credentials to refresh them.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="a06f4-170">![Zdroje údajov skopírované](media/data-sources-copied.png)</span><span class="sxs-lookup"><span data-stu-id="a06f4-170">![Data sources copied](media/data-sources-copied.png)</span></span>

<span data-ttu-id="a06f4-171">Po obnovení zdrojov údajov prejdite na stránku **Údaje** > **Zjednotiť**.</span><span class="sxs-lookup"><span data-stu-id="a06f4-171">After refreshing the data sources, go to **Data** > **Unify**.</span></span> <span data-ttu-id="a06f4-172">Tu nájdete nastavenia zo zdrojového prostredia.</span><span class="sxs-lookup"><span data-stu-id="a06f4-172">Here you'll find settings from the source environment.</span></span> <span data-ttu-id="a06f4-173">Upravte ich podľa potreby alebo stlačte možnosť **Spustiť**, čím začnete proces zjednotenia údajov a vytvoríte jednotnú entitu zákazníka.</span><span class="sxs-lookup"><span data-stu-id="a06f4-173">Edit them as needed or select **Run** to start the data unification process and create the unified customer entity.</span></span>

<span data-ttu-id="a06f4-174">Po dokončení zjednotenia údajov prejdite na stránku **Opatrenia** a **Segmenty**, čím ich tiež obnovíte.</span><span class="sxs-lookup"><span data-stu-id="a06f4-174">When the data unification is complete, go to **Measures** and **Segments** to refresh them too.</span></span>

## <a name="edit-an-existing-environment"></a><span data-ttu-id="a06f4-175">Úprava existujúceho prostredia</span><span class="sxs-lookup"><span data-stu-id="a06f4-175">Edit an existing environment</span></span>

<span data-ttu-id="a06f4-176">Môžete upraviť niektoré podrobnosti o existujúcich prostrediach.</span><span class="sxs-lookup"><span data-stu-id="a06f4-176">You can edit some of the details of existing environments.</span></span>

1. <span data-ttu-id="a06f4-177">Prejdite do **Správca** > **Systém** > **Informácie**.</span><span class="sxs-lookup"><span data-stu-id="a06f4-177">Go to **Admin** > **System** > **About**.</span></span>

2. <span data-ttu-id="a06f4-178">Vyberte **Upraviť**.</span><span class="sxs-lookup"><span data-stu-id="a06f4-178">Select **Edit**.</span></span>

3. <span data-ttu-id="a06f4-179">Môžete aktualizovať **Zobrazovaný názov** prostredia, ale nemôžete zmeniť **Región** ani **Typ**.</span><span class="sxs-lookup"><span data-stu-id="a06f4-179">You can update the environment's **Display name**, but you can't change the **Region** or **Type**.</span></span>

4. <span data-ttu-id="a06f4-180">Ak je prostredie nakonfigurované na ukladanie údajov do Azure Data Lake Storage Gen2, môžete aktualizovať **Kľúč účtu**.</span><span class="sxs-lookup"><span data-stu-id="a06f4-180">If an environment is configured to store data in Azure Data Lake Storage Gen2, you can update the **Account key**.</span></span> <span data-ttu-id="a06f4-181">Nemôžete však zmeniť **Názov účtu** ani názov **Kontajnera**.</span><span class="sxs-lookup"><span data-stu-id="a06f4-181">However, you can't change the **Account name** or **Container** name.</span></span>

5. <span data-ttu-id="a06f4-182">Prípadne môžete aktualizáciu vykonať cez pripojenie založené na kľúči účtu na pripojenie založené na zdrojoch alebo predplatnom.</span><span class="sxs-lookup"><span data-stu-id="a06f4-182">Optionally, you can update from an account key based connection to a resource-based or subscription-based connection.</span></span> <span data-ttu-id="a06f4-183">Po inovácii sa po aktualizácii už nebudete môcť vrátiť ku kľúču účtu.</span><span class="sxs-lookup"><span data-stu-id="a06f4-183">Once upgraded, you cannot revert to account key after the update.</span></span> <span data-ttu-id="a06f4-184">Ďalšie informácie sa dozviete v článku [Pripojenie prehľadov cieľových skupín k účtu Azure Data Lake Storage Gen2 pomocou objektu služby Azure](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="a06f4-184">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="a06f4-185">Pri aktualizácii pripojenia nemôžete zmeniť informácie o **kontajneri**.</span><span class="sxs-lookup"><span data-stu-id="a06f4-185">You can't change **Container** information when updating the connection.</span></span>

## <a name="reset-an-existing-environment"></a><span data-ttu-id="a06f4-186">Reset existujúceho prostredia</span><span class="sxs-lookup"><span data-stu-id="a06f4-186">Reset an existing environment</span></span>

<span data-ttu-id="a06f4-187">Ak chcete odstrániť všetky konfigurácie a odobrať prijaté údaje, môžete prostredie resetovať do prázdneho stavu.</span><span class="sxs-lookup"><span data-stu-id="a06f4-187">You can reset an environment to an empty state if you want to delete all configurations and remove the ingested data.</span></span>

1.  <span data-ttu-id="a06f4-188">Prejdite do **Správca** > **Systém** > **Informácie**.</span><span class="sxs-lookup"><span data-stu-id="a06f4-188">Go to **Admin** > **System** > **About**.</span></span>

2.  <span data-ttu-id="a06f4-189">Vyberte položku **Resetovať**.</span><span class="sxs-lookup"><span data-stu-id="a06f4-189">Select **Reset**.</span></span> 

3.  <span data-ttu-id="a06f4-190">Ak chcete potvrdiť odstránenie, zadajte názov prostredia a vyberte položku **Resetovať**.</span><span class="sxs-lookup"><span data-stu-id="a06f4-190">To confirm the deletion, enter the environment name and select **Reset**.</span></span>


## <a name="delete-an-existing-environment"></a><span data-ttu-id="a06f4-191">Odstránenie existujúceho prostredia</span><span class="sxs-lookup"><span data-stu-id="a06f4-191">Delete an existing environment</span></span>

1. <span data-ttu-id="a06f4-192">Prejdite do **Správca** > **Systém** > **Informácie**.</span><span class="sxs-lookup"><span data-stu-id="a06f4-192">Go to **Admin** > **System** > **About**.</span></span>

1. <span data-ttu-id="a06f4-193">Vyberte **Odstrániť**.</span><span class="sxs-lookup"><span data-stu-id="a06f4-193">Select **Delete**.</span></span>

1. <span data-ttu-id="a06f4-194">Odstránenie potvrdíte zadaním názvu prostredia a výberom položky **Odstrániť**.</span><span class="sxs-lookup"><span data-stu-id="a06f4-194">To confirm the deletion, enter the environment name and select **Delete**.</span></span>
