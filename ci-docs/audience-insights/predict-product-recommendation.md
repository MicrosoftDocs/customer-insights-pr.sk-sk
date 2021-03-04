---
title: Predikcia odporúčania produktov
description: Predikujte produkty, ktoré si zákazník pravdepodobne kúpi alebo ktoré bude chcieť použiť.
ms.date: 02/15/2021
ms.reviewer: zacook
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 5a2eb2b4697e51a0abb933b654a9b0b150dfa6a3
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 02/15/2021
ms.locfileid: "5270533"
---
# <a name="product-recommendation-prediction-preview"></a>Predikcia odporúčania produktov (verzia Preview)

Model odporúčaní produktov vytvára súbory prediktívnych odporúčaní produktov. Odporúčania vychádzajú z predchádzajúceho nákupného správania a zákazníkov s podobnými vzormi nákupov. Na stránke **Analýza** > **Predikcie** môžete vytvoriť nové predikcie odporúčaní produktov. Vyberte **Moje predikcie**, aby ste videli ďalšie predikcie, ktoré ste vytvorili.

Na odporúčania produktov sa môžu vzťahovať miestne zákony a nariadenia, ako aj očakávania zákazníkov, ktoré model nemusí vedieť zohľadniť.  Ako používateľ tejto prediktívnej funkcie **musíte skontrolovať odporúčania ešte predtým, ako ich doručíte zákazníkom**, aby ste sa ubezpečili, že dodržiavate všetky príslušné zákony alebo nariadenia, ako aj očakávania zákazníkov týkajúce sa toho, čo môžete odporučiť. 

Výstup tohto modelu vám navyše poskytne odporúčania založené na ID produktu. Váš mechanizmus doručovania bude musieť zobať predikované ID produktov a mapovať ich na vhodný obsah pre vašich zákazníkov, aby zohľadnil lokalizáciu, obsah obrázkov a ďalší obsah alebo správanie špecifické pre podnikanie.

## <a name="sample-guide"></a>Ukážkový sprievodca

Ak máte záujem vyskúšať túto funkciu, ale nemáte údaje na splnenie požiadaviek uvedených nižšie, môžete [vytvoriť ukážkovú implementáciu](sample-guide-predict-product-recommendation.md).

## <a name="prerequisites"></a>Predpoklady

- Minimálne [povolenia prispievateľa](permissions.md) v Customer Insights.
- Znalosti v oblasti obchodu, aby ste pochopili rôzne typy produktov pre vaše podnikanie a to, ako s nimi vaši zákazníci interagujú. Podporujeme odporúčanie produktov, ktoré už vaši zákazníci predtým kúpili, alebo odporúčania pre nové produkty.
- Údaje o transakciách, nákupoch a ich histórii:
    - Identifikátory transakcií na odlíšenie nákupov alebo transakcií.
    - Identifikátory zákazníkov, aby sa transakcie mapovali na vašich zákazníkov.
    - Dátumy transakčných udalostí, ktoré určujú dátumy, kedy došlo k transakcii.
    - (Voliteľné) Informácie o ID produktu pre transakciu.
    - (Voliteľné) Či sa dá transakcia vrátiť alebo nie.
    - Schéma sémantických údajov vyžaduje nasledujúce informácie:
        - **ID transakcie:** Jedinečný identifikátor nákupu alebo transakcie.
        - **Dátum transakcie:** Dátum nákupu alebo transakcie.
        - **Hodnota transakcie:** Číselná hodnota nákupu alebo transakcie.
        - **Jedinečné ID produktu:** ID zakúpeného produktu alebo služby, ak sú vaše údaje na úrovni riadkovej položky.
        - (Voliteľné) **Nákup alebo vrátanie:** Pole pravda/nepravda, ktoré identifikuje, či transakcia bola vrátením alebo nie. Ak je **Hodnota transakcie** negatívna, tieto informácie použijeme tiež na odvodenie návratu.


## <a name="create-a-product-recommendation-prediction"></a>Vytvorenie predikcie odporúčania produktu

