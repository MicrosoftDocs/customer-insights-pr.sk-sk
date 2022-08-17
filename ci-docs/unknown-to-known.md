---
title: Prispôsobte si svoje skúsenosti s údajmi o známych a neznámych používateľoch
description: Zahrňte informácie o predtým neznámych používateľoch, keď poznáte ich identitu.
ms.date: 07/07/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: 8e3477750d82f965dc2d62174fb35554d9447b7b
ms.sourcegitcommit: 52eca81c36e93d553140f5a37cf6013aaa42623a
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 08/03/2022
ms.locfileid: "9224314"
---
# <a name="personalize-your-experiences-with-data-about-known-and-unknown-users"></a>Prispôsobte si svoje skúsenosti s údajmi o známych a neznámych používateľoch

Správa údajov o zákazníkoch nie je novou výzvou, ale je čoraz ťažšia, keďže používatelia prechádzajú rôznymi digitálnymi kanálmi, ktoré značky ponúkajú. Používateľ, ktorý je známy (autentizovaný) v jednom kanáli, sa stáva neznámym (neautentizovaným) v inom, ak nie je prihlásený. Problémom často je, že neoverení (neznámi) používatelia nemajú spoločné ID. Dalo by sa použiť na priradenie zmysluplných atribútov profilov a generovanie zjednotených profilov zákazníkov. Customer Insights pomáha vyriešiť tento problém prijímaním údajov z metód sledovania vo vašich zdrojových systémoch. Konsolidácia neznámych a známych profilov poskytuje organizáciám úplný pohľad na aktuálne profily a ich historické transakcie, správanie a demografické údaje. Ide dokonca ešte o krok ďalej tým, že poskytuje rozlíšenie identity, ktoré vám umožňuje zjednotiť aktivitu zákazníkov naprieč viacerými kanálmi vrátane vášho webu, nákupu v obchode, vernostných programov atď.

## <a name="sample-scenario"></a>Vzorový scenár

Zamyslime sa nad kaviarenským reťazcom, ktorý má širokú zákaznícku základňu, ktorá nakupuje kávu a potraviny v obchodoch a objednáva produkty online. Online návštevníci často nie sú pri prehliadaní produktov overení, čo z nich robí „neznámych používateľov“. Pre reťazec kaviarní je ťažké poskytovať personalizované ponuky a skúsenosti, ak sú používatelia neznámi. Na druhej strane sa zákazníci môžu prihlásiť do svojho účtu a stať sa „známymi používateľmi“ spoločnosti tým, že sa zapoja do vernostného systému, čo zase umožňuje personalizovanejšie zážitky. Customer Insights môže pomôcť kaviarenskému reťazcu získať informácie o známych a predtým neznámych používateľoch.

Pomocou Customer Insights môže spoločnosť kombinovať profily zákazníkov s údajmi o aktivitách z neoverených (neznámych) relácií po tom, ako sa používateľ prihlási a stane sa známym. Kávový reťazec môže priniesť údaje z iných zdrojov údajov pomocou vstavaných konektorov do Customer Insights na zlúčenie identít pre zákazníkov z rôznych kanálov.

## <a name="prerequisites"></a>Požiadavky

- Webové údaje sa zhromažďujú a obsahujú „identifikátory návštevníkov“ pre všetkých návštevníkov.
- Webové údaje obsahujú „overené ID používateľov“ pre prihlásených návštevníkov. Tieto ID sú prepojené s vernostným systémom.
- Údaje o udalostiach vysokej hodnoty, ako sú „Zobrazenie produktu“ a „Pokladňa“, sú definované a zahrnuté v zdrojových údajoch spolu s časovou pečiatkou udalosti a ID udalosti.

Nasledujúca tabuľka zobrazuje zjednodušený príklad, ako by sa mohli zachytiť webové udalosti s vysokou hodnotou.

|EventID|Časová pečiatka udalosti|ID používateľa|LoyaltyID|EventName|
|--|--|--|--|--|
|1|07-23-2022 10:00:00|abc123|--|Pohľad na produkt|
|2|07-23-2022 10:05:00|abc123|707|Vernostné prihlásenie|
|3|07-23-2022 10:10:00|abc123|707|Pokladňa|
|4|07-23-2022 10:20:00|xyz789|--|Pohľad na produkt|

## <a name="data-ingestion"></a>Prijímanie údajov

Údaje o zákazníkoch môžu pochádzať z vašej webovej lokality ako údaje o udalostiach a môžu byť uložené vo vašich vlastných interných službách alebo službách analýzy údajov tretích strán. Webové údaje obsahujú známych a neznámych používateľov, ak má webová lokalita overovací tok, ktorý sa integruje s overovacou službou. Napríklad systém elektronického obchodu, ktorý vyžaduje, aby používatelia poskytli svoje úplné údaje na dokončenie nákupnej transakcie. Alebo vernostný systém, ktorý vyžaduje autentifikáciu na potvrdenie platného príjemcu zliav.

