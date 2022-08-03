---
title: Export segmentov do ActiveCampaign
description: Zistite, ako nakonfigurovať pripojenie a exportovať do ActiveCampaign.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 178d2df8edf1abcec72664e19d73a88f2b97f12d
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195586"
---
# <a name="export-segments-to-activecampaign-preview"></a>Export segmentov do ActiveCampaign (verzia Preview)

Exportujte segmenty zjednotených profilov zákazníkov do ActiveCampaign a použite ich na marketingové aktivity.

## <a name="prerequisites"></a>Požiadavky

- An [účet ActiveCampaign](https://www.activecampaign.com/) a zodpovedajúce poverenia správcu.
- An [ID zoznamu aktívnych kampaní](https://help.activecampaign.com/hc/articles/360000030559-How-to-create-a-list-in-ActiveCampaign).
- An [Kľúč API ActiveCampaign](https://help.activecampaign.com/hc/articles/207317590-Getting-started-with-the-API#how-to-obtain-your-activecampaign-api-url-and-key) a názov hostiteľa koncového bodu REST.
- [Konfigurované segmenty](segments.md) v Customer Insights.
- Zjednotené profily zákazníkov v exportovaných segmentoch obsahujú pole predstavujúce e-mailovú adresu.

## <a name="known-limitations"></a>Známe obmedzenia

- Až 1 milión zákazníckych profilov na export do ActiveCampaign, ktorého dokončenie môže trvať až 90 minút. Počet profilov zákazníkov, ktoré môžete exportovať do služby ActiveCampaign, závisí od vašej zmluvy so spoločnosťou ActiveCampaign.
- Iba segmenty.

## <a name="set-up-connection-to-activecampaign"></a>Nastavenie pripojenia k ActiveCampaign

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Prejdite do časti **Správca** > **Pripojenia**.

1. Vyberte **Pridať pripojenie** a vyberte si **Aktívna kampaň**.

1. Do poľa **Zobrazovaný názov** zadajte rozpoznateľný názov pripojenia. Zobrazovaný názov a typ spojenia, ktoré popisuje toto spojenie. Odporúčame zvoliť názov, ktorý vysvetľuje účel a cieľ tohto spojenia.

1. Vyberte používateľov, ktorí môžu používať toto pripojenie. Predvolene sú to iba správcovia. Viac informácií nájdete v časti [Umožnite prispievateľom použiť pripojenie na export](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Zadajte svoj kľúč rozhrania API ActiveCampaign a názov hostiteľa koncového bodu REST. Názov hostiteľa koncového bodu REST je iba názov hostiteľa bez https://.

1. Skontrolujte [ochrana osobných údajov a dodržiavanie predpisov](connections.md#data-privacy-and-compliance) a vyberte **Súhlasím**.

1. Vyberte **Pripojte sa** na inicializáciu pripojenia.

1. Vyberte položku **Pridať samého seba ako používateľa exportu** a uveďte svoje poverenia pre Customer Insights.

1. Stlačte možnosť **Uložiť** a dokončite pripojenie.

## <a name="configure-an-export"></a>Nakonfigurujte export

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Prejdite na **Údaje** > **Exporty**.

1. Vyberte **Pridať export**.

1. V poli **Pripojenie na export** vyberte pripojenie zo sekcie ActiveCampaign. Ak nie je k dispozícii pripojenie, kontaktujte správcu.

1. Zadajte názov exportu.

1. Zadajte svoje **ID zoznamu aktívnych kampaní**.

1. V sekcii **Párovanie údajov** v poli **E-mail** vyberte pole, ktoré predstavuje e-mailovú adresu zákazníka.

1. Voliteľne exportujte **krstné meno**, **·**, a **Telefón** na vytváranie prispôsobenejších e-mailov. Výberom položky **Pridať atribút** namapujete tieto polia.

1. Vyberte segmenty, ktoré chcete exportovať.

1. Vyberte **Uložiť**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
