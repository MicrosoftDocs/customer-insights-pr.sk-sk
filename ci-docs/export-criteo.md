---
title: Exportujte údaje Customer Insights do Criteo
description: Zistite, ako nakonfigurovať pripojenie a exportovať do Criteo.
ms.date: 05/27/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 854f5f0c53f053fc5d742d69a045db1926fec00c
ms.sourcegitcommit: bf65bc0a54cdab71680e658e1617bee7b2c2bb68
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 05/27/2022
ms.locfileid: "8808800"
---
# <a name="export-segments-to-criteo-preview"></a>Export segmentov do Criteo (ukážka)

Exportujte segmenty zjednotených zákazníckych profilov na generovanie kampaní, poskytovanie e-mailového marketingu a používanie špecifických skupín zákazníkov s Criteo.

## <a name="prerequisites-for-connection"></a>Predpoklad na pripojenie

-   Máš [Criteo Dynamics Retargeting účet](https://www.criteo.com/login/) a zodpovedajúce poverenia správcu.
-   Máte [nakonfigurované segmenty](segments.md).
-   Zjednotené profily zákazníkov v exportovaných segmentoch obsahujú pole predstavujúce e-mailovú adresu.

## <a name="known-limitations"></a>Známe obmedzenia

- Až 1 milión zákazníckych profilov na export do Criteo.
- Export do Critea je obmedzený na segmenty.
- Export segmentov s celkovo 1 miliónom profilov zákazníkov môže trvať až 30 minút. 
- Počet zákazníckych profilov, ktoré môžete exportovať do Critea, závisí a je obmedzený na vašej zmluve so spoločnosťou Criteo.

## <a name="set-up-connection-to-criteo"></a>Nastavte pripojenie k Criteo

1. Prejdite do časti **Správca** > **Pripojenia**.

1. Vyberte **Pridať pripojenie** a vyberte si **Criteo** na konfiguráciu pripojenia.

1. Do poľa **Zobrazovaný názov** zadajte rozpoznateľný názov pripojenia. Zobrazovaný názov a typ spojenia, ktoré popisuje toto spojenie. Odporúčame zvoliť názov, ktorý vysvetľuje účel a cieľ tohto spojenia.

1. Vyberte používateľov, ktorí môžu používať toto pripojenie. Ak neurobíte nič, predvolená hodnota bude Správcovia. Viac informácií nájdete v časti [Umožnite prispievateľom použiť pripojenie na export](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Vyberte **Súhlasím** na potvrdenie **Ochrana osobných údajov a dodržiavanie predpisov** a vyberte **Pripojte sa** inicializovať pripojenie k Criteo.

1. Vyberte **Overte sa pomocou Criteo** a zadajte svoje používateľské meno správcu a poverenia pre Criteo. 

1. Vyberte položku **Pridať samého seba ako používateľa exportu** a uveďte svoje poverenia pre Customer Insights.

1. Stlačte možnosť **Uložiť** a dokončite pripojenie.

## <a name="configure-an-export"></a>Nakonfigurujte export

Tento export môžete nakonfigurovať, ak máte prístup k pripojeniu tohto typu. Viac informácií nájdete na stránke [Na konfiguráciu exportu sú potrebné povolenia](export-destinations.md#set-up-a-new-export).

1. Prejdite na **Údaje** > **Exporty**.

1. Na vytvorenie nového exportu stlačte možnosť **Pridať cieľ**.

1. V **Pripojenie na export** vyberte spojenie zo sekcie Criteo. Ak nevidíte názov tejto sekcie, nemáte k dispozícii žiadne spojenia tohto typu. 

1. V sekcii **Párovanie údajov** v poli **E-mail** vyberte pole, ktoré predstavuje e-mailovú adresu zákazníka. 

1. Voliteľne môžete exportovať **ID inzerenta** a **názov**

1. Vyberte segmenty, ktoré chcete exportovať. 

1. Vyberte **Uložiť**.

Uloženie exportu nespustí export okamžite.

Export prebieha s každým [plánovaným obnovením](system.md#schedule-tab). Môžete tiež [exportovať údaje na požiadanie](export-destinations.md#run-exports-on-demand). 

## <a name="data-privacy-and-compliance"></a>Ochrana osobných údajov a dodržiavanie súladu s nariadeniami

Keď povolíte Dynamics 365 Customer Insights na prenos údajov do spoločnosti Criteo povoľujete prenos údajov mimo hraníc súladu pre Dynamics 365 Customer Insights, vrátane potenciálne citlivých údajov, ako sú Osobné údaje. Spoločnosť Microsoft prenesie takéto údaje na váš pokyn, ale vy ste zodpovední za zabezpečenie toho, že Criteo spĺňa všetky vaše prípadné povinnosti týkajúce sa ochrany osobných údajov alebo zabezpečenia. Ďalšie informácie nájdete vo [vyhlásení o ochrane súkromia spoločnosti Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Váš správca služby Dynamics 365 Customer Insights môže túto funkciu kedykoľvek prestať používať odstránením tohto cieľového umiestnenia exportu.


[!INCLUDE[footer-include](includes/footer-banner.md)]
