---
title: Spustite ukážku webovej súpravy SDK
description: Naučte sa, ako prispôsobiť a spustiť ukážku webovej súpravy SDK.
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 10/01/2021
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: a50a10db784ec7c1943c94e74000713309787e5c
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 02/16/2022
ms.locfileid: "8225350"
---
# <a name="run-the-web-sdk-sample-for-dynamics-365-customer-insights-engagement-insights-capability"></a>Spustite ukážku webovej SDK pre možnosť prehľadu interakcií Dynamics 365 Customer Insights

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Knižnica webovej súpravy na sledovanie interakcií je knižnica JavaScript so vzorovým kódom, ktorý môžete použiť na svojom webe.

## <a name="prerequisites"></a>Predpoklady

- Inštalácia [kódu Visual Studio](https://code.visualstudio.com/).
- [Nainštalujte si rozšírenie Live Server](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer) v kóde Visual Studio a oboznámte sa s tým, ako spustiť Live Server.
- Musíte mať [pracovný priestor s prehľadom interakcií](create-workspace.md).

## <a name="run-sample"></a>Spustiť vzorku

1. [Stiahnite si vzorku webového SDK](https://download.pi.dynamics.com/sdk/EngagementInsightsSamples/ei_websdk_sample.zip).

1. Rozbaľte skomprimovaný súbor `ei_websdk_sample.zip`.

1. Otvorte rozbalený priečinok v kóde Visual Studio.

1. Prejdite na portál prehľadu interakcií pre váš pracovný priestor. Vyberte **Správca** > **Pracovný priestor** a potom **Návod na inštaláciu**. Postupujte podľa prvej možnosti a vyberte **Kopírovať kód** na kopírovanie úryvku kódu JavaScript.

1. V súbore `ei_websdk_sample.html` vložte pod tento riadok úryvok kódu, ktorý ste práve skopírovali:

   - <-- VLOŽTE ÚRYVOK KÓDU JAVASCRIPT Z PORTÁLU PREHĽADY INTERAKCIÍ SEM POD TENTO RIADOK -->

1. Otvorte súbor `ei_websdk_sample.html` pomocou Live Server v kóde Visual Studio stlačením možnosti **Aktivovať** v stavovom riadku.

1. Pri otvorení stránky by sa mala automaticky odoslať udalosť prezerania. Kliknutím na ktorékoľvek z tlačidiel na stránke odošlete udalosti akcie. Tlačidlo **Sledovanie udalostí** tiež odošle vlastné udalosti. Stlačením tlačidla **Prejsť do služby Bing** sa pred prechodom na webovú stránku Bing odošle udalosť akcie.

1. Keď prechádzate do svojho pracovného priestoru, pozrite sa na plynúce udalosti. Tento pracovný priestor je priradený ku kľúču príjmu prijatému v kroku 4.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
