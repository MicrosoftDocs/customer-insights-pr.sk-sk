---
title: Export údajov Customer Insights do RollWorks
description: Zistite ako nakonfigurovať pripojenie a realizovať exportovanie do RollWorks.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: dce5d51ca4587b4d7a0644cc701c1826854882b5
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124108"
---
# <a name="export-segments-to-rollworks-preview"></a>Export segmentov do RollWorks (verzia Preview)

Exportujte segmenty zjednotených profilov zákazníkov do RollWorks a použite ich na reklamu. 

## <a name="prerequisites-for-a-connection"></a>Predpoklad na pripojenie

-   Máte [účet RollWorks](https://www.rollworks.com/) a zodpovedajúce poverenia správcu.
-   Máte [konfigurované segmenty](segments.md) v prehľadoch cieľových skupín.
-   Zjednotené profily zákazníkov v exportovaných segmentoch obsahujú pole predstavujúce e-mailovú adresu.

## <a name="known-limitations"></a>Známe obmedzenia

- Na jeden export do RollWorks môžete exportovať až 250 000 profilov.
- Do RollWorks nemôžete exportovať segmenty s menej ako 100 profilmi. 
- Exportovanie do RollWorks je obmedzené na segmenty.
- Exportovanie až 250 000 profilov do aplikácie RollWorks môže trvať až 10 minút. 
- Počet profilov, ktoré môžete exportovať do RollWorks, závisí a je obmedzený na vašu zmluvu so spoločnosťou RollWorks.

## <a name="set-up-connection-to-rollworks"></a>Nastavenie pripojenia k RollWorks

1. Prejdite do časti **Správca** > **Pripojenia**.

1. Stlačte možnosť **Pridať pripojenie** a stlačením možnosti **RollWorks** nakonfigurujte pripojenie.

1. Do poľa **Zobrazovaný názov** zadajte rozpoznateľný názov pripojenia. Zobrazovaný názov a typ spojenia, ktoré popisuje toto spojenie. Odporúčame zvoliť názov, ktorý vysvetľuje účel a cieľ tohto spojenia.

1. Vyberte používateľov, ktorí môžu používať toto pripojenie. Ak neurobíte nič, predvolená hodnota bude Správcovia. Viac informácií nájdete v časti [Umožnite prispievateľom použiť pripojenie na export](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Vyberte **Súhlasím** na potvrdenie **Ochrany osobných údajov a dodržiavanie súladu s nariadeniami**.

1. Stlačte možnosť **Pripojiť** na inicializáciu pripojenia k RollWorks.

1. Stlačte možnosť **Overenie pomocou služby RollWorks** a zadajte svoje poverenia správcu pre RollWorks.

1. Vyberte položku **Pridať samého seba ako používateľa exportu** a uveďte svoje poverenia pre Customer Insights.

1. Stlačte možnosť **Uložiť** a dokončite pripojenie.

## <a name="configure-an-export"></a>Nakonfigurujte export

Tento export môžete nakonfigurovať, ak máte prístup k pripojeniu tohto typu. Viac informácií nájdete na stránke [Na konfiguráciu exportu sú potrebné povolenia](export-destinations.md#set-up-a-new-export).

1. Prejdite na **Údaje** > **Exporty**.

1. Na vytvorenie nového exportu stlačte možnosť **Pridať cieľ**.

1. V poli **Pripojenie na export** vyberte pripojenie v časti RollWorks. Ak nevidíte názov tejto sekcie, nemáte k dispozícii žiadne spojenia tohto typu.

1. Zadajte svoje **ID inzerenta RollWorks** [Inzerovateľné v službe RollWorks](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).

3. V sekcii **Párovanie údajov** v poli **E-mail** do svojho zjednoteného profilu zákazníka vyberte pole, ktoré predstavuje e-mailovú adresu zákazníka. Je potrebné exportovať segmenty do RollWorks.

1. Vyberte segmenty, ktoré chcete exportovať. Vyberte segment s najmenej 100 členmi. Menšie segmenty nemôžete exportovať. Maximálna veľkosť segmentu na export je 250 000 členov na export. 

1. Vyberte položku **Uložiť**.

Uloženie exportu nespustí export okamžite.

Export prebieha s každým [plánovaným obnovením](system.md#schedule-tab). Môžete tiež [exportovať údaje na požiadanie](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Ochrana osobných údajov a dodržiavanie súladu s nariadeniami

Keď povolíte Dynamics 365 Customer Insights na prenos údajov do RollWorks, povolíte prenos údajov mimo hranice súladu s Dynamics 365 Customer Insights, a to vrátane potenciálne citlivých údajov, ako sú napríklad osobné údaje. Spoločnosť Microsoft prenesie tieto údaje na váš pokyn, ale vy ste zodpovední za zabezpečenie toho, aby služba RollWorks spĺňala všetky vaše povinnosti v oblasti ochrany osobných údajov alebo bezpečnosti. Ďalšie informácie nájdete vo [vyhlásení o ochrane súkromia spoločnosti Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).

Váš správca služby Dynamics 365 Customer Insights môže túto funkciu kedykoľvek prestať používať odstránením tohto cieľového umiestnenia exportu.
