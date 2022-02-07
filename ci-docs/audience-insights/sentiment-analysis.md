---
title: Analýza sentimentu pre spätnú väzbu od zákazníkov
description: 'Naučte sa, ako používať model analýzy sentimentu na spätnú väzbu od zákazníkov v Dynamics 365 Customer Insights.'
ms.date: 12/23/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: wmelewong
ms.author: wameng
manager: shellyha
---

# <a name="analyze-sentiment-in-customer-feedback-preview"></a>Analýza sentimentu v spätnej väzbe od zákazníkov (ukážka)

Zákazníci v dnešnej dobe očakávajú vysokú kvalitu produktov, služieb a skúseností. Najmä zákazníci, ktorí zdieľajú svoju spätnú väzbu. Pre organizácie je veľmi náročné analyzovať rastúci objem údajov bez zníženia presnosti a vyšších nákladov na pracovnú silu. Dynamics 365 Customer Insights ponúka model analýzy sentimentu pre spätnú väzbu od zákazníkov, ktorý umožňuje organizáciám analyzovať ich údaje presnejšie a pri nižších nákladoch.

Analýza sentimentu vám umožňuje syntetizovať sentiment zákazníkov a identifikovať obchodné aspekty ako príležitosti na zlepšenie. Táto funkcia Customer Insights vám pomôže pochopiť, čo funguje dobre a čo musíte riešiť. Zamerajte sa na najrelevantnejšie a najvplyvnejšie oblasti podnikania, aby ste zlepšili dojem svojich zákazníkov. V konečnom dôsledku vám môže pomôcť riadiť obchodné akcie, ktoré umožňujú skúsenosti, ktoré vedú k vysokej spokojnosti a lojalite zákazníkov.

## <a name="overview"></a>Prehľad

Funkcia analýzy sentimentu generuje dve odvodené štatistiky na ID zákazníka. Skóre sentimentu (od -5 do 5) a zoznam príslušných obchodných aspektov (oblastí podnikania) vám spoločne pomôžu lepšie pochopiť spätnú väzbu od zákazníkov. 

Tieto informácie vám môžu pomôcť dosiahnuť nasledujúce výsledky: 
- Získajte prehľad o náladách zákazníkov voči značke alebo organizácii
- Identifikujte zákazníkov s negatívnym sentimentom, aby ste mohli zamerať svoje kampane a interakcie a optimalizovať pre vyššiu návratnosť  
- Identifikujte obchodné aspekty s problémami, na ktoré poukazujú zákazníci  
- Segmentujte zákazníkov na základe ich sentimentu a spúšťajte personalizované kampane s cieleným predajom, marketingom a podporou
- Optimalizujte obchodné operácie riešením oblastí záujmu alebo príležitostí, ktoré uviedli zákazníci
- Rozpoznajte obchodné aspekty, ktorým sa darí, a odmeňte spokojných zákazníkov prostredníctvom vernostných a propagačných programov

Aby ste sa uistili, že výsledkom modelov môžete dôverovať, poskytujeme transparentné informácie o tom, ako sa modely rozhodujú. Dostanete zoznam slov, ktoré ovplyvnili rozhodnutie modelov priradiť komentárom spätnej väzby konkrétne skóre sentimentu alebo obchodný aspekt.  

Používame dve **Modely spracovania prirodzeného jazyka (NLP).** : Prvá priradí každému komentáru spätnej väzby skóre sentimentu. Druhý model spája každú spätnú väzbu so všetkými platnými obchodnými aspektmi. Modely sú trénované na verejných údajoch zo zdrojov zo sociálnych médií, maloobchodu, reštaurácií, spotrebných produktov a automobilového priemyslu.    
  
Vopred definované obchodné aspekty pre model, ktoré sa majú spojiť s údajmi spätnej väzby, zahŕňajú:
-   Správa kont
-   Pokladňa a platba
-   Zákaznícka podpora
-   Vyzdvihnutie v obchode
-   Preprava a prevzatie balíkov
-   Predobjednávka
-   Cena
-   Ochrana osobných údajov a zabezpečenie
-   Propagačné akcie a odmeny
-   Príjem a záruka
-   Vrátenie, výmena a zrušenie
-   Presnosť plnenia
-   Kvalita webovej lokality/aplikácie

> [!NOTE]
> V súčasnosti podporujeme len analýzu sentimentu na základe spätnej väzby od zákazníkov v angličtine. V budúcnosti bude podporovaných viac jazykov. Ak odošlete spätnú väzbu v iných jazykoch, model bude stále vracať výsledky. Tieto výsledky však nebudú presné. 

## <a name="prerequisites"></a>Požiadavky

