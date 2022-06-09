---
title: Export údajov z Customer Insights do ActiveCampaign
description: Zistite, ako nakonfigurovať pripojenie a exportovať do ActiveCampaign.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 5d15b9bf7383d06070ac92d7a729fc6e6e00c9d7
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 04/27/2022
ms.locfileid: "8643412"
---
# <a name="export-segments-to-activecampaign-preview"></a>Export segmentov do ActiveCampaign (verzia Preview)

Exportujte segmenty zjednotených profilov zákazníkov do ActiveCampaign a použite ich na marketingové aktivity.

## <a name="prerequisites"></a>Predpoklady

-   Máte [účet ActiveCampaign](https://www.activecampaign.com/) a zodpovedajúce poverenia správcu.
-   Máš [nakonfigurované segmenty](segments.md) v Customer Insights.
-   Zjednotené profily zákazníkov v exportovaných segmentoch obsahujú pole s e-mailovou adresou.

## <a name="known-limitations"></a>Známe obmedzenia

- Môžete exportovať až 1 milión profilov zákazníkov na export do služby ActiveCampaign, čo môže trvať až 90 minút.
- Export do ActiveCampaign je obmedzený na segmenty.
- Počet profilov zákazníkov, ktoré môžete exportovať do služby ActiveCampaign, závisí od vašej zmluvy so spoločnosťou ActiveCampaign.

## <a name="set-up-connection-to-activecampaign"></a>Nastavenie pripojenia k ActiveCampaign

1. Prejdite do časti **Správca** > **Pripojenia**.

1. Vyberte možnosť **Pridať pripojenie** a výberom položky **ActiveCampaign** nakonfigurujte pripojenie.

1. Do poľa **Zobrazovaný názov** zadajte rozpoznateľný názov pripojenia. Zobrazovaný názov a typ spojenia, ktoré popisuje toto spojenie. Odporúčame zvoliť názov, ktorý vysvetľuje účel a cieľ tohto spojenia.

1. Vyberte používateľov, ktorí môžu používať toto pripojenie. Predvolene sú to iba správcovia. Viac informácií nájdete v časti [Umožnite prispievateľom použiť pripojenie na export](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Zadajte svoj [kľúč rozhrania API ActiveCampaign a názov hostiteľa koncového bodu REST](https://help.activecampaign.com/hc/articles/207317590-Getting-started-with-the-API#how-to-obtain-your-activecampaign-api-url-and-key). Názov hostiteľa koncového bodu REST je iba názov hostiteľa bez https://. 

1. Vyberte **Súhlasím** na potvrdenie **Ochrany osobných údajov a dodržiavanie súladu s nariadeniami**.

1. Výberom možnosti **Pripojiť** nadviažete pripojenie k ActiveCampaign.

1. Vyberte položku **Pridať samého seba ako používateľa exportu** a uveďte svoje poverenia pre Customer Insights.

1. Stlačte možnosť **Uložiť** a dokončite pripojenie.

## <a name="configure-an-export"></a>Nakonfigurujte export

Export môžete nakonfigurovať, ak máte prístup k pripojeniu tohto typu. Viac informácií nájdete na stránke [Na konfiguráciu exportu sú potrebné povolenia](export-destinations.md#set-up-a-new-export).

1. Prejdite na **Údaje** > **Exporty**.

1. Na vytvorenie nového exportu stlačte možnosť **Pridať cieľ**.

1. V poli **Pripojenie na export** vyberte pripojenie zo sekcie ActiveCampaign. Ak nevidíte názov tejto sekcie, nemáte k dispozícii žiadne spojenia tohto typu.

1. Zadajte svoje [**ID zoznamu aplikácie ActiveCampaign**](https://help.activecampaign.com/hc/articles/360000030559-How-to-create-a-list-in-ActiveCampaign).    

1. V sekcii **Párovanie údajov** v poli **E-mail** vyberte pole, ktoré predstavuje e-mailovú adresu zákazníka. Je to potrebné na export segmentov do ActiveCampaign. Prípadne môžete aj exportovať krstné meno, priezvisko a telefón, a vytvoriť tak prispôsobenejšie e-maily. Výberom položky Pridať atribút namapujete tieto polia.

1. Vyberte položku **Uložiť**.

Uloženie exportu nespustí export okamžite.

Export prebieha s každým [plánovaným obnovením](system.md#schedule-tab). Môžete tiež [exportovať údaje na požiadanie](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Ochrana osobných údajov a dodržiavanie súladu s nariadeniami

Keď povolíte službe Dynamics 365 Customer Insights, aby prenášala údaje do ActiveCampaign, povoľujete tým aj prenos údajov mimo hranice súladu so službou Dynamics 365 Customer Insights vrátane potenciálne citlivých údajov, ako sú napríklad osobné údaje. Microsoft prenesie tieto údaje na váš pokyn, ale vy ste zodpovední za zabezpečenie toho, aby ActiveCampaign spĺňal všetky záväzky týkajúce sa ochrany vášho súkromia alebo bezpečnosti. Ďalšie informácie nájdete vo [vyhlásení o ochrane súkromia spoločnosti Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).

Váš správca služby Dynamics 365 Customer Insights môže túto funkciu kedykoľvek prestať používať odstránením tohto cieľového umiestnenia exportu.