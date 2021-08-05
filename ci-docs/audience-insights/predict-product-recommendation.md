---
title: Predikcia odporúčania produktov
description: Predikujte produkty, ktoré si zákazník pravdepodobne kúpi alebo ktoré bude chcieť použiť.
ms.date: 03/17/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: bcbafa513c2c61b0280c91aa7ed71e211c32c35c
ms.sourcegitcommit: dab2cbf818fafc9436e685376df94c5e44e4b144
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 07/13/2021
ms.locfileid: "6556143"
---
# <a name="product-recommendation-prediction-preview"></a>Predikcia odporúčania produktov (verzia Preview)

Model odporúčaní produktov vytvára súbory prediktívnych odporúčaní produktov. Odporúčania vychádzajú z predchádzajúceho nákupného správania a zákazníkov s podobnými vzormi nákupov. Na stránke **Analýza** > **Predikcie** môžete vytvoriť nové predikcie odporúčaní produktov. Vyberte **Moje predikcie**, aby ste videli ďalšie predikcie, ktoré ste vytvorili.

Na odporúčania výrobkov sa môžu vzťahovať miestne zákony a nariadenia a očakávania zákazníkov, ktorých model nie je zostavený tak, aby zohľadňoval konkrétne požiadavky.  Ako používateľ tejto prediktívnej schopnosti **predtým, ako ich doručíte zákazníkom, musíte si ich prečítať** aby ste sa ubezpečili, že dodržiavate všetky príslušné zákony alebo nariadenia a očakávania zákazníkov týkajúce sa toho, čo môžete odporučiť. 

Výstup tohto modelu vám navyše poskytne odporúčania založené na ID produktu. Váš mechanizmus doručovania bude musieť namapovať predpovedané ID produktu na vhodný obsah pre vašich zákazníkov, aby zohľadnili lokalizáciu, obrazový obsah a ďalší obsah alebo správanie špecifické pre podnikanie.

## <a name="sample-guide"></a>Ukážkový sprievodca

Ak máte záujem vyskúšať túto funkciu, ale nemáte údaje na splnenie požiadaviek uvedených nižšie, môžete [vytvoriť ukážkovú implementáciu](sample-guide-predict-product-recommendation.md).

## <a name="prerequisites"></a>Predpoklady

- Minimálne [povolenia prispievateľa](permissions.md) v Customer Insights.

- Znalosti v oblasti obchodu, aby ste pochopili rôzne typy produktov pre vaše podnikanie a to, ako s nimi vaši zákazníci interagujú. Podporujeme odporúčanie produktov, ktoré už vaši zákazníci predtým kúpili, alebo odporúčania pre nové produkty.

- Údaje o transakciách, nákupoch a ich histórii:
    - Identifikátory transakcií na odlíšenie nákupov alebo transakcií.
    - Identifikátory zákazníkov, aby sa transakcie mapovali na vašich zákazníkov.
    - Dátumy transakčných udalostí, ktoré určujú dátumy, kedy došlo k transakcii.
    - Informácie o ID produktu pre transakciu.
    - (Voliteľné) Entita údajových katalógov výrobkov na použitie filtra výrobkov.
    - (Voliteľné) Či sa dá transakcia vrátiť alebo nie.
    - Schéma sémantických údajov vyžaduje nasledujúce informácie:
        - **ID transakcie:** Jedinečný identifikátor nákupu alebo transakcie.
        - **Dátum transakcie:** Dátum nákupu alebo transakcie.
        - **Hodnota transakcie:** Číselná hodnota nákupu alebo transakcie.
        - **Jedinečné ID produktu:** ID zakúpeného produktu alebo služby, ak sú vaše údaje na úrovni riadkovej položky.
        - (Voliteľné) **Nákup alebo vrátenie:** Logické pole, kde je hodnota *true* identifikuje, že transakcia bola vrátená. Ak nie sú poskytnuté údaje o nákupe alebo vrátení, model a **Hodnota transakcie** sú negatívne, tieto informácie použijeme tiež na odvodenie návratnosti.
- Navrhované charakteristiky údajov:
    - Dostatočné historické údaje: Aspoň jeden rok transakčných údajov, najlepšie dva až tri roky, aby sa zohľadnila sezónnosť.
    - Viac nákupov na zákazníka: Tri alebo viac transakcií na ID zákazníka
    - Počet zákazníkov: Minimálne 100 zákazníkov, najlepšie viac ako 10 000 zákazníkov. Model zlyhá s menej ako 100 zákazníkmi.

