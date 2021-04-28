---
title: Práca s API
description: Používajte rozhrania API a pochopte ich obmedzenia.
ms.date: 03/10/2021
ms.reviewer: wimohabb
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: 59161456914df84d7e72402ed1f5faf70a5119ba
ms.sourcegitcommit: a39e00a50ad3eda820fd756c5611081f0ca04662
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 04/09/2021
ms.locfileid: "5873681"
---
# <a name="work-with-customer-insights-apis"></a><span data-ttu-id="daf59-103">Pracujte s rozhraniami API v službe Customer Insights</span><span class="sxs-lookup"><span data-stu-id="daf59-103">Work with Customer Insights APIs</span></span>

<span data-ttu-id="daf59-104">Dynamics 365 Customer Insights poskytuje rozhrania API na vytváranie vlastných aplikácií na základe vašich údajov v službe Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="daf59-104">Dynamics 365 Customer Insights provides APIs to build your own applications based you data in Customer Insights.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="daf59-105">Podrobnosti o týchto rozhraniach API sú uvedené v [referencii rozhraní API v službe Customer Insights](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights).</span><span class="sxs-lookup"><span data-stu-id="daf59-105">Details of these APIs, are listed on the [Customer Insights APIs reference](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights).</span></span> <span data-ttu-id="daf59-106">Patria sem dodatočné informácie o operáciách, parametroch a reakciách.</span><span class="sxs-lookup"><span data-stu-id="daf59-106">They include additional information about operations, parameters, and responses.</span></span>

<span data-ttu-id="daf59-107">Tento článok vás prevedie prístupom k rozhraniam API v službe Customer Insights, vytvorením registrácie aplikácie na portáli Azure a pomôže vám začať s dostupnými knižnicami klientov.</span><span class="sxs-lookup"><span data-stu-id="daf59-107">This article guides you to access to the Customer Insights APIs, create an Azure App Registration, and help you get started with the available client libraries.</span></span>

## <a name="get-started-trying-the-customer-insights-apis"></a><span data-ttu-id="daf59-108">Začnite skúšať rozhrania API v službe Customer Insights</span><span class="sxs-lookup"><span data-stu-id="daf59-108">Get started trying the Customer Insights APIs</span></span>

