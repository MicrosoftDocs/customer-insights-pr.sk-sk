---
title: Pred zjednotením údajov odstráňte duplikáty
description: Druhým krokom v procese zjednotenia je výber záznamu, ktorý sa má zachovať, keď sa nájdu duplikáty.
recommendations: false
ms.date: 04/22/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: v-wendysmith
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-map
- ci-match
- customerInsights
ms.openlocfilehash: 27dff3551ab411a12c273536d7431d651c48573e
ms.sourcegitcommit: 6a5f4312a2bb808c40830863f26620daf65b921d
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 05/11/2022
ms.locfileid: "8742980"
---
# <a name="remove-duplicates-before-unifying-data"></a>Pred zjednotením údajov odstráňte duplikáty

[!INCLUDE [m3-prod-trial-note](includes/m3-prod-trial-note.md)]

Tento krok zjednotenia vám voliteľne umožňuje nastaviť pravidlá pre zaobchádzanie s duplicitnými záznamami v rámci entity. *Deduplikácia* identifikuje duplicitné záznamy a zlúči ich do jedného záznamu. Zdrojové záznamy sa prepoja so zlúčeným záznamom s alternatívnymi ID. Ak pravidlá nie sú nakonfigurované, použijú sa pravidlá definované systémom.

## <a name="include-enriched-entities-preview"></a>Zahrnúť obohatené entity (ukážka)

Ak ste obohatili entity na úrovni zdroj údajov, aby ste pomohli zlepšiť výsledky zjednotenia, vyberte ich. Ďalšie informácie nájdete v časti [Obohatenie pre zdroje údajov](data-sources-enrichment.md).

1. Na **Duplicitné záznamy** stránku, vyberte **Použite obohatené entity** v hornej časti stránky.

1. Od **Použite obohatené entity** vyberte jednu alebo viacero obohatených entít.

1. Vyberte položku **Hotovo**.

## <a name="define-deduplication-rules"></a>Definujte pravidlá deduplikácie

1. Na **Duplicitné záznamy** vyberte entitu a vyberte **Pridať pravidlo** na definovanie pravidiel deduplikácie.

   :::image type="content" source="media/m3_duplicates_showmore.png" alt-text="Snímka obrazovky duplicitných záznamov so zvýraznenou možnosťou Zobraziť viac":::

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
        - **Základné** : Vyber z *Nízka (30 %)*, *(60 %)*, *(80 %)* a *Presne (100 %)*. Vyberte **Presne** aby sa zhodovali iba záznamy, ktoré sa stopercentne zhodujú.
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
      
      V prípade nerozhodného výsledku je víťazným záznamom ten, ktorý má MAX(PK) alebo vyššiu hodnotu primárneho kľúča.
      
   1. Voliteľne, ak chcete definovať preferencie zlúčenia pre jednotlivé atribúty entity, vyberte **Pokročilé** v spodnej časti tabule. Môžete sa napríklad rozhodnúť ponechať najnovší e-mail A najkompletnejšiu adresu z rôznych záznamov. Rozbaľte entitu, aby ste videli všetky jej atribúty a definujte, ktorá možnosť sa má použiť pre jednotlivé atribúty. Ak vyberiete možnosť založenú na aktuálnosti, musíte tiež zadať pole dátumu a času, ktoré definuje aktuálnosť.

      :::image type="content" source="media/m3_adv_merge.png" alt-text="Panel rozšírených predvolieb zlúčenia zobrazujúci posledný e-mail a úplnú adresu":::

   1. Vyberte **hotový** aplikujte svoje preferencie zlúčenia.

1. Po definovaní pravidiel deduplikácie a preferencií zlúčenia vyberte **Ďalšie**.
  
> [!div class="nextstepaction"]
> [Ďalší krok pre jednu entitu: Zjednotenie polí](merge-entities.md)

> [!div class="nextstepaction"]
> [Ďalší krok pre viaceré entity: Priraďovanie podmienok](match-entities.md)

## <a name="deduplication-output-as-an-entity"></a>Výstup deduplikácie ako entita

Proces deduplikácie vytvorí novú deduplikovanú entitu pre každú zo zdrojových entít. Tieto entity možno nájsť spolu s **ConflationMatchPairs:CustomerInsights** v sekcii **Systém** na stránke **Entity** s názvom **Deduplication_DataSource_Entity**.

Entita deduplikovaného výstupu obsahuje nasledujúce informácie:

- ID/kľúče
  - Polia Primárny kľúč a Alternatívne ID. Pole Alternatívne ID pozostáva zo všetkých alternatívnych ID identifikovaných pre záznam.
  - Pole Deduplication_GroupId zobrazuje skupinu alebo klaster identifikovaný v rámci entity, ktorá zoskupuje všetky podobné záznamy na základe zadaných deduplikačných polí. Používa sa na účely spracovania systému. Ak nie sú zadané žiadne pravidlá manuálnej deduplikácie a uplatňujú sa pravidlá systému definované pre deduplikáciu, toto pole v entite výstupu deduplikácie nenájdete.
  - Deduplication_WinnerId: Toto pole obsahuje ID víťaza z identifikovaných skupín alebo klastrov. Ak je hodnota Deduplication_WinnerId rovnaká ako hodnota primárneho kľúča pre záznam, znamená to, že záznam je víťazným záznamom.
- Polia používané na definovanie pravidiel deduplikácie.
- Polia Pravidlo a Skóre označujú, ktoré z pravidiel deduplikácie sa použili a skóre vrátené algoritmom párovania.

[!INCLUDE[footer-include](includes/footer-banner.md)]