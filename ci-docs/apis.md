---
title: Práca s API
description: Používajte rozhrania API a pochopte ich obmedzenia.
ms.date: 05/10/2021
ms.reviewer: wimohabb
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
searchScope:
- ci-system-api-usage
- customerInsights
ms.openlocfilehash: 9a04276f7326533cd389cba6554f468123463bac
ms.sourcegitcommit: bf65bc0a54cdab71680e658e1617bee7b2c2bb68
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 05/27/2022
ms.locfileid: "8808546"
---
# <a name="work-with-customer-insights-apis"></a>Pracujte s rozhraniami API v službe Customer Insights

Dynamics 365 Customer Insights poskytuje API na vytváranie vlastných aplikácií na základe vašich údajov v službe Customer Insights.

> [!IMPORTANT]
> Podrobnosti o týchto rozhraniach API sú uvedené v [referencii rozhraní API v službe Customer Insights](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights). Patria sem dodatočné informácie o operáciách, parametroch a reakciách.

Tento článok popisuje, ako získať prístup k rozhraniam API Customer Insights, vytvoriť registráciu aplikácie Azure a ako začať s klientskymi knižnicami.

## <a name="get-started-trying-the-customer-insights-apis"></a>Začnite skúšať rozhrania API v službe Customer Insights

