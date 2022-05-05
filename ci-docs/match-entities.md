---
title: Priraďovanie entít na účely zjednotenia údajov
description: Priraďujte entity na účely vytvorenia jednotných profilov zákazníkov.
ms.date: 02/07/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-match
- ci-merge
- ci-map
- customerInsights
ms.openlocfilehash: 44f030f69b84a00438e92aa5fddca832f4e54c41
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 04/27/2022
ms.locfileid: "8643376"
---
# <a name="match-entities"></a>Priradenie entít

Fáza zosúladenia určuje, ako skombinovať vaše množiny údajov do množiny údajov zjednoteného profilu zákazníka. Po dokončení [kroku mapy](map-entities.md) v procese zjednotenia údajov ste pripravení priradiť svoje entity. Fáza zosúladenia vyžaduje aspoň dve mapované entity.

Stránka priraďovania sa skladá z troch častí: 
- Kľúčové metriky, ktoré sumarizujú počet priradených záznamov
- Poradie zhody a pravidlá pre priraďovanie medzi entitami
- Pravidlá pre deduplikáciu zhodných entít

## <a name="specify-the-match-order"></a>Určenie objednávky zosúladenia

Každá zhoda zjednocuje dve alebo viac entít do jednej konsolidovanej entity. Zároveň vedie jedinečné záznamy o zákazníkoch. Poradie zhody označuje poradie, v ktorom sa systém pokúša priradiť záznamy.

> [!IMPORTANT]
> Entita, ktorú vyberiete ako primárnu, bude slúžiť ako základ pre jednotnú množinu údajov profilov. Ďalšie entity, ktoré sú vybraté počas fázy zosúladenia, sa pridajú do tejto entity. To neznamená, že zjednotená entita bude obsahovať *všetky* údaje zahrnuté v tejto entite.
>
> Existujú dva aspekty, ktoré vám môžu pomôcť pri výbere hierarchie entít:
>
> - Vyberte entitu s najkompletnejšími a najspoľahlivejšími profilovými údajmi o vašich zákazníkoch ako primárnu entitu.
> - Vyberte entitu, ktorá má niekoľko spoločných atribútov s inými entitami (napríklad meno, telefónne číslo alebo e-mailovú adresu), ako primárnu entitu.

1. Prejdite do ponuky **Údaje** > **Zjednotiť** > **Spárovať** a vyberte **Nastaviť poradie** na začatie fázy spárovania.
1. Vyberte **Objednávka entity**. Napríklad vyberte **Elektronický obchod:Kontakty elektronického obchodu** ako primárny subjekt a **LoyaltyScheme:loyCustomers** ako druhý subjekt. 
1. Ak chcete, aby každý záznam v entite bol jedinečným zákazníkom a priradený ku každej nasledujúcej entite, vyberte **Zahrňte všetky**.
1. Vyberte položku **Hotovo**. 

Po zadaní poradia zhody sa definované dvojice zhody zobrazia v **Podrobnosti o zhodných záznamoch** oddiel na **Údaje** > **Zjednotiť** > **Zápas**. Kľúčové metriky sú prázdne, kým sa proces zhody nedokončí.

:::image type="content" source="media/match-page.png" alt-text="Snímka obrazovky stránky Priradenie v oblasti Zjednotiť procesu zjednotenia údajov.":::
  
Primárna entita *eCommerce:eCommerceContacts* sa porovnáva s ďalšou entitou *LoyaltyScheme:loyCustomers*. Ak máte viac ako dve entity, množina údajov, ktorá je výsledkom prvého kroku zhody, sa zhoduje s nasledujúcou entitou.

## <a name="define-rules-for-match-pairs"></a>Definujte pravidlá pre dvojice párov

Pravidlá zosúladenia určujú logiku, podľa ktorej budú zosúladené špecifické dvojice entít.

Varovanie **Vyžadujú sa pravidlá** vedľa názvu entity naznačuje, že pre párový pár nie je definované žiadne pravidlo zhody. 

