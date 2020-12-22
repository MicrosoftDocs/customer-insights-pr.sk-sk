---
title: Príjem údajov v reálnom čase a obmedzenia
description: Všeobecné informácie o možnostiach v reálnom čase v prehľadoch cieľovej skupiny.
ms.date: 10/27/2020
ms.reviewer: nikeller
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: b00a72e6a67e33c8e70ccc6139c5e62020f9d3e1
ms.sourcegitcommit: b50c754481d0af6d0cf4b550775d7b31d95846ef
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 12/06/2020
ms.locfileid: "4689194"
---
# <a name="real-time-data-ingestion-preview"></a>Prijímanie údajov v reálnom čase (ukážka)

Vďaka funkcii takmer reálneho času môžete v priebehu niekoľkých sekúnd vidieť najnovšie interakcie, ktoré zákazníci vykonali s vašimi produktmi alebo službami.

[Plánované obnovenia](system.md#schedule-tab) zahŕňajú veľké množstvo záznamov a niekoľko zložitých operácií. Najskôr sa údaje načítajú zo zdroja údajov. Ďalej sú údaje zjednotené a potom obohatené o ďalšie informácie. Každé spustenie tohto procesu môže trvať minúty až hodiny.

Funkcia v reálnom čase sprístupňuje údaje okamžite na spotrebu, až kým nasledujúce naplánované obnovenie nenačíta tieto údaje zo zdroja údajov.

Aktualizácie v reálnom čase majú čas uplynutia platnosti, po ktorom už neprepíšu hodnotu zo zdroja údajov:

- Aktualizácie profilu sa budú uchovávať 4 hodiny
- Aktivity sa budú uchovávať 30 dní

Tieto hodnoty sú parametre volaní API, ktoré môžete zmeniť. Ich cieľom je zabezpečiť, aby vaše zdrojové údaje zostali zdrojom pravdy. Ak chcete, aby boli aktualizácie v reálnom čase zahrnuté na dlhšie obdobie, musíte ich pridať do zdroja údajov, aby sa načítali počas nasledujúcej plánovanej obnovy.

## <a name="real-time-update-of-the-unified-customer-profile-fields"></a>Aktualizácia zjednotených polí profilu zákazníka v reálnom čase

Aktualizované profily sa v priebehu niekoľkých sekúnd zobrazia v zobrazení karty zákazníka alebo v akejkoľvek inej vizualizácii.

Pretože operácie v reálnom čase sa uskutočňujú po zjednotení údajov, vzťahujú sa iba na zjednotené profily zákazníkov. V dôsledku toho zmeny profilu v reálnom čase neaktualizujú opatrenia, členstvo v segmentoch ani obohatenia.

### <a name="limitations"></a>Obmedzenia

- Profily zákazníkov môžu byť aktualizované, ale nemôžu byť vytvorené alebo odstránené.
- Export aktualizácií v reálnom čase do externých systémov, napr. Power BI, momentálne nie je možný.

## <a name="real-time-creation-of-activities"></a>Tvorba aktivít v reálnom čase

Rozhranie API v reálnom čase vám umožňuje publikovať novú aktivitu z vášho zdrojového systému (individuálny zdrojový záznam) do zjednoteného profilu zákazníka. Nová aktivita bude dostupná ako jednotná aktivita v časovej osi tohto zjednoteného profilu zákazníka do niekoľkých sekúnd. Časovú os môžete vidieť v zobrazení karty zákazníka alebo v akejkoľvek inej integrácii časovej osi, ktorú ste nakonfigurovali.

> [!NOTE]
>
> - Aktivity sú nemenné. Po vytvorení sa nemenia.
> - V súčasnosti sa segmenty a miery na základe novej aktivity neaktualizujú.
> - Aktivity pridané iba prostredníctvom rozhrania API v reálnom čase nie sú súčasťou exportu a nezobrazia sa v PowerBI.

Existujú dva spôsoby pripojenia k API v reálnom čase:

- [nepriamo](#connect-via-the-dynamics-365-customer-insights-connector), pomocou [konektora Dynamics 365 Customer Insights](https://docs.microsoft.com/connectors/customerinsights/)
- [priamo](#connect-directly-to-the-real-time-api), s kódom

Oba spôsoby vyžadujú splnenie nasledujúcich predpokladov:

- Prostredie Customer Insights
- Zjednotené profily zákazníka
- Aktivity boli nakonfigurované a spustené
- Povolenia prispievateľa alebo správcu na overenie vášho účtu

## <a name="connect-via-the-dynamics-365-customer-insights-connector"></a>Pripojenie cez konektor Dynamics 365 Customer Insights

Rozhranie API v reálnom čase môže prijímať údaje z vyhradeného konektora Power Platform, konektora [Dynamics 365 Customer Insights](https://docs.microsoft.com/connectors/customerinsights/), bez potreby písania a nasadenia akéhokoľvek kódu.    
Konektor môže vykonávať rovnaké akcie v reálnom čase ako API. Pre prémiové konektory potrebujete platnú licenciu. Ďalšie informácie nájdete v časti [Najčastejšie otázky o licenciách k Power Apps a Power Automate](https://docs.microsoft.com/power-platform/admin/powerapps-flow-licensing-faq).

- Power Platform [Power Apps a/alebo Power Automate](https://docs.microsoft.com/connectors/)
- [Logické aplikácie platformy Azure](https://docs.microsoft.com/azure/connectors/apis-list)

Podrobnosti o vytváraní postupov nájdete v [dokumentácii Power Automate](https://docs.microsoft.com/power-automate/).

## <a name="connect-directly-to-the-real-time-api"></a>Priame pripojenie k API v reálnom čase

Funkcie v reálnom čase môžete využiť vytvorením vlastného kanála a priamym pripojením k rozhraniu API v reálnom čase.    
Aktivitu môžete uverejniť vo formáte zdrojového systému alebo vo formáte UnifiedActivity. Získajte formát pomocou volania rozhrania API na /api/instances/{instanceId}/manage/entities/UnifiedActivity.

Podrobnosti o tomto API vrátane parametrov a odpovedí nájdete v časti **EntityData** v [referenčnej príručke rozhraní API pre Customer Insights](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights). Ďalšie informácie nájdete v téme [Práca s rozhraniami API pre Customer Insights](apis.md).

## <a name="understand-your-real-time-usage-with-telemetry"></a>Získajte informácie o svojom využití v reálnom čase pomocou telemetrie

Získajte prehľad o objeme požiadaviek na API v reálnom čase a informácie o problémoch, s ktorými sa systém môže stretnúť. Môžete [pristupovať k telemetrii v reálnom čase](system.md#api-usage-tab) tak, že prejdete do časti **Správca** > **Systém** > **Použitie API**. V tabuľke **Operácie** obsahujú riadky pre operácie nad rozhraním API, ktoré používajú metódy v reálnom čase, tlačidlo na zobrazenie použitia API v reálnom čase. Tlačidlo je vizualizované symbolom ďalekohľadu. Výberom tohto tlačidla otvoríte bočnú tablu obsahujúcu podrobnosti o použití rozhrania API v reálnom čase v aktuálnom prostredí.

Použite selektor **Zoskupiť podľa** na výber, ako najlepšie prezentovať svoje interakcie v reálnom čase na časovej osi od posledných 24 hodín do posledných 30 dní. Údaje môžete zoskupiť podľa metódy API, kvalifikovaného názvu entity (prijatá entita), spôsobu vytvorenia (zdroj udalosti), výsledku (úspech alebo zlyhanie) alebo chybových kódov. Dáta sú k dispozícii ako graf histórie a ako tabuľka.
