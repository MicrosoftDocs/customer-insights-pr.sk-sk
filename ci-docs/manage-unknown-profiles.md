---
title: Spravujte neznáme profily pomocou Customer Insights
description: Pracujte s neznámymi zákazníckymi profilmi, ktoré sú vytvorené a spravované v Dynamics 365 Customer Insights.
ms.date: 09/14/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: andtapia
ms.author: andreatapia
manager: shellyha
ms.openlocfilehash: 0e12f64a22b93d117009fb8aee76d02a7583e699
ms.sourcegitcommit: 24627d53dcdf607baaab1cc3c299a3584c386173
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 11/15/2022
ms.locfileid: "9776840"
---
# <a name="manage-unknown-profiles-with-customer-insights"></a>Spravujte neznáme profily pomocou Customer Insights

Používatelia internetu sú často online neidentifikovaní alebo anonymní. Dokonca aj tí najvernejší zákazníci sa môžu zdať „neznámi“, ak nie sú prihlásení na rôznych zariadeniach. Pre mnohé značky sú známi alebo overení používatelia menšinou napriek rastúcim očakávaniam zákazníkov v súvislosti s personalizáciou. Vzhľadom na budúcnosť súborov cookie tretích strán je na dosiahnutie prispôsobených skúseností rozhodujúce spravovanie používateľských preferencií na základe údajov prvej strany.

Zapamätateľné prispôsobenie závisí od toho, ako dobre poznáte svojho zákazníka a Customer Insights vám v tom pomáha sledovaním všetkých vašich zákazníkov.  Na začiatku činnosť zákazníka nemusíte obmedzovať ani zastaviť používanie údajov zozbieraných. Customer Insights vám umožňuje priniesť svoje vlastné údaje na vytvorenie zákazníckeho profilu pre neznámych používateľov. Potom môžete tento profil použiť na ďalšie akcie aj napriek chýbajúcim kontaktným informáciám. Importujte údaje prvej strany zo zdrojov, ako sú webové, mobilné alebo CRM systémy, do Customer Insights, aby ste neustále obohacovali profily zákazníkov. Keď zjednotíte viac interakcií, [otočte *neznámy* zákazníka do a *známy* zákazníka](unknown-to-known.md).

## <a name="sample-scenario"></a>Vzorový scenár

Predpokladajme, že používateľ používa svoje mobilné zariadenie na prehliadanie vášho webu elektronického obchodu. Webová stránka priradí návštevníkovi „mobile_guest123“ ako jedinečný identifikátor a vy začnete zbierať behaviorálne aktivity na základe ich online aktivity. Napríklad, ktoré stránky navštívili, koľko času na týchto stránkach strávili alebo na ktoré odkazy klikli. Nepoznáte ich meno ani e-mailovú adresu, no tieto údaje môžu značkám poskytnúť zmysluplné informácie o tomto konkrétnom používateľovi. Na druhej strane môžete tieto štatistiky použiť pri ďalšej návšteve stránky používateľa. Dopytujte na Customer Insights pre „mobile_guest123“, aby ste získali zoznam segmentov používateľa, ako napríklad „organický“, „mobilní predobjednávkoví zákazníci“, „zákazníci s vysokou hodnotou“ atď., alebo získajte profil a vytvorte si prispôsobené webové zážitky. Údaje môžete tiež exportovať do akéhokoľvek aktivačného systému a urobiť to isté.

## <a name="prerequisites"></a>Požiadavky

- Vkladajte údaje prvej strany do Customer Insights
- Každá entita má jedinečné ID, ktoré je nastavené ako primárny kľúč
- Každá entita s primárnym kľúčom na personalizáciu je zjednotená
- Redakčný systém vášho webu môže využívať API (na personalizáciu webu na základe priamej komunikácie so Customer Insights)

Nasledujúca tabuľka zobrazuje zjednodušený príklad toho, ako sa dajú zachytiť webové udalosti s vysokou hodnotou.

|EventID|Časová pečiatka udalosti|ID používateľa|Primárny kľúč|EventName|
|--|--|--|--|--|
|1|09-15-2022 9:00:00|abc123|CookieID1|Pohľad na produkt|
|2|09-18-2022 10:05:00|abc123|CookieID1|Pohľad na produkt|
|3|09-18-2022 10:10:00|abc123|CookieID1|Pridať do košíka|
|4|09-21-2022 09:05:00|abc123|CookieID1|Pohľad na produkt|

## <a name="data-ingestion"></a>Prijímanie údajov

Ďalšie informácie o dostupných možnostiach prijímania údajov nájdete v časti [Prehľad zdrojov údajov](data-sources.md).

## <a name="data-unification"></a>Zjednotenie údajov

Viac informácií o zjednotení zákazníckych profilov nájdete na [Prehľad zjednotenia údajov](data-unification.md).

## <a name="get-insights"></a>Získať prehľady

[Obohatiť](enrichment-hub.md) vaše dáta, zostavte [Opatrenia](measures.md) a vytvorte [segmentov](segments.md) pre ďalšiu aktiváciu.

Môžete napríklad vytvoriť segmenty neznámych používateľov, ktorí si prezerali rovnaké produktové stránky, ale nikdy nedokončili platbu.

## <a name="activation"></a>Aktivácia

S vašimi údajmi v Customer Insights a vašimi štatistikami pripravenými na prácu môžete Customer Insights použiť na prispôsobenie:

1. Použi [OData API](apis.md) na získanie členstva v segmente alebo zákazníckeho profilu Ďalšie príklady nájdete v časti [Príklady dotazov OData pre rozhrania API Customer Insights](odata-examples.md).

1. [Export](export-destinations.md) vaše údaje do vašich aktivačných systémov.

Príklad: Neznámy používateľ viackrát navštívi webovú stránku a navštívi stránky produktov pre rôzne modely koženej obuvi. S týmito údajmi dostupnými v Customer Insights môžete neznámeho používateľa zahrnúť do segmentu ľudí, ktorí sa zaujímajú o kožené topánky. Tento segment použite na informovanie o prispôsobení tvorby webových stránok pre vracajúcich sa návštevníkov. Pri ďalšej návšteve stránka rozpozná neznámeho používateľa a môže mu ponúknuť 10% kupón na kožené topánky.

[!INCLUDE [footer-include](includes/footer-banner.md)]
