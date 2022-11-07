---
title: Export segmentov do Braze (ukážka)
description: Zistite, ako nakonfigurovať pripojenie a exportovať do Braze.
ms.date: 10/06/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: a3967008ec166cb6f099659b0791f1318126c0da
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 10/27/2022
ms.locfileid: "9725235"
---
# <a name="export-segments-to-braze-preview"></a>Export segmentov do Braze (ukážka)

Exportujte segmenty zjednotených zákazníckych profilov do Braze a používajte ich na marketingové aktivity.

## <a name="prerequisites"></a>Požiadavky

- A [Braze účet](https://www.braze.com/) a zodpovedajúce poverenia správcu.
- A [Kľúč API na spájkovanie](https://www.braze.com/docs/api/basics/)
- Váš [Braze REST Endpoint](https://www.braze.com/docs/api/basics/#api-definitions) 
- [Konfigurované segmenty](segments.md) v Customer Insights.
- Zjednotené profily zákazníkov v exportovaných segmentoch obsahujú pole predstavujúce e-mailovú adresu a ID zákazníka Braze.

## <a name="known-limitations"></a>Známe obmedzenia

- Súkromný odkaz v kombinácii s Prineste si vlastný úložný priestor (BYOS) nie je podporovaný.
- Až 1 milión zákazníckych profilov na Braze, ktorých dokončenie môže trvať až 40 minút. Počet zákazníckych profilov, ktoré môžete exportovať do Braze, závisí od vašej zmluvy so spoločnosťou Braze.
- Iba segmenty.
- Azure Private Link nie je podporovaný pre export Braze.

## <a name="set-up-connection-to-braze"></a>Nastavte pripojenie k Braze

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Prejdite do časti **Správca** > **Pripojenia**.

1. Vyberte **Pridať pripojenie** a vyberte si **Spájkovať**.

1. Do poľa **Zobrazovaný názov** zadajte rozpoznateľný názov pripojenia. Zobrazovaný názov a typ spojenia, ktoré popisuje toto spojenie. Odporúčame zvoliť názov, ktorý vysvetľuje účel a cieľ tohto spojenia.

1. Vyberte používateľov, ktorí môžu používať toto pripojenie. Predvolene sú to iba správcovia. Viac informácií nájdete v časti [Umožnite prispievateľom použiť pripojenie na export](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Ak chcete pokračovať v prihlásení, poskytnite svoj kľúč rozhrania Braze API.

1. Skontrolujte [ochrana osobných údajov a dodržiavanie predpisov](connections.md#data-privacy-and-compliance) a vyberte **Súhlasím**.

1. Vyberte **Pripojte sa** na inicializáciu pripojenia.

1. Vyberte položku **Pridať samého seba ako používateľa exportu** a uveďte svoje poverenia pre Customer Insights.

1. Stlačte možnosť **Uložiť** a dokončite pripojenie.

## <a name="configure-an-export"></a>Nakonfigurujte export

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Prejdite na **Údaje** > **Exporty**.

1. Vyberte **Pridať export**.

1. V **Pripojenie na export** vyberte spojenie zo sekcie Pájka. Ak nie je k dispozícii pripojenie, kontaktujte správcu.

1. Zadajte svoj REST Endpoint do **Meno hosťa** pole v nasledujúcom formáte:`rest.iad-03.braze.com`.

1. Zadajte názov exportu.

1. V sekcii **Párovanie údajov** v poli **E-mail** vyberte pole, ktoré predstavuje e-mailovú adresu zákazníka. V **ID zákazníka** vyberte pole, ktoré predstavuje zákaznícke Braze ID. Segmenty v Braze sa vytvoria s rovnakým názvom segmentu ako v Dynamics 365 Customer Insights. Môžete si vybrať viac voliteľných polí na porovnávanie údajov.

1. Vyberte entity alebo segmenty, ktoré chcete exportovať.

1. Vyberte **Uložiť**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