1. <span data-ttu-id="daf59-109">[Prihláste sa](https://home.ci.ai.dynamics.com) do služby Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="daf59-109">[Sign in](https://home.ci.ai.dynamics.com) to Customer Insights.</span></span> <span data-ttu-id="daf59-110">Ak ešte nemáte predplatné, [zaregistrujte sa na skúšobnú verziu Customer Insights](https://aka.ms/tryci).</span><span class="sxs-lookup"><span data-stu-id="daf59-110">If you don't have a subscription yet, [sign up for a trial of Customer Insights](https://aka.ms/tryci).</span></span>

1. <span data-ttu-id="daf59-111">Ak chcete povoliť rozhrania API vo svojom prostredí služby Customer Insights, prejdite na **Správca** > **Povolenia**.</span><span class="sxs-lookup"><span data-stu-id="daf59-111">To enable APIs on your Customer Insights environment, go to **Admin** > **Permissions**.</span></span> <span data-ttu-id="daf59-112">Potrebujete na to povolenia správcu.</span><span class="sxs-lookup"><span data-stu-id="daf59-112">You'll need admin permissions to do so.</span></span>

1. <span data-ttu-id="daf59-113">Prejdite na kartu **Rozhrania API** a vyberte tlačidlo **Povoliť**.</span><span class="sxs-lookup"><span data-stu-id="daf59-113">Go to the **APIs** tab and select the **Enable** button.</span></span>    
   <span data-ttu-id="daf59-114">Povolením rozhraní API sa vytvorí primárny a sekundárny kľúč predplatného pre vašu inštanciu, ktorý sa použije pri požiadavkách pre rozhrania API.</span><span class="sxs-lookup"><span data-stu-id="daf59-114">Enabling the APIs creates a primary and secondary subscription key for your instance that gets used in the API requests.</span></span> <span data-ttu-id="daf59-115">Kľúče môžete znova vygenerovať výberom položky **Znova vygenerovať primárny** alebo **Znova vygenerovať sekundárny** v časti **Správca** > **Povolenia** > **Rozhrania API**.</span><span class="sxs-lookup"><span data-stu-id="daf59-115">You can regenerate the keys by selecting the **Regenerate primary** or **Regenerate secondary** on **Admin** > **Permissions** > **APIs**.</span></span>

   :::image type="content" source="media/enable-apis.gif" alt-text="Povoliť rozhrania API v službe Customer Insights":::

1. <span data-ttu-id="daf59-117">Výberom položky **Preskúmajte naše rozhrania API** si môžete [rozhrania API vyskúšať](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances).</span><span class="sxs-lookup"><span data-stu-id="daf59-117">Select **Explore our APIs** to [try out the APIs](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances).</span></span>

1. <span data-ttu-id="daf59-118">Vyberte operáciu pre rozhranie API a vyberte položku **Vyskúšať**.</span><span class="sxs-lookup"><span data-stu-id="daf59-118">Choose an API operation and select **Try it**.</span></span>

1. <span data-ttu-id="daf59-119">Na bočnej table nastavte hodnotu v rozbaľovacej ponuke **Oprávnenie** na **implicitné**.</span><span class="sxs-lookup"><span data-stu-id="daf59-119">In the side pane, set the value in the **Authorization** drop-down menu to **implicit**.</span></span> <span data-ttu-id="daf59-120">Hlavička `Authorization` sa získa s pridaným nosným tokenom.</span><span class="sxs-lookup"><span data-stu-id="daf59-120">The `Authorization` header gets with a bearer token added.</span></span> <span data-ttu-id="daf59-121">Váš kľúč predplatného sa vyplní automaticky.</span><span class="sxs-lookup"><span data-stu-id="daf59-121">Your subscription key will be automatically populated.</span></span>
  
1. <span data-ttu-id="daf59-122">Prípadne môžete pridať všetky potrebné parametre dotazu.</span><span class="sxs-lookup"><span data-stu-id="daf59-122">Optionally, add all necessary query parameters.</span></span>

1. <span data-ttu-id="daf59-123">Prejdite do dolnej časti bočnej tably a vyberte ikonu **Poslať**.</span><span class="sxs-lookup"><span data-stu-id="daf59-123">Scroll to the bottom of the side pane and select **Send**.</span></span>

<span data-ttu-id="daf59-124">Odpoveď protokolu HTTP sa čoskoro objaví nižšie.</span><span class="sxs-lookup"><span data-stu-id="daf59-124">The HTTP response will soon appear below.</span></span>


   :::image type="content" source="media/try-apis.gif" alt-text="Animovaný gif ukazujúci, ako zvoliť testovanie rozhraní API.":::

## <a name="create-a-new-app-registration-in-the-azure-portal"></a><span data-ttu-id="daf59-126">Vytvorte novú registráciu aplikácie na portáli Azure</span><span class="sxs-lookup"><span data-stu-id="daf59-126">Create a new app registration in the Azure portal</span></span>

<span data-ttu-id="daf59-127">Tieto kroky vám pomôžu začať používať rozhrania API v službe Customer Insights v aplikácii Azure pomocou delegovaných povolení.</span><span class="sxs-lookup"><span data-stu-id="daf59-127">These steps help you get started in using the Customer Insights APIs in an Azure application using delegated permissions.</span></span> <span data-ttu-id="daf59-128">Najskôr sa uistite, že ste dokončili [sekciu Začíname](#get-started-trying-the-customer-insights-apis).</span><span class="sxs-lookup"><span data-stu-id="daf59-128">Make sure to have completed [Getting started section](#get-started-trying-the-customer-insights-apis) first.</span></span>

1. <span data-ttu-id="daf59-129">Prihláste sa do [portálu Azure](https://portal.azure.com) pomocou účtu, ktorý má prístup k údajom služby Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="daf59-129">Sign in to the [Azure portal](https://portal.azure.com) with the account that can access the Customer Insights data.</span></span>

1. <span data-ttu-id="daf59-130">Vľavo vyberte položku **Registrácie aplikácií**.</span><span class="sxs-lookup"><span data-stu-id="daf59-130">On the left, select **App registrations**.</span></span>

1. <span data-ttu-id="daf59-131">Vyberte položku **Nová registrácia**, zadajte názov aplikácie a vyberte typ účtu.</span><span class="sxs-lookup"><span data-stu-id="daf59-131">Select **New registration** provide an application name and choose the account type.</span></span>
   <span data-ttu-id="daf59-132">Prípadne pridajte adresu URL presmerovania.</span><span class="sxs-lookup"><span data-stu-id="daf59-132">Optionally, add a redirect URL.</span></span> <span data-ttu-id="daf59-133">http://localhost postačí na vývoj aplikácie na vašom lokálnom počítači.</span><span class="sxs-lookup"><span data-stu-id="daf59-133">http://localhost is sufficient for developing an application on your local computer.</span></span>

1. <span data-ttu-id="daf59-134">Pri novej registrácii aplikácie prejdite na **Povolenia pre API**.</span><span class="sxs-lookup"><span data-stu-id="daf59-134">On your new App registration, go to **API permissions**.</span></span>

   :::image type="content" source="media/app-registration-1.gif" alt-text="Animovaný gif na nastavenie povolenia API v registrácii aplikácie.":::

1. <span data-ttu-id="daf59-136">Vyberte položku **Pridať povolenie** a vyberte položku **Customer Insights** na bočnej table.</span><span class="sxs-lookup"><span data-stu-id="daf59-136">Select **Add a permission** and select **Customer Insights** in the side pane.</span></span>

1. <span data-ttu-id="daf59-137">Ako **Typ povolenia** vyberte **Delegované povolenia** a vyberte povolenie **user_impersonation**.</span><span class="sxs-lookup"><span data-stu-id="daf59-137">For **Permission type**, select **Delegated permissions** and select the **user_impersonation** permission.</span></span>

1. <span data-ttu-id="daf59-138">Vyberte položku **Pridať povolenia**.</span><span class="sxs-lookup"><span data-stu-id="daf59-138">Select **Add permissions**.</span></span> <span data-ttu-id="daf59-139">Ak potrebujete získať prístup k rozhraniu API bez prihlásenia používateľa, skontrolujte [Povolenia aplikácií typu server-to-server](#server-to-server-application-permissions).</span><span class="sxs-lookup"><span data-stu-id="daf59-139">If you need to access the API without a user signing in, review the [Server-to-server application permissions](#server-to-server-application-permissions) section.</span></span>

1. <span data-ttu-id="daf59-140">Vyberte položku **Udeliť súhlas správcu pre...** na dokončenie registrácie aplikácie.</span><span class="sxs-lookup"><span data-stu-id="daf59-140">Select **Grant admin consent for...** to complete the app registration.</span></span>

<span data-ttu-id="daf59-141">ID aplikácie/klienta môžete použiť na registráciu tejto aplikácie v knižnici Microsoft Authentication Library (MSAL), aby ste získali nosný token, ktorý sa odošle s vašou požiadavkou pre API.</span><span class="sxs-lookup"><span data-stu-id="daf59-141">You can use the Application/Client ID for this app registration with the Microsoft Authentication Library (MSAL) to obtain a bearer token to send with your request to the API.</span></span>

:::image type="content" source="media/grant-admin-consent.gif" alt-text="Animovaný gif na udelenie súhlasu správcu.":::

<span data-ttu-id="daf59-143">Ďalšie informácie o MSAL nájdete v sekcii [Prehľad knižnice Microsoft Authentication Library (MSAL)](/azure/active-directory/develop/msal-overview).</span><span class="sxs-lookup"><span data-stu-id="daf59-143">For more information about MSAL, see [Overview of Microsoft Authentication Library (MSAL)](/azure/active-directory/develop/msal-overview).</span></span>

<span data-ttu-id="daf59-144">Ďalšie informácie o registrácii aplikácií v Azure nájdete v [novom prostredí na registráciu aplikácií na portáli Azure](/azure/active-directory/develop/app-registration-portal-training-guide).</span><span class="sxs-lookup"><span data-stu-id="daf59-144">For more information about app registration in Azure, see [The new Azure portal app registration experience](/azure/active-directory/develop/app-registration-portal-training-guide).</span></span>

<span data-ttu-id="daf59-145">Informácie o používaní rozhraní API našich knižníc klientov nájdete v sekcii [Knižnice klientov v službe Customer Insights](#customer-insights-client-libraries).</span><span class="sxs-lookup"><span data-stu-id="daf59-145">For information on using the APIs our client libraries, see [Customer Insights client libraries](#customer-insights-client-libraries).</span></span>

### <a name="server-to-server-application-permissions"></a><span data-ttu-id="daf59-146">Povolenia pre aplikácie typu server-to-server</span><span class="sxs-lookup"><span data-stu-id="daf59-146">Server-to-server application permissions</span></span>

<span data-ttu-id="daf59-147">[Sekcia registrácie aplikácií](#create-a-new-app-registration-in-the-azure-portal) opisuje, ako si zaregistrovať aplikáciu, ktorá vyžaduje od používateľa prihlásenie na účely overenia.</span><span class="sxs-lookup"><span data-stu-id="daf59-147">The [app registration section](#create-a-new-app-registration-in-the-azure-portal) outlines how to register an app that requires a user to sign in for authentication.</span></span> <span data-ttu-id="daf59-148">Ďalšie informácie o tom, ako vytvoriť registráciu aplikácie, ktorá nevyžaduje interakciu používateľa a možno ju spustiť na serveri.</span><span class="sxs-lookup"><span data-stu-id="daf59-148">Learn how to create an app registration that does not need user interaction and can be run on a server.</span></span>

1. <span data-ttu-id="daf59-149">Pri registrácii aplikácie na portáli Azure prejdite na **Povolenia pre API**.</span><span class="sxs-lookup"><span data-stu-id="daf59-149">On your App registration in the Azure portal, go to **API permissions**.</span></span>

1. <span data-ttu-id="daf59-150">Vyberte položku **Pridať povolenie** a vyberte položku **Customer Insights** na bočnej table.</span><span class="sxs-lookup"><span data-stu-id="daf59-150">Select **Add a permission** and select **Customer Insights** in the side pane.</span></span>

1. <span data-ttu-id="daf59-151">Ako **Typ povolenia** vyberte **Povolenia pre aplikáciu** a vyberte povolenie **CustomerInsights.Api.All**.</span><span class="sxs-lookup"><span data-stu-id="daf59-151">For **Permission type**, select **Application permissions** and select the **CustomerInsights.Api.All** permission.</span></span>

1. <span data-ttu-id="daf59-152">Vyberte položku **Pridať povolenia**.</span><span class="sxs-lookup"><span data-stu-id="daf59-152">Select **Add permissions**.</span></span>

1. <span data-ttu-id="daf59-153">Ak chcete udeliť súhlas správcu s týmto povolením pre aplikáciu, musíte pridať objekt služby.</span><span class="sxs-lookup"><span data-stu-id="daf59-153">To give admin consent on this Application permission, you need to add a Service Principal.</span></span>

   1. <span data-ttu-id="daf59-154">Nainštalujte modul Azure Active Directory (AD) PowerShell: `Install-Module -Name AzureAD -AllowClobber -Scope AllUsers`</span><span class="sxs-lookup"><span data-stu-id="daf59-154">Install the Azure Active Directory (AD) PowerShell module: `Install-Module -Name AzureAD -AllowClobber -Scope AllUsers`</span></span>
   1. <span data-ttu-id="daf59-155">Pripojte sa k svojmu účtu AD: `Connect-AzureAD -TenantId <your tenant id>`.</span><span class="sxs-lookup"><span data-stu-id="daf59-155">Connect to your AD account: `Connect-AzureAD -TenantId <your tenant id>`.</span></span> <span data-ttu-id="daf59-156">ID nájomníka nájdete v sekcii **Prehľad** > **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="daf59-156">You can find your tenant ID on **Overview** > **Azure Active Directory**.</span></span>
   1. <span data-ttu-id="daf59-157">Spustením nasledujúceho príkazu pridáte objekt služby Azure AD: `New-AzureADServicePrincipal -AppId "38c77d00-5fcb-4cce-9d93-af4738258e3c" -DisplayName "Microsoft Dynamics 365 Customer Insights"` Parameter AppId sa týka aplikácie rozhrania API v službe Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="daf59-157">Run the following command to add an Azure AD Service Principal: `New-AzureADServicePrincipal -AppId "38c77d00-5fcb-4cce-9d93-af4738258e3c" -DisplayName "Microsoft Dynamics 365 Customer Insights"` The AppId parameter pertains to the Customer Insights API app.</span></span>

   :::image type="content" source="media/azureAD-service-principal.png" alt-text="Ukážka objektu služby":::

1. <span data-ttu-id="daf59-159">Pri registrácii aplikácie sa vráťte na **Povolenia pre API**.</span><span class="sxs-lookup"><span data-stu-id="daf59-159">Go back to **API permissions** for your app registration.</span></span>

1. <span data-ttu-id="daf59-160">Vyberte položku **Udeliť súhlas správcu pre...** na dokončenie registrácie aplikácie.</span><span class="sxs-lookup"><span data-stu-id="daf59-160">Select **Grant admin consent for...** to complete the app registration.</span></span>

   :::image type="content" source="media/grant-admin-consent.gif" alt-text="Animovaný gif na udelenie súhlasu správcu.":::

1. <span data-ttu-id="daf59-162">Na záver musíme do služby Customer Insights pridať názov registrácie aplikácie ako používateľa.</span><span class="sxs-lookup"><span data-stu-id="daf59-162">To conclude, we have to add the name of the app registration as a user in Customer Insights.</span></span>    
   <span data-ttu-id="daf59-163">Otvorte službu Customer Insights, prejdite na položku **Správca** > **Povolenia** a vyberte položku **Pridať používateľa**.</span><span class="sxs-lookup"><span data-stu-id="daf59-163">Open Customer Insights, go to **Admin** > **Permissions** and select **Add user**.</span></span>

1. <span data-ttu-id="daf59-164">Vyhľadajte názov registrácie aplikácie, vyberte ho z výsledkov vyhľadávania a vyberte položku **Uložiť**.</span><span class="sxs-lookup"><span data-stu-id="daf59-164">Search for the name of your app registration, select it from the search results, and select **Save**.</span></span>

## <a name="customer-insights-client-libraries"></a><span data-ttu-id="daf59-165">Knižnice klientov v službe Customer Insights</span><span class="sxs-lookup"><span data-stu-id="daf59-165">Customer Insights client libraries</span></span>

<span data-ttu-id="daf59-166">Táto sekcia vám pomôže začať používať knižnice klientov dostupné pre rozhrania API v službe Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="daf59-166">This section helps you get started using the client libraries available for the Customer Insights APIs.</span></span> <span data-ttu-id="daf59-167">Všetky zdrojové kódy knižníc a vzorové aplikácie nájdete na [stránke Customer Insights GitHub](https://github.com/microsoft/Dynamics365-CustomerInsights-Client-Libraries).</span><span class="sxs-lookup"><span data-stu-id="daf59-167">All library source code and sample applications can be found on the [Customer Insights GitHub page](https://github.com/microsoft/Dynamics365-CustomerInsights-Client-Libraries).</span></span> 

### <a name="c-nuget"></a><span data-ttu-id="daf59-168">C# NuGet</span><span class="sxs-lookup"><span data-stu-id="daf59-168">C# NuGet</span></span>

<span data-ttu-id="daf59-169">Zistite viac o tom, ako začať používať knižnice klientov C# z NuGet.org. Ďalšie informácie o balíku NuGet nájdete v sekcii [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/).</span><span class="sxs-lookup"><span data-stu-id="daf59-169">Learn how to get started using the C# client libraries from NuGet.org. For more information on the NuGet package, see [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/).</span></span> <span data-ttu-id="daf59-170">V súčasnosti je tento balík zameraný na rámce netstandard2.0 a netcoreapp2.0.</span><span class="sxs-lookup"><span data-stu-id="daf59-170">Currently, this package targets the netstandard2.0 and netcoreapp2.0 frameworks.</span></span>

#### <a name="add-the-c-client-library-to-a-c-project"></a><span data-ttu-id="daf59-171">Pridajte knižnicu klientov C# do projektu C#</span><span class="sxs-lookup"><span data-stu-id="daf59-171">Add the C# client library to a C# project</span></span>

1. <span data-ttu-id="daf59-172">V nástroji Visual Studio otvorte **Správcu balíkov NuGet** pre váš projekt.</span><span class="sxs-lookup"><span data-stu-id="daf59-172">In Visual Studio, open the **NuGet Package Manager** for your project.</span></span>

1. <span data-ttu-id="daf59-173">Vyhľadajte výraz **Microsoft.Dynamics.CustomerInsights.Api**.</span><span class="sxs-lookup"><span data-stu-id="daf59-173">Search for **Microsoft.Dynamics.CustomerInsights.Api**.</span></span>

1. <span data-ttu-id="daf59-174">Výberom položky **Inštalovať** pridajte balíček do projektu.</span><span class="sxs-lookup"><span data-stu-id="daf59-174">Select **Install** to add the package to the project.</span></span>
   <span data-ttu-id="daf59-175">Prípadne môžete tento príkaz spustiť cez **konzolu Správcu balíka NuGet**: `Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`</span><span class="sxs-lookup"><span data-stu-id="daf59-175">Alternatively, run this command in the **NuGet Package Manager Console**: `Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`</span></span>

   :::image type="content" source="media/visual-studio-nuget-package.gif" alt-text="Pridajte balík NuGet do projektu nástroja Visual Studio":::

#### <a name="use-the-c-client-library"></a><span data-ttu-id="daf59-177">Použite knižnicu klientov C#</span><span class="sxs-lookup"><span data-stu-id="daf59-177">Use the C# client library</span></span>

1. <span data-ttu-id="daf59-178">Použite [knižnicu Microsoft Authentication Library (MSAL)](/azure/active-directory/develop/msal-overview), aby ste získali `AccessToken` pomocou svojej existujúcej [registrácie aplikácie Azure](#create-a-new-app-registration-in-the-azure-portal).</span><span class="sxs-lookup"><span data-stu-id="daf59-178">Use the [Microsoft Authentication Library (MSAL)](/azure/active-directory/develop/msal-overview) to get an `AccessToken` using your existing [Azure app registration](#create-a-new-app-registration-in-the-azure-portal).</span></span>

1. <span data-ttu-id="daf59-179">Po úspešnom overení a získaní tokenu vytvorte nový alebo použite existujúci `HttpClient` s dodatočným **„oprávnením“ DefaultRequestHeaders** nastavený na **Nosný <access token>** a **Ocp-Apim-Subscription-Key** nastavený na [**kľúč predplatného** z vášho prostredia služby Customer Insights](#get-started-trying-the-customer-insights-apis).</span><span class="sxs-lookup"><span data-stu-id="daf59-179">After successfully authenticating and acquiring a token, construct a new or use an existing `HttpClient` with the additional **DefaultRequestHeaders "Authorization"** set to **Bearer <access token>** and **Ocp-Apim-Subscription-Key** set to the [**subscription key** from your Customer Insights environment](#get-started-trying-the-customer-insights-apis).</span></span>    
   <span data-ttu-id="daf59-180">Resetujte hlavičku **Oprávnenie**, ak je to vhodné.</span><span class="sxs-lookup"><span data-stu-id="daf59-180">Reset the **Authorization** header when appropriate.</span></span> <span data-ttu-id="daf59-181">Napríklad ak vypršala platnosť tokenu.</span><span class="sxs-lookup"><span data-stu-id="daf59-181">For example, when the token expired.</span></span>

1. <span data-ttu-id="daf59-182">Presuňte tohto klienta `HttpClient` do tvorby klienta `CustomerInsights`.</span><span class="sxs-lookup"><span data-stu-id="daf59-182">Pass this `HttpClient` into the construction of the `CustomerInsights` client.</span></span>

   :::image type="content" source="media/httpclient-sample.png" alt-text="Ukážka klienta httpclient":::

1. <span data-ttu-id="daf59-184">Uskutočňujte hovory s klientom pre „metódy rozšírenia“, napríklad `GetAllInstancesAsync`.</span><span class="sxs-lookup"><span data-stu-id="daf59-184">Make calls with the client to the "extension methods", for example, `GetAllInstancesAsync`.</span></span> <span data-ttu-id="daf59-185">Ak je preferovaný prístup k základnému `Microsoft.Rest.HttpOperationResponse`, použite „metódy správ http“, napríklad `GetAllInstancesWithHttpMessagesAsync`.</span><span class="sxs-lookup"><span data-stu-id="daf59-185">If access to the underlying `Microsoft.Rest.HttpOperationResponse` is preferred, use the "http message methods", for example `GetAllInstancesWithHttpMessagesAsync`.</span></span>

1. <span data-ttu-id="daf59-186">Odpoveď bude pravdepodobne typu `object`, pretože metóda môže vrátiť viac typov (napríklad `IList<InstanceInfo>` a `ApiErrorResult`).</span><span class="sxs-lookup"><span data-stu-id="daf59-186">The response will likely be of type `object` because the method can return multiple types (for example, `IList<InstanceInfo>` and `ApiErrorResult`).</span></span> <span data-ttu-id="daf59-187">Ak chcete skontrolovať typ návratu, môžete objekty bezpečne obsadiť do typov odpovedí uvedených na [stránke s podrobnosťami o rozhraní API](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) pre danú operáciu.</span><span class="sxs-lookup"><span data-stu-id="daf59-187">To check the return type, you can safely cast the objects into the response types specified on the [API details page](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) for that operation.</span></span>    
   <span data-ttu-id="daf59-188">Ak sú potrebné ďalšie informácie o požiadavke, získajte prístup k nespracovanému objektu odpovede cez **metódy správ HTTP**.</span><span class="sxs-lookup"><span data-stu-id="daf59-188">If more information on the request is needed, use the **http message methods** to access the raw response object.</span></span>

### <a name="nodejs-package"></a><span data-ttu-id="daf59-189">Balíček NodeJS</span><span class="sxs-lookup"><span data-stu-id="daf59-189">NodeJS package</span></span>

<span data-ttu-id="daf59-190">Použite klientske knižnice NodeJS dostupné cez NPM: https://www.npmjs.com/package/@microsoft/customerinsights</span><span class="sxs-lookup"><span data-stu-id="daf59-190">Use the NodeJS client libraries available through NPM: https://www.npmjs.com/package/@microsoft/customerinsights</span></span>

### <a name="python-package"></a><span data-ttu-id="daf59-191">Balík Python</span><span class="sxs-lookup"><span data-stu-id="daf59-191">Python package</span></span>

<span data-ttu-id="daf59-192">Použite klientske knižnice Python dostupné cez PyPi: https://pypi.org/project/customerinsights/</span><span class="sxs-lookup"><span data-stu-id="daf59-192">Use the Python client libraries available through PyPi: https://pypi.org/project/customerinsights/</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
