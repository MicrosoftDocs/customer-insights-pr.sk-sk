---
title: Analyzujte sentiment pre spätnú väzbu od zákazníkov (ukážka)
description: Naučte sa, ako používať model analýzy sentimentu na spätnú väzbu od zákazníkov v Dynamics 365 Customer Insights.
ms.date: 09/14/2022
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: wmelewong
ms.author: wameng
manager: shellyha
ms.openlocfilehash: 61ce9fb18efa6152dddb2e31f4fd0366a31ac2c7
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610485"
---
# <a name="analyze-sentiment-in-customer-feedback-preview"></a>Analyzujte sentiment v spätnej väzbe od zákazníkov (ukážka)

Analýza sentimentu vám umožňuje syntetizovať sentiment zákazníkov a identifikovať obchodné aspekty ako príležitosti na zlepšenie. Táto funkcia Customer Insights vám pomôže pochopiť, čo funguje dobre a čo musíte riešiť. Môže vám pomôcť riadiť obchodné akcie, ktoré umožňujú skúsenosti, ktoré vedú k vysokej spokojnosti a lojalite zákazníkov.

## <a name="overview"></a>Prehľad

Funkcia analýzy sentimentu generuje dve odvodené štatistiky na ID zákazníka. Skóre sentimentu (od -5 do 5) a zoznam príslušných obchodných aspektov (oblastí podnikania), ktoré vám spoločne pomôžu lepšie pochopiť spätnú väzbu od zákazníkov.

Táto analýza vám pomôže:
- Získajte prehľad o náladách zákazníkov voči značke alebo organizácii
- Identifikujte zákazníkov s negatívnym sentimentom, aby ste mohli zamerať svoje kampane a interakcie a optimalizovať pre vyššiu návratnosť  
- Identifikujte obchodné aspekty s problémami, na ktoré poukazujú zákazníci  
- Segmentujte zákazníkov na základe ich sentimentu a spúšťajte personalizované kampane s cieleným predajom, marketingom a podporou
- Optimalizujte obchodné operácie riešením oblastí záujmu alebo príležitostí, ktoré uviedli zákazníci
- Rozpoznajte obchodné aspekty, ktorým sa darí, a odmeňte spokojných zákazníkov prostredníctvom vernostných a propagačných programov

Model poskytuje zoznam slov, ktoré ovplyvnili rozhodnutie modelu priradiť komentárom spätnej väzby konkrétne skóre sentimentu alebo obchodný aspekt.  

Používame dve **Modely spracovania prirodzeného jazyka (NLP).** : Prvá priradí každému komentáru spätnej väzby skóre sentimentu. Druhý model spája každú spätnú väzbu so všetkými platnými obchodnými aspektmi. Modely sú trénované na verejných údajoch zo zdrojov zo sociálnych médií, maloobchodu, reštaurácií, spotrebných produktov a automobilového priemyslu.
  
Vopred definované obchodné aspekty pre model, ktoré sa majú spojiť s údajmi spätnej väzby, zahŕňajú:
- Správa kont
- Pokladňa a platba
- Zákaznícka podpora
- Vyzdvihnutie v obchode
- Preprava a prevzatie balíkov
- Predobjednávka
- Cena
- Ochrana osobných údajov a zabezpečenie
- Propagačné akcie a odmeny
- Potvrdenie a záruka
- Vrátenie, výmena a zrušenie
- Presnosť plnenia
- Kvalita webovej lokality/aplikácie

> [!NOTE]
> V súčasnosti podporujeme analýzu sentimentu iba pri spätnej väzbe zákazníkov v angličtine. V budúcnosti bude podporovaných viac jazykov. Ak sa odovzdá spätná väzba v iných jazykoch, model bude stále vracať výsledky. Tieto výsledky však nebudú presné.

## <a name="prerequisites"></a>Požiadavky

