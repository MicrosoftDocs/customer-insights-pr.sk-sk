---
title: Export segmentov do Klaviyo (ukážka)
description: Zistite, ako nakonfigurovať pripojenie a exportovať do Klaviyo.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6e45ca5827afa29d97a746bd1a474c2346cc32d2
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196781"
---
# <a name="export-segments-to-klaviyo-preview"></a>Export segmentov do Klaviyo (ukážka)

Exportujte segmenty zjednotených profilov zákazníkov do Klaviyo a použite ich na marketingové aktivity.

## <a name="prerequisites"></a>Požiadavky

- A [Klaviyo účet](https://www.klaviyo.com/) a zodpovedajúce poverenia správcu.
- A [Klaviyo API kľúč](https://help.klaviyo.com/hc/articles/115005062267-How-to-Manage-Your-Account-s-API-Keys).
- A [ID zoznamu Klaviyo](https://help.klaviyo.com/hc/articles/115005078647-How-to-Find-a-List-ID).
- [Konfigurované segmenty](segments.md) v Customer Insights.
- Zjednotené profily zákazníkov v exportovaných segmentoch obsahujú pole predstavujúce e-mailovú adresu.

## <a name="known-limitations"></a>Známe obmedzenia

- Až 1 milión zákazníckych profilov na export do Klaviyo, ktorého dokončenie môže trvať až 20 minút. Počet zákazníckych profilov, ktoré môžete exportovať do Klaviyo, závisí od vašej zmluvy s Klaviyo.
- Iba segmenty.

## <a name="set-up-connection-to-klaviyo"></a>Nastavenie pripojenia k Klaviyo

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Prejdite do časti **Správca** > **Pripojenia**.

1. Vyberte **Pridať pripojenie** a vyberte si **Klaviyo**.

1. Do poľa **Zobrazovaný názov** zadajte rozpoznateľný názov pripojenia. Zobrazovaný názov a typ spojenia, ktoré popisuje toto spojenie. Odporúčame zvoliť názov, ktorý vysvetľuje účel a cieľ tohto spojenia.

1. Vyberte používateľov, ktorí môžu používať toto pripojenie. Predvolene sú to iba správcovia. Viac informácií nájdete v časti [Umožnite prispievateľom použiť pripojenie na export](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Poskytnite svoj Kľúč API Klaviyo na pokračovanie v prihlasovaní.

1. Skontrolujte [ochrana osobných údajov a dodržiavanie predpisov](connections.md#data-privacy-and-compliance) a vyberte **Súhlasím**.

1. Vyberte **Pripojte sa** na inicializáciu pripojenia.

1. Označte položku **Overiť cez Klaviyo** a poskytnite svoje poverenia správcu pre Klaviyo.

1. Vyberte položku **Pridať samého seba ako používateľa exportu** a uveďte svoje poverenia pre Customer Insights.

1. Stlačte možnosť **Uložiť** a dokončite pripojenie.

## <a name="configure-an-export"></a>Nakonfigurujte export

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Prejdite na **Údaje** > **Exporty**.

1. Vyberte **Pridať export**.

1. V poli **Pripojenie na export** vyberte pripojenie zo sekcie Klaviyo. Ak nie je k dispozícii pripojenie, kontaktujte správcu.

1. Zadajte názov exportu.

1. Zadajte svoje **ID zoznamu Klaviyo**.

1. V sekcii **Párovanie údajov** v poli **E-mail** vyberte pole, ktoré predstavuje e-mailovú adresu zákazníka.

1. Vyberte segmenty, ktoré chcete exportovať.

1. Vyberte **Uložiť**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
