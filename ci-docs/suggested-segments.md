---
title: Navrhované segmenty na základe meraní (ukážka)
description: Nechajte strojové učenie pomôcť vám nájsť nové a zaujímavé segmenty založené na atribútoch zákazníka.
ms.date: 10/15/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
manager: shellyha
searchScope:
- ci-segment-suggestions
- customerInsights
ms.openlocfilehash: e3f504827029afa12c65ec6f065a62606aaa823f
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 07/18/2022
ms.locfileid: "9170976"
---
# <a name="suggested-segments-based-on-measures-preview"></a>Navrhované segmenty na základe meraní (ukážka)

Objavte zaujímavé segmenty svojich zákazníkov pomocou modelu AI. Táto funkcia strojového učenia navrhuje segmenty na základe mier alebo atribútov zákazníka. Môže pomôcť zlepšiť vaše kľúčové ukazovatele výkonnosti (KPI) alebo lepšie pochopiť vplyv atribútov v kontexte iných atribútov.

> [!NOTE]
> Funkcia navrhovaných segmentov využíva automatizované prostriedky na vyhodnocovanie údajov a vytváranie predpovedí na základe týchto údajov. Preto je možné ho použiť ako metódu profilovania, keďže tento pojem je definovaný všeobecným nariadením o ochrane údajov (ďalej len „GDPR“). Vaše použitie tejto funkcie na spracovanie údajov môže podliehať GDPR alebo iným zákonom alebo predpisom. Ste zodpovední za zabezpečenie toho, že vaše používanie služby Dynamics 365 Customer Insights vrátane tejto funkcie bude v súlade so všetkými platnými zákonmi a nariadeniami vrátane zákonov týkajúcich sa ochrany súkromia, osobných údajov, biometrických údajov, ochrany údajov a dôvernosti komunikácií.

:::image type="content" source="media/suggested-segments.png" alt-text="Stránka s navrhovanými segmentmi, ktorá zobrazuje podrobnosti návrhu na bočnej table.":::

## <a name="suggested-segments-to-improve-your-kpis"></a>Navrhované segmenty na zlepšenie vašich KPI

Ak používate [vytvorené opatrenia](measures.md) aby ste pomohli sledovať svoje KPI, vytvorte segmenty na zobrazenie vplyvov na KPI. Tieto informácie môžete použiť na spustenie vysoko cielenej kampane.

Napríklad sledujete mieru s názvom *TotalSpendPerCustomer*. Ako firma by ste chceli, aby toto číslo rástlo. Výberom miery ako primárneho atribútu vyberte atribúty, ktorých vplyv chcete posúdiť. Povedzme *stupeň členstva*, *členské obdobie* a *povolanie*. Customer Insights potom môžu navrhnúť segment, ktorý vám povie, kto má na toto opatrenie najväčší vplyv. Napríklad *Účtovníci*, ktorí sú *zlatými* členmi a ktorí pracujú vo vašej firme *najmenej päť rokov* najviac ovplyvňujú *TotalSpendPerCustomer*. Pre každý návrh získate odhadovanú veľkosť segmentu. Tieto informácie môžete použiť na vytvorenie kampaní pre cieľové publikum.

## <a name="understand-what-influences-a-customer-attribute"></a>Pochopenie, čo ovplyvňuje atribút zákazníka

Namiesto miery môžete ako primárny atribút zvoliť atribút zákazníka. Na základe vášho výberu ovplyvňujúcich atribútov model AI vytvára sériu návrhov, ktoré ukazujú, ako vybrané atribúty ovplyvňujú primárny atribút.

Napríklad si vyberiete ako primárny atribút *Člen vernostného programu (áno/nie)*. *Funkčné obdobie*, *Povolanie* a *Počet žiadostí o podporu* sú nastavené ako ďalšie ovplyvňujúce atribúty. Model AI by mohol navrhnúť segmenty, ktoré naznačujú, že členmi odmien sú väčšinou IT profesionáli s funkčným obdobím dva roky. Ďalším návrhom by sa mohlo zdôrazniť, že účtovníci s funkčným obdobím nad jeden rok a menej ako troma žiadosťami o podporu sú členmi vernostného programu.

## <a name="artificial-intelligence-usage"></a>Použitie umelej inteligencie

Pomocou primárneho atribútu a ovplyvňujúcich atribútov navrhuje algoritmus rozhodovacieho stromu zaujímavé segmenty. Návrhy vychádzajú z pravidiel alebo vzorov, ktoré zachytil algoritmus AI. Ako návrhy sa zobrazia iba segmenty, ktoré sa výrazne líšia od priemernej populácie. Porovnanie s priemernou populáciou je založené na vybranej miere alebo primárnom atribúte.

### <a name="responsible-ai"></a>Zodpovedná AI

Pomocou navrhovaných segmentov vyberiete atribúty na vytvorenie nových segmentov a spracujete vybraté údaje. Pri výbere atribútov vrátane citlivých atribútov ako rasa, sexuálna orientácia alebo pohlavie musíte zabezpečiť, aby ste tieto údaje mohli a mali spracovávať. Ste zodpovední za dodržiavanie všetkých zákonov platných pre vašu organizáciu a za dodržiavanie zásad a ochrany osobných údajov vašej organizácie.

