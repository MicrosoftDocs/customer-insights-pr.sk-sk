---
title: Pracujte s rozhraniami API v službe Customer Insights
description: Používajte rozhrania API a pochopte ich obmedzenia.
ms.date: 08/31/2022
ms.reviewer: wimohabb
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
searchScope:
- ci-system-api-usage
- customerInsights
ms.openlocfilehash: f499bff4a6ac07a88ff0f773b9cee77dc74989e8
ms.sourcegitcommit: 624b27bb65a0de1970dc1ac436643b493f0a31cf
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 08/31/2022
ms.locfileid: "9387359"
---
# <a name="work-with-customer-insights-apis"></a>Pracujte s rozhraniami API v službe Customer Insights

Dynamics 365 Customer Insights poskytuje API na vytváranie vlastných aplikácií na základe vašich údajov v službe Customer Insights.

> [!IMPORTANT]
> Podrobnosti o týchto rozhraniach API sú uvedené v [referencii rozhraní API v službe Customer Insights](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights). Patria sem dodatočné informácie o operáciách, parametroch a reakciách.

Vyskúšajte rozhrania API Customer Insights, vytvorte registráciu aplikácií Azure a začnite používať klientske knižnice.

## <a name="get-started-trying-the-customer-insights-apis"></a>Začnite skúšať rozhrania API v službe Customer Insights

Povoľte rozhrania API Customer Insights a vyskúšajte ich. Správca Customer Insights musí povoliť prístup API k Customer Insights. Po povolení prístupu môže každý používateľ používať API s kľúčom predplatného.

