---
title: Zrušenie odberu predikcia (obsahuje video)
description: Predikuje, či hrozí riziko, že zákazník prestane používať predplatené produkty alebo služby vašej spoločnosti.
ms.date: 08/19/2020
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 72aa38242df21181f142833db03c825574455986
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 07/18/2022
ms.locfileid: "9171068"
---
# <a name="subscription-churn-prediction"></a>Predikcia straty predplatného

Predikcia rizika straty predplatného pomáha predikovať, či hrozí riziko, že zákazník prestane používať predplatené produkty alebo služby vašej spoločnosti. Môžete vytvoriť novú predikciu rizika straty predplatného na stránke **Inteligencia** > **Predikcie**. Vyberte **Moje predikcie**, aby ste videli ďalšie predikcie, ktoré ste vytvorili.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWOKNQ]

> [!TIP]
> Vyskúšajte kurz pre predikciu odchodov predplatiteľov pomocou vzorových údajov: [Predikcia odchodov predplatiteľov – vzorový sprievodca](sample-guide-predict-subscription-churn.md).

## <a name="prerequisites"></a>Predpoklady

- Minimálne [povolenia prispievateľa](permissions.md).
- Obchodné znalosti, aby ste pochopili, čo znamená pre vaše podnikanie riziko straty predplatného. Podporujeme definície rizika straty predplatného založené na čase. Znamená to, že zákazník sa považuje za strateného určitú dobu po ukončení predplatného.
- Údaje o vašich predplatných a ich história:
    - Identifikátory predplatného na rozlíšenie predplatného.
    - Identifikátory zákazníka, ktoré zodpovedajú predplatným vašich zákazníkov.
    - Dátumy udalostí predplatného, ktoré definujú dátumy začiatku, dátumy ukončenia a dátumy udalostí, ku ktorým došlo.
    - Informácie o predplatnom na definovanie toho, či ide o opakujúce sa predplatné a ako často sa obnovuje.
    - Schéma sémantických údajov pre predplatné vyžaduje nasledujúce informácie:
        - **ID predplatného:** Jedinečný identifikátor predplatného.
        - **Dátum ukončenia predplatného:** Dátum uplynutia platnosti predplatného pre zákazníka.
        - **Dátum začatia predplatného:** Dátum začatia platnosti predplatného pre zákazníka.
        - **Dátum transakcie:** Dátum zmeny predplatného. Napríklad zákazník kupujúci alebo rušiaci odber.
        - **Je to opakujúce sa predplatné:** Logické pole pravda/nepravda, ktoré určuje, či sa predplatné obnoví s rovnakým ID predplatného bez zásahu zákazníka
        - **Frekvencia opakovania (v mesiacoch):** V prípade opakujúceho sa predplatného je to obdobie, na ktoré sa predplatné obnoví. Je uvedené v mesiacoch. Napríklad ročné predplatné, ktoré sa automaticky obnovuje pre zákazníka každý rok na ďalší rok, má hodnotu 12.
        - (Voliteľne) **Suma predplatného:** Suma meny, ktorú zákazník zaplatí za obnovenie predplatného. Môže pomôcť identifikovať vzory pre rôzne úrovne predplatného.
- Údaje o zákazníckych aktivitách:
    - Identifikátory aktivity na rozlíšenie aktivít rovnakého typu.
    - Identifikátory zákazníka na mapovanie aktivít vašich zákazníkov.
    - Informácie o činnosti obsahujúce názov a dátum aktivity.
    - Schéma sémantických údajov pre aktivity zákazníka obsahuje:
        - **Primárny kľúč:** Jedinečný identifikátor aktivity. Napríklad návšteva webovej stránky alebo záznam o použití ukazujúci, že si zákazník pozrel epizódu televíznej show.
        - **Časová značka:** Dátum a čas udalosti identifikovaný primárnym kľúčom.
        - **Udalosť:** Názov skupiny udalosti, ktorú chcete použiť. Napríklad pole s názvom „UserAction“ v streamovanej video službe by mohlo mať hodnotu „Zobrazené“.
        - **Podrobnosti:** Podrobné informácie o udalosti. Napríklad pole s názvom „ShowTitle“ v streamovanej video službe by mohlo mať hodnotu videa, ktoré si prezeral zákazník.
