---
title: Export segmentov do Campaign Monitor (verzia Preview)
description: Zistite ako nakonfigurovať pripojenie a realizovať exportovanie do Campaign Monitor.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 82303c7bcb269ee68419c9639ee743e13451f273
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 10/27/2022
ms.locfileid: "9724703"
---
# <a name="export-segments-to-campaign-monitor-preview"></a>Export segmentov do Campaign Monitor (verzia Preview)

Exportujte segmenty zjednotených profilov zákazníkov do Campaign Monitor a použite ich na marketingové aktivity.

## <a name="prerequisites"></a>Požiadavky

- A [Účet Monitor kampane](https://www.campaignmonitor.com/) a zodpovedajúce poverenia správcu.
- A [ID zoznamu monitora kampane](https://www.campaignmonitor.com/api/getting-started/#your-list-id).
- A [Vygenerovaný kľúč API](https://www.campaignmonitor.com/api/getting-started/) od **Nastavenia účtu** v Campaign Monitor, aby ste získali ID zoznamu API.
- [Konfigurované segmenty](segments.md) v Customer Insights.
- Zjednotené profily zákazníkov v exportovaných segmentoch obsahujú pole predstavujúce e-mailovú adresu.

## <a name="known-limitations"></a>Známe obmedzenia

- Súkromný odkaz v kombinácii s Prineste si vlastný úložný priestor (BYOS) nie je podporovaný.
- Až 1 milión zákazníckych profilov na export do Campaign Monitor, ktorého dokončenie môže trvať až 20 minút. Počet zákazníckych profilov, ktoré môžete exportovať do Campaign Monitor, závisí od vašej zmluvy s Campaign Monitor.
- Iba segmenty.

## <a name="set-up-connection-to-campaign-monitor"></a>Nastavenie pripojenia k Campaign Monitor

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Prejdite do časti **Správca** > **Pripojenia**.

1. Vyberte **Pridať pripojenie** a vyberte si **Monitor kampane**.

1. Do poľa **Zobrazovaný názov** zadajte rozpoznateľný názov pripojenia. Zobrazovaný názov a typ spojenia, ktoré popisuje toto spojenie. Odporúčame zvoliť názov, ktorý vysvetľuje účel a cieľ tohto spojenia.

1. Vyberte používateľov, ktorí môžu používať toto pripojenie. Predvolene sú to iba správcovia. Viac informácií nájdete v časti [Umožnite prispievateľom použiť pripojenie na export](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Skontrolujte [ochrana osobných údajov a dodržiavanie predpisov](connections.md#data-privacy-and-compliance) a vyberte **Súhlasím**.

1. Stlačte možnosť **Pripojiť** na inicializáciu pripojenia k Campaign Monitor.

1. Stlačte možnosť **Overenie pomocou služby Campaign Monitor** a zadajte svoje poverenia správcu pre Campaign Monitor.

1. Vyberte položku **Pridať samého seba ako používateľa exportu** a uveďte svoje poverenia pre Customer Insights.

1. Stlačte možnosť **Uložiť** a dokončite pripojenie.

## <a name="configure-an-export"></a>Nakonfigurujte export

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Prejdite na **Údaje** > **Exporty**.

1. Na vytvorenie nového exportu stlačte možnosť **Pridať export**.

1. V poli **Pripojenie na export** vyberte pripojenie v časti Campaign Monitor. Ak nie je k dispozícii pripojenie, kontaktujte správcu.

1. Zadajte názov exportu.

1. Zadajte svoje **ID zoznamu monitora kampane**.

1. V sekcii **Párovanie údajov** v poli **E-mail** vyberte pole, ktoré predstavuje e-mailovú adresu zákazníka. Je potrebné exportovať segmenty do Campaign Monitor.

1. Vyberte segmenty, ktoré chcete exportovať.

1. Vyberte **Uložiť**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
