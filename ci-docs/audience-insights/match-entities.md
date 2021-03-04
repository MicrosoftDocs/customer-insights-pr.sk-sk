---
title: Priraďovanie entít na účely zjednotenia údajov
description: Priraďujte entity na účely vytvorenia jednotných profilov zákazníkov.
ms.date: 10/14/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: 05afd17b7f1b34f7f24a8fa8cb2dc32c1649d40f
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267497"
---
# <a name="match-entities"></a>Priradenie entít

Po dokončení fázy mapovania ste pripravení zosúladiť vaše entity. Fáza zosúladenia určuje, ako skombinovať vaše množiny údajov do množiny údajov zjednoteného profilu zákazníka. Fáza zosúladenia vyžaduje aspoň [dve mapované entity](map-entities.md).

## <a name="specify-the-match-order"></a>Určenie objednávky zosúladenia

Prejdite do ponuky **Údaje** > **Zjednotiť** > **Spárovať** a vyberte **Nastaviť poradie** na začatie fázy spárovania.

Každé zosúladenie zjednotí dve alebo viac entít do jednej entity a zároveň zachová každý jedinečný záznam zákazníka. V nasledujúcom príklade sme vybrali tri entity: **ContactCSV: TestData** ako **primárnu** entitu, **WebAccountCSV: TestData** ako **entitu 2** a **CallRecordSmall: TestData** ako **entitu 3**. Diagram nad výbermi ilustruje, ako sa vykoná objednávka zosúladenia.

> [!div class="mx-imgBorder"]
> ![Úprava objednávky zosúladenia údajov](media/configure-data-match-order-edit-page.png "Úprava objednávky zosúladenia údajov")
  
**Primárna** entita je zosúladená s **entitou 2**. Množina údajov, ktorá je výsledkom prvého zosúladenia, sa zosúlaďuje s **entitou 3**.
V tomto príklade sme vybrali len dve zosúladenia, ale systém ich môže podporovať viac.

> [!IMPORTANT]
> Entita, ktorú vyberiete ako **primárnu**, bude slúžiť ako základ pre jednotnú množinu údajov predlohy. Ďalšie entity, ktoré sú vybraté počas fázy zosúladenia, sa pridajú do tejto entity. Zároveň to neznamená, že zjednotená entita bude obsahovať *všetky* údaje zahrnuté v tejto entite.
>
> Existujú dva aspekty, ktoré vám môžu pomôcť pri výbere hierarchie entít:
>
> - O ktorej entite si myslíte, že obsahuje najúplnejšie a najspoľahlivejšie údaje o vašich zákazníkoch?
> - Má entita, ktorú ste práve určili, atribúty, ktoré zdieľajú aj iné entity (napríklad meno, telefónne číslo alebo e-mailová adresa)? Ak nie, vyberte si druhú najspoľahlivejšiu entitu.

Ak chcete uložiť objednávku zosúladenia, vyberte položku **Hotovo**.

## <a name="define-rules-for-your-first-match-pair"></a>Definovanie pravidiel pre váš prvý pár zosúladenia

Po zadaní objednávky zosúladenia sa na stránke **Zosúladiť** zobrazia definované zhody. Dlaždice v hornej časti obrazovky budú prázdne, kým nespustíte objednávku zosúladenia.

> [!div class="mx-imgBorder"]
> ![Definovanie pravidiel](media/configure-data-match-need-rules.png "Definovanie pravidiel")

Upozornenie **Vyžaduje pravidlá** informuje, že žiadne pravidlo zosúladenia nie je definované pre pár zosúladenia. Pravidlá zosúladenia určujú logiku, podľa ktorej budú zosúladené špecifické dvojice entít.

1. Ak chcete definovať prvé pravidlo, otvorte tablu **Definícia pravidla** výberom zodpovedajúceho riadka zosúladenia v tabuľke zosúladenia (1) a následným výberom položky **Vytvoriť nové pravidlo** (2).

   > [!div class="mx-imgBorder"]
   > ![Vytvoriť nové pravidlo](media/configure-data-match-new-rule2.png "Vytvoriť nové pravidlo")

