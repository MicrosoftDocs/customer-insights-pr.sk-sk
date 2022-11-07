---
title: Export segmentov do Marketo (ukážka)
description: Zistite ako nakonfigurovať pripojenie a realizovať exportovanie do Marketo.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: cba40b74b86a40fc41db856760c9361b755a8864
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 10/27/2022
ms.locfileid: "9724959"
---
# <a name="export-segments-to-marketo-preview"></a>Export segmentov do Marketo (ukážka)

Marketo umožňuje export zjednotených profilov zákazníkov s cieľom vytvárať kampane, poskytovať e-mailový marketing a využívať konkrétne skupiny zákazníkov.

## <a name="prerequisites"></a>Požiadavky

- A [Účet Marketo](https://login.marketo.com/) a zodpovedajúce poverenia správcu.
- A [ID klienta Marketo, tajný kľúč klienta a názov hostiteľa koncového bodu REST](https://developers.marketo.com/rest-api/authentication/).
- [Existujúce zoznamy v službe Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists) a príslušné ID.
- [Konfigurované segmenty](segments.md).
- Zjednotené profily zákazníkov v exportovaných segmentoch obsahujú pole predstavujúce e-mailovú adresu.

## <a name="known-limitations"></a>Známe obmedzenia

- Súkromný odkaz v kombinácii s Prineste si vlastný úložný priestor (BYOS) nie je podporovaný.
- Až 1 milión zákazníckych profilov na export do Marketo, čo môže trvať až 3 hodiny. Počet zákazníckych profilov, ktoré môžete exportovať do Marketo, závisí od vašej zmluvy so spoločnosťou Marketo.
- Iba segmenty.

## <a name="set-up-connection-to-marketo"></a>Nastavenie pripojenia k Marketo

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Prejdite do časti **Správca** > **Pripojenia**.

1. Vyberte **Pridať pripojenie** a vyberte si **Marketo**.

1. Do poľa **Zobrazovaný názov** zadajte rozpoznateľný názov pripojenia. Zobrazovaný názov a typ spojenia, ktoré popisuje toto spojenie. Odporúčame zvoliť názov, ktorý vysvetľuje účel a cieľ tohto spojenia.

1. Vyberte používateľov, ktorí môžu používať toto pripojenie. Predvolene sú to iba správcovia. Viac informácií nájdete v časti [Umožnite prispievateľom použiť pripojenie na export](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Zadajte svoje **ID klienta Marketo, tajný kľúč klienta a názov hostiteľa koncového bodu REST**. Názov hostiteľa koncového bodu REST je iba názov hostiteľa bez https://. Príklad: xyz-abc-123.mktorest.com.

1. Skontrolujte [ochrana osobných údajov a dodržiavanie predpisov](connections.md#data-privacy-and-compliance) a vyberte **Súhlasím**.

1. Vyberte **Pripojte sa** na inicializáciu pripojenia.

1. Vyberte položku **Pridať samého seba ako používateľa exportu** a uveďte svoje poverenia pre Customer Insights.

1. Stlačte možnosť **Uložiť** a dokončite pripojenie.

## <a name="configure-an-export"></a>Nakonfigurujte export

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Prejdite na **Údaje** > **Exporty**.

1. Vyberte **Pridať export**.

1. V poli **Pripojenie na export** vyberte pripojenie v časti Marketo. Ak nie je k dispozícii pripojenie, kontaktujte správcu.

1. Zadajte názov exportu.

1. Zadajte svoje **ID zoznamu Marketo**. ID zoznamu je čisto číselná hodnota. Ak je napríklad ID vášho zoznamu Marketo ST12345A7, odstráňte znak pred a za číslicami a zadajte *12345*.

1. V **Zhoda údajov** vyberte aspoň jedno pole, ktoré predstavuje e-mailovú adresu zákazníka alebo Marketo ID zákazníka.

1. Voliteľne exportujte **krstné meno**, **·**, **·**, **·**, a **Krajina/región** na vytváranie prispôsobenejších e-mailov. Výberom položky **Pridať atribút** namapujete tieto polia.

1. Vyberte segmenty, ktoré chcete exportovať.

1. Vyberte **Uložiť**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

V Markete nájdite svoje segmenty pod [Marketo zoznamy](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).

[!INCLUDE [footer-include](includes/footer-banner.md)]
