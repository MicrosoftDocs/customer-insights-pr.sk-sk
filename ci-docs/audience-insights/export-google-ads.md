---
title: Export údajov služby Customer Insights do Reklám Google
description: Zistite ako nakonfigurovať pripojenie a realizovať exportovanie do Google Ads.
ms.date: 03/31/2022
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 7a85237f7aff564d6b540b2c11553a52f875fac4
ms.sourcegitcommit: 5bd07f3a1288f003704acd576741cf6aedc1ac33
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 03/31/2022
ms.locfileid: "8523824"
---
# <a name="export-segments-to-google-ads-preview"></a>Exportovať segmenty do služby Google Ads (ukážka)

Exportujte segmenty zjednotených profilov zákazníkov do zoznamu cieľových skupín pre Google Ads a použite ich na inzerciu v rámci služby Vyhľadávanie Google, Gmail, YouTube a Google Display Network. 


## <a name="prerequisites-for-connection"></a>Predpoklad na pripojenie

-   Máte [účet Reklám Google](https://ads.google.com/) a zodpovedajúce poverenia správcu.
-   Spĺňate požiadavky [pravidiel pre priradenie zákazníkov](https://support.google.com/adspolicy/answer/6299717).
-   Spĺňate požiadavky [veľkostí remarketingového zoznamu](https://support.google.com/google-ads/answer/7558048).
-   Máte [nakonfigurované segmenty](segments.md).
-   Zjednotené profily zákazníkov v exportovaných segmentoch obsahujú polia predstavujúce e-mailovú adresu, telefón, ID mobilného inzerenta, ID používateľa tretej strany alebo adresu.

## <a name="known-limitations"></a>Známe obmedzenia

- Export do Reklám Google je obmedzený na segmenty.
- Export segmentov s celkovo 1 miliónom profilov zákazníkov môže z dôvodu obmedzení na strane poskytovateľa trvať až 30 minút. 
- Priraďovanie v Reklamách Google môže trvať až 48 hodín.

## <a name="set-up-connection-to-google-ads"></a>Nastavenie pripojenia do Google Ads

1. Prejdite do časti **Správca** > **Pripojenia**.

1. Stlačte možnosť **Pridať pripojenie** a stlačením možnosti **Google Ads** nakonfigurujte pripojenie.

1. Do poľa **Zobrazovaný názov** zadajte rozpoznateľný názov pripojenia. Zobrazovaný názov a typ spojenia, ktoré popisuje toto spojenie. Odporúčame zvoliť názov, ktorý vysvetľuje účel a cieľ tohto spojenia.

1. Vyberte používateľov, ktorí môžu používať toto pripojenie. Ak neurobíte nič, predvolená hodnota bude Správcovia. Viac informácií nájdete v časti [Umožnite prispievateľom použiť pripojenie na export](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Zadajte vaše **[ID zákazníka v Reklamách Google](https://support.google.com/google-ads/answer/1704344)**.

1. Vyberte **Súhlasím** na potvrdenie **Ochrany osobných údajov a dodržiavanie súladu s nariadeniami**.

1. Vyberte položku **Overenie pomocou Reklám Google** a poskytnite svoje poverenia pre Reklamy Google.

1. Vyberte položku **Pridať samého seba ako používateľa exportu** a uveďte svoje poverenia pre Customer Insights.

1. Stlačte možnosť **Uložiť** a dokončite pripojenie. 

## <a name="configure-an-export"></a>Nakonfigurujte export

Tento export môžete nakonfigurovať, ak máte prístup k pripojeniu tohto typu. Viac informácií nájdete na stránke [Na konfiguráciu exportu sú potrebné povolenia](export-destinations.md#set-up-a-new-export).

1. Prejdite na **Údaje** > **Exporty**.

1. Na vytvorenie nového exportu stlačte možnosť **Pridať cieľ**.

1. V poli **Pripojenie na export** vyberte pripojenie v časti Google Ads. Ak nevidíte názov tejto sekcie, nemáte k dispozícii žiadne pripojenia tohto typu.

1. Ak chcete vytvoriť nové publikum, ponechajte pole Google Audience ID prázdne. Vo vašom účte Google Ads automaticky vytvoríme nové publikum a použijeme názov exportovaného segmentu. Ak chcete aktualizovať existujúce publikum Google Ads, zadajte svoje [ID publika Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)

1. V **Zhoda údajov** vyberte jedno alebo viac dátových polí na export a vyberte pole, ktoré predstavuje zodpovedajúce dátové polia v Customer Insights.

1. Vyberte segmenty, ktoré chcete exportovať. 

Uloženie exportu nespustí export okamžite.

Export prebieha s každým [plánovaným obnovením](system.md#schedule-tab). 

Môžete tiež [exportovať údaje na požiadanie](export-destinations.md#run-exports-on-demand). 

## <a name="data-privacy-and-compliance"></a>Ochrana osobných údajov a dodržiavanie súladu s nariadeniami

Keď povolíte prenos údajov do Reklám Google v službe Dynamics 365 Customer Insights, povoľujete tým prenos údajov mimo hranice súladu so službou Dynamics 365 Customer Insights vrátane potenciálne citlivých údajov, ako sú napríklad osobné údaje. Spoločnosť Microsoft prenesie tieto údaje na váš pokyn, ale vy ste zodpovední za zabezpečenie toho, aby Reklamy Google plnili všetky prípadné povinnosti týkajúce sa ochrany vašich osobných údajov alebo zabezpečenia. Ďalšie informácie nájdete vo [vyhlásení o ochrane súkromia spoločnosti Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Váš správca služby Dynamics 365 Customer Insights môže túto funkciu kedykoľvek prestať používať odstránením tohto cieľového umiestnenia exportu.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