:::image type="content" source="media/match-rule-add.png" alt-text="Snímok obrazovky sekcie Podrobnosti o zhodnom zázname s ovládacím prvkom na pridanie zvýraznených pravidiel.":::

1. Vyberte **Pridať pravidlo** pod subjektom v **Podrobnosti o zhodných záznamoch** sekciu na definovanie pravidiel zápasu.

1. V table **Vytvoriť pravidlo** nakonfigurujte podmienky pravidla.

   :::image type="content" source="media/match-rule-conditions.png" alt-text="Snímka obrazovky otvoreného pravidla zhody s pridanými podmienkami.":::

   - **Entita/pole (prvý riadok)**: Vyberte súvisiacu entitu a atribút, aby ste určili vlastnosť záznamu, ktorá je pre zákazníka pravdepodobne jedinečná. Napríklad telefónne číslo alebo e-mailová adresa. Vyvarujte sa zhody podľa atribútov typu aktivity. Napríklad ID nákupu pravdepodobne nenájde zhodu v iných typoch záznamov.

   - **Entita/pole (druhý riadok)**: Vyberte atribút, ktorý sa týka atribútu entity uvedenej v prvom riadku.

   - **Normalizovať**: Vyberte si z nasledujúcich možností normalizácie pre vybrané atribúty. 
     - Číslice: Konvertuje ďalšie číselné systémy, napríklad rímske, na arabské číslice. *VIII* sa stane *8*.
     - Symboly: Odstráni všetky symboly a špeciálne znaky. *Head&Shoulder* sa stáva *HeadShoulder*.
     - Text na malé písmená: Konvertuje všetky znaky na malé písmená. *VŠETKY PÍSMENÁ VEĽKÉ a Nadpis* sa stáva *všetky písmená veľké a nadpis*.
     - Typ (telefón, meno, adresa, organizácia): Štandardizuje mená, tituly, telefónne čísla, adresy atď. 
     - Unicode na ASCII: Konvertuje notáciu Unicode na znaky ASCII. */u00B2* sa stáva *2*.
     - Medzery: Odstráni všetky medzery. *Ahoj svet* sa stáva *HelloWorld*.

   - **Presnosť**: Nastavte úroveň presnosti, ktorá sa má použiť pre túto podmienku. 
     - **Základné**: Vyber z možností *Nízka*, *Stredná*, *Vysoká* a *Presná*. Vyberte **Presne** aby sa zhodovali iba záznamy, ktoré sa stopercentne zhodujú. Vyberte jednu z ďalších úrovní, aby sa zosúladili záznamy, ktoré nie sú na 100 percent identické.
     - **Vlastné**: Nastavte percento, ktorému sa musia záznamy zhodovať. Systém bude porovnávať iba záznamy prekračujúce tento limit.

1. Zadajte **Názov** pre položku pravidla.

