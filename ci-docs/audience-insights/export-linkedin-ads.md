---
title: Export údajov Customer Insights do LinkedIn Ads
description: Zistite ako nakonfigurovať pripojenie a realizovať exportovanie do LinkedIn Ads.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 867a6541734746f75a35faaa8d3861e0479d6114
ms.sourcegitcommit: 9558ff772ee6c944fcb8db4bfc8cda13b38a1bff
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 11/29/2021
ms.locfileid: "7866907"
---
# <a name="export-segments-to-linkedin-ads-preview"></a>Export segmentov do služby LinkedIn Ads (verzia Preview)

Exportujte segmenty zjednotených profilov zákazníkov do LinkedIn Ads a vytvorte párované cieľové skupiny. Použite párované cieľové skupiny na zacielenie na spoločnosť a kontakty.

## <a name="prerequisites"></a>Požiadavky

-   Máte [LinkedIn Campaign Manager účet](https://business.linkedin.com/marketing-solutions/ads) a zodpovedajúce poverenia správcu.
-   Máte [konfigurované segmenty](segments.md) v prehľadoch cieľových skupín.
-   Profily zákazníkov v exportovaných segmentoch obsahujú pole s e-mailovou adresou.

## <a name="known-limitations"></a>Známe obmedzenia

- Váš segment v Customer Insights musí obsahovať aspoň 300 jedinečných profilov. 
- Do služby LinkedIn Ads môžete exportovať až 100 000 profilov zákazníkov.
- Exportovanie do LinkedIn Ads je obmedzené na segmenty.
- Export až 100 000 profilov zákazníkov do služby LinkedIn Ads môže trvať až 10 minút. 

## <a name="set-up-the-connection-to-linkedin-ads"></a>Príprava pripojenia do LinkedIn Ads

1. V prehľadoch cieľovej skupiny prejdite na **Správca** > **Pripojenia**.

1. Stlačte možnosť **Pridať pripojenie** a stlačením možnosti **LinkedIn Ads** nakonfigurujte pripojenie.

1. Do poľa **Zobrazovaný názov** zadajte rozpoznateľný názov pripojenia. Zobrazovaný názov a typ spojenia, ktoré popisuje toto spojenie. Odporúčame zvoliť názov, ktorý vysvetľuje účel a cieľ tohto spojenia.

1. Vyberte používateľov, ktorí môžu používať toto pripojenie. Ak neurobíte nič, predvolená hodnota bude správcovia. Viac informácií nájdete v časti [Umožnite prispievateľom použiť pripojenie na export](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Poskytnite svoje [LinkedIn Campaign Manager ID účtu](https://www.linkedin.com/help/lms/answer/a424270).

1. Vyberte **Súhlasím** na potvrdenie **Ochrany osobných údajov a dodržiavanie súladu s nariadeniami**.

1. Stlačte možnosť **Pripojiť** na inicializáciu pripojenia k Campaign Monitor.

1. Vyberte **Overte sa pomocou LinkedIn** a poskytnite svoje poverenia správcu pre LinkedIn Campaign Manager.

1. Vyberte položku **Pridať samého seba ako používateľa exportu** a uveďte svoje poverenia pre Customer Insights.

1. Stlačte možnosť **Uložiť** a dokončite pripojenie.

## <a name="configure-an-export"></a>Nakonfigurujte export

Export môžete nakonfigurovať, ak máte prístup k pripojeniu tohto typu. Viac informácií nájdete na stránke [Na konfiguráciu exportu sú potrebné povolenia](export-destinations.md#set-up-a-new-export).

1. Prejdite na **Údaje** > **Exporty**.

1. Na vytvorenie nového exportu stlačte možnosť **Pridať cieľ**.

1. V poli **Pripojenie na export** vyberte pripojenie v časti LinkedIn Ads. Ak nevidíte názov tejto sekcie, nemáte k dispozícii žiadne spojenia tohto typu.

1. Vyberte, či chcete exportovať údaje a vykonať [zacielenie na kontakty](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting) alebo [zacielenie na spoločnosť](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting) na LinkedIn. 

1. V sekcii **Párovanie údajov** vyberte pre zacielenie kontaktov aspoň jedno pole, ktoré predstavuje e-mailovú adresu zákazníka, Apple Ad ID, Google Ad ID, Google User ID alebo krstné meno a priezvisko. Ak si vyberiete zacielenie na spoločnosť, vyberte aspoň jedno pole, ktoré predstavuje názov spoločnosti, e-mailovú doménu, adresu URL stránky LinkedIn, symbol akcie alebo webovú stránku. Na ďalšie definovanie exportu je možné vybrať ďalšie polia. 

1. Vyberte segmenty, ktoré chcete exportovať. Priradené publiká v LinkedIn Campaign Manager sa automaticky vytvoria s názvom segmentov, ktoré ste vybrali na export. Výsledkom každého segmentu bude samostatná priradená cieľová skupina. 

1. Vyberte položku **Uložiť**.

Uloženie exportu nespustí export okamžite.

Export prebieha s každým [plánovaným obnovením](system.md#schedule-tab). Môžete tiež [exportovať údaje na požiadanie](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Ochrana osobných údajov a dodržiavanie súladu s nariadeniami

Keď povolíte Dynamics 365 Customer Insights prenášať údaje do LinkedIn Ads, povolíte prenos údajov mimo hraníc súladu pre Dynamics 365 Customer Insights, vrátane potenciálne citlivých údajov, ako sú Osobné údaje. Spoločnosť Microsoft prenesie tieto údaje na váš pokyn, ale vy ste zodpovední za zabezpečenie toho, aby služba LinkedIn Ads spĺňala všetky vaše povinnosti v oblasti ochrany osobných údajov alebo bezpečnosti. Ďalšie informácie nájdete vo [vyhlásení o ochrane súkromia spoločnosti Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).

Váš Dynamics 365 Customer Insights správca môže tento cieľ exportu kedykoľvek odstrániť a zastaviť tak používanie tejto funkcie.
