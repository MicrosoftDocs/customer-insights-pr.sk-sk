---
title: Obohaťte firemné profily o Dun & Bradstreet (ukážka)
description: Všeobecné informácie o obohatení Dun & Bradstreet treťou stranou.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 71b35e4295e19c13edadc6548ac79715555e8183
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196045"
---
# <a name="enrich-company-profiles-with-dun--bradstreet-preview"></a>Obohaťte firemné profily o Dun & Bradstreet (ukážka)

Dun & Bradstreet poskytuje firmám komerčné údaje, analýzy a štatistiky. Umožňuje zákazníkom so zjednotenými zákazníckymi profilmi pre spoločnosti obohacovať svoje údaje. Obohatenia zahŕňajú atribúty, ako je číslo DUNS, veľkosť spoločnosti, lokalita, odvetvie a ďalšie.

## <a name="prerequisites"></a>Požiadavky

- Aktívny [Dun & Bradstreet](https://www.dnb.com/marketing/media/give-your-data-a-boost.html?source=microsoft_audience_insights) licenciu.
- [Zjednotené profily zákazníkov](customer-profiles.md) pre firmy.
- Dun & Bradstreet [projektu](#set-up-your-dun--bradstreet-project) je nastavený.
- Dun & Bradstreet [spojenie](connections.md) je [nakonfigurovaný](#configure-a-connection-for-dun--bradstreet) správcom.

## <a name="set-up-your-dun--bradstreet-project"></a>Nastavte svoj projekt Dun & Bradstreet

Ako licencovaný používateľ Dun & Bradstreet môžete nastaviť projekt v [Dun & Bradstreet Connect](https://connect.dnb.com?lead_source=microsoft_audienceinsights).

1. Prihlásiť sa [Dun & Bradstreet Connect](https://connect.dnb.com?lead_source=microsoft_audienceinsights). Ak chcete získať poverenia, [obnovte svoje heslo](https://sso.dnb.com/signin/forgot-password?lead_source=microsoft_audienceinsights).

1. Stiahnuť ▼[náš súbor šablóny csv](https://c360devenrichment.blob.core.windows.net/mapping/DnBCIdatamapping.csv) ktoré sa použijú na mapovanie polí Customer Insights k zodpovedajúcim poliam Dun & Bradstreet.

1. Nahrajte súbor do **Nahrajte údaje** krok skúseností s tvorbou projektu Dun & Bradstreet.

1. Vyberte vodorovné bodky pod príslušným **zdroj** v novovytvorenom projekte Dun & Bradstreet, aby ste videli dostupné možnosti.

   :::image type="content" source="media/enrichment-dnb-dots.png" alt-text="Snímka obrazovky bodiek v projekte Dun & Bradstreet.":::

1. Vyberte si **Získajte podrobnosti o S3**. Uchovajte tieto informácie na bezpečnom mieste. Budete to potrebovať [vytvoriť spojenie na obohatenie](#configure-a-connection-for-dun--bradstreet) v Customer Insights.

   :::image type="content" source="media/enrichment-dnb-s3info.png" alt-text="Snímka obrazovky výberu informácií s3 v projekte Dun & Bradstreet.":::

## <a name="configure-a-connection-for-dun--bradstreet"></a>Nakonfigurujte pripojenie pre Dun & Bradstreet

Musíte byť [správca](permissions.md#admin) v Customer Insights a mať poverenia od Dun & Bradstreet Connect.

1. Vyberte **Pridať pripojenie** pri konfigurácii obohatenia alebo prejdite na **Admin** > **Spojenia** a vyberte **Nastaviť** na dlaždici Dun & Bradstreet.

1. Zadajte názov pripojenia.

1. Poskytnite platné poverenia Dun & Bradstreet a podrobnosti o projekte Dun & Bradstreet *Región, Drop folder path a Drop folder name*. vy [získať tieto informácie](#set-up-your-dun--bradstreet-project) z projektu Dun & Bradstreet.

1. Skontrolujte a poskytnite svoj súhlas pre [Ochranu osobných údajov a dodržiavanie súladu s nariadeniami](#data-privacy-and-compliance) výberom možnosti **Súhlasím**.

1. Vyberte **Overiť** potvrďte konfiguráciu a potom vyberte **Uložiť**.

   :::image type="content" source="media/enrichment-dnb-connection.png" alt-text="Konfiguračná stránka pripojenia Dun & Bradstreet.":::

### <a name="data-privacy-and-compliance"></a>Ochrana osobných údajov a dodržiavanie súladu s nariadeniami

Keď povolíte Dynamics 365 Customer Insights na prenos údajov do spoločnosti Dun & Bradstreet povolíte prenos údajov mimo hraníc súladu pre Dynamics 365 Customer Insights, vrátane potenciálne citlivých údajov, ako sú Osobné údaje. Spoločnosť Microsoft prenesie takéto údaje na váš pokyn, ale vy ste zodpovední za to, že Dun & Bradstreet spĺňa všetky vaše prípadné povinnosti týkajúce sa ochrany osobných údajov alebo zabezpečenia. Ďalšie informácie nájdete vo [vyhlásení o ochrane súkromia spoločnosti Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Váš správca služby Dynamics 365 Customer Insights môžete kedykoľvek prestať používať odstránením tohto obohatenia.

## <a name="supported-countries-or-regions"></a>Podporované krajiny alebo regióny

V súčasnosti podporujeme nasledujúce možnosti krajiny/regiónu: Kanada (angličtina) alebo Spojené štáty americké (angličtina).

## <a name="configure-the-enrichment"></a>Konfigurácia obohatenia

1. Prejdite na **Údaje** > **Obohatenie** a vyberte kartu **Objavovať**.

1. Vyberte **Obohaťte moje údaje** na **Údaje o spoločnosti** pre dlaždice Dun & Bradstreet.

   :::image type="content" source="media/enrichment-dnb-tile.png" alt-text="Snímka obrazovky dlaždice Dun & Bradstreet.":::

1. Skontrolujte prehľad a potom vyberte **Ďalšie**.

1. Vyberte pripojenie a potvrďte. Ak nie je k dispozícii pripojenie, kontaktujte správcu.

1. Vyberte **Ďalej**.

1. Vyberte **Súbor zákazníckych údajov** a vyberte si profil alebo segment, ktorý chcete obohatiť o firemné údaje z Dun & Bradstreet. The *Zákazník* subjekt obohacuje všetky vaše profily zákazníkov, zatiaľ čo segment obohacuje iba profily zákazníkov obsiahnuté v tomto segmente.

1. Definujte, ktorý typ polí z vašich zjednotených profilov sa má použiť na porovnávanie firemných údajov z Dun & Bradstreet. Aspoň jedno z polí **Meno a adresa**, **Telefón** alebo **Email** je požadované.

1. Vyberte **Ďalej**

1. Namapujte svoje polia na firemné údaje z Dun & Bradstreet. Buď **DUNS číslo** alebo **Názov spoločnosti** a **Krajina** polia sú povinné.

      :::image type="content" source="media/enrichment-dnb-mapping.png" alt-text="Panel mapovania poľa Dun & Bradstreet.":::

1. Stlačte možnosť **Ďalej** na vyplnenie mapovania poľa.

1. Poskytnúť **názov** za obohatenie a **Názov výstupnej entity**.

1. Stlačte možnosť **Uložiť obohatenie** po preskúmaní vašich možností.

1. Vyberte **Bežať** začať proces obohacovania alebo zavrieť návrat do **Obohatenia** stránku.

## <a name="view-enrichment-results"></a>Pozrite si výsledky obohatenia

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

## <a name="next-steps"></a>Ďalšie kroky

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE[footer-include](includes/footer-banner.md)]
