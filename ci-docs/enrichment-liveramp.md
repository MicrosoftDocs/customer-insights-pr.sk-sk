---
title: Obohaťte profily zákazníkov o údaje o identite z LiveRamp (ukážka)
description: Obohaťte profily zákazníkov o údaje LiveRamp.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 49bf558209ca91ab9d8db945862a57adccee1f6b
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196367"
---
# <a name="enrich-customer-profiles-with-identity-data-from-liveramp-preview"></a>Obohaťte profily zákazníkov o údaje o identite z LiveRamp (ukážka)

LiveRamp poskytuje deterministické offline rozlíšenie identity a konsolidáciu údajov o zákazníkoch. Osobné identifikátory vo svojich zákazníckych údajoch môžete namapovať na graf identity AbiliTec a získať AbiliTec ID. Tieto ID potom môžete použiť na lepšie zjednotenie údajov o vašich zákazníkoch.

## <a name="supported-countriesregions"></a>Podporované krajiny/regióny

V súčasnosti podporujeme obohatenie zákazníckych profilov o údaje LiveRamp iba v Spojených štátoch.

## <a name="prerequisites"></a>Požiadavky

- Aktívne predplatné LiveRamp. Ak chcete získať predplatné, kontaktujte tím svojho účtu LiveRamp alebo na [dynamics@liveramp.com](mailto:dynamics@liveramp.com) Pre viac informácií.

- Aktívne predplatné AbiliTec s ID klienta a tajným kódom na prístup k API. Viac informácií nájdete v časti [AbiliTec API Developer Hub](https://developers.liveramp.com/abilitec-api/).

- Živá rampa [spojenie](connections.md) je [nakonfigurovaný](#configure-the-connection-for-liveramp) správcom.

## <a name="configure-the-connection-for-liveramp"></a>Nakonfigurujte pripojenie pre LiveRamp

Musíte byť [správca](permissions.md#admin) v Customer Insights a mať aktívne ID klienta LiveRamp a tajný kľúč.

1. Vyberte **Pridať pripojenie** pri konfigurácii obohatenia alebo prejdite na **Admin** > **Spojenia** a vyberte **Nastaviť** na dlaždici LiveRamp.

   :::image type="content" source="media/liveramp-connection.png" alt-text="Konfiguračný panel na nastavenie pripojenia k službe LiveRamp AbiliTec.":::

1. Zadajte názov pripojenia a platné ID klienta LiveRamp a tajný kód.

1. Skontrolujte a poskytnite svoj súhlas pre [Ochranu osobných údajov a dodržiavanie súladu s nariadeniami](#data-privacy-and-compliance) výberom možnosti **Súhlasím**.

1. Vyberte **Overiť** potvrďte konfiguráciu a potom vyberte **Uložiť**.

### <a name="data-privacy-and-compliance"></a>Ochrana osobných údajov a dodržiavanie súladu s nariadeniami

Keď povolíte Dynamics 365 Customer Insights na prenos údajov do LiveRamp povolíte prenos údajov mimo hranice zhody pre Dynamics 365 Customer Insights, vrátane potenciálne citlivých údajov, ako sú Osobné údaje. Spoločnosť Microsoft prenesie takéto údaje na váš pokyn, ale vy ste zodpovední za zabezpečenie toho, že LiveRamp spĺňa všetky vaše povinnosti týkajúce sa ochrany osobných údajov alebo zabezpečenia. Ďalšie informácie nájdete na stránke [Vyhlásenie o ochrane osobných údajov spoločnosti Microsoft](https://go.microsoft.com/fwlink/?linkid=396732). Váš správca služby Dynamics 365 Customer Insights môžete kedykoľvek prestať používať odstránením tohto obohatenia.

## <a name="configure-the-enrichment"></a>Konfigurácia obohatenia

1. Prejdite na **Údaje** > **Obohatenie** a vyberte kartu **Objavovať**.

1. Vyberte **Obohaťte moje údaje** na **Identita** z dlaždice LiveRamp.

   :::image type="content" source="media/liveramp-tile.png" alt-text="Dlaždica identity na stránke prehľadu obohatenia.":::

1. Skontrolujte prehľad a potom vyberte **Ďalšie**.

1. Vyberte pripojenie. Ak nie je k dispozícii pripojenie, kontaktujte správcu.

1. Vyberte **Ďalej**.

1. Vyberte **Súbor zákazníckych údajov** a vyberte si profil alebo segment, ktorý chcete obohatiť o údaje o identite z LiveRamp. The *Zákazník* subjekt obohacuje všetky vaše profily zákazníkov, zatiaľ čo segment obohacuje iba profily zákazníkov obsiahnuté v tomto segmente.

1. Definujte, ktorý typ polí z vašich zjednotených profilov sa má použiť na porovnávanie údajov o identite z LiveRamp. Aspoň jedno z polí **Meno a adresa**, **-mail**, alebo **Telefón** sa vyžaduje. Pre vyššiu presnosť zhody pridajte ďalšie polia. Vyberte **Ďalej**.

1. Namapujte svoje polia na identifikačné údaje z LiveRamp.

   :::image type="content" source="media/liveramp-data-mapping.png" alt-text="Možnosti mapovania údajov pre obohatenie LiveRamp.":::

1. Stlačte možnosť **Ďalej** na vyplnenie mapovania poľa.

1. Poskytnúť **názov** za obohatenie a **Názov výstupnej entity**.

1. Stlačte možnosť **Uložiť obohatenie** po preskúmaní vašich možností.

1. Vyberte **Bežať** začať proces obohacovania alebo zavrieť návrat do **Obohatenia** stránku.

## <a name="view-enrichment-results"></a>Pozrite si výsledky obohatenia

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

The **Počet zákazníkov obohatený o odbor** poskytuje hĺbkovú analýzu pokrytia každého obohateného poľa.

## <a name="next-steps"></a>Ďalšie kroky

Stavajte na svojich obohatených údajoch o zákazníkoch. Použite AbiliTec ID na konsolidáciu zákazníckych profilov do osobného zobrazenia.
[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
