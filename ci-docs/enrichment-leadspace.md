---
title: Obohaťte firemné profily pomocou Leadspace (ukážka)
description: Všeobecné informácie o obohatení pomocou obohatenia tretej stranou Leadspace.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 3f23fe7177f931db3e3179970915d0cd3c736f87
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196229"
---
# <a name="enrich-company-profiles-with-leadspace-preview"></a>Obohaťte firemné profily pomocou Leadspace (ukážka)

Leadspace je dátová vedecká spoločnosť, ktorá poskytuje platformu údajov zákazníkov pre scenáre „firma a firma“. Umožňuje prostrediam so zjednotenými profilmi zákazníkov na základe obchodných vzťahov obohatiť ich údaje. Obohaťte *Profily zákazníkov* s atribútmi, ako je veľkosť spoločnosti, umiestnenie alebo odvetvie. Obohaťte *Kontaktné profily* s atribútmi, ako sú titul, osoba alebo overenie e-mailom.

## <a name="prerequisites"></a>Požiadavky

- Aktívna licencia Leadspace.
- [Zjednotené profily zákazníkov](customer-profiles.md) na základe účtov.
- Leadspace [spojenie](connections.md) je [nakonfigurovaný](#configure-the-connection-for-leadspace) správcom. Kontakt [Leadspace](https://www.leadspace.com/leadspace-microsoft-dynamics-365/) priamo pre podrobnosti o ich produkte.

## <a name="configure-the-connection-for-leadspace"></a>Nakonfigurujte pripojenie pre Leadspace

Musíte byť [správca](permissions.md#admin) v Customer Insights a majú „trvalý kľúč“ (označovaný ako **Token leadspace**).

1. Vyberte **Pridať pripojenie** pri konfigurácii obohatenia alebo prejdite na **Admin** > **Spojenia** a vyberte **Nastaviť** na dlaždici Leadspace.

   :::image type="content" source="media/enrichment-Leadspace-connection.png" alt-text="Konfiguračná stránka pripojenia Leadspace.":::

1. Zadajte názov pripojenia a platný token Leadspace.

1. Skontrolujte a poskytnite svoj súhlas pre [Ochranu osobných údajov a dodržiavanie súladu s nariadeniami](#data-privacy-and-compliance) výberom možnosti **Súhlasím**.

1. Vyberte **Overiť** potvrďte konfiguráciu a potom vyberte **Uložiť**.

### <a name="data-privacy-and-compliance"></a>Ochrana osobných údajov a dodržiavanie súladu s nariadeniami

Keď povolíte prenos údajov spoločnosti Leadspace v službe Dynamics 365 Customer Insights, povoľujete tým prenos údajov mimo hranice súladu so službou Dynamics 365 Customer Insights vrátane potenciálne citlivých údajov, ako sú napríklad osobné údaje. Spoločnosť Microsoft prenesie tieto údaje na váš pokyn, ale vy ste zodpovední za zabezpečenie toho, aby spoločnosť Leadspace plnila všetky prípadné povinnosti týkajúce sa ochrany vašich osobných údajov alebo zabezpečenia. Ďalšie informácie nájdete vo [vyhlásení o ochrane súkromia spoločnosti Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Váš správca služby Dynamics 365 Customer Insights môžete kedykoľvek prestať používať odstránením tohto obohatenia.

## <a name="configure-the-enrichment"></a>Konfigurácia obohatenia

1. Prejdite na **Údaje** > **Obohatenie** a vyberte kartu **Objavovať**.

1. Vyberte **Obohaťte moje údaje** na **Údaje o spoločnosti** z dlaždice Leadspace.

   :::image type="content" source="media/leadspace-tile.png" alt-text="Snímka obrazovky dlaždice Leadspace.":::

1. Skontrolujte prehľad a potom vyberte **Ďalšie**.

1. Vyberte pripojenie. Ak nie je k dispozícii pripojenie, kontaktujte správcu.

1. Vyberte **Ďalej**.

1. Vyberte **Súbor zákazníckych údajov** a vyberte si profil alebo segment, ktorý chcete obohatiť o firemné údaje z Leadspace. The *Zákazník* subjekt obohacuje všetky vaše profily zákazníkov, zatiaľ čo segment obohacuje iba profily zákazníkov obsiahnuté v tomto segmente.

    :::image type="content" source="media/enrichment-Leadspace-configuration-customer-data-set.png" alt-text="Snímka obrazovky pri výbere množiny údajov o zákazníkoch.":::

1. Definujte, ktorý typ polí z vašich zjednotených profilov sa má použiť na porovnávanie: primárna a/alebo sekundárna adresa. Môžete určiť mapovanie poľa pre obe adresy a profily pre obe adresy na samostatné obohatenie. Napríklad pre adresu bydliska a adresu firmy. Vyberte **Ďalej**.

1. Namapujte svoje polia na firemné údaje z Leadspace. Pole **Názov spoločnosti** je povinné. Pre vyššiu presnosť zhody možno pridať až dve ďalšie polia, **Webová lokalita spoločnosti** a **Sídlo spoločnosti**.

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="Tabla mapovania polí Leadspace.":::

1. Stlačte možnosť **Ďalej** na vyplnenie mapovania poľa.

1. Začiarknite políčko, ak máte *Kontaktné profily*, ktoré by ste chceli obohatiť. Customer Insights automaticky zmapuje požadované polia.

   :::image type="content" source="media/enrichment-leadspace-contacts.png" alt-text="Obohatenie záznamov kontaktov Leadspace.":::

1. Vyberte **Ďalej**.

1. Poskytnúť **názov** za obohatenie a **Názov výstupnej entity**.

1. Stlačte možnosť **Uložiť obohatenie** po preskúmaní vašich možností.

1. Vyberte **Bežať** začať proces obohacovania alebo zavrieť návrat do **Obohatenia** stránku.

## <a name="view-enrichment-results"></a>Pozrite si výsledky obohatenia

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

Ďalšie informácie sa dozviete v časti [API Leadspace](https://support.leadspace.com/hc/en-us/sections/201997649-API).

## <a name="next-steps"></a>Ďalšie kroky

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
