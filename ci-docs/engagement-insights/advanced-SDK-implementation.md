---
title: Pokročilé webové scenáre SDK
description: Pokročilé scenáre, ktoré treba brať do úvahy pri vybavovaní vášho webu SDK.
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 11/12/2020
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 7455d276035bfaf1f8a93d0e3b0b0884353a4010715c05d1d696309f7eb4b233
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036347"
---
# <a name="advanced-web-sdk-instrumentation"></a>Pokročilé vybavenie web SDK

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Tento článok vás prevedie pokročilými scenármi, ktoré je potrebné zvážiť [pri vybavovaní vašej webovej stránky](instrument-website.md) s možnosťami prehľadov interakcií Dynamics 365 Customer Insights SDK.

## <a name="setting-user-details-for-your-event"></a>Nastavenie podrobností používateľa pre vašu udalosť

Súprava SDK umožňuje definovať informácie o používateľovi, ktoré je možné odoslať pri každej udalosti. Môžete určiť podrobnosti používateľa vo vlastnosti nazvanej `user` (očakávané údaje pre túto vlastnosť sú objekt `IUser`), podobne ako `src`, `name` a `cfg` v konfigurácii úryvku kódu.

Objekt `IUser` obsahuje nasledujúce vlastnosti reťazca:

- **localId**: Miestne ID používateľa.
- **authId**: ID autentifikovaného užívateľa.
- **authType**: Typ autentifikácie používaný na získanie autentifikovaného ID užívateľa.
- **meno**: Meno používateľa.
- **e-mail**: Používateľská e-mailová adresa.
    
Nasledujúci príklad ukazuje úryvok kódu, ktorý odosiela informácie o používateľovi. Tam, kde vidíte funkcie označené *, nahraďte ich implementáciou názvov týchto hodnôt:  

```
[…]
window, document 
{
    src:"https://download.pi.dynamics.com/sdk/web/mspi-0.min.js", 
    name:"myproject",      
    cfg:{ 
      ingestionKey:<paste your ingestion key>", 
      autoCapture:{ 
        view:true, 
        click:true 
      }
    },
    user:{
      authId: getLoggedInUserId()*,
      email: getLoggedInUserEmail()*,
      authType: "MSA",
      name: "John Doe"
    }
[…]
```

Môžete tiež určiť informácie o používateľovi vyvolaním `setUser(user: IUser)` API na SDK. Telemetria odoslaná po vyvolaní `setUser API` bude obsahovať informácie o používateľovi.

## <a name="adding-custom-properties-for-each-event"></a>Pridávanie vlastných vlastností pre každú udalosť

Súprava SDK umožňuje zadať vlastné vlastnosti, ktoré je možné odoslať pri každej udalosti. Vlastné vlastnosti môžete určiť ako objekt obsahujúci páry kľúč - hodnota (hodnota môže byť typu `string | number | boolean`). Objekt je možné pridať do vlastnosti s názvom `props`, čo je podobné `src`, `name` a `cfg` v konfigurácii úryvku kódu. 

Nasledujúci príklad ukazuje úryvok kódu, ktorý odosiela vlastné vlastnosti:

```
[…]
window, document 
{
    src:"https://download.pi.dynamics.com/sdk/web/mspi-0.min.js", 
    name:"myproject",      
    cfg:{ 
      ingestionKey:<paste your ingestion key>", 
      autoCapture:{ 
        view:true, 
        click:true 
      }
    },
    props:{
      "key_name_string": "value",
      "key_name_number": 10,
      "key_name_bool": true
    }
[…]
```

Vlastné vlastnosti môžete určiť aj jednotlivo vyvolaním `setProperty(name: string, value: string | number | boolean)` API na SDK.

## <a name="sending-custom-events"></a>Odoslanie vlastných udalostí

Pomocou SDK môžete odosielať vlastné udalosti. Musíte určiť názov udalosti a vlastnosti, ktoré sa majú s udalosťou odoslať.

Nasledujúci príklad ukazuje úryvok kódu, ktorý sleduje vlastnú udalosť. „NAME“ je hodnota v kľúču `name` v konfigurácii úryvku. Je to tiež názov premennej v objekte okna, kde je načítaná súprava SDK.

```
window["NAME"].trackEvent({
    name: "event_name",
    properties: {
        "duration": 320,
        "name": "getting_started",
        "ad_shown": true
    }
});
```


[!INCLUDE[footer-include](../includes/footer-banner.md)]