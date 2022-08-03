---
title: Dodržujte podmienky zjednotenia údajov
description: Priraďujte entity na účely vytvorenia jednotných profilov zákazníkov.
recommendations: false
ms.date: 05/05/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: v-wendysmith
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-match
- ci-merge
- ci-map
- customerInsights
ms.openlocfilehash: e3e4e37d5b4c9caf2520a789d5f78ef33b491793
ms.sourcegitcommit: 3c5b0b40b2b45e420015bbdd228ce0e610245e6f
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 07/12/2022
ms.locfileid: "9139722"
---
# <a name="match-conditions-for-data-unification"></a>Dodržujte podmienky zjednotenia údajov

Tento krok zjednotenia definuje poradie zhody a pravidlá pre zhodu medzi entitami. Tento krok vyžaduje aspoň dve entity.

> [!NOTE]
> Po vytvorení podmienok zhody a výbere **Ďalšie**, nemôžete odstrániť vybratú entitu alebo atribút. V prípade potreby vyberte **späť** pred pokračovaním skontrolujte vybrané entity a atribúty.

## <a name="include-enriched-entities-preview"></a>Zahrnúť obohatené entity (ukážka)

Ak ste obohatili entity na úrovni zdroj údajov, aby ste pomohli zlepšiť výsledky zjednotenia, vyberte ich. Viac informácií nájdete v časti [Obohatenie pre zdroje údajov](data-sources-enrichment.md). Ak ste vybrali obohatené entity na **Duplicitné záznamy** stránku, nemusíte ich znova vyberať.

1. Na **Zodpovedajúce podmienky** stránku, vyberte **Použite obohatené entity** v hornej časti stránky.

1. Z **Použite obohatené entity** vyberte jednu alebo viac obohatených entít.

1. Vyberte položku **Hotovo**.

## <a name="specify-the-match-order"></a>Určenie objednávky zosúladenia

Každá zhoda zjednocuje dve alebo viac entít do jednej konsolidovanej entity. Zároveň vedie jedinečné záznamy o zákazníkoch. Poradie zhody označuje poradie, v ktorom sa systém pokúša zladiť záznamy.

> [!IMPORTANT]
> Prvá entita v zozname sa nazýva primárna entita. Primárna entita slúži ako základ pre váš jednotný súbor údajov profilov. Do tejto entity sa pridajú ďalšie vybraté entity.
>
> Dôležité úvahy:
>
> - Ako primárny subjekt vyberte subjekt s najúplnejšími a najspoľahlivejšími profilovými údajmi o vašich zákazníkoch.
> - Vyberte entitu, ktorá má niekoľko spoločných atribútov s inými entitami (napríklad meno, telefónne číslo alebo e-mailovú adresu), ako primárnu entitu.

1. Na **Zodpovedajúce podmienky** pomocou šípok nahor a nadol presuňte entity v požadovanom poradí alebo ich presuňte myšou. Napríklad vyberte **Kontakty: elektronický obchod** ako primárny subjekt a **CustomerLoyalty:Lojalita** ako druhý subjekt.

1. Ak chcete mať každý záznam v entite ako jedinečného zákazníka bez ohľadu na to, či sa nájde zhoda, vyberte **Zahrňte všetky záznamy**. Všetky záznamy v tejto entite, ktoré sa nezhodujú so záznamami v iných entitách, sú zahrnuté v zjednotenom profile. Záznamy, ktoré nemajú zhodu, sa nazývajú singletony.
  
Primárna entita *Kontakty: elektronický obchod* sa zhoduje s ďalšou entitou *CustomerLoyalty:Lojalita*. Ak máte viac ako dve entity, množina údajov, ktorá je výsledkom prvého kroku zhody, sa zhoduje s nasledujúcou entitou.

:::image type="content" source="media/m3_match.png" alt-text="Snímka obrazovky vybratého poradia zhody pre entity." lightbox="media/m3_match.png":::

## <a name="define-rules-for-match-pairs"></a>Definujte pravidlá pre dvojice párov

Pravidlá zosúladenia určujú logiku, podľa ktorej budú zosúladené špecifické dvojice entít. Pravidlo pozostáva z jednej alebo viacerých podmienok.

Upozornenie vedľa názvu entity znamená, že pre pár zhody nie je definované žiadne pravidlo zhody.

1. Vyberte **Pridať pravidlo** pre pár entít na definovanie pravidiel zhody.

