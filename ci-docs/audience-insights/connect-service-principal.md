---
title: Pripojenie k účtu Azure Data Lake Storage Gen2 pomocou objektu služby
description: Použite objekt služby Azure pre prehľady cieľových skupín na pripojenie vlastného Data Lake, keď ho pripájate k prehľadom cieľových skupín.
ms.date: 02/10/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: c670b0065a2833a6dc311d9e86d2b351140382ce
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596518"
---
# <a name="connect-to-an-azure-data-lake-storage-gen2-account-with-an-azure-service-principal-for-audience-insights"></a><span data-ttu-id="91770-103">Pripojenie k účtu Azure Data Lake Storage Gen2 pomocou objektu služby Azure pre prehľady cieľových skupín</span><span class="sxs-lookup"><span data-stu-id="91770-103">Connect to an Azure Data Lake Storage Gen2 account with an Azure service principal for audience insights</span></span>

<span data-ttu-id="91770-104">Automatizované nástroje, ktoré využívajú služby Azure, by mali mať vždy obmedzené povolenia.</span><span class="sxs-lookup"><span data-stu-id="91770-104">Automated tools that use Azure services should always have restricted permissions.</span></span> <span data-ttu-id="91770-105">Namiesto prihlasovania aplikácií ako plne privilegovaného používateľa ponúka Azure objekty služieb.</span><span class="sxs-lookup"><span data-stu-id="91770-105">Instead of having applications sign in as a fully privileged user, Azure offers service principals.</span></span> <span data-ttu-id="91770-106">Čítajte ďalej a dozviete sa, ako prepojiť prehľady cieľových skupín s účtom Azure Data Lake Storage Gen2, ktorý používa objekt služby Azure namiesto kľúčov účtu ukladacieho priestoru.</span><span class="sxs-lookup"><span data-stu-id="91770-106">Read on to learn how to connect audience insights with an Azure Data Lake Storage Gen2 account using an Azure service principal instead of storage account keys.</span></span> 

