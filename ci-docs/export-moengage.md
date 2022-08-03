---
title: Export segmentov do MoEngage
description: Zistite, ako nakonfigurovať pripojenie a exportovať do MoEngage.
ms.date: 07/26/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: ffc591c01a5a9434cde41f2da25fa930a515b8c1
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 07/27/2022
ms.locfileid: "9199241"
---
# <a name="export-segments-to-moengage-preview"></a>Export segmentov do MoEngage (ukážka)

Exportujte segmenty zjednotených zákazníckych profilov do MoEngage a použite ich na e-mailový marketing v MoEngage.

## <a name="prerequisites-for-a-connection"></a>Predpoklad na pripojenie

- [účet MoEngage](https://www.moengage.com/) a zodpovedajúce poverenia správcu.
- MoEngage API kľúč z Nastavenia > API v MoEngage.
- [Konfigurované segmenty](segments.md) v Customer Insights.

## <a name="known-limitations"></a>Známe obmedzenia

- Až 100 000 zákazníckych profilov na export do MoEngage, čo môže trvať až 15 minút. Počet zákazníckych profilov, ktoré môžete exportovať do MoEngage, závisí od vašej zmluvy s MoEngage.
- Iba segmenty.

## <a name="set-up-connection-to-moengage"></a>Nastavte pripojenie k MoEngage

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Prejdite do časti **Správca** > **Pripojenia**.

1. Vyberte **Pridať pripojenie** a vyberte si **MoEngage** na konfiguráciu pripojenia.

1. Do poľa **Zobrazovaný názov** zadajte rozpoznateľný názov pripojenia. Zobrazovaný názov a typ spojenia, ktoré popisuje toto spojenie. Odporúčame zvoliť názov, ktorý vysvetľuje účel a cieľ tohto spojenia.

1. Vyberte používateľov, ktorí môžu používať toto pripojenie. Ak neurobíte nič, predvolená hodnota bude Správcovia. Viac informácií nájdete v časti [Umožnite prispievateľom použiť pripojenie na export](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Zadajte svoje [Identifikátor rozhrania API MoEngage a kľúč rozhrania API](https://developers.moengage.com/hc/articles/4404674776724-Overview#:~:text=Navigate%20to%20Settings%20%3E%20APIs%20%3E%20DATA,ID%20Password%20%2D%20DATA%20API%20KEY).

1. Skontrolujte [ochrana osobných údajov a dodržiavanie predpisov](connections.md#data-privacy-and-compliance) a vyberte **Súhlasím**.

1. Vyberte **Pripojte sa** na inicializáciu pripojenia k MoEngage.

1. Vyberte položku **Pridať samého seba ako používateľa exportu** a uveďte svoje poverenia pre Customer Insights.

1. Stlačte možnosť **Uložiť** a dokončite pripojenie.

## <a name="configure-an-export"></a>Nakonfigurujte export

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Prejdite na **Údaje** > **Exporty**.

1. Na vytvorenie nového exportu stlačte možnosť **Pridať export**.

1. V **Pripojenie na export** vyberte spojenie zo sekcie MoEngage. Ak nevidíte názov tejto sekcie, nemáte k dispozícii žiadne spojenia tohto typu.

1. V sekcii **Párovanie údajov** v poli **E-mail** vyberte pole, ktoré predstavuje e-mailovú adresu zákazníka. Opakujte rovnaké kroky pre ďalšie voliteľné polia.

1. Vyberte segmenty, ktoré chcete exportovať. Vytvoríme jeden alebo viac segmentov s rovnakým názvom ako vybrané segmenty v MoEngage pod **Segmenty** > **Vlastné segmenty**.

1. Vyberte **Uložiť**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
