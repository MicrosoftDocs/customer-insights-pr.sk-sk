---
title: Prepojenia s inými službami zo služby Customer Insights.
description: Zdieľajte údaje s inými službami.
ms.date: 04/09/2021
ms.reviewer: nikeller
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: overview
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: e78e18b75ee9797b5fc76486615992e301e4c650
ms.sourcegitcommit: bb1ca84bc38e81fb2ff2961c457384b7beb5b5fa
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 01/15/2022
ms.locfileid: "7977756"
---
# <a name="connections-preview-overview"></a>Prehľad pripojení (ukážka)

Pripojenia sú kľúčom na umožnenie zdieľania údajov smerom do a z Customer Insights. Každé pripojenie ustanovuje zdieľanie údajov s konkrétnou službou. Spojenia sú základom pre [konfiguráciu obohatenia tretích strán](enrichment-hub.md) a [konfiguráciu exportov](export-destinations.md). Rovnaké pripojenie je možné použiť viackrát. Napríklad jedno pripojenie k Dynamics 365 Marketing funguje pre viac exportov a jedno pripojenie Leadspace je možné použiť pre niekoľko obohatení.

Prejdite na **Správca** > **Pripojenia** na vytváranie a prezeranie pripojení.

Karta **Pripojenia** zobrazuje všetky aktívne pripojenia. Zoznam zobrazuje riadok pre každé pripojenie. 

Získajte rýchly prehľad, popis a zistite, čo môžete robiť s každou možnosťou rozšíriteľnosti na karte **Objavovať**.

### <a name="exports"></a>Exporty

