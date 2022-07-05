---
title: Vytvorenie segmentov
description: Vytvorte segmenty zákazníkov a zoskupte ich na základe rôznych atribútov pomocou nástroja na tvorbu segmentov alebo rýchlych segmentov.
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
ms.openlocfilehash: b99d9575d3b6af91758d80eb04170773b08cc9ab
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 06/29/2022
ms.locfileid: "9053991"
---
# <a name="create-segments"></a>Vytvorenie segmentov

Definujte komplexné filtre okolo zjednotenej entity zákazníka a jej súvisiacich entít. Každý segment po spracovaní vytvorí skupinu zákazníckych záznamov, ktoré môžete exportovať a podniknúť kroky. Segmenty sú spravované na stránke **Segmenty**. Môžete [vytvárať nové segmenty](#create-a-new-segment) s použitím zostavovača segmentov alebo [vytvárať rýchle segmenty](#quick-segments) z iných oblastí aplikácie.

> [!TIP]
> - Rýchle segmenty sú podporované iba v prostrediach pre **individuálnych zákazníkov**.
> - Segmenty založené na **individuálnych zákazníkoch** automaticky zahŕňajú dostupné kontaktné informácie pre členov segmentu. V prostrediach pre **firemné obchodné vzťahy** sú segmenty založené na obchodných vzťahoch (spoločnostiach alebo dcérskych spoločnostiach). Ak chcete zahrnúť kontaktné informácie do segmentu, použite funkciu **Atribúty projektu** v nástroji na tvorbu segmentov. Uistite sa, že zdroje kontaktných údajov sú [sémanticky mapované na entitu ContactProfile](semantic-mappings.md#define-a-contactprofile-semantic-entity-mapping).

## <a name="segment-builder"></a>Zostavovač segmentov

Nasledujúci obrázok ilustruje rôzne aspekty zostavovača segmentov. Zobrazí segment, ktorého výsledkom je skupina zákazníkov. Zákazníci si objednali tovar v konkrétnom časovom rámci a získali body za odmenu alebo minuli určité množstvo peňazí.

:::image type="content" source="media/segment-builder-overview.png" alt-text="Prvky zostavovača segmentov." lightbox="media/segment-builder-overview.png":::

1. Organizujte svoj segment pomocou pravidiel a čiastkových pravidiel. Každé pravidlo alebo čiastkové pravidlo pozostáva z podmienok. Skombinujte podmienky s logickými operátormi

1. Vyberte položku [postup vzťahu](relationships.md) medzi entitami, ktoré sa vzťahujú na pravidlo. Postup vzťahu určuje, ktoré atribúty je možné použiť v podmienke.

1. Spravujte pravidlá a čiastkové pravidlá. Zmeňte pozíciu pravidla alebo ho odstráňte.

1. Pridajte podmienky a vytvorte správnu úroveň vnorenia pomocou podradených pravidiel.

1. Aplikujte nastavené operácie na prepojené pravidlá.

1. Pomocou tably atribútov pridajte dostupné atribúty entity alebo vytvorte podmienky na základe atribútov. Tabla zobrazuje zoznam entít a atribútov na základe vybraného postupu vzťahu, ktoré sú k dispozícii pre vybraté pravidlo.

1. Pridajte podmienky na základe atribútov k existujúcim pravidlám a čiastkovým pravidlám alebo ich pridajte do nového pravidla.

1. Zrušenie a opätovné vykonanie zmien pri vytváraní segmentu.

Vyššie uvedený príklad ilustruje schopnosť segmentácie. Definovali sme segment pre zákazníkov, ktorí online kúpili tovar aspoň v hodnote 500 dolárov *a* majú záujem o vývoj softvéru.

## <a name="create-a-new-segment"></a>Vytvorenie nového segmentu

Existuje niekoľko spôsobov, ako vytvoriť nový segment. Táto časť popisuje, ako vytvoriť svoj vlastný segment úplne od začiatku. Môžete tiež vytvoriť *rýchly segment* na základe existujúcich entít alebo využite modely strojového učenia na získanie *navrhovaných segmentov*. Ďalšie informácie získate v [prehľade segmentov](segments.md).

Pri vytváraní segmentu môžete uložiť koncept. V štádiu konceptu je segment uložený ako neaktívny segment. Keď dokončíte konfiguráciu segmentu, spustením ho aktivujte. Môžete tiež **Aktivovať** segment zo stránky **Všetky segmenty**.

1. Prejdite na stránku **Segmenty**.

1. Vyberte položku **Nový** > **Vytvorte si vlastný**.

1. Na stránke tvorcu segmentov definujete alebo zostavujete pravidlá. Pravidlo pozostáva z jednej alebo viacerých podmienok, ktoré definujú skupinu zákazníkov.

1. V **Pravidlo 1** vyberte atribút subjektu, podľa ktorého chcete filtrovať zákazníkov. Existujú dva spôsoby výberu atribútov:
   - Pozrite si zoznam dostupných entít a atribútov na table **Pridať k pravidlu** a označte **+** ikonu vedľa atribútu, ktorý chcete pridať. Určte, či chcete atribút pridať k existujúcemu pravidlu, alebo ho použijete na vytvorenie nového pravidla.
   - Návrhy na zhodu zobrazíte zadaním názvu atribútu do sekcie pravidiel.

1. Vyberte operátory a určte príslušné hodnoty podmienky. Atribút môže mať ako hodnotu jeden zo štyroch dátových typov: číselný, reťazcový, dátumový alebo boolovský. Podľa typu údajov atribútu sú na určenie podmienky k dispozícii rôzne operátory. Pre segmenty s firemnými obchodnými vzťahmi sú k dispozícii dva špeciálne operátory na zahrnutie potenciálnych hierarchií medzi prijaté obchodné vzťahy. Použite operátory *podriadená položka k* a *nadradená položka k*, ak chcete zahrnúť súvisiace obchodné vzťahy.

1. Vybraním možnosti **Pridať podmienku** pridáte do pravidla ďalšie podmienky. Ak chcete vytvoriť pravidlo podľa aktuálneho pravidla, vyberte položku **Pridajte čiastkové pravidlo**.

1. Ak pravidlo používa iné entity než *Zákazník*, je potrebné nastaviť cestu vzťahu. Cesta vzťahu je potrebná na to, aby informovala systém, cez ktoré vzťahy majú pristupovať k zjednotenej entite zákazníka. Označte možnosť **Nastaviť cestu vzťahu** na mapovanie vybranej entity pre zjednotenú entitu zákazníka. Ak pre vzťah existuje iba jedna možná cesta, systém ju vyberie automaticky. Rôzne postupy vzťahov môžu priniesť rôzne výsledky. Každé pravidlo môže mať pre vzťah vlastnú cestu.

   :::image type="content" source="media/relationship-path.png" alt-text="Cesta potenciálneho vzťahu pri vytváraní pravidla na základe entity mapovanej na zjednotenú entitu zákazníka.":::

   Napríklad entita *eCommerce_eCommercePurchases* na snímkach obrazovky má pre mapovanie entity *Zákazník* štyri možnosti:
   - eCommerce_eCommercePurchases > eCommerce_eCommerceContacts > Zákazník
   - eCommerce_eCommercePurchases > Zákazník
   - eCommerce_eCommercePurchases > eCommerce_eCommerceContacts > POS_posPurchases > Zákazník
   - eCommerce_eCommercePurchases> eCommerce_eCommerceContacts> POS_posPurchases> loyaltyScheme_loyCustomers> Zákazník Pri výbere poslednej možnosti je možné do podmienok pravidla vložiť atribúty zo všetkých uvedených entít. Pravdepodobne získame menej výsledkov, pretože zodpovedajúce záznamy o zákazníkoch musia byť súčasťou všetkých entít. V tomto prípade si zakúpili tovar prostredníctvom elektronického obchodu (*eCommerce_eCommercePurchases*), v mieste predaja (*POS_posPurchases*) a zúčastňujú sa nášho vernostného programu (*loyaltyScheme_loyCustomers*). Pri výbere druhej možnosti môžeme vybrať iba atribúty z entity *eCommerce_eCommerce_eCommercePurchases* a *Zákazník*. Vo výsledku dostaneme pravdepodobne viac výsledných zákazníckych profilov.

1. Ak máte v pravidle viac podmienok, môžete si vybrať, aký logický operátor ich má spájať.  
   - **A** operátor: Na zaradenie záznamu do segmentu musia byť splnené všetky podmienky. Táto voľba je najužitočnejšia, keď definujete podmienky pre rôzne entity.
   - **ALEBO** operátor: Na zaradenie záznamu do segmentu musí byť splnená aspoň jedna podmienka. Táto voľba je najužitočnejšia, keď definujete viac podmienok pre jednu entitu.

   :::image type="content" source="media/segmentation-either-condition.png" alt-text="Pravidlo s dvomi podmienkami A.":::

   Ak použijete operátor ALEBO, je potrebné, aby byť všetky podmienky boli založené na entitách zahrnutých v ceste vzťahu.

   - Je možné vytvoriť viac pravidiel a vytvoriť tak rôzne súpravy záznamov o zákazníkoch. Skupiny môžete skombinovať tak, aby zahŕňali zákazníkov požadovaných pre váš obchodný prípad. Ak chcete vytvoriť nové pravidlo, vyberte možnosť **Pridať pravidlo**. Konkrétne, ak nemôžete zahrnúť entitu do pravidla z dôvodu zadanej cesty vzťahu, musíte vytvoriť nové pravidlo, aby ste z neho vybrali atribúty.

      :::image type="content" source="media/segment-rule-grouping.png" alt-text="Pridajte nové pravidlo do segmentu a vyberte nastavený operátor.":::

   - Vyberte jedného z nastavených operátorov: **Zjednotiť**, **Prienik** alebo **Okrem**.

      - **Zjednotenie** zjednocuje obe skupiny.
      - **Prienik** prekrýva obe skupiny. Iba údaje, ktoré *sú bežné* pre obe skupiny, zostávajú v zjednotenej skupine.
      - Možnosť **Okrem** kombinuje dve skupiny. Iba údaje v skupine A, ktoré *nie je bežné* pre údaje v skupine B, sa uchovajú.

1. Predvolene segmenty vytvoria výstupnú entitu, ktorá obsahuje všetky atribúty profilov zákazníkov zodpovedajúcich definovaným filtrom. Ak je segment založený na iných entitách ako entita *Zákazník*, môžete do výstupnej entity pridať ďalšie atribúty z týchto entít. Stlačte možnosť **Atribúty projektu** na výber atribútov, ktoré sa pripoja k výstupnej entite.

   > [!IMPORTANT]
   > V prípade segmentov založených na firemných obchodných vzťahoch je potrebné do segmentu zahrnúť podrobnosti o jednom alebo viacerých kontaktoch každého obchodného vzťahu z entity *ContactProfile*, aby bolo možné segment aktivovať alebo exportovať do destinácií, ktoré vyžadujú kontaktné informácie. Pre viac informácií o entite *ContactProfile* si prečítajte [Sémantické mapovania](semantic-mappings.md).
   > Vzorový výstup pre segment založený na obchodných vzťahoch s projektovanými atribútmi kontaktov by mohol vyzerať takto:
   >
   > |Identifikátor  |Názov obchodného vzťahu  |Výnos  |Meno kontaktu  | Rola kontaktu|
   > |---------|---------|---------|---------|---|
   > |10021     | Contoso | 100 tis. | [Abbie Moss, Ruth Soto]  | [CEO, manažér pre obstarávanie]

   :::image type="content" source="media/segments-project-attributes.png" alt-text="Príklad projektovaných atribútov vybratých na bočnej table, ktoré sa majú pridať do výstupnej entity.":::
  
   Napríklad: Segment je založený na entite, ktorá obsahuje údaje o nákupoch, ktoré súvisia s entitou *Zákazník*. Segment vyhľadá všetkých zákazníkov zo Španielska, ktorí v aktuálnom roku nakúpili tovar. Môžete sa rozhodnúť, či pripojíte atribúty ako cena tovaru alebo dátum nákupu ku všetkým príslušným záznamom zákazníkov vo výslednej entite. Tieto údaje môžu byť užitočné, ak chcete analyzovať sezónne korelácie s celkovými výdavkami.

   > [!NOTE]
   > - **Atribúty projektu** funguje iba pre entity, ktoré majú vzťah s entitou zákazníka jeden k mnohým. Napríklad jeden zákazník môže mať viac predplatných.
   > - Ak je atribút, ktorý chcete premietať, vzdialený viac ako jeden skok od entity *Zákazník*, ako je definované vzťahom, tento atribút by mal byť použitý v každom pravidle dotazu segmentu, ktorý vytvárate.
   > - Ak je atribút, ktorý chcete premietať, len na jeden skok od entity *Zákazník*, tento atribút nemusí byť prítomný v každom pravidle dotazu segmentu, ktorý vytvárate.
   > - **Premietané atribúty** sa zohľadňujú pri použití množinových operátorov.

1. Vyberte **Upraviť podrobnosti** vedľa segmentu bez názvu. Zadajte názov pre segment a aktualizujte navrhovaný **Názov výstupnej entity** pre daný segment. Voliteľne pridajte popis a [značky](work-with-tags-columns.md#manage-tags) do segmentu.

   :::image type="content" source="media/segments_edit_details.png" alt-text="Dialógové okno Upraviť podrobnosti.":::

1. Vyberte **Spustiť** na uloženie segmentu, aktivujte ho a začnite spracovávať svoj segment na základe všetkých pravidiel a podmienok. V opačnom prípade bude uložený ako neaktívny segment.

1. Ak sa chcete vrátiť späť na stránku **Segmenty**, vyberte **Späť na segmenty**.

1. V predvolenom nastavení je segment vytvorený ako dynamický segment. Znamená to, že segment sa obnovuje počas obnovovania systému. Ak chcete [zastaviť automatické obnovenie](segments.md#manage-existing-segments), vyberte segment a následne možnosť **Nastaviť ako statické**. Statické segmenty je možné [obnoviť manuálne](segments.md#refresh-segments) kedykoľvek.

> [!TIP]
> - Pri nastavovaní operátorov pre podmienky zostavovač segmentov nenavrhne platné hodnoty z entít. Môžete prejsť do časti **Údaje** > **Entity** a stiahnuť si údaje entity, aby ste zistili, ktoré hodnoty sú dostupné.
> - Podmienky založené na dátumoch vám umožnia prepínať sa medzi pevnými dátumami a pohyblivým rozsahom dátumov.
> - Ak máte pre svoj segment viacero pravidiel, pravidlo, ktoré upravujete, má vedľa seba zvislú modrú čiaru.
> - Pravidlá a podmienky môžete presunúť na iné miesta v definícii segmentu. Vyberte zvislú elipsu (&vellip;) vedľa pravidla alebo podmienky a vyberte, ako a kam ju presunúť.
> - Ovládacie prvky **Vrátiť späť** a **Znova** na paneli príkazov vám umožňujú vrátiť zmeny späť.
> - Po vytvorení segmentu vám to niektoré segmenty umožňujú [sledovať využitie segmentu](segments.md#track-usage-of-a-segment).

## <a name="quick-segments"></a>Rýchle segmenty

Rýchle segmenty vám umožňujú rýchlo vytvárať jednoduché segmenty pomocou jedného operátora a získať tak rýchlejší prehľad.

1. Na stránke **Segmenty** stlačte možnosť **Nový** > **Vytvoriť z**.
   - Vyberte možnosť **Profily** na vytvorenie segmentu, ktorý je založený na *zjednotenej entite zákazníka*.
   - Stlačte možnosť **Opatrenia** a vytvorte segment okolo opatrení, ktoré ste predtým vytvorili.
   - Vyberte možnosť **Analýza** na zostavenie segmentu okolo jednej z výstupných entít, ktoré ste vygenerovali pomocou funkcií **Predpovede** alebo **Vlastné modely**.

2. V dialógovom okne **Nový rýchly segment** vyberte atribút z rozbaľovacej ponuky **Pole**.

3. Systém poskytne viac pohľadov, ktoré vám pomôžu vytvoriť lepšie segmenty vašich zákazníkov.
   - Pre kategorické polia zobrazíme 10 najvyšších počtov zákazníkov. Vyberte **Hodnota** a potom **Skontrolovať**.
   - Pokiaľ ide o číselný atribút, systém ukáže, ktorá hodnota atribútu spadá pod percentil každého zákazníka. Vyberte **Operátor** a **Hodnota**, potom vyberte **Skontrolovať**.

4. Systém vám poskytne **Odhadovanú veľkosť segmentu**. Môžete si vybrať, či chcete vygenerovať segment, ktorý ste definovali, alebo ho znova opraviť, aby ste získali inú veľkosť segmentu.

   :::image type="content" source="media/quick-segment-name.png" alt-text="Názov a odhad rýchleho segmentu.":::

5. Poskytnúť **názov** a **Názov výstupnej entity** pre váš segment. Prípadne pridajte [značky](work-with-tags-columns.md#manage-tags).

6. Výberom položky **Uložiť** vytvorte segment.

7. Po dokončení spracovania môžete segment zobraziť ako akýkoľvek iný segment, ktorý ste vytvorili.

## <a name="next-steps"></a>Ďalšie kroky

[Exportujte segment](export-destinations.md) a preskúmajte časť [Integrácia karty zákazníka](customer-card-add-in.md) na používanie segmentov v iných aplikáciách.

[!INCLUDE [footer-include](includes/footer-banner.md)]