1. V Customer Insights prejdite na stránku **Analýza** > **Predikcie**.

1. Vyberte dlaždicu **Model produktových odporúčaní (verzia Preview)** a vyberte **Použiť tento model**.
   > [!div class="mx-imgBorder"]
   > ![Dlaždica Model odporúčaní produktov s tlačidlom Použiť tento model](media/product-recommendation-usethismodel.PNG "Dlaždica Model odporúčaní produktov s tlačidlom Použiť tento model")

1. Skontrolujte informácie o požiadavkách na model. Ak máte požadované údaje, vyberte **Začíname**.

### <a name="name-model"></a>Názov modelu

1. Zadajte názov modelu, ktorý ho odlíši od ostatných modelov.

1. Zadajte názov výstupnej entity iba pomocou písmen a číslic, bez medzier. Toto je názov, ktorý bude používať modelová entita. Potom vyberte položku **Ďalej**.

### <a name="define-product-recommendation-configuration"></a>Definujte konfiguráciu odporúčania produktu

1. Nastavte **Počet produktov**, ktoré chcete odporučiť zákazníkovi. Táto hodnota závisí od toho, ako váš spôsob doručenia vyplní údaje. Ak môžete odporučiť tri produkty, nastavte túto hodnotu zodpovedajúcim spôsobom.
   
   >[!TIP]
   > Môžete si vybrať **Uložiť a zavrieť** kedykoľvek a predikciu uložiť ako koncept. Koncept predikcie nájdete na karte **Moje predikcie**.

1. Vyberte, ak chcete **Navrhnúť produkty, ktoré si zákazníci nedávno zakúpili**.

1. Ak ste sa rozhodli *neodporúčať* nedávno zakúpené produkty, nastavte **Dĺžka spätného zobrazenia**. Toto nastavenie určuje časový rámec, ktorý model zváži pred opätovným odporúčaním produktu používateľovi. Napríklad uveďte, že zákazník si kúpi notebook každé 2 roky. Toto okno sa zameriava na históriu nákupov za posledné 2 roky a ak nájde položku, položka sa odfiltruje z odporúčaní.

1. Vyberte **Ďalej**

### <a name="add-required-data"></a>Pridanie požadovaných údajov

