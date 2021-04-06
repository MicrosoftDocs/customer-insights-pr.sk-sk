---
title: Export údajov služby Customer Insights do Autopilot
description: Zistite, ako môžete nakonfigurovať pripojenie k Autopilot.
ms.date: 12/08/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6d039c4afd84eaad942d214d4e6fb8ef7b1ec72a
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596150"
---
# <a name="connector-for-autopilot-preview"></a>Konektor pre Autopilot (ukážka)

Exportujte segmenty zjednotených profilov zákazníkov do služby Autopilot a použite ich na e-mailový marketing v službe Autopilot. 

## <a name="prerequisites"></a>Predpoklady

-   Máte [účet Autopilot](https://www.autopilothq.com/) a zodpovedajúce poverenia správcu.
-   Máte [konfigurované segmenty](segments.md) v prehľadoch cieľových skupín.
-   Zjednotené profily zákazníkov v exportovaných segmentoch obsahujú pole predstavujúce e-mailovú adresu.

## <a name="connect-to-autopilot"></a>Pripojenie k službe AutoPilot

1. Prejdite do ponuky **Správca** > **Ciele exportu**.

1. V časti **Autopilot** vyberte položku **Nastaviť**.

1. Do poľa **Zobrazovaný názov** zadajte rozpoznateľný názov cieľa exportu.

   :::image type="content" source="media/export-autopilot.PNG" alt-text="Konfiguračná tabla na pripojenie služby Autopilot.":::

1. Zadajte svoj **Kľúč API pre Autopilot** [Kľúč API pre Autopilot](https://autopilot.docs.apiary.io/#).

1. Vyberte **Súhlasím** na potvrdenie **Ochrany osobných údajov a dodržiavanie súladu s nariadeniami**.

1. Vyberte položku **Pripojiť** na inicializáciu pripojenia k Autopilot.

1. Vyberte položku **Pridať samého seba ako používateľa exportu** a uveďte svoje poverenia pre Customer Insights.

1. Vyberte **Ďalej** a nakonfigurujte export.

## <a name="configure-the-connector"></a>Nakonfigurujte konektor

1. V sekcii **Párovanie údajov** v poli **E-mail** do svojho zjednoteného profilu zákazníka vyberte pole, ktoré predstavuje e-mailovú adresu zákazníka. Rovnaký postup zopakujte pri ďalších voliteľných poliach, ako je **Krstné meno** a **Priezvisko**.

1. Vyberte segmenty, ktoré chcete exportovať. Dôrazne **odporúčame neexportovať celkovo viac ako 100 000 profilov zákazníkov** do Autopilot. 

1. Vyberte položku **Uložiť**.

## <a name="export-the-data"></a>Export údajov

Môžete [exportovať údaje na vyžiadanie](export-destinations.md). Export sa spustí aj pri každej [plánovanej obnove](system.md#schedule-tab).

## <a name="known-limitations"></a>Známe obmedzenia

- Do služby Autopilot môžete exportovať spolu až 100 000 profilov.
- Export do Autopilot je obmedzený na segmenty.
- Export až 100 000 profilov do služby Autopilot môže trvať až niekoľko hodín. 
- Počet profilov, ktoré môžete exportovať do Autopilot, závisí a je obmedzený vašou zmluvou so spoločnosťou Autopilot.

## <a name="data-privacy-and-compliance"></a>Ochrana osobných údajov a dodržiavanie súladu s nariadeniami

Keď povolíte prenos údajov spoločnosti Autopilot v službe Dynamics 365 Customer Insights, povoľujete tým prenos údajov mimo hranice súladu so službou Dynamics 365 Customer Insights vrátane potenciálne citlivých údajov, ako sú napríklad osobné údaje. Spoločnosť Microsoft prenesie tieto údaje na váš pokyn, ale vy ste zodpovední za zabezpečenie toho, aby spoločnosť Autopilot plnila všetky prípadné povinnosti týkajúce sa ochrany vašich osobných údajov alebo zabezpečenia. Ďalšie informácie nájdete vo [vyhlásení o ochrane súkromia spoločnosti Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Váš správca služby Dynamics 365 Customer Insights môže túto funkciu kedykoľvek prestať používať odstránením tohto cieľového umiestnenia exportu.


[!INCLUDE[footer-include](../includes/footer-banner.md)]