---
title: Export segmentov do Snapchat (verzia Preview)
description: Zistite ako nakonfigurovať pripojenie a realizovať exportovanie do Snapchat.
ms.date: 06/08/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: abe04cd1464c3f7df969da3c769329382d603d7e
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 06/29/2022
ms.locfileid: "9051932"
---
# <a name="export-segments-to-snapchat-preview"></a>Export segmentov do Snapchat (verzia Preview)

Exportujte segmenty zjednotených profilov zákazníkov do Snapchat a použite ich na reklamu. 

## <a name="prerequisites-for-a-connection"></a>Predpoklad na pripojenie

-   Máte [Účet Snapchat Business](https://business.snapchat.com/) a [Účet Snapchat Ads](https://ads.snapchat.com/) a zodpovedajúce poverenia správcu. Musíte byť aspoň členom účtu organizácie a správcom údajov konkrétneho účtu reklamy. 
-   V správcovi Snapchat Audience Manager máte aspoň jedno publikum typu SAM (Snap Audience Match). 
-   Máš [nakonfigurované segmenty](segments.md) v Customer Insights.
-   Zjednotené profily zákazníkov v exportovaných segmentoch obsahujú pole predstavujúce e-mailovú adresu.

## <a name="known-limitations"></a>Známe obmedzenia

- Exportovanie do Snapchat je obmedzené na segmenty.
- Export až 1 milióna profilov zákazníkov do služby Snapchat môže trvať až 15 minút. 

## <a name="set-up-connection-to-snapchat"></a>Nastavenie pripojenia k Snapchat

1. Prejdite do časti **Správca** > **Pripojenia**.

1. Stlačte možnosť **Pridať pripojenie** a stlačením možnosti **Snapchat** nakonfigurujte pripojenie.

1. Do poľa **Zobrazovaný názov** zadajte rozpoznateľný názov pripojenia. Zobrazovaný názov a typ spojenia, ktoré popisuje toto spojenie. Odporúčame zvoliť názov, ktorý vysvetľuje účel a cieľ tohto spojenia.

1. Vyberte používateľov, ktorí môžu používať toto pripojenie. Ak neurobíte nič, predvolená hodnota bude Správcovia. Viac informácií nájdete v časti [Umožnite prispievateľom použiť pripojenie na export](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Vyberte **Súhlasím** na potvrdenie **Ochrany osobných údajov a dodržiavanie súladu s nariadeniami**.

1. Stlačte možnosť **Pripojiť** na inicializáciu pripojenia k Snapchat.

1. Stlačte možnosť **Overenie pomocou služby Snapchat** a zadajte svoje poverenia správcu pre Snapchat. 

1. Vyberte položku **Pridať samého seba ako používateľa exportu** a uveďte svoje poverenia pre Customer Insights.

1. Stlačte možnosť **Uložiť** a dokončite pripojenie.

## <a name="configure-an-export"></a>Nakonfigurujte export

Tento export môžete nakonfigurovať, ak máte prístup k pripojeniu tohto typu. Viac informácií nájdete na stránke [Na konfiguráciu exportu sú potrebné povolenia](export-destinations.md#set-up-a-new-export).

1. Prejdite na **Údaje** > **Exporty**.

1. Na vytvorenie nového exportu stlačte možnosť **Pridať cieľ**.

1. V poli **Pripojenie na export** vyberte pripojenie v časti Snapchat. Ak nevidíte názov tejto sekcie, nemáte k dispozícii žiadne spojenia tohto typu.

1. Zadajte [**ID segmentu/publika Snapchat**](https://businesshelp.snapchat.com/s/article/custom-audiences). ID publika nájdete v URL po výbere publika v Snapchat Audience Manager. 

1. V sekcii **Párovanie údajov** v poli **E-mail** vyberte pole, ktoré predstavuje e-mailovú adresu zákazníka. Je potrebné exportovať segmenty do Snapchat.

1. Vyberte segmenty, ktoré chcete exportovať. 

1. Vyberte položku **Uložiť**.

Uloženie exportu nespustí export okamžite.

Export prebieha s každým [plánovaným obnovením](system.md#schedule-tab). Môžete tiež [exportovať údaje na požiadanie](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Ochrana osobných údajov a dodržiavanie súladu s nariadeniami

Keď povolíte Dynamics 365 Customer Insights na prenos údajov do Snapchat, povolíte prenos údajov mimo hranice súladu s Dynamics 365 Customer Insights, a to vrátane potenciálne citlivých údajov, ako sú napríklad osobné údaje. Spoločnosť Microsoft prenesie tieto údaje na váš pokyn, ale vy ste zodpovední za zabezpečenie toho, aby služba Snapchat spĺňala všetky vaše povinnosti v oblasti ochrany osobných údajov alebo bezpečnosti. Ďalšie informácie nájdete vo [vyhlásení o ochrane súkromia spoločnosti Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).

Váš správca služby Dynamics 365 Customer Insights môže túto funkciu kedykoľvek prestať používať odstránením tohto cieľového umiestnenia exportu.
