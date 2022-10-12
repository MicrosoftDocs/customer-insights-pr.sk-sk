---
title: Predikcia odporúčaní produktov
description: Predikujte produkty, ktoré si zákazník pravdepodobne kúpi alebo ktoré bude chcieť použiť.
ms.date: 09/30/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: wmelewong
ms.author: wameng
manager: shellyha
ms.openlocfilehash: 0057d6796bb60db44d08b58d9e0daaf6e7c90fde
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610301"
---
# <a name="predict-product-recommendations"></a>Predikcia odporúčaní produktov

Model odporúčaní produktov vytvára súbory prediktívnych odporúčaní produktov. Odporúčania vychádzajú z predchádzajúceho nákupného správania a zákazníkov s podobnými vzormi nákupov. Tento model je určený pre individuálnych spotrebiteľov (B-to-C).

Musíte mať obchodné znalosti o rôznych typoch produktov pre vašu firmu a o tom, ako s nimi vaši zákazníci interagujú. Podporujeme odporúčanie produktov, ktoré už vaši zákazníci predtým kúpili, alebo odporúčania pre nové produkty.

Na odporúčania výrobkov sa môžu vzťahovať miestne zákony a nariadenia a očakávania zákazníkov, ktorých model nie je zostavený tak, aby zohľadňoval konkrétne požiadavky. preto **musíte si prečítať odporúčania skôr, ako ich doručíte svojim zákazníkom** aby ste sa uistili, že dodržiavate všetky príslušné zákony alebo nariadenia a očakávania zákazníkov týkajúce sa toho, čo môžete odporučiť.

Výstup tohto modelu poskytuje odporúčania na základe ID produktu. Váš mechanizmus doručovania musí namapovať predpokladané ID produktov k vhodnému obsahu pre vašich zákazníkov, aby zohľadnil lokalizáciu, obsah obrázkov a iný špecifický obchodný obsah alebo správanie.

> [!TIP]
> Vyskúšajte odporúčanie produktu predikcia pomocou vzorových údajov: [Odporúčanie produktu predikcia vzorová príručka](sample-guide-predict-product-recommendation.md).

## <a name="prerequisites"></a>Požiadavky

- Najmenej [Povolenia prispievateľa](permissions.md)
- Minimálne 100 zákazníkov, najlepšie viac ako 10 000 zákazníkov.
- Customer Identifier, jedinečný identifikátor na priradenie transakcií k jednotlivému zákazníkovi
- Najmenej jeden rok transakčných údajov, najlepšie dva až tri roky, aby sa do nich zahrnula určitá sezónnosť. V ideálnom prípade aspoň tri alebo viac transakcií na jedno ID zákazníka. História transakcií musí obsahovať:
  - **ID transakcie** : Jedinečný identifikátor nákupu alebo transakcie.
  - **Dátum transakcie** : Dátum nákupu alebo transakcie.
  - **Hodnota transakcie** : Číselná hodnota nákupu alebo transakcie.
  - **Jedinečné ID produktu** : ID zakúpeného produktu alebo služby, ak sú vaše údaje na úrovni riadkovej položky.
  - **Nákup alebo vrátenie** : Logická hodnota true/false kde *pravda* identifikuje, že transakcia bola vrátená. Ak údaje o nákupe alebo vrátení nie sú uvedené v modeli a **Hodnota transakcie** je záporná, odvodzujeme návratnosť.
- Entita údajov katalógu produktov, ktorá sa má použiť ako filter produktov.

> [!NOTE]
> - Model vyžaduje históriu transakcií vašich zákazníkov, pričom transakciou sú akékoľvek údaje, ktoré popisujú interakciu používateľa s produktom. Napríklad nákup produktu, absolvovanie kurzu alebo účasť na udalosti.
> - Je možné nakonfigurovať iba jednu entitu histórie transakcií. Ak existuje viacero nákupných entít, skombinujte ich Power Query pred prijímaním údajov.
> - Ak sú objednávka a podrobnosti objednávky odlišné entity, pred použitím v modeli ich spojte. Model v entite nefunguje iba s ID objednávky alebo príjmovým dokladom.

