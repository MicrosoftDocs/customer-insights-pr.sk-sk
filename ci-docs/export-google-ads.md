---
title: Exportovať segmenty do služby Google Ads (ukážka)
description: Zistite ako nakonfigurovať pripojenie a realizovať exportovanie do Google Ads.
ms.date: 07/25/2022
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: a46623e609665f8031f223593a6644147e5209d8
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 10/27/2022
ms.locfileid: "9725097"
---
# <a name="export-segments-to-google-ads-preview"></a>Exportovať segmenty do služby Google Ads (ukážka)

Exportujte segmenty zjednotených profilov zákazníkov do zoznamu cieľových skupín pre Google Ads a použite ich na inzerciu v rámci služby Vyhľadávanie Google, Gmail, YouTube a Google Display Network.

## <a name="prerequisites"></a>Požiadavky

- A [účet Google Ads](https://ads.google.com/) a zodpovedajúce poverenia správcu.
- A [ID zákazníka Google Ads](https://support.google.com/google-ads/answer/1704344).
- Požiadavky na [Pravidlá pre zoznamy zákazníkov](https://support.google.com/adspolicy/answer/6299717) sú splnené.
- Požiadavky na [veľkosti remarketingových zoznamov](https://support.google.com/google-ads/answer/7558048) sú splnené.
- [Konfigurované segmenty](segments.md).
- Zjednotené profily zákazníkov v exportovaných segmentoch obsahujú polia predstavujúce e-mailovú adresu, telefón, ID mobilného inzerenta, ID používateľa tretej strany alebo adresu.

## <a name="known-limitations"></a>Známe obmedzenia

- Súkromný odkaz v kombinácii s Prineste si vlastný úložný priestor (BYOS) nie je podporovaný.
- Exportujte až 1 milión zákazníckych profilov na export do služby Google Ads, čo môže z dôvodu obmedzení na strane poskytovateľa trvať až 30 minút.
- Iba segmenty.
- Zhoda v službe Google Ads môže trvať až 48 hodín.

## <a name="set-up-connection-to-google-ads"></a>Nastavenie pripojenia do Google Ads

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Prejdite do časti **Správca** > **Pripojenia**.

1. Vyberte **Pridať pripojenie** a vyberte si **Google Ads**.

1. Do poľa **Zobrazovaný názov** zadajte rozpoznateľný názov pripojenia. Zobrazovaný názov a typ spojenia, ktoré popisuje toto spojenie. Odporúčame zvoliť názov, ktorý vysvetľuje účel a cieľ tohto spojenia.

1. Vyberte používateľov, ktorí môžu používať toto pripojenie. Predvolene sú to iba správcovia. Viac informácií nájdete v časti [Umožnite prispievateľom použiť pripojenie na export](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Zadajte svoje číslo zákazníka Google Ads.

1. Skontrolujte [ochrana osobných údajov a dodržiavanie predpisov](connections.md#data-privacy-and-compliance) a vyberte **Súhlasím**.

1. Vyberte položku **Overenie pomocou Reklám Google** a poskytnite svoje poverenia pre Reklamy Google.

1. Vyberte položku **Pridať samého seba ako používateľa exportu** a uveďte svoje poverenia pre Customer Insights.

1. Stlačte možnosť **Uložiť** a dokončite pripojenie.

## <a name="configure-an-export"></a>Nakonfigurujte export

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Prejdite na **Údaje** > **Exporty**.

1. Vyberte **Pridať export**.

1. V poli **Pripojenie na export** vyberte pripojenie v časti Google Ads. Ak nie je k dispozícii pripojenie, kontaktujte správcu.

1. Zadajte názov exportu.

1. Vyberte, či chcete použiť existujúce publikum alebo vytvoriť nové:
   - Ak chcete aktualizovať existujúce publikum Google Ads, zadajte svoje [ID publika Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns).
   - Ak chcete vytvoriť nové publikum, ponechajte pole Google Audience ID prázdne. Customer Insights automaticky vytvorí nové publikum vo vašom účte Google Ads a použije názov exportovaného segmentu.

1. V **Zhoda údajov** vyberte jedno alebo viac údajových polí na export a vyberte pole, ktoré predstavuje zodpovedajúce údajové polia v Customer Insights.

1. Vyberte segmenty, ktoré chcete exportovať.

1. Vyberte **Uložiť**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
