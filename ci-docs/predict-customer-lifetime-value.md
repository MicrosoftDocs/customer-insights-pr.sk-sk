---
title: Predikcia hodnoty životnosti zákazníka (CLV)
description: Predpovedajte potenciálny výnos pre aktívnych zákazníkov v budúcnosti.
ms.date: 02/05/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: wameng
manager: shellyha
searchScope:
- ci-predictions
- ci-create-prediction
- ci-custom-models
- customerInsights
ms.openlocfilehash: ea7acd1ddbb0eb8d66fb82018637a85b6ffb369b
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 06/29/2022
ms.locfileid: "9055233"
---
# <a name="customer-lifetime-value-clv-prediction"></a>Predikcia hodnoty životnosti zákazníka (CLV)

Predikujte potenciálnu hodnotu (výnos), ktorú jednotliví aktívni zákazníci prinesú do vášho podnikania v definovanom budúcom časovom období. Táto funkcia vám môže pomôcť dosiahnuť rôzne ciele:
- Identifikovať zákazníkov s vysokou hodnotou a spracovať tento prehľad
- Vytvárať strategické zákaznícke segmenty na základe ich potenciálnej hodnoty pre uskutočňovanie personalizovaných kampaní s cieleným predajom, marketingom a podporou
- Usmerňovať vývoj produktov zameraním na funkcie, ktoré zvyšujú hodnotu zákazníka
- Optimalizovať predajnú alebo marketingovú stratégiu a presnejšie rozdeľovať rozpočet na získavanie zákazníkov
- Identifikovať a odmeňovať zákazníkov s vysokou hodnotou prostredníctvom vernostných programov alebo programov odmien 

## <a name="prerequisites"></a>Predpoklady

Skôr ako začnete, sa zamyslite, čo CLV znamená pre vaše podnikanie. V súčasnosti podporujeme predikciu CLV založenú na predikciách. Predikovaná hodnota zákazníka je založená na histórii obchodných transakcií. Na vytvorenie predikcie potrebujete minimálne povolania [Prispievateľa](permissions.md).

Pretože konfigurácia a spustenie modelu CLV netrvá dlho, zvážte vytvorenie niekoľkých modelov s rôznymi preferenciami vstupu a porovnajte výsledky modelu, aby ste zistili, ktorý modelový scenár najlepšie vyhovuje vašim obchodným potrebám.

###  <a name="data-requirements"></a>Požiadavky na údaje

Nasledujúce údaje sú povinné. Označené voliteľné údaje sa odporúčajú pre zvýšenie výkonu modelu. Čím viac údajov bude môcť model spracovať, tým presnejšia bude predikcia. Preto vám odporúčame, aby ste prijali viac údajov o aktivite zákazníkov, ak sú k dispozícii.

- Identifikátor zákazníka: Jedinečný identifikátor na priradenie transakcií k jednotlivému zákazníkovi

- História transakcií: Historický protokol transakcií so schémou sémantických údajov nižšie
    - **ID transakcie**: Jedinečný identifikátor každej transakcie
    - **Dátum transakcie**: Dátum, najlepšie časová pečiatka každej transakcie
    - **Suma transakcie**: Peňažná hodnota (napríklad výnos alebo rentabilita tržieb) každej transakcie
    - **Označenie priradené k návratkám** (voliteľné): Boolovská hodnota označujúca, či je transakcia návratom 
    - **ID produktu** (voliteľné): ID produktu zahrnutého do transakcie

- Dodatočné údaje (voliteľné), napríklad
    - Webové aktivity: história návštev webových stránok, história e-mailov
    - Vernostné aktivity: prírastky vernostných bonusových bodov a história uplatnení
    - Denník služieb pre zákazníkov, servisné volanie, reklamácia alebo história vrátení
- Údaje o aktivitách zákazníka (voliteľné):
    - Identifikátory aktivity na rozlíšenie aktivít rovnakého typu
    - Identifikátory zákazníka na mapovanie aktivít vašich zákazníkov
    - Informácie o činnosti obsahujúce názov a dátum aktivity
    - Schéma sémantických údajov pre aktivity obsahuje: 
        - **Primárny kľúč:** Jedinečný identifikátor aktivity.
        - **Časová značka**: Dátum a čas udalosti identifikovaný primárnym kľúčom.
        - **Udalosť (názov aktivity)**: Názov udalosti, ktorý chcete použiť
        - **Podrobnosti (suma alebo hodnota)**: Podrobnosti o aktivite zákazníka