2. Na table **Upraviť pravidlo** nakonfigurujte podmienky pre toto pravidlo. Každá podmienka je zastúpená dvoma riadkami, ktoré obsahujú povinné výbery.

   > [!div class="mx-imgBorder"]
   > ![Tabla nového pravidla](media/configure-data-match-new-rule-condition.png "Tabla nového pravidla")

   Entita/pole (prvé) – Atribút, ktorý sa použije na zosúladenie z prvej entity páru zosúladenia. Príkladom môže byť telefónne číslo alebo e-mailová adresa. Vyberte atribút, ktorý je pravdepodobne jedinečný pre zákazníka.

   > [!TIP]
   > Vyhýbajte sa zosúladeniu na základe atribútov typu aktivita. Inými slovami, ak sa zdá, že atribút je aktivitou, môže ísť o zlé kritérium na zosúladenie.  

   Entita/pole (druhé) – Atribút, ktorý sa použije na zosúladenie z druhej entity páru zosúladenia.

   Normalizovať – **Metóda normalizácie**: Rôzne možnosti normalizácie sú k dispozícii pre vybrané atribúty. Napríklad odstránenie interpunkcie alebo odstránenie medzier

   Pre normalizáciu názvu organizácie (náhľad) môžete tiež vybrať **typ (telefón, meno, organizácia)**

   > [!div class="mx-imgBorder"]
   > ![Normalizácia-B2B](media/match-normalization-b2b.png "Normalizácia-B2B")

   Úroveň presnosti – Úroveň presnosti, ktorá sa použije pre túto podmienku. Nastavenie úrovne presnosti pre podmienku zosúladenia môže mať dva typy: **základné** a **vlastné**.  
   - Základné: Poskytuje štyri možnosti na výber: nízka, stredná, vysoká a presná. Vyberte **presná**, aby sa zosúladili len záznamy, ktoré zodpovedajú na 100 percent. Vyberte jednu z ďalších úrovní, aby sa zosúladili záznamy, ktoré nie sú na 100 percent identické.
   - Vlastné: Pomocou jazdca definujte vlastnú percentuálnu zhodu záznamov alebo zadajte zhodu do poľa **Vlastné**. Systém zosúladí iba záznamy, ktoré presahujú tento prah. Hodnoty na jazdci sú medzi 0 a 1. Takže 0,64 predstavuje 64 percent.

3. Ak chcete pravidlo uložiť, kliknite na položku **Hotovo**.

### <a name="add-multiple-conditions"></a>Pridanie viacerých podmienok

Ak chcete zosúladiť svoje entity iba v prípade splnenia viacerých podmienok, pridajte ďalšie podmienky, ktoré sú prepojené prostredníctvom operátora A.

1. Na table **Upraviť pravidlo** vyberte položku **Pridať podmienku**. Podmienky môžete odstrániť aj tak, že vyberiete tlačidlo Odstrániť vedľa existujúcej podmienky.

2. Ak chcete pravidlo uložiť, kliknite na položku **Hotovo**.

## <a name="add-multiple-rules"></a>Pridanie viacerých pravidiel

Každá podmienka sa vzťahuje na jeden pár atribútov, zatiaľ čo pravidlá predstavujú množiny podmienok. Ak chcete, aby boli vaše entity zosúladené podľa rôznych množín atribútov, môžete pridať ďalšie pravidlá.

1. V prehľadoch cieľových skupín prejdite na **Údaje** > **Zjednotiť** > **Priradiť**.

2. Vyberte entitu, ktorú chcete zosúladiť, a potom **Pridať pravidlá**.

