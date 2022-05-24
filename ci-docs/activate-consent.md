---
title: Aktivujte pravidlá súhlasu pre segmenty
description: Ak chcete prepojiť údaje o súhlase a aktivovať kontroly súhlasu v, postupujte podľa týchto krokov Dynamics 365 Customer Insights. Správca môže tiež zakázať kontroly súhlasu.
ms.date: 04/27/2022
ms.topic: how-to
author: anubhav-t
ms.author: antando
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: f82e3a4031fee8bcaa88575cbd68b37385a7fffb
ms.sourcegitcommit: 4ae316c856b8de0f08a4605f73e75a8c2cf51c4e
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 05/13/2022
ms.locfileid: "8755189"
---
# <a name="activate-consent-rules"></a>Aktivujte pravidlá súhlasu

The [Centrum súhlasu (ukážka)](consent-management/overview.md) vám pomôže zosúladiť údaje o súhlase z rôznych zdrojov. Použite jednotné *Súhlas* subjekt na použitie predvolených kontrol súhlasu. Po importovaní údajov o súhlase a konfigurácii pravidiel mapy sa *Súhlas* entita sa automaticky synchronizuje s Dynamics 365 Customer Insights.

## <a name="enable-consent-checks"></a>Povolenie kontrol súhlasu

S údajmi o súhlase importovanými do Centra súhlasu (ukážka) a nastavenými pravidlami môžete povoliť kontroly súhlasu. 

:::image type="content" source="consent-management/media/enable-consent-checks.png" alt-text="Karta Súhlas v nastaveniach Customer Insights s aktivovanými údajmi o súhlase.":::

1. V Customer Insights prejdite na stránku **Správca** > **Systém**.

1. Vyberte **Súhlas (ukážka)** tab.

1. V **Povoliť kontroly súhlasu** sekciu, nastavte prepínač na **zapnuté** pre všetky oblasti, ktoré chcete povoliť.

1. Vyberte **Povoliť prepísanie predvolených pravidiel súhlasu** začiarkavacie políčko na odstránenie predvolených kontrol súhlasu vynútených v konkrétnom segmente. 

1. V rozbaľovacej ponuke vyberte, kde chcete povoliť prepisy.     

1. V **Prepojiť súhlas s profilmi zákazníkov** vyberte atribút, ktorý sa používa ako identifikátor na prepojenie údajov o súhlase s údajmi zákazníkov. Pravdepodobne to bude telefónne číslo alebo e-mailová adresa. 

1. Vyberte **Uložiť** aby ste použili vaše nastavenia.

## <a name="disable-consent-checks"></a>Zakázať kontroly súhlasu

Ak chcete prestať používať údaje o súhlase v Customer Insights, správca musí zodpovedajúcim spôsobom aktualizovať nastavenia systému.

1. V Customer Insights prejdite na stránku **Správca** > **Systém**.

1. Vyberte **Súhlas (ukážka)** tab.

1. V **Povoliť kontroly súhlasu** sekciu, nastavte prepínač na **Vypnuté**.

> [!TIP]
> Ak chcete prestať používať funkciu správy súhlasu, pozrite si časť [Systémové nastavenia v Centre súhlasu (ukážka)](consent-management/system-settings.md).
