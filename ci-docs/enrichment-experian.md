---
title: Obohaťte profily zákazníkov o demografické údaje od spoločnosti Experian (verzia Preview)
description: Všeobecné informácie o obohatení pomocou tretej strany Experian.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 876853ab42e8c08ad1abacb8d8a205c0aadabcf7
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195955"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a>Obohaťte profily zákazníkov o demografické údaje od spoločnosti Experian (verzia Preview)

Experian je svetovým lídrom v oblasti vykazovania spotrebiteľských a obchodných úverov a marketingových služieb. So službami obohatenia údajov spoločnosti Experian môžete lepšie porozumieť svojim zákazníkom tým, že obohatíte ich zákaznícke profily o demografické údaje, ako je veľkosť domácnosti, príjem a podobne.

## <a name="supported-countriesregions"></a>Podporované krajiny/regióny

V súčasnosti podporujeme obohacovanie profilov zákazníkov iba v Spojených štátoch.

## <a name="prerequisites"></a>Požiadavky

- Aktívny Experian predplatné. Ak chcete získať predplatné, [kontaktujte priamo spoločnosť Experian](https://www.experian.com/marketing-services/contact). [Získajte ďalšie informácie obohatení údajov Experian](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).

- An Experian [spojenie](connections.md) je [nakonfigurovaný](#configure-the-connection-for-experian) správcom.

- Experian ID používateľa, ID strany a číslo modelu pre váš účet Secure Transport (ST) s povoleným SSH Experian vytvorené pre vás.

## <a name="configure-the-connection-for-experian"></a>Konfigurácia pripojenia pre Experian

Musíte byť [správca](permissions.md#admin) v Customer Insights a mať Experian ID používateľa, ID strany a číslo modelu.

1. Vyberte **Pridať pripojenie** pri konfigurácii obohatenia alebo prejdite na **Admin** > **Spojenia** a vyberte **Nastaviť** na Experian dlaždica.

   :::image type="content" source="media/enrichment-Experian-connection.png" alt-text="Tabla konfigurácie pripojenia Experian.":::

1. Zadajte názov pripojenia a platné ID používateľa, ID strany a číslo modelu Experian Účet Secure Transport.

1. Skontrolujte a poskytnite svoj súhlas pre [Ochranu osobných údajov a dodržiavanie súladu s nariadeniami](#data-privacy-and-compliance) výberom možnosti **Súhlasím**.

1. Vyberte **Overiť** potvrďte konfiguráciu a potom vyberte **Uložiť**.

### <a name="data-privacy-and-compliance"></a>Ochrana osobných údajov a dodržiavanie súladu s nariadeniami

Keď povolíte službe Dynamics 365 Customer Insights, aby prenášala údaje spoločnosti Experian, povoľujete tým aj prenos údajov mimo hranice súladu so službou Dynamics 365 Customer Insights vrátane potenciálne citlivých údajov, ako sú napríklad osobné údaje. Microsoft prenesie tieto údaje na váš pokyn, ale vy ste zodpovední za zabezpečenie toho, aby Experian spĺňal všetky záväzky týkajúce sa ochrany vášho súkromia alebo bezpečnosti. Ďalšie informácie nájdete vo [vyhlásení o ochrane súkromia spoločnosti Microsoft](https://go.microsoft.com/fwlink/?linkid=396732). Váš správca služby Dynamics 365 Customer Insights môžete kedykoľvek prestať používať odstránením tohto obohatenia.

## <a name="configure-the-enrichment"></a>Konfigurácia obohatenia

1. Prejdite na **Údaje** > **Obohatenie** a vyberte kartu **Objavovať**.

1. Vyberte **Obohaťte moje údaje** na **Demografické údaje** od Experian dlaždica.

   :::image type="content" source="media/experian-tile.png" alt-text="Experian dlaždicu na stránke prehľadu obohatenia.":::

1. Skontrolujte prehľad a potom vyberte **Ďalšie**.

1. Vyberte pripojenie. Ak nie je k dispozícii pripojenie, kontaktujte správcu.

1. Vyberte **Ďalej**.

1. Vyberte **Súbor zákazníckych údajov** a vyberte profil alebo segment, ktorý chcete obohatiť o demografické údaje Experian. The *Zákazník* subjekt obohacuje všetky vaše profily zákazníkov, zatiaľ čo segment obohacuje iba profily zákazníkov obsiahnuté v tomto segmente.

    :::image type="content" source="media/enrichment-Experian-configuration-customer-data-set.png" alt-text="Snímka obrazovky pri výbere množiny údajov o zákazníkoch.":::

1. Definujte, ktorý typ polí z vašich zjednotených profilov sa má použiť na porovnávanie demografických údajov Experian. Aspoň jedno z polí **Meno a adresa**, **Telefón** alebo **Email** je požadované. Pre vyššiu presnosť zhody pridajte ďalšie polia. Vyberte **Ďalej**.

1. Mapujte svoje polia na demografické údaje z Experian.

1. Stlačte možnosť **Ďalej** na vyplnenie mapovania poľa.

1. Poskytnúť **názov** za obohatenie a **Názov výstupnej entity**.

1. Stlačte možnosť **Uložiť obohatenie** po preskúmaní vašich možností.

1. Vyberte **Bežať** začať proces obohacovania alebo zavrieť návrat do **Obohatenia** stránku.

## <a name="view-enrichment-results"></a>Pozrite si výsledky obohatenia

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

The **Počet zákazníkov obohatený o odbor** poskytuje hĺbkovú analýzu pokrytia každého obohateného poľa.

## <a name="next-steps"></a>Ďalšie kroky

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
