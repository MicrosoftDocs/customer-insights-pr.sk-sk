---
title: Inštalácia a konfigurácia doplnku Karta zákazníka
description: Inštalácia a konfigurácia doplnku Karta zákazníka pre Dynamics 365 Customer Insights.
ms.date: 08/04/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: aab5deaf89b4b019f6688a1bca950ec2277ad5fb
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 11/25/2020
ms.locfileid: "4644062"
---
# <a name="customer-card-add-in-preview"></a>Doplnok Karta zákazníka (ukážka)

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Získajte kompletný prehľad o svojich zákazníkoch priamo v aplikáciách Dynamics 365. Pomocou doplnku Karta zákazníka si môžete prezerať demografické údaje, štatistiky a časové harmonogramy aktivít.

## <a name="prerequisites"></a>Predpoklady

- Aplikácia Dynamics 365 (napríklad Centrum predaja alebo Centrum služieb pre zákazníkov), verzia 9.0 a novšia, s povoleným Zjednoteným rozhraním.
- Profily zákazníkov [prijaté z aplikácie Dynamics 365 pomocou služby Common Data Service](connect-power-query.md).
- Používatelia doplnku Karta zákazníka musia byť [pridaní ako používatelia](permissions.md) v prehľadoch cieľových skupín.
- [Konfigurované možnosti vyhľadávania a filtrovania](search-filter-index.md).
- Demografický ovládací prvok: Demografické polia, ako napríklad vek alebo pohlavie, sú k dispozícii v zjednotenom profile zákazníka.
- Kontrola obohatenia: Vyžaduje sa aktívne [obohatenie](enrichment-hub.md) aplikované na profily zákazníkov.
- Inteligenčný ovládací prvok: Vyžaduje údaje generované pomocou strojového učenia platformy Azure ([predpovede](predictions.md) alebo [vlastné modely](custom-models.md))
- Merací ovládací prvok: Vyžadujú sa [nakonfigurované miery](measures.md).
- Ovládací prvok časovej osi: Vyžadujú sa [nakonfigurované aktivity](activities.md).

## <a name="install-the-customer-card-add-in"></a>Inštalácia doplnku Karta zákazníka

Doplnok ku karte zákazníka je riešením pre aplikácie na zapojenie zákazníkov do Dynamics 365. Ak chcete nainštalovať riešenie, prejdite do AppSource a vyhľadajte **Karta zákazníka Dynamics**. Vyberte [Doplnok Karta zákazníka v AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) a vyberte **Získať teraz**.

Možno sa budete musieť prihlásiť so svojimi prihlasovacími údajmi, aby mohla aplikácia Dynamics 365 nainštalovať riešenie.

Môže to trvať nejaký čas, kým sa riešenie nainštaluje do vášho prostredia.

## <a name="configure-the-customer-card-add-in"></a>Konfigurácia doplnku Karta zákazníka

1. Ako správca prejdite do časti **Nastavenia** v Dynamics 365 a vyberte položku **Riešenia**.

1. Vyberte odkaz **Zobrazovaný názov** pre riešenie **Doplnok Karta zákazníka Dynamics 365 Customer Insights (ukážka)**.

   > [!div class="mx-imgBorder"]
   > ![Výber zobrazovaného názvu](media/select-display-name.png "Výber zobrazovaného názvu")

1. Vyberte **Prihlásiť sa** a zadajte prihlasovacie údaje pre účet správcu, ktorý používate na konfiguráciu Customer Insights.

   > [!NOTE]
   > Skontrolujte, či blokovanie automaticky otváraných okien v prehľadávači neblokuje overovacie okno, keď vyberiete tlačidlo **Prihlásiť sa**.

1. Vyberte prostredie, z ktorého chcete načítať údaje.

1. Definujte, ktoré pole sa má namapovať k záznamom v aplikácii Dynamics 365.
   - Na mapovanie ku kontaktu vyberte pole v entite Zákazník, ktoré sa zhoduje s ID entity vášho kontaktu.
   - Na mapovanie k obchodnému vzťahu vyberte pole v entite Zákazník, ktoré sa zhoduje s ID entity vášho obchodného vzťahu.

   > [!div class="mx-imgBorder"]
   > ![Pole ID kontaktu](media/contact-id-field.png "Pole ID kontaktu")

1. Stlačením možnosti **Uložiť konfiguráciu** uložte nastavenia.

1. Ďalej musíte v Dynamics 365 prideliť roly zabezpečenia, aby si používatelia mohli prispôsobiť a vidieť Kartu zákazníka. V aplikácii Dynamics 365 prejdite do časti **Nastavenie** > **Zabezpečenie** > **Používatelia**. Vyberte používateľov, ktorých chcete upraviť, a vyberte **Spravovať roly**.

1. Priraďte rolu **Prispôsobovač karty služby Customer Insights** používateľom, ktorí prispôsobia obsah zobrazený na karte pre celú organizáciu.

## <a name="add-customer-card-controls-to-forms"></a>Pridanie ovládacích prvkov Zákazníckej karty do formulárov
  
1. Ak chcete pridať ovládacie prvky Karty zákazníka do svojho formulára Kontakt, prejdite na stránku **Nastavenia** > **Prispôsobenia** v Dynamics 365.

1. Stlačte možnosť **Prispôsobenie systému**.

1. Vyhľadajte entitu **Kontakt**, rozbaľte ju a potom vyberte položku **Formuláre**.

1. Vyberte formulár kontaktu, do ktorého chcete pridať ovládacie prvky Karty zákazníka.

    > [!div class="mx-imgBorder"]
    > ![Výber formulára kontaktu](media/contact-active-forms.png "Výber formulára kontaktu")

1. Ak chcete pridať ovládací prvok, v editore formulárov presuňte ľubovoľné pole z **Prieskumníka polí** na miesto, kde sa má zobraziť ovládací prvok.

1. Vyberte pole vo formulári, ktoré ste práve pridali, a potom položku **Zmeniť vlastnosti**.

1. Prejdite na kartu **Ovládacie prvky** a vyberte položku **Pridať ovládací prvok**. Vyberte jeden z dostupných vlastných ovládacích prvkov a potom položku **Pridať**.

1. V dialógovom okne **Vlastnosti poľa** zrušte začiarknutie políčka **Zobraziť menovku vo formulári**.

1. Vyberte možnosť **Web** pre ovládací prvok. Pre kontrolu obohatenia vyberte typ obohatenia, ktorý chcete zobraziť, nakonfigurovaním poľa **enrichmentType**. Pre každý druh obohatenia musíte pridať samostatnú kontrolu obohatenia.

1. Výberom **Uložiť** a **Publikovať** zverejnite aktualizovaný kontaktný formulár.

1. Prejdite na publikovaný kontaktný formulár. Uvidíte novo pridaný ovládací prvok. Možno sa budete musieť prihlásiť pri prvom použití.

1. Ak chcete prispôsobiť, čo chcete zobraziť vo vlastnom ovládacom prvku, vyberte tlačidlo Upraviť v pravom hornom rohu.
