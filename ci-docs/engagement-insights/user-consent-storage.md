---
title: Spravujte súbory cookie a súhlas používateľa s ukladaním údajov používateľa
description: Zistite, ako sa súbory cookie a súhlas používateľa používajú na identifikáciu návštevníkov webových stránok.
author: mochimochi016
ms.reviewer: mhart
ms.author: jefhar
ms.date: 10/30/2020
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 7b3195a92c969ab36e5b43f4c2e4221ff477a0a8958838e1256528f58fe13dce
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036757"
---
# <a name="manage-cookies-and-user-consent"></a>Spravovanie súborov cookie súhlasov používateľa

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Funkcia prehľadu interakcií Dynamics 365 Customer Insights využíva súbory cookie a miestne úložisko (`localStorage`) na identifikáciu návštevníkov webových stránok.

Súbory cookie sú malé súbory, ktoré ukladajú informácie o interakciách používateľa s webovou stránkou. Sú uložené vo webových prehliadačoch. Keď používatelia navštívia webovú stránku, pre ktorú majú vaši používatelia uložené súbory cookie, prehľadávač odošle tieto informácie na server, ktorý vráti informácie, ktoré sú pre používateľa jedinečné. Toto je technológia, ktorá umožňuje napríklad nákupnému košíku online uchovávať vybrané položky v ňom, aj keď sa používateľ dostane mimo webovú stránku.

## <a name="user-consent"></a>Súhlas používateľa

[Všeobecné nariadenie o ochrane údajov (GDPR)](/dynamics365/get-started/gdpr/) je nariadenie Európskej únie (EÚ), ktoré nariaďuje, ako by organizácie mali nakladať so súkromím a bezpečnosťou svojich používateľov. Súbory cookie často ukladajú alebo zhromažďujú „osobné údaje“, napríklad online identifikátor, na ktorý sa vzťahuje nariadenie GDPR. Ak váš podnik zamestnáva alebo predáva tovary či služby dotknutým osobám v EÚ, GDPR sa vás týka. [Prečítajte si viac informácií o tom, ako vám spoločnosť Microsoft môže pomôcť dosiahnuť súlad s nariadením GDPR](https://www.microsoft.com/trust-center/privacy/gdpr-faqs).

Ak chcete povoliť súhrnným prehľadom interakcií, aby mohli ukladať súbory cookie alebo iné citlivé informácie, musíte určiť, či s tým vaši používatelia súhlasili. K tomu dochádza pri inicializácii SDK.

Ak naznačíte, že neexistuje súhlas používateľa, súprava SDK nebude ukladať žiadne údaje a nebude odosielať udalosti, ktoré možno použiť na sledovanie správania používateľov. Všetky predtým uložené údaje budú z prehliadača odstránené.

Ak nie je zadaná žiadna hodnota súhlasu používateľa, SDK bude predpokladať, že používateľ vyjadril súhlas. To znamená, že ak (ako náš zákazník) nezadáte hodnotu pre súhlas používateľa v súprave SDK, údaje sa zhromaždia. Ak však určíte, že hodnota pre súhlas používateľa musí byť „true“, údaje sa nebudú zhromažďovať, ak používateľ odmietne alebo neposkytne výslovný súhlas.

## <a name="visitor-data-storage-in-engagement-insights-capability"></a>Uloženie údajov o návštevníkoch s možnosťou získania prehľadov o interakcii

### <a name="cookies"></a>Súbory cookie

- _msei
    - Ukladá anonymné ID používateľa. Tento súbor cookie je nastavený v doméne zákazníka a jeho platnosť vyprší o 365 dní.

### <a name="local-storage"></a>Lokálny ukladací priestor

Schopnosť prehľadu zapojenia tiež využíva miestne úložisko (`localStorage`) na sledovanie necitlivých údajov. Tieto údaje sú úplne uložené v samotnom prehliadači a na vaše servery sa neprenáša žiadny prenos.

- *EISession.Id* 
    - Ukladá informácie o prebiehajúcej relácii používateľa, napríklad ID relácie, kedy sa spustila a kedy končí.
- *EISession.Previous*
    - Ukladá adresu URL predtým navštívenej stránky v aktuálnej relácii.
    
Platnosť kľúčov v miestnom úložisku nevyprší automaticky. Obnoví ich SDK počas nasledujúcej relácie.

## <a name="deleting-cookies"></a>Odstraňovanie súborov cookies

Vaši zákazníci môžu kedykoľvek ručne odstrániť súbory cookie a kľúče miestneho úložiska prostredníctvom nastavení svojich prehliadačov.


[!INCLUDE[footer-include](../includes/footer-banner.md)]