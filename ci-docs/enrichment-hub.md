---
title: Obohatenie zjednotených profilov zákazníkov
description: Využite možnosti na obohatenie údajov vašich zákazníkov.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.custom: intro-internal
searchScope:
- ci-enrichments
- ci-enrichment-details
- ci-enrichment-wizard
- customerInsights
ms.openlocfilehash: 3bbe8b829a6698da55d84709dbab6c36aa76792a
ms.sourcegitcommit: 27c5473eecd851263e60b2b6c96f6c0a99d68acb
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 06/13/2022
ms.locfileid: "8954060"
---
# <a name="enrichment-for-customer-profiles-preview"></a>Obohacovanie profilov zákazníkov (ukážka)

Na obohatenie údajov o zákazníkoch použite údaje zo zdrojov ako Microsoft a ďalších partnerov.

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Stránka centra obohatenia.":::

Ísť do **Údaje** > **Obohacovanie** pracovať s možnosťami obohatenia.  

Ak chcete vytvárať alebo upravovať obohatenia, musíte mať oprávnenie prispievateľa alebo správcu. Ďalšie informácie nájdete v časti [Povolenia](permissions.md).

Na karte **Objavovať** nájdete všetky podporované možnosti obohatenia.

# <a name="individual-consumers-b-to-c"></a>[Jednotliví spotrebitelia (firma a spotrebiteľ)](#tab/b2c)

- [AbiliTec Identity](enrichment-liveramp.md) poskytuje LiveRamp AbiliTec
- [Značky](enrichment-microsoft.md) od spoločnosti Microsoft
- [Demografické údaje](enrichment-experian.md), ktoré poskytuje Experian
- [Vylepšené adresy](enrichment-enhanced-addresses.md) poskytované spoločnosťou Microsoft
- [Záujmy](enrichment-microsoft.md) od spoločnosti Microsoft
- [Údaje o polohe](enrichment-azure-maps.md) poskytuje Microsoft Azure Mapy
- [Údaje o polohe](enrichment-here.md) poskytované spoločnosťou HERE Technologies
- [Vlastné údaje SFTP](enrichment-SFTP-custom-import.md) cez protokol Secure File Transfer Protocol (SFTP)

# <a name="business-accounts-b-to-b"></a>[Firemné obchodné vzťahy (firma a firma)](#tab/b2b)

- [Údaje o interakcii účtu](enrichment-office.md) poskytovaná spoločnosťou Microsoft
- [Údaje o spoločnosti](enrichment-dnb.md) poskytuje Dun & Bradstreet
- [Údaje o spoločnosti](enrichment-leadspace.md) poskytované spoločnosťou Leadspace
- [Vylepšené adresy](enrichment-enhanced-addresses.md) poskytované spoločnosťou Microsoft
- [Vylepšené firemné údaje](enrichment-enhanced-company-data.md) poskytovaná spoločnosťou Microsoft
- [Údaje o polohe](enrichment-azure-maps.md) poskytuje Microsoft Azure Mapy
- [Údaje o polohe](enrichment-here.md) poskytované spoločnosťou HERE Technologies
- [Vlastné údaje SFTP](enrichment-SFTP-custom-import.md) cez protokol Secure File Transfer Protocol (SFTP)

---

Na karte **Moje obohatenia** môžete vidieť obohatenia, ktoré ste nakonfigurovali, a upraviť ich vlastnosti. Môžete tiež vytvoriť [segmentov](segments.md) alebo [Opatrenia](measures.md) z obohatenia.

## <a name="manage-existing-enrichments"></a>Spravovanie existujúcich obohatení

Prejdite na kartu **Moje obohatenia**, kde nájdete všetky nakonfigurované obohatenia. Každé obohatenie je predstavované ako riadok, ktorý obsahuje ďalšie informácie o obohatení.

Ak chcete zobraziť prístupné možnosti, označte položku obohatenia. Môžete tiež vybrať zvislú elipsu (&vellip;) na položke zoznamu, aby ste videli možnosti. Ak ste nakonfigurovali niekoľko obohatení, môžete ich rýchlo nájsť pomocou vyhľadávacieho poľa.

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="Možnosti na spravovanie obohatení v zozname obohatení.":::

- **Zobrazenie** podrobností o obohatení s počtom obohatených profilov zákazníkov.
- **Úprava** konfigurácie obohacovania.
- **Spustite** obohatenie na aktualizáciu profilov zákazníkov o najnovšie údaje.
- **Deaktivácia** existujúceho obohatenie, ktoré zabráni automatickému obnoveniu pri každom plánovanom obnovení. Dáta z poslednej úspešnej obnovy budú naďalej k dispozícii. **Aktivácia** neaktívneho obohatenie na reštartovanie automatického obnovovania pri každom plánovanom obnovení.
- **Odstrániť** obohatenie.