## <a name="create-a-product-recommendation-prediction"></a>Vytvorenie predikcie odporúčania produktu

Vyberte **Uložiť koncept** kedykoľvek uložiť predikcia ako koncept. Koncept predikcia sa zobrazí v **Moje predpovede** tab.

1. Ísť do **Inteligencia** > **Predpovede**.

1. Na **Vytvorte** kartu, vyberte **Použite model** na **Odporúčania produktov (ukážka)** dlaždica.

1. Vyberte **Začíname**.

1. **Pomenujte tento model** a **Názov výstupnej entity**, aby ste ich odlíšili od iných modelov alebo entít.

1. Vyberte **Ďalej**.

### <a name="define-product-recommendation-preferences"></a>Definujte preferencie odporúčaní produktov

1. Nastaviť **Počet produktov** odporučiť zákazníkovi. Táto hodnota závisí od toho, ako váš spôsob doručenia vyplní údaje.

1. Vyberte, či chcete zahrnúť produkty, ktoré si zákazníci v minulosti zakúpili **Očakávajú sa opakované nákupy** lúka.

1. Nastaviť **Pohľad dozadu okno** s časovým rámcom, ktorý model zvažuje pred opätovným odporúčaním produktu používateľovi. Napríklad uveďte, že zákazník si kúpi notebook každé dva roky. Model sa pozrie na históriu nákupov za posledné dva roky a ak nájde položku, položka sa odfiltruje z odporúčaní.

1. Vyberte **Ďalej**

### <a name="add-purchase-history"></a>Pridanie histórie nákupov

1. Vyberte **Pridajte údaje** pre **História transakcií zákazníka**.

1. Vyberte typ sémantickej aktivity **SalesOrderLine** ktorý obsahuje požadované informácie o histórii transakcií alebo nákupov. Ak aktivita nebola nastavená, vyberte **tu** a vytvorte ho.

1. Pod **Aktivity**, ak boli atribúty aktivity pri vytváraní aktivity sémanticky mapované, vyberte konkrétne atribúty alebo entitu, na ktoré sa má výpočet zamerať. Ak sémantické mapovanie nenastalo, vyberte **Upraviť** a zmapovať svoje údaje.

   :::image type="content" source="media/product-recommendation-select-semantic-activity.PNG" alt-text="Bočná tabla zobrazujúca výber daných činností v rámci sémantického typu.":::

1. Vyberte **Ďalšie** a skontrolujte atribúty požadované pre tento model.

1. Vyberte **Uložiť**.

1. Vyberte **Ďalej**.

### <a name="add-product-information-and-filters"></a>Pridajte informácie o produkte a filtre

Niekedy sú pre určitý typ predikcie prospešné alebo vhodné iba určité produkty. Pomocou produktových filtrov identifikujte podskupinu produktov so špecifickými vlastnosťami, ktoré môžete odporučiť svojim zákazníkom. Model použije na získanie vzorov všetky dostupné produkty, ale vo svojom výstupe použije iba produkty zodpovedajúce filtru produktov.

1. Pridajte svoju entitu katalógu produktov, ktorá obsahuje informácie pre každý produkt. Namapujte požadované informácie a vyberte **Uložiť**.

1. Vyberte **Ďalej**.

1. Vyberte **Produktové filtre**:

   - **Žiadne filtre**: Použite všetky produkty v predikcii odporúčaní produktov.

   - **Definujte konkrétne filtre produktu**: Používajte konkrétne produkty v predikcii odporúčaní produktov. V **Atribúty katalógu produktov** vyberte atribúty z entity katalógu produktov, ktoré chcete zahrnúť do filtra.

     :::image type="content" source="media/product-filters-sidepane.png" alt-text="Bočný panel zobrazujúci priradené v entite katalógu výrobkov, ktorý sa má vybrať pre filtre výrobkov.":::

1. Vyberte, či chcete použiť produktový filter **a** alebo **alebo** aby ste logicky skombinovali svoj výber atribútov z katalógu produktov.

   :::image type="content" source="media/product-filters-sample.png" alt-text="Ukážka konfigurácie produktových filtrov kombinovaná s logickými konektormi AND.":::

