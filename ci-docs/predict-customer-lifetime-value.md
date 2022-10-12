---
title: Predikcia hodnoty životnosti zákazníka (CLV)
description: Predpovedajte potenciálny výnos pre aktívnych zákazníkov v budúcnosti.
ms.date: 09/30/2022
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
ms.openlocfilehash: f27462ac327027e50e23387ac9f75a671db9a86d
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610393"
---
# <a name="predict-customer-lifetime-value-clv"></a>Predikcia hodnoty životnosti zákazníka (CLV)

Predikujte potenciálnu hodnotu (výnos), ktorú jednotliví aktívni zákazníci prinesú do vášho podnikania v definovanom budúcom časovom období. Toto predikcia vám pomôže:

- Identifikujte zákazníkov s vysokou hodnotou a spracujte tieto poznatky.
- Vytvorte strategické segmenty zákazníkov na základe ich potenciálnej hodnoty, aby ste mohli spúšťať personalizované kampane s cieleným predajom, marketingom a podporou.
- Usmerňujte vývoj produktov zameraním sa na funkcie, ktoré zvyšujú hodnotu pre zákazníkov.
- Optimalizujte predajnú alebo marketingovú stratégiu a presnejšie prideľujte rozpočet podľa dosahu zákazníkov.
- Rozpoznajte a odmeňte zákazníkov s vysokou hodnotou prostredníctvom vernostných alebo odmeňovacích programov.

Zistite, čo znamená CLV pre vaše podnikanie. Podporujeme CLV založené na transakciách predikcia. Predpokladaná hodnota zákazníka je založená na histórii obchodných transakcií. Zvážte vytvorenie niekoľkých modelov s rôznymi vstupnými preferenciami a porovnajte výsledky modelov, aby ste zistili, ktorý modelový scenár najlepšie vyhovuje vašim obchodným potrebám.

> [!TIP]
> Vyskúšajte CLV predikcia pomocou vzorových údajov: [Celoživotná hodnota zákazníka (CLV) predikcia vzorový sprievodca](sample-guide-predict-clv.md).

## <a name="prerequisites"></a>Požiadavky

- Najmenej [Prispievateľ](permissions.md) povolenia
- Minimálne 100 unikátnych zákazníkov, najlepšie viac ako 10 000 zákazníkov
- Customer Identifier, jedinečný identifikátor na priradenie transakcií k jednotlivému zákazníkovi
- Minimálne jeden rok transakčnej histórie, najlepšie dva až tri roky. V ideálnom prípade aspoň dve až tri transakcie na ID zákazníka, najlepšie vo viacerých dátumoch. História transakcií musí obsahovať:
  - **ID transakcie**: Jedinečný identifikátor každej transakcie
  - **Dátum transakcie** : Dátum alebo časová pečiatka každej transakcie
  - **Suma transakcie**: Peňažná hodnota (napríklad výnos alebo rentabilita tržieb) každej transakcie
  - **Štítok priradený k vráteniu tovaru** : Booleovská hodnota true/false označujúca, či je transakcia vrátená
  - **identifikačné číslo produktu** : ID produktu produktu zapojeného do transakcie
- Údaje o zákazníckych aktivitách:
  - **Primárny kľúč** : Jedinečný identifikátor aktivity
  - **Časová značka** : Dátum a čas udalosti identifikovanej primárnym kľúčom
  - **Udalosť (názov aktivity)** : Názov udalosti, ktorú chcete použiť
  - **Podrobnosti (suma alebo hodnota)**: Podrobnosti o aktivite zákazníka
- Dodatočné údaje, ako napríklad:
  - Webové aktivity: História návštev webových stránok alebo história e-mailov
  - Vernostné aktivity: Pribúdanie vernostných odmeňovacích bodov a história ich spätného odkúpenia
  - Služby pre zákazníkov log: História servisných volaní, sťažností alebo vrátení
  - Informácie o profile zákazníka
- Menej ako 20 % chýbajúcich hodnôt v povinných poliach

> [!NOTE]
> Je možné nakonfigurovať iba jednu entitu histórie transakcií. Ak existuje viacero nákupných alebo transakčných entít, skombinujte ich Power Query pred prijímaním údajov.

## <a name="create-a-customer-lifetime-value-prediction"></a>Vytvorenie predikcie hodnoty životnosti zákazníka

Vyberte **Uložiť koncept** kedykoľvek uložiť predikcia ako koncept. Koncept predikcia sa zobrazí v **Moje predpovede** tab.

