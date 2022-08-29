---
title: Pred zjednotením údajov odstráňte duplikáty
description: Druhým krokom v procese zjednotenia je výber záznamu, ktorý sa má ponechať, keď sa nájdu duplikáty.
recommendations: false
ms.date: 08/01/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: v-wendysmith
ms.author: sstabbert
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-map
- ci-match
- customerInsights
ms.openlocfilehash: 3f84c1c149f0befcbe489ccdd8a666ce6d5d798a
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304492"
---
# <a name="remove-duplicates-before-unifying-data"></a>Pred zjednotením údajov odstráňte duplikáty

Tento voliteľný krok zjednotenia vám umožňuje nastaviť pravidlá na odstránenie duplicitných záznamov **v rámci** entita. Deduplikácia identifikuje viacero záznamov pre zákazníka a vyberie najlepší záznam na uchovanie (na základe základných preferencií zlučovania) alebo zlúči záznamy do jedného (na základe pokročilých preferencií zlučovania). Zdrojové záznamy sa prepoja so zlúčeným záznamom s alternatívnymi ID. Ak pravidlá nie sú nakonfigurované, použijú sa pravidlá definované systémom.

## <a name="default-deduplication"></a>Predvolená deduplikácia

Ak nie sú pridané žiadne pravidlá deduplikácie, použijú sa systémom definované pravidlá.

- Primárny kľúč je deduplikovaný.
  Pre všetky záznamy s rovnakým primárnym kľúčom, **Najviac naplnené** rekord (ten s najmenším počtom nulových hodnôt) je víťaz.
- Na entitu sa aplikujú všetky pravidlá párovania medzi entitami.
  Napríklad: V kroku zhody, ak je entita A priradená k entite B zapnutá *Celé meno* a *Dátum narodenia*, potom je entita A tiež deduplikovaná podľa *Celé meno* a *Dátum narodenia*. Pretože *Celé meno* a *Dátum narodenia* sú platné kľúče na identifikáciu zákazníka v účtovnej jednotke A, tieto kľúče sú platné aj na identifikáciu duplicitných zákazníkov v účtovnej jednotke A.

## <a name="include-enriched-entities-preview"></a>Zahrnúť obohatené entity (ukážka)

Ak ste obohatili entity na úrovni zdroj údajov, aby ste pomohli zlepšiť výsledky zjednotenia, vyberte ich. Viac informácií nájdete v časti [Obohatenie pre zdroje údajov](data-sources-enrichment.md).

1. Na **Duplicitné záznamy** stránku, vyberte **Použite obohatené entity** v hornej časti stránky.

1. Z **Použite obohatené entity** vyberte jednu alebo viac obohatených entít.

1. Vyberte položku **Hotovo**.

## <a name="define-deduplication-rules"></a>Definujte pravidlá deduplikácie

