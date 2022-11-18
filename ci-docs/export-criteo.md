---
title: Export segmentov do Criteo (ukážka)
description: Zistite, ako nakonfigurovať pripojenie a exportovať do Criteo.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 811752da943cd5e40608d48644a1744c7971d3c8
ms.sourcegitcommit: 40ae3322ac95913e485607494754dd03814e42bb
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 11/11/2022
ms.locfileid: "9760045"
---
# <a name="export-segments-to-criteo-preview"></a>Export segmentov do Criteo (ukážka)

Exportujte segmenty zjednotených zákazníckych profilov na generovanie kampaní, poskytovanie e-mailového marketingu a používanie špecifických skupín zákazníkov s Criteo.

## <a name="prerequisites"></a>Požiadavky

- A [Criteo Dynamics Retargeting účet](https://www.criteo.com/login/) a zodpovedajúce poverenia správcu.
- [Konfigurované segmenty](segments.md).
- Zjednotené profily zákazníkov v exportovaných segmentoch obsahujú pole predstavujúce e-mailovú adresu.

## <a name="known-limitations"></a>Známe obmedzenia

- Až 1 milión zákazníckych profilov na export do Criteo, ktorého dokončenie môže trvať až 30 minút. Počet zákazníckych profilov, ktoré môžete exportovať do Criteo, závisí od vašej zmluvy s Criteo.
- Iba segmenty.

## <a name="set-up-connection-to-criteo"></a>Nastavte pripojenie k Criteo

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Prejdite do časti **Správca** > **Pripojenia**.

1. Vyberte **Pridať pripojenie** a vyberte si **Criteo**.

1. Do poľa **Zobrazovaný názov** zadajte rozpoznateľný názov pripojenia. Zobrazovaný názov a typ spojenia, ktoré popisuje toto spojenie. Odporúčame zvoliť názov, ktorý vysvetľuje účel a cieľ tohto spojenia.

1. Vyberte používateľov, ktorí môžu používať toto pripojenie. Predvolene sú to iba správcovia. Viac informácií nájdete v časti [Umožnite prispievateľom použiť pripojenie na export](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Skontrolujte [ochrana osobných údajov a dodržiavanie predpisov](connections.md#data-privacy-and-compliance) a vyberte **Súhlasím** .

1. Vyberte **Pripojte sa** na inicializáciu pripojenia.

1. Vyberte **Overte sa pomocou Criteo** a zadajte svoje používateľské meno správcu a poverenia pre Criteo.

1. Vyberte položku **Pridať samého seba ako používateľa exportu** a uveďte svoje poverenia pre Customer Insights.

1. Stlačte možnosť **Uložiť** a dokončite pripojenie.

## <a name="configure-an-export"></a>Nakonfigurujte export

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Prejdite na **Údaje** > **Exporty**.

1. Vyberte **Pridať export** .

1. V **Pripojenie na export** vyberte spojenie zo sekcie Criteo. Ak nie je k dispozícii pripojenie, kontaktujte správcu.

1. Zadajte názov exportu.

1. V sekcii **Párovanie údajov** v poli **E-mail** vyberte pole, ktoré predstavuje e-mailovú adresu zákazníka.

1. Vyberte segmenty, ktoré chcete exportovať.

1. Vyberte **Uložiť**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