3. Postupujte podľa pokynov uvedených v článku [Definovanie pravidiel pre váš prvý pár zosúladenia](#define-rules-for-your-first-match-pair).

> [!NOTE]
> Záleží na poradí pravidiel. Algoritmus zosúladenia sa pokúša vykonať zosúladenie na základe vášho prvého pravidla a pokračuje v druhom pravidle, len ak sa v rámci prvého pravidla neurčili žiadne zhodné položky.

## <a name="define-deduplication-on-a-match-entity"></a>Definovanie deduplikácie na priradenej entite

Spolu so zadaním pravidiel priraďovania medzi entitami, ako je stanovené vo vyššie uvedených častiach, môžete tiež určiť pravidlá deduplikácií. *Deduplikácia* je proces. Identifikuje duplicitné záznamy, zlúci ich do jedného záznamu a prepojí všetky zdrojové záznamy s týmto zlúčeným záznamom s alternatívnymi ID k zlúčenému záznamu.

Po identifikácii deduplikovaného záznamu sa tento záznam použije v procese priraďovania medzi entitami. Deduplikácia sa implementuje na úrovni entity a je možné ju použiť na každú entitu použitú v procese priraďovania.

### <a name="add-deduplication-rules"></a>Pridanie pravidiel deduplikácie

1. V prehľadoch cieľových skupín prejdite na **Údaje** > **Zjednotiť** > **Priradiť**.

1. V sekcii **Zlúčené duplikáty** vyberte položku **Nastaviť entity**.

1. V sekcii **Predvoľby zlúčenia** vyberte entity, na ktoré chcete použiť deduplikáciu.

1. Uveďte, ako sa majú zlúčiť duplicitné záznamy, a vyberte jednu z troch možností zlúčenia:
   - *Najviac vyplnené*: Identifikuje záznam s najviac vyplnenými atribútmi ako víťazný záznam. Toto je predvolená možnosť zlučovania.
   - *Najnovšie*: Identifikuje víťazný záznam na základe najväčšej aktuálnosti. Na definovanie aktuálnosti sa vyžaduje dátum alebo číselné pole.
   - *Najstaršie*: Identifikuje víťazný záznam na základe najmenšej aktuálnosti. Na definovanie aktuálnosti sa vyžaduje dátum alebo číselné pole.
 
   > [!div class="mx-imgBorder"]
   > ![Krok 1 pri pravidlách deduplikácie](media/match-selfconflation.png "Krok 1 pri pravidlách deduplikácie")
 
1. Po výbere entít a nastavení predvoľby zlúčenia vyberte položku **Vytvoriť nové pravidlo** a definujte pravidlá deduplikácie na úrovni entity.
   - **Vybrať pole** obsahuje zoznam všetkých dostupných polí z entity, pre ktorú chcete deduplikovať zdrojové údaje.
   - Zadajte nastavenie normalizácie a presnosti podobným spôsobom, aký je uvedený pri priraďovaní medzi entitami.
   - Ďalšie podmienky môžete definovať výberom položky **Pridať podmienku**.
 
   > [!div class="mx-imgBorder"]
   > ![Krok 2 pri pravidlách deduplikácie](media/match-selfconflation-rules.png "Krok 2 pri pravidlách deduplikácie")

  Pre entitu môžete vytvoriť viacero pravidiel deduplikácie. 

1. Spustením procesu priradenia teraz zoskupíte záznamy na základe podmienok definovaných v pravidlách deduplikácie. Po zoskupení záznamov sa na identifikáciu víťazného záznamu použije politika zlúčenia.

1. Tento víťazný záznam sa potom odovzdá na párovanie medzi entitami spolu so záznamami, ktoré nie sú víťazné (napríklad alternatívne ID), aby sa zlepšila kvalita párovania.

1. Akékoľvek vlastné pravidlá priraďovania definované pre možnosti vždy priradiť a nikdy nepriradiť majú väčšiu prioritu ako pravidlá deduplikácie. Ak pravidlo deduplikácie identifikuje priradené záznamy a ak je nastavené vlastné pravidlo priraďovania, ktoré sa nikdy nebude zhodovať s týmito záznamami, potom sa tieto dva záznamy nezhodujú.

1. Po spustení procesu priraďovania sa zobrazia štatistiky deduplikácie.
   
> [!NOTE]
> Zadávanie pravidiel deduplikácie nie je povinné. Ak nie sú nakonfigurované žiadne takéto pravidlá, použijú sa systémovo definované pravidlá. Zbalia všetky záznamy, ktoré majú rovnakú kombináciu hodnôt (presná zhoda) z primárneho kľúča a polí v pravidlách párovania, do jedného záznamu, skôr než údaje entity prepošlú na účely priradenia medzi entitami, čím sa zvyšuje výkon a usporiadanosť systému.

## <a name="run-your-match-order"></a>Spustenie objednávky zosúladenia

Po definovaní pravidiel priraďovania vrátane pravidiel priradenia medzi entitami a pravidiel deduplikácie môžete spustiť poradie priraďovania. Na stránke **Zosúladenie** vyberte položku **Spustiť**, čím spustíte proces. Dokončenie príslušného algoritmu môže nejaký čas trvať. Vlastnosti na stránke **Zosúladenie** nie je možné zmeniť, kým sa nedokončí proces zosúladenia. Nájdete zjednotenú entitu profilu zákazníka, ktorá bola vytvorená na stránke **Entity**. Vaša zjednotená entita zákazníka sa nazýva **ConflationMatchPairs : CustomerInsights**.

Ak chcete vykonať ďalšie zmeny a zopakovať krok, môžete zrušiť prebiehajúce zosúladenie. Vyberte text **Obnovuje sa…** a vyberte **Zrušiť úlohu** v spodnej časti zobrazenej bočnej tably.

Po dokončení procesu porovnávania sa text **Obnovuje sa…** zmení na **Úspešné** a môžete znova využiť všetky funkcie stránky.

Výsledkom prvého zosúladenia je vytvorenie zjednotenej hlavnej entity. Všetky následné zosúlaďovania vedú k rozšíreniu tejto entity.

> [!TIP]
> Existuje [šesť druhov stavov](system.md#status-types) pre úlohy/procesy. Okrem toho väčšina procesov [závisí na ďalších nadväzujúcich procesoch](system.md#refresh-policies). Môžete si vybrať stav procesu a zobraziť podrobnosti o priebehu celej úlohy. Po výbere **Pozrieť detaily** pre jednu z úloh úlohy nájdete ďalšie informácie: čas spracovania, posledný dátum spracovania a všetky chyby a varovania spojené s úlohou.

## <a name="deduplication-output-as-an-entity"></a>Výstup deduplikácie ako entita
Okrem zjednotenej hlavnej entity vytvorenej ako súčasť krížového párovania entít, proces deduplikácie tiež generuje novú entitu pre každú entitu z poradia párovania na identifikáciu deduplikovaných záznamov. Tieto entity možno nájsť spolu s **ConflationMatchPairs:CustomerInsights** v sekcii **Systém** na stránke **Entity** s názvom **Deduplication_Datasource_Entity**.

Entita deduplikovaného výstupu obsahuje nasledujúce informácie:
- ID/kľúče
  - Pole primárneho kľúča a jeho alternatívne ID pole. Alternatívne ID pole obsahuje všetky alternatívne ID identifikované pre záznam.
  - Pole Deduplication_GroupId zobrazuje skupinu alebo klaster identifikovaný v rámci entity, ktorá zoskupuje všetky podobné záznamy na základe zadaných deduplikačných polí. Používa sa na účely spracovania systému. Ak nie sú zadané žiadne pravidlá manuálnej deduplikácie a uplatňujú sa pravidlá systému definované pre deduplikáciu, toto pole v entite výstupu deduplikácie nenájdete.
  - Deduplication_WinnerId: Toto pole obsahuje ID víťaza z identifikovaných skupín alebo klastrov. Ak je hodnota Deduplication_WinnerId rovnaká ako hodnota primárneho kľúča pre záznam, znamená to, že záznam je víťazným záznamom.
- Polia používané na definovanie pravidiel deduplikácie.
- Polia Pravidlo a Skóre označujú, ktoré z pravidiel deduplikácie sa použili a skóre vrátené algoritmom párovania.

## <a name="review-and-validate-your-matches"></a>Kontrola a potvrdenie zosúladených výsledkov

Vyhodnoťte kvalitu vašich zosúladených párov a zosúlaďte ich:

- Na stránke **Zosúladenie** nájdete dve dlaždice ukazujúce úvodné prehľady o vašich údajoch.

  - **Jedineční zákazníci**: zobrazuje počet jedinečných profilov, ktoré systém identifikoval.
  - **Zosúladené záznamy**: zobrazuje počet zosúladení vo všetkých zosúladených pároch.

- V tabuľke **Objednávka zosúladenia** môžete vyhodnotiť výsledky každého zosúladeného páru porovnaním počtu záznamov, ktoré boli dodané z tejto entity páru zosúladenia oproti percentu úspešne zosúladených záznamov.

- V sekcii **Pravidlá** entity v tabuľke poradie **Objednávka zosúladenia** nájdete percento úspešne zosúladených záznamov na úrovni pravidla. Výberom symbolu tabuľky vedľa pravidla môžete zobraziť všetky tieto záznamy na úrovni pravidiel. Odporúčame, aby ste skontrolovali podmnožinu záznamov a overili, či boli zosúladené správne.

- Experimentujte s odlišnými hodnotami presností vo vašich podmienkach, aby ste určili optimálnu hodnotu.

  1. Vyberte tri bodky (...) pre pravidlo páru zosúlaďovania, s ktorým chcete experimentovať, a vyberte položku **Upraviť**.

  2. Zvoľte podmienku, s ktorou chcete experimentovať. Každé kritérium je reprezentované jedným riadkom na table **Pravidlo zosúladenia**.

  3. Obsah stránky **Ukážka kritéria** závisí od úrovne presnosti, ktorú ste vybrali pre podmienku. Nájdite počet zosúladených a nezosúladených záznamov pre vybratú podmienku.

     Získajte bohatý prehľad o účinkoch rôznych prahových úrovní. Môžete porovnať, koľko záznamov bude zosúladených pod každou prahovou úrovňou, a zobraziť záznamy pod každou možnosťou. Vyberte každú z dlaždíc a skontrolujte údaje v sekcii tabuľky.

## <a name="optimize-your-matches"></a>Optimalizácia zosúladení

Zvýšte kvalitu tým, že prekonfigurujete niektoré z vašich parametrov zosúlaďovania:

- **Ak chcete objednávku zosúladenia**, vyberte **Upraviť** a zmeňte polia objednávky zosúladenia.

  > [!div class="mx-imgBorder"]
  > ![Úprava objednávky zosúladenia údajov](media/configure-data-match-order-edit.png "Úprava objednávky zosúladenia údajov")

- Ak ste definovali viacero pravidiel, **zmeňte poradie vašich pravidiel**. Pravidlá zosúlaďovania môžete preusporiadať tak, že vyberiete možnosť **Posunúť nahor** a **Posunúť nadol** v mriežke pravidiel zosúlaďovania.

  > [!div class="mx-imgBorder"]
  > ![Zmena poradia pravidla](media/configure-data-change-rule-order.png "Zmena poradia pravidla")

- **Duplikujte pravidlá**, ak ste definovali pravidlo zosúladenia a chceli by ste vytvoriť podobné pravidlo s úpravami. Tak urobíte výberom možnosti **Duplikovať**.

  > [!div class="mx-imgBorder"]
  > ![Duplikovanie pravidla](media/configure-data-duplicate-rule.png "Duplikovanie pravidla")

- **Deaktivovať pravidlo** na zachovanie pravidla párovania pri jeho vylúčení z procesu párovania.

  > [!div class="mx-imgBorder"]
  > ![Deaktivácia pravidla](media/configure-data-deactivate-rule.png "Deaktivácia pravidla")

- **Upravte pravidlá** výberom symbolu **Upraviť**. Môžete tiež použiť nasledujúce zmeny:

  - Zmena atribútov pre podmienku: Vyberte nové atribúty v riadku špecifickej podmienky.
  - Zmena prahovej hodnoty pre podmienku: Upravte jazdec presnosti.
  - Zmena metódy normalizácie podmienky: Aktualizujte metódu normalizácie.

## <a name="specify-your-custom-match-records"></a>Zadanie vlastných záznamov zosúlaďovania

Môžete určiť podmienky, aby sa niektoré záznamy zosúladili vždy alebo nikdy. Tieto pravidlá možno hromadne odovzdať do procesu zosúlaďovania.

1. Vyberte možnosť **Vlastné zosúladenie** na obrazovke **Objednávka zosúladenia**.

   > [!div class="mx-imgBorder"]
   > ![Vytvorenie vlastného zosúladenia](media/custom-match-create.png "Vytvorenie vlastného zosúladenia")

2. Ak nemáte žiadne nahrané entity, zobrazí sa nové dialógové okno **Vlastné zosúladenie**, v ktorom je potrebné vyplniť niektoré podrobnosti. Ak ste tieto podrobnosti zadali skôr, prejdite na krok 8.

   > [!div class="mx-imgBorder"]
   > ![Dialógové okno Nové vlastné zosúladenie](media/custom-match-new-dialog-box.png "Dialógové okno Nové vlastné zosúladenie")

3. Vyberte **Vyplniť šablónu**, ak chcete získať súbor šablóny, ktorý môže určovať, ktoré záznamy z ktorých entít sa majú vždy zosúladiť a ktoré sa nemajú zosúladiť nikdy. Budete musieť samostatne vyplniť záznamy „vždy zosúladiť“ a „nikdy nezosúladiť“ v dvoch rôznych súboroch.

4. Šablóna obsahuje polia na určenie hodnôt entity a primárneho kľúča entity, ktoré sa majú použiť pri vlastnom zosúlaďovaní. Ak napríklad chcete, aby sa váš primárny kľúč 12345 z entity Predaj vždy zosúladil s primárnym kľúčom 34567 z entity Kontakt, musíte zadať nasledovné:
    - Entity1: Predaj
    - Entity1Key: 12345
    - Entity2: Kontakt
    - Entity2Key: 34567

   Rovnaký súbor šablóny môže určiť vlastné záznamy zosúlaďovania z viacerých entít.
   
   Ak chcete určiť vlastné párovanie pre deduplikáciu entity, zadajte rovnakú entitu pre Entitu1 aj Entitu2 a nastavte rôzne hodnoty primárneho kľúča.

5. Po pridaní všetkých úprav, ktoré chcete použiť, uložte súbor šablóny.

6. Prejdite na **Údaje** > **Zdroje údajov** a prijmite súbory šablón ako nové entity. Po príprave ich môžete použiť na určenie konfigurácie zosúladenia.

7. Po nahratí súborov a entít k dispozícii, vyberte znova možnosť **Vlastné zosúladenie**. Zobrazia sa možnosti na určenie entít, ktoré chcete zahrnúť. Z rozbaľovacej ponuky vyberte požadované entity.

   > [!div class="mx-imgBorder"]
   > ![Vlastné prepísanie zosúladenia](media/custom-match-overrides.png "Vlastné prepísanie zosúladenia")

8. Vyberte entity, ktoré chcete použiť pre **Vždy zosúladiť** a **Nikdy nezosúladiť**, a vyberte **Hotovo**.

9. Vyberte **Uložiť** na stránke **Zosúladiť** pre konfiguráciu vlastného zosúladenia, ktorú ste práve nastavili.

10. Vyberte **Spustiť** na stránke **Zosúladiť** a začnite s procesom zosúladenia. Použije sa vlastné konfigurácia zosúlaďovania. Všetky systémové pravidlá zosúlaďovania sa prepíšu nakonfigurovanou množinou.

11. Po dokončení zosúladenia môžete overiť entitu **ConflationMatchPair**, aby sa potvrdilo, že prepísania sa použili pri zosúlaďovaní.

## <a name="next-step"></a>Nasledujúci krok

Po dokončení procesu zosúladenia pre aspoň jeden pár zosúladenia môžete vyriešiť možné rozpory vo svojich údajoch podľa témy [**Zosúladenie**](merge-entities.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]