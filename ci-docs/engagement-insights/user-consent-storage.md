---
title: Aby ste mohli ukladať údaje do služby Dynamics 365 Customer Insights, je potrebná správa súborov cookie a súhlasu používateľa
description: Zistite, ako sa súbory cookie a súhlas používateľa používajú na identifikáciu návštevníkov webových stránok.
author: mochimochi016
ms.reviewer: mhart
ms.author: jefhar
ms.date: 09/27/2021
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 018263220d4628690e9f0beb8453e58b0356d099
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 02/16/2022
ms.locfileid: "8229004"
---
# <a name="manage-cookies-and-user-consent"></a>Spravovanie súborov cookie súhlasov používateľa

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Funkcia prehľadov interakcií Dynamics 365 Customer Insights používa súbory cookie a kľúče (`localStorage`) na to, aby identifikovala návštevníkov webovej lokality.

Súbory cookie sú malé súbory, ktoré ukladajú informácie o interakciách používateľa s webovou stránkou. Sú uložené vo webových prehliadačoch. Keď používatelia navštívia webovú stránku, pre ktorú majú vaši používatelia uložené súbory cookie, prehľadávač odošle tieto informácie na server, ktorý vráti informácie, ktoré sú pre používateľa jedinečné. Toto je technológia, ktorá umožňuje napríklad nákupnému košíku online uchovávať vybrané položky v ňom, aj keď sa používateľ dostane mimo webovú stránku.

## <a name="user-consent"></a>Súhlas používateľa

[Všeobecné nariadenie o ochrane údajov (GDPR)](/dynamics365/get-started/gdpr/) je nariadenie Európskej únie (EÚ), ktoré nariaďuje, ako by organizácie mali nakladať so súkromím a bezpečnosťou svojich používateľov. Súbory cookie často ukladajú alebo zhromažďujú „osobné údaje“, napríklad online identifikátor, na ktorý sa vzťahuje nariadenie GDPR. Ak váš podnik zamestnáva alebo predáva tovary či služby dotknutým osobám v EÚ, GDPR sa vás týka. [Prečítajte si viac informácií o tom, ako vám spoločnosť Microsoft môže pomôcť dosiahnuť súlad s nariadením GDPR](https://www.microsoft.com/trust-center/privacy/gdpr-faqs).

Ak chcete povoliť súhrnným prehľadom interakcií, aby mohli ukladať súbory cookie alebo iné citlivé informácie, musíte určiť, či s tým vaši používatelia súhlasili. To nastáva pri inicializácii súpravy SDK nastavením poľa `userConsent` v konfigurácii.

Ak naznačíte, že neexistuje súhlas používateľa, súprava SDK nebude ukladať žiadne údaje a nebude odosielať udalosti, ktoré možno použiť na sledovanie správania používateľov. Všetky predtým uložené údaje budú z prehliadača odstránené.

Ak nie je zadaná žiadna hodnota súhlasu používateľa, SDK bude predpokladať, že používateľ vyjadril súhlas. To znamená, že ak (ako náš zákazník) nezadáte hodnotu pre súhlas používateľa v súprave SDK, údaje sa zhromaždia. Ak však určíte, že hodnota pre súhlas používateľa musí byť „true“, údaje sa nebudú zhromažďovať, ak používateľ odmietne alebo neposkytne výslovný súhlas.

Dole je uvedený úryvok kódu, ktorý slúži na inicializáciu webovej súpravy SDK so súhlasom používateľa:
```js
<script>
  (function(a,t,i){var e="MSEI";var s="Analytics";var o=e+"queue";a[o]=a[o]||[];var r=a[e]||function(n){var t={};t[s]={};function e(e){while(e.length){var r=e.pop();t[s][r]=function(e){return function(){a[o].push([e,n,arguments])}}(r)}}var r="track";var i="set";e([r+"Event",r+"View",r+"Action",i+"Property",i+"User","initialize","teardown"]);return t}(i.name);var n=i.name;if(!a[e]){a[n]=r[s];a[o].push(["new",n]);setTimeout(function(){var e="script";var r=t.createElement(e);r.async=1;r.src=i.src;var n=t.getElementsByTagName(e)[0];n.parentNode.insertBefore(r,n)},1)}else{a[n]=new r[s]}if(i.user){a[n].setUser(i.user)}if(i.props){for(var c in i.props){a[n].setProperty(c,i.props[c])}}a[n].initialize(i.cfg)})(window,document,{
    src:"https://download.pi.dynamics.com/sdk/web/msei-1.min.js",
    name:"EiJS",
    cfg:{
      ingestionKey:"YOUR-INGESTIONKEY",
      autoCapture:{
        view:true,
        click:true
      },
      userConsent: true
    }
  });
</script>
```

## <a name="visitor-data-storage-in-engagement-insights-capability"></a>Uloženie údajov o návštevníkoch s možnosťou získania prehľadov o interakcii

### <a name="cookies"></a>Súbory cookie

- _msei
    - Ukladá anonymné ID používateľa. Tento súbor cookie je nastavený v doméne zákazníka a jeho platnosť vyprší o 365 dní.

### <a name="local-storage"></a>Lokálny ukladací priestor

Funkcia prehľadov interakcií využíva aj kľúče (`localStorage`) na sledovanie necitlivých údajov. Tieto údaje sú úplne uložené v samotnom prehliadači a na vaše servery sa neprenáša žiadny prenos.

- *EISession.Id*
    - Ukladá informácie o prebiehajúcej relácii používateľa, napríklad ID relácie, kedy sa spustila a kedy končí.
- *EISession.Previous*
    - Ukladá adresu URL predtým navštívenej stránky v aktuálnej relácii.

Kľúče v miestnom úložisku neexspirujú automaticky, a budú obnovené pri nasledujúcej relácii súpravy SDK.

## <a name="deleting-cookies"></a>Odstraňovanie súborov cookies

Vaši zákazníci môžu kedykoľvek ručne odstrániť súbory cookie a kľúče miestneho úložiska prostredníctvom nastavení svojich prehliadačov.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