- Navrhované charakteristiky údajov:
    - Dostatočné historické údaje: Aspoň jeden rok transakčných údajov. Najlepšie je dva až tri roky transakčných údajov na predpovedanie CLV na jeden rok.
    - Viacnásobné nákupy na zákazníka: V ideálnom prípade minimálne dve až tri transakcie na jedno ID zákazníka, najlepšie vo viacerých dátumoch.
    - Počet zákazníkov: Minimálne 100 jedinečných zákazníkov, najlepšie viac ako 10 000 zákazníkov. Model zlyhá s menej ako 100 zákazníkmi a nedostatkom historických údajov.
    - Úplnosť údajov: Menej ako 20 % chýbajúcich hodnôt v povinných poliach vstupných údajov   

> [!NOTE]
> - Tento model vyžaduje históriu transakcií vašich zákazníkov. Aktuálne je možné nakonfigurovať iba jednu entitu histórie transakcií. Ak existuje viacero nákupných/transakčných subjektov, môžete ich spojiť Power Query pred prijímaním údajov.
> - Pre ďalšie údaje o aktivite zákazníkov (voliteľné) však môžete pridať toľko entít aktivity zákazníkov, koľko by ste chceli, aby ich model zvážil.

## <a name="create-a-customer-lifetime-value-prediction"></a>Vytvorenie predikcie hodnoty životnosti zákazníka

1. Ísť do **Inteligencia** > **Predpovede**.

1. Vyberte dlaždicu **Hodnota životnosti zákazníka** a následne **Použiť model**. 

1. V **Celoživotná hodnota zákazníka** panel, vyberte **Začať**.

1. **Pomenujte tento model** a **Názov výstupnej entity**, aby ste ich odlíšili od iných modelov alebo entít.

1. Vyberte **Ďalej**.

### <a name="define-model-preferences"></a>Definujte predvoľby modelu

1. Nastavte **Časové obdobie predikcie**, aby ste zadefinovali, ako ďaleko do budúcnosti chcete predikovať CLV.    
   Štandardne je jednotka nastavená na mesiace. Môžete to zmeniť na roky, aby ste sa v budúcnosti pozerali ďalej.

   > [!TIP]
   > Ak chcete presne predpovedať CLV pre vami nastavené časové obdobie, potrebujete porovnateľné obdobie historických údajov. Napríklad ak chcete predikovať CLV nasledujúcich 12 mesiacov, odporúča sa mať k dispozícii minimálne 18 – 24 mesiacov historických údajov.

1. Uveďte, čím sú pri vašom podnikaní charakterizovaní **Aktívni zákazníci**. Nastavte časový rámec, v ktorom musí zákazník mať najmenej jednu transakciu, aby sa mohol považovať za aktívneho. Model bude predpovedať CLV iba pre aktívnych zákazníkov. 
   - **Nechajte vypočítať nákupný interval prostredníctvom modelu (odporúča sa)**: Model analyzuje vaše údaje a určuje časové obdobie na základe historických nákupov.
   - **Manuálne nastavenie intervalu**: Ak máte konkrétnu obchodnú definíciu aktívneho zákazníka, vyberte túto možnosť a podľa toho nastavte časové obdobie.

