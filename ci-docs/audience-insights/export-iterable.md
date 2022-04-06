---
title: Exportujte údaje Customer Insights do Iterable
description: Zistite, ako nakonfigurovať pripojenie a exportovať do Iterable.
ms.date: 03/29/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 4de499fcc4a5a0dcc2dfd3bae02913c81a59647b
ms.sourcegitcommit: 5bd07f3a1288f003704acd576741cf6aedc1ac33
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 03/31/2022
ms.locfileid: "8524605"
---
# <a name="export-segment-lists-to-iterable-preview"></a>Exportovať zoznamy segmentov do Iterable (ukážka)

Exportujte segmenty zjednotených zákazníckych profilov do Iterable a použite ich na marketingové aktivity.

## <a name="prerequisites"></a>Požiadavky

-   Máte [Iterovateľný účet](https://iterable.com/) a zodpovedajúce poverenia správcu.
-   Máte [konfigurované segmenty](segments.md) v prehľadoch cieľových skupín.
-   Zjednotené profily zákazníkov v exportovaných segmentoch obsahujú pole predstavujúce e-mailovú adresu.

## <a name="known-limitations"></a>Známe obmedzenia

- Export do Iterable je obmedzený na segmenty.
- Export až 1 milióna zákazníckych profilov do Iterable môže trvať až 30 minút. 
- Počet zákazníckych profilov, ktoré môžete exportovať do Iterable, závisí a je obmedzený na vašej zmluve s Iterable.

## <a name="set-up-connection-to-iterable"></a>Nastavte pripojenie k Iterable

1. Prejdite do časti **Správca** > **Pripojenia**.

1. Vyberte **Pridať pripojenie** a vyberte si **Iterovateľné** na konfiguráciu pripojenia.

1. Do poľa **Zobrazovaný názov** zadajte rozpoznateľný názov pripojenia. Zobrazovaný názov a typ spojenia, ktoré popisuje toto spojenie. Odporúčame zvoliť názov, ktorý vysvetľuje účel a cieľ tohto spojenia.

1. Vyberte používateľov, ktorí môžu používať toto pripojenie. Ak neurobíte nič, predvolená hodnota bude Správcovia. Viac informácií nájdete v časti [Umožnite prispievateľom použiť pripojenie na export](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Poskytnite svoje [Iterovateľný kľúč API](https://support.iterable.com/hc/en-us/articles/360043464871) pokračovať v prihlásení. 

1. Vyberte **Súhlasím** na potvrdenie **Ochrany osobných údajov a dodržiavanie súladu s nariadeniami**.

1. Vyberte **Pripojte sa** na inicializáciu pripojenia k Iterable.

1. Vyberte položku **Pridať samého seba ako používateľa exportu** a uveďte svoje poverenia pre Customer Insights.

1. Stlačte možnosť **Uložiť** a dokončite pripojenie.

## <a name="configure-an-export"></a>Nakonfigurujte export

Tento export môžete nakonfigurovať, ak máte prístup k pripojeniu tohto typu. Viac informácií nájdete na stránke [Na konfiguráciu exportu sú potrebné povolenia](export-destinations.md#set-up-a-new-export).

1. Prejdite na **Údaje** > **Exporty**.

1. Na vytvorenie nového exportu stlačte možnosť **Pridať cieľ**.

1. V **Pripojenie na export** vyberte pripojenie zo sekcie Iterable. Ak nevidíte názov tejto sekcie, nemáte k dispozícii žiadne spojenia tohto typu.

3. V sekcii **Párovanie údajov** v poli **E-mail** vyberte pole, ktoré predstavuje e-mailovú adresu zákazníka. Je potrebné exportovať segmenty do Iterable. Zoznam vytvorený v Iterable dostane presne rovnaký názov ako váš segment v Dynamics 365 Customer Insights.

1. Vyberte **Uložiť**.

Uloženie exportu nespustí export okamžite.

Export prebieha s každým [plánovaným obnovením](system.md#schedule-tab). Môžete tiež [exportovať údaje na požiadanie](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Ochrana osobných údajov a dodržiavanie súladu s nariadeniami

Keď povolíte Dynamics 365 Customer Insights na prenos údajov do Iterable povolíte prenos údajov mimo hranice súladu pre Dynamics 365 Customer Insights, vrátane potenciálne citlivých údajov, ako sú Osobné údaje. Spoločnosť Microsoft prenesie takéto údaje na váš pokyn, ale vy ste zodpovední za zabezpečenie toho, že Iterable spĺňa všetky vaše povinnosti týkajúce sa ochrany osobných údajov alebo zabezpečenia. Ďalšie informácie nájdete vo [vyhlásení o ochrane súkromia spoločnosti Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).

Váš správca služby Dynamics 365 Customer Insights môže túto funkciu kedykoľvek prestať používať odstránením tohto cieľového umiestnenia exportu.
