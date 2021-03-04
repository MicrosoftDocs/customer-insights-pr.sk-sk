---
title: Export údajov služby Customer Insights do Marketo
description: Zistite, ako môžete nakonfigurovať pripojenie k Marketo.
ms.date: 11/12/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: e0245f2d01aabc86f43532822c056965ff7ae67a
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267100"
---
# <a name="connector-for-marketo-preview"></a>Konektor pre Marketo (ukážka)

Marketo umožňuje export zjednotených profilov zákazníkov s cieľom vytvárať kampane, poskytovať e-mailový marketing a využívať konkrétne skupiny zákazníkov.

## <a name="prerequisites"></a>Predpoklady

-   Máte [účet Marketo](https://login.marketo.com/) a zodpovedajúce poverenia správcu.
-   V službe Marketo a zodpovedajúcich ID existujú zoznamy. Ďalšie informácie nájdete v téme [Zoznamy služby Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).
-   Máte [nakonfigurované segmenty](segments.md).
-   Zjednotené profily zákazníkov v exportovaných segmentoch obsahujú pole predstavujúce e-mailovú adresu.

## <a name="connect-to-marketo"></a>Pripojiť sa k poskytovateľovi obsahu Marketo

1. Prejdite do ponuky **Správca** > **Ciele exportu**.

1. V časti **Marketo** vyberte položku **Nastaviť**.

1. Do poľa **Zobrazovaný názov** zadajte rozpoznateľný názov cieľa exportu.

1. Zadajte svoje **[ID klienta Marketo, tajný kľúč klienta a názov hostiteľa koncového bodu REST](https://developers.marketo.com/rest-api/authentication/)**.

1. Zadajte svoje **[ID zoznamu Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)** 

1. Výberom položky **Súhlasím** potvrďte **Ochranu osobných údajov a dodržiavanie súladu s nariadeniami** a vyberte položku **Pripojiť** na inicializáciu pripojenia k službe Marketo.

1. Vyberte položku **Pridať samého seba ako používateľa exportu** a uveďte svoje poverenia pre Customer Insights.

   :::image type="content" source="media/export-connect-marketo.png" alt-text="Sníma obrazovky exportu pre pripojenie k Marketo":::

1. Vyberte **Ďalej** a nakonfigurujte export.

## <a name="configure-the-connector"></a>Nakonfigurujte konektor

1. V sekcii **Párovanie údajov** v poli **E-mail** do svojho zjednoteného profilu zákazníka vyberte pole, ktoré predstavuje e-mailovú adresu zákazníka. 

1. Prípadne môžete exportovať **Krstné meno**, **Priezvisko**, **Mesto**, **Štát** a **Krajina/Región** ako dodatočné polia na vytvorenie viac prispôsobených e-mailov. Výberom položky **Pridať atribút** namapujete tieto polia.

1. Vyberte segmenty, ktoré chcete exportovať. Do služby Marketo môžete exportovať spolu až 1 milión zákazníckych profilov.

   :::image type="content" source="media/export-segment-marketo.png" alt-text="Vyberte polia a segmenty, ktoré chcete exportovať do Marketo":::

1. Vyberte položku **Uložiť**.

## <a name="export-the-data"></a>Export údajov

Môžete [exportovať údaje na vyžiadanie](export-destinations.md). Export sa spustí aj pri každej [plánovanej obnove](system.md#schedule-tab). V službe Marketo teraz nájdete svoje segmenty v sekcii [Zoznamy Marketo](ttps://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).

## <a name="known-limitations"></a>Známe obmedzenia

- Až 1 milión profilov na export do Marketo.
- Export do Marketo je obmedzený na segmenty.
- Export segmentov s celkovým počtom 1 miliónov profilov môže trvať až 3 hodiny. 
- Počet profilov, ktoré môžete exportovať do Marketo, závisí a je obmedzený vašou zmluvou so spoločnosťou Marketo.

## <a name="data-privacy-and-compliance"></a>Ochrana osobných údajov a dodržiavanie súladu s nariadeniami

Keď povolíte prenos údajov spoločnosti Marketo v službe Dynamics 365 Customer Insights, povoľujete tým prenos údajov mimo hranice súladu so službou Dynamics 365 Customer Insights vrátane potenciálne citlivých údajov, ako sú napríklad osobné údaje. Spoločnosť Microsoft prenesie tieto údaje na váš pokyn, ale vy ste zodpovední za zabezpečenie toho, aby spoločnosť Marketo plnila všetky prípadné povinnosti týkajúce sa ochrany vašich osobných údajov alebo zabezpečenia. Ďalšie informácie nájdete vo [vyhlásení o ochrane súkromia spoločnosti Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Váš správca služby Dynamics 365 Customer Insights môže túto funkciu kedykoľvek prestať používať odstránením tohto cieľového umiestnenia exportu.


[!INCLUDE[footer-include](../includes/footer-banner.md)]