1. Ísť do **Inteligencia** > **Predpovede**.

1. Na **Vytvorte** kartu, vyberte **Použite model** na **Celoživotná hodnota zákazníka** dlaždica.

1. Vyberte **Začíname**.

1. **Pomenujte tento model** a **Názov výstupnej entity**, aby ste ich odlíšili od iných modelov alebo entít.

1. Vyberte **Ďalej**.

### <a name="define-model-preferences"></a>Definujte predvoľby modelu

1. Nastavte **Časové obdobie predikcie**, aby ste zadefinovali, ako ďaleko do budúcnosti chcete predikovať CLV. Štandardne je jednotka nastavená na mesiace.

   > [!TIP]
   > Na presné predpovedanie CLV pre nastavené časové obdobie je potrebné porovnateľné obdobie historických údajov. Napríklad, ak chcete predpovedať CLV na nasledujúcich 12 mesiacov, majte aspoň 18 – 24 mesiacov historických údajov.

1. Nastavte časový rámec, v ktorom musí zákazník mať najmenej jednu transakciu, aby sa mohol považovať za aktívneho. Model predpovedá iba CLV **Aktívni zákazníci**.
   - **Nechajte model vypočítať nákupný interval (odporúča sa)** : Model analyzuje vaše údaje a na základe historických nákupov určí časové obdobie.
   - **Nastavte interval manuálne** : Časové obdobie pre vašu definíciu aktívneho zákazníka.