1. Definujte percentil **Zákazníka s vysokou hodnotou**, aby ste umožnili modelu poskytovať výsledky, ktoré zodpovedajú vašej obchodnej definícii.
    - **Výpočet modelu (odporúčaný)**: Model analyzuje vaše údaje a na základe histórie transakcií vašich zákazníkov určuje, čo by pre vašu firmu mohol byť zákazník s vysokou hodnotou. Model používa heuristické pravidlo (inšpirované pravidlom 80/20 alebo Paretovým princípom) na zistenie podielu zákazníkov s vysokou hodnotou. Percento zákazníkov, ktorí v historickom období prispeli k 80 % kumulatívnych výnosom pre vaše podnikanie, sa považuje za zákazníkov s vysokou hodnotou. K 80% kumulatívnych výnosov zvyčajne prispieva menej ako 30 – 40 % zákazníkov. Toto číslo sa však môže líšiť v závislosti od vášho podnikania a odvetvia.    
    - **Percento top aktívnych zákazníkov**: Definujte pre svoju firmu zákazníkov s vysokou hodnotou ako percentil top aktívnych platiacich zákazníkov. Túto možnosť môžete napríklad použiť na definovanie zákazníkov s vysokou hodnotou ako top 20 % budúcich platiacich zákazníkov.

    Ak vaša firma definuje zákazníkov s vysokou hodnotou iným spôsobom, [dajte nám o tom vedieť, radi si to vypočujeme](https://go.microsoft.com/fwlink/?linkid=2074172).

1. Stlačením tlačidla **Ďalej** môžete pokračovať nasledujúcim krokom.

### <a name="add-required-data"></a>Pridanie požadovaných údajov

1. V kroku **Požadované údaje** vyberte **Pridať údaje** pre **Históriu transakcií zákazníka** a vyberte entitu, ktorá poskytuje informácie o histórii transakcií, ako je to opísané v [predpokladoch](#prerequisites).

1. Mapujte sémantické polia na atribúty v entite histórie nákupu a vyberte **Ďalej**.

   :::image type="content" source="media/clv-add-customer-data-mapping.png" alt-text="Obrázok kroku konfigurácie na mapovanie atribútov údajov pre požadované údaje.":::
 
1. Ak polia uvedené nižšie nie sú vyplnené, nakonfigurujte vzťah medzi entitou histórie nákupov a entitou *Zákazník* a vyberte možnosť **Uložiť**.
    1. Vyberte entitu histórie transakcií.
    1. Vyberte pole, ktoré identifikuje zákazníka v entite histórie nákupov. Musí sa vzťahovať na ID primárneho zákazníka vašej entity Zákazník.
    1. Vyberte entitu, ktorá sa zhoduje s entitou primárneho zákazníka.
    1. Zadajte názov, ktoré opisuje vzťah.

      :::image type="content" source="media/clv-add-customer-data-relationship.png" alt-text="Obrázok konfiguračného kroku na definovanie vzťahu s entitou zákazníka.":::

1. Vyberte **Ďalej**.

### <a name="add-optional-data"></a>Pridať voliteľné údaje

Údaje odrážajúce kľúčové interakcie so zákazníkom (napríklad web, služby pre zákazníkov a protokoly udalostí) pridávajú do záznamov transakcií kontext. Ďalšie vzory, ktoré sa nachádzajú v dátach o aktivite zákazníka, môžu zlepšiť presnosť predikcií. 

1. V kroku **Dodatočné údaje (voliteľné)** vyberte **Pridať údaje**. Vyberte entitu aktivity zákazníka, ktorá poskytuje informácie o aktivite zákazníka, ako je opísané v [nevyhnutných podmienkach](#prerequisites).

1. Mapujte sémantické polia na atribúty v entite aktivity zákazníka a vyberte **Ďalej**.

   :::image type="content" source="media/clv-additional-data-mapping.png" alt-text="Obrázok kroku konfigurácie na mapovanie polí pre doplnkové údaje.":::

1. Vyberte typ aktivity, ktorý zodpovedá typu aktivity zákazníka, ktorú pridávate. Vyberte si z existujúcich typov aktivít alebo pridajte nový typ aktivity.

1. Nakonfigurujte vzťah medzi entitou aktivity zákazníkov a entitou *Zákazník*.
    
    1. Vyberte pole, ktoré identifikuje zákazníka v tabuľke aktivity zákazníkov. Môže to priamo súvisieť s primárnym ID zákazníka vašej entity *Zákazník*.
    1. Vyberte entitu *Zákazník*, ktorá sa zhoduje s vašou primárnou entitou *Zákazník*.
    1. Zadajte názov, ktoré opisuje vzťah.

   :::image type="content" source="media/clv-additional-data.png" alt-text="Obrázok kroku v konfiguračnom postupe na pridanie ďalších údajov a konfiguráciu aktivity s vyplnenými príkladmi.":::

1. Vyberte položku **Uložiť**.    
    Pridajte ďalšie údaje, ak chcete zahrnúť aj ďalšie aktivity zákazníkov.

1. Vyberte **Ďalej**.

### <a name="set-update-schedule"></a>Nastavenie plánu aktualizácie

1. V kroku **Plán aktualizácie údajov** vyberte frekvenciu preškolenia modelu na základe najnovších údajov. Toto nastavenie je dôležité na aktualizáciu presnosti predpovedí pri prijímaní nových údajov do Customer Insights. Väčšina firiem môže preškoľovať raz mesačne a získať dobrú presnosť pre svoju predikciu.

1. Vyberte **Ďalej**.

### <a name="review-and-run-the-model-configuration"></a>Skontrolujte a spustite konfiguráciu modelu

1. V kroku **Kontrola podrobností o modeli** overte konfiguráciu predikcie. Výberom položky **Upraviť** pod zobrazenou hodnotu sa môžete vrátiť späť do ktorejkoľvek časti konfigurácie predikcie. Krok konfigurácie môžete zvoliť aj z indikátora priebehu.

1. Ak sú všetky hodnoty správne nakonfigurované, zvoľte **Uložiť a spustiť** na spustenie modelu. Na karte **Moje predikcie** sa zobrazuje stav procesu predikcie. Proces môže trvať niekoľko hodín, v závislosti od množstva údajov použitých v predikcii.

## <a name="review-prediction-status-and-results"></a>Kontrola stavu a výsledkov predikcie

### <a name="review-prediction-status"></a>Kontrola stavu predikcie

1.  Prejdite do ponuky **Analýza** > **Predikcie** a vyberte kartu **Moje predikcie**.
2.  Vyberte predikciu, ktorú chcete skontrolovať.

- **Názov predikcie**: Názov predikcie zadaný pri jej vytváraní.
- **Typ predikcie**: Typ modelu použitého pre predikciu
- **Výstupná entita**: Názov entity, do ktorej sa má uložiť výstup predikcie. Prejdite do **Údaje** > **Entity** a nájdite entitu s týmto názvom.
- **Predpovedané pole**: Toto pole je vyplnené iba pre niektoré typy predikcií a nepoužíva sa v predikcii hodnoty životnosti zákazníka.
- **Stav**: Stav spustenia predikcie.
    - **Vo fronte**: Predikcia čaká na dokončenie ďalších procesov.
    - **Obnovuje sa**: Predikcia momentálne beží, aby vytvárala výsledky, ktoré budú prúdiť do výstupnej entity.
    - **Zlyhanie**: Spustenie predikcie zlyhalo. Viac informácií získate [kontrolou záznamov](manage-predictions.md#troubleshoot-a-failed-prediction).
    - **Úspech**: Predikcia prebehla úspešne. Vyberte **Zobraziť** pod zvislými troma bodkami, aby ste skontrolovali výsledky predikcie.
- **Upravené**: Dátum zmeny konfigurácie pre predikciu sa zmenil.
- **Posledná aktualizácia**: Dátum obnovenia výsledkov predikcie vo výstupnej entite.

### <a name="review-prediction-results"></a>Výsledky stavu predikcie

1. Prejdite do ponuky **Analýza** > **Predikcie** a vyberte kartu **Moje predikcie**.

1. Vyberte predikciu, pre ktorú chcete skontrolovať výsledky.

Na stránke s výsledkami sú tri základné sekcie údajov.

- **Výkon tréningového modelu**: A, B alebo C sú možné klasifikácie. Táto klasifikácia označuje výkon predikcie a môže vám pomôcť pri rozhodovaní o použití výsledkov uložených vo výstupnej entite. Vyberte **Ďalšie informácie o tomto skóre**, ak chcete lepšie pochopiť základné metriky výkonu modelu a ako sa odvodil konečný stupeň klasifikácie modelu.
  
  :::image type="content" source="media/clv-model-score.png" alt-text="Obrázok informačného poľa skóre modelu s klasifikáciou A.":::

  Pomocou definície zákazníkov s vysokou hodnotou, ktorú ste zadali pri konfigurácii predikcie, systém vyhodnotí, aký výkon dosiahol model AI pri predikovaní zákazníkov s vysokou hodnotou v porovnaní so základným modelom.    

  Klasifikácie sa určujú na základe nasledujúcich pravidiel:
  - **A** Keď model presne predikoval najmenej o 5 % viac zákazníkov s vysokou hodnotou v porovnaní so základným modelom.
  - **B** Keď model presne predikoval o 0 až 5 % viac zákazníkov s vysokou hodnotou v porovnaní so základným modelom.
  - **C** Keď model presne predikoval menej zákazníkov s vysokou hodnotou v porovnaní so základným modelom.

  Tabla **Hodnotenie modelu** zobrazuje ďalšie podrobnosti o výkone modelu AI a základnom modeli. Základný model využíva prístup, ktorý nie je založený na umelej inteligencii, na výpočet hodnoty životnosti zákazníka predovšetkým na základe historických nákupov uskutočnených zákazníkmi.     
  Štandardný vzorec použitý na výpočet CLV podľa základného modelu:    

  _**CLV pre každého zákazníka** = Priemerný mesačný nákup uskutočnený zákazníkom v aktívnom okne pre zákazníka * Počet mesiacov v období CLV predikcie * Celková miera udržania všetkých zákazníkov*_

  Model AI sa porovnáva so základným modelom na základe dvoch metrík výkonu modelu.
  
  - **Miera úspešnosti pri predikovaní zákazníkov s vysokou hodnotou**

    Pozrite sa na rozdiel v predikcii zákazníkov s vysokou hodnotou pomocou modelu AI v porovnaní so základným modelom. Napríklad 84 % miera úspešnosti znamená, že zo všetkých zákazníkov s vysokou hodnotou v tréningových údajov dokázal model AI presne zachytiť 84 %. Potom porovnáme túto úspešnosť s úspešnosťou základného modelu, aby sme mohli nahlásiť relatívnu zmenu. Táto hodnota sa používa na priradenie klasifikácie k modelu.

  - **Metriky chýb**
    
    Ďalšia metrika vám umožňuje skontrolovať celkovú výkonnosť modelu z hľadiska chyby pri predikovaní budúcich hodnôt. Na vyhodnotenie tejto chyby používame celkovú metriku strednej kvadratickej chyby (RMSE). RMSE je štandardný spôsob merania chyby modelu pri predpovedaní kvantitatívnych údajov. RMSE modelu AI sa porovnáva s RMSE základného modelu a uvádza sa relatívny rozdiel.

  Model AI uprednostňuje presné poradie zákazníkov podľa toho, akú hodnotu pre vaše podnikanie majú. Na odvodenie výslednej klasifikácie modelu sa teda používa iba úspešnosť predikcie zákazníkov s vysokou hodnotou. Metrika RMSE je citlivá na odľahlé hodnoty. V scenároch, kde máte malé percento zákazníkov s mimoriadne vysokými hodnotami nákupu, nemusí celková metrika RMSE poskytnúť úplný obraz o výkone modelu.   

- **Hodnota zákazníkov podľa percentilu**: Podľa vašej definície zákazníkov s vysokou hodnotou sú zákazníci zoskupení do skupín s nízkou a vysokou hodnotou na základe ich predikcií CLV, a zobrazení v grafe. Umiestnením kurzora myši na pruhy v histograme uvidíte počet zákazníkov v každej skupine a priemerný CLV v tejto skupine. Tieto údaje vám môžu pomôcť, ak chcete [vytvárať segmenty zákazníkov](segments.md) na základe ich predikcií CLV.

- **Najvplyvnejšie faktory**: Pri vytváraní vašej predikcie CLV sa zohľadňujú rôzne faktory na základe vstupných údajov poskytnutých modelu AI. Každý z faktorov má svoju dôležitosť vypočítanú pre agregované predikcie, ktoré model vytvára. Tieto faktory môžete použiť na overenie výsledkov svojich predikcií. Tieto faktory tiež poskytujú lepší prehľad o najvplyvnejších faktoroch, ktoré prispeli k predikcii CLV u všetkých vašich zákazníkov.

## <a name="manage-predictions"></a>Spravovanie predikcií

Je možné optimalizovať, odstraňovať problémy, obnovovať alebo mazať predikcie. V prehľade použiteľnosti vstupných údajov nájdete informácie o tom, ako urobiť predikciu rýchlejšou a spoľahlivejšou. Ďalšie informácie nájdete v článku [Spravovanie predikcií](manage-predictions.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
