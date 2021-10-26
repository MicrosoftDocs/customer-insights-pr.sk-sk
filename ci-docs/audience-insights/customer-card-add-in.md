---
title: Doplnok Customer Card pre aplikácie Dynamics 365
description: Pomocou tohto doplnku zobrazujte údaje z prehľadov cieľovej skupiny v aplikáciách Dynamics 365.
ms.date: 09/30/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: c9c7cfbf9f47cca53e5543e2cda2584e25ad855d
ms.sourcegitcommit: 1565f4f7b4e131ede6ae089c5d21a79b02bba645
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 10/14/2021
ms.locfileid: "7643467"
---
# <a name="customer-card-add-in-preview"></a>Doplnok Karta zákazníka (ukážka)

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Získajte kompletný prehľad o svojich zákazníkoch priamo v aplikáciách Dynamics 365. Keď je v podporovanej aplikácii Dynamics 365 nainštalovaný doplnok karty zákazníka, môžete sa rozhodnúť zobrazovať polia profilu zákazníka, prehľady a časovú os aktivít. Doplnok načíta údaje z Customer Insights bez ovplyvnenia údajov v pripojenej aplikácii Dynamics 365.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWN1qv]

## <a name="prerequisites"></a>Predpoklady

- Doplnok funguje iba s aplikáciami Dynamics 365 riadenými modelmi, ako sú napríklad Sales alebo Customer Service, verzia 9.0 a novšia.
- Aby sa vaše údaje Dynamics 365 mohli namapovať do profilov cieľovej skupiny, musia byť [prijaté z aplikácie Dynamics 365 pomocou konektora Microsoft Dataverse](connect-power-query.md).
- Všetci používatelia Dynamics 365 doplnku Customer Card musia byť [pridaní ako používatelia](permissions.md) v prehľade cieľových skupín, aby mohli vidieť údaje.
- [Konfigurované možnosti vyhľadávania a filtrovania](search-filter-index.md) v prehľadoch cieľovej skupiny sú nevyhnutné na fungovanie vyhľadávania údajov.
- Každá kontrola doplnku sa spolieha na konkrétne údaje vo prehľadoch cieľovej skupiny. Niektoré údaje a ovládacie prvky sú k dispozícii iba v prostrediach špecifických typov. Konfigurácia doplnku vás bude informovať, ak ovládací prvok nie je k dispozícii z dôvodu zvoleného typu prostredia. Ďalšie informácie o [prípadoch použitia prostredia](work-with-business-accounts.md).
  - **Ovládací prvok Miera**: Vyžaduje [nakonfigurované miery](measures.md) typových atribútov zákazníkov.
  - **Ovládací prvok Analýza**: Vyžaduje údaje generované pomocou [predikcií](predictions.md) alebo [vlastných modelov](custom-models.md).
  - **Ovládací prvok Podrobnosti o zákazníkovi**: Všetky polia z profilu sú k dispozícii v zjednotenom profile zákazníka.
  - **Ovládací prvok Obohatenie**: Vyžaduje sa aktívne [obohatenia](enrichment-hub.md) aplikované na profily zákazníkov.
  - **Ovládací prvok Kontakty**: Vyžaduje definíciu sémantickej entity typových kontaktov.
  - **Ovládací prvok Časová os**: Vyžadujú sa [nakonfigurované aktivity](activities.md).

## <a name="install-the-customer-card-add-in"></a>Inštalácia doplnku Karta zákazníka

Doplnok ku karte zákazníka je riešením pre aplikácie na zapojenie zákazníkov do Dynamics 365. Ak chcete nainštalovať riešenie, prejdite do AppSource a vyhľadajte **Karta zákazníka Dynamics**. Vyberte [Doplnok Karta zákazníka v AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) a vyberte **Získať teraz**.

Možno sa budete musieť prihlásiť so svojimi prihlasovacími údajmi, aby mohla aplikácia Dynamics 365 nainštalovať riešenie. Môže to trvať nejaký čas, kým sa riešenie nainštaluje do vášho prostredia.

## <a name="configure-the-customer-card-add-in"></a>Konfigurácia doplnku Karta zákazníka

1. Ako správca prejdite do časti **Nastavenia** v Dynamics 365 a vyberte položku **Riešenia**.

1. Vyberte odkaz **Zobrazovaný názov** pre riešenie **Doplnok Karta zákazníka Dynamics 365 Customer Insights (ukážka)**.

   > [!div class="mx-imgBorder"]
   > ![Výber zobrazovaného názvu.](media/select-display-name.png "Vyberte zobrazovaný názov.")

1. Vyberte **Prihlásiť sa** a zadajte prihlasovacie údaje pre účet správcu, ktorý používate na konfiguráciu Customer Insights.

   > [!NOTE]
   > Skontrolujte, či blokovanie automaticky otváraných okien v prehľadávači neblokuje overovacie okno, keď vyberiete tlačidlo **Prihlásiť sa**.

1. Vyberte prostredie Customer Insights, z ktorého chcete načítať údaje.

