---
title: Pripojte údaje z Common Data Model k účtu Azure Data Lake
description: Pracujte s údajmi z Common Data Model cez Azure Data Lake Storage.
ms.date: 05/29/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: 25de23e615704a72f6b41d98ae9418beb338e77e
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643477"
---
# <a name="connect-to-a-common-data-model-folder-using-an-azure-data-lake-account"></a><span data-ttu-id="123c4-103">Pripojte priečinok Common Data Model použitím účtu Azure Data Lake</span><span class="sxs-lookup"><span data-stu-id="123c4-103">Connect to a Common Data Model folder using an Azure Data Lake account</span></span>

<span data-ttu-id="123c4-104">Tento článok poskytuje informácie o tom, ako prijímať údaje z Common Data Model pomocou vášho účtu Azure Data Lake Storage Gen2.</span><span class="sxs-lookup"><span data-stu-id="123c4-104">This article provides information on how to ingest data from a Common Data Model folder using your Azure Data Lake Storage Gen2 account.</span></span>

## <a name="important-considerations"></a><span data-ttu-id="123c4-105">Dôležité aspekty</span><span class="sxs-lookup"><span data-stu-id="123c4-105">Important considerations</span></span>

- <span data-ttu-id="123c4-106">Údaje vo vašom úložisku Azure Data Lake musia zodpovedať štandardu Common Data Model.</span><span class="sxs-lookup"><span data-stu-id="123c4-106">Data in your Azure Data Lake needs to follow the Common Data Model standard.</span></span> <span data-ttu-id="123c4-107">Iné formáty momentálne nie sú podporované.</span><span class="sxs-lookup"><span data-stu-id="123c4-107">Other formats aren't supported at the moment.</span></span>

- <span data-ttu-id="123c4-108">Príjem údajov podporuje výhradne účty ukladacieho priestoru Azure Data Lake *Gen2*.</span><span class="sxs-lookup"><span data-stu-id="123c4-108">Data ingestion supports Azure Data Lake *Gen2* storage accounts exclusively.</span></span> <span data-ttu-id="123c4-109">Na príjem údajov nemôžete použiť účty ukladacieho priestoru Azure Data Lake Gen1.</span><span class="sxs-lookup"><span data-stu-id="123c4-109">You can't use Azure Data Lake Gen1 storage accounts to ingest data.</span></span>

- <span data-ttu-id="123c4-110">Ak chcete vykonať overenie pomocou objektu služby Azure, uistite sa, že je nakonfigurovaný vo vašom nájomníkovi.</span><span class="sxs-lookup"><span data-stu-id="123c4-110">To authenticate with an Azure service principal, make sure it's configured in your tenant.</span></span> <span data-ttu-id="123c4-111">Ďalšie informácie sa dozviete v článku [Pripojenie prehľadov cieľových skupín k účtu Azure Data Lake Storage Gen2 pomocou objektu služby Azure](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="123c4-111">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span>

- <span data-ttu-id="123c4-112">Azure Data Lake, ku ktorému sa chcete pripojiť a z ktorého prijímať údaje, musí byť v rovnakej oblasti Azure ako prostredie Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="123c4-112">The Azure Data Lake you want to connect and ingest data from have to be in the same Azure region as the Dynamics 365 Customer Insights environment.</span></span> <span data-ttu-id="123c4-113">Pripojenia k priečinku Common Data Model z dátového jazera v inej oblasti Azure nie sú podporované.</span><span class="sxs-lookup"><span data-stu-id="123c4-113">Connections to a Common Data Model folder from a data lake in a different Azure region is not supported.</span></span> <span data-ttu-id="123c4-114">Ak chcete spoznať oblasť Azure v prostredí, prejdite na časť **Správca** > **Systém** > **Informácie** v prehľadoch o cieľových skupinách.</span><span class="sxs-lookup"><span data-stu-id="123c4-114">To know the Azure region of the environment, go to **Admin** > **System** > **About** in audience insights.</span></span>

