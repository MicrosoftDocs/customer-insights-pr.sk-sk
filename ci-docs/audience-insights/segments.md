---
title: Slúži na vytvorenie a spravovanie segmentov
description: Vytvorenie segmentov zákazníkov na ich zoskupenie na základe rôznych atribútov.
ms.date: 10/15/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: jimsonc
manager: shellyha
ms.openlocfilehash: 6931110c2ae93cd2792d319aa5a34f0df3088552
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406942"
---
# <a name="create-and-manage-segments"></a>Slúži na vytvorenie a spravovanie segmentov

Segmenty vám umožňujú zoskupiť zákazníkov na základe demografických, transakčných alebo behaviorálnych atribútov. Segmenty môžete použiť na zacielenie reklamných kampaní, predajných aktivít a akcií podpory zákazníkov na dosiahnutie vašich obchodných cieľov.

Okolo entity profilu zákazníka a jej príbuzných entít môžete definovať zložité filtre. Každý segment po spracovaní vytvorí skupinu zákazníckych záznamov, ktoré môžete exportovať a podniknúť kroky. Platia niektoré [obmedzenia služby](service-limits.md).

Pokiaľ nie je uvedené inak, všetky segmenty sú **dynamické segmenty**, ktoré sa obnovujú podľa opakujúceho sa plánu.

Nasledujúci príklad ilustruje možnosti segmentácie. Definovali sme segment pre zákazníkov, ktorí za posledných 90 dní objednali tovar aspoň za 500 USD *a* ktorí boli zapojení do hovoru služieb pre zákazníkov, ktorý bol eskalovaný.

> [!div class="mx-imgBorder"]
> ![Viac skupín](media/segmentation-group1-2.png "Viac skupín")

## <a name="create-a-new-segment"></a>Vytvorenie nového segmentu

Segmenty sú spravované na stránke **Segmenty**.

1. V prehľadoch cieľových skupín prejdite na stránku **Segmenty**.

2. Vyberte **Nový** > **Prázdny segment**.

3. Na table **Nový segment** vyberte typ segmentu a zadajte a **Názov**.

   Voliteľne uveďte zobrazovaný názov a popis, ktorý pomôže identifikovať segment.

4. Vyberte **Ďalšie** a prejdite na stránku **Tvorca segmentov**, kde definujete skupinu. Skupina je množina zákazníkov.

5. Vyberte entity, ktorá obsahuje atribút, podľa ktorého chcete segmentovať.

6. Vyberte atribút pre segment podľa. Tento atribút môže mať jeden zo štyroch typov hodnôt: číselný, reťazec, dátum alebo logický.

7. Vyberte operátora a hodnotu pre vybraného atribútu.

   > [!div class="mx-imgBorder"]
   > ![Filter vlastnej skupiny](media/customer-group-numbers.png "Filter skupiny zákazníkov")

   |Číslo |Definícia  |
   |---------|---------|
   |1     |Entity          |
   |2     |Atribút          |
   |3    |Operátor         |
   |4    |Hodnota         |

8. Ak je entita prepojená so zjednotenou entitou zákazníka prostredníctvom [vzťahov](relationships.md), musíte definovať cestu vzťahov, aby ste vytvorili platný segment. Pridajte entity z cesty vzťahov, kým si nevyberiete entitu **Zákazník: CustomerInsights** z rozbaľovacej ponuky. Potom vyberte **Všetky záznamy** pre každú podmienku.

   > [!div class="mx-imgBorder"]
   > ![Cesta vzťahov pri vytváraní segmentov](media/segments-multiple-relationships.png "Cesta vzťahov pri vytváraní segmentov")

9. Segment uložte výberom položky **Uložiť**. Váš segment bude uložený a spracovaný, ak budú splnené všetky požiadavky. V opačnom prípade sa uloží ako koncept.

10. Ak sa chcete vrátiť späť na stránku **Segmenty**, vyberte **Späť na segmenty**.

## <a name="manage-existing-segments"></a>Spravovanie existujúcich segmentov

Na stránke **Segmenty** môžete zobraziť všetky uložené segmenty a spravovať ich.

Každý segment je reprezentovaný radom, ktorý obsahuje ďalšie informácie o segmente.

Segmenty v stĺpci môžete zoradiť výberom záhlavia stĺpca.

Použite pole **Vyhľadávanie** v pravom hornom rohu na filtrovanie segmentov.

> [!div class="mx-imgBorder"]
> ![Možnosti správy existujúceho segmentu](media/segments-selected-segment.png "Možnosti správy existujúceho segmentu")

Po výbere segmentu sú k dispozícii nasledujúce akcie:

- **Zobrazenie** podrobností o segmente vrátane trendu počtu členov a ukážky členov segmentu.
- **Úprava** segmentu na zmenu jeho vlastností.
- **Obnova** segmentu, ktorý obsahuje najnovšie údaje.
- **Aktivácia** alebo **deaktivácia** segmentu. Segmenty majú dva možné stavy – aktívny alebo neaktívny. Tieto stavy sa hodia pri úprave segmentu. Pre neaktívne segmenty existuje definícia segmentu, zatiaľ však neobsahuje žiadnych zákazníkov. Keď aktivujete segment, jeho stav sa zmení z „neaktívneho“ na „aktívny“ a začne hľadať zákazníkov, ktorí zodpovedajú definícii segmentu. Ak je [plánované obnovenie](system.md#schedule-tab) nakonfigurované, neaktívne segmenty majú **Postavenie** uvedené ako **Preskočené**, čo naznačuje, že k obnoveniu ani nedošlo. Keď je neaktívny segment aktivovaný, obnoví sa a bude zahrnutý do plánovaných aktualizácií.
  Prípadne môžete použiť funkciu **Naplánovať neskôr** v rozbaľovacej ponuke **Aktivácia/Deaktivácia** na určenie budúceho dátumu a času aktivácie a deaktivácie konkrétneho segmentu.
- **Premenovanie** segmentu.
- **Stiahnutie** zoznam členov ako súbor .CSV.
- Možnosť **Pridať do** odošle zoznam ID zákazníkov v segmente na spracovanie v inej aplikácii.
- **Odstránenie** segmentu.

## <a name="refresh-segments"></a>Obnovenie segmentov

Výberom možnosti **Obnoviť všetko** na stránke **Segmenty** môžete obnoviť všetky segmenty naraz alebo môžete jeden alebo viac segmentov, keď ich vyberiete a následne vyberiete **Obnoviť** z možností. Prípadne môžete nakonfigurovať opakujúce sa obnovovanie v ponuke **Správca** > **Systém** > **Plán**.

> [!TIP]
> Existuje [šesť druhov stavov](system.md#status-types) pre úlohy/procesy. Okrem toho väčšina procesov [závisí na ďalších nadväzujúcich procesoch](system.md#refresh-policies). Môžete si vybrať stav procesu a zobraziť podrobnosti o priebehu celej úlohy. Po výbere **Pozrieť detaily** pre jednu z úloh úlohy nájdete ďalšie informácie: čas spracovania, posledný dátum spracovania a všetky chyby a varovania spojené s úlohou.

## <a name="download-and-export-segments"></a>Sťahovanie a exportovanie segmentov

Svoje segmenty si môžete stiahnuť do súboru CSV alebo ich exportovať do Dynamics 365 Sales.

### <a name="download-segments-to-a-csv-file"></a>Stiahnite segmenty do súboru CSV

1. V prehľadoch cieľových skupín prejdite na stránku **Segmenty**.

2. Vyberte tri bodky v dlaždici konkrétneho segmentu.

3. Vyberte **Stiahnuť ako CSV** z rozbaľovacieho zoznamu akcií.

### <a name="export-segments-to-dynamics-365-sales"></a>Export segmentov do Dynamics 365 Sales

Pred exportom segmentov do Dynamics 365 Sales musí správca [vytvoriť cieľ exportu](export-destinations.md) pre Dynamics 365 Sales.

1. V prehľadoch cieľových skupín prejdite na stránku **Segmenty**.

2. Vyberte tri bodky v dlaždici konkrétneho segmentu.

3. Vyberte **Pridať k** z rozbaľovacieho zoznamu akcií a vyberte cieľ exportu, do ktorého chcete dáta poslať.

## <a name="draft-mode-for-segments"></a>Režim konceptu pre segmenty

Ak nie sú splnené všetky požiadavky na spracovanie segmentu, môžete segment uložiť ako koncept a získať prístup k nemu zo stránky **Segmenty**.

Uloží sa ako neaktívny segment a nebude ho možné aktivovať, kým nebude platný.

## <a name="add-more-conditions-to-a-group"></a>Pridanie ďalších podmienok do skupiny

Na pridanie ďalších podmienok do skupiny môžete použiť dva logické operátory:

- Operátor **A**: Obe podmienky musia byť splnené ako súčasť procesu segmentácie. Táto voľba je najužitočnejšia, keď definujete podmienky pre rôzne entity.

- Operátor **ALEBO**: V rámci procesu segmentácie musí byť splnená jedna z podmienok. Táto voľba je najužitočnejšia, keď definujete viac podmienok pre jednu entitu.

   > [!div class="mx-imgBorder"]
   > ![Operátor ALEBO, ktorý musí splniť ktorúkoľvek z podmienok](media/segmentation-either-condition.png "Operátor ALEBO, ktorý musí splniť ktorúkoľvek z podmienok")

V súčasnosti je možné vnoriť operátor **ALEBO** pod operátor **A**, ale nie naopak.

## <a name="combine-multiple-groups"></a>Kombinácia viacerých skupín

Každá skupina produkuje špecifickú skupinu zákazníkov. Tieto skupiny môžete skombinovať tak, aby zahŕňali zákazníkov požadovaných pre váš obchodný prípad.

1. V prehľadoch cieľových skupín prejdite na stránku **Segmenty** a vyberte segment.

2. Vyberte **Pridať skupinu**.

   > [!div class="mx-imgBorder"]
   > ![Skupina zákazníkov – pridanie skupiny](media/customer-group-add-group.png "Skupina zákazníkov – pridanie skupiny")

3. Vyberte jednu z nasledujúcich množín operátorov: **Zjednotenie**, **Prienik** alebo **Okrem**.

   > [!div class="mx-imgBorder"]
   > ![Skupina zákazníkov – pridanie zjednotenia](media/customer-group-union.png "Skupina zákazníkov – pridanie zjednotenia")

   Vyberte operátora množín na definovanie novej skupiny. Uložením rôznych skupín určíte, ktoré údaje sa budú získavať:

   - **Zjednotenie** zjednocuje obe skupiny.

   - **Prienik** prekrýva obe skupiny. Iba údaje, ktoré *sú spoločné* pre obe skupiny, sa zachovávajú v zjednotenej skupine.

   - Možnosť **Okrem** kombinuje dve skupiny. Zachovajú sa iba údaje v skupine A, ktoré *nie sú spoločné* s údajmi v skupine B.

## <a name="view-processing-history-and-segment-members"></a>Zobrazenie histórie spracovania a členov segmentu

Ak chcete zobraziť konsolidované údaje o segmente, prečítajte si podrobnosti.

Na stránke **Segmenty** vyberte segment, ktorý chcete skontrolovať.

Horná časť stránky obsahuje graf trendov, ktorý vizualizuje zmeny v počte členov. Ak umiestnite kurzor myši nad údajové body, zobrazí sa počet členov k určitému dátumu.

Môžete aktualizovať časový rámec vizualizácie.

> [!div class="mx-imgBorder"]
> ![Časový rozsah segmentu](media/segment-time-range.png "Časový rozsah segmentu")

Spodná časť obsahuje zoznam členov segmentu.

> [!NOTE]
> Polia, ktoré sa nachádzajú v tomto zozname, sú založené na atribútoch entít vášho segmentu.
>
>Zoznam predstavuje ukážku zodpovedajúcich členov segmentu a zobrazuje prvých 100 záznamov segmentu, aby ste ho mohli rýchlo vyhodnotiť a podľa potreby skontrolovať jeho definície. Ak chcete zobraziť všetky zodpovedajúce záznamy, musíte [exportovať segment](export-destinations.md).

## <a name="quick-segments"></a>Rýchle segmenty

Okrem nástroja na tvorbu segmentov existuje ešte jedna cesta k vytváraniu segmentov. Rýchle segmenty vám umožňujú rýchlo a vytvárať jednoduché segmenty s jediným operátorom s okamžitým prehľadom.

1. Na stránke **Segmenty** vyberte **Nový** > **Rýchlo vytvoriť z**.

   - Vyberte možnosť **Profily** na vytvorenie segmentu, ktorý je založený na jednotnej entite zákazníka.
   - Vyberte možnosť **Opatrenia** na vybudovanie segmentu okolo každého z opatrení typu Atribút zákazníka, ktoré ste predtým vytvorili na stránke **Opatrenia**.
   - Vyberte možnosť **Analýza** na zostavenie segmentu okolo jednej z výstupných entít, ktoré ste vygenerovali pomocou funkcií **Predpovede** alebo **Vlastné modely**.

2. V dialógovom okne **Nový rýchly segment** vyberte atribút z rozbaľovacej ponuky **Pole**.

3. Systém poskytne niektoré ďalšie informácie, ktoré vám pomôžu vytvoriť lepšie segmenty vašich zákazníkov.
   - Pre kategorické polia zobrazíme 10 najvyšších počtov zákazníkov. Vyberte **Hodnota** a potom **Skontrolovať**.

   - Pokiaľ ide o číselný atribút, systém ukáže, ktorá hodnota atribútu spadá pod percentil každého zákazníka. Vyberte **Operátor** a **Hodnota**, potom vyberte **Skontrolovať**.

4. Systém vám poskytne **Odhadovanú veľkosť segmentu**. Môžete si vybrať, či chcete vygenerovať segment, ktorý ste definovali, alebo ho znova opraviť, aby ste získali inú veľkosť segmentu.

    > [!div class="mx-imgBorder"]
    > ![Názov a odhad rýchleho segmentu](media/quick-segment-name.png "Názov a odhad rýchleho segmentu")

5. Zadajte **Názov** pre svoj segment. Voliteľne zadajte **Zobrazovaný názov**.

6. Výberom položky **Uložiť** vytvorte segment.

7. Po dokončení spracovania môžete segment zobraziť ako akýkoľvek iný segment, ktorý ste vytvorili.

Pre nasledujúce scenáre odporúčame radšej použiť nástroj na tvorbu segmentov než odporúčané možnosti segmentov:

- Vytváranie segmentov s filtrami v kategorických poliach, v ktorých je operátor iný ako **Je**
- Vytváranie segmentov s filtrami v číselných poliach, v ktorých je operátor iný ako **Medzi**, **Väčší než** a **Menší než**
- Vytváranie segmentov s filtrami v poliach typu dátumu

## <a name="next-steps"></a>Ďalšie kroky

[Exportujte segment](export-destinations.md) a preskúmajte [kartu zákazníka](customer-card-add-in.md) a [konektory](export-power-bi.md), aby ste získali prehľad o úrovni zákazníka.
