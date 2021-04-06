---
title: Export údajov služby Customer Insights do SendGrid
description: Zistite, ako môžete nakonfigurovať pripojenie k SendGrid.
ms.date: 12/08/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 1a1f679fa42d47d524ebfdd6e931ae2822565f77
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597300"
---
# <a name="connector-for-sendgrid-preview"></a>Konektor pre SendGrid (ukážka)

Exportujte segmenty zjednotených profilov zákazníkov do zoznamov kontaktov SendGrid a použite ich pre kampane a e-mailový marketing v SendGrid. 

## <a name="prerequisites"></a>Predpoklady

-   Máte [účet SendGrid](https://sendgrid.com/) a zodpovedajúce poverenia správcu.
-   V službe SendGrid existujú zoznamy kontaktov a zodpovedajúce ID. Ďalšie informácie nájdete v časti [SendGrid – spravovanie kontaktov](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts).
-   Máte [konfigurované segmenty](segments.md) v prehľadoch cieľových skupín.
-   Zjednotené profily zákazníkov v exportovaných segmentoch obsahujú pole predstavujúce e-mailovú adresu.

## <a name="connect-to-sendgrid"></a>Pripojenie k SendGrid

1. Prejdite do ponuky **Správca** > **Ciele exportu**.

1. V časti **SendGrid** vyberte položku **Nastaviť**.

1. Do poľa **Zobrazovaný názov** zadajte rozpoznateľný názov cieľa exportu.

   :::image type="content" source="media/export-sendgrid.PNG" alt-text="Tabla konfigurácie exportu SendGrid.":::

1. Zadajte svoj **Kľúč API SendGrid** [Kľúč API SendGrid](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).

1. Zadajte svoje **[ID zoznamu SendGrid](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)**.

1. Vyberte **Súhlasím** na potvrdenie **Ochrany osobných údajov a dodržiavanie súladu s nariadeniami**.

1. Vyberte položku **Pripojiť** na inicializáciu pripojenia k SendGrid.

1. Vyberte položku **Pridať samého seba ako používateľa exportu** a uveďte svoje poverenia pre Customer Insights.

1. Vyberte **Ďalej** a nakonfigurujte export.

## <a name="configure-the-connector"></a>Nakonfigurujte konektor

1. V sekcii **Párovanie údajov** v poli **E-mail** do svojho zjednoteného profilu zákazníka vyberte pole, ktoré predstavuje e-mailovú adresu zákazníka. Rovnaký postup zopakujte pri ďalších voliteľných poliach, ako je **Krstné meno**, **Priezvisko**, **Krajina/región**, **Štát**, **Mesto** a **PSČ**.

1. Vyberte segmenty, ktoré chcete exportovať. Dôrazne **odporúčame neexportovať celkovo viac ako 100 000 profilov zákazníkov** do SendGrid. 

1. Vyberte položku **Uložiť**.

## <a name="export-the-data"></a>Export údajov

Môžete [exportovať údaje na vyžiadanie](export-destinations.md). Export sa spustí aj pri každej [plánovanej obnove](system.md#schedule-tab).

## <a name="known-limitations"></a>Známe obmedzenia

- Až 100 000 profilov celkovo do služby SendGrid.
- Export do SendGrid je obmedzený na segmenty.
- Export až 100 000 profilov do služby SendGrid môže trvať až niekoľko hodín. 
- Počet profilov, ktoré môžete exportovať do SendGrid, závisí a je obmedzený vašou zmluvou so spoločnosťou SendGrid.

## <a name="data-privacy-and-compliance"></a>Ochrana osobných údajov a dodržiavanie súladu s nariadeniami

Keď povolíte službe Dynamics 365 Customer Insights prenos údajov do SendGrid, povoľujete tým prenos údajov mimo hranice súladu so službou Dynamics 365 Customer Insights vrátane potenciálne citlivých údajov, ako sú napríklad osobné údaje. Spoločnosť Microsoft prenesie tieto údaje na váš pokyn, ale vy ste zodpovední za zabezpečenie toho, aby SendGrid plnila všetky prípadné povinnosti týkajúce sa ochrany vašich osobných údajov alebo zabezpečenia. Ďalšie informácie nájdete vo [vyhlásení o ochrane súkromia spoločnosti Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Váš správca služby Dynamics 365 Customer Insights môže túto funkciu kedykoľvek prestať používať odstránením tohto cieľového umiestnenia exportu.


[!INCLUDE[footer-include](../includes/footer-banner.md)]