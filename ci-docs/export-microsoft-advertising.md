---
title: Export segmentov do služby Microsoft Advertising (verzia Preview)
description: Zistite ako nakonfigurovať pripojenie a realizovať exportovanie do Microsoft Advertising.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: ca37159ec6473ad5c331a0ce1aa8424d277529ff
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 06/29/2022
ms.locfileid: "9082815"
---
# <a name="export-segments-to-microsoft-advertising-preview"></a>Export segmentov do služby Microsoft Advertising (verzia Preview)

Exportujte segmenty Customer Insights do služby Microsoft Advertising a vytvorte cieľovú skupinu súladu so zákazníkmi. Použite tieto cieľové skupiny pre svoje reklamné kampane.

## <a name="prerequisites"></a>Predpoklady

-   [Účet Microsoft Advertising](https://ads.microsoft.com/) a zodpovedajúce poverenia správcu.
-   Prijali ste podmienky používania súladu so zákazníkmi. 
-   [Konfigurované segmenty](segments.md) v Customer Insights.
-   Zjednotené profily zákazníkov v exportovaných segmentoch obsahujú pole s e-mailovou adresou.

## <a name="known-limitations"></a>Známe obmedzenia

- Do Microsoft Advertising môžete exportovať až 500 000 profilov zákazníkov.
- Exportovanie do Microsoft Advertising je obmedzené na segmenty.
- Export až 500 000 profilov zákazníkov do Microsoft Advertising môže trvať až 10 minút. 


## <a name="set-up-the-connection-to-microsoft-advertising"></a>Nastavenie pripojenia do Microsoft Advertising

1. Prejdite do časti **Správca** > **Pripojenia**.

1. Vyberte **Pridať pripojenie** a výberom možnosti **Microsoft Advertising** nakonfigurujte pripojenie.

1. Do poľa **Zobrazovaný názov** zadajte rozpoznateľný názov pripojenia. Zobrazovaný názov a typ spojenia, ktoré popisuje toto spojenie. Odporúčame zvoliť názov, ktorý vysvetľuje účel a cieľ tohto spojenia.

1. Vyberte používateľov, ktorí môžu používať toto pripojenie. Predvolená hodnota je správcovia. Viac informácií nájdete v časti [Umožnite prispievateľom použiť pripojenie na export](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Vyberte **Súhlasím** na potvrdenie **Ochrany osobných údajov a dodržiavanie súladu s nariadeniami**.

1. Stlačte možnosť **Pripojiť** na inicializáciu pripojenia k Microsoft Advertising.

1. Stlačte možnosť **Overenie pomocou služby Microsoft Advertising** a zadajte svoje poverenia správcu pre Microsoft Advertising.

1. Vyberte položku **Pridať samého seba ako používateľa exportu** a uveďte svoje poverenia pre Customer Insights.

1. Stlačte možnosť **Uložiť** a dokončite pripojenie.

## <a name="configure-an-export"></a>Nakonfigurujte export

Tento export môžete nakonfigurovať, ak máte prístup k pripojeniu tohto typu. Viac informácií nájdete na stránke [Na konfiguráciu exportu sú potrebné povolenia](export-destinations.md#set-up-a-new-export).

1. Prejdite na **Údaje** > **Exporty**.

1. Na vytvorenie nového exportu stlačte možnosť **Pridať cieľ**.

1. V poli **Pripojenie na export** vyberte pripojenie v časti Microsoft Advertising. Ak nevidíte názov tejto sekcie, nemáte k dispozícii žiadne spojenia tohto typu.

1. Vyberte segmenty, ktoré chcete exportovať. Cieľové skupiny súladu so zákazníkmi v službe Microsoft Advertising sa automaticky vytvárajú s názvom segmentov vybratých na export. Výsledkom každého segmentu bude samostatná cieľová skupina súladu so zákazníkmi. 

1. Zadajte svoje **ID zákazníka Microsoft Advertising a ID konta**. ID zákazníka (`cid`) a ID obchodného vzťahu (`aid`) v parametroch adresy URL, keď ste prihlásení do služby Microsoft Advertising.

1. V sekcii **Párovanie údajov** v poli **E-mail** vyberte pole s e-mailovou adresou zákazníka. Je potrebné exportovať segmenty do Microsoft Advertising.

1. Vyberte položku **Uložiť**.

Uloženie exportu nespustí export okamžite.

Export prebieha s každým [plánovaným obnovením](system.md#schedule-tab). Môžete tiež [exportovať údaje na požiadanie](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Ochrana osobných údajov a dodržiavanie súladu s nariadeniami

Keď povolíte Dynamics 365 Customer Insights na prenos údajov do Microsoft Advertising, povolíte prenos údajov mimo hranice súladu pre Dynamics 365 Customer Insights, a to vrátane potenciálne citlivých údajov, ako sú napríklad osobné údaje. Spoločnosť Microsoft prenesie tieto údaje na váš pokyn, ale vy ste zodpovední za zabezpečenie toho, aby služba Microsoft Advertising spĺňala všetky vaše povinnosti v oblasti ochrany osobných údajov alebo bezpečnosti. Ďalšie informácie nájdete vo [vyhlásení o ochrane súkromia spoločnosti Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).

Túto funkciu môžete kedykoľvek prestať používať odstránením tohto cieľového umiestnenia exportu správcom služby Dynamics 365 Customer Insights.