1. [Prihláste sa](https://home.ci.ai.dynamics.com) do služby Customer Insights. Ak ešte nemáte predplatné, [zaregistrujte sa na skúšobnú verziu Customer Insights](https://aka.ms/tryci).

1. Ísť do **Admin** > **Bezpečnosť** a vyberte **API** tab.

1. Ak nebol nastavený prístup API k prostrediu, vyberte **Povoliť**.

   Povolením rozhraní API sa vytvorí primárny a sekundárny kľúč predplatného pre vašu inštanciu, ktorý sa použije pri požiadavkách pre rozhrania API. Ak chcete obnoviť kľúče, vyberte **Primárne regenerovať** alebo **Regenerovať sekundárne** na **API** tab.

1. Vyberte [**Preskúmajte naše rozhrania API**](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances) na vyskúšanie API.

1. Vyhľadajte a vyberte operáciu API a vyberte **Skús to**.

   :::image type="content" source="media/try-api.png" alt-text="Ako testovať rozhrania API.":::

1. Na bočnej table nastavte hodnotu v rozbaľovacej ponuky **Oprávnenie** na **implicitné**. Hlavička `Authorization` sa pridá s nosným tokenom. Váš predplatiteľský kľúč sa vyplní automaticky.
  
1. Prípadne môžete pridať všetky potrebné parametre dotazu.

1. Prejdite do dolnej časti bočnej tably a vyberte ikonu **Poslať**.

   Odpoveď HTTP sa zobrazí v spodnej časti tably.

## <a name="create-a-new-app-registration-in-the-azure-portal"></a>Vytvorte novú registráciu aplikácie na portáli Azure

Vytvorte nový [registrácia aplikácie](/graph/auth-register-app-v2) na používanie rozhraní API Customer Insights v aplikácii Azure pomocou delegovaných povolení.

1. Dokončiť [Sekcia Začíname](#get-started-trying-the-customer-insights-apis).

1. Prihláste sa do [portálu Azure](https://portal.azure.com) pomocou účtu, ktorý má prístup k údajom služby Customer Insights.

1. Vyhľadajte a potom vyberte **Registrácia aplikácií**.

1. Vyberte položku **Nová registrácia**, zadajte názov aplikácie a vyberte typ účtu.

   Prípadne pridajte adresu URL presmerovania. http://localhost postačí na vývoj aplikácie na vašom lokálnom počítači.

1. Vyberte položku **Registrovať**.

1. Pri novej registrácii aplikácie prejdite na **Povolenia pre API**.

1. Vyberte **Pridajte povolenie** a vyberte **Dynamics 365 AI for Customer Insights** v bočnom paneli.

1. Pre **Typ povolenia** vyberte možnosť **Delegované povolenia** a potom vyberte povolenie **user_impersonation**.

1. Vyberte položku **Pridať povolenia**.

1. Vyberte položku **Udeliť súhlas správcu pre...** na dokončenie registrácie aplikácie.

1. Ak chcete získať prístup k API bez prihlásenia používateľa, prejdite na [Povolenia aplikácie server-to-server](#server-to-server-application-permissions).

Na registráciu tejto aplikácie môžete použiť ID aplikácie/klienta s [Microsoft Authentication Library (MSAL)](/azure/active-directory/develop/msal-overview) na získanie tokenu nosiča, ktorý sa odošle s vašou požiadavkou do API.

<!-- :::image type="content" source="media/grant-admin-consent.gif" alt-text="How to grant admin consent."::: -->

Informácie o používaní rozhraní API v našich klientskych knižniciach nájdete v sekcii [Klientske knižnice Customer Insights](#customer-insights-client-libraries).

### <a name="server-to-server-application-permissions"></a>Povolenia pre aplikácie typu server-to-server

Vytvorte registráciu aplikácie, ktorá nevyžaduje interakciu používateľa a možno ju spustiť na serveri.

1. Pri registrácii aplikácie na portáli Azure prejdite na **Povolenia pre API**.

1. Vyberte **Pridať povolenie**.

1. Stlačte kartu **Rozhrania API, ktoré používa moja organizácia** a stlačte v zozname možnosť **Dynamics 365 AI for Customer Insights**.

1. Pre **Typ povolenia** vyberte možnosť **Povolenia pre aplikácie** a potom vyberte povolenie **CustomerInsights.Api.All**.

1. Vyberte položku **Pridať povolenia**.

1. Pri registrácii aplikácie sa vráťte na **Povolenia pre API**.

1. Vyberte položku **Udeliť súhlas správcu pre...** na dokončenie registrácie aplikácie.

   <!--  :::image type="content" source="media/grant-admin-consent.gif" alt-text="How to grant admin consent."::: -->

1. Pridajte názov registrácie aplikácie ako používateľa do Customer Insights.

   1. Otvorte Customer Insights, prejdite na **Admin** > **Bezpečnosť** a vyberte **Pridajte používateľov**.

   1. Vyhľadajte názov registrácie aplikácie, vyberte ho z výsledkov vyhľadávania a vyberte položku **Uložiť**.

## <a name="sample-queries"></a>Vzorové otázky

Krátky zoznam vzorových dotazov OData na prácu s rozhraniami API nájdete na stránke [Príklady dotazov OData](odata-examples.md).

## <a name="customer-insights-client-libraries"></a>Knižnice klientov v službe Customer Insights

Začnite používať klientske knižnice dostupné pre rozhrania Customer Insights API. Všetky zdrojové kódy knižníc a vzorové aplikácie nájdete na [stránke Customer Insights GitHub](https://github.com/microsoft/Dynamics365-CustomerInsights-Client-Libraries).

### <a name="c-nuget"></a>C# NuGet

Použite klientske knižnice C# z NuGet .org. V súčasnosti sa balík zameriava na rámce netstandard2.0 a netcoreapp2.0. Pre viac informácií na NuGet balík, viď [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/).

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

1. Uskutočňujte hovory s klientom pre „metódy rozšírenia“, napríklad `GetAllInstancesAsync`. Ak je prístup k podkladu`Microsoft.Rest.HttpOperationResponse` je preferované, použite "metódy správy http", napr.`GetAllInstancesWithHttpMessagesAsync`.

1. Odpoveď je pravdepodobná`object` typu, pretože metóda môže vrátiť viacero typov (napr.`IList<InstanceInfo>` a`ApiErrorResult`). Ak chcete skontrolovať návratový typ, použite objekty v typoch odpovedí špecifikovaných na [Stránka s podrobnosťami o rozhraní API](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) na tú operáciu.

   Ak sú potrebné ďalšie informácie o požiadavke, získajte prístup k nespracovanému objektu odpovede cez **metódy správ HTTP**.

### <a name="nodejs-package"></a>Balíček NodeJS

Použite klientske knižnice NodeJS dostupné cez NPM: https://www.npmjs.com/package/@microsoft/customerinsights

### <a name="python-package"></a>Balík Python

Použite klientske knižnice Python dostupné cez PyPi: https://pypi.org/project/customerinsights/

[!INCLUDE [footer-include](includes/footer-banner.md)]