- Navrhované charakteristiky údajov:
    - Dostatočné historické údaje: Údaje o predplatnom minimálne na dvojnásobok zvoleného časového okna. Najlepšie dva až tri roky predplatných údajov.
    - Stav predplatného: Údaje zahŕňajú aktívne a neaktívne predplatné pre každého zákazníka, takže na každé číslo zákazníka existuje viac záznamov.
    - Počet zákazníkov: Minimálne 10 zákazníckych profilov, najlepšie viac ako 1 000 jedinečných zákazníkov. Model zlyhá s menej ako 10 zákazníkmi a nedostatkom historických údajov.
    - Úplnosť údajov: Menej ako 20 % chýbajúcich hodnôt v údajovom poli poskytnutej entity.
   
   > [!NOTE]
   > Budete potrebovať aspoň dva záznamy o aktivite pre 50 % zákazníkov, pre ktorých chcete vypočítať mieru odchodu.

## <a name="create-a-subscription-churn-prediction"></a>Vytvorenie predikcia rizika straty predplatného

1. Ísť do **Inteligencia** > **Predpovede**.
1. Vyberte **Model vracania predplatného** dlaždice a vyberte **Použite tento model**.
   > [!div class="mx-imgBorder"]
   > ![Dlaždica modelu rizika zrusenia predplatného zákazníkmi s tlačidlom Použiť tento model.](media/subscription-churn-usethismodel.PNG "Dlaždica modelu rizika straty predplatného s tlačidlom Použiť tento model")

### <a name="name-model"></a>Názov modelu

1. Zadajte názov modelu, ktorý ho odlíši od ostatných modelov.
1. Zadajte názov výstupnej entity iba pomocou písmen a číslic, bez medzier. Toto je názov, ktorý bude používať modelová entita. Potom vyberte položku **Ďalej**.

### <a name="define-customer-churn"></a>Definujte odídených zákazníkov

1. Zadajte číslo **Dni od skončenia predplatného**, po ktorých bude vaša firma považovať zákazníka za strateného. Toto obdobie je zvyčajne určené pre obchodné aktivity, ako sú ponuky alebo iné marketingové úsilie, ktoré sa snažia zabrániť strate zákazníka.
1. Zadajte počet **Dni skúmania budúcnosti na predpovedanie odchodu** na nastavenie okna, pre ktoré chcete predpovedať odchod. Ak chcete napríklad predpovedať riziko odchodu zákazníkov počas nasledujúcich 90 dní, aby ste sa prispôsobili svojmu marketingovému úsiliu o udržanie. Predpovedanie rizika churn na dlhšie alebo kratšie časové obdobia môže sťažiť riešenie faktorov vo vašom profile rizika churn, v závislosti od vašich konkrétnych obchodných požiadaviek. Na pokračovanie zvoľte možnosť **Ďalej**
   >[!TIP]
   > Môžete si vybrať **Uložiť koncept** kedykoľvek uložiť predikcia ako koncept. Draft predikcie nájdete na karte **Moje predikcie**, kde môžete pokračovať.

### <a name="add-required-data"></a>Pridanie požadovaných údajov

