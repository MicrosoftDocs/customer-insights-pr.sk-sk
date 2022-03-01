---
title: Spustite ukážku webovej súpravy SDK
description: Naučte sa, ako prispôsobiť a spustiť ukážku webovej súpravy SDK.
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 10/30/2020
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 97e50a51231bcf05f3e381397f0cf41e49afc10e3c3674d7c709c8f521979e12
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036622"
---
# <a name="run-the-web-sdk-sample-for-dynamics-365-customer-insights-engagement-insights-capability"></a>Spustite ukážku webovej SDK pre možnosť prehľadu interakcií Dynamics 365 Customer Insights

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Knižnica webovej súpravy na sledovanie interakcií je knižnica JavaScript so vzorovým kódom, ktorý môžete použiť na svojom webe.

## <a name="prerequisites"></a>Predpoklady

- Inštalácia [kódu Visual Studio](https://code.visualstudio.com/).
- [Nainštalujte si rozšírenie Live Server](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer) v kóde Visual Studio a oboznámte sa s tým, ako spustiť Live Server.
- Musíte mať [kľúč prijatia](instrument-website.md).

## <a name="run-sample"></a>Spustiť vzorku

1. [Stiahnite si vzorku webového SDK](https://download.pi.dynamics.com/sdk/EngagementInsightsSamples/ei_websdk_sample.zip).

1. Rozbaľte skomprimovaný súbor `ei_websdk_sample.zip`.

1. Otvorte rozbalený priečinok v kóde Visual Studio.

1. V súbore `ei_websdk_sample.html` nahraďte reťazec „INGESTION_KEY“ kľúčom na príjem z portálu schopností prehľadu interakcií a reťazec „NAME“ globálnym názvom, v ktorom chcete vytvoriť inštanciu súpravy SDK. Uistite sa, že ste nahradili všetky výskyty.

1. Otvorte súbor `ei_websdk_sample.html` pomocou Live Server v kóde Visual Studio stlačením možnosti **Aktivovať** v stavovom riadku.

1. Pri otvorení stránky by sa mala automaticky odoslať udalosť prezerania. Kliknutím na ktorékoľvek z tlačidiel na stránke odošlete udalosti akcie. Tlačidlo **Sledovanie udalostí** tiež odošle vlastné udalosti. Stlačením tlačidla **Prejsť do služby Bing** sa pred prechodom na webovú stránku Bing odošle udalosť akcie.

1. Keď prechádzate do svojho pracovného priestoru, pozrite sa na plynúce udalosti. Tento pracovný priestor je priradený ku kľúču príjmu prijatému v kroku 4.


[!INCLUDE[footer-include](../includes/footer-banner.md)]