1. [Pridajte ďalšie podmienky](#add-conditions-to-a-rule) alebo stlačte **Hotovo** a dokončite pravidlo.

1. Voliteľne stlačte možnosť [pridať ďalšie pravidlá](#add-rules-to-a-match-pair).

1. Zmeny vykonajte výberom položky **Uložiť**.

### <a name="add-conditions-to-a-rule"></a>Pridanie podmienok k pravidlu

Ak chcete priradiť entity, iba ak atribúty spĺňajú viac podmienok, pridajte do pravidla zhody ďalšie podmienky. Podmienky sú spojené s logickým operátorom AND a tak sa vykonávajú iba vtedy, ak sú splnené všetky podmienky.

1. Prejdite do časti **Údaje** > **Zjednotiť** > **Priradiť** a vyberte **Upraviť** pri pravidle, ku ktorému chcete pridať podmienky.

1. Na table **Upraviť pravidlo** vyberte položku **Pridať podmienku**.

1. Ak chcete pravidlo uložiť, kliknite na položku **Hotovo**.

### <a name="add-rules-to-a-match-pair"></a>Pridajte pravidlá k páru

Pravidlá spárovania predstavujú súbory podmienok. Ak chcete priradiť entity podľa podmienok na základe viacerých atribútov, pridajte ďalšie pravidlá.

1.  Prejdite do časti **Údaje** > **Zjednotiť** > **Priradiť** a vyberte **Pridať pravidlo** pri entite, ku ktorej chcete pridať podmienky.

2. Postupujte podľa pokynov v časti [Definujte pravidlá pre dvojice párov](#define-rules-for-match-pairs).

> [!NOTE]
> Na poradí pravidiel záleží. Algoritmus priraďovania sa pokúša zhodovať na základe vášho prvého pravidla a na druhé pravidlo pokračuje, iba ak s prvým pravidlom neboli identifikované žiadne zhody.

### <a name="change-the-entity-order-in-match-rules"></a>Zmeňte poradie entít v pravidlách zhody

Môžete zmeniť poradie entít pre pravidlá zhody, aby ste zmenili poradie, v ktorom sú spracované. Pravidlá, ktoré sú v rozpore so zmeneným poradím, budú odstránené. Odstránené pravidlá musíte znova vytvoriť v aktualizovanej konfigurácii.

1. Prejdite do ponuky **Údaje** > **Zjednotiť** > **Spárovanie** a stlačte možnosť **Upraviť**.

1. Na table **Upraviť pravidlo** stlačte ovládací prvok **Pohyb hore/dole** alebo presúvaním entít môžete meniť poradie.

   :::image type="content" source="media/reorder-match-rules.png" alt-text="Možnosti zmeny, v akom poradí sa entity spracovávajú vo fáze spárovania.":::

1. Ak chcete pravidlo uložiť, kliknite na položku **Hotovo**.

## <a name="define-deduplication-on-a-match-entity"></a>Definovanie deduplikácie na priradenej entite

Okrem [pravidlá zhody medzi entitami](#define-rules-for-match-pairs), môžete tiež určiť pravidlá deduplikácie. *Deduplikácia* je ďalší proces pri párovaní záznamov. Identifikuje duplicitné záznamy a zlúčte ich do jedného záznamu. Zdrojové záznamy sa prepoja so zlúčeným záznamom s alternatívnymi ID.

Deduplikované záznamy sa používajú v procese porovnávania medzi entitami. Deduplikácia prebieha na jednotlivých entitách a možno ju nakonfigurovať pre každú entitu používanú v pároch zhody.

Zadávanie pravidiel deduplikácie nie je povinné. Ak nie sú nakonfigurované žiadne takéto pravidlá, použijú sa systémovo definované pravidlá. Kombinujú všetky záznamy do jedného záznamu pred odovzdaním údajov entity do porovnávania medzi entitami na zvýšenie výkonu.

### <a name="add-deduplication-rules"></a>Pridanie pravidiel deduplikácie

1. Prejdite na **Údaje** > **Zjednotenie** > **Spárovanie**.

1. V **Podrobnosti o deduplikovaných záznamoch** sekciu, vyberte **Nastaviť entity**. Ak sú pravidlá deduplikácie už vytvorené, vyberte možnosť **Upraviť**.

1. V table **Predvoľby zlúčenia** vyberte entity, na ktoré chcete použiť deduplikáciu.

   1. Uveďte, ako sa majú kombinovať duplicitné záznamy, a vyberte jednu z troch možností zlúčenia:
      - **Najviac vyplnené**: Identifikuje záznam s najviac vyplnenými poľami atribútov ako víťazný záznam. Toto je predvolená možnosť zlučovania.
      - **Najnovšie**: Identifikuje víťazný záznam na základe najväčšej aktuálnosti. Na definovanie aktuálnosti sa vyžaduje dátum alebo číselné pole.
      - **Najstaršie**: Identifikuje víťazný záznam na základe najmenšej aktuálnosti. Na definovanie aktuálnosti sa vyžaduje dátum alebo číselné pole.

   1. Voliteľne, ak chcete definovať pravidlá deduplikácie pre jednotlivé atribúty entity, vyberte **Pokročilé**. Môžete sa napríklad rozhodnúť ponechať najnovší e-mail A najkompletnejšiu adresu z rôznych záznamov. Rozbaľte entitu, aby ste videli všetky jej atribúty a definujte, ktorá možnosť sa má použiť pre jednotlivé atribúty. Ak vyberiete možnosť založenú na aktuálnosti, musíte tiež zadať pole dátumu a času, ktoré definuje aktuálnosť. 
 
      > [!div class="mx-imgBorder"]
      > ![Krok 1 pri pravidlách deduplikácie.](media/match-selfconflation.png "Krok 1 pri pravidlách deduplikácie")

   1. Vyberte **hotový** na použitie vašich preferencií zlúčenia na deduplikáciu.
 
1. Po výbere entít a nastavení predvoľby zlúčenia vyberte položku **Pridať pravidlo** a definujte pravidlá deduplikácie na úrovni entity.
   - Možnosť **Vybrať pole** vypíše všetky dostupné polia od tejto entity. Vyberte pole, v ktorom chcete skontrolovať duplikáty. Vyberte polia, ktoré sú pravdepodobne jedinečné pre každého zákazníka. Napríklad e-mailová adresa alebo kombinácia mena, mesta a telefónneho čísla.
   - Zadajte nastavenie normalizácie a presnosti.
   - Definujte ďalšie podmienky výberom položky **Pridať podmienku**.
 
   > [!div class="mx-imgBorder"]
   > ![Krok 2 pri pravidlách deduplikácie.](media/match-selfconflation-rules.png "Krok 2 pri pravidlách deduplikácie")

  Pre entitu môžete vytvoriť viacero pravidiel deduplikácie. 

1. Spustením procesu priradenia teraz zoskupíte záznamy na základe podmienok definovaných v pravidlách deduplikácie. Po zoskupení záznamov sa na identifikáciu víťazného záznamu použije politika zlúčenia.

1. Tento víťazný záznam sa potom odovzdá na párovanie medzi entitami spolu so záznamami, ktoré nie sú víťazné (napríklad alternatívne ID), aby sa zlepšila kvalita párovania.

1. Všetky definované vlastné pravidlá zhody prepíšu pravidlá deduplikácie. Ak pravidlo deduplikácie identifikuje priradené záznamy a ak je nastavené vlastné pravidlo priraďovania, ktoré sa nikdy nebude zhodovať s týmito záznamami, potom sa tieto dva záznamy nezhodujú.

1. Po [spustenie procesu zápasu](#run-the-match-process), uvidíte štatistiky deduplikácie v dlaždiciach kľúčových metrík.

### <a name="deduplication-output-as-an-entity"></a>Výstup deduplikácie ako entita

Proces deduplikácie vytvorí novú entitu pre každú entitu z páru na identifikáciu deduplikovaných záznamov. Tieto entity možno nájsť spolu s **ConflationMatchPairs:CustomerInsights** v sekcii **Systém** na stránke **Entity** s názvom **Deduplication_DataSource_Entity**.

Entita deduplikovaného výstupu obsahuje nasledujúce informácie:
- ID/kľúče
  - Pole primárneho kľúča a jeho alternatívne ID pole. Alternatívne ID pole obsahuje všetky alternatívne ID identifikované pre záznam.
  - Pole Deduplication_GroupId zobrazuje skupinu alebo klaster identifikovaný v rámci entity, ktorá zoskupuje všetky podobné záznamy na základe zadaných deduplikačných polí. Používa sa na účely spracovania systému. Ak nie sú zadané žiadne pravidlá manuálnej deduplikácie a uplatňujú sa pravidlá systému definované pre deduplikáciu, toto pole v entite výstupu deduplikácie nenájdete.
  - Deduplication_WinnerId: Toto pole obsahuje ID víťaza z identifikovaných skupín alebo klastrov. Ak je hodnota Deduplication_WinnerId rovnaká ako hodnota primárneho kľúča pre záznam, znamená to, že záznam je víťazným záznamom.
- Polia používané na definovanie pravidiel deduplikácie.
- Polia Pravidlo a Skóre označujú, ktoré z pravidiel deduplikácie sa použili a skóre vrátené algoritmom párovania.
 
## <a name="include-enriched-entities-preview"></a>Zahrnúť obohatené entity (ukážka)

Ak ste obohatili entity na úrovni zdroj údajov, vyberte ich pred spustením procesu zhody. Obohatené entity môžu zlepšiť vaše výsledky zjednotenia. Viac informácií nájdete v časti [Obohatenie pre zdroje údajov](data-sources-enrichment.md). 

Obohatená entita obsahuje pôvodné polia zdroj údajov a obohatené polia. Ak sa teda rozhodnete pracovať s obohatenou entitou, existujúca konfigurácia nebude ovplyvnená. Možno však budete musieť aktualizovať pravidlá zhody, aby ste namiesto toho používali obohatené polia.

1. Ísť do **Údaje** > **Zjednotiť** > **Zápas** a vyberte **Použite obohatené entity** v hornej časti stránky.

1. Od **Použite obohatené entity** vyberte jednu alebo viacero obohatených entít.

1. Vyberte položku **Hotovo**. Kdekoľvek sa použije zdrojová entita (napríklad poradie alebo pravidlá zhody), automaticky sa zmení na obohatenú entitu.
  
## <a name="run-the-match-process"></a>Spustenie procesu spárovania

Po konfigurovaní pravidiel priraďovania vrátane pravidiel priradenia medzi entitami a pravidiel deduplikácie môžete spustiť proces priraďovania. 

Prejdite do časti **Údaje** > **Zjednotiť** > **Spárovať** a vyberte **Spustiť** na spustenie procesu. Dokončenie porovnávacieho algoritmu trvá istý čas a konfiguráciu nemôžete zmeniť, kým sa nedokončí. Ak chcete pristúpiť k zmenám, môžete zrušiť spustenie. Vyberte stav úlohy a zvoľte **Zrušiť úlohu** na table **Podrobnosti o postupe**.

Výsledok úspešného spustenia, entita zjednoteného profilu zákazníka, nájdete na stránke **Entity**. Vaša zjednotená entita zákazníka sa nazývala **Zákazníci** v časti **Profily**. Prvé úspešné spustenie priradenia vytvára zjednotenú entitu *Zákazník*. Všetky nasledujúce spustenia zhôd túto entitu rozširujú.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="review-and-validate-your-matches"></a>Kontrola a potvrdenie zosúladených výsledkov

Prejdite do časti **Údaje** > **Zjednotiť** > **Spárovanie** a vyhodnoťte kvalitu svojich spárovaní a v prípade potreby ich vylepšite.

Dlaždice v hornej časti stránky zobrazujú kľúčové metriky, ktoré sumarizujú počet zhodných záznamov a duplikátov.

:::image type="content" source="media/match-KPIs.png" alt-text="Orezaná snímka obrazovky s kľúčovými metrikami na stránke Zhoda s číslami a podrobnosťami.":::

- **Jedinečné zdrojové záznamy** zobrazuje počet jednotlivých zdrojových záznamov, ktoré boli spracované v poslednom spustení priraďovania.
- **Spárované a nespárované záznamy** zdôrazňuje, koľko jedinečných záznamov zostáva po spracovaní pravidiel zhody.
- **Iba zodpovedajúce záznamy** zobrazuje počet spárovaní vo všetkých vašich pároch.

Výsledky každého páru a jeho pravidlá môžete posúdiť v table **Podrobnosti o zhodných záznamoch**. Porovnajte počet záznamov, ktoré pochádzajú zo zhodnej dvojice, s percentom úspešne zhodných záznamov.

Prezrite si pravidlá spárovania a uvidíte percento úspešne zhodných záznamov na úrovni pravidiel. Vyberte elipsu (...) a potom stlačte možnosť **Ukážka zhody** na zobrazenie všetkých týchto záznamov na úrovni pravidla. Odporúčame vám pozrieť sa na niektoré záznamy, aby ste overili, či boli správne priradené.

Vyskúšajte rôzne prahové hodnoty presnosti za určitých podmienok, aby ste našli optimálnu hodnotu.

  1. Vyberte elipsu (...) pre pravidlo, s ktorým chcete experimentovať, a vyberte možnosť **Upraviť**.

  2. Zmeňte hodnoty presnosti v podmienkach, ktoré chcete upraviť.

  3. Stlačte **Ukážka** a pozrite si počet spárovaných a nepárovaných záznamov pre vybranú podmienku.

## <a name="manage-match-rules"></a>Spravovať pravidlá spárovania

Väčšinu parametrov zhody môžete prekonfigurovať a doladiť.

:::image type="content" source="media/match-rules-management.png" alt-text="Snímka obrazovky s rozbaľovacou ponukou s možnosťami pravidla zhody.":::

- Ak ste definovali viacero pravidiel, **zmeňte poradie vašich pravidiel**. Môžete zmeniť poradie pravidiel spárovania stlačením položky **Posunúť nahor** a **Posunúť nadol** alebo pretiahnutím.

- **Zmeňte podmienky pravidla** stlačením možnosti **Upraviť** a zvoľte si rôzne polia.

- **Deaktivovať pravidlo** na zachovanie pravidla párovania pri jeho vylúčení z procesu párovania.

- **Duplikujte svoje pravidlá** ak ste definovali pravidlo zhody a chcete vytvoriť podobné pravidlo s úpravami, zvoľte **Duplikovať**.

- **Odstráňte pravidlo** stlačením symbolu **Odstrániť**.

## <a name="advanced-options"></a>Rozšírené možnosti

### <a name="add-exceptions-to-a-rule"></a>Pridajte do pravidla výnimky

Vo väčšine prípadov zhoda entity vedie k jedinečným užívateľským profilom s konsolidovanými údajmi. Ak chcete dynamicky riešiť zriedkavé prípady falošne pozitívnych a falošne negatívnych výsledkov, môžete definovať výnimky pre pravidlo zhody. Výnimky sa uplatňujú po spracovaní pravidiel zhody a vyhýbajú sa zhodovaniu všetkých záznamov, ktoré spĺňajú kritériá výnimky.

Napríklad, ak vaše pravidlo zhody kombinuje priezvisko, mesto a dátum narodenia, systém identifikuje dvojčatá s rovnakým priezvisko, ktoré žijú v rovnakom meste ako rovnaký profil. Môžete zadať výnimku, ktorá sa nezhoduje s profilmi, ak krstné meno v entitách, ktoré kombinujete, nie sú rovnaké.

1. Prejdite do časti **Údaje** > **Zjednotiť** > **Priradiť** a vyberte **Upraviť** pri pravidle, ku ktorému chcete pridať podmienky.

1. V **Upraviť pravidlo** panel, vyberte **Pridať výnimku**.

1. Zadajte kritériá výnimiek. 

1. Ak chcete pravidlo uložiť, kliknite na položku **Hotovo**.

### <a name="specify-custom-match-conditions"></a>Zadajte vlastné podmienky spárovania

Môžete zadať podmienky, ktoré prepíšu predvolenú logiku zhody. K dispozícii sú štyri možnosti: 

|Možnosť  |Description |Príklad  |
|---------|---------|---------|
|Vždy sa zhodovať     | Definuje hodnoty, ktoré sa vždy zhodujú.         |  Vždy sa zhodujú *Mike* a *MikeR*.       |
|Nikdy sa nezhodovať     | Definuje hodnoty, ktoré sa nikdy nezhodujú.        | Nikdy sa nezhodujte *John* a *Jonathan*.        |
|Vlastné obídenie     | Definuje hodnoty, ktoré by mal systém vždy ignorovať vo fáze zápasu. |  Ignorujte hodnoty *11111* a *Neznámy* počas zápasu.        |
|Mapovanie aliasu    | Definovanie hodnôt, ktoré by mal systém považovať za rovnakú hodnotu.         | Zvážte *Joe* byť rovný *Jozefa*.        |

1. Prejdite do časti **Údaje** > **Zjednotiť** > **Spárovanie** a stlačte **Vlastná zhoda** v časti **Podrobnosti o zhodných záznamoch**.

   :::image type="content" source="media/custom-match-create.png" alt-text="Snímok obrazovky sekcie pravidiel spárovania so zvýrazneným vlastným ovládacím prvkom spárovania.":::

1. V **Vlastné** panel, prejdite na **Záznamy** tab.

1. Vyberte možnosť vlastnej zhody z **Vlastný typ** rozbaľovací zoznam a vyberte **Stiahnite si šablónu**. Pre každú možnosť zhody potrebujete samostatnú šablónu.

1. Otvorte stiahnutý súbor šablóny a vyplňte podrobnosti. Šablóna obsahuje polia na určenie hodnôt entity a primárneho kľúča entity, ktoré sa majú použiť pri vlastnom zosúlaďovaní. Napríklad ak chcete primárny kľúč *12345* od entity *Predaj*, aby sa vždy zhodoval s primárnym kľúčom *34567* od entity *Kontakt*, vyplňte šablónu:
    - Entity1: Predaj
    - Entity1Key: 12345
    - Entity2: Kontakt
    - Entity2Key: 34567

   Rovnaký súbor šablóny môže určiť vlastné záznamy zosúlaďovania z viacerých entít.
   
   Ak chcete určiť vlastné párovanie pre deduplikáciu entity, zadajte rovnakú entitu pre Entitu1 aj Entitu2 a nastavte rôzne hodnoty primárneho kľúča.

1. Po pridaní všetkých prepísaní uložte súbor šablóny.

1. Prejdite na **Údaje** > **Zdroje údajov** a prijmite súbory šablón ako nové entity.

1. Po nahratí súborov a entít k dispozícii, vyberte znova možnosť **Vlastné zosúladenie**. Zobrazia sa možnosti na určenie entít, ktoré chcete zahrnúť. Z rozbaľovacej ponuky vyberte požadované entity a vyberte **hotový**.

   :::image type="content" source="media/custom-match-overrides.png" alt-text="Snímka obrazovky dialógového okna na výber prepísania pre vlastný scenár zhody.":::

1. Použitie vlastnej zhody závisí od možnosti zhody, ktorú chcete použiť. 

   - Pre **Vždy sa zhodujú** alebo **Nikdy sa nezhodujú**, prejdite na ďalší krok.
   - Pre **Vlastný bypass** alebo **Mapovanie aliasu**, vyberte **Upraviť** na existujúce pravidlo zhody alebo vytvorte nové pravidlo. V rozbaľovacej ponuke Normalizácie vyberte možnosť **Vlastný bypass** alebo **Mapovanie aliasu** možnosť a vyberte **hotový**.

1. Stlačte možnosť **Uložiť** na stránke **Spárovanie** použiť vlastnú konfiguráciu zhody.

1. Stlačte možnosť **Spustiť** na stránke **Zhoda** na spustenie procesu spárovania. Ostatné zadané pravidlá zhody sú prepísané vlastnou konfiguráciou zhody.

#### <a name="known-issues"></a>Známe problémy

- Vlastná konflácia neukazuje normalizované údaje v deduplikačných entitách. Normalizáciu však aplikuje interne počas deduplikácie. Je to navrhnuté pre všetky normalizácie. 
- Ak je nastavenie sémantického typu odstránené v **Mapa** fázy, keď pravidlo zhody používa mapovanie aliasu alebo vlastné obídenie, normalizácia sa nepoužije. Stáva sa to iba vtedy, ak po konfigurácii normalizácie v pravidle zhody vymažete sémantický typ, pretože sémantický typ bude neznámy.


## <a name="next-step"></a>Ďalší krok

Po dokončení procesu zápasu pre aspoň jeden zápasový pár pokračujte na [**Zlúčiť**](merge-entities.md) krok.


[!INCLUDE [footer-include](includes/footer-banner.md)]
