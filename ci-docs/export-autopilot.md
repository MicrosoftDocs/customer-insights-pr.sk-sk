---
title: Export segmentov do Autopilot (ukážka)
description: Zistite ako nakonfigurovať pripojenie a realizovať exportovanie do Autopilot.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: b4b14ba9de2c7e20175fac664a705f2212a411fd
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 10/27/2022
ms.locfileid: "9724821"
---
# <a name="export-segments-to-autopilot-preview"></a>Export segmentov do Autopilot (ukážka)

Exportujte segmenty zjednotených profilov zákazníkov do služby Autopilot a použite ich na e-mailový marketing v službe Autopilot.

## <a name="prerequisites-for-a-connection"></a>Predpoklad na pripojenie

- An [Účet autopilota](https://www.autopilothq.com/) a zodpovedajúce poverenia správcu.
- An [Autopilot API kľúč](https://autopilot.docs.apiary.io/#)
- [Konfigurované segmenty](segments.md) v Customer Insights.
- Zjednotené profily zákazníkov v exportovaných segmentoch obsahujú pole predstavujúce e-mailovú adresu.

## <a name="known-limitations"></a>Známe obmedzenia

- Súkromný odkaz v kombinácii s Prineste si vlastný úložný priestor (BYOS) nie je podporovaný.
- Až 100 000 profilov zákazníkov na export do Autopilota, ktorého dokončenie môže trvať až niekoľko hodín. Počet zákazníckych profilov, ktoré môžete exportovať do Autopilota, závisí od vašej zmluvy s Autopilotom.
- Iba segmenty.

## <a name="set-up-connection-to-autopilot"></a>Nastavenie pripojenia k Autopilot

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Prejdite do časti **Správca** > **Pripojenia**.

1. Vyberte **Pridať pripojenie** a vyberte si **Autopilot**.

1. Do poľa **Zobrazovaný názov** zadajte rozpoznateľný názov pripojenia. Zobrazovaný názov a typ spojenia, ktoré popisuje toto spojenie. Odporúčame zvoliť názov, ktorý vysvetľuje účel a cieľ tohto spojenia.

1. Vyberte používateľov, ktorí môžu používať toto pripojenie. Predvolene sú to iba správcovia. Viac informácií nájdete v časti [Umožnite prispievateľom použiť pripojenie na export](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Zadajte svoj kľúč API Autopilot.

1. Skontrolujte [ochrana osobných údajov a dodržiavanie predpisov](connections.md#data-privacy-and-compliance) a vyberte **Súhlasím**.

1. Vyberte **Pripojte sa** na inicializáciu pripojenia.

1. Vyberte položku **Pridať samého seba ako používateľa exportu** a uveďte svoje poverenia pre Customer Insights.

1. Stlačte možnosť **Uložiť** a dokončite pripojenie.

## <a name="configure-an-export"></a>Nakonfigurujte export

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Prejdite na **Údaje** > **Exporty**.

1. Vyberte **Pridať export**.

1. V poli **Pripojenie na export** vyberte pripojenie v časti Autopilot. Ak nie je k dispozícii pripojenie, kontaktujte správcu.

1. Zadajte názov exportu.

1. V sekcii **Párovanie údajov** v poli **E-mail** vyberte pole, ktoré predstavuje e-mailovú adresu zákazníka.

1. Voliteľne exportujte ďalšie polia ako napr **krstné meno** a **priezvisko**.

1. Vyberte segmenty, ktoré chcete exportovať, v súlade so známymi obmedzeniami.

1. Vyberte **Uložiť**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