1. V **Pridať pravidlo** nakonfigurujte podmienky pre pravidlo.

   :::image type="content" source="media/m3_add_rule.png" alt-text="Snímka obrazovky panela Pridať pravidlo.":::

   - **Vyberte entitu/pole (prvý riadok)** : Vyberte súvisiacu entitu a atribút na určenie vlastnosti záznamu, ktorá je pravdepodobne jedinečná pre zákazníka. Napríklad telefónne číslo alebo e-mailová adresa. Vyvarujte sa zhody podľa atribútov typu aktivity. Napríklad ID nákupu pravdepodobne nenájde zhodu v iných typoch záznamov.

   - **Vyberte entitu/pole (druhý riadok)** : Vyberte atribút, ktorý súvisí s atribútom entity uvedenej v prvom riadku.

   - **Normalizovať**: Vyberte si z nasledujúcich možností normalizácie pre vybrané atribúty.
     - **Číslice** : Prevedie iné číselné sústavy, napríklad rímske číslice, na arabské číslice. *VIII* sa stane *8*.
     - **Symboly** : Odstráni všetky symboly a špeciálne znaky. *Head&Shoulder* sa stáva *HeadShoulder*.
     - **Text na malé písmená** : Skonvertuje všetky znaky na malé písmená. *VŠETKY PÍSMENÁ VEĽKÉ a Nadpis* sa stáva *všetky písmená veľké a nadpis*.
     - **Typ (telefón, meno, adresa, organizácia)** : Štandardizuje mená, tituly, telefónne čísla, adresy a organizácie.
     - **Unicode na ASCII** : Konvertuje notáciu Unicode na znaky ASCII. */u00B2* sa stáva *2*.
     - **Biely vesmír** : Odstráni všetky medzery. *Ahoj svet* sa stáva *HelloWorld*.

   - **Presnosť**: Nastavte úroveň presnosti, ktorá sa má použiť pre túto podmienku.
     - **Základné** : Vyber z *Nízka (30 %)*, *(60 %)*, *(80 %)*, a *Presne (100 %)*. Vyberte **Presne** aby sa zhodovali iba záznamy, ktoré sa stopercentne zhodujú.
     - **Vlastné**: Nastavte percento, ktorému sa musia záznamy zhodovať. Systém bude porovnávať iba záznamy prekračujúce tento limit.

   - **názov** : Názov pravidla.

1. Ak chcete priradiť entity iba vtedy, ak atribúty spĺňajú viaceré podmienky, vyberte **Pridať** > **Pridať podmienku** na pridanie ďalších podmienok k pravidlu zhody. Podmienky sú spojené s logickým operátorom AND a tak sa vykonávajú iba vtedy, ak sú splnené všetky podmienky.