- <span data-ttu-id="123c4-115">Údaje uložené v online službách sa môžu ukladať na inom mieste ako tam, kde sa údaje spracúvajú alebo ukladajú v rámci služby Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="123c4-115">Data stored in online services, may be stored in a different location than where data is processed or stored in Dynamics 365 Customer Insights.</span></span><span data-ttu-id="123c4-116">Importovaním alebo pripojením sa k údajom uloženým v online službách súhlasíte s tým, že údaje je možné prenášať a ukladať pomocou Dynamics 365 Customer Insights.  [Ďalšie informácie nájdete v Centre dôveryhodnosti spoločnosti Microsoft.](https://www.microsoft.com/trust-center)</span><span class="sxs-lookup"><span data-stu-id="123c4-116"> By importing or connecting to data stored in online services, you agree that data can be transferred to and stored with Dynamics 365 Customer Insights. [Learn more at the Microsoft Trust Center.](https://www.microsoft.com/trust-center)</span></span>

## <a name="connect-to-a-common-data-model-folder"></a><span data-ttu-id="123c4-117">Pripojiť k priečinku Common Data Model</span><span class="sxs-lookup"><span data-stu-id="123c4-117">Connect to a Common Data Model folder</span></span>

1. <span data-ttu-id="123c4-118">V prehľadoch cieľových skupín prejdite na **Údaje** > **Zdroje údajov**.</span><span class="sxs-lookup"><span data-stu-id="123c4-118">In audience insights, go to **Data** > **Data sources**.</span></span>

1. <span data-ttu-id="123c4-119">Vyberte položku **Pridať zdroj údajov**.</span><span class="sxs-lookup"><span data-stu-id="123c4-119">Select **Add data source**.</span></span>

1. <span data-ttu-id="123c4-120">Vyberte položku **Pripojiť k priečinku Common Data Model**, zadajte **Názov** zdroja údajov a vyberte položku **Ďalej**.</span><span class="sxs-lookup"><span data-stu-id="123c4-120">Select **Connect to a Common Data Model folder**, enter a **Name** for the data source, and select **Next**.</span></span>

1. <span data-ttu-id="123c4-121">Na overenie si môžete vybrať medzi použitím možnosti založenej na zdrojoch a možnosti založenej na predplatnom.</span><span class="sxs-lookup"><span data-stu-id="123c4-121">You can choose between using a resource-based option and a subscription-based option for authentication.</span></span> <span data-ttu-id="123c4-122">Ďalšie informácie sa dozviete v článku [Pripojenie prehľadov cieľových skupín k účtu Azure Data Lake Storage Gen2 pomocou objektu služby Azure](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="123c4-122">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="123c4-123">Zadajte informáciu **Kontajner** a vyberte položku **Ďalej**.</span><span class="sxs-lookup"><span data-stu-id="123c4-123">Enter the **Container** information and select **Next**.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="123c4-124">![Dialógové okno na zadávanie podrobností o pripojení k Azure Data Lake](media/enter-new-storage-details.png)</span><span class="sxs-lookup"><span data-stu-id="123c4-124">![Dialog box to enter connection details for Azure Data Lake](media/enter-new-storage-details.png)</span></span>

1. <span data-ttu-id="123c4-125">V dialógovom okne **Vybrať priečinok Common Data Model** vyberte súbor model.json, z ktorého chcete importovať údaje, a vyberte položku **Ďalej**.</span><span class="sxs-lookup"><span data-stu-id="123c4-125">In the **Select a Common Data Model folder** dialog, select the model.json file to import data from, and select **Next**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="123c4-126">Žiadny súbor model.json spojený s iným zdrojom údajov v prostredí sa v zozname nezobrazí.</span><span class="sxs-lookup"><span data-stu-id="123c4-126">Any model.json file associated with another data source in the environment won't show in the list.</span></span>

1. <span data-ttu-id="123c4-127">Vo vybranom súbore model.json získate zoznam dostupných entít.</span><span class="sxs-lookup"><span data-stu-id="123c4-127">You'll get a list of available entities in the selected model.json file.</span></span> <span data-ttu-id="123c4-128">Môžete skontrolovať a vybrať zo zoznamu dostupných entít a vybrať položku **Uložiť**.</span><span class="sxs-lookup"><span data-stu-id="123c4-128">You can review and select from the list of available entities and select **Save**.</span></span> <span data-ttu-id="123c4-129">Všetky vybraté entity sa prijmú z nového zdroja údajov.</span><span class="sxs-lookup"><span data-stu-id="123c4-129">All of the selected entities will be ingested from the new data source.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="123c4-130">![Dialógové okno so zoznamom entít zo súboru model.json](media/review-entities.png)</span><span class="sxs-lookup"><span data-stu-id="123c4-130">![Dialog box showing a list of entities from a model.json file](media/review-entities.png)</span></span>

8. <span data-ttu-id="123c4-131">Uveďte, pre ktoré údajové entity chcete povoliť profilovanie údajov, a vyberte položku **Uložiť**.</span><span class="sxs-lookup"><span data-stu-id="123c4-131">Indicate which data entities you want to enable data profiling and select **Save**.</span></span> <span data-ttu-id="123c4-132">Profilovanie údajov umožňuje analýzy a ďalšie funkcie.</span><span class="sxs-lookup"><span data-stu-id="123c4-132">Data profiling enables analytics and other capabilities.</span></span> <span data-ttu-id="123c4-133">Môžete vybrať celú entitu, ktorá vyberie všetky atribúty z entity, alebo môžete vybrať určité atribúty podľa vlastného výberu.</span><span class="sxs-lookup"><span data-stu-id="123c4-133">You can select the whole entity, which selects all attributes from the entity, or select certain attributes of your choice.</span></span> <span data-ttu-id="123c4-134">V predvolenom nastavení nie je pre profilovanie údajov povolená žiadna entita.</span><span class="sxs-lookup"><span data-stu-id="123c4-134">By default, no entity is enabled for data profiling.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="123c4-135">![Dialógové okno zobrazujúce profilovanie údajov](media/dataprofiling-entities.png)</span><span class="sxs-lookup"><span data-stu-id="123c4-135">![Dialog box showing a data profiling](media/dataprofiling-entities.png)</span></span>

9. <span data-ttu-id="123c4-136">Po uložení vašich výberov sa otvorí stránka **Zdroje údajov**.</span><span class="sxs-lookup"><span data-stu-id="123c4-136">After saving your selections, the **Data sources** page opens.</span></span> <span data-ttu-id="123c4-137">Teraz by ste mali vidieť pripojenie priečinka Common Data Model ako zdroja údajov.</span><span class="sxs-lookup"><span data-stu-id="123c4-137">You should now see the Common Data Model folder connection as a data source.</span></span>

> [!NOTE]
> <span data-ttu-id="123c4-138">Súbor model.json sa môže v rovnakom prostredí spojiť iba s jedným zdrojom údajov.</span><span class="sxs-lookup"><span data-stu-id="123c4-138">A model.json file can only associate with one data source in the same environment.</span></span> <span data-ttu-id="123c4-139">Rovnaký súbor model.json je však možné použiť pre zdroje údajov vo viacerých prostrediach.</span><span class="sxs-lookup"><span data-stu-id="123c4-139">However, the same model.json file can be used for data sources in multiple environments.</span></span>

## <a name="edit-a-common-data-model-folder-data-source"></a><span data-ttu-id="123c4-140">Úprava zdroja údajov pre Common Data Model</span><span class="sxs-lookup"><span data-stu-id="123c4-140">Edit a Common Data Model folder data source</span></span>

<span data-ttu-id="123c4-141">Môžete aktualizovať prístupový kľúč pre účet úložiska, ktoré obsahuje priečinok Common Data Model.</span><span class="sxs-lookup"><span data-stu-id="123c4-141">You can update the access key for the storage account containing the Common Data Model folder.</span></span> <span data-ttu-id="123c4-142">Môžete tiež zmeniť súbor model.json.</span><span class="sxs-lookup"><span data-stu-id="123c4-142">You may also change the model.json file.</span></span> <span data-ttu-id="123c4-143">Ak sa chcete pripojiť k inému kontajneru z účtu úložiska alebo zmeniť názov účtu, musíte [vytvoriť nové pripojenie k zdroju údajov](#connect-to-a-common-data-model-folder).</span><span class="sxs-lookup"><span data-stu-id="123c4-143">To connect to a different container from your storage account, or change the account name, [create a new data source connection](#connect-to-a-common-data-model-folder).</span></span>

1. <span data-ttu-id="123c4-144">V prehľadoch cieľových skupín prejdite na **Údaje** > **Zdroje údajov**.</span><span class="sxs-lookup"><span data-stu-id="123c4-144">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="123c4-145">Vedľa zdroja údajov, ktorý chcete aktualizovať, vyberte tri bodky.</span><span class="sxs-lookup"><span data-stu-id="123c4-145">Next to the data source you'd like to update, select the ellipsis.</span></span>

3. <span data-ttu-id="123c4-146">Zo zoznamu vyberte možnosť **Upraviť**.</span><span class="sxs-lookup"><span data-stu-id="123c4-146">Select the **Edit** option from the list.</span></span>

4. <span data-ttu-id="123c4-147">Prípadne aktualizujte **Prístupový kľúč** a vyberte položku **Ďalej**.</span><span class="sxs-lookup"><span data-stu-id="123c4-147">Optionally, update the **Access key** and select **Next**.</span></span>

   ![Dialógové okno na úpravu a aktualizáciu prístupového kľúča k existujúcemu zdroju údajov](media/edit-access-key.png)

5. <span data-ttu-id="123c4-149">Prípadne môžete aktualizáciu vykonať cez pripojenie kľúča účtu na pripojenie založené na zdrojoch alebo predplatnom.</span><span class="sxs-lookup"><span data-stu-id="123c4-149">Optionally, you can update from an account key connection to a resource-based or a subscription-based connection.</span></span> <span data-ttu-id="123c4-150">Ďalšie informácie sa dozviete v článku [Pripojenie prehľadov cieľových skupín k účtu Azure Data Lake Storage Gen2 pomocou objektu služby Azure](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="123c4-150">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="123c4-151">Pri aktualizácii pripojenia nemôžete zmeniť informácie o **kontajneri**.</span><span class="sxs-lookup"><span data-stu-id="123c4-151">You can't change **Container** information when updating the connection.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="123c4-152">![Dialógové okno na zadávanie podrobností o pripojení k Azure Data Lake](media/enter-existing-storage-details.png)</span><span class="sxs-lookup"><span data-stu-id="123c4-152">![Dialog box to enter connection details for Azure Data Lake](media/enter-existing-storage-details.png)</span></span>

6. <span data-ttu-id="123c4-153">Prípadne vyberte iný súbor model.json s inou množinou entít z kontajnera.</span><span class="sxs-lookup"><span data-stu-id="123c4-153">Optionally, choose a different model.json file with a different set of entities from the container.</span></span>

7. <span data-ttu-id="123c4-154">Prípadne môžete vybrať ďalšie entity na príjem.</span><span class="sxs-lookup"><span data-stu-id="123c4-154">Optionally, you can select additional entities to ingest.</span></span> <span data-ttu-id="123c4-155">Ak už neexistujú žiadne závislosti, môžete odstrániť aj všetky už vybrané entity.</span><span class="sxs-lookup"><span data-stu-id="123c4-155">You can also remove any already selected entities if there are no dependencies.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="123c4-156">Ak existujú závislosti na existujúcom súbore model.json a množine entít, zobrazí sa chybová správa a vy nebudete môcť vybrať iný súbor model.json.</span><span class="sxs-lookup"><span data-stu-id="123c4-156">If there are dependencies on the existing model.json file and the set of entities, you'll see an error message and can't select a different model.json file.</span></span> <span data-ttu-id="123c4-157">Pred zmenou súboru model.json odstráňte tieto závislosti alebo vytvorte nový zdroj údajov so súborom model.json, ktorý chcete použiť na to, aby ste zabránili odstráneniu závislostí.</span><span class="sxs-lookup"><span data-stu-id="123c4-157">Remove those dependencies before changing the model.json file or create a new data source with the model.json file that you want to use to avoid removing the dependencies.</span></span>

8. <span data-ttu-id="123c4-158">Prípadne môžete vybrať ďalšie atribúty alebo entity, ktoré povolia profilovanie údajov alebo zakážu tie už vybrané.</span><span class="sxs-lookup"><span data-stu-id="123c4-158">Optionally, you can select additional attributes or entities to enable data profiling on or disable already selected ones.</span></span>   