1. Vyberte **Ďalej**.

### <a name="set-update-schedule"></a>Nastavenie plánu aktualizácie

1. Vyberte frekvenciu preškolenia svojho modelu. Toto nastavenie je dôležité na aktualizáciu presnosti predpovedí pri prijímaní nových údajov do Customer Insights. Väčšina firiem môže preškoľovať raz mesačne a získať dobrú presnosť pre svoju predikciu.

1. Vyberte **Ďalej**.

### <a name="review-and-run-the-model-configuration"></a>Skontrolujte a spustite konfiguráciu modelu

The **Skontrolujte a spustite** krok zobrazuje súhrn konfigurácie a poskytuje možnosť vykonať zmeny pred vytvorením predikcia.

1. Vyberte **Upraviť** pri ktoromkoľvek z krokov na kontrolu a vykonanie akýchkoľvek zmien.

1. Ak ste s výberom spokojní, vyberte si **Uložiť a spustiť** na spustenie modelu. Vyberte položku **Hotovo**. The **Moje predpovede** karta sa zobrazí počas vytvárania predikcia. Proces môže trvať niekoľko hodín, v závislosti od množstva údajov použitých v predikcii.

[!INCLUDE [progress-details](includes/progress-details-pane.md)]

## <a name="view-prediction-results"></a>Zobraziť výsledky predikcia

1. Ísť do **Inteligencia** > **Predpovede**.

1. V **Moje predpovede** vyberte predikcia, ktorý chcete zobraziť.

Na stránke s výsledkami je päť primárnych sekcií údajov.

- **Výkon modelu:** Stupne A, B alebo C označujú výkon predikcia a môžu vám pomôcť pri rozhodovaní o použití výsledkov uložených vo výstupnej entite.
  
  :::image type="content" source="media/product-recommendation-modelperformance.PNG" alt-text="Obrázok výsledku výkonu modelu so stupňom A.":::

  Klasifikácie sa určujú na základe nasledujúcich pravidiel:
  - **A** keď je metrika „Success @ K“ aspoň o 10 % vyššia ako základná hodnota.
  - **B** keď je metrika „Success @ K“ o 0 % až 10 % vyššia ako základná hodnota.
  - **C** keď je metrika „Success @ K“ nižšia ako základná hodnota.
  - **Základná línia** : Najviac odporúčané produkty podľa nákupu sa počítajú medzi všetkými zákazníkmi + naučené pravidlá identifikované modelom = súbor odporúčaní pre zákazníkov. Predikcie sa potom porovnajú s najlepšími produktmi vypočítanými podľa počtu zákazníkov, ktorí si produkt kúpili. Ak má zákazník v odporúčaných produktoch aspoň jeden produkt, ktorý sa tiež zobrazil v najpredávanejších produktoch, považuje sa to za súčasť základnej úrovne. Ak si napríklad 10 z týchto zákazníkov zakúpilo odporúčaný produkt z celkového počtu 100 zákazníkov, základná hodnota je 10 %.
  - **Úspech @K** : Odporúčania sa vytvárajú pre všetkých zákazníkov a porovnávajú sa s overovacím súborom časového obdobia transakcií. Napríklad v 12-mesačnom období je 12. mesiac vyčlenený ako overovací súbor údajov. Ak model predikuje aspoň jednu vec, ktorú by ste si kúpili v 12. mesiaci, na základe toho, čo sa dozvedel z predchádzajúcich 11 mesiacov, zákazník by zvýšil metriku „Úspech pri K“.

- **Najčastejšie navrhované produkty (s počítadlom):** Prvých päť produktov, ktoré boli predpovedané pre vašich zákazníkov.
  
  :::image type="content" source="media/product-recommendation-topproducts.PNG" alt-text="Graf znázorňujúci 5 najdôležitejších produktov.":::

