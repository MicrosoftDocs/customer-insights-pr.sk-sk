---
title: Odlíšte webové udalosti od predtým overených návštevníkov od neznámych k známym
description: Funkcia od neznámych k známym umožňuje priradiť udalosti na webovej lokalite k návštevníkom, ktorí predtým boli overení.
ms.reviewer: mhart
ms.author: mkisel
author: mkisel11
ms.date: 7/15/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: overview
ms.manager: shellyha
ms.openlocfilehash: d1bbc3315b55e2ee233dc672456e0c27e4ad0fbd5937af09cc790c96ee274000
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036802"
---
# <a name="recognize-web-events-from-previously-authenticated-visitors"></a>Odlíšte webové udalosti od predtým overených návštevníkov

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Funkcia **od neznámych k známym** vo funkcii prehľadu interakcií umožňuje priradiť udalosti na webovej lokalite k návštevníkom, ktorí predtým boli overení. Ak je táto funkcia zakázaná, návštevníci overení pri predchádzajúcej návšteve, ktorí potom odišli, nebudú pri návrate znovu identifikovaní, a budú sa musieť nechať overiť znovu. 

Niekto napríklad pred týždňom navštívil webovú lokalitu, prihlásil sa do svojho používateľského účtu na tejto lokalite, a prezeral si produktový katalóg. Táto osoba sa nasledujúci týždeň vráti, aby si prezrela ďalšie produkty bez prihlásenia sa do svojho účtu. Majiteľ stránky pomocou funkcie **od neznámych k známym** by vedel, že sa vrátila rovnaká osoba a aké úkony urobila na lokalite. Takto bude možné presnejšie vykázať a analyzovať aktivitu na webových lokalitách.

## <a name="enable-unknown-to-known"></a>Povoliť funkciu Od neznámych k známym

Na povolenie tejto funkcie potrebujete povolenia [správcu pracovného priestoru](user-roles.md) . 

1. V prehľadoch zapojenia zobrazte časť **Správca** > **Pracovný priestor**. 
2. Vyberte kartu **Nastavenia**.
3. V časti **Od neznámych k známym** nastavte prepínač na **Povolené**.

![Povoliť funkciu Od neznámych k známym](media/U2Ktoggle.png "Povoliť funkciu Od neznámych k známym")

## <a name="adding-javascript-code-to-your-sites-tracking-snippet"></a>Pridanie kódu JavaScript do úryvku kódu sledovania vašej lokality

Webová lokalita môže zachytiť **authId používateľa** s nasledujúcou ukážkou JavaScriptu pomocou [webovej súpravy SDK prehľadov interakcií ](advanced-SDK-implementation.md). Aby funkcia **Od neznámych k známym** fungovala, je potrebné zachytiť autorizáciu authId *a* povoliť nastavenie userMapping:True vo vašom úryvku kódu JavaScript, ako je to uvedené v ukážke nižšie.

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
},
userMapping: true
},
user:{
authId: getLoggedInUserId()*,
email: getLoggedInUserEmail()*,
authType: "MSA",
name: "Alex Jensen"
}
[…]
```

[!INCLUDE[footer-include](../includes/footer-banner.md)]
