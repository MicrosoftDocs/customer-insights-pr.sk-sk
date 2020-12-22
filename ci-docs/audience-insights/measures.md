---
title: Vytváranie a úprava mier
description: Definovanie mier týkajúcich sa zákazníkov s cieľom analyzovať a odrážať výkonnosť určitých oblastí podnikania.
ms.date: 10/15/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: wameng
manager: shellyha
ms.openlocfilehash: 0e214a6eb66abd27f7292db3ce2c2a6e16a8ff33
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406933"
---
# <a name="define-and-manage-measures"></a>Definovanie a spravovanie mier

**Miery** predstavujú kľúčové ukazovatele výkonu (KPI), ktoré odrážajú výkonnosť a zdravie konkrétnych oblastí podnikania. Prehľady cieľových skupín poskytujú intuitívne prostredie na vytváranie rôznych typov mier pomocou nástroja na tvorbu dotazov, ktorý nevyžaduje, aby ste svoje opatrenia programovali alebo overovali ručne. Môžete sledovať svoje obchodné miery na stránke **Domov**, sledovať miery pre konkrétnych zákazníkov na **Karte zákazníka** a používať miery na definovanie segmentov zákazníka na stránke **Segmenty**.

## <a name="create-a-measure"></a>Vytvorenie miery

Táto časť vás prevedie vytvorením miery od nuly. Miery môžete vytvárať s údajmi z viacerých zdrojov údajov, ktoré sú pripojené prostredníctvom entity Zákazník. Platia niektoré [obmedzenia služby](service-limits.md).

1. V prehľadoch cieľových skupín prejdite na **Miery**.

2. Vyberte **Nová miera**.

3. Vyberte mieru **Typ**:

   - **Atribút zákazníka**: Jedno pole na zákazníka, ktoré odráža skóre, hodnotu alebo stav pre zákazníka. Atribúty zákazníka sa vytvárajú ako atribúty v novej systémovo generovanej entite s názvom **Miera zákazníka**.

   - **Miera zákazníka**: Informácie o správaní sa zákazníka s rozpisom podľa vybraných dimenzií. Pre každú mieru sa vytvorí nová entita, potenciálne s viacerými záznamami na zákazníka.

   - **Obchodná miera**: Sleduje výkonnosť vašej firmy a jej zdravie. Obchodné miery môžu mať dva rôzne výstupy: číselný výstup, ktorý sa zobrazuje na stránke **Domov** alebo novú entitu, ktorú nájdete na stránke **Entity**.

4. Uveďte **Názov** a voliteľný **Zobrazovaný názov**, potom vyberte **Ďalej**.

5. V sekcii **Entity** vyberte prvú entitu z rozbaľovacieho zoznamu. V tomto okamihu by ste sa mali rozhodnúť, či sú potrebné ďalšie entity ako súčasť definície vašej miery.

   > [!div class="mx-imgBorder"]
   > ![Definícia miery](media/measure-definition.png "Definícia miery")

   Ak chcete pridať ďalšie entity, vyberte položku **Pridať entitu** a vyberte entity, ktoré chcete pre danú mieru použiť.

   > [!NOTE]
   > Môžete vybrať iba entity, ktoré majú vzťahy s východiskovou entitou. Ďalšie informácie o definovaní kľúčových vzťahov sa dozviete v časti [Vzťahy](relationships.md).

6. Voliteľne môžete nakonfigurovať premenné. V sekcii **Premenné** vyberte **Nová premenná**.

   Premenné sú výpočty, ktoré sa vykonávajú na každom z vašich vybratých záznamov. Napríklad sčítanie predajov v kamenných predajniach (POS) a online pre každý záznam vašich zákazníkov.

7. Zadajte parameter **Názov** pre premennú.

8. V oblasti **Vyjadrenie** vyberte pole, pri ktorom chcete začať s výpočtom.

9. Zadajte výraz do oblasti **Vyjadrenie** pri výbere ďalších polí, ktoré sa zahrnú do vášho výpočtu.

   > [!NOTE]
   > V súčasnosti sú podporované iba aritmetické výrazy. Výpočet premenných navyše nie je podporovaný pre entity z rôznych [ciest entít](relationships.md).

10. Vyberte **Hotovo**.

