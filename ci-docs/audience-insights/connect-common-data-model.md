---
title: Pripojte údaje z Common Data Model k účtu Azure Data Lake
description: Pracujte s údajmi z Common Data Model cez Azure Data Lake Storage.
ms.date: 05/29/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 385406b706890d741fec2694c190c0fada7809d7
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596564"
---
# <a name="connect-to-a-common-data-model-folder-using-an-azure-data-lake-account"></a><span data-ttu-id="6f699-103">Pripojte priečinok Common Data Model použitím účtu Azure Data Lake</span><span class="sxs-lookup"><span data-stu-id="6f699-103">Connect to a Common Data Model folder using an Azure Data Lake account</span></span>

<span data-ttu-id="6f699-104">Tento článok poskytuje informácie o tom, ako prijímať údaje z Common Data Model pomocou vášho účtu Azure Data Lake Storage Gen2.</span><span class="sxs-lookup"><span data-stu-id="6f699-104">This article provides information on how to ingest data from a Common Data Model folder using your Azure Data Lake Storage Gen2 account.</span></span>

## <a name="important-considerations"></a><span data-ttu-id="6f699-105">Dôležité aspekty</span><span class="sxs-lookup"><span data-stu-id="6f699-105">Important considerations</span></span>

- <span data-ttu-id="6f699-106">Údaje vo vašom úložisku Azure Data Lake musia zodpovedať štandardu Common Data Model.</span><span class="sxs-lookup"><span data-stu-id="6f699-106">Data in your Azure Data Lake needs to follow the Common Data Model standard.</span></span> <span data-ttu-id="6f699-107">Iné formáty momentálne nie sú podporované.</span><span class="sxs-lookup"><span data-stu-id="6f699-107">Other formats aren't supported at the moment.</span></span>

- <span data-ttu-id="6f699-108">Príjem údajov podporuje výhradne účty ukladacieho priestoru Azure Data Lake *Gen2*.</span><span class="sxs-lookup"><span data-stu-id="6f699-108">Data ingestion supports Azure Data Lake *Gen2* storage accounts exclusively.</span></span> <span data-ttu-id="6f699-109">Na príjem údajov nemôžete použiť účty ukladacieho priestoru Azure Data Lake Gen1.</span><span class="sxs-lookup"><span data-stu-id="6f699-109">You can't use Azure Data Lake Gen1 storage accounts to ingest data.</span></span>

- <span data-ttu-id="6f699-110">Ak chcete vykonať overenie pomocou objektu služby Azure, uistite sa, že je nakonfigurovaný vo vašom nájomníkovi.</span><span class="sxs-lookup"><span data-stu-id="6f699-110">To authenticate with an Azure service principal, make sure it's configured in your tenant.</span></span> <span data-ttu-id="6f699-111">Ďalšie informácie sa dozviete v článku [Pripojenie prehľadov cieľových skupín k účtu Azure Data Lake Storage Gen2 pomocou objektu služby Azure](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="6f699-111">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span>

- <span data-ttu-id="6f699-112">Azure Data Lake, ku ktorému sa chcete pripojiť a z ktorého prijímať údaje, musí byť v rovnakej oblasti Azure ako prostredie Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="6f699-112">The Azure Data Lake you want to connect and ingest data from have to be in the same Azure region as the Dynamics 365 Customer Insights environment.</span></span> <span data-ttu-id="6f699-113">Pripojenia k priečinku Common Data Model z dátového jazera v inej oblasti Azure nie sú podporované.</span><span class="sxs-lookup"><span data-stu-id="6f699-113">Connections to a Common Data Model folder from a data lake in a different Azure region is not supported.</span></span> <span data-ttu-id="6f699-114">Ak chcete spoznať oblasť Azure v prostredí, prejdite na časť **Správca** > **Systém** > **Informácie** v prehľadoch o cieľových skupinách.</span><span class="sxs-lookup"><span data-stu-id="6f699-114">To know the Azure region of the environment, go to **Admin** > **System** > **About** in audience insights.</span></span>