1. Definujte mapovanie poľa na záznamy v aplikácii Dynamics 365. V závislosti od vašich údajov v Customer Insights môžete mapovať nasledujúce možnosti:
   - Na mapovanie ku kontaktu vyberte pole v entite Zákazník, ktoré sa zhoduje s ID entity vášho kontaktu.
   - Na mapovanie k obchodnému vzťahu vyberte pole v entite Zákazník, ktoré sa zhoduje s ID entity vášho obchodného vzťahu.

   > [!div class="mx-imgBorder"]
   > ![Pole ID kontaktu.](media/contact-id-field.png "Pole ID kontaktu.")

1. Stlačením možnosti **Uložiť konfiguráciu** uložte nastavenia.

1. Ďalej musíte v Dynamics 365 prideliť roly zabezpečenia, aby si používatelia mohli prispôsobiť a vidieť Kartu zákazníka. V aplikácii Dynamics 365 prejdite do časti **Nastavenie** > **Zabezpečenie** > **Používatelia**. Vyberte používateľov, ktorých chcete upraviť, a vyberte **Spravovať roly**.

1. Priraďte rolu **Prispôsobovač karty služby Customer Insights** používateľom, ktorí prispôsobia obsah zobrazený na karte pre celú organizáciu.

## <a name="add-customer-card-controls-to-forms"></a>Pridanie ovládacích prvkov Zákazníckej karty do formulárov

V závislosti od vášho scenára sa môžete rozhodnúť pridať ovládacie prvky do ktoréhokoľvek z formulárov **Kontakt** alebo **Obchodný vzťah**. Ak používate prostredie s prehľadmi cieľovej skupiny pre firemné obchodné vzťahy, odporúčame vám pridať ovládacie prvky do formulára Obchodný vzťah. V takom prípade nahraďte „kontakt“ v nižšie uvedených krokoch „obchodným vzťahom“.

1. Ak chcete pridať ovládacie prvky Karty zákazníka do svojho formulára Kontakt, prejdite na stránku **Nastavenia** > **Prispôsobenia** v Dynamics 365.

1. Stlačte možnosť **Prispôsobenie systému**.

1. Vyhľadajte entitu **Kontakt**, rozbaľte ju a potom vyberte položku **Formuláre**.

1. Vyberte formulár kontaktu, do ktorého chcete pridať ovládacie prvky Karta zákazníka.

    > [!div class="mx-imgBorder"]
    > ![Výber formulára kontaktu.](media/contact-active-forms.png "Vyberte formulár Kontakt.")

1. Ak chcete pridať ovládací prvok, v editore formulárov presuňte ľubovoľné pole z **Prieskumníka polí** na miesto, kde sa má zobraziť ovládací prvok.

1. Vyberte pole vo formulári, ktoré ste práve pridali, a potom položku **Zmeniť vlastnosti**.

1. Prejdite na kartu **Ovládacie prvky** a vyberte položku **Pridať ovládací prvok**. Vyberte jeden z dostupných vlastných ovládacích prvkov a potom položku **Pridať**.

1. V dialógovom okne **Vlastnosti poľa** zrušte začiarknutie políčka **Zobraziť menovku vo formulári**.

1. Vyberte možnosť **Web** pre ovládací prvok. Pre kontrolu obohatenia vyberte typ obohatenia, ktorý chcete zobraziť, nakonfigurovaním poľa **enrichmentType**. Pre každý typ obohatenia pridajte samostatnú kontrolu obohatenia.

1. Výberom **Uložiť** a **Publikovať** zverejnite aktualizovaný kontaktný formulár.

1. Prejdite na publikovaný kontaktný formulár. Uvidíte novo pridaný ovládací prvok. Možno sa budete musieť prihlásiť pri prvom použití.

1. Ak chcete prispôsobiť, čo chcete zobraziť vo vlastnom ovládacom prvku, vyberte tlačidlo Upraviť v pravom hornom rohu.

## <a name="upgrade-customer-card-add-in"></a>Aktualizácia doplnku Karta zákazníka

Doplnok Karta zákazníka sa neaktualizuje automaticky. Ak chcete aktualizovať na najnovšiu verziu, v aplikácii Dynamics 365, v ktorej je doplnok nainštalovaný, postupujte nasledovne.

1. V aplikácii Dynamics 365 prejdite na **Nastavenia** > **Prispôsobenie** a vyberte **Riešenia**.

1. V tabuľke doplnkov hľadajte **CustomerInsightsCustomerCard** a vyberte riadok.

1. Vyberte **Aplikovať inováciu riešenia** v lište akcií.

   :::image type="content" source="media/customer-card-add-in-upgrade.png" alt-text="Inovujte riešenie v oblasti Prispôsobenie aplikácií Dynamics 365.":::

1. Po spustení procesu inovácie sa vám bude zobrazovať indikátor načítania, kým sa aktualizácia nedokončí. Ak nie je k dispozícii novšia verzia, pri inovácii sa zobrazí chybové hlásenie.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