1. Vyberte **Pridať údaje** pre **Históriu predplatného** a vyberte entitu, ktorá poskytuje informácie o histórii predplatného, ako je opísané v [požiadavkách](#prerequisites).
1. Ak polia uvedené nižšie nie sú vyplnené, nakonfigurujte vzťah medzi entitou histórie predplatného a entitou Zákazník.
    1. Vyberte **Entita histórie predplatného**.
    1. Vyberte **Pole**, ktoré identifikuje zákazníka v entite histórie predplatného. Musí sa vzťahovať na ID primárneho zákazníka vašej entity Zákazník.
    1. Vyberte **Entitu zákazníka**, ktorá sa zhoduje s vašou primárnou entitou zákazníka.
    1. Zadajte názov, ktoré opisuje vzťah.
       > [!div class="mx-imgBorder"]
       > ![Stránka histórie predplatného, ktorá ukazuje vytvorenie vzťahu so zákazníkom.](media/subscription-churn-subscriptionhistoryrelationship.PNG "Stránka histórie predplatného, ktorá ukazuje vytvorenie vzťahu so zákazníkom")
1. Vyberte **Ďalej**.
1. Mapujte sémantické polia na atribúty v rámci entity histórie predplatného a vyberte položku **Uložiť**. Pre popis polí sa pozrite na [požiadavky](#prerequisites).
   > [!div class="mx-imgBorder"]
   > ![Stránka histórie predplatného, ktorá zobrazuje sémantické atribúty, ktoré sú mapované do polí vo vybratej entite histórie predplatného.](media/subscription-churn-subscriptionhistorymapping.PNG "Stránka histórie predplatného, ktorá zobrazuje sémantické atribúty, ktoré sú mapované do polí vo vybratej entite histórie predplatného")
1. Vyberte **Pridať údaje** pre **Aktivity zákazníka** a vyberte entitu, ktorá poskytuje informácie o aktivite zákazníka, ako je opísané v požiadavkách.
1. Vyberte typ aktivity, ktorý sa zhoduje s typom aktivity zákazníka, ktorú konfigurujete.  Vyberte **Vytvoriť nový** a uveďte meno, ak nevidíte možnosť, ktorá sa zhoduje s typom aktivity, ktorú potrebujete.
1. Budete musieť nakonfigurovať vzťah medzi vašou entitou aktivity zákazníka a entitou Zákazník.
    1. Vyberte pole, ktoré identifikuje zákazníka v tabuľke aktivity zákazníka, ktoré môže priamo súvisieť s primárnym ID zákazníka vašej entity Zákazník.
    1. Vyberte entitu Zákazníka, ktorá sa zhoduje s vašou primárnou entitou Zákazník
    1. Zadajte názov, ktoré opisuje vzťah.
1. Vyberte **Ďalej**.
1. Mapujte sémantické polia na atribúty v rámci entity aktivity zákazníka a vyberte položku **Uložiť**. Pre popis polí sa pozrite na [požiadavky](#prerequisites).
1. (Voliteľné) Ak máte akékoľvek ďalšie aktivity zákazníka, ktoré chcete zahrnúť, zopakujte vyššie uvedené kroky.
   > [!div class="mx-imgBorder"]
   > ![Definovanie vzťahu entity.](media/subscription-churn-customeractivitiesmapping.PNG "Stránka aktivít zákazníkov, ktorá zobrazuje sémantické atribúty, ktoré sú mapované do polí vo vybratej entite aktivity zákazníka")
1. Vyberte **Ďalej**.

### <a name="set-schedule-and-review-configuration"></a>Nastavenie plánu a kontrola konfigurácie

1. Nastavte frekvenciu na preškolenie modelu. Toto nastavenie je dôležité na aktualizáciu presnosti predpovedí pri prijímaní nových údajov do Customer Insights. Väčšina firiem môže preškoľovať raz mesačne a získať dobrú presnosť pre svoju predikciu.
1. Vyberte **Ďalej**.
1. Skontrolujte konfiguráciu. Výberom položky **Upraviť** pod zobrazenou hodnotu sa môžete vrátiť späť do ktorejkoľvek časti konfigurácie predikcie. Alebo si môžete vybrať krok konfigurácie z indikátora priebehu.
1. Ak sú všetky hodnoty správne nakonfigurované, vyberte položku **Uložiť a spustiť** a začnite proces predikcie. Na karte **Moje predikcie** sa zobrazuje stav vašich predikcií. Proces môže trvať niekoľko hodín, v závislosti od množstva údajov použitých v predikcii.

## <a name="review-a-prediction-status-and-results"></a>Skontrolujte stav a výsledky predikcie

1. Prejdite na kartu **Moje predikcie** na **Inteligencia** > **Predikcie**.
   > [!div class="mx-imgBorder"]
   > ![Zobrazenie stránky Moje predikcie.](media/subscription-churn-mypredictions.PNG "Zobrazenie stránky Moje predikcie")
1. Vyberte predikciu, ktorú chcete skontrolovať.
   - **Názov predikcie:** Názov predikcie uvedený pri jej vytváraní.
   - **Typ predikcie:** Typ modelu použitého na predikciu
   - **Entita Výstup:** Názov entity, do ktorej sa má uložiť výstup predikcie. Entitu s týmto názvom nájdete v časti **Údaje** > **Entity**.    
     Vo výstupnej entite *ChurnScore* je predpovedaná pravdepodobnosť churn a *IsChurn* je binárny štítok založený na *ChurnScore* s prahom 0,5. Predvolená hranica nemusí pre váš scenár fungovať. [Vytvorte nový segment](segments.md#create-a-segment) s vami preferovaným prahom.
   - **Predikované pole:** Toto pole sa vyplní iba pre niektoré typy predikcií a nepoužíva sa v predikcii rizika straty predplatného.
   - **Postavenie:** Aktuálny stav spustenia predikcie.
        - **Vo fronte:** Predikcia momentálne čaká na spustenie ďalších procesov.
        - **Obnovuje sa:** Predikcia momentálne beží v etape „skóre“, aby sa dosiahli výsledky, ktoré sa dostanú do výstupnej entity.
        - **Zlyhalo:** predikcia zlyhala. Podrobnosti si prečítajte po stlačení možnosti **Záznamy**.
        - **Úspešné:** predikcia bola úspešná. Vyberte **Zobrazenie** pod zvislými troma bokami na kontrolu predikcie
   - **Upravené:** Dátum zmeny konfigurácie pre predikciu sa zmenil.
   - **Posledná aktualizácia:** Dátum obnovenia výsledkov predikcie vo výstupnej entite.
1. Vyberte zvislé tri bodky vedľa predikcie, pre ktorú chcete skontrolovať výsledky, a vyberte **Zobraziť**.
   > [!div class="mx-imgBorder"]
   > ![Zobrazenie možností v ponuke vertikálnych troch bodiek pre predikciu vrátane úprav, obnovenia, zobrazenia, protokolov a odstránenia.](media/subscription-churn-verticalellipses.PNG "Zobrazenie možností v ponuke vertikálnych troch bodiek pre predikciu vrátane úprav, obnovenia, zobrazenia, protokolov a odstránenia")
1. Na stránke s výsledkami sú tri základné sekcie údajov:
    1. **Výkon tréningového modelu:** A, B alebo C sú možné skóre. Toto skóre označuje výkon predikcie a môže vám pomôcť pri rozhodovaní o použití výsledkov uložených vo výstupnej entite.
        - Skóre sa určujú na základe nasledujúcich pravidiel:
            - **A** Keď model presne predpovedal najmenej 50 % celkových predpovedí a keď percentuálny podiel presných predpovedí pre zákazníkov, ktorí odišli, je väčší ako historická priemerná miera odchodu najmenej o 10 % historickej priemernej miery odchodu.
            - **B** Keď model presne predpovedal najmenej 50 % celkových predpovedí a keď percentuálny podiel presných predpovedí pre zákazníkov, ktorí odišli, je až o 10 % väčší ako historická priemerná miera odchodu najmenej historickej priemernej miery odchodu.
            - **C** Keď model presne predpovedal menej ako 50 % celkových predpovedí, alebo keď percento presných predpovedí pre zákazníkov, ktorí odišli, je nižšie ako historická priemerná miera odchodu.
               > [!div class="mx-imgBorder"]
               > ![Zobrazenie výsledku výkonnosti modelu.](media/subscription-churn-modelperformance.PNG "Zobrazenie výsledku výkonnosti modelu")
    1. **Pravdepodobnosť straty (počet zákazníkov):** Skupiny zákazníkov na základe ich predpokladaného rizika straty. Tieto údaje vám môžu pomôcť neskôr, ak chcete vytvoriť segment zákazníkov s vysokým rizikom straty. Takéto segmenty pomáhajú pochopiť, kde by malo byť vaše obmedzenie pre členstvo v segmente.
       > [!div class="mx-imgBorder"]
       > ![Graf znázorňujúci distribúciu výsledkov rizika straty, rozdelený do intervalov od 0 do 100 %.](media/subscription-churn-resultdistribution.PNG "Graf znázorňujúci distribúciu výsledkov rizika straty, rozdelený do intervalov od 0 do 100 %")
    1. **Najvýznamnejšie faktory:** Pri vytváraní vašej predikcie sa zohľadňuje veľa faktorov. Každý z faktorov má svoju dôležitosť vypočítanú pre agregované predikcie, ktoré model vytvára. Tieto faktory môžete použiť na overenie výsledkov svojich predikcií. Alebo môžete tieto informácie použiť neskôr na [vytváranie segmentov](segments.md), ktoré by mohli pomôcť ovplyvniť riziko straty zákazníkov.
       > [!div class="mx-imgBorder"]
       > ![Zoznam ukazujúci vplyvné faktory a ich dôležitosť pri predikcii výsledkov rizika straty.](media/subscription-churn-influentialfactors.PNG "Zoznam ukazujúci vplyvné faktory a ich dôležitosť pri predikcii výsledkov rizika straty")

## <a name="manage-predictions"></a>Spravovanie predikcií

Je možné optimalizovať, odstraňovať problémy, obnovovať alebo mazať predikcie. V prehľade použiteľnosti vstupných údajov nájdete informácie o tom, ako urobiť predikciu rýchlejšou a spoľahlivejšou. Ďalšie informácie nájdete v článku [Spravovanie predikcií](manage-predictions.md).


[!INCLUDE [footer-include](includes/footer-banner.md)]
