---
title: Práca s API
description: Používajte rozhrania API a pochopte ich obmedzenia.
ms.date: 12/04/2020
ms.reviewer: wimohabb
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 5a03e916676800afdd8692da865a1060952d5c4f
ms.sourcegitcommit: b50c754481d0af6d0cf4b550775d7b31d95846ef
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 12/06/2020
ms.locfileid: "4689149"
---
# <a name="work-with-customer-insights-apis"></a>Pracujte s rozhraniami API v službe Customer Insights

Dynamics 365 Customer Insights poskytuje rozhrania API na vytváranie vlastných aplikácií na základe vašich údajov v službe Customer Insights.

> [!IMPORTANT]
> Podrobnosti o týchto rozhraniach API sú uvedené v [referencii rozhraní API v službe Customer Insights](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights). Patria sem dodatočné informácie o operáciách, parametroch a reakciách.

Tento článok vás prevedie prístupom k rozhraniam API v službe Customer Insights, vytvorením registrácie aplikácie na portáli Azure a pomôže vám začať s dostupnými knižnicami klientov.

## <a name="get-started-trying-the-customer-insights-apis"></a>Začnite skúšať rozhrania API v službe Customer Insights

1. [Prihláste sa](https://home.ci.ai.dynamics.com) do služby Customer Insights. Ak ešte nemáte predplatné, [zaregistrujte sa na skúšobnú verziu Customer Insights](https://aka.ms/tryci).

1. Ak chcete povoliť rozhrania API vo svojom prostredí služby Customer Insights, prejdite na **Správca** > **Povolenia**. Potrebujete na to povolenia správcu.

1. Prejdite na kartu **Rozhrania API** a vyberte tlačidlo **Povoliť**.    
   Povolením rozhraní API sa vytvorí primárny a sekundárny kľúč predplatného pre vašu inštanciu, ktorý sa použije pri požiadavkách pre rozhrania API. Kľúče môžete znova vygenerovať výberom položky **Znova vygenerovať primárny** alebo **Znova vygenerovať sekundárny** v časti **Správca** > **Povolenia** > **Rozhrania API**.

   :::image type="content" source="media/enable-apis.gif" alt-text="Povoliť rozhrania API v službe Customer Insights":::

1. Výberom položky **Preskúmajte naše rozhrania API** si môžete rozhrania API vyskúšať.

1. Vyberte operáciu pre rozhranie API a vyberte položku **Vyskúšať**.

1. Na bočnej table nastavte hodnotu v rozbaľovacej ponuke **Oprávnenie** na **implicitné**. Hlavička `Authorization` sa získa s pridaným nosným tokenom. Váš kľúč predplatného sa vyplní automaticky.
  
1. Prípadne môžete pridať všetky potrebné parametre dotazu.

1. Prejdite do dolnej časti bočnej tably a vyberte ikonu **Poslať**.

Odpoveď protokolu HTTP sa čoskoro objaví nižšie.

## <a name="create-a-new-app-registration-in-the-azure-portal"></a>Vytvorte novú registráciu aplikácie na portáli Azure

Tieto kroky vám pomôžu začať používať rozhrania API v službe Customer Insights v aplikácii Azure pomocou delegovaných povolení. Najskôr sa uistite, že ste dokončili [sekciu Začíname](#get-started-trying-the-customer-insights-apis).

1. Prihláste sa do [portálu Azure](https://portal.azure.com) pomocou účtu, ktorý má prístup k údajom služby Customer Insights.

1. Vľavo vyberte položku **Registrácie aplikácií**.

1. Vyberte položku **Nová registrácia**, zadajte názov aplikácie a vyberte typ účtu.
   Prípadne pridajte adresu URL presmerovania. http://localhost postačí na vývoj aplikácie na vašom lokálnom počítači.

1. Pri novej registrácii aplikácie prejdite na **Povolenia pre API**.

1. Vyberte položku **Pridať povolenie** a vyberte položku **Customer Insights** na bočnej table.

1. Ako **Typ povolenia** vyberte **Delegované povolenia** a vyberte povolenie **user_impersonation**.

1. Vyberte položku **Pridať povolenia**. Ak potrebujete získať prístup k rozhraniu API bez prihlásenia používateľa, skontrolujte [Povolenia aplikácií typu server-to-server](#server-to-server-application-permissions).

1. Vyberte položku **Udeliť súhlas správcu pre...** na dokončenie registrácie aplikácie.

ID aplikácie/klienta môžete použiť na registráciu tejto aplikácie v knižnici Microsoft Authentication Library (MSAL), aby ste získali nosný token, ktorý sa odošle s vašou požiadavkou pre API.

Ďalšie informácie o MSAL nájdete v sekcii [Prehľad knižnice Microsoft Authentication Library (MSAL)](https://docs.microsoft.com/azure/active-directory/develop/msal-overview).

Ďalšie informácie o registrácii aplikácií v Azure nájdete v [novom prostredí na registráciu aplikácií na portáli Azure](https://docs.microsoft.com/azure/active-directory/develop/app-registration-portal-training-guide).

Informácie o používaní rozhraní API našich knižníc klientov nájdete v sekcii [Knižnice klientov v službe Customer Insights](#customer-insights-client-libraries).

### <a name="server-to-server-application-permissions"></a>Povolenia pre aplikácie typu server-to-server

[Sekcia registrácie aplikácií](#create-a-new-app-registration-in-the-azure-portal) opisuje, ako si zaregistrovať aplikáciu, ktorá vyžaduje od používateľa prihlásenie na účely overenia. Ďalšie informácie o tom, ako vytvoriť registráciu aplikácie, ktorá nevyžaduje interakciu používateľa a možno ju spustiť na serveri.

1. Pri registrácii aplikácie na portáli Azure prejdite na **Povolenia pre API**.

1. Vyberte položku **Pridať povolenie** a vyberte položku **Customer Insights** na bočnej table.

1. Ako **Typ povolenia** vyberte **Povolenia pre aplikáciu** a vyberte povolenie **CustomerInsights.Api.All**.

1. Vyberte položku **Pridať povolenia**.

1. Ak chcete udeliť súhlas správcu s týmto povolením pre aplikáciu, musíte pridať objekt služby.

   1. Nainštalujte modul Azure Active Directory (AD) PowerShell: `Install-Module -Name AzureAD -AllowClobber -Scope AllUsers`
   1. Pripojte sa k svojmu účtu AD: `Connect-AzureAD -TenantId <your tenant id>`. ID nájomníka nájdete v sekcii **Prehľad** > **Azure Active Directory**.
   1. Spustením nasledujúceho príkazu pridáte objekt služby Azure AD: `New-AzureADServicePrincipal -AppId "38c77d00-5fcb-4cce-9d93-af4738258e3c" -DisplayName "Microsoft Dynamics 365 Customer Insights"` Parameter AppId sa týka aplikácie rozhrania API v službe Customer Insights.

   :::image type="content" source="media/azureAD-service-principal.png" alt-text="Ukážka objektu služby":::

1. Pri registrácii aplikácie sa vráťte na **Povolenia pre API**.

1. Vyberte položku **Udeliť súhlas správcu pre...** na dokončenie registrácie aplikácie.

1. Na záver musíme do služby Customer Insights pridať názov registrácie aplikácie ako používateľa.    
   Otvorte službu Customer Insights, prejdite na položku **Správca** > **Povolenia** a vyberte položku **Pridať používateľa**.

1. Vyhľadajte názov registrácie aplikácie, vyberte ho z výsledkov vyhľadávania a vyberte položku **Uložiť**.

## <a name="customer-insights-client-libraries"></a>Knižnice klientov v službe Customer Insights

Táto sekcia vám pomôže začať používať knižnice klientov dostupné pre rozhrania API v službe Customer Insights.

### <a name="c-nuget"></a>C# NuGet

Zistite viac o tom, ako začať používať knižnice klientov C# z NuGet.org. Ďalšie informácie o balíku NuGet nájdete v sekcii [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/). V súčasnosti je tento balík zameraný na rámce netstandard2.0 a netcoreapp2.0.

#### <a name="add-the-c-client-library-to-a-c-project"></a>Pridajte knižnicu klientov C# do projektu C#

1. V nástroji Visual Studio otvorte **Správcu balíkov NuGet** pre váš projekt.

1. Vyhľadajte výraz **Microsoft.Dynamics.CustomerInsights.Api**.

1. Výberom položky **Inštalovať** pridajte balíček do projektu.
   Prípadne môžete tento príkaz spustiť cez **konzolu Správcu balíka NuGet**: `Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`

   :::image type="content" source="media/visual-studio-nuget-package.gif" alt-text="Pridajte balík NuGet do projektu nástroja Visual Studio":::

#### <a name="use-the-c-client-library"></a>Použite knižnicu klientov C#

1. Použite [knižnicu Microsoft Authentication Library (MSAL)](https://docs.microsoft.com/azure/active-directory/develop/msal-overview), aby ste získali `AccessToken` pomocou svojej existujúcej [registrácie aplikácie Azure](#create-a-new-app-registration-in-the-azure-portal).

1. Po úspešnom overení a získaní tokenu vytvorte nový alebo použite existujúci `HttpClient` s dodatočným **„oprávnením“ DefaultRequestHeaders** nastavený na **Nosný <access token>** a **Ocp-Apim-Subscription-Key** nastavený na [**kľúč predplatného** z vášho prostredia služby Customer Insights](#get-started-trying-the-customer-insights-apis).    
   Resetujte hlavičku **Oprávnenie**, ak je to vhodné. Napríklad ak vypršala platnosť tokenu.

1. Presuňte tohto klienta `HttpClient` do tvorby klienta `CustomerInsights`.

   :::image type="content" source="media/httpclient-sample.png" alt-text="Ukážka klienta httpclient":::

1. Uskutočňujte hovory s klientom pre „metódy rozšírenia“, napríklad `GetAllInstancesAsync`. Ak je preferovaný prístup k základnému `Microsoft.Rest.HttpOperationResponse`, použite „metódy správ http“, napríklad `GetAllInstancesWithHttpMessagesAsync`.

1. Odpoveď bude pravdepodobne typu `object`, pretože metóda môže vrátiť viac typov (napríklad `IList<InstanceInfo>` a `ApiErrorResult`). Ak chcete skontrolovať typ návratu, môžete objekty bezpečne obsadiť do typov odpovedí uvedených na [stránke s podrobnosťami o rozhraní API](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) pre danú operáciu.    
   Ak sú potrebné ďalšie informácie o požiadavke, získajte prístup k nespracovanému objektu odpovede cez **metódy správ HTTP**.
