---
title: Prehľad obohatenia údajov (ukážka).
description: Využite možnosti od spoločnosti Microsoft a ďalších služieb tretích strán na obohatenie údajov o svojich zákazníkoch.
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
ms.openlocfilehash: 0c2a900190b4ab6e93098d05a2fd66bcd2b847fd
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 08/10/2022
ms.locfileid: "9245898"
---
# <a name="data-enrichment-preview-overview"></a>Prehľad obohatenia údajov (ukážka).

Na obohatenie údajov o zákazníkoch použite údaje zo zdrojov ako Microsoft a ďalších partnerov. Obohatenia tretích strán sa konfigurujú pomocou [spojení](connections.md), ktorý správca zriadi pomocou prihlasovacích údajov a poskytne súhlas na prenos údajov. Pripojenia môžu používať správcovia a prispievatelia na konfiguráciu obohatení.  

## <a name="multiple-enrichments-of-the-same-type"></a>Viacnásobné obohatenie rovnakého typu

Entita, ktorá sa má obohatiť, sa špecifikuje počas konfigurácie obohatenia, ktorá umožňuje obohatiť iba podmnožinu vašich profilov. Môžete napríklad obohatiť údaje iba v konkrétnom segmente. Môžete nakonfigurovať niekoľko obohatení rovnakého typu a znova použiť to isté pripojenie. Niektoré obohatenia budú mať obmedzený počet obohatení rovnakého typu, ktoré je možné vytvoriť. Limity a aktuálne využitie je možné vidieť na každej dlaždici **Objavte** kartu z **Obohacovanie** stránku.

## <a name="enrich-data-sources-before-unification"></a>Obohaťte zdroje údajov pred zjednotením

Pred zjednotením údajov môžete obohatiť údaje o svojich zákazníkoch, aby ste zvýšili kvalitu zhody údajov. Ďalšie informácie nájdete v časti [zdroj údajov obohatenie](data-sources-enrichment.md).

## <a name="create-an-enrichment"></a>Vytvorenie obohatenia

Musíte mať prispievateľa alebo správcu [povolenia](permissions.md) vytvárať alebo upravovať obohatenia.

Prejdite na položku **Údaje** > **Obohatenie**. The **Objavte** karta zobrazuje všetky podporované možnosti obohatenia.

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Stránka centra obohatenia.":::

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

- [Údaje o interakcii účtu](enrichment-office.md) poskytuje spoločnosť Microsoft
- [Údaje o spoločnosti](enrichment-dnb.md) poskytuje Dun & Bradstreet
- [Údaje o spoločnosti](enrichment-leadspace.md) poskytované spoločnosťou Leadspace
- [Vylepšené adresy](enrichment-enhanced-addresses.md) poskytované spoločnosťou Microsoft
- [Vylepšené firemné údaje](enrichment-enhanced-company-data.md) poskytuje spoločnosť Microsoft
- [Údaje o polohe](enrichment-azure-maps.md) poskytuje Microsoft Azure Mapy
- [Údaje o polohe](enrichment-here.md) poskytované spoločnosťou HERE Technologies
- [Vlastné údaje SFTP](enrichment-SFTP-custom-import.md) cez protokol Secure File Transfer Protocol (SFTP)

---

## <a name="manage-existing-enrichments"></a>Spravovanie existujúcich obohatení

Prejdite na položku **Údaje** > **Obohatenie**. Na **Moje obohatenia** zobrazte nakonfigurované rozšírenia, ich stav, počet obohatených zákazníkov a čas poslednej aktualizácie údajov. Zoznam obohatení môžete zoradiť podľa ľubovoľného stĺpca alebo použiť vyhľadávacie pole na nájdenie obohatenia, ktoré chcete spravovať.

Výberom obohatenia zobrazíte dostupné akcie.

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="Možnosti na spravovanie obohatení v zozname obohatení.":::