11. V sekcii **Definícia entity** definujete, ako sa budú vybrané entity a vypočítané premenné agregovať do novej entity alebo atribútu miery.

12. Vyberte **Nový rozmer**. Rozmer si môžete predstaviť ako funkciu *zoskupiť podľa*. Výstup údajov vašej entity alebo atribútu miery bude zoskupený podľa všetkých vašich definovaných rozmerov.

    > [!div class="mx-imgBorder"]
    > ![Vyberte agregovaný cyklus](media/measures-businessreport-measure-definition2.png "Vyberte agregovaný cyklus")

    Vyberte alebo zadajte nasledujúce informácie ako súčasť definície vašej dimenzie:

    - **Entita**: Ak definujete entitu Miera, mala by obsahovať aspoň jeden atribút. Ak definujete atribút Miera, bude štandardne obsahovať iba jeden atribút. Tento výber sa týka výberu entity, ktorá tento atribút obsahuje.
    - **Pole**: Vyberte konkrétny atribút, ktorý sa má zahrnúť do entity alebo atribútu Miera.
    - **Kontajner**: Vyberte, či chcete agregovať údaje denne, mesačne alebo ročne. Je to povinný výber, iba ak ste vybrali atribút typu dátumu.
    - **Ako**: Definuje názov nového poľa.
    - **Zobrazovaný názov**: Definuje zobrazovaný názov poľa.

    > [!NOTE]
    > Vaša obchodná miera sa uloží ako entita s jediným číslom a objaví sa na stránke **Domov**, pokiaľ do merania nepridáte ďalšie dimenzie. Po pridaní ďalších dimenzií sa miera *nebude* zobrazovať na stránke **Domov**.

13. Voliteľne pridajte agregačné funkcie. Akákoľvek agregácia, ktorú vytvoríte, má za následok novú hodnotu v rámci vašej entity alebo atribútu Miery. Podporované agregačné funkcie sú: **Min**, **Max**, **Priemern**, **Medián**, **Súčet**, **Počet jedinečný**, **Prvý** (vezme prvý záznam hodnoty rozmeru) a **Posledný** (vezme posledný záznam pridaný do hodnoty rozmeru).

14. Výberom možnosti **Uložiť** použijete zmeny miery.

## <a name="manage-your-measures"></a>Spravovanie mier

Po vytvorení aspoň jednej miery sa zobrazí zoznam mier na stránke **Miery**.

Nájdete tu informácie o type miery, tvorcovi, dátume a čase vytvorenia, poslednom dátume a čase úpravy, stave (či je miera aktívna, neaktívna alebo neúspešná) a poslednom dátume a čase obnovenia. Keď vyberiete mieru zo zoznamu, zobrazí sa ukážka jej výstupu.

Ak chcete obnoviť všetky svoje miery naraz, vyberte položku **Obnoviť všetko** bez výberu konkrétnej miery.

> [!div class="mx-imgBorder"]
> ![Akcie na spravovanie jednotlivých mier](media/measure-actions.png "Akcie na spravovanie jednotlivých mier")

Prípadne vyberte mieru zo zoznamu a vykonajte jednu z nasledujúcich akcií:

- Kliknutím na názov miery zobrazíte podrobnosti.
- **Upravte** konfiguráciu miery.
- **Premenujte** mieru.
- **Odstráňte** mieru.
- Vyberte tri bodky (…) a potom **Obnoviť** na spustenie procesu obnovenia miery.
- Vyberte tri bodky (…) a potom **Stiahnuť** na získanie súboru .CSV miery.

> [!TIP]
> Existuje [šesť druhov stavov](system.md#status-types) pre úlohy/procesy. Okrem toho väčšina procesov [závisí na ďalších nadväzujúcich procesoch](system.md#refresh-policies). Môžete si vybrať stav procesu a zobraziť podrobnosti o priebehu celej úlohy. Po výbere **Pozrieť detaily** pre jednu z úloh úlohy nájdete ďalšie informácie: čas spracovania, posledný dátum spracovania a všetky chyby a varovania spojené s úlohou.

## <a name="next-step"></a>Nasledujúci krok

Existujúce miery môžete využiť na vytvorenie svojho prvého segmentu zákazníkov na stránke **Segmenty**. Ďalšie informácie nájdete v časti [Segmenty](segments.md).