Analýza sentimentu je založená na údajoch textovej spätnej väzby, ktoré prešli [proces zjednotenia údajov](data-unification.md). Vrelo vám odporúčame [nakonfigurujte svoje entity údajov spätnej väzby ako entity aktivity sémantického typu](map-entities.md#select-primary-key-and-semantic-type-for-attributes) (Typ spätnej väzby) vopred. 

Na konfiguráciu modelu analýzy sentimentu potrebujete min [Povolenia prispievateľa](permissions.md).

Customer Insights dokáže spracovať až 10 miliónov záznamov spätnej väzby pre jeden chod modelu. Model dokáže analyzovať komentáre spätnej väzby v rozsahu až 128 slov. Ak je komentár so spätnou väzbou dlhší, analýza zohľadňuje iba prvých 128 slov.

### <a name="data-requirements"></a>Požiadavky na údaje
  
Vyžadujú sa nasledujúce atribúty údajov:
- Zjednotené ID zákazníka (UCID) na priradenie dátových záznamov textovej spätnej väzby k jednotlivým zákazníkom. Toto ID je výsledkom [proces zjednotenia údajov](data-unification.md).
- ID pripomienok
- Časová pečiatka spätnej väzby
- Text pripomienok   

> [!TIP]
> Analýza sentimentu vyžaduje textovú spätnú väzbu vašich zákazníkov. Momentálne je možné nakonfigurovať iba jednu entitu spätnej väzby. Ak existuje viacero entít spätnej väzby, môžete ich spojiť Power Query pred začatím prijímania údajov.

## <a name="configure-a-sentiment-analysis"></a>Nakonfigurujte analýzu sentimentu 

1. V Customer Insights prejdite na stránku **Analýza** > **Predikcie**.

1. Na **Analýza sentimentu zákazníkov** dlaždice, vyberte **Použite model**.

1. V **Analýza sentimentu zákazníkov (ukážka)** panel, vyberte **Začať**.

1. V **Meno modela** krok, poskytnúť a **názov** pre vašu analýzu. 

1. Poskytnite **Názov výstupnej entity obchodného aspektu** a **Názov výstupnej entity skóre sentimentu** a potom vyberte **Ďalšie**.

1. V **Požadované údaje** krok, vyberte **Pridajte údaje**.

   :::image type="content" source="media/sentiment-add-data.png" alt-text="Pridajte tok údajov do modelu analýzy sentimentu.":::

1. V **Pridajte údaje** vyberte sémantický typ **Spätná väzba** zo zoznamu.

   :::image type="content" source="media/sentiment-add-feedback-activities.png" alt-text="Konfiguračný krok na výber aktivít spätnej väzby pre analýzu sentimentu.":::

1. Vyberte aktivity, ktoré chcete použiť pre túto analýzu sentimentu, a potom vyberte **Ďalšie**.
 
1. Namapujte atribúty vo svojich údajoch na atribúty modelu. Vyberte **Uložiť** aby ste použili svoj výber. 

1. Vidíte stav mapovania údajov. Na pokračovanie zvoľte možnosť **Ďalej**. 

1. V **Skontrolujte podrobnosti o svojom modeli** krok, potvrďte konfiguráciu analýzy vášho sentimentu. Môžete sa vrátiť do ktorejkoľvek časti konfigurácie predikcia. Vyberte **Uložiť a spustiť** na spustenie analýzy. 

   :::image type="content" source="media/sentiment-model-review-config.png" alt-text="Krok kontroly pre model sentimentu zobrazujúci všetky nakonfigurované položky.":::

1. Vyberte **hotový** aby ste opustili konfiguračný zážitok. Proces môže trvať niekoľko hodín v závislosti od množstva použitých údajov. 

## <a name="review-analysis-status"></a>Skontrolujte stav analýzy

1.  Prejdite do ponuky **Analýza** > **Predikcie** a vyberte kartu **Moje predikcie**.
2.  Vyberte predikciu, ktorú chcete skontrolovať.
- **Názov predikcie**: Názov predikcie zadaný pri jej vytváraní.
- **predikcia typ** : Typ modelu použitého pre predikcia.
- **Výstupná entita**: Názov entity, do ktorej sa má uložiť výstup predikcie. Prejdite do **Údaje** > **Entity** a nájdite entitu s týmto názvom.
- **Predpovedané pole**: Toto pole je vyplnené iba pre niektoré typy predikcií a nepoužíva sa v predikcii hodnoty životnosti zákazníka.
- **Stav**: Stav spustenia predikcie.
  - **Vo fronte**: Predikcia čaká na dokončenie ďalších procesov.
  - **Obnovuje sa**: Predikcia momentálne beží, aby vytvárala výsledky, ktoré budú prúdiť do výstupnej entity.
  - **Zlyhanie**: Spustenie predikcie zlyhalo. Viac informácií získate kontrolou záznamov.
  - **Úspech**: Predikcia prebehla úspešne. Vyberte Zobraziť pod zvislými troma bodkami, aby ste skontrolovali výsledky predikcie.
- **Upravené**: Dátum zmeny konfigurácie pre predikciu sa zmenil.
- **Naposledy obnovené** : Dátum obnovenia výsledkov predikcia vo výstupnej entite.

## <a name="manage-sentiment-analysis"></a>Spravujte analýzu sentimentu

Predpovede môžete optimalizovať, odstraňovať problémy, obnovovať ich alebo odstraňovať. V prehľade použiteľnosti vstupných údajov nájdete informácie o tom, ako urobiť predikciu rýchlejšou a spoľahlivejšou. Ďalšie informácie nájdete v článku [Spravovanie predikcií](manage-predictions.md).

## <a name="review-analysis-results"></a>Skontrolujte výsledky analýzy
 
1. Prejdite do ponuky **Analýza** > **Predikcie** a vyberte kartu **Moje predikcie**. 
1. Vyberte názov predikcia, ktorého výsledky chcete skontrolovať. V tomto prípade vyberte analýzu sentimentu, ktorú chcete skontrolovať. 

### <a name="summary-tab"></a>Karta súhrnu

Stránka s výsledkami obsahuje štyri hlavné časti údajov. 

- **Priemerné skóre sentimentu** : Pomáha vám porozumieť celkovému sentimentu všetkých zákazníkov. Skóre sentimentu sú zoskupené do troch kategórií: 
  1.    Negatívne (-5 > 2)
  2.    Neutrálny (-1 > 1)
  3.    Pozitívne (2 > 5) 
  
  :::image type="content" source="media/overall-customer-sentiment.png" alt-text="Vizuálne znázornenie celkového sentimentu zákazníka.":::

- **Rozdelenie zákazníkov podľa skóre sentimentu** : Zákazníci sú kategorizovaní do negatívnych, neutrálnych a pozitívnych skupín na základe skóre ich sentimentu. Umiestnením kurzora myši na stĺpce v histograme zobrazíte počet zákazníkov a priemerné skóre sentimentu v každej skupine. Tieto údaje vám môžu pomôcť [vytvárať segmenty zákazníkov](segments.md) na základe skóre ich sentimentu.  

  :::image type="content" source="media/distribution-customer-sentiment.png" alt-text="Stĺpcový graf znázorňujúci sentiment zákazníkov v rámci troch skupín nálad.":::

- **Priemerné skóre sentimentu v priebehu času** : Nálady zákazníkov sa môžu časom meniť. Poskytujeme trendy v pocitoch vašich zákazníkov pre časový rozsah vašich údajov. Toto zobrazenie vám môže pomôcť zmerať vplyv sezónnych akcií, uvádzania produktov na trh alebo iných časovo ohraničených zásahov na sentiment zákazníkov. Pozrite si graf výberom roku záujmu z rozbaľovacej ponuky. 

  :::image type="content" source="media/sentiment-score-over-time.png" alt-text="Graf histórie so skóre sentimentu v priebehu času znázorneným ako čiara.":::
 
- **Sentiment naprieč obchodnými aspektmi** : Táto tabuľka uvádza priemerný sentiment v rámci obchodných aspektov. Môže vám pomôcť zmerať, ktoré aspekty vášho podnikania už uspokojujú zákazníkov alebo aspekty, ktoré si vyžadujú viac pozornosti. Záznamy spätnej väzby, ktoré sa nezhodujú so žiadnym z podporovaných obchodných aspektov, sú kategorizované pod **Iné**. Tabuľka je štandardne zoradená podľa abecedy. Triedenie môžete upraviť výberom hlavičky tabuľky.

  :::image type="content" source="media/sentiment-across-business-aspects.png" alt-text="Zoznam obchodných aspektov s pridruženou hodnotou sentimentu a počtom zákazníkov, ktorí to uvádzajú.":::
 
  Výberom názvu obchodného aspektu zobrazíte ďalšie informácie o tom, ako model identifikuje obchodný aspekt. V tomto paneli sú dve časti: 

  - **Vplyvné slová** : Zobrazuje hlavné slová, ktoré ovplyvnili identifikáciu obchodného aspektu modelu AI v spätnej väzbe od zákazníkov. 
    **Ukážte urážlivé slová** : Umožňuje vám zahrnúť urážlivé slová do zoznamu z pôvodných údajov spätnej väzby od zákazníkov. V predvolenom nastavení je vypnutá.  Maskovanie urážlivých slov je založené na modeli AI a nemusí odhaliť všetky urážlivé slová. Pokračujeme v iterácii a trénovaní klasifikátora pre optimálny výkon. Ak nájdete urážlivé slovo, ktoré nebolo filtrované podľa očakávania, dajte nám vedieť. 
    
    :::image type="content" source="media/offensive-words-sentiment.png" alt-text="Zoznam vplyvných slov s prepínačom na zobrazenie alebo skrytie nevhodných slov.":::
 
  - **Vzorky spätnej väzby** : Zobrazuje skutočné záznamy spätnej väzby vo vašich údajoch. Slová sú farebne odlíšené podľa ich vplyvu na identifikáciu obchodného aspektu. 


### <a name="influential-words-analysis-tab"></a>Karta Analýza vplyvných slov

Existujú tri časti dodatočných informácií, ktoré vysvetľujú, ako funguje model sentimentu.
  
1. **Najlepšie slová prispievajúce k pozitívnemu sentimentu** : Zobrazuje najdôležitejšie slová, ktoré ovplyvnili identifikáciu pozitívneho sentimentu modelu AI v spätnej väzbe od zákazníkov.  
2. **Hlavné slová, ktoré prispievajú k negatívnemu sentimentu** : Zobrazuje najdôležitejšie slová, ktoré ovplyvnili identifikáciu negatívneho sentimentu modelu AI v spätnej väzbe zákazníkov.  
3. **Vzorky spätnej väzby** : Zobrazuje aktuálne záznamy spätnej väzby, jeden s negatívnym a druhý s pozitívnym sentimentom. Slová v záznamoch spätnej väzby sú zvýraznené podľa ich príspevku k priradenému skóre sentimentu. Slová, ktoré prispievajú k pozitívnemu skóre sentimentu, sú zvýraznené zelenou farbou. Slová, ktoré prispievajú k negatívnemu skóre, sú zvýraznené červenou farbou.
   Vyberte **Pozrieť viac** načítať viac vzoriek spätnej väzby, ktoré poskytujú viac informácií a kontextu o tom, ako funguje model sentimentu.
   
   :::image type="content" source="media/sentiment-feedback-samples.png" alt-text="Príklady analýzy sentimentu na základe spätnej väzby od zákazníkov.":::
 
**Ukážte urážlivé slová** : Umožňuje vám zahrnúť urážlivé slová do zoznamu z pôvodných údajov spätnej väzby od zákazníkov. V predvolenom nastavení je vypnutá.  Maskovanie urážlivých slov je založené na modeli AI a nemusí odhaliť všetky urážlivé slová. Pokračujeme v iterácii a trénovaní klasifikátora pre optimálny výkon. Ak nájdete urážlivé slovo, ktoré nebolo filtrované podľa očakávania, dajte nám vedieť. 

## <a name="act-on-analysis-results"></a>Zákon o výsledkoch analýzy

Môžete jednoducho začať vytvárať nové segmenty zákazníkov zo stránky s výsledkami analýzy sentimentu výberom **Vytvorte segmenty** v hornej časti stránky s výsledkami modelu.

:::image type="content" source="media/create-segment-model.png" alt-text="Panel príkazov s možnosťami na modeloch predikcia.":::
 
## <a name="potential-bias"></a>Potenciálna zaujatosť

Ako pri každej funkcii, ktorá využíva prediktívnu umelú inteligenciu, mali by ste si byť vedomí potenciálnej skreslenia údajov, ktoré používate na predpovedanie sentimentu zákazníkov. Ak napríklad zbierate spätnú väzbu iba digitálne, môže vám chýbať spätná väzba od zákazníkov, ktorí s vami primárne obchodujú osobne, čo by mohlo ovplyvniť výstup funkcie.

Keďže táto funkcia využíva automatizované prostriedky na vyhodnocovanie údajov a vytváranie predpovedí na základe týchto údajov, môže sa použiť ako metóda profilovania, ako je tento pojem definovaný vo všeobecnom nariadení o ochrane údajov (ďalej len „GDPR“). Vaše použitie tejto funkcie na spracovanie údajov môže podliehať GDPR alebo iným zákonom alebo predpisom. Ste zodpovední za zabezpečenie toho, že používate Dynamics 365 Customer Insights, vrátane analýzy sentimentu, je v súlade so všetkými platnými zákonmi a nariadeniami, vrátane zákonov týkajúcich sa súkromia, osobných údajov, biometrických údajov, ochrany údajov a dôvernosti komunikácie.

[!INCLUDE[footer-include](../includes/footer-banner.md)]