1. Prípadne zvážte pokročilé možnosti ako napr [výnimky](#add-exceptions-to-a-rule) alebo [vlastné podmienky zhody](#specify-custom-match-conditions).

1. Vyberte **hotový** dokončiť pravidlo.

1. Voliteľne stlačte možnosť [pridať ďalšie pravidlá](#add-rules-to-a-match-pair).

1. Kliknite na tlačidlo **Ďalej**.

> [!div class="nextstepaction"]
> [Ďalší krok: Zjednotenie polí](merge-entities.md)

### <a name="add-rules-to-a-match-pair"></a>Pridajte pravidlá k páru

Pravidlá spárovania predstavujú súbory podmienok. Ak chcete priradiť entity podľa podmienok na základe viacerých atribútov, pridajte ďalšie pravidlá.

1. Vyberte **Pridať pravidlo** na entite, do ktorej chcete pridať pravidlá.

1. Postupujte podľa pokynov v časti [Definujte pravidlá pre dvojice párov](#define-rules-for-match-pairs).

> [!NOTE]
> Na poradí pravidiel záleží. Algoritmus priraďovania sa pokúša nájsť zhodu s daným záznamom zákazníka na základe vášho prvého pravidla a pokračuje k druhému pravidlu iba vtedy, ak neboli identifikované žiadne zhody s prvým pravidlom.

## <a name="advanced-options"></a>Rozšírené možnosti

### <a name="add-exceptions-to-a-rule"></a>Pridajte do pravidla výnimky

Vo väčšine prípadov zhoda entity vedie k jedinečným profilom zákazníkov s konsolidovanými údajmi. Ak chcete dynamicky riešiť zriedkavé prípady falošne pozitívnych a falošne negatívnych výsledkov, môžete definovať výnimky pre pravidlo zhody. Výnimky sa uplatňujú po spracovaní pravidiel zhody a vyhýbajú sa zhodovaniu všetkých záznamov, ktoré spĺňajú kritériá výnimky.

Napríklad, ak vaše pravidlo zhody kombinuje priezvisko, mesto a dátum narodenia, systém identifikuje dvojčatá s rovnakým priezvisko, ktoré žijú v rovnakom meste ako rovnaký profil. Môžete zadať výnimku, ktorá sa nezhoduje s profilmi, ak krstné meno v entitách, ktoré kombinujete, nie sú rovnaké.

1. V **Upraviť pravidlo** panel, vyberte **Pridať** > **Pridať výnimku**.

1. Zadajte kritériá výnimiek.

1. Ak chcete pravidlo uložiť, kliknite na položku **Hotovo**.

### <a name="specify-custom-match-conditions"></a>Zadajte vlastné podmienky spárovania

Môžete zadať podmienky, ktoré prepíšu predvolenú logiku zhody. K dispozícii sú štyri možnosti:

|Možnosť  |Description |Príklad  |
|---------|---------|---------|
|Vždy sa zhodovať     | Definuje hodnoty, ktoré sa vždy zhodujú.         |  Vždy sa zhodujú *Mike* a *MikeR*.       |
|Nikdy sa nezhodovať     | Definuje hodnoty, ktoré sa nikdy nezhodujú.        | Nikdy sa nezhodujú *John* a *Jonathan*.        |
|Vlastné obídenie     | Definuje hodnoty, ktoré by mal systém vždy ignorovať vo fáze zápasu. |  Ignorujte hodnoty *11111* a *Neznámy* počas zápasu.        |
|Mapovanie aliasu    | Definovanie hodnôt, ktoré by mal systém považovať za rovnakú hodnotu.         | Zvážte *Joe* byť rovný *Jozefa*.        |

1. Vyberte **Vlastné**.

   :::image type="content" source="media/m3_match_custom.png" alt-text="Vlastné tlačidlo":::

1. Vyber **Vlastný typ** a vyberte **Stiahnite si šablónu**. Pre každú možnosť zhody potrebujete samostatnú šablónu.

1. Otvorte stiahnutý súbor šablóny a vyplňte podrobnosti. Šablóna obsahuje polia na určenie hodnôt entity a primárneho kľúča entity, ktoré sa majú použiť pri vlastnom zosúlaďovaní. Napríklad ak chcete primárny kľúč *12345* od entity *Predaj*, aby sa vždy zhodoval s primárnym kľúčom *34567* od entity *Kontakt*, vyplňte šablónu:
    - Entity1: Predaj
    - Entity1Key: 12345
    - Entity2: Kontakt
    - Entity2Key: 34567

   Rovnaký súbor šablóny môže určiť vlastné záznamy zosúlaďovania z viacerých entít.

   Ak chcete určiť vlastné párovanie pre deduplikáciu entity, zadajte rovnakú entitu pre Entitu1 aj Entitu2 a nastavte rôzne hodnoty primárneho kľúča.

1. Po pridaní všetkých prepísaní uložte súbor šablóny.

1. Prejdite na **Údaje** > **Zdroje údajov** a prijmite súbory šablón ako nové entity.

1. Po nahratí súborov vyberte **Vlastné** možnosť znova. Z rozbaľovacej ponuky vyberte požadované entity a vyberte **Hotový**.

   :::image type="content" source="media/custom-match-overrides.png" alt-text="Snímka obrazovky dialógového okna na výber prepísania pre vlastný scenár zhody.":::

1. Použitie vlastnej zhody závisí od možnosti zhody, ktorú chcete použiť.

   - Pre **Vždy sa zhodujú** alebo **Nikdy sa nezhodujú**, prejdite na ďalší krok.
   - Pre **Obchvat** alebo **Mapovanie aliasu**, vyberte **Upraviť** na existujúce pravidlo zhody alebo vytvorte nové pravidlo. V rozbaľovacej ponuke Normalizácie vyberte možnosť **Vlastný bypass** alebo **Mapovanie aliasu** možnosť a vyberte **hotový**.

1. Vyberte **hotový** na **Vlastné** panel na použitie vlastnej konfigurácie zhody.

> [!div class="nextstepaction"]
> [Ďalší krok: Zjednotenie polí](merge-entities.md)

[!INCLUDE [footer-include](includes/footer-banner.md)]
