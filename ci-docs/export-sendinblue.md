---
title: Export segmentov do Sendinblue (verzia Preview)
description: Zistite, ako nakonfigurovať pripojenie a exportovať do Sendinblue.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: fc4ac34c1de096e25ba6c374fe17b1da6b2f745f
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 10/27/2022
ms.locfileid: "9724913"
---
# <a name="export-segments-to-sendinblue-preview"></a>Export segmentov do Sendinblue (verzia Preview)

Sendinblue umožňuje export segmentov zjednotených zákazníkov na tvorbu kampaní, poskytovanie e-mailového marketingu a využívanie konkrétny skupín zákazníkov.

## <a name="prerequisites"></a>Požiadavky

- A [Účet Sendinblue](https://www.sendinblue.com/) a zodpovedajúce poverenia správcu.
- A [SendinBlue API kľúč](https://developers.sendinblue.com/docs/getting-started#:~:text=Get%20your%20API%20key&text=You%20can%20create%20one%20from,your%20settings%20This%20API%20key).
- Existujúce zoznamy v Sendinblue a zodpovedajúce ID.
- [Konfigurované segmenty](segments.md).
- Zjednotené profily zákazníkov v exportovaných segmentoch obsahujú pole predstavujúce e-mailovú adresu.

## <a name="known-limitations"></a>Známe obmedzenia

- Súkromný odkaz v kombinácii s Prineste si vlastný úložný priestor (BYOS) nie je podporovaný.
- Až 1 milión zákazníckych profilov na export do Sendinblue, ktorého dokončenie môže trvať až 90 minút. Počet zákazníckych profilov, ktoré môžete exportovať do Sendinblue, závisí od vašej zmluvy so Sendinblue.
- Iba segmenty.

## <a name="set-up-connection-to-sendinblue"></a>Nastavenie pripojenia k Sendinblue

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Prejdite do časti **Správca** > **Pripojenia**.

1. Vyberte **Pridať pripojenie** a vyberte si **Sendinblue**.

1. Do poľa **Zobrazovaný názov** zadajte rozpoznateľný názov pripojenia. Zobrazovaný názov a typ spojenia, ktoré popisuje toto spojenie. Odporúčame zvoliť názov, ktorý vysvetľuje účel a cieľ tohto spojenia.

1. Vyberte používateľov, ktorí môžu používať toto pripojenie. Predvolene sú to iba správcovia. Viac informácií nájdete v časti [Umožnite prispievateľom použiť pripojenie na export](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Zadajte svoje **SendinBlue API kľúč**.

1. Skontrolujte [ochrana osobných údajov a dodržiavanie predpisov](connections.md#data-privacy-and-compliance) a vyberte **Súhlasím**.

1. Vyberte **Pripojte sa** na inicializáciu pripojenia.

1. Vyberte položku **Pridať samého seba ako používateľa exportu** a uveďte svoje poverenia pre Customer Insights.

1. Stlačte možnosť **Uložiť** a dokončite pripojenie.

## <a name="configure-an-export"></a>Nakonfigurujte export

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Prejdite na **Údaje** > **Exporty**.

1. Vyberte **Pridať export**.

1. V poli **Pripojenie na export** vyberte pripojenie zo sekcie Sendinblue. Ak nie je k dispozícii pripojenie, kontaktujte správcu.

1. Zadajte názov exportu.

1. Zadajte svoje **ID zoznamu Sendinblue**.

1. V sekcii **Párovanie údajov** v poli **E-mail** vyberte pole, ktoré predstavuje e-mailovú adresu zákazníka.

1. Voliteľne exportujte **krstné meno**, **·**, a **Telefón** na vytváranie prispôsobenejších e-mailov. Výberom položky **Pridať atribút** namapujete tieto polia.

1. Vyberte segmenty, ktoré chcete exportovať.

1. Vyberte **Uložiť**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
