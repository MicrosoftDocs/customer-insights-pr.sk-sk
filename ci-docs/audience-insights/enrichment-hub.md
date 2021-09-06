---
title: Obohatenie zjednotených profilov zákazníkov
description: Využite možnosti na obohatenie údajov vašich zákazníkov.
ms.date: 07/01/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: a64bbd754d4013d0a6243074ac9f55991547be82b269047a9937b583baf98697
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 08/10/2021
ms.locfileid: "7032547"
---
# <a name="enrichment-for-customer-profiles-preview"></a>Obohacovanie profilov zákazníkov (ukážka)

Na obohatenie údajov o zákazníkoch použite údaje zo zdrojov ako Microsoft a ďalších partnerov.

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Stránka centra obohatenia.":::

V prehľadoch cieľových skupín prejdite na **Údaje** > **Obohatenie**, aby ste mohli pracovať s možnosťami obohacovania.  

Ak chcete vytvárať alebo upravovať obohatenia, musíte mať oprávnenie prispievateľa alebo správcu. Ďalšie informácie nájdete v časti [Povolenia](permissions.md).

Na internete **Objavovať** nájdete nasledujúce obohatenia:

- [Značky](enrichment-microsoft.md) od spoločnosti Microsoft
- [Záujmy](enrichment-microsoft.md) od spoločnosti Microsoft
- [Vylepšené adresy](enrichment-enhanced-addresses.md) poskytované spoločnosťou Microsoft
- [Údaje o spoločnosti](enrichment-leadspace.md) poskytované spoločnosťou Leadspace
- [Demografické údaje](enrichment-experian.md), ktoré poskytuje Experian
- [Údaje o polohe](enrichment-here.md) poskytované spoločnosťou HERE Technologies
- [Vlastné údaje](enrichment-SFTP-custom-import.md) prostredníctvom protokolu SFTP (Secure File Transfer Protocol)

Na karte **Moje obohatenia** môžete vidieť obohatenia, ktoré ste nakonfigurovali, a upraviť ich vlastnosti.

## <a name="manage-existing-enrichments"></a>Spravovanie existujúcich obohatení

Prejdite na kartu **Moje obohatenia**, kde nájdete všetky nakonfigurované obohatenia. Každé obohatenie je predstavované ako riadok, ktorý obsahuje ďalšie informácie o obohatení.

Ak chcete zobraziť prístupné možnosti, označte položku obohatenia. Možnosti môžete zobraziť aj tak, že stlačíte tri bodky (...) v položke zoznamu. Ak ste nakonfigurovali niekoľko obohatení, môžete ich rýchlo nájsť pomocou vyhľadávacieho poľa.

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="Možnosti na spravovanie obohatení v zozname obohatení.":::

- **Zobrazenie** podrobností o obohatení s počtom obohatených profilov zákazníkov.
- **Úprava** konfigurácie obohacovania.
- **Spustite** obohatenie na aktualizáciu profilov zákazníkov o najnovšie údaje.
- **Deaktivácia** existujúceho obohatenie, ktoré zabráni automatickému obnoveniu pri každom plánovanom obnovení. Dáta z poslednej úspešnej obnovy budú naďalej k dispozícii. **Aktivácia** neaktívneho obohatenie na reštartovanie automatického obnovovania pri každom plánovanom obnovení.
- **Odstrániť** obohatenie.

Spusťte alebo vypnite viacero obohatení súčasne tak, že ich označíte v zozname. Možnosti zobrazenia a úpravy nie sú k dispozícii ako hromadné akcie. Fungujú iba na jedno obohatenie súčasne.

## <a name="enrichments-and-connections"></a>Obohatenia a pripojenia

Obohatenia tretích strán sa konfigurujú pomocou [spojení](connections.md), ktorý správca zriadi pomocou prihlasovacích údajov a poskytne súhlas na prenos údajov. Pripojenie môžu správcovia a prispievatelia použiť na konfiguráciu obohatení.  

## <a name="multiple-enrichments-of-the-same-type"></a>Viacnásobné obohatenie rovnakého typu

Entita, ktorá sa má obohatiť, sa špecifikuje počas konfigurácie obohatenia, ktorá umožňuje obohatiť iba podmnožinu vašich profilov. Môžete napríklad obohatiť údaje iba v konkrétnom segmente. Môžete nakonfigurovať niekoľko obohatení rovnakého typu a znova použiť to isté pripojenie. Niektoré obohatenia budú mať obmedzený počet obohatení rovnakého typu, ktoré je možné vytvoriť. Limity a súčasné použitie sú uvedené na stránke **Obohatenie**.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