> [!NOTE]
> - Tento model vyžaduje históriu transakcií vašich zákazníkov. Definícia transakcie je dosť flexibilná. Ako vstup môžu slúžiť všetky údaje, ktoré popisujú interakciu používateľa a produktu. Napríklad nákup produktu, absolvovanie kurzu alebo účasť na udalosti.
> - Aktuálne je možné nakonfigurovať iba jednu entitu histórie transakcií. Ak existuje viac entít nákupu, pred prijatím údajov ich zjednoťte v Power Query.
> - Ak sú objednávka a podrobnosti objednávky odlišné entity, pred použitím v modeli ich spojte. Model v entite nefunguje iba s ID objednávky alebo príjmovým dokladom.


## <a name="create-a-product-recommendation-prediction"></a>Vytvorenie predikcie odporúčania produktu

1. V Customer Insights prejdite na stránku **Analýza** > **Predikcie**.

1. Vyberte dlaždicu **Model produktových odporúčaní (verzia Preview)** a vyberte **Použiť tento model**.
   > [!div class="mx-imgBorder"]
   > ![Dlaždica Model odporúčaní produktov s tlačidlom Použiť tento model.](media/product-recommendation-usethismodel.PNG "Dlaždica Model odporúčaní produktov s tlačidlom Použiť tento model")

1. Skontrolujte informácie o požiadavkách na model. Ak máte požadované údaje, vyberte **Začíname**.

### <a name="name-model"></a>Názov modelu

1. Zadajte názov modelu, ktorý ho odlíši od ostatných modelov.

1. Zadajte názov výstupnej entity iba pomocou písmen a číslic, bez medzier. Toto je názov, ktorý bude používať modelová entita. Potom vyberte položku **Ďalej**.

### <a name="define-product-recommendation-configuration"></a>Definujte konfiguráciu odporúčania produktu

1. Nastavte **Počet produktov**, ktoré chcete odporučiť zákazníkovi. Táto hodnota závisí od toho, ako váš spôsob doručenia vyplní údaje. Ak môžete odporučiť tri produkty, nastavte túto hodnotu zodpovedajúcim spôsobom.
   
   >[!TIP]
   > Môžete si vybrať **Uložiť a zavrieť** kedykoľvek a predikciu uložiť ako koncept. Koncept predikcie nájdete na karte **Moje predikcie**.

1. Vyberte, ak chcete **Navrhnúť produkty, ktoré si zákazníci nedávno zakúpili**.

1. Ak ste sa rozhodli *neodporúčať* nedávno zakúpené produkty, nastavte **Dĺžka spätného zobrazenia**. Toto nastavenie určuje časový rámec, ktorý model zváži pred opätovným odporúčaním produktu používateľovi. Napríklad uveďte, že zákazník si kúpi notebook každé dva roky. Toto okno sa zameriava na históriu nákupov za posledné dva roky a ak nájdu položku, položka sa odfiltruje z odporúčaní.

1. Vyberte **Ďalej**

### <a name="add-required-data"></a>Pridanie požadovaných údajov