1. Vyberte **Pridať údaje** pre **História transakcií zákazníka** a vyberte entitu, ktorá poskytuje informácie o histórii transakcií/nákupov, ako je to opísané v [predpokladoch](#prerequisites).

1. Mapujte sémantické polia na atribúty v entite histórie nákupu a vyberte **Ďalej**. Pre popis polí sa pozrite na [požiadavky](#prerequisites).
   > [!div class="mx-imgBorder"]
   > ![Definovanie vzťahu entity](media/product-recommendation-purchasehistorymapping.PNG "Stránka História nákupu zobrazujúca sémantické atribúty, ktoré sú mapované na polia vo vybranej entite histórie nákupu")

1. Ak polia nie sú vyplnené, nakonfigurujte vzťah medzi entitou histórie nákupov a entitou *Zákazník*.
    1. Vyberte **entitu histórie nákupov**.
    1. Vyberte **Pole**, ktoré identifikuje zákazníka v entite histórie nákupov. Musí sa vzťahovať na ID primárneho zákazníka vašej entity *Zákazník*.
    1. Vyberte **Entitu zákazníka**, ktorá sa zhoduje s vašou primárnou entitou zákazníka.
    1. Zadajte názov, ktoré opisuje vzťah.
       > [!div class="mx-imgBorder"]
       > ![Stránka histórie nákupov zobrazujúca vytvorenie vzťahu so zákazníkom](media/model-purchase-join.png "Stránka histórie nákupov zobrazujúca vytvorenie vzťahu so zákazníkom")

1. Vyberte položku **Uložiť**.

1. Vyberte **Ďalej**.

### <a name="set-schedule-and-review-configuration"></a>Nastavenie plánu a kontrola konfigurácie

1. Nastavte frekvenciu na preškolenie modelu. Toto nastavenie je dôležité na aktualizáciu presnosti predikcií, keď sa nové údaje importujú do Customer Insights. Väčšina firiem môže preškoľovať raz mesačne a získať dobrú presnosť pre svoju predikciu.

1. Vyberte **Ďalej**.

1. Skontrolujte konfiguráciu. Výberom položky **Upraviť** pod zobrazenou hodnotu sa môžete vrátiť späť do ktorejkoľvek časti konfigurácie predikcie. Alebo si môžete vybrať krok konfigurácie z indikátora priebehu.

1. Ak sú všetky hodnoty správne nakonfigurované, vyberte položku **Uložiť a spustiť** a začnite proces predikcie. Na karte **Moje predikcie** sa zobrazuje stav vašich predikcií. Proces môže trvať niekoľko hodín, v závislosti od množstva údajov použitých v predikcii.

## <a name="review-a-prediction-status-and-results"></a>Skontrolujte stav a výsledky predikcie

1. Prejdite na kartu **Moje predikcie** na **Inteligencia** > **Predikcie**.
   > [!div class="mx-imgBorder"]
   > ![Zobrazenie stránky Moje predikcie](media/product-recommendation-mypredictions.PNG "Zobrazenie stránky Moje predikcie")

1. Vyberte predikciu, ktorú chcete skontrolovať.
   - **Názov predikcie:** Názov predikcie uvedený pri jej vytváraní.
   - **Typ predikcie:** Typ modelu použitého na predikciu
   - **Entita Výstup:** Názov entity, do ktorej sa má uložiť výstup predikcie. Entitu s týmto názvom nájdete v časti **Údaje** > **Entity**.
   - **Predikované pole:** Toto pole je vyplnené iba pre niektoré typy predikcií a nepoužíva sa v predikcie odchodov.
   - **Postavenie:** Aktuálny stav spustenia predikcie.
        - **Vo fronte:** Predikcia momentálne čaká na spustenie ďalších procesov.
        - **Obnovuje sa:** Predikcia momentálne beží v etape „skóre“, aby sa dosiahli výsledky, ktoré sa dostanú do výstupnej entity.
        - **Zlyhalo:** predikcia zlyhala. Podrobnosti si prečítajte po stlačení možnosti **Záznamy**.
        - **Úspešné:** predikcia bola úspešná. Vyberte **Zobrazenie** pod zvislými troma bokami na kontrolu predikcie
   - **Upravené:** Dátum zmeny konfigurácie pre predikciu sa zmenil.
   - **Posledná aktualizácia:** Dátum obnovenia výsledkov predikcie vo výstupnej entite.

1. Vyberte zvislé tri bodky vedľa predikcie, pre ktorú chcete skontrolovať výsledky, a vyberte **Zobraziť**.
   > [!div class="mx-imgBorder"]
   > ![Zobrazenie možností v ponuke vertikálnych troch bodiek pre predikciu vrátane úprav, obnovenia, zobrazenia, protokolov a odstránenia](media/product-recommendation-verticalellipses.PNG "Zobrazenie možností v ponuke vertikálnych troch bodiek pre predikciu vrátane úprav, obnovenia, zobrazenia, protokolov a odstránenia")

1. Na stránke s výsledkami sú tri základné sekcie údajov:
    1. **Výkon tréningového modelu:** A, B alebo C sú možné skóre. Toto skóre označuje výkon predikcie a môže vám pomôcť pri rozhodovaní o použití výsledkov uložených vo výstupnej entite.
        - Skóre sa určujú na základe nasledujúcich pravidiel:
            - **A** Model bude brať do úvahy kvalitu **A**, ak je metrika „Úspech pri K“ minimálne o 10 % vyššia ako základná hodnota. 
            - **B** Model bude brať do úvahy kvalitu **B**, ak je metrika „Úspech pri K“ o 0 až 10 % vyššia ako základná hodnota.
            - **C** Model bude brať do úvahy kvalitu **C**, ak je metrika „Úspech pri K“ nižšia ako základná hodnota.
               
               > [!div class="mx-imgBorder"]
               > ![Zobrazenie výsledku výkonnosti modelu](media/product-recommendation-modelperformance.PNG "Zobrazenie výsledku výkonnosti modelu")
            - **Východisková hodnota**: Model preberá najviac odporúčané produkty podľa počtu nákupov u všetkých zákazníkov a na základe naučených pravidiel identifikovaných v modeli vytvára pre zákazníkov skupinu odporúčaní. Predikcie sa potom porovnajú s najlepšími produktmi vypočítanými podľa počtu zákazníkov, ktorí si produkt kúpili. Ak má zákazník v odporúčaných produktoch aspoň jeden produkt, ktorý sa tiež zobrazil v najpredávanejších produktoch, považuje sa to za súčasť základnej úrovne. Ak by tu bolo 10 z týchto zákazníkov, ktorí si kúpili odporúčaný produkt z celkovo 100 zákazníkov, základná hodnota by bola 10 %.
            - **Úspech pri K**: Pomocou overovacej množiny časového obdobia transakcií sa vytvoria odporúčania pre všetkých zákazníkov a porovnajú sa s overovacou množinou transakcií. Napríklad v období 12 mesiacov môže byť 12. mesiac vyčlenený ako súbor overovacích údajov. Ak model predikuje aspoň jednu vec, ktorú by ste si kúpili v 12. mesiaci, na základe toho, čo sa dozvedel z predchádzajúcich 11 mesiacov, zákazník by zvýšil metriku „Úspech pri K“.
    
    1. **Najčastejšie odporúčané produkty (s počítadlom):** 5 najlepších produktov, ktoré boli predikované pre vašich zákazníkov.
       > [!div class="mx-imgBorder"]
       > ![Graf znázorňujúci 5 najdôležitejších produktov](media/product-recommendation-topproducts.PNG "Graf znázorňujúci 5 najdôležitejších produktov")
    
    1. **Vysoko spoľahlivé odporúčania produktu:** Ukážka odporúčaní poskytnutých zákazníkom, o ktorých model verí, že si ich zákazník pravdepodobne kúpi.
       > [!div class="mx-imgBorder"]
       > ![Zoznam zobrazujúci návrhy vysokej dôveryhodnosti pre vybranú skupinu individuálnych zákazníkov](media/product-recommendation-highconfidence.PNG "Zoznam zobrazujúci návrhy vysokej dôveryhodnosti pre vybranú skupinu individuálnych zákazníkov")

## <a name="fix-a-failed-prediction"></a>Oprava neúspešnej predpovede

1. Prejdite na kartu **Moje predikcie** na **Inteligencia** > **Predikcie**.

1. Vyberte predikciu, pre ktorú chcete zobraziť denníky chýb, a vyberte **Denníky**.

1. Skontrolujte všetky chyby. Môže sa vyskytnúť niekoľko typov chýb, ktoré popisujú, ktorý stav chybu spôsobil. Napríklad chyba, že nie je dostatok údajov na presnú predikciu, sa zvyčajne vyrieši načítaním ďalších údajov do Customer Insights.

## <a name="refresh-a-prediction"></a>Obnovenie predikcie

Predikcie sa automaticky obnovujú podľa rovnakého [plánu, ako sa obnovujú údaje](system.md#schedule-tab), ako je nakonfigurované v nastaveniach.

1. Prejdite na kartu **Moje predikcie** na **Inteligencia** > **Predikcie**.

1. Vyberte zvislé tri bodky vedľa predikcie, ktorú chcete obnoviť.

1. Vyberte **Obnoviť**.

## <a name="delete-a-prediction"></a>Odstránenie predikcie

Odstránenie predikcie tiež odstráni jeho výstupnú entitu.

1. Prejdite na kartu **Moje predikcie** na **Inteligencia** > **Predikcie**.

1. Vyberte zvislé tri bodky vedľa predikcie, ktorú chcete odstrániť.

1. Vyberte **Odstrániť**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]