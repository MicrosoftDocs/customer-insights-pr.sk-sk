---
title: Export segmentov do Mailchimp (verzia Preview)
description: Zistite ako nakonfigurovať pripojenie a realizovať exportovanie do Mailchimp.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 54aec10e24b6356e2e4317cf33e740a1a086a2dd
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196873"
---
# <a name="export-segments-to-mailchimp-preview"></a>Export segmentov do Mailchimp (verzia Preview)

Exportujte segmenty zjednotených profilov zákazníkov do služby Mailchimp a vytvárajte bulletiny a e-mailové kampane.

## <a name="prerequisites"></a>Požiadavky

- A [Účet Mailchimp](https://mailchimp.com/) a zodpovedajúce poverenia správcu.
- [Existujúce publiká v Mailchimpe](https://mailchimp.com/help/create-audience/) a zodpovedajúce [ID publika](https://mailchimp.com/help/find-audience-id/).
- [Konfigurované segmenty](segments.md).
- Zjednotené profily zákazníkov v exportovaných segmentoch obsahujú pole predstavujúce e-mailovú adresu.

## <a name="known-limitations"></a>Známe obmedzenia

- Až 1 milión zákazníckych profilov na export do Mailchimpu, čo môže trvať až tri hodiny. Počet zákazníckych profilov, ktoré môžete exportovať do Mailchimpu, závisí od vašej zmluvy s Mailchimpom.
- Iba segmenty.

## <a name="set-up-connection-to-mailchimp"></a>Nastavenie pripojenia k Mailchimp

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Prejdite do časti **Správca** > **Pripojenia**.

1. Vyberte **Pridať pripojenie** a vyberte si **Mailchimp**.

1. Do poľa **Zobrazovaný názov** zadajte rozpoznateľný názov pripojenia. Zobrazovaný názov a typ spojenia, ktoré popisuje toto spojenie. Odporúčame zvoliť názov, ktorý vysvetľuje účel a cieľ tohto spojenia.

1. Vyberte používateľov, ktorí môžu používať toto pripojenie. Predvolene sú to iba správcovia. Viac informácií nájdete v časti [Umožnite prispievateľom použiť pripojenie na export](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Skontrolujte [ochrana osobných údajov a dodržiavanie predpisov](connections.md#data-privacy-and-compliance) a vyberte **Súhlasím**.

1. Vyberte **Pripojte sa** na inicializáciu pripojenia.

1. Vyberte položku **Overenie pomocou služby Mailchimp** a poskytnite svoje poverenia pre Mailchimp.

1. Vyberte položku **Pridať samého seba ako používateľa exportu** a uveďte svoje poverenia pre Customer Insights.

1. Stlačte možnosť **Uložiť** a dokončite pripojenie.

## <a name="configure-an-export"></a>Nakonfigurujte export

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Prejdite na **Údaje** > **Exporty**.

1. Vyberte **Pridať export**.

1. V poli **Pripojenie na export** vyberte pripojenie v časti Mailchimp. Ak nie je k dispozícii pripojenie, kontaktujte správcu.

1. Zadajte názov exportu.

1. Zadajte svoje **ID publika Mailchimp**.

1. V sekcii **Párovanie údajov** v poli **E-mail** vyberte pole, ktoré predstavuje e-mailovú adresu zákazníka.

1. Voliteľne exportujte **krstné meno** a **priezvisko** na vytváranie prispôsobenejších e-mailov. Výberom položky **Pridať atribút** namapujete tieto polia.

1. Vyberte segmenty, ktoré chcete exportovať.

1. Vyberte **Uložiť**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