1. Na **Duplicitné záznamy** vyberte entitu a vyberte **Pridať pravidlo** na definovanie pravidiel deduplikácie.

   :::image type="content" source="media/m3_duplicates_showmore.png" alt-text="Snímka obrazovky stránky Duplicitné záznamy so zvýraznenou entitou a zobrazeným pravidlom Pridať"  lightbox="media/m3_duplicates_showmore.png":::

   1. V **Pridať pravidlo** panel, zadajte nasledujúce informácie:
      - **Vyberte pole** : Vyberte si zo zoznamu dostupných polí entity, v ktorej chcete skontrolovať duplikáty. Vyberte polia, ktoré sú pravdepodobne jedinečné pre každého zákazníka. Napríklad e-mailová adresa alebo kombinácia mena, mesta a telefónneho čísla.
      - **Normalizovať**: Vyberte si z nasledujúcich možností normalizácie pre vybrané atribúty.
        - **Číslice** : Prevedie iné číselné sústavy, napríklad rímske číslice, na arabské číslice. *VIII* sa stane *8*.
        - **Symboly** : Odstráni všetky symboly a špeciálne znaky. *Head&Shoulder* sa stáva *HeadShoulder*.
        - **Text na malé písmená: Skonvertuje všetky znaky na malé písmená**. *VŠETKY PÍSMENÁ VEĽKÉ a Nadpis* sa stáva *všetky písmená veľké a nadpis*.
        - **Typ (telefón, meno, adresa, organizácia)** : Štandardizuje mená, tituly, telefónne čísla, adresy atď.
        - **Unicode na ASCII** : Konvertuje notáciu Unicode na znaky ASCII. */u00B2* sa stáva *2*.
        - **Biely vesmír** : Odstráni všetky medzery. *Ahoj svet* sa stáva *HelloWorld*.
      - **Presnosť**: Nastavte úroveň presnosti, ktorá sa má použiť pre túto podmienku.
        - **Základné** : Vyber z *Nízka (30 %)*, *(60 %)*, *(80 %)*, a *Presne (100 %)*. Vyberte **Presne** aby sa zhodovali iba záznamy, ktoré sa stopercentne zhodujú.
        - **Vlastné**: Nastavte percento, ktorému sa musia záznamy zhodovať. Systém bude porovnávať iba záznamy prekračujúce tento limit.
      - **názov** : Názov pravidla.

      :::image type="content" source="media/m3_duplicates_add.png" alt-text="Snímka obrazovky panela Pridať pravidlo na odstránenie duplikátov.":::

   1. Voliteľne vyberte **Pridať** > **Pridať podmienku** pridať ďalšie podmienky do pravidla. Podmienky sú spojené s logickým operátorom AND a tak sa vykonávajú iba vtedy, ak sú splnené všetky podmienky.

   1. voliteľne **Pridať** > **Pridať výnimku** do [pridať výnimky z pravidla](match-entities.md#add-exceptions-to-a-rule). Výnimky sa používajú na riešenie zriedkavých prípadov falošne pozitívnych a falošne negatívnych výsledkov.

   1. Vyberte **hotový** na vytvorenie pravidla.

1. Voliteľne stlačte možnosť [pridať ďalšie pravidlá](#define-deduplication-rules).

1. Vyberte entitu a potom **Upravte predvoľby zlúčenia**.

1. V **Zlúčiť predvoľby** tabuľka:
   1. Vyberte jednu z troch možností na určenie, ktorý záznam sa má ponechať, ak sa nájde duplikát:
      - **Najviac vyplnené**: Identifikuje záznam s najviac vyplnenými poľami atribútov ako víťazný záznam. Toto je predvolená možnosť zlučovania.
      - **Najnovšie**: Identifikuje víťazný záznam na základe najväčšej aktuálnosti. Na definovanie aktuálnosti sa vyžaduje dátum alebo číselné pole.
      - **Najstaršie**: Identifikuje víťazný záznam na základe najmenšej aktuálnosti. Na definovanie aktuálnosti sa vyžaduje dátum alebo číselné pole.

      V prípade nerozhodného výsledku je víťazným záznamom záznam s MAX(PK) alebo vyššou hodnotou primárneho kľúča.

   1. Voliteľne, ak chcete definovať preferencie zlúčenia pre jednotlivé atribúty entity, vyberte **Pokročilé** v spodnej časti tabule. Môžete sa napríklad rozhodnúť ponechať najnovší e-mail A najkompletnejšiu adresu z rôznych záznamov. Rozbaľte entitu, aby ste videli všetky jej atribúty a definujte, ktorá možnosť sa má použiť pre jednotlivé atribúty. Ak vyberiete možnosť založenú na aktuálnosti, musíte tiež zadať pole dátumu a času, ktoré definuje aktuálnosť.

      :::image type="content" source="media/m3_adv_merge.png" alt-text="Panel rozšírených predvolieb zlúčenia zobrazujúci posledný e-mail a úplnú adresu":::

   1. Vyberte **hotový** aplikujte svoje preferencie zlúčenia.

1. Po definovaní pravidiel deduplikácie a preferencií zlúčenia vyberte **Ďalšie**.
  
> [!div class="nextstepaction"]
> [Ďalší krok pre jednu entitu: Zjednotenie polí](merge-entities.md)

> [!div class="nextstepaction"]
> [Ďalší krok pre viaceré entity: Priraďovanie podmienok](match-entities.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]