### <a name="different-results-for-primary-attributes-with-categorical-and-numeric-values"></a>Odlišné výsledky pre primárne atribúty s kategorickými a číselnými hodnotami

Návrhy segmentov sa líšia, ak ako primárny atribút vyberiete číselný atribút alebo kategorický atribút. Hodnoty v kategorickom atribúte obsahujú dve alebo viac kategórií alebo typov. Číselný atribút obsahuje kvantitatívne údaje a je s ním spojený zmysel pre meranie.

S číselným atribútom ako *ročný príjem* alebo *členské obdobie* ako primárnym atribútom systém navrhuje segmenty, ktoré majú vyššiu alebo nižšiu priemernú hodnotu číselného atribútu v porovnaní so všetkými zákazníkmi.

Kategorický atribút ako *spokojnosť zákazníkov* ako primárny atribút vedie k navrhovaným segmentom, ktoré majú vyššie alebo nižšie percento zákazníkov patriacich do konkrétnej kategórie v porovnaní s percentom všetkých zákazníkov patriacich do tej istej kategórie. Napríklad *spokojnosť zákazníkov* je vybraná ako primárny atribút a skladá sa z troch kategórií (*Nízka*, *Stredná* a *Vysoká*). Pre každú kategóriu budú navrhnuté segmenty, ktoré majú vyššie alebo nižšie percento zákazníkov patriacich do danej kategórie v porovnaní s podielom všetkých zákazníkov v rovnakej kategórii. Ak má 22 % všetkých zákazníkov *Vysokú* spokojnosť, potom len segmenty, ktoré majú vyšší alebo nižší podiel zákazníkov s *Vysokou* spokojnosťou v porovnaní s 22 % budú navrhnuté pre túto kategóriu. Podobne platí, že budú navrhnuté segmenty pre každú z ďalších kategórií (*Nízka* a *Stredná*), ak sú štatisticky významné.

> [!NOTE]
> V súčasnosti podporujeme iba primárne kategorické atribúty, ktoré majú až 10 kategórií. Ak chcete zobraziť návrhy segmentov na základe primárneho atribútu s viac ako 10 kategóriami, odporúčame vám zoskupiť niektoré kategórie, aby ste znížili počet kategórií na 10 alebo menej. Toto obmedzenie sa vzťahuje iba na primárne atribúty. Na ovplyvnenie kategorických atribútov v súčasnosti podporujeme maximálne 100 kategórií.

## <a name="generate-suggested-segments"></a>Generovanie navrhovaných segmentov

1. Ísť do **Segmenty** a vyberte **Návrhy (ukážka)** tab.

1. Vyberte **Nájdite nové návrhy** a vyberte si **Zlepšite mieru/metriku**. Vyberte **Štart**.

   :::image type="content" source="media/suggested-segments-measure.png" alt-text="Výber opatrenia na zlepšenie v navrhovaných segmentoch.":::

1. Vyberte atribút zákazníka alebo mieru ako primárny atribút a vyberte **Ďalšie**.

1. Vyberte ovplyvňujúce atribúty a vyberte **Bežať**.

   > [!TIP]
   > Výber viacerých ovplyvňujúcich atribútov zvyšuje šance na vyhodnotenie toho, ako ovplyvňujú primárny atribút. Nezahŕňajte atribúty, ktoré nemajú vplyv na primárny atribút. Napríklad ak sú všetci vaši zákazníci z konkrétnej krajiny, neuvádzajte atribút *krajina*, pretože to nebude mať žiadny vplyv na výstup.

V závislosti od počtu profilov zákazníkov a vybraných atribútov môže spracovanie vybraných atribútov trvať niekoľko minút.

## <a name="manage-suggested-segments"></a>Spravujte navrhované segmenty

Ísť do **Segmenty** a vyberte **Návrhy (ukážka)** tab. V **Návrhy segmentov založené na atribútoch** vyberte navrhovaný segment na zobrazenie dostupných akcií.

- **vyhliadka** navrhované detaily segmentov a hodnoty atribútov alebo pravidlá, ktoré sa naučil model AI.
- **Uložiť ako segment** návrh ako segment. Zobrazuje sa na **Všetky segmenty** kartu a môže byť [obnovené, upravené alebo odstránené](segments.md).
- **Upravte atribúty** a upravte nakonfigurované atribúty, ktoré nahradia aktuálne návrhy.
- **Obnoviť návrhy** na obnovenie návrhov pri zachovaní nakonfigurovaných atribútov.

## <a name="limitations"></a>Obmedzenia

1. Nesúlad odhadovanej veľkosti segmentu: Ak vyberiete primárny atribút, ktorý obsahuje prázdne hodnoty, môže to mať vplyv na odhadovanú veľkosť segmentu v návrhoch segmentov. Pri ukladaní takéhoto segmentu sa skutočná veľkosť segmentu môže líšiť od pôvodného odhadu.

2. Primárne atribúty boolovského typu nefungujú: V súčasnosti podporujeme ako primárny atribút iba reťazcové a číselné typy údajov.

3. Navrhované segmenty nie sú dostatočne odlišné: Nezabudnite, že vybrané atribúty a rozloženie hodnôt týchto atribútov ovplyvňuje výsledky. Môžete zmeniť svoje ovplyvňujúce atribúty alebo dokonca hlavný atribút, aby ste dosiahli rôzne výsledky.

[!INCLUDE [footer-include](includes/footer-banner.md)]