1. Definujte percentil **Zákazník s vysokou hodnotou**.
    - **Modelový výpočet (odporúča sa)** : Model používa pravidlo 80/20. Percento zákazníkov, ktorí v historickom období prispeli k 80 % kumulatívnych výnosom pre vaše podnikanie, sa považuje za zákazníkov s vysokou hodnotou. K 80% kumulatívnych výnosov zvyčajne prispieva menej ako 30 – 40 % zákazníkov. Toto číslo sa však môže líšiť v závislosti od vášho podnikania a odvetvia.
    - **Percento najaktívnejších zákazníkov** : Špecifický percentil pre zákazníka s vysokou hodnotou. Napríklad zadajte **25** definovať zákazníkov s vysokou hodnotou ako najlepších 25 % budúcich platiacich zákazníkov.

    Ak vaša firma definuje zákazníkov s vysokou hodnotou iným spôsobom, [dajte nám o tom vedieť, radi si to vypočujeme](https://go.microsoft.com/fwlink/?linkid=2074172).

1. Vyberte **Ďalej**.

### <a name="add-required-data"></a>Pridajte požadované údaje

1. Vyberte **Pridajte údaje** pre **História transakcií zákazníka**.

1. Vyberte typ sémantickej aktivity, **Predajné objednávky** alebo **SalesOrderLine**, ktorý obsahuje históriu transakcií. Ak aktivita nebola nastavená, vyberte **tu** a vytvorte ho.

1. Pod **Aktivity**, ak boli atribúty aktivity pri vytváraní aktivity sémanticky mapované, vyberte konkrétne atribúty alebo entitu, na ktoré sa má výpočet zamerať. Ak sémantické mapovanie nenastalo, vyberte **Upraviť** a zmapovať svoje údaje.
  
   :::image type="content" source="media/CLV-add-required.PNG" alt-text="Pridajte požadované údaje pre model CLV":::

1. Vyberte **Ďalšie** a skontrolujte atribúty požadované pre tento model.

1. Vyberte **Uložiť**.

1. Pridajte ďalšie aktivity alebo vyberte **Ďalšie**.

### <a name="add-optional-activity-data"></a>Pridajte voliteľné údaje o aktivite

Údaje odrážajúce kľúčové interakcie so zákazníkom (napríklad web, služby pre zákazníkov a protokoly udalostí) pridávajú do záznamov transakcií kontext. Ďalšie vzory, ktoré sa nachádzajú v dátach o aktivite zákazníka, môžu zlepšiť presnosť predikcií.

1. Vyberte **Pridajte údaje** pod **Rozšírte informácie o modeli o ďalšie údaje o aktivite**.

1. Vyberte typ aktivity, ktorý zodpovedá typu aktivity zákazníka, ktorú pridávate. Ak aktivita nebola nastavená, vyberte **tu** a vytvorte ho.

1. Pod **Aktivity**, ak boli atribúty aktivity zmapované pri vytváraní aktivity, vyberte konkrétne atribúty alebo entitu, na ktoré sa má výpočet zamerať. Ak mapovanie neprebehlo, vyberte **Upraviť** a zmapovať svoje údaje.

1. Vyberte **Ďalšie** a skontrolujte atribúty požadované pre tento model.

1. Vyberte **Uložiť**.

1. Vyberte **Ďalej**.

1. [Pridajte voliteľné údaje o zákazníkovi](#add-optional-customer-data) alebo vyberte **Ďalšie** a prejdite na [Nastavte plán aktualizácie](#set-update-schedule).

### <a name="add-optional-customer-data"></a>Pridajte voliteľné údaje o zákazníkovi

Vyberte si z 18 bežne používaných atribútov profilu zákazníka, ktoré chcete zahrnúť ako vstup do modelu. Tieto atribúty môžu viesť k prispôsobenejším, relevantnejším a použiteľnejším výsledkom modelov pre vaše obchodné prípady použitia.

Napríklad: Contoso Coffee chce predpovedať celoživotnú hodnotu zákazníka a zacieliť na zákazníkov s vysokou hodnotou pomocou personalizovanej ponuky súvisiacej s uvedením ich nového kávovaru na espresso. Contoso používa model CLV a pridáva všetkých 18 atribútov profilu zákazníka, aby zistil, ktoré faktory ovplyvňujú ich zákazníkov s najvyššou hodnotou. Zistia, že poloha zákazníka je pre týchto zákazníkov najvplyvnejším faktorom.
Na základe týchto informácií organizujú miestne podujatie na uvedenie kávovaru na espresso a spolupracujú s miestnymi predajcami, aby im poskytli personalizované ponuky a špeciálny zážitok na podujatí. Bez týchto informácií by Contoso možno poslal iba všeobecné marketingové e-maily a premeškal príležitosť prispôsobiť sa pre tento miestny segment svojich vysokohodnotných zákazníkov.

1. Vyberte **Pridajte údaje** pod **Rozšírte informácie o modeli ešte viac pomocou dodatočných údajov o zákazníkoch**.

1. Pre **Entita**, vyberte si **Zákazník: CustomerInsights** na výber jednotného profilu zákazníka, ktorý sa mapuje na údaje atribútov zákazníka. Pre **ID zákazníka**, vyberte si **System.Customer.CustomerId**.

1. Mapujte viac polí, ak sú údaje dostupné vo vašich zjednotených zákazníckych profiloch.

   :::image type="content" source="media/clv-optional-customer-profile-mapping.png" alt-text="Príklad namapovaných polí pre údaje profilu zákazníka.":::

1. Vyberte **Uložiť**.

1. Vyberte **Ďalej**.

### <a name="set-update-schedule"></a>Nastavenie plánu aktualizácie

1. Zvoľte si frekvenciu pretrénovania svojho modelu na základe najnovších údajov. Toto nastavenie je dôležité na aktualizáciu presnosti predpovedí pri prijímaní nových údajov do Customer Insights. Väčšina firiem môže preškoľovať raz mesačne a získať dobrú presnosť pre svoju predikciu.

1. Vyberte **Ďalej**.

### <a name="review-and-run-the-model-configuration"></a>Skontrolujte a spustite konfiguráciu modelu

The **Skontrolujte a spustite** krok zobrazuje súhrn konfigurácie a poskytuje možnosť vykonať zmeny pred vytvorením predikcia.

1. Vyberte **Upraviť** pri ktoromkoľvek z krokov na kontrolu a vykonanie akýchkoľvek zmien.

1. Ak ste s výberom spokojní, vyberte si **Uložiť a spustiť** na spustenie modelu. Vyberte položku **Hotovo**. The **Moje predpovede** karta sa zobrazí počas vytvárania predikcia. Proces môže trvať niekoľko hodín, v závislosti od množstva údajov použitých v predikcii.

[!INCLUDE [progress-details](includes/progress-details-pane.md)]

## <a name="view-prediction-results"></a>Zobraziť výsledky predikcia

1. Ísť do **Inteligencia** > **Predpovede**.

1. V **Moje predpovede** vyberte predikcia, ktorý chcete zobraziť.

Na stránke s výsledkami sú tri základné sekcie údajov.

- **Výkon tréningového modelu** : Stupne A, B alebo C označujú výkon predikcia a môžu vám pomôcť pri rozhodovaní o použití výsledkov uložených vo výstupnej entite.
  
  :::image type="content" source="media/clv-model-score.png" alt-text="Obrázok informačného poľa skóre modelu s klasifikáciou A.":::

  Customer Insights hodnotí, ako sa modelu AI darilo pri predpovedaní zákazníkov s vysokou hodnotou v porovnaní so základným modelom.

  Klasifikácie sa určujú na základe nasledujúcich pravidiel:
  - **A** Keď model presne predikoval najmenej o 5 % viac zákazníkov s vysokou hodnotou v porovnaní so základným modelom.
  - **B** Keď model presne predikoval o 0 až 5 % viac zákazníkov s vysokou hodnotou v porovnaní so základným modelom.
  - **C** Keď model presne predikoval menej zákazníkov s vysokou hodnotou v porovnaní so základným modelom.
  
  Vyberte [**Prečítajte si o tomto skóre**](#learn-about-the-score) otvoriť **Hodnotenie modelu** panel, ktorý zobrazuje ďalšie podrobnosti o výkone modelu AI a základnom modeli. Pomôže vám to lepšie pochopiť základné metriky výkonnosti modelu a spôsob odvodenia konečného stupňa výkonnosti modelu. Základný model využíva prístup, ktorý nie je založený na umelej inteligencii, na výpočet hodnoty životnosti zákazníka predovšetkým na základe historických nákupov uskutočnených zákazníkmi.

- **Hodnota zákazníkov podľa percentilu** : Zákazníci s nízkou a vysokou hodnotou sa zobrazujú v grafe. Umiestnením kurzora myši na stĺpce v histograme zobrazíte počet zákazníkov v každej skupine a priemernú hodnotu CLV tejto skupiny. voliteľne [vytvárať segmenty zákazníkov](prediction-based-segment.md) na základe ich predpovedí CLV.
  
   :::image type="content" source="media/CLV-value-percent.png" alt-text="Hodnota zákazníkov podľa percentilu pre model CLV":::

- **Najvplyvnejšie faktory**: Pri vytváraní vašej predikcie CLV sa zohľadňujú rôzne faktory na základe vstupných údajov poskytnutých modelu AI. Každý z faktorov má svoju dôležitosť vypočítanú pre agregované predikcie, ktoré model vytvára. Použite tieto faktory na overenie vašich výsledkov predikcia. Tieto faktory tiež poskytujú lepší prehľad o najvplyvnejších faktoroch, ktoré prispeli k predikcii CLV u všetkých vašich zákazníkov.
  
   :::image type="content" source="media/CLV-influence-factors.png" alt-text="Najvplyvnejšie faktory pre model CLV":::

### <a name="learn-about-the-score"></a>Získajte informácie o skóre

Štandardný vzorec použitý na výpočet CLV podľa základného modelu:

 _**CLV pre každého zákazníka** = Priemerný mesačný nákup uskutočnený zákazníkom v aktívnom zákazníckom okne * Počet mesiacov v období CLV predikcia * Celková miera udržania všetkých zákazníkov_

Model AI sa porovnáva so základným modelom na základe dvoch metrík výkonu modelu.
  
- **Miera úspešnosti pri predikovaní zákazníkov s vysokou hodnotou**

  Pozrite sa na rozdiel v predikcii zákazníkov s vysokou hodnotou pomocou modelu AI v porovnaní so základným modelom. Napríklad 84 % miera úspešnosti znamená, že zo všetkých zákazníkov s vysokou hodnotou v tréningových údajov dokázal model AI presne zachytiť 84 %. Potom porovnáme túto úspešnosť s úspešnosťou základného modelu, aby sme mohli nahlásiť relatívnu zmenu. Táto hodnota sa používa na priradenie klasifikácie k modelu.

- **Metriky chýb**

  Pozrite si celkový výkon modelu z hľadiska chyby pri predpovedaní budúcich hodnôt. Na vyhodnotenie tejto chyby používame celkovú metriku strednej kvadratickej chyby (RMSE). RMSE je štandardný spôsob merania chyby modelu pri predpovedaní kvantitatívnych údajov. RMSE modelu AI sa porovnáva s RMSE základného modelu a uvádza sa relatívny rozdiel.

Model AI uprednostňuje presné poradie zákazníkov podľa toho, akú hodnotu pre vaše podnikanie majú. Na odvodenie výslednej klasifikácie modelu sa teda používa iba úspešnosť predikcie zákazníkov s vysokou hodnotou. Metrika RMSE je citlivá na odľahlé hodnoty. V scenároch, kde máte malé percento zákazníkov s mimoriadne vysokými hodnotami nákupu, nemusí celková metrika RMSE poskytnúť úplný obraz o výkone modelu.

[!INCLUDE [footer-include](includes/footer-banner.md)]