- **Kľúčové faktory odporúčania:** Model využíva históriu transakcií zákazníkov na vydávanie odporúčaní k produktom. Učí sa vzory založené na minulých nákupoch a zisťuje podobnosti medzi zákazníkmi a produktmi. Tieto podobnosti sa potom používajú na generovanie odporúčaní k produktom.
  Nasledujúce faktory môžu ovplyvniť odporúčanie produktu generované modelom.
  - **Minulé transakcie** : Odporúčaný produkt bol založený na nákupoch v minulosti. Model môže napríklad odporučiť *Myš Surface Arc* ak si niekto nedávno kúpil *Surface Book 3* a *pero Surface*. Model sa dozvedel, že historicky si veľa zákazníkov zakúpilo produkt *Myš Surface Arc* po zakúpení *Surface Book 3* a *pera Surface*.
  - **Podobnosť zákazníka** : Odporúčaný produkt historicky kúpili iní zákazníci, ktorí vykazujú podobné vzorce nákupu. Napríklad Jozef dostal odporúčanie *Surface Headphones 2*, pretože Lenka a Robo si nedávno kúpili *Surface Headphones 2*. Tento model verí, že Jozef je podobný Lenke a Robovi, pretože v minulosti mali podobné nákupné vzory.
  - **Podobnosť produktu**: Odporúčaný produkt je podobný ako u iných produktov, ktoré si zákazník predtým kúpil. Model považuje dva výrobky za podobné, ak ich kúpili spoločne alebo podobní zákazníci. Napríklad niekto dostane odporúčanie na *úložnú jednotku USB* pretože predtým kúpili *Adaptér USB-C na USB* a model je presvedčený, že *Úložná jednotka USB* je podobná *Adaptéru USB-C na USB* na základe historických nákupných vzorcov.

  Každé odporúčanie produktu je ovplyvnené jedným alebo viacerými z týchto faktorov. Percento odporúčaní, v ktorých zohrával úlohu každý ovplyvňujúci faktor, je znázornené v grafe. V nasledujúcom príklade bolo 100 % odporúčaní ovplyvnených minulými transakciami, 60 % podobnosťou zákazníkov a 22 % podobnosťou produktov. Umiestnením kurzora myši na pruhy v grafe zobrazíte presné percento, kam prispeli ovplyvňujúce faktory.
  
  :::image type="content" source="media/product-recommendation-keyrecommendationfactors.png" alt-text="Kľúčové faktory odporúčaní získané modelom na generovanie odporúčaní produktov.":::

- **Štatistiky údajov** : Prehľad počtu transakcií, zákazníkov a produktov, ktoré model zvažoval. Je založený na vstupných údajoch, ktoré boli použité na osvojenie vzorcov a generovanie odporúčaní produktov.

  :::image type="content" source="media/product-recommendation-datastatistics.png" alt-text="Štatistika údajov okolo vstupných údajov používaných modelom na učenie sa vzorov.":::
  
  Model využíva všetky dostupné údaje na učenie vzorcov. Ak teda v konfigurácii modelu používate filtrovanie produktov, táto časť zobrazuje celkový počet produktov, ktoré model analyzoval, aby sa naučil vzory, ktorý sa môže líšiť od počtu produktov, ktoré zodpovedajú definovaným kritériám filtrovania. Filtrovanie sa aplikuje na výstup generovaný modelom.

- **Vzorové odporúčania produktov:** Vzorka odporúčaní, o ktorých sa modelka domnieva, že si ich zákazník pravdepodobne kúpi. Ak sa pridá katalóg produktov, ID produktov sa nahradia názvami produktov.

  :::image type="content" source="media/product-recommendation-highconfidence.PNG" alt-text="Zoznam zobrazujúci návrhy vysokej dôveryhodnosti pre vybranú skupinu individuálnych zákazníkov.":::

> [!NOTE]
> Vo výstupnej entite pre tento model *skóre* ukazuje kvantitatívnu mieru odporúčania. Model odporúča produkty s vyšším skóre v porovnaní s produktmi s nižším skóre. Ak chcete zobraziť skóre, prejdite na **Údaje** > **entity** a zobrazte kartu údajov pre výstupnú entitu, ktorú ste definovali pre tento model.

[!INCLUDE [footer-include](includes/footer-banner.md)]