- <span data-ttu-id="6f699-115">Údaje uložené v online službách sa môžu ukladať na inom mieste ako tam, kde sa údaje spracúvajú alebo ukladajú v rámci služby Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="6f699-115">Data stored in online services, may be stored in a different location than where data is processed or stored in Dynamics 365 Customer Insights.</span></span><span data-ttu-id="6f699-116">Importovaním alebo pripojením sa k údajom uloženým v online službách súhlasíte s tým, že údaje je možné prenášať a ukladať pomocou Dynamics 365 Customer Insights.  [Ďalšie informácie nájdete v Centre dôveryhodnosti spoločnosti Microsoft.](https://www.microsoft.com/trust-center)</span><span class="sxs-lookup"><span data-stu-id="6f699-116"> By importing or connecting to data stored in online services, you agree that data can be transferred to and stored with Dynamics 365 Customer Insights. [Learn more at the Microsoft Trust Center.](https://www.microsoft.com/trust-center)</span></span>

## <a name="connect-to-a-common-data-model-folder"></a><span data-ttu-id="6f699-117">Pripojiť k priečinku Common Data Model</span><span class="sxs-lookup"><span data-stu-id="6f699-117">Connect to a Common Data Model folder</span></span>

1. <span data-ttu-id="6f699-118">V prehľadoch cieľových skupín prejdite na **Údaje** > **Zdroje údajov**.</span><span class="sxs-lookup"><span data-stu-id="6f699-118">In audience insights, go to **Data** > **Data sources**.</span></span>

1. <span data-ttu-id="6f699-119">Vyberte položku **Pridať zdroj údajov**.</span><span class="sxs-lookup"><span data-stu-id="6f699-119">Select **Add data source**.</span></span>

1. <span data-ttu-id="6f699-120">Vyberte položku **Pripojiť k priečinku Common Data Model**, zadajte **Názov** zdroja údajov a vyberte položku **Ďalej**.</span><span class="sxs-lookup"><span data-stu-id="6f699-120">Select **Connect to a Common Data Model folder**, enter a **Name** for the data source, and select **Next**.</span></span> <span data-ttu-id="6f699-121">Pokyny týkajúce sa pomenovania:</span><span class="sxs-lookup"><span data-stu-id="6f699-121">Name guidelines:</span></span> 
   - <span data-ttu-id="6f699-122">Začnite písmenom.</span><span class="sxs-lookup"><span data-stu-id="6f699-122">Start with a letter.</span></span>
   - <span data-ttu-id="6f699-123">Používajte iba písmená a číslice.</span><span class="sxs-lookup"><span data-stu-id="6f699-123">Use letters and numbers only.</span></span> <span data-ttu-id="6f699-124">Nie je povolené zadávanie špeciálnych znakov a medzier.</span><span class="sxs-lookup"><span data-stu-id="6f699-124">Special characters and spaces are not allowed.</span></span>
   - <span data-ttu-id="6f699-125">Použite 3 až 64 znakov.</span><span class="sxs-lookup"><span data-stu-id="6f699-125">Use between 3 and 64 characters.</span></span>

1. <span data-ttu-id="6f699-126">Na overenie si môžete vybrať medzi použitím možnosti založenej na zdrojoch a možnosti založenej na predplatnom.</span><span class="sxs-lookup"><span data-stu-id="6f699-126">You can choose between using a resource-based option and a subscription-based option for authentication.</span></span> <span data-ttu-id="6f699-127">Ďalšie informácie sa dozviete v článku [Pripojenie prehľadov cieľových skupín k účtu Azure Data Lake Storage Gen2 pomocou objektu služby Azure](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="6f699-127">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="6f699-128">Zadajte informáciu **Kontajner** a vyberte položku **Ďalej**.</span><span class="sxs-lookup"><span data-stu-id="6f699-128">Enter the **Container** information and select **Next**.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="6f699-129">![Dialógové okno na zadanie nových podrobností pripojenia pre Azure Data Lake](media/enter-new-storage-details.png)
   > </span><span class="sxs-lookup"><span data-stu-id="6f699-129">![Dialog box to enter new connection details for Azure Data Lake](media/enter-new-storage-details.png)
   > </span></span>[!NOTE]
<span data-ttu-id="6f699-130">Aby ste sa mohli pripojiť a vytvoriť zdroj údajov, potrebujete jednu z nasledujúcich rol buď pre kontajner alebo vyššie uvedený účet úložiska:</span><span class="sxs-lookup"><span data-stu-id="6f699-130">You need one of the following roles either to the container or the storage account referred above to be able to connect to and create a data source:</span></span>
   >  - <span data-ttu-id="6f699-131">Čítačka údajov objektu Blob</span><span class="sxs-lookup"><span data-stu-id="6f699-131">Storage Blob Data Reader</span></span>
   >  - <span data-ttu-id="6f699-132">Majiteľ údajov objektu Blob</span><span class="sxs-lookup"><span data-stu-id="6f699-132">Storage Blob Data Owner</span></span>
   >  - <span data-ttu-id="6f699-133">Prispievateľ údajov do objektu BLOB úložiska</span><span class="sxs-lookup"><span data-stu-id="6f699-133">Storage Blob Data Contributor</span></span>

1. <span data-ttu-id="6f699-134">V dialógovom okne **Vybrať priečinok Common Data Model** vyberte súbor model.json alebo manifest.json, z ktorého chcete importovať údaje, a vyberte položku **Ďalej**.</span><span class="sxs-lookup"><span data-stu-id="6f699-134">In the **Select a Common Data Model folder** dialog, select the model.json or manifest.json file to import data from, and select **Next**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="6f699-135">Žiadny súbor model.json ani manifest.json spojený s iným zdrojom údajov v prostredí sa v zozname nezobrazí.</span><span class="sxs-lookup"><span data-stu-id="6f699-135">Any model.json or manifest.json file associated with another data source in the environment won't show in the list.</span></span>

1. <span data-ttu-id="6f699-136">Vo vybranom súbore model.json alebo manifest.json získate zoznam dostupných entít.</span><span class="sxs-lookup"><span data-stu-id="6f699-136">You'll get a list of available entities in the selected model.json or manifest.json file.</span></span> <span data-ttu-id="6f699-137">Môžete skontrolovať a vybrať zo zoznamu dostupných entít a vybrať položku **Uložiť**.</span><span class="sxs-lookup"><span data-stu-id="6f699-137">You can review and select from the list of available entities and select **Save**.</span></span> <span data-ttu-id="6f699-138">Všetky vybraté entity sa prijmú z nového zdroja údajov.</span><span class="sxs-lookup"><span data-stu-id="6f699-138">All of the selected entities will be ingested from the new data source.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="6f699-139">![Dialógové okno so zoznamom entít zo súboru model.json](media/review-entities.png)</span><span class="sxs-lookup"><span data-stu-id="6f699-139">![Dialog box showing a list of entities from a model.json file](media/review-entities.png)</span></span>

8. <span data-ttu-id="6f699-140">Uveďte, pre ktoré údajové entity chcete povoliť profilovanie údajov, a vyberte položku **Uložiť**.</span><span class="sxs-lookup"><span data-stu-id="6f699-140">Indicate which data entities you want to enable data profiling and select **Save**.</span></span> <span data-ttu-id="6f699-141">Profilovanie údajov umožňuje analýzy a ďalšie funkcie.</span><span class="sxs-lookup"><span data-stu-id="6f699-141">Data profiling enables analytics and other capabilities.</span></span> <span data-ttu-id="6f699-142">Môžete vybrať celú entitu, ktorá vyberie všetky atribúty z entity, alebo môžete vybrať určité atribúty podľa vlastného výberu.</span><span class="sxs-lookup"><span data-stu-id="6f699-142">You can select the whole entity, which selects all attributes from the entity, or select certain attributes of your choice.</span></span> <span data-ttu-id="6f699-143">V predvolenom nastavení nie je pre profilovanie údajov povolená žiadna entita.</span><span class="sxs-lookup"><span data-stu-id="6f699-143">By default, no entity is enabled for data profiling.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="6f699-144">![Dialógové okno zobrazujúce profilovanie údajov](media/dataprofiling-entities.png)</span><span class="sxs-lookup"><span data-stu-id="6f699-144">![Dialog box showing a data profiling](media/dataprofiling-entities.png)</span></span>

9. <span data-ttu-id="6f699-145">Po uložení vašich výberov sa otvorí stránka **Zdroje údajov**.</span><span class="sxs-lookup"><span data-stu-id="6f699-145">After saving your selections, the **Data sources** page opens.</span></span> <span data-ttu-id="6f699-146">Teraz by ste mali vidieť pripojenie priečinka Common Data Model ako zdroja údajov.</span><span class="sxs-lookup"><span data-stu-id="6f699-146">You should now see the Common Data Model folder connection as a data source.</span></span>

> [!NOTE]
> <span data-ttu-id="6f699-147">Súbor model.json alebo manifest.json sa môže v rovnakom prostredí spojiť iba s jedným zdrojom údajov.</span><span class="sxs-lookup"><span data-stu-id="6f699-147">A model.json file or manifest.json can only associate with one data source in the same environment.</span></span> <span data-ttu-id="6f699-148">Rovnaký súbor model.json alebo manifest.json je však možné použiť pre zdroje údajov vo viacerých prostrediach.</span><span class="sxs-lookup"><span data-stu-id="6f699-148">However, the same model.json or manifest.json file can be used for data sources in multiple environments.</span></span>

## <a name="edit-a-common-data-model-folder-data-source"></a><span data-ttu-id="6f699-149">Úprava zdroja údajov pre Common Data Model</span><span class="sxs-lookup"><span data-stu-id="6f699-149">Edit a Common Data Model folder data source</span></span>

<span data-ttu-id="6f699-150">Môžete aktualizovať prístupový kľúč pre účet úložiska, ktoré obsahuje priečinok Common Data Model.</span><span class="sxs-lookup"><span data-stu-id="6f699-150">You can update the access key for the storage account containing the Common Data Model folder.</span></span> <span data-ttu-id="6f699-151">Môžete tiež zmeniť súbor model.json alebo manifest.json.</span><span class="sxs-lookup"><span data-stu-id="6f699-151">You may also change the model.json or manifest.json file.</span></span> <span data-ttu-id="6f699-152">Ak sa chcete pripojiť k inému kontajneru z účtu úložiska alebo zmeniť názov účtu, musíte [vytvoriť nové pripojenie k zdroju údajov](#connect-to-a-common-data-model-folder).</span><span class="sxs-lookup"><span data-stu-id="6f699-152">To connect to a different container from your storage account, or change the account name, [create a new data source connection](#connect-to-a-common-data-model-folder).</span></span>

1. <span data-ttu-id="6f699-153">V prehľadoch cieľových skupín prejdite na **Údaje** > **Zdroje údajov**.</span><span class="sxs-lookup"><span data-stu-id="6f699-153">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="6f699-154">Vedľa zdroja údajov, ktorý chcete aktualizovať, vyberte tri bodky.</span><span class="sxs-lookup"><span data-stu-id="6f699-154">Next to the data source you'd like to update, select the ellipsis.</span></span>

3. <span data-ttu-id="6f699-155">Zo zoznamu vyberte možnosť **Upraviť**.</span><span class="sxs-lookup"><span data-stu-id="6f699-155">Select the **Edit** option from the list.</span></span>

4. <span data-ttu-id="6f699-156">Prípadne aktualizujte **Prístupový kľúč** a vyberte položku **Ďalej**.</span><span class="sxs-lookup"><span data-stu-id="6f699-156">Optionally, update the **Access key** and select **Next**.</span></span>

   ![Dialógové okno na úpravu a aktualizáciu prístupového kľúča k existujúcemu zdroju údajov](media/edit-access-key.png)

5. <span data-ttu-id="6f699-158">Prípadne môžete aktualizáciu vykonať cez pripojenie kľúča účtu na pripojenie založené na zdrojoch alebo predplatnom.</span><span class="sxs-lookup"><span data-stu-id="6f699-158">Optionally, you can update from an account key connection to a resource-based or a subscription-based connection.</span></span> <span data-ttu-id="6f699-159">Ďalšie informácie sa dozviete v článku [Pripojenie prehľadov cieľových skupín k účtu Azure Data Lake Storage Gen2 pomocou objektu služby Azure](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="6f699-159">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="6f699-160">Pri aktualizácii pripojenia nemôžete zmeniť informácie o **kontajneri**.</span><span class="sxs-lookup"><span data-stu-id="6f699-160">You can't change **Container** information when updating the connection.</span></span>
   > [!div class="mx-imgBorder"]

   > ![Dialógové okno na zadanie podrobností pripojenia pre Azure Data Lake k existujúcemu účtu úložiska](media/enter-existing-storage-details.png)

   > [!NOTE]
   > <span data-ttu-id="6f699-162">Aby ste sa mohli pripojiť a vytvoriť zdroj údajov, potrebujete jednu z nasledujúcich rol buď pre kontajner alebo vyššie uvedený účet úložiska:</span><span class="sxs-lookup"><span data-stu-id="6f699-162">You need one of the following roles either to the container or the storage account referred above to be able to connect to and create a data source:</span></span>
   >  - <span data-ttu-id="6f699-163">Čítačka údajov objektu Blob</span><span class="sxs-lookup"><span data-stu-id="6f699-163">Storage Blob Data Reader</span></span>
   >  - <span data-ttu-id="6f699-164">Majiteľ údajov objektu Blob</span><span class="sxs-lookup"><span data-stu-id="6f699-164">Storage Blob Data Owner</span></span>
   >  - <span data-ttu-id="6f699-165">Prispievateľ údajov do objektu Blob úložiska</span><span class="sxs-lookup"><span data-stu-id="6f699-165">Storage Blob Data Contributo</span></span>


6. <span data-ttu-id="6f699-166">Voliteľne môžete z kontajnera zvoliť iný súbor model.json alebo manifest.json s inou množinou entít.</span><span class="sxs-lookup"><span data-stu-id="6f699-166">Optionally, choose a different model.json or manifest.json file with a different set of entities from the container.</span></span>

7. <span data-ttu-id="6f699-167">Prípadne môžete vybrať ďalšie entity na príjem.</span><span class="sxs-lookup"><span data-stu-id="6f699-167">Optionally, you can select additional entities to ingest.</span></span> <span data-ttu-id="6f699-168">Ak už neexistujú žiadne závislosti, môžete odstrániť aj všetky už vybrané entity.</span><span class="sxs-lookup"><span data-stu-id="6f699-168">You can also remove any already selected entities if there are no dependencies.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="6f699-169">Ak existujú závislosti na existujúcom súbore model.json alebo manifest.json a množine entít, zobrazí sa chybové hlásenie a nemôžete vybrať iný súbor model.json alebo manifest.json.</span><span class="sxs-lookup"><span data-stu-id="6f699-169">If there are dependencies on the existing model.json or manifest.json file and the set of entities, you'll see an error message and can't select a different model.json or manifest.json file.</span></span> <span data-ttu-id="6f699-170">Pred zmenou súboru model.json alebo manifest.json tieto závislosti odstráňte alebo vytvorte nový zdroj údajov so súborom model.json alebo manifest.json, ktorý chcete použiť, aby ste sa vyhli odstráneniu závislostí.</span><span class="sxs-lookup"><span data-stu-id="6f699-170">Remove those dependencies before changing the model.json or manifest.json file or create a new data source with the model.json or manifest.json file that you want to use to avoid removing the dependencies.</span></span>

8. <span data-ttu-id="6f699-171">Prípadne môžete vybrať ďalšie atribúty alebo entity, ktoré povolia profilovanie údajov alebo zakážu tie už vybrané.</span><span class="sxs-lookup"><span data-stu-id="6f699-171">Optionally, you can select additional attributes or entities to enable data profiling on or disable already selected ones.</span></span>   


[!INCLUDE[footer-include](../includes/footer-banner.md)]