---
title: Export segmentov do služby Microsoft Advertising (verzia Preview)
description: Zistite ako nakonfigurovať pripojenie a realizovať exportovanie do Microsoft Advertising.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 44217e7823ffbe14d232b3e33de1b4ea6ed69dcf
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196551"
---
# <a name="export-segments-to-microsoft-advertising-preview"></a>Export segmentov do služby Microsoft Advertising (verzia Preview)

Exportujte segmenty Customer Insights do služby Microsoft Advertising a vytvorte cieľovú skupinu súladu so zákazníkmi. Použite tieto cieľové skupiny pre svoje reklamné kampane.

## <a name="prerequisites"></a>Požiadavky

- A [Účet Microsoft Advertising](https://ads.microsoft.com/) a zodpovedajúce poverenia správcu.
- ID zákazníka a ID účtu služby Microsoft Advertising. Nájdite ID zákazníka (`cid`) a ID účtu (`aid`) v parametroch adresy URL, keď ste prihlásení do služby Microsoft Advertising.
- Podmienky používania Vlastných zoznamov zákazníkov sú akceptované.
- [Konfigurované segmenty](segments.md) v Customer Insights.
- Zjednotené profily zákazníkov v exportovaných segmentoch obsahujú pole predstavujúce e-mailovú adresu.

## <a name="known-limitations"></a>Známe obmedzenia

- Až 500 000 profilov zákazníkov na export do služby Microsoft Advertising, čo môže trvať až 10 minút.
- Iba segmenty.

## <a name="set-up-connection-to-microsoft-advertising"></a>Nastavte pripojenie k službe Microsoft Advertising

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Prejdite do časti **Správca** > **Pripojenia**.

1. Vyberte **Pridať pripojenie** a vyberte si **Microsoft Advertising**.

1. Do poľa **Zobrazovaný názov** zadajte rozpoznateľný názov pripojenia. Zobrazovaný názov a typ spojenia, ktoré popisuje toto spojenie. Odporúčame zvoliť názov, ktorý vysvetľuje účel a cieľ tohto spojenia.

1. Vyberte používateľov, ktorí môžu používať toto pripojenie. Predvolená hodnota je správcovia. Viac informácií nájdete v časti [Umožnite prispievateľom použiť pripojenie na export](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Zadajte **ID zákazníka služby Microsoft Advertising**.

1. Skontrolujte [ochrana osobných údajov a dodržiavanie predpisov](connections.md#data-privacy-and-compliance) a vyberte **Súhlasím**.

1. Vyberte **Pripojte sa** na inicializáciu pripojenia.

1. Stlačte možnosť **Overenie pomocou služby Microsoft Advertising** a zadajte svoje poverenia správcu pre Microsoft Advertising.

1. Vyberte položku **Pridať samého seba ako používateľa exportu** a uveďte svoje poverenia pre Customer Insights.

1. Stlačte možnosť **Uložiť** a dokončite pripojenie.

## <a name="configure-an-export"></a>Nakonfigurujte export

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Prejdite na **Údaje** > **Exporty**.

1. Vyberte **Pridať export**.

1. V poli **Pripojenie na export** vyberte pripojenie v časti Microsoft Advertising. Ak nie je k dispozícii pripojenie, kontaktujte správcu.

1. Zadajte názov exportu.

1. Vyberte segmenty, ktoré chcete exportovať. Cieľové skupiny súladu so zákazníkmi v službe Microsoft Advertising sa automaticky vytvárajú s názvom segmentov vybratých na export. Výsledkom každého segmentu bude samostatná cieľová skupina súladu so zákazníkmi.

1. Zadajte svoje **ID zákazníka Microsoft Advertising a ID konta**.

1. V sekcii **Párovanie údajov** v poli **E-mail** vyberte pole s e-mailovou adresou zákazníka.

1. Vyberte **Uložiť**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
