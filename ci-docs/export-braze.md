---
title: Export segmentov do Braze (ukážka)
description: Zistite, ako nakonfigurovať pripojenie a exportovať do Braze.
ms.date: 06/29/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 314a61f82c4040a8dbd6dff1dd5d92e20464f82a
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 06/29/2022
ms.locfileid: "9082689"
---
# <a name="export-segments-to-braze-preview"></a>Export segmentov do Braze (ukážka)

Exportujte segmenty zjednotených zákazníckych profilov do Braze a používajte ich na marketingové aktivity.

## <a name="prerequisites"></a>Požiadavky

- A [Braze účet](https://www.braze.com/) a zodpovedajúce poverenia správcu.
- Existujúce [segmenty v Braze](https://www.braze.com/docs/user_guide/engagement_tools/segments/creating_a_segment/).
- [Konfigurované segmenty](segments.md) v Customer Insights.
- Zjednotené profily zákazníkov v exportovaných segmentoch obsahujú pole predstavujúce e-mailovú adresu a ID zákazníka Braze.

## <a name="known-limitations"></a>Známe obmedzenia

- Export do Braze je obmedzený na segmenty.
- Export až 1 milióna zákazníckych profilov do Braze môže trvať až 40 minút.
- Počet zákazníckych profilov, ktoré môžete exportovať do Braze, závisí a je obmedzený na vašej zmluve so spoločnosťou Braze.

## <a name="set-up-connection-to-braze"></a>Nastavte pripojenie k Braze

1. Prejdite do časti **Správca** > **Pripojenia**.

1. Vyberte **Pridať pripojenie** a vyberte si **Spájkovať** na konfiguráciu pripojenia.

1. Do poľa **Zobrazovaný názov** zadajte rozpoznateľný názov pripojenia. Zobrazovaný názov a typ spojenia, ktoré popisuje toto spojenie. Odporúčame zvoliť názov, ktorý vysvetľuje účel a cieľ tohto spojenia.

1. Vyberte používateľov, ktorí môžu používať toto pripojenie. Ak neurobíte nič, predvolená hodnota bude Správcovia. Viac informácií nájdete v časti [Umožnite prispievateľom použiť pripojenie na export](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Poskytnite svoje [Kľúč API na spájkovanie](https://www.braze.com/docs/api/basics/) pokračovať v prihlásení.

1. Vyberte **Súhlasím** na potvrdenie **Ochrany osobných údajov a dodržiavanie súladu s nariadeniami**.

1. Vyberte **Pripojte sa** na inicializáciu pripojenia k Braze.

1. Vyberte položku **Pridať samého seba ako používateľa exportu** a uveďte svoje poverenia pre Customer Insights.

1. Stlačte možnosť **Uložiť** a dokončite pripojenie.

## <a name="configure-an-export"></a>Nakonfigurujte export

Tento export môžete nakonfigurovať, ak máte prístup k pripojeniu tohto typu. Viac informácií nájdete na stránke [Na konfiguráciu exportu sú potrebné povolenia](export-destinations.md#set-up-a-new-export).

1. Prejdite na **Údaje** > **Exporty**.

1. Na vytvorenie nového exportu stlačte možnosť **Pridať cieľ**.

1. V **Pripojenie na export** vyberte spojenie zo sekcie Pájka. Ak túto sekciu nevidíte, nemáte k dispozícii žiadne pripojenia tohto typu.  

1. Pridaj **Zobraziť meno** pre váš export.

1. Pridajte identifikátor API segmentu Braze, do ktorého chcete exportovať **Identifikátor rozhrania API segmentu spájky** lúka. Identifikátor nájdete v detaile segmentu na platforme Braze.

1. V sekcii **Párovanie údajov** v poli **E-mail** vyberte pole, ktoré predstavuje e-mailovú adresu zákazníka. V **ID zákazníka** vyberte pole, ktoré predstavuje zákaznícke Braze ID. Je potrebné exportovať segmenty do Braze. Voliteľne môžete vybrať viac polí.

1. Vyberte **Uložiť**.

Uloženie exportu nespustí export okamžite.

Export prebieha s každým [plánovaným obnovením](system.md#schedule-tab). Môžete tiež [exportovať údaje na požiadanie](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Ochrana osobných údajov a dodržiavanie súladu s nariadeniami

Keď povolíte Dynamics 365 Customer Insights na prenos údajov do Braze povolíte prenos údajov mimo hranice súladu pre Dynamics 365 Customer Insights, vrátane potenciálne citlivých údajov, ako sú Osobné údaje. Spoločnosť Microsoft prenesie takéto údaje na váš pokyn, ale zodpovedáte za to, že spoločnosť Braze splní všetky vaše prípadné povinnosti týkajúce sa ochrany osobných údajov alebo zabezpečenia. Ďalšie informácie nájdete vo [vyhlásení o ochrane súkromia spoločnosti Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).

Váš správca služby Dynamics 365 Customer Insights môže túto funkciu kedykoľvek prestať používať odstránením tohto cieľového umiestnenia exportu.
