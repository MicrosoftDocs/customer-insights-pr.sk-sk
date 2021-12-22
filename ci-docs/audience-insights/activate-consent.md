---
title: Aktivujte pravidlá súhlasu pre segmenty
description: Ak chcete prepojiť údaje o súhlase a aktivovať kontroly súhlasu v štatistikách publika, postupujte podľa týchto krokov. Správca môže tiež zakázať kontroly súhlasu.
ms.date: 11/12/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: smithy7
ms.author: smithc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 552cb0739c4d17266dd028638df067f3384b738a
ms.sourcegitcommit: 48d799535fad84e8b63c80aef48b5c5e87628f58
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 12/03/2021
ms.locfileid: "7884093"
---
# <a name="activate-consent-rules"></a>Aktivujte pravidlá súhlasu

The [Centrum súhlasu (ukážka)](../consent-management/overview.md) vám pomôže zosúladiť údaje o súhlase z rôznych zdrojov. Použite jednotné *Súhlas* subjekt na použitie predvolených kontrol súhlasu. Po importovaní údajov o súhlase do Centra súhlasu a konfigurácii pravidiel pre údaje, *Súhlas* entita sa automaticky synchronizuje so štatistikami publika.

## <a name="enable-consent-checks"></a>Povolenie kontrol súhlasu

S údajmi o súhlase importovanými do Centra súhlasu (ukážka) a nastavenými pravidlami môžete povoliť kontroly súhlasu. 

:::image type="content" source="../consent-management/media/enable-consent-checks-audience-insights.png" alt-text="Karta Súhlas v nastaveniach štatistík publika s aktivovanými údajmi o súhlase.":::

1. V prehľadoch cieľových skupín prejdite na **Správca** > **Systém**.

1. Vyberte **Súhlas (ukážka)** tab.

1. V **Povoliť kontroly súhlasu** sekciu, nastavte prepínač na **zapnuté** pre všetky oblasti, ktoré chcete povoliť.

1. Vyberte **Povoliť prepísanie predvolených pravidiel súhlasu** začiarkavacie políčko na odstránenie predvolených kontrol súhlasu vynútených v konkrétnom segmente. 

1. V rozbaľovacej ponuke vyberte, kde chcete povoliť prepisy.     

1. V **Prepojiť súhlas s profilmi zákazníkov** vyberte atribút, ktorý sa používa ako identifikátor na prepojenie údajov o súhlase s údajmi zákazníkov. Pravdepodobne to bude telefónne číslo alebo e-mailová adresa. 

1. Vyberte **Uložiť** aby ste použili vaše nastavenia.

## <a name="disable-consent-checks"></a>Zakázať kontroly súhlasu

Ak chcete prestať používať údaje o súhlase v štatistikách publika, správca musí zodpovedajúcim spôsobom aktualizovať nastavenia systému.

1. V prehľadoch cieľových skupín prejdite na **Správca** > **Systém**.

1. Vyberte **Súhlas (ukážka)** tab.

1. V **Povoliť kontroly súhlasu** sekciu, nastavte prepínač na **Vypnuté**.

> [!TIP]
> Ak chcete prestať používať funkciu správy súhlasu, pozrite si časť [Systémové nastavenia v Centre súhlasu (ukážka)](../consent-management/system-settings.md).
