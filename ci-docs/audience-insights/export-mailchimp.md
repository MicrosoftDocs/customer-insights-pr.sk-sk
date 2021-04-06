---
title: Export údajov služby Customer Insights do Mailchimp
description: Zistite, ako môžete nakonfigurovať pripojenie k Mailchimp.
ms.date: 10/26/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 9f86616731c3cc3d26370727103ea9c5d4288c8d
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598220"
---
# <a name="connector-for-mailchimp-preview"></a>Konektor pre Mailchimp (ukážka)

Exportujte segmenty zjednotených profilov zákazníkov do služby Mailchimp a vytvárajte bulletiny a e-mailové kampane.

## <a name="prerequisites"></a>Predpoklady

-   Máte [účet Mailchimp](https://mailchimp.com/) a zodpovedajúce poverenia správcu.
-   V Mailchimp a zodpovedajúcich ID existujú cieľové skupiny. Ďalšie informácie nájdete v časti [Cieľové skupiny Mailchimp](https://mailchimp.com/help/create-audience/).
-   Máte [nakonfigurované segmenty](segments.md)
-   Zjednotené profily zákazníkov v exportovaných segmentoch obsahujú pole predstavujúce e-mailovú adresu.

## <a name="connect-to-mailchimp"></a>Pripojiť k Mailchimpu

1. Prejdite do ponuky **Správca** > **Ciele exportu**.

1. V časti **Mailchimp** vyberte položku **Nastaviť**.

1. Do poľa **Zobrazovaný názov** zadajte rozpoznateľný názov cieľa exportu.

1. Vyberte **Súhlasím** na potvrdenie **Ochrany osobných údajov a dodržiavanie súladu s nariadeniami**.

1. Zadajte vaše **[ID cieľovej skupiny Mailchimp](https://mailchimp.com/help/find-audience-id/)** a vyberte položku **Pripojiť** na inicializáciu pripojenia k Mailchimp.

1. Vyberte položku **Overenie pomocou služby Mailchimp** a poskytnite svoje poverenia pre Mailchimp.

1. Vyberte položku **Pridať samého seba ako používateľa exportu** a uveďte svoje poverenia pre Customer Insights.

   :::image type="content" source="media/export-connect-mailchimp.png" alt-text="Sníma obrazovky exportu pre pripojenie k Mailchimp":::

1. Vyberte **Ďalej** a nakonfigurujte export.

## <a name="configure-the-connector"></a>Nakonfigurujte konektor

1. V sekcii **Párovanie údajov** v poli **E-mail** do svojho zjednoteného profilu zákazníka vyberte pole, ktoré predstavuje e-mailovú adresu zákazníka. 

1. Prípadne môžete exportovať **Krstné meno** a **Priezvisko** ako dodatočné polia na vytvorenie viac prispôsobených e-mailov. Výberom položky **Pridať atribút** namapujete tieto polia.

1. Vyberte segmenty, ktoré chcete exportovať. Do služby Mailchimp môžete exportovať spolu až 1 milión zákazníckych profilov.

   :::image type="content" source="media/export-segments-mailchimp.png" alt-text="Vyberte polia a segmenty, ktoré chcete exportovať do Mailchimp":::

1. Vyberte položku **Uložiť**.

## <a name="export-the-data"></a>Export údajov

Môžete [exportovať údaje na vyžiadanie](export-destinations.md). Export sa spustí aj pri každej [plánovanej obnove](system.md#schedule-tab). V službe Mailchimp teraz nájdete svoje segmenty v sekcii [Cieľové skupiny služby Mailchimp](https://mailchimp.com/help/create-audience/).

## <a name="known-limitations"></a>Známe obmedzenia

- Až 1 milión profilov na export do Mailchimp.
- Export do Mailchimp je obmedzený na segmenty.
- Export segmentov s celkovým počtom 1 miliónov profilov môže trvať až tri hodiny z dôvodu obmedzení na strane poskytovateľa. 
- Počet profilov, ktoré môžete exportovať do Mailchimp, závisí a je obmedzený vašou zmluvou so spoločnosťou Mailchimp.

## <a name="data-privacy-and-compliance"></a>Ochrana osobných údajov a dodržiavanie súladu s nariadeniami

Keď povolíte prenos údajov spoločnosti Mailchimp v službe Dynamics 365 Customer Insights, povoľujete tým prenos údajov mimo hranice súladu so službou Dynamics 365 Customer Insights vrátane potenciálne citlivých údajov, ako sú napríklad osobné údaje. Spoločnosť Microsoft prenesie tieto údaje na váš pokyn, ale vy ste zodpovední za zabezpečenie toho, aby spoločnosť Mailchimp plnila všetky prípadné povinnosti týkajúce sa ochrany vašich osobných údajov alebo zabezpečenia. Ďalšie informácie nájdete vo [vyhlásení o ochrane súkromia spoločnosti Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Váš správca služby Dynamics 365 Customer Insights môže túto funkciu kedykoľvek prestať používať odstránením tohto cieľového umiestnenia exportu.


[!INCLUDE[footer-include](../includes/footer-banner.md)]