---
title: Export údajov z Customer Insights do Klaviyo
description: Zistite, ako nakonfigurovať pripojenie a exportovať do Klaviyo.
ms.date: 08/13/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 7c1297fd5381c00c07d6501186c51fe4798773d1
ms.sourcegitcommit: 205f931ec671a0ab1850f2c1c94df3307ffb62c9
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 08/13/2021
ms.locfileid: "7385807"
---
# <a name="export-segment-lists-to-klaviyo-preview"></a>Exportovať zoznamy segmentov do Klaviyo (ukážka)

Exportujte segmenty zjednotených profilov zákazníkov do Klaviyo a použite ich na marketingové aktivity.

## <a name="prerequisites"></a>Predpoklady

-   Máte [účet Klaviyo](https://www.klaviyo.com/) a zodpovedajúce poverenia správcu.
-   Máte [konfigurované segmenty](segments.md) v prehľadoch cieľových skupín.
-   Zjednotené profily zákazníkov v exportovaných segmentoch obsahujú pole predstavujúce e-mailovú adresu.

## <a name="known-limitations"></a>Známe obmedzenia

- Na Klaviyo môžete exportovať až 100 000 profilov na export.
- Export do Klaviyo je obmedzený na segmenty.
- Export až 1 milión profilov do služby Klaviyo môže trvať až 20 minút. 
- Počet profilov, ktoré môžete exportovať do Klaviyo, ovplyvňuje a limituje vaša zmluva so spoločnosťou Klaviyo.

## <a name="set-up-connection-to-klaviyo"></a>Nastavenie pripojenia k Klaviyo

1. Prejdite do časti **Správca** > **Pripojenia**.

1. Vyberte možnosť **Pridať pripojenie** a výberom položky **Klaviyo** nakonfigurujte pripojenie.

1. Do poľa **Zobrazovaný názov** zadajte rozpoznateľný názov pripojenia. Zobrazovaný názov a typ spojenia, ktoré popisuje toto spojenie. Odporúčame zvoliť názov, ktorý vysvetľuje účel a cieľ tohto spojenia.

1. Vyberte používateľov, ktorí môžu používať toto pripojenie. Ak neurobíte nič, predvolená hodnota bude Správcovia. Viac informácií nájdete v časti [Umožnite prispievateľom použiť pripojenie na export](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Poskytnite svoj [Kľúč API Klaviyo](https://help.klaviyo.com/hc/articles/115005062267-How-to-Manage-Your-Account-s-API-Keys) na pokračovanie v prihlasovaní. 

1. Vyberte **Súhlasím** na potvrdenie **Ochrany osobných údajov a dodržiavanie súladu s nariadeniami**.

1. Výberom možnosti **Pripojiť** nadviažete pripojenie ku Klaviyo.

1. Označte položku **Overiť cez Klaviyo** a poskytnite svoje poverenia správcu pre Klaviyo.

1. Vyberte položku **Pridať samého seba ako používateľa exportu** a uveďte svoje poverenia pre Customer Insights.

1. Stlačte možnosť **Uložiť** a dokončite pripojenie.

## <a name="configure-an-export"></a>Nakonfigurujte export

Tento export môžete nakonfigurovať, ak máte prístup k pripojeniu tohto typu. Viac informácií nájdete na stránke [Na konfiguráciu exportu sú potrebné povolenia](export-destinations.md#set-up-a-new-export).

1. Prejdite na **Údaje** > **Exporty**.

1. Na vytvorenie nového exportu stlačte možnosť **Pridať cieľ**.

1. V poli **Pripojenie na export** vyberte pripojenie zo sekcie Klaviyo. Ak nevidíte názov tejto sekcie, nemáte k dispozícii žiadne spojenia tohto typu.

1. Zadajte svoje [**ID zoznamu aplikácie Klaviyo**](https://help.klaviyo.com/hc/articles/115005078647-How-to-Find-a-List-ID).     

3. V sekcii **Párovanie údajov** v poli **E-mail** do svojho zjednoteného profilu zákazníka vyberte pole, ktoré predstavuje e-mailovú adresu zákazníka. Je to potrebné na export segmentov do Klaviyo.

1. Vyberte položku **Uložiť**.

Uloženie exportu nespustí export okamžite.

Export prebieha s každým [plánovaným obnovením](system.md#schedule-tab). Môžete tiež [exportovať údaje na požiadanie](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Ochrana osobných údajov a dodržiavanie súladu s nariadeniami

Keď povolíte službe Dynamics 365 Customer Insights, aby prenášala údaje do Klaviyo, povoľujete tým aj prenos údajov mimo hranice súladu so službou Dynamics 365 Customer Insights vrátane potenciálne citlivých údajov, ako sú napríklad osobné údaje. Microsoft prenesie tieto údaje na váš pokyn, ale vy ste zodpovední za zabezpečenie toho, aby Klaviyo spĺňal všetky záväzky týkajúce sa ochrany vášho súkromia alebo bezpečnosti. Ďalšie informácie nájdete vo [vyhlásení o ochrane súkromia spoločnosti Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).

Váš správca služby Dynamics 365 Customer Insights môže túto funkciu kedykoľvek prestať používať odstránením tohto cieľového umiestnenia exportu.
