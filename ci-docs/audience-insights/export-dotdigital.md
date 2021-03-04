---
title: Export údajov služby Customer Insights do DotDigital
description: Zistite, ako môžete nakonfigurovať pripojenie k DotDigital.
ms.date: 11/14/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 573a22e24f84c65fc4d21faf823cace801cc7ea3
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269119"
---
# <a name="connector-for-dotdigital-preview"></a>Konektor pre DotDigital (ukážka)

Exportujte segmenty zjednotených profilov zákazníkov do adresárov DotDigital a použite ich na kampane, e-mailový marketing a na vytváranie segmentov zákazníkov cez DotDigital. 

## <a name="prerequisites"></a>Predpoklady

-   Máte [účet DotDigital](https://dotdigital.com/) a zodpovedajúce poverenia správcu.
-   V DotDigital a zodpovedajúcich ID existujú adresáre. ID nájdete v adrese URL, keď vyberiete a otvoríte adresár. Ďalšie informácie nájdete v [adresároch DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).
-   Máte [konfigurované segmenty](segments.md) v prehľadoch cieľových skupín.
-   Zjednotené profily zákazníkov v exportovaných segmentoch obsahujú pole predstavujúce e-mailovú adresu.

## <a name="connect-to-dotdigital"></a>Pripojiť k DotDigital

1. Prejdite do ponuky **Správca** > **Ciele exportu**.

1. V časti **DotDigital** vyberte položku **Nastaviť**.

1. Do poľa **Zobrazovaný názov** zadajte rozpoznateľný názov cieľa exportu.

   :::image type="content" source="media/DotDigital_config.PNG" alt-text="Konfiguračná tabla pre export do DotDigital.":::

1. Zadajte **používateľské meno a heslo pre DotDigital**.

1. Zadajte **[ID adresára DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**.

1. Vyberte **Súhlasím** na potvrdenie **Ochrany osobných údajov a dodržiavanie súladu s nariadeniami**.

1. Vyberte položku **Pripojiť** na inicializáciu pripojenia k DotDigital.

1. Vyberte položku **Pridať samého seba ako používateľa exportu** a uveďte svoje poverenia pre Customer Insights.

1. Vyberte **Ďalej** a nakonfigurujte export.

## <a name="configure-the-connector"></a>Nakonfigurujte konektor

1. V sekcii **Párovanie údajov** v poli **E-mail** do svojho zjednoteného profilu zákazníka vyberte pole, ktoré predstavuje e-mailovú adresu zákazníka. Rovnaký postup zopakujte pri ďalších voliteľných poliach, ako je **Krstné meno**, **Priezvisko**, **Celé meno**, **Rod** a **PSČ**.

1. Vyberte segmenty, ktoré chcete exportovať. Do DotDigital môžete exportovať spolu až 1 milión zákazníckych profilov.

1. Vyberte položku **Uložiť**.

## <a name="export-the-data"></a>Export údajov

Môžete [exportovať údaje na vyžiadanie](export-destinations.md). Export sa spustí aj pri každej [plánovanej obnove](system.md#schedule-tab). V DotDigital teraz nájdete svoje segmenty v [adresároch DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).

## <a name="known-limitations"></a>Známe obmedzenia

- Až 1 milión profilov na export do DotDigital.
- Export do DotDigital je obmedzený na segmenty.
- Export segmentov s celkovým počtom 1 miliónov profilov môže trvať až 3 hodiny z dôvodu obmedzení na strane poskytovateľa. 
- Počet profilov, ktoré môžete exportovať do DotDigital, závisí a je obmedzený vašou zmluvou so spoločnosťou DotDigital.

## <a name="data-privacy-and-compliance"></a>Ochrana osobných údajov a dodržiavanie súladu s nariadeniami

Keď povolíte prenos údajov spoločnosti DotDigital v službe Dynamics 365 Customer Insights, povoľujete tým prenos údajov mimo hranice súladu so službou Dynamics 365 Customer Insights vrátane potenciálne citlivých údajov, ako sú napríklad osobné údaje. Spoločnosť Microsoft prenesie tieto údaje na váš pokyn, ale vy ste zodpovední za zabezpečenie toho, aby spoločnosť DotDigital plnila všetky prípadné povinnosti týkajúce sa ochrany vašich osobných údajov alebo zabezpečenia. Ďalšie informácie nájdete vo [vyhlásení o ochrane súkromia spoločnosti Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Váš správca služby Dynamics 365 Customer Insights môže túto funkciu kedykoľvek prestať používať odstránením tohto cieľového umiestnenia exportu.


[!INCLUDE[footer-include](../includes/footer-banner.md)]