Iba správcovia môžu konfigurovať nové pripojenia, môžu však prispievateľom udeliť prístup k použitiu existujúcich pripojení. Správcovia kontrolujú, kam môžu údaje smerovať, prispievatelia definujú užitočné zaťaženie a frekvenciu zodpovedajúcu ich potrebám. Viac informácií nájdete v časti [Umožnite prispievateľom použiť pripojenie na export](#allow-contributors-to-use-a-connection-for-exports).

### <a name="enrichments"></a>Obohatenia

Iba správcovia môžu konfigurovať nové pripojenia, ale vytvorené pripojenia sú vždy k dispozícii správcom aj prispievateľom. Správcovia spravujú poverenia a udeľujú súhlas s prenosmi údajov. Pripojenia možno použiť na obohatenie správcov aj prispievateľov.

## <a name="add-a-new-connection"></a>Pridať nové pripojenie

Ak chcete pridať pripojenia, musíte mať [oprávnenia správcu](permissions.md). Ak sa pripájate k iným službám spoločnosti Microsoft, predpokladáme, že obe služby sú v rovnakej organizácii.

1. Prejdite do časti **Správca** > **Pripojenia (ukážka)**.

1. Prejdite na kartu **Pripojenia**.

1. Ak chcete vytvoriť nové pripojenie, vyberte **Pridať pripojenie**. Z rozbaľovacej ponuky si vyberte, aký typ pripojenia chcete vytvoriť.

1. V table **Nastaviť pripojenie** zadajte požadované podrobnosti. 
   1. **Zobrazovaný názov** a typ spojenia popisujú spojenie. Odporúčame zvoliť názov, ktorý vysvetľuje účel a cieľ tohto spojenia.
   1. Presné polia závisia od toho, ku ktorej službe sa pripájate. V článku o cieľovej službe sa môžete dozvedieť viac podrobností o konkrétnom type pripojenia.
   1. Ak [použijete svoj vlastný Key Vault](use-azure-key-vault.md) na uloženie tajomstiev, aktivujte **Použiť Key Vault** a vyberte tajomstvo zo zoznamu.

1. Na vytvorenie pripojenia stlačte možnosť **Uložiť**.

Môžete tiež vybrať **Nastaviť** na dlaždici na karte **Objavovať**.

### <a name="allow-contributors-to-use-a-connection-for-exports"></a>Umožnite prispievateľom použiť pripojenie na exportovania

Pri nastavovaní alebo úprave exportného pripojenia si vyberáte, ktorí používatelia majú povolené toto konkrétne pripojenie na definovanie [exportov](export-destinations.md). V predvolenom nastavení je pripojenie k dispozícii používateľom s rolou správcu. Toto nastavenie môžete zmeniť v časti **Vyberte používateľov, ktorí môžu používať toto pripojenie** a umožniť používateľom s rolou prispievateľa používať toto pripojenie.

- Prispievatelia nebudú môcť zobraziť ani upraviť pripojenie. Zobrazený názov a jeho typ sa im zobrazí iba pri vytváraní exportu.
- Zdieľaním pripojenia umožňujete prispievateľom používať pripojenie. Prispievateľom sa po nastavení exportu zobrazia zdieľané pripojenia. Môžu spravovať každý export, ktorý používa toto konkrétne pripojenie.
- Toto nastavenie môžete zmeniť pri zachovaní exportov, ktoré už boli definované prispievateľmi.

## <a name="edit-a-connection"></a>Upraviť pripojenie

1. Prejdite do časti **Správca** > **Pripojenia (ukážka)**.

1. Prejdite na kartu **Pripojenia**.

1. Vyberte zvislé tri bodky pri pripojení, ktoré chcete upraviť.

1. Vyberte **Upraviť**.

1. Zmeňte hodnoty, ktoré chcete aktualizovať, a stlačte možnosť **Uložiť**.

## <a name="remove-a-connection"></a>Odstrániť pripojenie

Ak je pripojenie, ktoré odstraňujete, obohatené alebo exportované, musíte ich najskôr odpojiť alebo odstrániť. Dialógové okno odstránenia vás prevedie príslušným obohatením alebo exportom. 

Oddelené obohatenia a exporty sa stanú neaktívnymi. Znova ich aktivujete pridaním ďalšieho spojenia na ne na stránke [Obohatenia](enrichment-hub.md) alebo [Exporty](export-destinations.md).

1. Prejdite do časti **Správca** > **Pripojenia (ukážka)**.

1. Prejdite na kartu **Pripojenia**.

1. Vyberte zvislé tri bodky pri pripojení, ktoré chcete odstrániť.

1. Vyberte položku **Odstrániť** z rozbaľovacej ponuky. Zobrazí sa dialógové okno s potvrdením.

   1. Ak pomocou tohto pripojenia existujú obohatenia alebo exporty, kliknutím na toto tlačidlo zobrazíte informácie o tom, čo toto pripojenie využíva.
      - **Exporty:** Môžete si vybrať, či chcete odstrániť alebo odpojiť exporty, aby ste mohli pripojenie odstrániť. Na odpojenie exportu môžu správcovia použiť akciu **Odpojiť**. Táto akcia je k dispozícii pre jednotlivé a viaceré vybrané exporty. Odpojením si ponecháte konfiguráciu exportu, ale nespustí sa, kým k nej nepridáte ďalšie pripojenie.
      - **Obohatenia:** Môžete si vybrať, či chcete odstrániť alebo deaktivovať obohatenia, aby ste mohli pripojenie odstrániť. 
   1. Keď už pripojenie nemá žiadne ďalšie závislosti, vráťte sa späť na časť **Správca** > **Pripojenia** a skúste pripojenie znova odstrániť.

1. Na potvrdenie odstránenia vyberte možnosť **Odstrániť**.

## <a name="set-up-connections-with-secrets-managed-by-your-own-key-vault"></a>Nastavte si pripojenia pomocou tajomstiev, ktoré spravuje váš vlastný Key Vault

Niektoré pripojenia vyžadujú tajomstvá, ako sú kľúče API alebo heslá. Niektoré pripojenia podporujú tajomstvá uložené vo vašom vlastnom Key Vault. Prečítajte si viac o podporovaných pripojeniach a o tom, ako ich nastaviť [vo svojom vlastnom Key Vault pre prehľady cieľových skupín](use-azure-key-vault.md).
