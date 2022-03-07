---
title: Spustenie ukážky iOS SDK
description: Ukážkový projekt, kde sa dozviete viac o súprave iOS SDK
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 06/23/2021
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: bbe4ba648952a8081af4c8f2610276809fa5efeb
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 02/16/2022
ms.locfileid: "8232861"
---
# <a name="run-the-ios-sdk-sample"></a>Spustenie ukážky iOS SDK

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Tento ukážkový projekt pre iOS vám pomôže pochopiť, ako SDK funguje v aplikácii. Nemusíte si zapisovať žiadne kódy. Stačí pridať kľúč prijatia a okamžite môžete vo vašom pracovnom priestore vidieť udalosti.

## <a name="prerequisites"></a>Predpoklady

- [Verzia Xcode 9+](https://developer.apple.com/xcode/downloads/)
- [Kľúč prijatia](get-started-ios.md)

## <a name="download-the-ios-sdk-sample"></a>Stiahnuť ukážku súpravy iOS SDK

1. [Stiahnite si ukážku prehľadov interakcií súpravy iOS SDK](https://download.pi.dynamics.com/sdk/EI-SDKs/ei-ios-sample.zip).
1. Rozbaľte skomprimovaný súbor `ei-ios-sample.zip`.
1. Otvorte ukážkový projekt aplikácie v Xcode.
1. V súbore `EIConfig.plist` nahraďte reťazec `“YOUR-INGESTION-KEY”` v poli `ingestionKey` kľúčom prijatia vášho pracovného priestoru z prehľadov interakcií v sekcii **Správca** > **Pracovný priestor** > **Návod na inštaláciu**.
1. Ak chcete spustiť ukážkový projekt, vyberte tlačidlo **Spustiť**.
1. Zobrazte si udalosti vo svojom pracovnom priestore.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
