---
title: Export segmentov do Constant Contact (verzia Preview)
description: Zistite ako nakonfigurovať pripojenie a realizovať exportovanie do Constant Contact.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 4d2ec29c194dc481ee40048b8ecbed813291b4d2
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196505"
---
# <a name="export-segments-to-constant-contact-preview"></a>Export segmentov do Constant Contact (verzia Preview)

Exportujte segmenty zjednotených profilov zákazníkov do Constant Contact a použite ich na marketingové aktivity.

## <a name="prerequisites"></a>Požiadavky

- A [Konto neustáleho kontaktu](https://www.constantcontact.com/account-home) a zodpovedajúce poverenia správcu.
- A [Identifikátor konštantného zoznamu kontaktov](https://app.constantcontact.com/pages/contacts/ui#lists). Otvorte zoznam v zozname Constant Contact a vyhľadajte identifikátor zoznamu v adrese URL.
- [Konfigurované segmenty](segments.md) v Customer Insights.
- Zjednotené profily zákazníkov v exportovaných segmentoch obsahujú pole predstavujúce e-mailovú adresu.

## <a name="known-limitations"></a>Známe obmedzenia

- Až 1 milión zákazníckych profilov na export do Constant Contact, ktorého dokončenie môže trvať až jednu hodinu. Počet zákazníckych profilov, ktoré môžete exportovať do Constant Contact, závisí od vašej zmluvy s Constant Contact.
- Iba segmenty.

## <a name="set-up-connection-to-constant-contact"></a>Nastavenie pripojenia do Constant Contact

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Prejdite do časti **Správca** > **Pripojenia**.

1. Vyberte **Pridať pripojenie** a vyberte si **Neustály kontakt**.

1. Do poľa **Zobrazovaný názov** zadajte rozpoznateľný názov pripojenia. Zobrazovaný názov a typ spojenia, ktoré popisuje toto spojenie. Odporúčame zvoliť názov, ktorý vysvetľuje účel a cieľ tohto spojenia.

1. Vyberte používateľov, ktorí môžu používať toto pripojenie. Predvolene sú to iba správcovia. Viac informácií nájdete v časti [Umožnite prispievateľom použiť pripojenie na export](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Skontrolujte [ochrana osobných údajov a dodržiavanie predpisov](connections.md#data-privacy-and-compliance) a vyberte **Súhlasím**.

1. Vyberte **Pripojte sa** na inicializáciu pripojenia.

1. Označte položku **Overiť cez Constant Contact** a poskytnite svoje poverenia správcu pre Constant Contact.

1. Vyberte položku **Pridať samého seba ako používateľa exportu** a uveďte svoje poverenia pre Customer Insights.

1. Stlačte možnosť **Uložiť** a dokončite pripojenie.

## <a name="configure-an-export"></a>Nakonfigurujte export

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Prejdite na **Údaje** > **Exporty**.

1. Vyberte **Pridať export**.

1. V poli **Pripojenie na export** vyberte pripojenie v časti Constant Contact. Ak nie je k dispozícii pripojenie, kontaktujte správcu.

1. Zadajte názov exportu.

1. Zadajte svoje **Identifikátor konštantného zoznamu kontaktov**.

1. V sekcii **Párovanie údajov** v poli **E-mail** vyberte pole, ktoré predstavuje e-mailovú adresu zákazníka.

1. Voliteľne exportujte **krstné meno** a **priezvisko** ako ďalšie polia na vytváranie prispôsobenejších e-mailov. Výberom položky **Pridať atribút** namapujete tieto polia.

1. Vyberte segmenty, ktoré chcete exportovať.

1. Vyberte **Uložiť**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
