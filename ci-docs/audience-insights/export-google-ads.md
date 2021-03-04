---
title: Export údajov služby Customer Insights do Reklám Google
description: Zistite, ako môžete nakonfigurovať pripojenie k Reklamám Google.
ms.date: 11/18/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: ba7c82e643ea0dc1897e0954e78646932cafffa3
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268981"
---
# <a name="connector-for-google-ads-preview"></a>Konektor pre Reklamy Google (ukážka)

Exportujte segmenty zjednotených profilov zákazníkov do zoznamu cieľových skupín v Reklamách Google a použite ich na inzerciu v službách Vyhľadávanie Google, Gmail, YouTube a Obsahová sieť Google. 

## <a name="prerequisites"></a>Predpoklady

-   Máte [účet Reklám Google](https://ads.google.com/) a zodpovedajúce poverenia správcu.
-   V Reklamách Google a zodpovedajúcich ID existujú cieľové skupiny. Ďalšie informácie nájdete v časti [Cieľové skupiny Reklám Google](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).
-   Máte [nakonfigurované segmenty](segments.md)
-   Zjednotené profily zákazníkov v exportovaných segmentoch obsahujú polia predstavujúce e-mailovú adresu, krstné meno a priezvisko

## <a name="connect-to-google-ads"></a>Pripojenie k službe Google Ads

1. Prejdite do ponuky **Správca** > **Ciele exportu**.

1. V časti **Reklamy Google** vyberte položku **Nastavenie**.

1. Do poľa **Zobrazovaný názov** zadajte rozpoznateľný názov cieľa exportu.

1. Zadajte vaše **[ID zákazníka v Reklamách Google](https://support.google.com/google-ads/answer/1704344)**.

1. Zadajte váš **[Token vývojára schválený Reklamami Google](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**.

1. Vyberte **Súhlasím** na potvrdenie **Ochrany osobných údajov a dodržiavanie súladu s nariadeniami**.

1. Zadajte vaše **[ID cieľovej skupiny Reklám Google](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** a vyberte položku **Pripojiť** na inicializáciu pripojenia k Reklamám Google.

1. Vyberte položku **Overenie pomocou Reklám Google** a poskytnite svoje poverenia pre Reklamy Google.

1. Vyberte položku **Pridať samého seba ako používateľa exportu** a uveďte svoje poverenia pre Customer Insights.

   :::image type="content" source="media/export-segments-googleads.PNG" alt-text="Sníma obrazovky exportu pre pripojenie k Reklamám Google":::

1. Vyberte **Ďalej** a nakonfigurujte export.

## <a name="configure-the-connector"></a>Nakonfigurujte konektor

1. V sekcii **Párovanie údajov** v poli **E-mail** do svojho zjednoteného profilu zákazníka vyberte pole, ktoré predstavuje e-mailovú adresu zákazníka. Rovnaký postup opakujte aj pre polia **Krstné meno** a **Priezvisko**.

1. Vyberte segmenty, ktoré chcete exportovať. Do Reklám Google môžete exportovať spolu až 1 milión zákazníckych profilov.

1. Vyberte položku **Uložiť**.

## <a name="export-the-data"></a>Export údajov

Môžete [exportovať údaje na vyžiadanie](export-destinations.md). Export sa spustí aj pri každej [plánovanej obnove](system.md#schedule-tab). V Reklamách Google teraz nájdete svoje segmenty v sekcii [Cieľové skupiny Reklám Google](https://support.google.com/google-ads/answer/7558048?hl=en/).

## <a name="known-limitations"></a>Známe obmedzenia

- Až 1 milión profilov na export do Reklám Google.
- Export do Reklám Google je obmedzený na segmenty.
- Export segmentov s celkovým počtom 1 miliónov profilov môže trvať až 5 minút z dôvodu obmedzení na strane poskytovateľa. 
- Priraďovanie v Reklamách Google môže trvať až 48 hodín.

## <a name="data-privacy-and-compliance"></a>Ochrana osobných údajov a dodržiavanie súladu s nariadeniami

Keď povolíte prenos údajov do Reklám Google v službe Dynamics 365 Customer Insights, povoľujete tým prenos údajov mimo hranice súladu so službou Dynamics 365 Customer Insights vrátane potenciálne citlivých údajov, ako sú napríklad osobné údaje. Spoločnosť Microsoft prenesie tieto údaje na váš pokyn, ale vy ste zodpovední za zabezpečenie toho, aby Reklamy Google plnili všetky prípadné povinnosti týkajúce sa ochrany vašich osobných údajov alebo zabezpečenia. Ďalšie informácie nájdete vo [vyhlásení o ochrane súkromia spoločnosti Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Váš správca služby Dynamics 365 Customer Insights môže túto funkciu kedykoľvek prestať používať odstránením tohto cieľového umiestnenia exportu.


[!INCLUDE[footer-include](../includes/footer-banner.md)]