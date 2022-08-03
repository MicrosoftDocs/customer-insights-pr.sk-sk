---
title: Export segmentov do Snapchat (verzia Preview)
description: Zistite ako nakonfigurovať pripojenie a realizovať exportovanie do Snapchat.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 85443dcb54ebd58182997fbb56a738901f2a051f
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195401"
---
# <a name="export-segments-to-snapchat-preview"></a>Export segmentov do Snapchat (verzia Preview)

Exportujte segmenty zjednotených profilov zákazníkov do Snapchat a použite ich na reklamu.

## <a name="prerequisites"></a>Požiadavky

- A [Snapchat Business účet](https://business.snapchat.com/), a [Účet Snapchat Ads](https://ads.snapchat.com/) a zodpovedajúce poverenia správcu. Musíte byť aspoň členom účtu organizácie a správcom údajov konkrétneho účtu reklamy.
- Aspoň jedno publikum v Snapchat Audience manager typu SAM (Snap Audience Match).
- The [ID segmentu/publika Snapchat](https://businesshelp.snapchat.com/s/article/custom-audiences). ID publika nájdete v URL po výbere publika v Snapchat Audience Manager.
- [Konfigurované segmenty](segments.md) v Customer Insights.
- Zjednotené profily zákazníkov v exportovaných segmentoch obsahujú pole predstavujúce e-mailovú adresu.

## <a name="known-limitations"></a>Známe obmedzenia

- Až 1 milión zákazníckych profilov, ktorých vyplnenie môže trvať až 15 minút.
- Iba segmenty.

## <a name="set-up-connection-to-snapchat"></a>Nastavenie pripojenia k Snapchat

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Prejdite do časti **Správca** > **Pripojenia**.

1. Vyberte **Pridať pripojenie** a vyberte si **Snapchat**.

1. Do poľa **Zobrazovaný názov** zadajte rozpoznateľný názov pripojenia. Zobrazovaný názov a typ spojenia, ktoré popisuje toto spojenie. Odporúčame zvoliť názov, ktorý vysvetľuje účel a cieľ tohto spojenia.

1. Vyberte používateľov, ktorí môžu používať toto pripojenie. Predvolene sú to iba správcovia. Viac informácií nájdete v časti [Umožnite prispievateľom použiť pripojenie na export](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Skontrolujte [ochrana osobných údajov a dodržiavanie predpisov](connections.md#data-privacy-and-compliance) a vyberte **Súhlasím**.

1. Vyberte **Pripojte sa** na inicializáciu pripojenia.

1. Stlačte možnosť **Overenie pomocou služby Snapchat** a zadajte svoje poverenia správcu pre Snapchat.

1. Vyberte položku **Pridať samého seba ako používateľa exportu** a uveďte svoje poverenia pre Customer Insights.

1. Stlačte možnosť **Uložiť** a dokončite pripojenie.

## <a name="configure-an-export"></a>Nakonfigurujte export

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Prejdite na **Údaje** > **Exporty**.

1. Vyberte **Pridať export**.

1. V poli **Pripojenie na export** vyberte pripojenie v časti Snapchat. Ak nie je k dispozícii pripojenie, kontaktujte správcu.

1. Zadajte názov exportu.

1. Zadajte **ID segmentu/publika Snapchat**.

1. V sekcii **Párovanie údajov** v poli **E-mail** vyberte pole, ktoré predstavuje e-mailovú adresu zákazníka.

1. Vyberte segmenty, ktoré chcete exportovať.

1. Vyberte **Uložiť**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
