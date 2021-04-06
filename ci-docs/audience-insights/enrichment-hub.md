---
title: Obohatenie zjednotených profilov zákazníkov
description: Využite možnosti na obohatenie údajov vašich zákazníkov.
ms.date: 11/02/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 36e6f7f8fcd64fc2591e913910918b83bf27567b
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597714"
---
# <a name="enrichment-for-customer-profiles-preview"></a>Obohacovanie profilov zákazníkov (ukážka)

Na obohatenie údajov o zákazníkoch použite údaje zo zdrojov ako Microsoft a ďalších partnerov.

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Stránka centra obohatenia":::

V prehľadoch cieľových skupín prejdite na **Údaje** > **Obohatenie**, aby ste mohli pracovať s možnosťami obohacovania.    
Ak chcete vytvárať alebo upravovať obohatenia, musíte mať oprávnenie prispievateľa alebo správcu. Ďalšie informácie nájdete v časti [Povolenia](permissions.md).

Na internete **Objavovať** nájdete nasledujúce obohatenia:

- [Značky](enrichment-microsoft-graph.md) poskytuje Microsoft Graph
- [Záujmy](enrichment-microsoft-graph.md) poskytuje Microsoft Graph
- [Údaje o spoločnosti](enrichment-leadspace.md) poskytované spoločnosťou Leadspace
- [Demografické údaje](enrichment-experian.md) poskytované spoločnosťou Experian
- [Údaje o polohe](enrichment-here.md) poskytované spoločnosťou HERE Technologies
- [Vlastné údaje](enrichment-SFTP-custom-import.md) prostredníctvom protokolu SFTP (Secure File Transfer Protocol)

Na karte **Moje obohatenia** môžete vidieť obohatenia, ktoré ste nakonfigurovali, a upraviť ich vlastnosti.

## <a name="manage-existing-enrichments"></a>Spravovanie existujúcich obohatení

Prejdite do **Moje obohatenia**, aby ste videli všetky nakonfigurované obohatenia. Každé obohatenie je predstavované ako riadok, ktorý obsahuje ďalšie informácie o obohatení.

Vyberte obohatenie a zobrazia sa dostupné možnosti. Môžete tiež zvoliť tri bodky (...) v položke zoznamu a zobraziť možnosti.

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="Možnosti na spravovanie obohatení v zozname obohatení":::

- **Zobrazenie** podrobností o obohatení s počtom obohatených profilov zákazníkov.
- **Úprava** konfigurácie obohacovania.
- **Spustite** obohatenie na aktualizáciu profilov zákazníkov o najnovšie údaje.
- **Deaktivácia** existujúceho obohatenie, ktoré zabráni automatickému obnoveniu pri každom plánovanom obnovení. Dáta z poslednej úspešnej obnovy budú naďalej k dispozícii. **Aktivácia** neaktívneho obohatenie na reštartovanie automatického obnovovania pri každom plánovanom obnovení.
- **Odstráňte** obohatenie.

Výberom v zozname môžete spustiť alebo deaktivovať viac obohatení naraz. Možnosti zobrazenia a úpravy nie sú k dispozícii ako hromadná akcia a fungujú naraz iba pre jedno obohatenie.


[!INCLUDE[footer-include](../includes/footer-banner.md)]