1. [Prihláste sa](https://home.ci.ai.dynamics.com) do služby Customer Insights. Ak ešte nemáte predplatné, [zaregistrujte sa na skúšobnú verziu Customer Insights](https://aka.ms/tryci).

1. Ak chcete povoliť rozhrania API vo svojom prostredí Customer Insights, prejdite na stránku **Admin** > **Bezpečnosť**. Potrebujete na to povolenia správcu.

1. Prejdite na kartu **Rozhrania API** a vyberte tlačidlo **Povoliť**.    
 
   Povolením rozhraní API sa vytvorí primárny a sekundárny kľúč predplatného pre vašu inštanciu, ktorý sa použije pri požiadavkách pre rozhrania API. Kľúče môžete obnoviť výberom položky **Primárne regenerovať** alebo **Regenerovať sekundárne** na **Admin** > **Bezpečnosť** > **API**.

<!--  :::image type="content" source="media/enable-apis.gif" alt-text="Enable Customer Insights APIs."::: -->

1. Výberom položky **Preskúmajte naše rozhrania API** si môžete [rozhrania API vyskúšať](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances).

1. Vyberte operáciu pre rozhranie API a vyberte položku **Vyskúšať**.

1. Na bočnej table nastavte hodnotu v rozbaľovacej ponuky **Oprávnenie** na **implicitné**. Hlavička `Authorization` sa pridá s nosným tokenom. Váš kľúč predplatného sa vyplní automaticky.
  
1. Prípadne môžete pridať všetky potrebné parametre dotazu.

1. Prejdite do dolnej časti bočnej tably a vyberte ikonu **Poslať**.

Odpoveď protokolu HTTP sa čoskoro objaví nižšie.

<!--   :::image type="content" source="media/try-apis.gif" alt-text="How to test the APIs."::: -->

## <a name="create-a-new-app-registration-in-the-azure-portal"></a>Vytvorte novú registráciu aplikácie na portáli Azure

Tieto kroky vám pomôžu začať s používaním rozhraní API pre Customer Insights v aplikácii Azure pomocou delegovaných povolení. Nezabudnite najskôr dokončiť [sekciu Začíname](#get-started-trying-the-customer-insights-apis).

1. Prihláste sa do [portálu Azure](https://portal.azure.com) pomocou účtu, ktorý má prístup k údajom služby Customer Insights.

1. Vľavo vyberte položku **Registrácie aplikácií**.

1. Vyberte položku **Nová registrácia**, zadajte názov aplikácie a vyberte typ účtu.

   Prípadne pridajte adresu URL presmerovania. http://localhost postačí na vývoj aplikácie na vašom lokálnom počítači.

1. Pri novej registrácii aplikácie prejdite na **Povolenia pre API**.

1. Vyberte **Pridajte povolenie** a vyberte **Dynamics 365 AI pre Customer Insights** v bočnom paneli.

1. Pre **Typ povolenia** vyberte možnosť **Delegované povolenia** a potom vyberte povolenie **user_impersonation**.

1. Vyberte položku **Pridať povolenia**. Ak potrebujete získať prístup k rozhraniu API bez prihlásenia používateľa, skontrolujte [Povolenia aplikácií typu server-to-server](#server-to-server-application-permissions).

1. Vyberte položku **Udeliť súhlas správcu pre...** na dokončenie registrácie aplikácie.

ID aplikácie/klienta môžete použiť na registráciu tejto aplikácie v knižnici Microsoft Authentication Library (MSAL), aby ste získali nosný token, ktorý sa odošle s vašou požiadavkou pre API.

<!-- :::image type="content" source="media/grant-admin-consent.gif" alt-text="How to grant admin consent."::: -->

Ďalšie informácie o MSAL nájdete v sekcii [Prehľad knižnice Microsoft Authentication Library (MSAL)](/azure/active-directory/develop/msal-overview).

Ďalšie informácie o registrácii aplikácií v službe Azure nájdete v sekcii [Registrácia aplikácie](/graph/auth-register-app-v2).

Informácie o používaní rozhraní API v našich klientskych knižniciach nájdete v sekcii [Klientske knižnice Customer Insights](#customer-insights-client-libraries).

### <a name="server-to-server-application-permissions"></a>Povolenia pre aplikácie typu server-to-server

[Sekcia registrácie aplikácií](#create-a-new-app-registration-in-the-azure-portal) opisuje, ako si zaregistrovať aplikáciu, ktorá vyžaduje od používateľa prihlásenie na účely overenia. Zistite, ako vytvoriť registráciu aplikácie, ktorá nevyžaduje zásah používateľa a možno ju spustiť na serveri.

1. Pri registrácii aplikácie na portáli Azure prejdite na **Povolenia pre API**.

1. Vyberte **Pridať povolenie**. 

1. Stlačte kartu **Rozhrania API, ktoré používa moja organizácia** a stlačte v zozname možnosť **Dynamics 365 AI for Customer Insights**. 

1. Pre **Typ povolenia** vyberte možnosť **Povolenia pre aplikácie** a potom vyberte povolenie **CustomerInsights.Api.All**.

1. Vyberte položku **Pridať povolenia**.

1. Pri registrácii aplikácie sa vráťte na **Povolenia pre API**.

1. Vyberte položku **Udeliť súhlas správcu pre...** na dokončenie registrácie aplikácie.

 <!--  :::image type="content" source="media/grant-admin-consent.gif" alt-text="How to grant admin consent."::: -->

1. Na záver musíme do služby Customer Insights pridať názov registrácie aplikácie ako používateľa.  
   
   Otvorte Customer Insights, prejdite na **Admin** > **Bezpečnosť** a vyberte **Pridať používateľa**.

1. Vyhľadajte názov registrácie aplikácie, vyberte ho z výsledkov vyhľadávania a vyberte položku **Uložiť**.

## <a name="sample-queries"></a>Vzorové otázky

Zostavili sme krátky zoznam vzorových dotazov OData na prácu s rozhraniami API: [Príklady dotazov OData](odata-examples.md).

## <a name="customer-insights-client-libraries"></a>Knižnice klientov v službe Customer Insights

Táto sekcia vám pomôže začať používať knižnice klientov dostupné pre rozhrania API v službe Customer Insights. Všetky zdrojové kódy knižníc a vzorové aplikácie nájdete na [stránke Customer Insights GitHub](https://github.com/microsoft/Dynamics365-CustomerInsights-Client-Libraries). 

### <a name="c-nuget"></a>C# NuGet

Zistite viac o tom, ako začať používať knižnice klientov C# z NuGet.org. Ďalšie informácie o balíku NuGet nájdete v sekcii [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/). V súčasnosti je tento balík zameraný na rámce netstandard2.0 a netcoreapp2.0.

#### <a name="add-the-c-client-library-to-a-c-project"></a>Pridajte knižnicu klientov C# do projektu C#

1. V nástroji Visual Studio otvorte **Správcu balíkov NuGet** pre váš projekt.

1. Vyhľadajte výraz **Microsoft.Dynamics.CustomerInsights.Api**.

1. Výberom položky **Inštalovať** pridajte balíček do projektu.
 
   Prípadne môžete tento príkaz spustiť cez **konzolu Správcu balíka NuGet**: `Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`

 <!--  :::image type="content" source="media/visual-studio-nuget-package.gif" alt-text="Add NuGet package to Visual Studio project."::: -->

#### <a name="use-the-c-client-library"></a>Použite knižnicu klientov C#

1. Použite [knižnicu Microsoft Authentication Library (MSAL)](/azure/active-directory/develop/msal-overview), aby ste získali `AccessToken` pomocou svojej existujúcej [registrácie aplikácie Azure](#create-a-new-app-registration-in-the-azure-portal).

1. Po úspešnom overení a získaní tokenu vytvorte nový alebo použite existujúci`HttpClient` s **DefaultRequestHeaders "Autorizácia"** nastavený na **Nosič "prístupový token"** a **Ocp-Apim-Subscription-Key** nastaviť na [**predplatiteľský kľúč** z prostredia Customer Insights](#get-started-trying-the-customer-insights-apis).   
 
   Resetujte hlavičku **Oprávnenie**, ak je to vhodné. Napríklad ak vypršala platnosť tokenu.

1. Presuňte tohto klienta `HttpClient` do tvorby klienta `CustomerInsights`.

<!--   :::image type="content" source="media/httpclient-sample.png" alt-text="Sample of httpclient."::: -->

1. Uskutočňujte hovory s klientom pre „metódy rozšírenia“ – napríklad `GetAllInstancesAsync`. Ak je preferovaný prístup k základnému `Microsoft.Rest.HttpOperationResponse`, použite „metódy správ http“ – napríklad `GetAllInstancesWithHttpMessagesAsync`.

1. Odpoveď bude pravdepodobne typu `object`, pretože metóda môže vrátiť viac typov (napríklad `IList<InstanceInfo>` a `ApiErrorResult`). Ak chcete skontrolovať návratový typ, použite objekty v typoch odpovedí špecifikovaných na [Stránka s podrobnosťami o rozhraní API](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) pre danú operáciu.    
   
   Ak sú potrebné ďalšie informácie o požiadavke, získajte prístup k nespracovanému objektu odpovede cez **metódy správ HTTP**.

### <a name="nodejs-package"></a>Balíček NodeJS

Použite klientske knižnice NodeJS dostupné cez NPM: https://www.npmjs.com/package/@microsoft/customerinsights

### <a name="python-package"></a>Balík Python

Použite klientske knižnice Python dostupné cez PyPi: https://pypi.org/project/customerinsights/

[!INCLUDE [footer-include](includes/footer-banner.md)]
