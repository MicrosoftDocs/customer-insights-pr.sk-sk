---
title: Export údajov služby Customer Insights do Reklám Google
description: Zistite ako nakonfigurovať pripojenie a realizovať exportovanie do Google Ads.
ms.date: 09/27/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: c958f58c927b76364f305dad8f524dde29b2a638
ms.sourcegitcommit: f1e3cc51ea4cf68210eaf0210ad6e14b15ac4fe8
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 09/27/2021
ms.locfileid: "7558991"
---
# <a name="export-segments-to-google-ads-preview"></a>Exportovať segmenty do služby Google Ads (ukážka)

Exportujte segmenty zjednotených profilov zákazníkov do zoznamu cieľových skupín pre Google Ads a použite ich na inzerciu v rámci služby Vyhľadávanie Google, Gmail, YouTube a Google Display Network. 

> [!IMPORTANT]
> Aktuálne je možné vytvoriť nové pripojenie a exportovať údaje do služby Google Ads iba vtedy, ak už máte schválený token vývojára Google Ads. Pre zmenu zásad budeme zanedlho aktualizovať export služby Google Ads a ponúkneme voľbu exportovania, ktorá nevyžaduje token vývojára. Zaistí sa tak kontinuita vašej skúsenosti a zjednoduší sa export do služby Google Ads. Odporúčame nenastavovať ďalšie pripojenia k službe Google Ads, aby sa zjednodušil prechod na novú možnosť exportu.

## <a name="prerequisites-for-connection"></a>Predpoklad na pripojenie

-   Máte [účet Reklám Google](https://ads.google.com/) a zodpovedajúce poverenia správcu.
-   Máte [schválený token vývojára pre Google Ads](https://developers.google.com/google-ads/api/docs/first-call/dev-token). 
-   Spĺňate požiadavky [pravidiel pre priradenie zákazníkov](https://support.google.com/adspolicy/answer/6299717).
-   Spĺňate požiadavky [veľkostí remarketingového zoznamu](https://support.google.com/google-ads/answer/7558048).
-   V Reklamách Google a zodpovedajúcich ID existujú cieľové skupiny. Ďalšie informácie nájdete v časti [Cieľové skupiny Reklám Google](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).
-   Máte [nakonfigurované segmenty](segments.md).
-   Zjednotené profily zákazníkov v exportovaných segmentoch obsahujú polia predstavujúce e-mailovú adresu, krstné meno a priezvisko.

## <a name="known-limitations"></a>Známe obmedzenia

- Až 1 milión profilov na export do Reklám Google.
- Export do Reklám Google je obmedzený na segmenty.
- Export segmentov s celkovým počtom 1 miliónov profilov môže trvať až 5 minút z dôvodu obmedzení na strane poskytovateľa. 
- Priraďovanie v Reklamách Google môže trvať až 48 hodín.

## <a name="set-up-connection-to-google-ads"></a>Nastavenie pripojenia do Google Ads

1. Prejdite do časti **Správca** > **Pripojenia**.

1. Stlačte možnosť **Pridať pripojenie** a stlačením možnosti **Google Ads** nakonfigurujte pripojenie.

1. Do poľa **Zobrazovaný názov** zadajte rozpoznateľný názov pripojenia. Zobrazovaný názov a typ spojenia, ktoré popisuje toto spojenie. Odporúčame zvoliť názov, ktorý vysvetľuje účel a cieľ tohto spojenia.

1. Vyberte používateľov, ktorí môžu používať toto pripojenie. Ak neurobíte nič, predvolená hodnota bude Správcovia. Viac informácií nájdete v časti [Umožnite prispievateľom použiť pripojenie na export](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Zadajte vaše **[ID zákazníka v Reklamách Google](https://support.google.com/google-ads/answer/1704344)**.

1. Zadajte váš **[Token vývojára schválený Reklamami Google](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**.

1. Vyberte **Súhlasím** na potvrdenie **Ochrany osobných údajov a dodržiavanie súladu s nariadeniami**.

1. Vyberte položku **Overenie pomocou Reklám Google** a poskytnite svoje poverenia pre Reklamy Google.

1. Vyberte položku **Pridať samého seba ako používateľa exportu** a uveďte svoje poverenia pre Customer Insights.

1. Stlačte možnosť **Uložiť** a dokončite pripojenie. 

## <a name="configure-an-export"></a>Nakonfigurujte export

Tento export môžete nakonfigurovať, ak máte prístup k pripojeniu tohto typu. Viac informácií nájdete na stránke [Na konfiguráciu exportu sú potrebné povolenia](export-destinations.md#set-up-a-new-export).

1. Prejdite na **Údaje** > **Exporty**.

1. Na vytvorenie nového exportu stlačte možnosť **Pridať cieľ**.

1. V poli **Pripojenie na export** vyberte pripojenie v časti Google Ads. Ak nevidíte názov tejto sekcie, nemáte k dispozícii žiadne pripojenia tohto typu.

1. Zadajte vaše **[ID cieľovej skupiny Reklám Google](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** a vyberte položku **Pripojiť** na inicializáciu pripojenia k Reklamám Google.

1. V sekcii **Párovanie údajov** v poli **E-mail** do svojho zjednoteného profilu zákazníka vyberte pole, ktoré predstavuje e-mailovú adresu zákazníka.

1. Vyberte segmenty, ktoré chcete exportovať. Do Reklám Google môžete exportovať spolu až 1 milión zákazníckych profilov.

Uloženie exportu nespustí export okamžite.

Export prebieha s každým [plánovaným obnovením](system.md#schedule-tab). 

Môžete tiež [exportovať údaje na požiadanie](export-destinations.md#run-exports-on-demand). 

## <a name="data-privacy-and-compliance"></a>Ochrana osobných údajov a dodržiavanie súladu s nariadeniami

Keď povolíte prenos údajov do Reklám Google v službe Dynamics 365 Customer Insights, povoľujete tým prenos údajov mimo hranice súladu so službou Dynamics 365 Customer Insights vrátane potenciálne citlivých údajov, ako sú napríklad osobné údaje. Spoločnosť Microsoft prenesie tieto údaje na váš pokyn, ale vy ste zodpovední za zabezpečenie toho, aby Reklamy Google plnili všetky prípadné povinnosti týkajúce sa ochrany vašich osobných údajov alebo zabezpečenia. Ďalšie informácie nájdete vo [vyhlásení o ochrane súkromia spoločnosti Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Váš správca služby Dynamics 365 Customer Insights môže túto funkciu kedykoľvek prestať používať odstránením tohto cieľového umiestnenia exportu.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
