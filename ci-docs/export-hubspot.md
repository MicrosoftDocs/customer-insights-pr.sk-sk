---
title: Exportujte údaje Customer Insights do HubSpot
description: Zistite, ako nakonfigurovať pripojenie a exportovať do HubSpot.
ms.date: 09/23/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 0281be288b2c4d9e5da7ad8e2ed25f7b51b8498e
ms.sourcegitcommit: f959c85871777e5f4eab289e91b2fd114cd72153
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 09/23/2022
ms.locfileid: "9588938"
---
# <a name="export-segments-to-hubspot-preview"></a>Export segmentov do HubSpot (ukážka)

Exportujte segmenty zjednotených zákazníckych profilov do HubSpot a použite ich na e-mailový marketing.

## <a name="prerequisites-for-a-connection"></a>Predpoklad na pripojenie

- A [účet HubSpot](https://www.hubspot.com/) a zodpovedajúce poverenia správcu.
- [API kľúč](https://knowledge.hubspot.com/Integrations/How-do-I-get-my-HubSpot-API-key) z HubSpot.
- [Konfigurované segmenty](segments.md) v Customer Insights.

## <a name="known-limitations"></a>Známe obmedzenia

- Až 100 000 zákazníckych profilov na export do HubSpot, ktorého dokončenie môže trvať až 15 minút. Počet zákazníckych profilov, ktoré môžete exportovať do HubSpot, závisí a je obmedzený na vašej zmluve s HubSpot.
- Iba segmenty.

## <a name="set-up-connection-to-hubspot"></a>Nastavte pripojenie k HubSpot

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Prejdite do časti **Správca** > **Pripojenia**.

1. Vyberte **Pridať pripojenie** a vyberte si **HubSpot** na konfiguráciu pripojenia.

1. Do poľa **Zobrazovaný názov** zadajte rozpoznateľný názov pripojenia. Zobrazovaný názov a typ spojenia, ktoré popisuje toto spojenie. Odporúčame zvoliť názov, ktorý vysvetľuje účel a cieľ tohto spojenia.

1. Vyberte používateľov, ktorí môžu používať toto pripojenie. Ak neurobíte nič, predvolená hodnota bude Správcovia. Viac informácií nájdete v časti [Umožnite prispievateľom použiť pripojenie na export](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Po zobrazení výzvy zadajte svoje poverenia HubSpot.

1. Skontrolujte [ochrana osobných údajov a dodržiavanie predpisov](connections.md#data-privacy-and-compliance) a vyberte **Súhlasím**.

1. Vyberte **Pripojte sa** na inicializáciu pripojenia k HubSpot.

1. Vyberte položku **Pridať samého seba ako používateľa exportu** a uveďte svoje poverenia pre Customer Insights.

1. Stlačte možnosť **Uložiť** a dokončite pripojenie.

## <a name="configure-an-export"></a>Nakonfigurujte export

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Prejdite na **Údaje** > **Exporty**.

1. Na vytvorenie nového exportu stlačte možnosť **Pridať export**.

1. V **Pripojenie na export** vyberte pripojenie zo sekcie HubSpot. Ak nevidíte názov tejto sekcie, nemáte k dispozícii žiadne spojenia tohto typu.

1. V sekcii **Párovanie údajov** v poli **E-mail** vyberte pole, ktoré predstavuje e-mailovú adresu zákazníka. Opakujte rovnaké kroky pre ďalšie voliteľné polia.

1. Vyberte segmenty, ktoré chcete exportovať.

1. Vyberte **Uložiť**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
