---
title: Obohatenie zjednotených profilov zákazníkov
description: Využite možnosti na obohatenie údajov vašich zákazníkov.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 10c338b89a6f9971912d05986c105cba1221b01b
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896024"
---
# <a name="enrichment-for-customer-profiles-preview"></a>Obohacovanie profilov zákazníkov (ukážka)

Na obohatenie údajov o zákazníkoch použite údaje zo zdrojov ako Microsoft a ďalších partnerov.

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Stránka centra obohatenia":::

V prehľadoch cieľových skupín prejdite na **Údaje** > **Obohatenie**, aby ste mohli pracovať s možnosťami obohacovania.    
Ak chcete vytvárať alebo upravovať obohatenia, musíte mať oprávnenie prispievateľa alebo správcu. Ďalšie informácie nájdete v časti [Povolenia](permissions.md).

Na internete **Objavovať** nájdete nasledujúce obohatenia:

- [Značky](enrichment-microsoft.md) od spoločnosti Microsoft
- [Záujmy](enrichment-microsoft.md) od spoločnosti Microsoft
- [Údaje o spoločnosti](enrichment-leadspace.md) poskytované spoločnosťou Leadspace
- [Demografické údaje](enrichment-experian.md) poskytované spoločnosťou Experian
- [Údaje o polohe](enrichment-here.md) poskytované spoločnosťou HERE Technologies
- [Vlastné údaje](enrichment-SFTP-custom-import.md) prostredníctvom protokolu SFTP (Secure File Transfer Protocol)

Na karte **Moje obohatenia** môžete vidieť obohatenia, ktoré ste nakonfigurovali, a upraviť ich vlastnosti.

## <a name="manage-existing-enrichments"></a>Spravovanie existujúcich obohatení

Prejdite do **Moje obohatenia**, aby ste videli všetky nakonfigurované obohatenia. Každé obohatenie je predstavované ako riadok, ktorý obsahuje ďalšie informácie o obohatení.

Vyberte obohatenie a zobrazia sa dostupné možnosti. Možnosti môžete zobraziť aj tak, že stlačíte tri bodky (...) v položke zoznamu.

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="Možnosti na spravovanie obohatení v zozname obohatení":::

- **Zobrazenie** podrobností o obohatení s počtom obohatených profilov zákazníkov.
- **Úprava** konfigurácie obohacovania.
- **Spustite** obohatenie na aktualizáciu profilov zákazníkov o najnovšie údaje.
- **Deaktivácia** existujúceho obohatenie, ktoré zabráni automatickému obnoveniu pri každom plánovanom obnovení. Dáta z poslednej úspešnej obnovy budú naďalej k dispozícii. **Aktivácia** neaktívneho obohatenie na reštartovanie automatického obnovovania pri každom plánovanom obnovení.
- **Odstráňte** obohatenie.

Výberom v zozname môžete spustiť alebo deaktivovať viac obohatení naraz. Možnosti zobrazenia a úpravy nie sú k dispozícii ako hromadná akcia a fungujú naraz iba pre jedno obohatenie.

## <a name="enrichments-and-connections"></a>Obohatenia a pripojenia

Obohatenia tretích strán sa konfigurujú pomocou [spojení](connections.md), ktorý správca zriadi pomocou prihlasovacích údajov a poskytne súhlas na prenos údajov. Pripojenie môžu správcovia a prispievatelia použiť na konfiguráciu obohatení.  

## <a name="multiple-enrichments-of-the-same-type"></a>Viacnásobné obohatenie rovnakého typu

Entita, ktorá sa má obohatiť, sa špecifikuje počas konfigurácie obohatenia, ktorá umožňuje obohatiť iba podmnožinu vašich profilov. V prípade obohaťte údaje iba o konkrétny segment. Môžete nakonfigurovať niekoľko obohatení rovnakého typu a znova použiť to isté pripojenie. Niektoré obohatenia budú mať obmedzený počet obohatení rovnakého typu, ktoré je možné vytvoriť. Limity a súčasné použitie sú uvedené na stránke **Obohatenie**.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
