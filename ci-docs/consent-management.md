---
title: Použite súhlas zákazníka
description: Rešpektujte predvoľby súhlasu vašich zákazníkov v Customer Insights importovaním údajov o súhlase.
ms.date: 06/07/2022
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 77b09b6eb0a916e724542d503d96d19c5581aca1
ms.sourcegitcommit: 27c5473eecd851263e60b2b6c96f6c0a99d68acb
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 06/14/2022
ms.locfileid: "8947531"
---
# <a name="use-customer-consent"></a>Použite súhlas zákazníka

Nariadenia o ochrane údajov a súkromia poskytujú jednotlivcom právo riadiť, ako organizácia používa ich osobné údaje. Príkladmi takýchto nariadení sú všeobecné nariadenie o ochrane údajov v Európskej únii alebo kalifornský zákon o ochrane osobných údajov spotrebiteľov v Spojených štátoch. Tieto nariadenia umožňujú ľuďom odmietnuť zhromažďovanie, spracúvanie alebo zdieľanie ich osobných údajov s tretími stranami.  

Zákazníci sa môžu rozhodnúť odvolať alebo odoprieť svoj súhlas pre konkrétne formy kontaktu. Môžu tiež požiadať, aby ste ich odhlásili zo zhromažďovania, uchovávania, používania alebo predaja ich osobných údajov. Je dôležité, aby vaša organizácia rešpektovala súhlas a preferencie ochrany osobných údajov všetkých zákazníkov.  

Dynamics 365 Customer Insights vám pomôže splniť požiadavky vašich zákazníkov importovaním a uložením ich preferencií ako súčasť zjednotených zákazníckych profilov.

Ak sú údaje o súhlase uložené oddelene od vašich zákazníckych profilov, [pridajte údaje o svojom súhlase ako nové zdroj údajov](#import-and-unify-consent-data). Zdroj údajov, ktorý obsahuje údaje o súhlase, sa pridá do procesu zjednotenia údajov. Úspešné zjednotenie údajov o súhlase a zákazníckych profilov potom vedie k zjednoteným zákazníckym profilom, ktoré obsahujú informácie o súhlase. V prípade profilov zákazníkov, ktoré už obsahujú informácie o súhlase, prejdite priamo na stránku [používať údaje o súhlase](#use-consent-data) oddiele.

## <a name="prerequisites"></a>Požiadavky

Na zjednotenie údajov o súhlase s profilmi iných zákazníkov musia byť vo vašich zdrojových údajoch k dispozícii nasledujúce informácie:

- Alternatívny kľúč na mapovanie informácií o súhlase k užívateľským profilom v Customer Insights. Napríklad e-mailová adresa alebo telefónne číslo.
- Hodnota súhlasu na určenie stavu súhlasu zákazníka.

Zvážte pridanie nasledujúceho *voliteľné* informácie:

- Primárny kľúč na aktualizáciu stavu súhlasu, ak zákazník požaduje zmenu.
- Typ súhlasu, ak existuje viac ako jeden spôsob spracovania informácií o zákazníkovi.
- Dátum súhlasu alebo akýkoľvek iný typ údajov relevantných pre scenáre vášho súhlasu.

Príklad tabuľky jednoduchej databázy súhlasov s viacerými možnosťami súhlasu:

|ID súhlasu (primárny kľúč)   |E-mail (alternatívny kľúč)  |Možnosť súhlasu  |Hodnota súhlasu  |
|---------|---------|---------|---------|
|1    |  holly@contoso.com       |  Newsletter       |  Nepravdivé       |
|2    |  holly@contoso.com       |  Aktualizácie produktu       |  Pravdivé       |
|3    |  frank@contoso.com       |  Newsletter       | Pravdivé        |
|4    |  frank@contoso.com       |  Aktualizácie produktu       |  Nepravdivé       |

## <a name="import-and-unify-consent-data"></a>Importujte a zjednocujte údaje o súhlase

Údaje o súhlase môžete importovať rovnakým spôsobom, akým prijímate iné zdroje údajov do Customer Insights. Ďalšie informácie o podporovaných zdrojoch údajov a spôsobe ich importovania nájdete v časti [Prehľad zdrojov údajov](data-sources.md).

Ďalšie informácie o zjednotení zdrojov údajov nájdete v časti [Prehľad zjednotenia údajov](data-unification.md).

## <a name="use-consent-data"></a>Použite údaje o súhlase

Keď budú údaje o vašom súhlase súčasťou vašich zjednotených zákazníckych profilov, môžete ich použiť v Customer Insights. Vytvorte napríklad segment s pravidlom, ktoré zabezpečí, že budete rešpektovať preferencie ochrany súkromia a údajov vašich zákazníkov. Pravidlá podporujúce preferencie súhlasu sa používajú na vylúčenie používateľov zo segmentu na základe atribútov profilu. Pridanie pravidla do segmentu, ktorý vylučuje profily zákazníkov, ktorí neposkytli súhlas s kontaktovaním.

Podľa vzorovej tabuľky vyššie môže segment obsahovať toto pravidlo:`Consent option=Newsletter & Consent value=True`. Výsledkom tejto konfigurácie je segment, ktorý rešpektuje preferencie kontaktov na odosielanie bulletinu.

Viac informácií o stavebných segmentoch nájdete na [Vytvorte segmenty](segment-builder.md).

Po vytvorení segmentu môžete použiť jeden z mnohých [možnosti exportu](export-destinations.md) na použitie segmentu v iných aplikáciách.

## <a name="ensure-updated-consent-status"></a>Zabezpečte aktualizovaný stav súhlasu

Je dôležité aktualizovať stav súhlasu pre vašich zákazníkov. Plánované obnovenie v Customer Insights vždy importuje najnovší stav vašich zdrojov údajov. Tieto informácie sú následne spracované prostredníctvom zjednotenia údajov a výsledkom sú aktualizované profily zákazníkov. Tieto aktualizované profily sa potom používajú na obnovenie segmentov, aby ste sa uistili, že pracujete s najaktuálnejšími informáciami.

Inými slovami, uistite sa, že zdrojové údaje, ktoré sa importujú do Customer Insights, majú vždy najnovšie informácie.

Viac informácií nájdete v časti [Obnovte segmenty manuálne](segments.md#refresh-segments) alebo [nakonfigurovať plánovanú obnovu](system.md#schedule-tab).