- Najmenej [Povolenia prispievateľa](permissions.md)
- [Jednotný](data-unification.md) textová spätná väzba. Vrelo vám odporúčame [nakonfigurujte entity údajov spätnej väzby ako entity aktivity sémantického typu](map-entities.md#select-primary-key-and-semantic-type-for-attributes) (Typ spätnej väzby).
- Zjednotené ID zákazníka (UCID) zo zjednotenia údajov na priradenie údajových záznamov textovej spätnej väzby k jednotlivému zákazníkovi.
- ID pripomienok
- Časová pečiatka spätnej väzby
- Text pripomienok

Customer Insights dokáže spracovať až 10 miliónov záznamov spätnej väzby pre jeden chod modelu. Model dokáže analyzovať komentáre spätnej väzby v rozsahu až 128 slov. Ak je komentár so spätnou väzbou dlhší, analýza zohľadňuje iba prvých 128 slov.

> [!NOTE]
> Je možné nakonfigurovať iba jednu entitu spätnej väzby. Ak existuje viacero entít spätnej väzby, skombinujte ich Power Query pred prijímaním údajov.

## <a name="configure-a-sentiment-analysis"></a>Nakonfigurujte analýzu sentimentu

1. Ísť do **Inteligencia** > **Predpovede**.

1. Na **Vytvorte** kartu, vyberte **Použite model** na **Analýza sentimentu zákazníkov (ukážka)** dlaždica.

1. Vyberte **Začíname**.

1. **názov** analýzu a poskytnúť **Názov výstupnej entity obchodného aspektu** a **Názov výstupnej entity skóre sentimentu**.

1. Vyberte **Ďalej**.

1. Vyberte **Pridajte údaje** pre **Spätná väzba od zákazníka**.

1. Vyberte typ sémantickej aktivity **Spätná väzba** ktorý obsahuje údaje spätnej väzby. Ak aktivita nebola nastavená, vyberte **tu** a vytvorte ho.

   :::image type="content" source="media/sentiment-add-feedback-activities.png" alt-text="Konfiguračný krok na výber aktivít spätnej väzby pre analýzu sentimentu.":::

1. Vyberte aktivity, ktoré chcete použiť pre túto analýzu sentimentu, a potom vyberte **Ďalšie**.

1. Namapujte atribúty vo svojich údajoch na atribúty modelu. 

1. Vyberte **Uložiť**.

1. Vyberte **Ďalej**. The **Skontrolujte a spustite** krok zobrazuje súhrn konfigurácie a poskytuje možnosť vykonať zmeny pred vytvorením analýzy.

1. Vyberte **Upraviť** pri ktoromkoľvek z krokov na kontrolu a vykonanie akýchkoľvek zmien.

1. Ak ste s výberom spokojní, vyberte si **Uložiť a spustiť** na spustenie modelu. Vyberte položku **Hotovo**. The **Moje predpovede** karta sa zobrazí počas vytvárania predikcia. Proces môže trvať niekoľko hodín, v závislosti od množstva údajov použitých v predikcii.

[!INCLUDE [progress-details](includes/progress-details-pane.md)]

## <a name="view-analysis-results"></a>Pozrite si výsledky analýzy

1. Ísť do **Inteligencia** > **Predpovede**.

1. V **Moje predpovede** vyberte predikcia, ktorý chcete zobraziť.

K dispozícii sú dve karty výsledkov.

### <a name="sumary-tab"></a>Karta Súhrn

Stránka s výsledkami obsahuje štyri hlavné časti údajov.

- **Priemerné skóre sentimentu** : Skóre sentimentu vám pomáha porozumieť celkovému sentimentu všetkých zákazníkov.
  - **Negatívne** (-5 > 2)
  - **Neutrálne** (-1 > 1)
  - **Pozitívny** (2 > 5)
  
  :::image type="content" source="media/overall-customer-sentiment.png" alt-text="Vizuálne znázornenie celkového sentimentu zákazníka.":::

- **Rozdelenie zákazníkov podľa skóre sentimentu** : Zákazníci sú kategorizovaní do negatívnych, neutrálnych a pozitívnych skupín na základe skóre ich sentimentu. Umiestnením kurzora myši na stĺpce v histograme zobrazíte počet zákazníkov a priemerné skóre sentimentu v každej skupine. Tieto údaje vám môžu pomôcť [vytvárať segmenty zákazníkov](prediction-based-segment.md) na základe skóre ich sentimentu.  

  :::image type="content" source="media/distribution-customer-sentiment.png" alt-text="Stĺpcový graf znázorňujúci sentiment zákazníkov v rámci troch skupín nálad.":::

- **Priemerné skóre sentimentu v priebehu času** : Nálady zákazníkov sa môžu časom meniť. Poskytujeme trendy v pocitoch vašich zákazníkov pre časový rozsah vašich údajov. Toto zobrazenie vám pomáha zmerať vplyv sezónnych akcií, uvádzania produktov na trh alebo iných časovo ohraničených zásahov na sentiment zákazníkov. Pozrite si graf výberom roku záujmu z rozbaľovacej ponuky.

  :::image type="content" source="media/sentiment-score-over-time.png" alt-text="Graf histórie so skóre sentimentu v priebehu času znázorneným ako čiara.":::

- **Sentiment naprieč obchodnými aspektmi** : Priemerný sentiment naprieč obchodnými aspektmi vám pomáha odhadnúť, ktoré aspekty vášho podnikania už uspokojujú zákazníkov alebo vyžadujú viac pozornosti. Záznamy spätnej väzby, ktoré sa nezhodujú so žiadnym z podporovaných obchodných aspektov, sú kategorizované pod **Iné**. Zoraďte údaje výberom ľubovoľného stĺpca.

  :::image type="content" source="media/sentiment-across-business-aspects.png" alt-text="Zoznam obchodných aspektov s pridruženou hodnotou sentimentu a počtom zákazníkov, ktorí to uvádzajú.":::

  Vyberte názov obchodného aspektu, aby ste videli, ako identifikuje obchodný aspekt model:

  - **Vplyvné slová** : Hlavné slová, ktoré ovplyvnili identifikáciu obchodného aspektu modelu AI v spätnej väzbe od zákazníkov.
    **Ukážte urážlivé slová** : Umožňuje vám zahrnúť urážlivé slová do zoznamu z pôvodných údajov spätnej väzby od zákazníkov. V predvolenom nastavení je vypnutá.  Maskovanie urážlivých slov je založené na modeli AI a nemusí odhaliť všetky urážlivé slová. Ak zistíte urážlivé slovo, ktoré nebolo filtrované podľa očakávania, dajte nám vedieť.

    :::image type="content" source="media/offensive-words-sentiment.png" alt-text="Zoznam vplyvných slov s prepínačom na zobrazenie alebo skrytie nevhodných slov.":::

  - **Vzorky spätnej väzby** : Skutočné záznamy spätnej väzby vo vašich údajoch. Slová sú farebne odlíšené podľa ich vplyvu na identifikáciu obchodného aspektu.

### <a name="influential-words-analysis-tab"></a>Karta Analýza vplyvných slov

Existujú tri časti dodatočných informácií, ktoré vysvetľujú, ako funguje model sentimentu.
  
- **Najlepšie slová prispievajúce k pozitívnemu sentimentu** : Hlavné slová, ktoré ovplyvnili identifikáciu pozitívneho sentimentu modelu AI v spätnej väzbe od zákazníkov.  

- **Hlavné slová, ktoré prispievajú k negatívnemu sentimentu** : Hlavné slová, ktoré ovplyvnili identifikáciu negatívneho sentimentu modelu AI v spätnej väzbe zákazníkov.

- **Vzorky spätnej väzby** : Skutočné záznamy spätnej väzby, jeden s negatívnym a druhý s pozitívnym sentimentom. Slová v záznamoch spätnej väzby sú zvýraznené podľa ich príspevku k priradenému skóre sentimentu. Slová, ktoré prispievajú k pozitívnemu skóre sentimentu, sú zvýraznené zelenou farbou. Slová, ktoré prispievajú k negatívnemu skóre, sú zvýraznené červenou farbou.
   Vyberte **Pozrieť viac** načítať viac vzoriek spätnej väzby.
  
   :::image type="content" source="media/sentiment-feedback-samples.png" alt-text="Príklady analýzy sentimentu na základe spätnej väzby od zákazníkov.":::

**Ukážte urážlivé slová** : Umožňuje vám zahrnúť urážlivé slová do zoznamu z pôvodných údajov spätnej väzby od zákazníkov. V predvolenom nastavení je vypnutá.  Maskovanie urážlivých slov je založené na modeli AI a nemusí odhaliť všetky urážlivé slová. Ak zistíte urážlivé slovo, ktoré nebolo filtrované podľa očakávania, dajte nám vedieť.

## <a name="act-on-analysis-results"></a>Zákon o výsledkoch analýzy

Ak chcete vytvoriť nové segmenty zákazníkov z výsledkov analýzy sentimentu, vyberte **Vytvorte segmenty** v hornej časti stránky s výsledkami modelu.

## <a name="potential-bias"></a>Potenciálna zaujatosť

Rovnako ako pri každej funkcii, ktorá využíva predikčnú umelú inteligenciu, môžu existovať potenciálne skreslené údaje, ktoré používate na predpovedanie nálady zákazníkov. Ak napríklad spätnú väzbu zhromažďujete iba digitálne, môže vám chýbať spätná väzba od zákazníkov, ktorí s vami primárne obchodujú osobne, čo ovplyvňuje výstup funkcie.

Keďže táto funkcia využíva automatizované prostriedky na vyhodnocovanie údajov a vytváranie predpovedí na základe týchto údajov, môže byť použitá ako metóda profilovania, keďže tento pojem je definovaný všeobecným nariadením o ochrane údajov („GDPR“). Vaše použitie tejto funkcie na spracovanie údajov môže podliehať GDPR alebo iným zákonom alebo predpisom. Ste zodpovedný za zabezpečenie toho, že používate Dynamics 365 Customer Insights, vrátane analýzy sentimentu, je v súlade so všetkými platnými zákonmi a nariadeniami, vrátane zákonov týkajúcich sa súkromia, osobných údajov, biometrických údajov, ochrany údajov a dôvernosti komunikácie.

[!INCLUDE [footer-include](includes/footer-banner.md)]

