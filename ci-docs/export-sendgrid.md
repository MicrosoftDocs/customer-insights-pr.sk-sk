---
title: Export segmentov do SendGrid (ukážka)
description: Zistite ako nakonfigurovať pripojenie a realizovať exportovanie do SendGrid.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: f2990ad410dda0cbf952f82f3fc30b3a53a7bcd4
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 07/27/2022
ms.locfileid: "9197011"
---
# <a name="export-segments-to-sendgrid-preview"></a>Export segmentov do SendGrid (ukážka)

Exportujte segmenty zjednotených profilov zákazníkov do zoznamov kontaktov SendGrid a použite ich pre kampane a e-mailový marketing v SendGrid.

## <a name="prerequisites"></a>Požiadavky

- A [Účet SendGrid](https://sendgrid.com/) a zodpovedajúce poverenia správcu.
- [Existujúce zoznamy kontaktov v SendGrid](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts) a príslušné ID.
- A [SendGrid API kľúč](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).
- [Konfigurované segmenty](segments.md) v Customer Insights.
- Zjednotené profily zákazníkov v exportovaných segmentoch obsahujú pole predstavujúce e-mailovú adresu.

## <a name="known-limitations"></a>Známe obmedzenia

- Celkovo až 100 000 zákazníckych profilov do SendGrid, čo môže trvať až niekoľko hodín. Počet zákazníckych profilov, ktoré môžete exportovať do SendGrid, závisí od vašej zmluvy so SendGrid.
- Iba segmenty.

## <a name="set-up-connection-to-sendgrid"></a>Nastavenie pripojenia k SendGrid

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Prejdite do časti **Správca** > **Pripojenia**.

1. Vyberte **Pridať pripojenie** a vyberte si **SendGrid**.

1. Do poľa **Zobrazovaný názov** zadajte rozpoznateľný názov pripojenia. Zobrazovaný názov a typ spojenia, ktoré popisuje toto spojenie. Odporúčame zvoliť názov, ktorý vysvetľuje účel a cieľ tohto spojenia.

1. Vyberte používateľov, ktorí môžu používať toto pripojenie. Predvolene sú to iba správcovia. Viac informácií nájdete v časti [Umožnite prispievateľom použiť pripojenie na export](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Zadajte svoje **SendGrid API kľúč**.

1. Skontrolujte [ochrana osobných údajov a dodržiavanie predpisov](connections.md#data-privacy-and-compliance) a vyberte **Súhlasím**.

1. Vyberte **Pripojte sa** na inicializáciu pripojenia.

1. Vyberte položku **Pridať samého seba ako používateľa exportu** a uveďte svoje poverenia pre Customer Insights.

1. Stlačte možnosť **Uložiť** a dokončite pripojenie.

## <a name="configure-an-export"></a>Nakonfigurujte export

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Prejdite na **Údaje** > **Exporty**.

1. Vyberte **Pridať export**.

1. V poli **Pripojenie na export** vyberte pripojenie v časti SendGrid. Ak nie je k dispozícii pripojenie, kontaktujte správcu.

1. Zadajte názov exportu.

1. Zadajte svoje **ID zoznamu SendGrid**.

1. V sekcii **Párovanie údajov** v poli **E-mail** vyberte pole, ktoré predstavuje e-mailovú adresu zákazníka.

1. Voliteľne vyberte polia ako napr **krstné meno**, **·**, **/región**, **·**, **·**, a **PSČ**.

1. Podľa známych obmedzení vyberte segmenty, ktoré chcete exportovať.

1. Vyberte **Uložiť**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
