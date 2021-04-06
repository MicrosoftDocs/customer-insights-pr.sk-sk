---
title: Export údajov služby Customer Insights do AdRoll
description: Zistite, ako môžete nakonfigurovať pripojenie k AdRoll.
ms.date: 02/15/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6fedd549c2e7de362f36e3fb23d363200bb92a04
ms.sourcegitcommit: d24e52150fe5a4fab45128e12d6a03637771d9b9
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 03/19/2021
ms.locfileid: "5697093"
---
# <a name="connector-for-adroll-preview"></a>Konektor pre AdRoll (ukážka)

Exportujte segmenty zjednotených profilov zákazníkov do služby AdRoll a použite ich na reklamu. 

## <a name="prerequisites"></a>Predpoklady

-   Máte [účet AdRoll](https://www.adroll.com/) a zodpovedajúce poverenia správcu.
-   Máte [konfigurované segmenty](segments.md) v prehľadoch cieľových skupín.
-   Zjednotené profily zákazníkov v exportovaných segmentoch obsahujú pole predstavujúce e-mailovú adresu.

## <a name="connect-to-adroll"></a>Pripojenie k službe AdRoll

1. Prejdite do ponuky **Správca** > **Ciele exportu**.

1. V časti **AdRoll** vyberte položku **Nastaviť**.

1. Do poľa **Zobrazovaný názov** zadajte rozpoznateľný názov cieľa exportu.

   :::image type="content" source="media/AdRoll_config.PNG" alt-text="Konfiguračná tabla na pripojenie služby AdRoll.":::

1. Vyberte **Súhlasím** na potvrdenie **Ochrany osobných údajov a dodržiavanie súladu s nariadeniami**.

1. Vyberte položku **Pripojiť** na inicializáciu pripojenia k AdRoll.

1. Vyberte položku **Overenie pomocou AdRoll** a poskytnite svoje poverenia správcu pre AdRoll. 

1. Vyberte položku **Pridať samého seba ako používateľa exportu** a uveďte svoje poverenia pre Customer Insights.

1. Zadajte svoje **ID inzerenta AdRoll** [AdRoll inzerovateľný](https://help.adroll.com/hc/en-us/articles/212011838-Advertiser-Profiles).

1. Vyberte **Ďalej** a nakonfigurujte export.

## <a name="configure-the-connector"></a>Nakonfigurujte konektor

1. V sekcii **Párovanie údajov** v poli **E-mail** do svojho zjednoteného profilu zákazníka vyberte pole, ktoré predstavuje e-mailovú adresu zákazníka. Je potrebné exportovať segmenty do služby AdRoll.

1. Vyberte segmenty, ktoré chcete exportovať. Vyberte segment s najmenej 100 členmi. Menšie segmenty nemôžete exportovať. Maximálna veľkosť segmentu na export je 250 000 členov na export. 

1. Vyberte položku **Uložiť**.

## <a name="export-the-data"></a>Export údajov

Môžete [exportovať údaje na vyžiadanie](export-destinations.md). Export sa spustí aj pri každej [plánovanej obnove](system.md#schedule-tab).

## <a name="known-limitations"></a>Známe obmedzenia

- Do služby AdRoll môžete exportovať spolu až 250 000 profilov na export.
- Do služby AdRoll nemôžete exportovať segmenty s menej ako 100 profilmi. 
- Export do AdRoll je obmedzený na segmenty.
- Export až 250 000 profilov do služby AdRoll môže trvať až 10 minút. 
- Počet profilov, ktoré môžete exportovať do AdRoll, závisí a je obmedzený vašou zmluvou so spoločnosťou AdRoll.

## <a name="data-privacy-and-compliance"></a>Ochrana osobných údajov a dodržiavanie súladu s nariadeniami

Keď povolíte prenos údajov do AdRoll v službe Dynamics 365 Customer Insights, povoľujete tým prenos údajov mimo hranice súladu so službou Dynamics 365 Customer Insights vrátane potenciálne citlivých údajov, ako sú napríklad osobné údaje. Spoločnosť Microsoft prenesie tieto údaje na váš pokyn, ale vy ste zodpovední za zabezpečenie toho, aby AdRoll plnila všetky prípadné povinnosti týkajúce sa ochrany vašich osobných údajov alebo zabezpečenia. Ďalšie informácie nájdete vo [vyhlásení o ochrane súkromia spoločnosti Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).

Váš správca služby Dynamics 365 Customer Insights môže túto funkciu kedykoľvek prestať používať odstránením tohto cieľového umiestnenia exportu.
