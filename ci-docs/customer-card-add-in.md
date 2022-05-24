---
title: Doplnok zákazníckej karty pre aplikácie Dynamics 365 (obsahuje video)
description: Zobrazujte údaje profilu zákazníka z Customer Insights v aplikáciách Dynamics 365 pomocou tohto doplnku.
ms.date: 02/02/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: Nils-2m
ms.author: nikeller
manager: shellyha
searchScope:
- ci-customers-page
- ci-search-filter
- ci-customer-card
- customerInsights
ms.openlocfilehash: 8508880bb3274bb491a314a043a5222d4d381073
ms.sourcegitcommit: 4ae316c856b8de0f08a4605f73e75a8c2cf51c4e
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 05/13/2022
ms.locfileid: "8755655"
---
# <a name="customer-card-add-in-preview"></a>Doplnok Karta zákazníka (ukážka)

Získajte kompletný prehľad o svojich zákazníkoch priamo v aplikáciách Dynamics 365. Keď je v podporovanej aplikácii Dynamics 365 nainštalovaný doplnok karty zákazníka, môžete sa rozhodnúť zobrazovať polia profilu zákazníka, prehľady a časovú os aktivít. Doplnok načíta údaje z Customer Insights bez ovplyvnenia údajov v pripojenej aplikácii Dynamics 365.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWN1qv]

## <a name="prerequisites"></a>Predpoklady

- Doplnok funguje iba s aplikáciami Dynamics 365 riadenými modelmi, ako sú napríklad Sales alebo Customer Service, verzia 9.0 a novšia.
- Odporúčame vám, aby sa vaše údaje Dynamics 365 namapovali na zákaznícke profily Customer Insights [prijaté z aplikácie Dynamics 365 pomocou Microsoft Dataverse konektor](connect-power-query.md). Ak na prijímanie kontaktov (alebo účtov) Dynamics 365 používate inú metódu, musíte sa uistiť`contactid` (alebo`accountid`) je nastavené ako [primárny kľúč pre tento zdroj údajov v kroku mapy procesu zjednotenia údajov](map-entities.md#select-primary-key-and-semantic-type-for-attributes).
- Všetci používatelia Dynamics 365 doplnku Zákaznícka karta musia byť [pridané ako používatelia](permissions.md) v Customer Insights, aby ste videli údaje.
- [Konfigurované možnosti vyhľadávania a filtrovania](search-filter-index.md) v Customer Insights sú potrebné na fungovanie vyhľadávania údajov.
- Každý ovládací prvok doplnku závisí od konkrétnych údajov v Customer Insights. Niektoré údaje a ovládacie prvky sú k dispozícii iba v prostrediach špecifických typov. Konfigurácia doplnku vás bude informovať, ak ovládací prvok nie je dostupný z dôvodu zvoleného typu prostredia. Ďalšie informácie o [prípadoch použitia prostredia](work-with-business-accounts.md).
  - **Ovládací prvok Miera**: Vyžaduje [nakonfigurované miery](measures.md) typových atribútov zákazníkov.
  - **Kontrola inteligencie** : Vyžaduje údaje generované pomocou [predpovede alebo vlastné modely](predictions-overview.md).
  - **Ovládací prvok Podrobnosti o zákazníkovi**: Všetky polia z profilu sú k dispozícii v zjednotenom profile zákazníka.
  - **Ovládací prvok Obohatenie**: Vyžaduje sa aktívne [obohatenia](enrichment-hub.md) aplikované na profily zákazníkov. Doplnok karty podporuje tieto vylepšenia: [Značky](enrichment-microsoft.md) poskytované spoločnosťou Microsoft, [Záujmy](enrichment-microsoft.md) poskytované spoločnosťou Microsoft a [Údaje o zapojení do kancelárie](enrichment-office.md) poskytovaná spoločnosťou Microsoft.
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

V závislosti od vášho scenára sa môžete rozhodnúť pridať ovládacie prvky do ktoréhokoľvek z formulárov **Kontakt** alebo **Obchodný vzťah**. Ak je vaše prostredie Customer Insights pre firemné účty, odporúčame vám pridať ovládacie prvky do formulára Účet. V takom prípade nahraďte „kontakt“ v nižšie uvedených krokoch „obchodným vzťahom“.

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

## <a name="troubleshooting"></a>Riešenie problémov

### <a name="controls-from-customer-card-add-in-dont-find-data"></a>Ovládacie prvky z doplnku zákazníckej karty nenájdu údaje

**problém:**

Dokonca aj pri správne nakonfigurovaných poliach ID nemôžu ovládacie prvky nájsť údaje pre žiadneho zákazníka.  

**Riešenie:**

1. Uistite sa, že ste nakonfigurovali doplnok karty podľa pokynov: [Nakonfigurujte doplnok Zákaznícka karta](#configure-the-customer-card-add-in)

1. Skontrolujte konfiguráciu prijímania údajov. Upravte zdroj údajov pre systém Dynamics 365, ktorý obsahuje ID kontaktu GUID. Ak sa ID kontaktu GUID zobrazuje s veľkými písmenami Power Query editor, skúste nasledujúce kroky:
    1. Upravte zdroj údajov a otvorte zdroj údajov v Power Query Editor.
    1. Vyberte stĺpec ID kontaktu.
    1. Vyberte **Transformovať** v hlavičke zobrazíte dostupné akcie.
    1. Vyberte **malými písmenami**. Overte, či sú GUID v tabuľke teraz malé.
    1. Uložte zdroj údajov.
    1. Spustite prijímanie údajov, zjednotenie a následné procesy na šírenie zmien do GUID.

Po dokončení úplného obnovenia systému by ovládacie prvky doplnku zákazníckej karty mali zobrazovať očakávané údaje.

[!INCLUDE [footer-include](includes/footer-banner.md)]