Spusťte alebo vypnite viacero obohatení súčasne tak, že ich označíte v zozname. Možnosti zobrazenia a úpravy nie sú k dispozícii ako hromadné akcie. Fungujú iba na jedno obohatenie súčasne.

## <a name="enrichments-and-connections"></a>Obohatenia a pripojenia

Obohatenia tretích strán sa konfigurujú pomocou [spojení](connections.md), ktorý správca zriadi pomocou prihlasovacích údajov a poskytne súhlas na prenos údajov. Pripojenia môžu používať správcovia a prispievatelia na konfiguráciu obohatení.  

## <a name="multiple-enrichments-of-the-same-type"></a>Viacnásobné obohatenie rovnakého typu

Entita, ktorá sa má obohatiť, sa špecifikuje počas konfigurácie obohatenia, ktorá umožňuje obohatiť iba podmnožinu vašich profilov. Môžete napríklad obohatiť údaje iba v konkrétnom segmente. Môžete nakonfigurovať niekoľko obohatení rovnakého typu a znova použiť to isté pripojenie. Niektoré obohatenia budú mať obmedzený počet obohatení rovnakého typu, ktoré je možné vytvoriť. Limity a aktuálne využitie je možné vidieť na každej dlaždici na **Objavte** záložku **Obohacovanie** stránku.

## <a name="enrich-data-sources-before-unification"></a>Obohaťte zdroje údajov pred zjednotením

Pred zjednotením údajov môžete obohatiť údaje o svojich zákazníkoch, aby ste zvýšili kvalitu zhody údajov. Viac informácií nájdete v časti [zdroj údajov obohatenie](data-sources-enrichment.md).

## <a name="run-or-refresh-enrichments"></a>Beh alebo osvieženie obohatenie

1. Ak chcete spustiť proces obohatenia, vyberte **Bežať**. Alebo nechajte systém spustiť obohatenie automaticky ako súčasť a [plánované obnovenie](system.md#schedule-tab). Čas spracovania závisí od veľkosti vašich zákazníckych údajov.

1. voliteľne [vidieť priebeh procesu obohacovania](#see-the-progress-of-the-enrichment-process).

1. Po dokončení procesu obohatenia prejdite na **Moje obohatenia** na kontrolu údajov novo obohatených profilov zákazníkov, času poslednej aktualizácie a počtu obohatených profilov.

1. Vyberte obohatenie, ktoré chcete vidieť [výsledky obohatenia](#enrichment-results).

### <a name="see-the-progress-of-the-enrichment-process"></a>Zobrazte priebeh procesu obohacovania

Môžete nájsť detaily spracúvania obohatenia vrátane jeho stavu a možných problémov počas obnovovania či po dokončení obnovenia. Zoznámte sa s procesmi, ktoré sú súčasťou obnovenia obohatenia, a dĺžkou behu týchto procesov. Stav obohatenia je podporovaný pre Experian, Leadspace, HERE Technologies, import SFTP a Azure Maps.

1. Prejdite na položku **Údaje** > **Obohatenie**.
1. V **Moje obohatenia** vyberte stav obohatenia a otvorte bočný panel.
1. Na table **Podrobnosti o priebehu** rozbaľte časť **Obohatenia**.
1. Pod položkou obohatenia, ktoré chcete vidieť, označte položku **Zobraziť podrobnosti**.
1. V table **Podrobnosti o úlohe** označením položky **Zobraziť podrobnosti** zobrazíte procesy tvoriace proces aktualizácie obohatenia, a ich stav.

## <a name="enrichment-results"></a>Výsledky obohatenia

Po dokončení cyklu obohatenia skontrolujte výsledky obohatenia.

1. Prejdite na položku **Údaje** > **Obohatenie**.
1. V **Moje obohatenia** vyberte obohatenie, o ktorom chcete získať informácie.

Všetky obohatenia zobrazujú základné informácie, ako je počet obohatených profilov a počet obohatených profilov v priebehu času. The **Ukážka obohatených zákazníkov** dlaždica zobrazuje vzorku vygenerovanej entity obohatenia. Ak chcete zobraziť podrobné zobrazenie, vyberte **Pozrieť viac** a vyberte **Údaje** tab.

:::image type="content" source="media/enrichments-results.png" alt-text="Stránka s výsledkami obohatení.":::

Ak je k dispozícii, **Počet zákazníkov obohatený o odbor** poskytuje hĺbkovú analýzu pokrytia každého obohateného poľa.

Niektoré obohatenia tiež zobrazujú informácie špecifické pre daný typ obohatenia. Ďalšie informácie nájdete v súvisiacej dokumentácii.

[!INCLUDE [footer-include](includes/footer-banner.md)]
