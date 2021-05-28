---
title: Export údajov služby Customer Insights do Mailchimp
description: Zistite ako nakonfigurovať pripojenie a realizovať exportovanie do Mailchimp.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 35848998e738c7ecc1642f2b75912ff78d85f79e
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976174"
---
# <a name="export-segment-lists-to-mailchimp-preview"></a>Exportovanie zoznamov segmentov do Mailchimp (ukážka)

Exportujte segmenty zjednotených profilov zákazníkov do služby Mailchimp a vytvárajte bulletiny a e-mailové kampane.

## <a name="prerequisites-for-connection"></a>Predpoklad na pripojenie

-   Máte [účet Mailchimp](https://mailchimp.com/) a zodpovedajúce poverenia správcu.
-   V Mailchimp a zodpovedajúcich ID existujú cieľové skupiny. Ďalšie informácie nájdete v časti [Cieľové skupiny Mailchimp](https://mailchimp.com/help/create-audience/).
-   Máte [nakonfigurované segmenty](segments.md)
-   Zjednotené profily zákazníkov v exportovaných segmentoch obsahujú pole predstavujúce e-mailovú adresu.

## <a name="known-limitations"></a>Známe obmedzenia

- Až 1 milión profilov na export do Mailchimp.
- Export do Mailchimp je obmedzený na segmenty.
- Export segmentov s miliónom profilov môže trvať až tri hodiny. 
- Počet profilov, ktoré môžete exportovať do Mailchimp, závisí a je obmedzený vašou zmluvou so spoločnosťou Mailchimp.

## <a name="set-up-connection-to-mailchimp"></a>Nastavenie pripojenia k Mailchimp

1. Prejdite do časti **Správca** > **Pripojenia**.

1. Stlačte možnosť **Pridať pripojenie** a stlačením možnosti **Autopilot** nakonfigurujte pripojenie.

1. Do poľa **Zobrazovaný názov** zadajte rozpoznateľný názov pripojenia. Zobrazovaný názov a typ spojenia, ktoré popisuje toto spojenie. Odporúčame zvoliť názov, ktorý vysvetľuje účel a cieľ tohto spojenia.

1. Vyberte používateľov, ktorí môžu používať toto pripojenie. Ak neurobíte nič, predvolená hodnota bude Správcovia. Viac informácií nájdete v časti [Umožnite prispievateľom použiť pripojenie na export](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Vyberte **Súhlasím** na potvrdenie **Ochrany osobných údajov a dodržiavanie súladu s nariadeniami**.

1. Stlačte možnosť **Pripojiť** na inicializáciu pripojenia k Mailchimp.

1. Vyberte položku **Overenie pomocou služby Mailchimp** a poskytnite svoje poverenia pre Mailchimp.

1. Vyberte položku **Pridať samého seba ako používateľa exportu** a uveďte svoje poverenia pre Customer Insights.

1. Stlačte možnosť **Uložiť** a dokončite pripojenie. 

## <a name="configure-the-connector"></a>Nakonfigurujte konektor

Tento export môžete nakonfigurovať, ak máte prístup k pripojeniu tohto typu. Viac informácií nájdete na stránke [Na konfiguráciu exportu sú potrebné povolenia](export-destinations.md#set-up-a-new-export).

1. Prejdite na **Údaje**> **Exporty**.

1. Na vytvorenie nového exportu stlačte možnosť **Pridať cieľ**.

1. V poli **Pripojenie na export** vyberte pripojenie v časti Mailchimp. Ak nevidíte názov tejto sekcie, nemáte k dispozícii žiadne spojenia tohto typu.

1. Zadajte svoj **[identifikátor cieľovej skupiny Mailchimp](https://mailchimp.com/help/find-audience-id/)**

3. V sekcii **Párovanie údajov** v poli **E-mail** do svojho zjednoteného profilu zákazníka vyberte pole, ktoré predstavuje e-mailovú adresu zákazníka. 

1. Voliteľné možno exportovať **Krstné meno** a **Priezvisko** a vytvorte si viac prispôsobené e-maily. Výberom položky **Pridať atribút** namapujete tieto polia.

1. Vyberte segmenty, ktoré chcete exportovať. Do služby Mailchimp môžete exportovať spolu až 1 milión zákazníckych profilov.

1. Vyberte položku **Uložiť**.

Uloženie exportu nespustí export okamžite.

Export prebieha s každým [plánovaným obnovením](system.md#schedule-tab). Môžete tiež [exportovať údaje na požiadanie](export-destinations.md#run-exports-on-demand). 

## <a name="data-privacy-and-compliance"></a>Ochrana osobných údajov a dodržiavanie súladu s nariadeniami

Keď povolíte prenos údajov spoločnosti Mailchimp v službe Dynamics 365 Customer Insights, povoľujete tým prenos údajov mimo hranice súladu so službou Dynamics 365 Customer Insights vrátane potenciálne citlivých údajov, ako sú napríklad osobné údaje. Spoločnosť Microsoft prenesie tieto údaje na váš pokyn, ale vy ste zodpovední za zabezpečenie toho, aby spoločnosť Mailchimp plnila všetky prípadné povinnosti týkajúce sa ochrany vašich osobných údajov alebo zabezpečenia. Ďalšie informácie nájdete vo [vyhlásení o ochrane súkromia spoločnosti Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Váš správca služby Dynamics 365 Customer Insights môže túto funkciu kedykoľvek prestať používať odstránením tohto cieľového umiestnenia exportu.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