Údaje udalostí v našom príklade vyššie obsahujú odlišné ID profilu známych a neznámych používateľov. V prípade 1 a 4 sú používatelia neznámi, zatiaľ čo v prípade 2 a 3 sa používateľ s ID abc123 zaregistruje do vernostného programu.

:::image type="content" source="media/website-data-source.png" alt-text="Zdroje údajov vrátane webovej stránky Contoso.":::

Ďalšie informácie o dostupných možnostiach prijímania údajov nájdete v časti [Prehľad zdrojov údajov](data-sources.md).

## <a name="data-unification"></a>Zjednotenie údajov

Konvergovanie neznámych identít so známymi identitami pomáha umožniť personalizáciu založenú na správaní používateľov bez ohľadu na stav ich profilu (známy alebo neznámy). Personalizovaný obsah pre všetkých používateľov pomáha zákazníkom rýchlo sa dostať k najrelevantnejším produktom alebo službám, o ktoré majú v danej chvíli záujem.

Keďže niektorí používatelia v našich údajoch sú známi, môžeme použiť Customer Insights na spojenie týchto údajov s profilom používateľa. Viac informácií o zjednotení zákazníckych profilov nájdete na [Prehľad zjednotenia údajov](data-unification.md).

1. Vyberte zdrojové polia z entity webových údajov. Použite údaje profilu, ktoré sú uložené vo vašich webových údajoch, a vyberte polia, ktoré predstavujú ID s demografickými údajmi.

   :::image type="content" source="media/website-source-fields.png" alt-text="Zdrojové polia pre web zdroj údajov.":::

1. Pridajte pravidlá na zlúčenie duplicitných záznamov. Pre webové údaje vyberte najviac vyplnené údaje.

1. Nakonfigurujte pravidlá a podmienky zápasu. Údaje udalostí webových profilov v tomto príklade sa budú zhodovať na ID s profilmi z iných zdrojov údajov, ktoré obsahujú informácie o zákazníkoch. Nastavte pravidlá presnej zhody pre ID ako samostatné pravidlá pre každú z ostatných entít profilu, ktoré majú zodpovedajúci primárny kľúč alebo zhodu ID. V tomto príklade sú údaje profilu webovej udalosti použité ako posledná zodpovedajúca entita, takže ostatné údaje profilu sa kombinujú ako prvé.
   1. Nekontrolujem **Zahrňte všetky záznamy** vytvára jednotné profily pre známych používateľov a zahŕňa ich zodpovedajúce neznáme ID používateľov. Je to užitočné v scenároch, keď máte záujem o zobrazenie minulých behaviorálnych aktivít známych používateľov, keď boli ešte neznámi.
   1. Kontrola **Zahrnúť všetky záznamy** vytvára samostatné profilové záznamy pre neznámych používateľov. Neznámi používatelia získajú jedinečné ID zákazníka. V budúcnosti, keď je známy profil priradený k údajom profilu webových udalostí, potom je možné zobraziť cestu nového známeho používateľa a použiť ju na prispôsobenie na základe minulých neznámych údajov o správaní.

:::image type="content" source="media/website-match-rule.png" alt-text="Pravidlo zhody pre webovú entitu zdroj údajov.":::

## <a name="get-insights"></a>Získať prehľady

Ak sa vytvoria profily zákazníkov pre neznámych a známych používateľov, môžu sa použiť údaje o udalostiach na webe s vysokou hodnotou [činnosti](activities.md). Tieto aktivity možno použiť na vytvorenie ďalších prehľadov. Napríklad zákazníci, ktorí navštívili webovú stránku pred šiestimi mesiacmi (keď boli ešte neznámi) alebo zákazníci, ktorí nemajú vernostné ID, nikdy nedokončili platbu.

:::image type="content" source="media/website-known-unknown.png" alt-text="Snímka obrazovky zákazníckej stránky so známymi a neznámymi zákazníkmi.":::

[Obohatiť](enrichment-hub.md) vaše dáta, zostavte [Opatrenia](measures.md) a vytvorte [segmentov](segments.md) pre ďalšiu aktiváciu.

Môžete napríklad vytvoriť segmenty známych používateľov, ktorí si prezerali niektoré produkty, ale nikdy nedokončili platbu.

Ďalšie informácie nájdete v časti [Prehľad segmentov](segments.md).

## <a name="activate-insights"></a>Aktivujte prehľady

Existuje niekoľko spôsobov, ako exportovať údaje a podniknúť kroky na základe základných štatistík.

Ďalšie informácie nájdete v časti [Prehľad exportov](export-destinations.md).