1. Vyberte **Pridať údaje** pre **História transakcií zákazníka** a vyberte entitu, ktorá poskytuje informácie o histórii transakcií/nákupov, ako je to opísané v [predpokladoch](#prerequisites).

1. Mapujte sémantické polia na atribúty v entite histórie nákupu a vyberte **Ďalej**. Pre popis polí sa pozrite na [požiadavky](#prerequisites).
   > [!div class="mx-imgBorder"]
   > ![Definovanie vzťahu entity.](media/product-recommendation-purchasehistorymapping.PNG "Stránka História nákupu zobrazujúca sémantické atribúty, ktoré sú mapované na polia vo vybranej entite histórie nákupu")

1. Ak polia nie sú vyplnené, nakonfigurujte vzťah medzi entitou histórie nákupov a entitou *Zákazník*.
    1. Vyberte **entitu histórie nákupov**.
    1. Vyberte **Pole**, ktoré identifikuje zákazníka v entite histórie nákupov. Musí sa vzťahovať na ID primárneho zákazníka vašej entity *Zákazník*.
    1. Vyberte **Entitu zákazníka**, ktorá sa zhoduje s vašou primárnou entitou zákazníka.
    1. Zadajte názov, ktoré opisuje vzťah.
       > [!div class="mx-imgBorder"]
       > ![Stránka histórie nákupov zobrazujúca vytvorenie vzťahu so zákazníkom.](media/model-purchase-join.png "Stránka histórie nákupov zobrazujúca vytvorenie vzťahu so zákazníkom")

1. Vyberte položku **Uložiť**.

1. Vyberte **Ďalej**.

### <a name="configure-product-filters"></a>Konfigurácia filtrov produktov

Niekedy sú pre určitý typ predikcie prospešné alebo vhodné iba určité produkty. Filtre produktov vám umožňujú identifikovať podmnožinu produktov so špecifickými vlastnosťami, ktoré môžete odporučiť zákazníkom. Model použije na získanie vzorov všetky dostupné produkty, ale vo svojom výstupe použije iba produkty zodpovedajúce filtru produktov.

1. V kroku **Pridajte informácie o produkte** pridajte katalóg svojich produktov s informáciami o každom produkte. Mapujte požadované informácie vo výbere možnosti **Ďalej**.

3. V kroku **Produktové filtre** vyberte jednu z nasledujúcich možností.

   * **Žiadne filtre**: Použite všetky produkty v predikcii odporúčaní produktov.

   * **Definujte konkrétne filtre produktu**: Používajte konkrétne produkty v predikcii odporúčaní produktov.

1. Vyberte **Ďalej**.

1. Ak sa rozhodnete definovať produktový filter, musíte ho definovať teraz. V table **Atribúty katalógu výrobkov** vyberte atribúty z *entity katalógu výrobkov*, ktoré chcete zahrnúť do filtra.

   :::image type="content" source="media/product-filters-sidepane.png" alt-text="Bočný panel zobrazujúci priradené v entite katalógu výrobkov, ktorý sa má vybrať pre filtre výrobkov.":::

1. Vyberte, či chcete aby produktový filter použil **a** alebo **alebo** konektory, ktoré logicky kombinujú váš výber atribútov z katalógu produktov.
   
   :::image type="content" source="media/product-filters-sample.png" alt-text="Ukážka konfigurácie produktových filtrov kombinovaná s logickými konektormi AND.":::

1. Vyberte **Ďalej**.

### <a name="set-update-schedule-and-review-configuration"></a>Nastavte plán aktualizácií a skontrolujte konfiguráciu

1. Nastavte frekvenciu na preškolenie modelu. Toto nastavenie je dôležité na aktualizáciu presnosti predikcií, keď sa nové údaje importujú do Customer Insights. Väčšina firiem môže preškoľovať raz mesačne a získať dobrú presnosť pre svoju predikciu.

1. Vyberte **Ďalej**.

1. Skontrolujte konfiguráciu. Výberom položky **Upraviť** pod zobrazenou hodnotu sa môžete vrátiť späť do ktorejkoľvek časti konfigurácie predikcie. Alebo si môžete vybrať krok konfigurácie z indikátora priebehu.

1. Ak sú všetky hodnoty správne nakonfigurované, vyberte položku **Uložiť a spustiť** a začnite proces predikcie. Na karte **Moje predikcie** sa zobrazuje stav vašich predikcií. Proces môže trvať niekoľko hodín, v závislosti od množstva údajov použitých v predikcii.

## <a name="review-a-prediction-status-and-results"></a>Skontrolujte stav a výsledky predikcie

1. Prejdite na kartu **Moje predikcie** na **Inteligencia** > **Predikcie**.
   > [!div class="mx-imgBorder"]
   > ![Zobrazenie stránky Moje predikcie.](media/product-recommendation-mypredictions.PNG "Zobrazenie stránky Moje predikcie")

1. Vyberte predikciu, ktorú chcete skontrolovať.
   - **Názov predikcie:** Názov predikcie uvedený pri jej vytváraní.
   - **Typ predikcie:** Typ modelu použitého na predikciu
   - **Entita Výstup:** Názov entity, do ktorej sa má uložiť výstup predikcie. Entitu s týmto názvom nájdete v časti **Údaje** > **Entity**.    
      *Skóre* vo výstupnej entite je kvantitatívne opatrenie odporúčania. Model odporúča produkty s vyšším skóre v porovnaní s produktmi s nižším skóre.
   - **Predpovedané pole:** Toto pole je vyplnené iba pre niektoré typy predpovedí a nepoužíva sa v predikcii odporúčaní produktu.
   - **Postavenie:** Aktuálny stav spustenia predikcie.
        - **Vo fronte:** Predikcia momentálne čaká na spustenie ďalších procesov.
        - **Obnovuje sa:** Predikcia momentálne beží v etape „skóre“, aby sa dosiahli výsledky, ktoré sa dostanú do výstupnej entity.
        - **Zlyhalo:** predikcia zlyhala. Podrobnosti si prečítajte po stlačení možnosti **Záznamy**.
        - **Úspešné:** predikcia bola úspešná. Vyberte **Zobrazenie** pod zvislými troma bokami na kontrolu predikcie
   - **Upravené:** Dátum zmeny konfigurácie pre predikciu sa zmenil.
   - **Posledná aktualizácia:** Dátum obnovenia výsledkov predikcie vo výstupnej entite.

1. Vyberte zvislé tri bodky vedľa predikcie, pre ktorú chcete skontrolovať výsledky, a vyberte **Zobraziť**.
   > [!div class="mx-imgBorder"]
   > ![Zobrazenie možností v ponuke vertikálnych troch bodiek pre predikciu vrátane úprav, obnovenia, zobrazenia, protokolov a odstránenia.](media/product-recommendation-verticalellipses.PNG "Zobrazenie možností v ponuke vertikálnych troch bodiek pre predikciu vrátane úprav, obnovenia, zobrazenia, protokolov a odstránenia")

1. Na stránke s výsledkami sa nachádza päť hlavných sekcií údajov:
    1. **Výkon tréningového modelu:** A, B alebo C sú možné skóre. Toto skóre označuje výkon predikcie a môže vám pomôcť pri rozhodovaní o použití výsledkov uložených vo výstupnej entite.
        - Skóre sa určujú na základe nasledujúcich pravidiel:
            - **A** Model bude brať do úvahy kvalitu **A**, ak je metrika „Úspech pri K“ minimálne o 10 % vyššia ako základná hodnota. 
            - **B** Model bude brať do úvahy kvalitu **B**, ak je metrika „Úspech pri K“ o 0 až 10 % vyššia ako základná hodnota.
            - **C** Model bude brať do úvahy kvalitu **C**, ak je metrika „Úspech pri K“ o 0 až 10 % menšia ako základná hodnota.
               
               > [!div class="mx-imgBorder"]
               > ![Zobrazenie výsledku výkonnosti modelu.](media/product-recommendation-modelperformance.PNG "Zobrazenie výsledku výkonnosti modelu")
            - **Východisková hodnota**: Model preberá najviac odporúčané produkty podľa počtu nákupov u všetkých zákazníkov a na základe naučených pravidiel identifikovaných v modeli vytvára pre zákazníkov skupinu odporúčaní. Predikcie sa potom porovnajú s najlepšími produktmi vypočítanými podľa počtu zákazníkov, ktorí si produkt kúpili. Ak má zákazník v odporúčaných produktoch aspoň jeden produkt, ktorý sa tiež zobrazil v najpredávanejších produktoch, považuje sa to za súčasť základnej úrovne. Ak by tu bolo 10 z týchto zákazníkov, ktorí si kúpili odporúčaný produkt z celkovo 100 zákazníkov, základná hodnota by bola 10 %.
            - **Úspech pri K**: Pomocou overovacej množiny časového obdobia transakcií sa vytvoria odporúčania pre všetkých zákazníkov a porovnajú sa s overovacou množinou transakcií. Napríklad v období 12 mesiacov môže byť 12. mesiac vyčlenený ako súbor overovacích údajov. Ak model predikuje aspoň jednu vec, ktorú by ste si kúpili v 12. mesiaci, na základe toho, čo sa dozvedel z predchádzajúcich 11 mesiacov, zákazník by zvýšil metriku „Úspech pri K“.
    
    1. **Najčastejšie navrhované produkty (s počítadlom):** Prvých päť produktov, ktoré boli predpovedané pre vašich zákazníkov.
       > [!div class="mx-imgBorder"]
       > ![Graf znázorňujúci 5 najdôležitejších produktov.](media/product-recommendation-topproducts.PNG "Graf znázorňujúci 5 najdôležitejších produktov")
    
    1. **Kľúčové faktory odporúčania:** Model využíva históriu transakcií zákazníkov na vydávanie odporúčaní k produktom. Učí sa vzory založené na minulých nákupoch a zisťuje podobnosti medzi zákazníkmi a produktmi. Tieto podobnosti sa potom používajú na generovanie odporúčaní k produktom.
    Nasledujú faktory, ktoré by mohli ovplyvniť odporúčanie produktu generované modelom. 
        - **Minulé transakcie**: Model nákupu v minulosti využíval na generovanie odporúčaní k produktom. Model môže napríklad odporučiť _Myš Surface Arc_ ak si niekto nedávno kúpil _Surface Book 3_ a _pero Surface_. Model sa dozvedel, že historicky si veľa zákazníkov zakúpilo produkt _Myš Surface Arc_ po zakúpení _Surface Book 3_ a _pera Surface_.
        - **Podobnosť zákazníka** : Odporúčaný produkt historicky kúpili iní zákazníci, ktorí vykazujú podobné vzorce nákupu. Napríklad Jozef dostal odporúčanie _Surface Headphones 2_, pretože Lenka a Robo si nedávno kúpili _Surface Headphones 2_. Tento model verí, že Jozef je podobný Lenke a Robovi, pretože v minulosti mali podobné nákupné vzory.
        - **Podobnosť produktu**: Odporúčaný produkt je podobný ako u iných produktov, ktoré si zákazník predtým kúpil. Model považuje dva výrobky za podobné, ak ich kúpili spoločne alebo podobní zákazníci. Napríklad niekto dostane odporúčanie na _úložnú jednotku USB_ pretože predtým kúpili _Adaptér USB-C na USB_ a model je presvedčený, že _Úložná jednotka USB_ je podobná _Adaptéru USB-C na USB_ na základe historických nákupných vzorcov.

        Každé odporúčanie produktu je ovplyvnené jedným alebo viacerými z týchto faktorov. Percento odporúčaní, v ktorých zohrával úlohu každý ovplyvňujúci faktor, je znázornené v grafe. V nasledujúcom príklade bolo 100 % odporúčaní ovplyvnených minulými transakciami, 60 % podobnosťou zákazníkov a 22 % podobnosťou produktov. Umiestnením kurzora myši na pruhy v grafe zobrazíte presné percento, kam prispeli ovplyvňujúce faktory.

        > [!div class="mx-imgBorder"]
        > ![Kľúčové faktory odporúčaní.](media/product-recommendation-keyrecommendationfactors.png "Kľúčové faktory odporúčaní, ktoré sa model naučil pri generovaní odporúčaní produktu")
       
     
   1. **Štatistika údajov**: Poskytuje prehľad počtu transakcií, zákazníkov a produktov, ktoré model zohľadňuje. Je založený na vstupných údajoch, ktoré boli použité na osvojenie vzorcov a generovanie odporúčaní produktov.

      > [!div class="mx-imgBorder"]
      > ![Štatistika údajov.](media/product-recommendation-datastatistics.png "Štatistika údajov okolo vstupných údajov, ktoré model používa na učenie sa vzorov")

      Táto časť zobrazuje štatistiky okolo údajových bodov, ktoré model použil na získanie vzorov a generovanie odporúčaní produktov. Filtrovanie, ako je nakonfigurované v konfigurácii modelu, sa použije na výstup generovaný modelom. Model však využíva všetky dostupné údaje na osvojenie si vzorcov. Preto ak v konfigurácii modelu použijete filtrovanie produktov, v tejto časti sa zobrazí celkový počet produktov, ktoré model analyzoval, aby sa naučil vzory, ktoré sa môžu líšiť od počtu produktov, ktoré zodpovedajú definovaným kritériám filtrovania.

   1. **Vysoko spoľahlivé odporúčania produktu:** Ukážka odporúčaní poskytnutých zákazníkom, o ktorých model verí, že si ich zákazník pravdepodobne kúpi.    
      Ak sa pridá katalóg produktov, ID produktov sa nahradia názvami produktov. Názvy produktov poskytujú efektívnejšie a intuitívnejšie informácie o predpovediach.
       > [!div class="mx-imgBorder"]
       > ![Zoznam zobrazujúci návrhy vysokej dôveryhodnosti pre vybranú skupinu individuálnych zákazníkov.](media/product-recommendation-highconfidence.PNG "Zoznam zobrazujúci návrhy vysokej dôveryhodnosti pre vybranú skupinu individuálnych zákazníkov")

## <a name="manage-predictions"></a>Spravovanie predikcií

Je možné optimalizovať, odstraňovať problémy, obnovovať alebo mazať predikcie. V prehľade použiteľnosti vstupných údajov nájdete informácie o tom, ako urobiť predikciu rýchlejšou a spoľahlivejšou. Ďalšie informácie nájdete v článku [Spravovanie predikcií](manage-predictions.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
