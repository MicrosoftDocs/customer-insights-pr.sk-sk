---
title: Export údajov služby Customer Insights do SendGrid
description: Zistite ako nakonfigurovať pripojenie a realizovať exportovanie do SendGrid.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: a4c64cf77c682e07f3d0759c43355336b5806fc8
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 03/31/2021
ms.locfileid: "5759784"
---
# <a name="export-segments-to-sendgrid-preview"></a>Export segmentov do SendGrid (ukážka)

Exportujte segmenty zjednotených profilov zákazníkov do zoznamov kontaktov SendGrid a použite ich pre kampane a e-mailový marketing v SendGrid. 

## <a name="prerequisites-for-a-connection"></a>Predpoklad na pripojenie

-   Máte [účet SendGrid](https://sendgrid.com/) a zodpovedajúce poverenia správcu.
-   V službe SendGrid existujú zoznamy kontaktov a zodpovedajúce ID. Ďalšie informácie nájdete v časti [SendGrid – spravovanie kontaktov](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts).
-   Máte [konfigurované segmenty](segments.md) v prehľadoch cieľových skupín.
-   Zjednotené profily zákazníkov v exportovaných segmentoch obsahujú pole predstavujúce e-mailovú adresu.

## <a name="known-limitations"></a>Známe obmedzenia

- Až 100 000 profilov celkovo do služby SendGrid.
- Export do SendGrid je obmedzený na segmenty.
- Export až 100 000 profilov do služby SendGrid môže trvať až niekoľko hodín. 
- Počet profilov, ktoré môžete exportovať do SendGrid, závisí a je obmedzený vašou zmluvou so spoločnosťou SendGrid.

## <a name="set-up-connection-to-sendgrid"></a>Nastavenie pripojenia k SendGrid

1. Prejdite do časti **Správca** > **Pripojenia**.

1. Stlačte možnosť **Pridať pripojenie** a stlačením možnosti **SendGrid** nakonfigurujte pripojenie.

1. Do poľa **Zobrazovaný názov** zadajte rozpoznateľný názov pripojenia. Zobrazovaný názov a typ spojenia, ktoré popisuje toto spojenie. Odporúčame zvoliť názov, ktorý vysvetľuje účel a cieľ tohto spojenia.

1. Vyberte používateľov, ktorí môžu používať toto pripojenie. Ak neurobíte nič, predvolená hodnota bude Správcovia. Viac informácií nájdete v časti [Umožnite prispievateľom použiť pripojenie na export](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Zadajte svoj **Kľúč API SendGrid** [Kľúč API SendGrid](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).

1. Vyberte **Súhlasím** na potvrdenie **Ochrany osobných údajov a dodržiavanie súladu s nariadeniami**.

1. Vyberte položku **Pripojiť** na inicializáciu pripojenia k SendGrid.

1. Vyberte položku **Pridať samého seba ako používateľa exportu** a uveďte svoje poverenia pre Customer Insights.

1. Stlačte možnosť **Uložiť** a dokončite pripojenie.

## <a name="configure-an-export"></a>Nakonfigurujte export

Tento export môžete nakonfigurovať, ak máte prístup k pripojeniu tohto typu. Viac informácií nájdete na stránke [Na konfiguráciu exportu sú potrebné povolenia](export-destinations.md#set-up-a-new-export).

1. Prejdite na **Údaje** > **Exporty**.

1. Na vytvorenie nového exportu stlačte možnosť **Pridať cieľ**.

1. V poli **Pripojenie na export** vyberte pripojenie v časti SendGrid. Ak nevidíte názov tejto sekcie, nemáte k dispozícii žiadne spojenia tohto typu.

1. Zadajte svoje **[ID zoznamu SendGrid](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)**.

1. V sekcii **Párovanie údajov** v poli **E-mail** do svojho zjednoteného profilu zákazníka vyberte pole, ktoré predstavuje e-mailovú adresu zákazníka. Rovnaký postup zopakujte pri ďalších voliteľných poliach, ako je **Krstné meno**, **Priezvisko**, **Krajina/región**, **Štát**, **Mesto** a **PSČ**.

1. Vyberte segmenty, ktoré chcete exportovať. Dôrazne **odporúčame neexportovať celkovo viac ako 100 000 profilov zákazníkov** do SendGrid. 

1. Vyberte položku **Uložiť**.

Uloženie exportu nespustí export okamžite.

Export prebieha s každým [plánovaným obnovením](system.md#schedule-tab). Môžete tiež [exportovať údaje na požiadanie](export-destinations.md#run-exports-on-demand). 

## <a name="data-privacy-and-compliance"></a>Ochrana osobných údajov a dodržiavanie súladu s nariadeniami

Keď povolíte službe Dynamics 365 Customer Insights prenos údajov do SendGrid, povoľujete tým prenos údajov mimo hranice súladu so službou Dynamics 365 Customer Insights vrátane potenciálne citlivých údajov, ako sú napríklad osobné údaje. Spoločnosť Microsoft prenesie tieto údaje na váš pokyn, ale vy ste zodpovední za zabezpečenie toho, aby SendGrid plnila všetky prípadné povinnosti týkajúce sa ochrany vašich osobných údajov alebo zabezpečenia. Ďalšie informácie nájdete vo [vyhlásení o ochrane súkromia spoločnosti Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Váš správca služby Dynamics 365 Customer Insights môže túto funkciu kedykoľvek prestať používať odstránením tohto cieľového umiestnenia exportu.


[!INCLUDE[footer-include](../includes/footer-banner.md)]