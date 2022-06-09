---
title: Export údajov služby Customer Insights do AdRoll
description: Zistite ako nakonfigurovať pripojenie a realizovať exportovanie do AdRoll.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: ec7d2d4d137f2f0e3e1ff2ec0d09bff8ac4f28ea
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 04/27/2022
ms.locfileid: "8643178"
---
# <a name="export-segments-to-adroll-preview"></a>Export segmentov do AdRoll (verzia Preview)

Exportujte segmenty zjednotených profilov zákazníkov do služby AdRoll a použite ich na reklamu. 

## <a name="prerequisites-for-a-connection"></a>Predpoklad na pripojenie

-   Máte [účet AdRoll](https://www.adroll.com/) a zodpovedajúce poverenia správcu.
-   Máš [nakonfigurované segmenty](segments.md) v Customer Insights.
-   Zjednotené profily zákazníkov v exportovaných segmentoch obsahujú pole predstavujúce e-mailovú adresu.

## <a name="known-limitations"></a>Známe obmedzenia

- Do AdRoll môžete naraz exportovať až 250 000 zákazníckych profilov.
- Do AdRoll nemôžete exportovať segmenty s menej ako 100 profilmi zákazníkov. 
- Export do AdRoll je obmedzený na segmenty.
- Export až 250 000 profilov zákazníkov do AdRoll môže trvať až 10 minút. 
- Počet profilov zákazníkov, ktoré môžete exportovať do služby AdRoll, závisí od vašej zmluvy so spoločnosťou AdRoll.

## <a name="set-up-connection-to-adroll"></a>Nastavenie pripojenia k AdRoll

1. Prejdite do časti **Správca** > **Pripojenia**.

1. Stlačte možnosť **Pridať pripojenie** a stlačením možnosti **AdRoll** nakonfigurujte pripojenie.

1. Do poľa **Zobrazovaný názov** zadajte rozpoznateľný názov pripojenia. Zobrazovaný názov a typ spojenia, ktoré popisuje toto spojenie. Odporúčame zvoliť názov, ktorý vysvetľuje účel a cieľ tohto spojenia.

1. Vyberte používateľov, ktorí môžu používať toto pripojenie. Ak neurobíte nič, predvolená hodnota bude Správcovia. Viac informácií nájdete v časti [Umožnite prispievateľom použiť pripojenie na export](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Vyberte **Súhlasím** na potvrdenie **Ochrany osobných údajov a dodržiavanie súladu s nariadeniami**.

1. Vyberte položku **Pripojiť** na inicializáciu pripojenia k AdRoll.

1. Vyberte položku **Overenie pomocou AdRoll** a poskytnite svoje poverenia správcu pre AdRoll. 

1. Vyberte položku **Pridať samého seba ako používateľa exportu** a uveďte svoje poverenia pre Customer Insights.

1. Stlačte možnosť **Uložiť** a dokončite pripojenie.

## <a name="configure-an-export"></a>Nakonfigurujte export

Tento export môžete nakonfigurovať, ak máte prístup k pripojeniu tohto typu. Viac informácií nájdete na stránke [Na konfiguráciu exportu sú potrebné povolenia](export-destinations.md#set-up-a-new-export).

1. Prejdite na **Údaje** > **Exporty**.

1. Na vytvorenie nového exportu stlačte možnosť **Pridať cieľ**.

1. V poli **Pripojenie na export** vyberte pripojenie v časti AdRoll. Ak nevidíte názov tejto sekcie, nemáte k dispozícii žiadne pripojenia tohto typu.

1. Zadajte svoje **ID zadávateľa reklamy v službe AdRoll**. Ďalšie informácie nájdete v sekcii [Profily zadávateľov reklamy v službe AdRoll](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).

1. V sekcii **Párovanie údajov** v poli **E-mail** vyberte pole, ktoré predstavuje e-mailovú adresu zákazníka. Je potrebné exportovať segmenty do služby AdRoll.

1. Vyberte segmenty, ktoré chcete exportovať. Vyberte segment s najmenej 100 členmi. Menšie segmenty nemôžete exportovať. Maximálna veľkosť segmentu na export je 250 000 členov na export. 

1. Vyberte položku **Uložiť**.

Uloženie exportu nespustí export okamžite.

Export prebieha s každým [plánovaným obnovením](system.md#schedule-tab). 

Môžete tiež [exportovať údaje na požiadanie](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Ochrana osobných údajov a dodržiavanie súladu s nariadeniami

Keď povolíte prenos údajov do AdRoll v službe Dynamics 365 Customer Insights, povoľujete tým prenos údajov mimo hranice súladu so službou Dynamics 365 Customer Insights vrátane potenciálne citlivých údajov, ako sú napríklad osobné údaje. Spoločnosť Microsoft prenesie tieto údaje na váš pokyn, ale vy ste zodpovední za zabezpečenie toho, aby AdRoll plnila všetky prípadné povinnosti týkajúce sa ochrany vašich osobných údajov alebo zabezpečenia. Ďalšie informácie nájdete vo [vyhlásení o ochrane súkromia spoločnosti Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).

Váš správca služby Dynamics 365 Customer Insights môže túto funkciu kedykoľvek prestať používať odstránením tohto cieľového umiestnenia exportu.