---
title: Vytvárajte zložité segmenty pomocou nástroja na tvorbu segmentov
description: Pomocou nástroja na tvorbu segmentov vytvorte komplexné segmenty zákazníkov ich zoskupením na základe rôznych atribútov.
ms.date: 03/25/2022
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-segments
- ci-segment-builder
- ci-segment-details
- customerInsights
ms.openlocfilehash: cde373cd65e296675e1b3c92f3024e1093853842
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 07/18/2022
ms.locfileid: "9170654"
---
# <a name="create-complex-segments-with-segment-builder"></a>Vytvárajte zložité segmenty pomocou nástroja na tvorbu segmentov

Definujte komplexné filtre okolo zjednotenej entity zákazníka a jej súvisiacich entít. Každý segment po spracovaní vytvorí skupinu zákazníckych záznamov, ktoré môžete exportovať a podniknúť kroky.

> [!TIP]
> Segmenty založené na **individuálnych zákazníkoch** automaticky zahŕňajú dostupné kontaktné informácie pre členov segmentu. V prostrediach pre **firemné obchodné vzťahy** sú segmenty založené na obchodných vzťahoch (spoločnostiach alebo dcérskych spoločnostiach). Ak chcete zahrnúť kontaktné informácie do segmentu, použite funkciu **Atribúty projektu** v nástroji na tvorbu segmentov. Uistite sa, že zdroje kontaktných údajov sú [sémanticky mapované na entitu ContactProfile](semantic-mappings.md#define-a-contactprofile-semantic-entity-mapping).

## <a name="segment-builder"></a>Zostavovač segmentov

Nasledujúci obrázok ilustruje rôzne aspekty zostavovača segmentov. Zobrazí segment, ktorého výsledkom je skupina zákazníkov. Zákazníci si objednali tovar v konkrétnom časovom rámci a získali body za odmenu alebo minuli určité množstvo peňazí.

:::image type="content" source="media/segment-builder-overview.png" alt-text="Prvky zostavovača segmentov." lightbox="media/segment-builder-overview.png":::

1. Organizujte svoj segment pomocou pravidiel a čiastkových pravidiel. Každé pravidlo alebo čiastkové pravidlo pozostáva z podmienok. Skombinujte podmienky s logickými operátormi.

1. Vyberte položku [postup vzťahu](relationships.md) medzi entitami, ktoré sa vzťahujú na pravidlo. Postup vzťahu určuje, ktoré atribúty je možné použiť v podmienke.

1. Spravujte pravidlá a čiastkové pravidlá. Zmeňte pozíciu pravidla alebo ho odstráňte.

1. Pridajte podmienky a vytvorte správnu úroveň vnorenia pomocou podradených pravidiel.

1. Aplikujte nastavené operácie na prepojené pravidlá.

1. Pomocou tably atribútov pridajte dostupné atribúty entity alebo vytvorte podmienky na základe atribútov. Tabla zobrazuje zoznam entít a atribútov na základe vybraného postupu vzťahu, ktoré sú k dispozícii pre vybraté pravidlo.

1. Pridajte podmienky na základe atribútov k existujúcim pravidlám a čiastkovým pravidlám alebo ich pridajte do nového pravidla.

1. Zrušenie a opätovné vykonanie zmien pri vytváraní segmentu.

Vyššie uvedený príklad ilustruje schopnosť segmentácie. Definovali sme segment pre zákazníkov, ktorí online kúpili tovar aspoň v hodnote 500 dolárov *a* majú záujem o vývoj softvéru.

## <a name="create-a-new-segment-with-segment-builder"></a>Vytvorte nový segment pomocou nástroja na tvorbu segmentov

1. Prejdite na **Segmenty**.

1. Vyberte položku **Nový** > **Vytvorte si vlastný**. Na stránke tvorcu segmentov definujete alebo zostavujete pravidlá. Pravidlo pozostáva z jednej alebo viacerých podmienok, ktoré definujú skupinu zákazníkov.

1. Vyberte **Upraviť podrobnosti** vedľa segmentu bez názvu. Zadajte názov pre segment a aktualizujte navrhovaný **Názov výstupnej entity** pre daný segment. Voliteľne pridajte popis a [značky](work-with-tags-columns.md#manage-tags) do segmentu.

   :::image type="content" source="media/segments_edit_details.png" alt-text="Dialógové okno Upraviť podrobnosti.":::

1. V **Pravidlo 1** vyberte atribút subjektu, podľa ktorého chcete filtrovať zákazníkov. Existujú dva spôsoby výberu atribútov:
   - Pozrite si zoznam dostupných entít a atribútov na table **Pridať k pravidlu** a označte **+** ikonu vedľa atribútu, ktorý chcete pridať. Určte, či chcete atribút pridať k existujúcemu pravidlu, alebo ho použijete na vytvorenie nového pravidla.
   - Návrhy na zhodu zobrazíte zadaním názvu atribútu do sekcie pravidiel.

1. Vyberte operátory a určte príslušné hodnoty podmienky. Atribút môže mať ako hodnotu jeden zo štyroch dátových typov: číselný, reťazcový, dátumový alebo boolovský. Podľa typu údajov atribútu sú na určenie podmienky k dispozícii rôzne operátory. Pre segmenty s firemnými obchodnými vzťahmi sú k dispozícii dva špeciálne operátory na zahrnutie potenciálnych hierarchií medzi prijaté obchodné vzťahy. Použite operátory *podriadená položka k* a *nadradená položka k*, ak chcete zahrnúť súvisiace obchodné vzťahy.

1. Vybraním možnosti **Pridať podmienku** pridáte do pravidla ďalšie podmienky. Ak chcete vytvoriť pravidlo podľa aktuálneho pravidla, vyberte položku **Pridajte čiastkové pravidlo**.

1. Ak pravidlo používa iné entity ako *Zákazník* subjekt, vyberte **Nastavte cestu vzťahu** na mapovanie vybranej entity k jednotnej entite zákazníka. Ak existuje len jedna možná cesta vzťahu, systém ju vyberie automaticky. Rôzne [vzťahové cesty](relationships.md#relationship-paths) môže priniesť rôzne výsledky. Každé pravidlo môže mať pre vzťah vlastnú cestu.

   :::image type="content" source="media/relationship-path.png" alt-text="Cesta potenciálneho vzťahu pri vytváraní pravidla na základe entity mapovanej na zjednotenú entitu zákazníka.":::

1. Ak máte v pravidle viacero podmienok, vyberte, ktorý logický operátor ich spája.  
   - **A** operátor: Na zaradenie záznamu do segmentu musia byť splnené všetky podmienky. Túto možnosť použite, keď definujete podmienky pre rôzne entity.
   - **ALEBO** operátor: Na zaradenie záznamu do segmentu musí byť splnená aspoň jedna podmienka. Túto možnosť použite, keď definujete viacero podmienok pre rovnakú entitu.

   :::image type="content" source="media/segmentation-either-condition.png" alt-text="Pravidlo s dvomi podmienkami A.":::

   Ak použijete operátor ALEBO, je potrebné, aby byť všetky podmienky boli založené na entitách zahrnutých v ceste vzťahu.

1. Ak chcete vytvoriť rôzne sady záznamov zákazníkov, vytvorte viacero pravidiel. Ak chcete zahrnúť zákazníkov požadovaných pre váš obchodný prípad, skombinujte skupiny. Konkrétne, ak nemôžete zahrnúť entitu do pravidla z dôvodu zadanej cesty vzťahu, vytvorte nové pravidlo na výber atribútov z nej.

      :::image type="content" source="media/segment-rule-grouping.png" alt-text="Pridajte nové pravidlo do segmentu a vyberte nastavený operátor.":::

   1. Vyberte **Pridať pravidlo**.
   1. Vyberte jedného z nastavených operátorov: **Zjednotiť**, **Prienik** alebo **Okrem**.

      - **Zjednotenie** zjednocuje obe skupiny.
      - **Prienik** prekrýva obe skupiny. Iba údaje, ktoré *sú bežné* pre obe skupiny, zostávajú v zjednotenej skupine.
      - Možnosť **Okrem** kombinuje dve skupiny. Iba údaje v skupine A, ktoré *nie je bežné* pre údaje v skupine B, sa uchovajú.

1. Štandardne bude výstupná entita automaticky obsahovať všetky atribúty zákazníckych profilov, ktoré zodpovedajú definovaným filtrom. Ak je segment založený na iných entitách ako na *Zákazník* subjekt, vyberte **Atribúty projektu** pridať ďalšie atribúty z týchto entít do výstupnej entity.

   > [!IMPORTANT]
   > Pre segmenty založené na obchodných účtoch podrobnosti o jednom alebo viacerých kontaktoch každého účtu z *Kontaktný profil* entita musí byť zahrnutá do segmentu, aby bolo možné tento segment aktivovať alebo exportovať do destinácií, ktoré vyžadujú kontaktné informácie. Pre viac informácií o entite *ContactProfile* si prečítajte [Sémantické mapovania](semantic-mappings.md).
   > Vzorový výstup pre segment založený na obchodných vzťahoch s projektovanými atribútmi kontaktov by mohol vyzerať takto:
   >
   > |Identifikátor  |Názov obchodného vzťahu  |Výnos  |Meno kontaktu  | Rola kontaktu|
   > |---------|---------|---------|---------|---|
   > |10021     | Contoso | 100 tis. | [Abbie Moss, Ruth Soto]  | [CEO, manažér pre obstarávanie]

   :::image type="content" source="media/segments-project-attributes.png" alt-text="Príklad projektovaných atribútov vybratých na bočnej table, ktoré sa majú pridať do výstupnej entity.":::
  
   Napríklad: Segment je založený na entite, ktorá obsahuje údaje o nákupoch, ktoré súvisia s entitou *Zákazník*. Segment vyhľadá všetkých zákazníkov zo Španielska, ktorí v aktuálnom roku nakúpili tovar. Môžete sa rozhodnúť pripojiť atribúty ako cena tovaru alebo dátum nákupu ku všetkým zodpovedajúcim záznamom zákazníkov vo výstupnej entite. Tieto údaje môžu byť užitočné, ak chcete analyzovať sezónne korelácie s celkovými výdavkami.

   > [!NOTE]
   > - **Atribúty projektu** funguje iba pre entity, ktoré majú vzťah s entitou zákazníka jeden k mnohým. Napríklad jeden zákazník môže mať viac predplatných.
   > - Ak je atribút, ktorý chcete premietať, vzdialený viac ako jeden skok od entity *Zákazník*, ako je definované vzťahom, tento atribút by mal byť použitý v každom pravidle dotazu segmentu, ktorý vytvárate.
   > - Ak je atribút, ktorý chcete premietať, len na jeden skok od entity *Zákazník*, tento atribút nemusí byť prítomný v každom pravidle dotazu segmentu, ktorý vytvárate.
   > - **Premietané atribúty** sa zohľadňujú pri použití množinových operátorov.

1. Vyberte **Bežať** na vytvorenie segmentu. Vyberte **Uložiť** ak chcete zachovať aktuálnu konfiguráciu a spustiť segment neskôr. The **Segmenty** zobrazí stránka.

### <a name="segment-builder-tips"></a>Tipy na tvorbu segmentov

Pri vytváraní segmentu pomocou nástroja na tvorbu segmentov majte na pamäti nasledujúce tipy:

- Pri nastavovaní operátorov pre podmienky zostavovač segmentov nenavrhne platné hodnoty z entít. Môžete prejsť do časti **Údaje** > **Entity** a stiahnuť si údaje entity, aby ste zistili, ktoré hodnoty sú dostupné.
- Podmienky založené na dátumoch vám umožňujú prepínať medzi pevnými dátumami a pohyblivým rozsahom dátumov.
- Ak máte pre svoj segment viacero pravidiel, pravidlo, ktoré upravujete, má vedľa seba zvislú modrú čiaru.
- Pravidlá a podmienky môžete presunúť na iné miesta v definícii segmentu. Vyberte zvislú elipsu (&vellip;) vedľa pravidla alebo podmienky a vyberte, ako a kam ju presunúť.
- Ovládacie prvky **Vrátiť späť** a **Znova** na paneli príkazov vám umožňujú vrátiť zmeny späť.
- Po vytvorení segmentu vám to niektoré segmenty umožňujú [sledovať využitie segmentu](segments.md#track-usage-of-a-segment).

## <a name="next-steps"></a>Ďalšie kroky

[Exportujte segment](export-destinations.md) a preskúmajte časť [Integrácia karty zákazníka](customer-card-add-in.md) na používanie segmentov v iných aplikáciách.

[!INCLUDE [footer-include](includes/footer-banner.md)]