<span data-ttu-id="91770-107">Objekt služby môžete použiť na bezpečné [pridanie alebo úpravu priečinka Common Data Model ako zdroj údajov](connect-common-data-model.md) alebo [vytvorenie nového či aktualizáciu existujúceho prostredia](manage-environments.md#create-an-environment-in-an-existing-organization).</span><span class="sxs-lookup"><span data-stu-id="91770-107">You can use the service principal to securely [add or edit a Common Data Model folder as a data source](connect-common-data-model.md) or [create a new or update an existing environment](manage-environments.md#create-an-environment-in-an-existing-organization).</span></span>

> [!IMPORTANT]
> - <span data-ttu-id="91770-108">Účet úložiska Azure Data Lake Gen2, ktorý chce používať objekt služby, musí mať [povolený Hierarchický menný priestor (HNS)](/azure/storage/blobs/data-lake-storage-namespace).</span><span class="sxs-lookup"><span data-stu-id="91770-108">The Azure Data Lake Gen2 storage account that intends to use the service principal must have [Hierarchical Name Space (HNS) enabled](/azure/storage/blobs/data-lake-storage-namespace).</span></span>
> - <span data-ttu-id="91770-109">Na vytvorenie objektu služby potrebujete povolenia správcu predplatného Azure.</span><span class="sxs-lookup"><span data-stu-id="91770-109">You need admin permissions for your Azure subscription to create the service principal.</span></span>

## <a name="create-azure-service-principal-for-audience-insights"></a><span data-ttu-id="91770-110">Vytvorte objekt služby Azure pre prehľady cieľových skupín</span><span class="sxs-lookup"><span data-stu-id="91770-110">Create Azure service principal for audience insights</span></span>

<span data-ttu-id="91770-111">Pred vytvorením nového objektu služby pre prehľady cieľových skupín skontrolujte, či už vo vašej organizácii existuje.</span><span class="sxs-lookup"><span data-stu-id="91770-111">Before creating a new service principal for audience insights, check if it already exists in your organization.</span></span>

### <a name="look-for-an-existing-service-principal"></a><span data-ttu-id="91770-112">Vyhľadajte existujúci objekt služby</span><span class="sxs-lookup"><span data-stu-id="91770-112">Look for an existing service principal</span></span>

1. <span data-ttu-id="91770-113">Prejdite do [portálu spravovania služby Azure](https://portal.azure.com) a prihláste sa do svojej organizácie.</span><span class="sxs-lookup"><span data-stu-id="91770-113">Go to the [Azure admin portal](https://portal.azure.com) and sign in to your organization.</span></span>

2. <span data-ttu-id="91770-114">Vyberte položku **Azure Active Directory** zo služieb Azure.</span><span class="sxs-lookup"><span data-stu-id="91770-114">Select **Azure Active Directory** from the Azure services.</span></span>

3. <span data-ttu-id="91770-115">V časti **Spravovať** vyberte **Podnikové aplikácie**.</span><span class="sxs-lookup"><span data-stu-id="91770-115">Under **Manage**, select **Enterprise Applications**.</span></span>

4. <span data-ttu-id="91770-116">Vyhľadajte ID aplikácie prvej strany s prehľadmi cieľových skupín `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` alebo názov `Dynamics 365 AI for Customer Insights`.</span><span class="sxs-lookup"><span data-stu-id="91770-116">Search for the audience insights first party application ID `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` or the name `Dynamics 365 AI for Customer Insights`.</span></span>

5. <span data-ttu-id="91770-117">Ak nájdete zodpovedajúci záznam, znamená to, že objekt služby pre prehľady cieľových skupín existuje.</span><span class="sxs-lookup"><span data-stu-id="91770-117">If you find a matching record, it means that the service principal for audience insights exists.</span></span> <span data-ttu-id="91770-118">Nemusíte nič znova vytvárať.</span><span class="sxs-lookup"><span data-stu-id="91770-118">You don't need to create it again.</span></span>
   
   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="Snímka obrazovky, ktorá ukazuje existujúci objekt služby.":::
   
6. <span data-ttu-id="91770-120">Ak sa nevrátia žiadne výsledky, vytvorte nový objekt služby.</span><span class="sxs-lookup"><span data-stu-id="91770-120">If no results are returned, create a new service principal.</span></span>

### <a name="create-a-new-service-principal"></a><span data-ttu-id="91770-121">Vytvorte nový objekt služby</span><span class="sxs-lookup"><span data-stu-id="91770-121">Create a new service principal</span></span>

1. <span data-ttu-id="91770-122">Nainštalujte si najnovšiu verziu **Azure Active Directory PowerShell pre Graph**.</span><span class="sxs-lookup"><span data-stu-id="91770-122">Install the latest version of the **Azure Active Directory PowerShell for Graph**.</span></span> <span data-ttu-id="91770-123">Ďalšie informácie nájdete v sekcii [Inštalovať Azure Active Directory PowerShell pre Graph](/powershell/azure/active-directory/install-adv2).</span><span class="sxs-lookup"><span data-stu-id="91770-123">For more information, see [Install Azure Active Directory PowerShell for Graph](/powershell/azure/active-directory/install-adv2).</span></span>
   - <span data-ttu-id="91770-124">Na počítači vyberte kláves Windows na klávesnici a vyhľadajte výraz **Windows PowerShell** a **Spustiť ako správca**.</span><span class="sxs-lookup"><span data-stu-id="91770-124">On your PC, select the Windows key on your keyboard and search for **Windows PowerShell** and **Run as Administrator**.</span></span>
   
   - <span data-ttu-id="91770-125">Do okna PowerShell, ktoré sa otvorí, zadajte výraz `Install-Module AzureAD`.</span><span class="sxs-lookup"><span data-stu-id="91770-125">In the PowerShell window that opens, enter `Install-Module AzureAD`.</span></span>

2. <span data-ttu-id="91770-126">Vytvorte objekt služby pre prehľady cieľových skupín pomocou modulu Azure AD PowerShell.</span><span class="sxs-lookup"><span data-stu-id="91770-126">Create the  service principal for audience insights with the Azure AD PowerShell Module.</span></span>
   - <span data-ttu-id="91770-127">Do okna PowerShell zadajte výraz `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure`.</span><span class="sxs-lookup"><span data-stu-id="91770-127">In the PowerShell window, enter `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure`.</span></span> <span data-ttu-id="91770-128">Nahraďte „ID vášho nájomníka“ skutočným ID vášho nájomníka, v ktorom chcete vytvoriť objekt služby.</span><span class="sxs-lookup"><span data-stu-id="91770-128">Replace “your tenant ID” with the actual ID of your tenant where you want to create the service principal.</span></span> <span data-ttu-id="91770-129">Parameter názvu prostredia `AzureEnvironmentName` je voliteľný.</span><span class="sxs-lookup"><span data-stu-id="91770-129">The environment name parameter `AzureEnvironmentName` is optional.</span></span>
  
   - <span data-ttu-id="91770-130">Zadajte `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`.</span><span class="sxs-lookup"><span data-stu-id="91770-130">Enter `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`.</span></span> <span data-ttu-id="91770-131">Tento príkaz vytvorí objekt služby pre prehľady cieľových skupín vo vybranom nájomníkovi.</span><span class="sxs-lookup"><span data-stu-id="91770-131">This command creates the service principal for audience insights on the selected tenant.</span></span>  

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a><span data-ttu-id="91770-132">Udeľte povolenia pre objekt služby na prístup k účtu úložiska</span><span class="sxs-lookup"><span data-stu-id="91770-132">Grant permissions to the service principal to access the storage account</span></span>

<span data-ttu-id="91770-133">Prejdite na portál Azure a udeľte objektu služby povolenia pre účet úložiska, ktorý chcete použiť v prehľadoch cieľových skupín.</span><span class="sxs-lookup"><span data-stu-id="91770-133">Go to the Azure portal to grant permissions to the service principal for the storage account you want to use in audience insights.</span></span>

1. <span data-ttu-id="91770-134">Prejdite do [portálu spravovania služby Azure](https://portal.azure.com) a prihláste sa do svojej organizácie.</span><span class="sxs-lookup"><span data-stu-id="91770-134">Go to the [Azure admin portal](https://portal.azure.com) and sign in to your organization.</span></span>

1. <span data-ttu-id="91770-135">Otvorte účet úložiska, ku ktorému má mať prístup objekt služby pre prehľady cieľových skupín.</span><span class="sxs-lookup"><span data-stu-id="91770-135">Open the storage account you want the service principal for audience insights to have access to.</span></span>

1. <span data-ttu-id="91770-136">Vyberte položku **Riadenie prístupu (IAM)** na navigačnej table a vyberte položku **Pridať** > **Pridajte priradenie roly**.</span><span class="sxs-lookup"><span data-stu-id="91770-136">Select **Access control (IAM)** from the navigation pane and select **Add** > **Add role assignment**.</span></span>
   
   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text="Snímka obrazovky, ktorá ukazuje portál Azure pri pridávaní priradenia roly.":::
   
1. <span data-ttu-id="91770-138">Na table **Pridať priradenie roly** nastavte nasledujúce vlastnosti:</span><span class="sxs-lookup"><span data-stu-id="91770-138">In the **Add role assignment** pane, set the following properties:</span></span>
   - <span data-ttu-id="91770-139">Rola: *Prispievateľ údajov do objektu BLOB úložiska*</span><span class="sxs-lookup"><span data-stu-id="91770-139">Role: *Storage Blob Data Contributor*</span></span>
   - <span data-ttu-id="91770-140">Priradiť prístup k: *Používateľovi, skupine alebo objektu služby*</span><span class="sxs-lookup"><span data-stu-id="91770-140">Assign access to: *User, group, or service principal*</span></span>
   - <span data-ttu-id="91770-141">Vyberte: *Dynamics 365 AI for Customer Insights* ([objekt služby, ktorý ste vytvorili](#create-a-new-service-principal))</span><span class="sxs-lookup"><span data-stu-id="91770-141">Select: *Dynamics 365 AI for Customer Insights* (the [service principal you created](#create-a-new-service-principal))</span></span>

1.  <span data-ttu-id="91770-142">Vyberte položku **Uložiť**.</span><span class="sxs-lookup"><span data-stu-id="91770-142">Select **Save**.</span></span>

<span data-ttu-id="91770-143">Vyplnenie zmien môže byť dokončené až o 15 minút.</span><span class="sxs-lookup"><span data-stu-id="91770-143">It can take up to 15 minutes to propagate the changes.</span></span>

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-audience-insights"></a><span data-ttu-id="91770-144">Zadajte ID zdroja Azure alebo podrobnosti o predplatnom služby Azure v prílohe účtu úložiska k Audience Insights.</span><span class="sxs-lookup"><span data-stu-id="91770-144">Enter the Azure Resource ID or the Azure Subscription details in the storage account attachment to Audience Insights.</span></span>

<span data-ttu-id="91770-145">Pripojte účet úložiska Azure Data Lake v prehľadoch cieľových skupín na [ukladanie výstupných údajov](manage-environments.md) alebo [jeho použitie ako zdroja údajov](connect-common-data-service-lake.md).</span><span class="sxs-lookup"><span data-stu-id="91770-145">Attach an Azure Data Lake storage account in audience insights to [store output data](manage-environments.md) or [use it as a data source](connect-common-data-service-lake.md).</span></span> <span data-ttu-id="91770-146">Výber možnosti Azure Data Lake vám umožní vybrať si medzi prístupom založeným na zdrojoch alebo na predplatnom.</span><span class="sxs-lookup"><span data-stu-id="91770-146">Choosing the Azure Data Lake option lets you choose between a resource-based or a subscription-based based approach.</span></span>

<span data-ttu-id="91770-147">Podľa nasledujúcich pokynov uveďte požadované informácie o vybranom prístupe.</span><span class="sxs-lookup"><span data-stu-id="91770-147">Follow the below steps to provide the required information on the selected approach.</span></span>

### <a name="resource-based-storage-account-connection"></a><span data-ttu-id="91770-148">Pripojenie účtu úložiska na základe zdrojov</span><span class="sxs-lookup"><span data-stu-id="91770-148">Resource-based storage account connection</span></span>

1. <span data-ttu-id="91770-149">Prejdite na [portál spravovania služby Azure](https://portal.azure.com), prihláste sa do predplatného a otvorte účet úložiska.</span><span class="sxs-lookup"><span data-stu-id="91770-149">Go to the [Azure admin portal](https://portal.azure.com), sign in to your subscription and open the storage account.</span></span>

1. <span data-ttu-id="91770-150">Prejdite na časť **Nastavenia** > **Vlastnosti** na navigačnej table.</span><span class="sxs-lookup"><span data-stu-id="91770-150">Go to **Settings** > **Properties** on navigation pane.</span></span>

1. <span data-ttu-id="91770-151">Skopírujte hodnotu ID zdroja účtu úložiska.</span><span class="sxs-lookup"><span data-stu-id="91770-151">Copy the storage account resource ID value.</span></span>

   :::image type="content" source="media/ADLS-SP-ResourceId.png" alt-text="Skopírujte ID zdroja účtu úložiska.":::

1. <span data-ttu-id="91770-153">V prehľadoch cieľových skupín vložte ID zdroja do poľa zdroja zobrazeného na obrazovke pripojenia účtu úložiska.</span><span class="sxs-lookup"><span data-stu-id="91770-153">In audience insights, insert the resource ID in the resource field displayed in the storage account connection screen.</span></span>

   :::image type="content" source="media/ADLS-SP-ResourceIdConnection.png" alt-text="Zadajte informácie o ID zdroja účtu úložiska.":::   
   
1. <span data-ttu-id="91770-155">Pokračujte zvyšnými krokmi v prehľadoch cieľových skupín a pripojte účet úložiska.</span><span class="sxs-lookup"><span data-stu-id="91770-155">Continue with the remaining steps in audience insights to attach the storage account.</span></span>

### <a name="subscription-based-storage-account-connection"></a><span data-ttu-id="91770-156">Pripojenie účtu úložiska na základe predplatného</span><span class="sxs-lookup"><span data-stu-id="91770-156">Subscription-based storage account connection</span></span>

1. <span data-ttu-id="91770-157">Prejdite na [portál spravovania služby Azure](https://portal.azure.com), prihláste sa do predplatného a otvorte účet úložiska.</span><span class="sxs-lookup"><span data-stu-id="91770-157">Go to the [Azure admin portal](https://portal.azure.com), sign in to your subscription and open the storage account.</span></span>

1. <span data-ttu-id="91770-158">Prejdite na časť **Nastavenia** > **Vlastnosti** na navigačnej table.</span><span class="sxs-lookup"><span data-stu-id="91770-158">Go to **Settings** > **Properties** on navigation pane.</span></span>

1. <span data-ttu-id="91770-159">Skontrolujte **Predplatné**, **Skupinu zdrojov** a **Názov** účtu úložiska, aby ste v prehľadoch cieľových skupín vybrali správne hodnoty.</span><span class="sxs-lookup"><span data-stu-id="91770-159">Review the **Subscription**, **Resource group**, and the **Name** of the storage account to make sure you select the right values in audience insights.</span></span>

1. <span data-ttu-id="91770-160">Pri pripájaní účtu úložiska vyberte v prehľadoch cieľových skupín hodnoty alebo príslušné polia.</span><span class="sxs-lookup"><span data-stu-id="91770-160">In audience insights, choose the values or for the corresponding fields when attaching the storage account.</span></span>
   
1. <span data-ttu-id="91770-161">Pokračujte zvyšnými krokmi v prehľadoch cieľových skupín a pripojte účet úložiska.</span><span class="sxs-lookup"><span data-stu-id="91770-161">Continue with the remaining steps in audience insights to attach the storage account.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]