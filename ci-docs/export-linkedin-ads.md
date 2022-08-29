---
title: Export segmentov do služby LinkedIn Ads (verzia Preview)
description: Zistite ako nakonfigurovať pripojenie a realizovať exportovanie do LinkedIn Ads.
ms.date: 08/12/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 4c3928e05db0ebda262b4ad3e928ce85f70035b9
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304722"
---
# <a name="export-segments-to-linkedin-ads-preview"></a>Export segmentov do služby LinkedIn Ads (verzia Preview)

Exportujte segmenty zjednotených profilov zákazníkov do LinkedIn Ads a vytvorte párované cieľové skupiny. Použite párované cieľové skupiny na zacielenie na spoločnosť a kontakty.

## <a name="prerequisites"></a>Požiadavky

- A [LinkedIn Campaign Manager účtu](https://business.linkedin.com/marketing-solutions/ads) a zodpovedajúce poverenia správcu.
- A [LinkedIn Campaign Manager Číslo účtu](https://www.linkedin.com/help/lms/answer/a424270).
- [Konfigurované segmenty](segments.md) v Customer Insights.
- Exportované segmenty potrebujú aspoň jedno špecifické pole podľa toho, či si vyberiete [kontaktné cielenie](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting) alebo [zameranie spoločnosti](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting) na LinkedIn. Možné polia sú uvedené v **Zhoda údajov** krok kedy [konfigurácia exportu](#configure-an-export).

## <a name="known-limitations"></a>Známe obmedzenia

- Až 100 000 profilov zákazníkov na export do reklám LinkedIn, ktorého dokončenie môže trvať až 10 minút.
- Iba segmenty. Segment musí obsahovať aspoň 300 jedinečných profilov.

## <a name="set-up-connection-to-linkedin-ads"></a>Nastavte pripojenie k LinkedIn Ads

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Prejdite do časti **Správca** > **Pripojenia**.

1. Vyberte **Pridať pripojenie** a vyberte si **Reklamy na LinkedIn**.

1. Do poľa **Zobrazovaný názov** zadajte rozpoznateľný názov pripojenia. Zobrazovaný názov a typ spojenia, ktoré popisuje toto spojenie. Odporúčame zvoliť názov, ktorý vysvetľuje účel a cieľ tohto spojenia.

1. Vyberte používateľov, ktorí môžu používať toto pripojenie. Predvolene sú to iba správcovia. Viac informácií nájdete v časti [Umožnite prispievateľom použiť pripojenie na export](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Poskytnite svoje LinkedIn Campaign Manager Číslo účtu.

1. Skontrolujte [ochrana osobných údajov a dodržiavanie predpisov](connections.md#data-privacy-and-compliance) a vyberte **Súhlasím**.

1. Vyberte **Pripojte sa** na inicializáciu pripojenia.

1. Stlačte možnosť **Overenie pomocou služby LinkedIn** a zadajte svoje poverenia správcu pre LinkedIn Campaign Manager.

1. Vyberte položku **Pridať samého seba ako používateľa exportu** a uveďte svoje poverenia pre Customer Insights.

1. Stlačte možnosť **Uložiť** a dokončite pripojenie.

## <a name="configure-an-export"></a>Nakonfigurujte export

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Prejdite na **Údaje** > **Exporty**.

1. Vyberte **Pridať export**.

1. V poli **Pripojenie na export** vyberte pripojenie v časti LinkedIn Ads. Ak nie je k dispozícii pripojenie, kontaktujte správcu.

1. Zadajte názov exportu.

1. Vyberte, či chcete exportovať údaje a vykonať [zacielenie na kontakty](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting) alebo [zacielenie na spoločnosť](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting) na LinkedIn.

1. V sekcii **Párovanie údajov** vyberte pre zacielenie kontaktov aspoň jedno pole, ktoré predstavuje e-mailovú adresu zákazníka, Apple Ad ID, Google Ad ID, Google User ID alebo krstné meno a priezvisko. Ak si vyberiete zacielenie na spoločnosť, vyberte aspoň jedno pole, ktoré predstavuje názov spoločnosti, e-mailovú doménu, adresu URL stránky LinkedIn, symbol akcie alebo webovú stránku.

1. Voliteľne pridajte polia na ďalšie definovanie exportu. Výberom položky **Pridať atribút** namapujete tieto polia.

1. Vyberte segmenty, ktoré chcete exportovať. Priradené cieľové skupiny v LinkedIn Campaign Manager sa automaticky vytvoria s názvom segmentov, ktoré ste vybrali na export. Výsledkom každého segmentu bude samostatná priradená cieľová skupina.

1. Vyberte **Uložiť**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