- **Zobrazenie** podrobností o obohatení s počtom obohatených profilov zákazníkov.
- **Úprava** konfigurácie obohacovania.
- [**Bežať**](#run-or-refresh-enrichments) obohatenie o aktualizáciu zákazníckych profilov o najnovšie údaje. Spustite viacero obohatení naraz ich výberom v zozname.
- **Aktivovať** alebo **Deaktivovať** obohatenie. Neaktívne obohatenia sa počas a [plánované obnovenie](schedule-refresh.md).
- **Odstrániť** obohatenie.

Môžete tiež vytvoriť [segmentov](segments.md) alebo [Opatrenia](measures.md) z obohatenia.

## <a name="run-or-refresh-enrichments"></a>Beh alebo osvieženie obohatenie

Po spustení sa obohatenia môžu obnoviť podľa automatického plánu alebo manuálne na požiadanie.

1. Ak chcete manuálne obnoviť jedno alebo viac obohatení, vyberte ich a vyberte **Bežať**. Komu [naplánovať automatické obnovenie](schedule-refresh.md), ísť do **Admin** > **Systém** > **Rozvrh**. Čas spracovania závisí od veľkosti vašich zákazníckych údajov.

1. voliteľne [vidieť priebeh procesu obohacovania](#see-the-progress-of-the-enrichment-process).

1. Po dokončení procesu obohatenia prejdite na **Moje obohatenia** na kontrolu údajov novo obohatených profilov zákazníkov, času poslednej aktualizácie a počtu obohatených profilov.

1. Vyberte obohatenie, ktoré chcete vidieť [výsledky obohatenia](#view-enrichment-results).

### <a name="see-the-progress-of-the-enrichment-process"></a>Zobrazte priebeh procesu obohacovania

Môžete nájsť detaily spracúvania obohatenia vrátane jeho stavu a možných problémov počas obnovovania či po dokončení obnovenia. Zoznámte sa s procesmi, ktoré sú súčasťou obnovenia obohatenia, a dĺžkou behu týchto procesov. Stav obohatenia je podporovaný pre Experian, Leadspace, HERE Technologies, import SFTP a Azure Maps.

1. Prejdite na položku **Údaje** > **Obohatenie**.
1. V **Moje obohatenia** vyberte stav obohatenia a otvorte bočný panel.
1. Na table **Podrobnosti o priebehu** rozbaľte časť **Obohatenia**.
1. Pod položkou obohatenia, ktoré chcete vidieť, označte položku **Zobraziť podrobnosti**.
1. V table **Podrobnosti o úlohe** označením položky **Zobraziť podrobnosti** zobrazíte procesy tvoriace proces aktualizácie obohatenia, a ich stav.

[!INCLUDE [progress-details-pane](includes/progress-details-pane.md)]

## <a name="view-enrichment-results"></a>Pozrite si výsledky obohatenia

Po dokončení cyklu obohatenia skontrolujte výsledky obohatenia.

1. Prejdite na položku **Údaje** > **Obohatenie**.
1. V **Moje obohatenia** vyberte obohatenie, ktoré chcete zobraziť.

Všetky obohatenia zobrazujú základné informácie, ako je počet obohatených profilov a počet obohatených profilov v priebehu času. The **Ukážka obohatených zákazníkov** dlaždica zobrazuje vzorku vygenerovanej entity obohatenia. Ak chcete zobraziť podrobné zobrazenie, vyberte **Pozrieť viac** a vyberte **Údaje** tab.

:::image type="content" source="media/enrichments-results.png" alt-text="Stránka s výsledkami obohatení.":::

Ak je k dispozícii, **Počet zákazníkov obohatený o odbor** poskytuje hĺbkovú analýzu pokrytia každého obohateného poľa.

Niektoré obohatenia tiež zobrazujú informácie špecifické pre daný typ obohatenia. Ďalšie informácie nájdete v súvisiacej dokumentácii.

[!INCLUDE [footer-include](includes/footer-banner.md)]
