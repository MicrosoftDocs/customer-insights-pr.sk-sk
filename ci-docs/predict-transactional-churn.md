---
title: Ukončenie transakcie predikcia (obsahuje video)
description: Predikujte, či bude zákazník ohrozený, keď prestane nakupovať produkty alebo služby vašej spoločnosti.
ms.date: 09/30/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: fd8df0f0a168ddfab9e8ad3af9e1f1fc0bc1b7a2
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610531"
---
# <a name="predict-transaction-churn"></a>Predikcia úbytku transakcií

Predikcia odchodov založená na transakciách pomáha predvídať, že zákazník v danom časovom období nebude kupovať vaše produkty alebo služby.

Musíte mať obchodné znalosti, aby ste pochopili, čo znamená churn pre vaše podnikanie. Podporujeme definície odchodov založených na čase, čo znamená, že zákazník sa považuje za odídeného po určitom období bez nákupu.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWN6Eg]

V prostrediach založených na firemných obchodných vzťahoch môžeme predikovať odchody založené na transakciách pre obchodný vzťah a tiež kombináciu obchodného vzťahu a ďalšej úrovne informácií, ako je kategória produktu. Pridanie dimenzie môže napríklad pomôcť určiť, aká je pravdepodobnosť, že účet „Contoso“ prestane nakupovať kategóriu produktov „kancelárske potreby“. Okrem toho v prípade firemných obchodných vzťahov môžeme AI použiť aj na generovanie zoznamu potenciálnych dôvodov, prečo je pravdepodobné, že v prípade obchodného vzťahu dôjde k odchodu v prípade kategórie informácií sekundárnej úrovne.

> [!TIP]
> Vyskúšajte zmenu transakcie predikcia pomocou vzorových údajov: [Vzorový sprievodca vrátením transakcií predikcia](sample-guide-predict-transactional-churn.md).

## <a name="prerequisites"></a>Požiadavky

- Minimálne [povolenia prispievateľa](permissions.md).
- Minimálne 10 zákazníckych profilov, najlepšie viac ako 1 000 unikátnych zákazníkov.
- Customer Identifier, jedinečný identifikátor na priradenie transakcií k vašim zákazníkom.
- Údaje o transakciách za minimálne dvojnásobok zvoleného časového okna, ako napríklad dva až tri roky histórie transakcií. Ideálne aspoň dve transakcie na zákazníka. História transakcií musí obsahovať:
  - **ID transakcie** : Jedinečný identifikátor nákupu alebo transakcie.
  - **dátum transakcie** : Dátum nákupu alebo transakcie.
  - **Hodnota transakcie** : Mena alebo číselná hodnota sumy transakcie.
  - **Jedinečné ID produktu** : ID zakúpeného produktu alebo služby, ak sú vaše údaje na úrovni riadkovej položky.
  - **Či bola táto transakcia návratom** : Pole pravda/nepravda, ktoré identifikuje, či transakcia bola vrátená alebo nie. Ak **Hodnota transakcie** je záporná, odvodzujeme návratnosť.
- Údaje o aktivite zákazníkov:
  - Customer Identifier, jedinečný identifikátor na mapovanie aktivít vašich zákazníkov.
  - **Primárny kľúč:** Jedinečný identifikátor aktivity. Napríklad návšteva webu alebo záznam o použití, ktorý ukazuje, že zákazník vyskúšal vzorku vášho produktu.
  - **Časová značka:** Dátum a čas udalosti identifikovaný primárnym kľúčom.
  - **Udalosť:** Názov udalosti, ktorú chcete použiť. Napríklad pole s názvom „UserAction“ v obchode s potravinami môže byť kupónom, ktorý zákazník použije.
  - **Podrobnosti:** Podrobné informácie o udalosti. Hodnota poľa kupónu môže byť napríklad pole s názvom „CouponValue“ v obchode s potravinami.
- Menej ako 20 % chýbajúcich hodnôt v dátovom poli poskytnutého subjektu

Pre firemné účty (B-to-B) pridajte zákaznícke údaje zosúladené so statickými atribútmi, aby ste zabezpečili, že model bude fungovať najlepšie:
- **CustomerID:** Jedinečný identifikátor pre zákazníka.
- **Dátum vytvorenia:** Dátum prvého pridania zákazníka.
- **Štát alebo provincia:** Miesto štátu alebo provincie zákazníka.
- **Krajina:** Krajina zákazníka.
- **Priemysel:** Odvetvový typ zákazníka. Napríklad pole s názvom „Odvetvie“ u pražiča kávy môže napríklad indikovať, či bol zákazník maloobchodný.
- **Klasifikácia:** Kategorizácia zákazníka pre vašu firmu. Napríklad pole s názvom „ValueSegment“ u pražiča kávy môže byť vrstvou zákazníka na základe jeho veľkosti.

> [!NOTE]
> Pre firmy s vysokou frekvenciou nákupu zákazníkov (každých pár týždňov) sa odporúča zvoliť kratšie okno predikcie a definíciu zmeny. Pre nízku frekvenciu nákupov (každých pár mesiacov alebo raz ročne) vyberte dlhšie predikcia okno a definíciu churn.

## <a name="create-a-transaction-churn-prediction"></a>Vytvorenie predikcie odchodov založených na transakciách

1. Ísť do **Inteligencia** > **Predpovede**.

1. Na **Vytvorte** kartu, vyberte **Použite model** na **Model odchodu zákazníkov** dlaždica.

1. Vyberte **Transakcia** pre typ churn a potom **Začať**.

1. **Pomenujte tento model** a **Názov výstupnej entity**, aby ste ich odlíšili od iných modelov alebo entít.

1. Vyberte **Ďalej**.

### <a name="define-customer-churn"></a>Definujte odídených zákazníkov

Vyberte **Uložiť koncept** kedykoľvek uložiť predikcia ako koncept. Koncept predikcia sa zobrazí v **Moje predpovede** tab.

1. Nastaviť **predikcia okno**. Napríklad predikujte riziko odchodu zákazníkov počas nasledujúcich 90 dní, aby ste sa prispôsobili svojmu marketingovému úsiliu o udržanie. Predikcia rizika odchodu pre dlhšie alebo kratšie obdobie môže sťažiť riešenie faktorov vo vašom profile rizika odchodov, ale záleží to na vašich konkrétnych obchodných požiadavkách.

1. Zadajte počet dní na definovanie odchodu **Definícia odchodu** lúka. Ak napríklad zákazník neuskutočnil nákup za posledných 30 dní, môže byť považovaný za zákazníka, ktorý bol pre vašu firmu zrušený.

1. Vyberte **Ďalej**.

### <a name="add-purchase-history"></a>Pridanie histórie nákupov

1. Vyberte **Pridajte údaje** pre **História transakcií zákazníka**.

1. Vyberte typ sémantickej aktivity, **Predajné objednávky** alebo **SalesOrderLine**, ktorý obsahuje informácie o histórii transakcií. Ak aktivita nebola nastavená, vyberte **tu** a vytvorte ho.

1. Pod **Aktivity**, ak boli atribúty aktivity pri vytváraní aktivity sémanticky mapované, vyberte konkrétne atribúty alebo entitu, na ktoré sa má výpočet zamerať. Ak sémantické mapovanie nenastalo, vyberte **Upraviť** a zmapovať svoje údaje.

   :::image type="content" source="media/transaction-churn-select-activity.PNG" alt-text="Bočná tabla zobrazujúca výber daných činností v rámci sémantického typu.":::

1. Vyberte **Ďalšie** a skontrolujte atribúty požadované pre tento model.

1. Vyberte **Uložiť**.

1. Pridajte ďalšie aktivity alebo vyberte **Ďalšie**.

# <a name="individual-consumers-b-to-c"></a>[Jednotliví spotrebitelia (firma a spotrebiteľ)](#tab/b2c)

### <a name="add-additional-data-optional"></a>Pridanie ďalších údajov (voliteľné)

1. Vyberte **Pridajte údaje** pre **Zákaznícke aktivity**.

1. Vyberte typ sémantickej aktivity, ktorý obsahuje údaje, ktoré chcete použiť. Ak aktivita nebola nastavená, vyberte **tu** a vytvorte ho.

1. Pod **Aktivity**, ak boli atribúty aktivity pri vytváraní aktivity sémanticky mapované, vyberte konkrétne atribúty alebo entitu, na ktoré sa má výpočet zamerať. Ak sémantické mapovanie nenastalo, vyberte **Upraviť** a zmapovať svoje údaje.

1. Vyberte **Ďalšie** a skontrolujte atribúty požadované pre tento model.

1. Vyberte **Uložiť**.

1. Vyberte **Ďalej**

# <a name="business-accounts-b-to-b"></a>[Firemné obchodné vzťahy (firma a firma)](#tab/b2b)

### <a name="select-prediction-level"></a>Výber úrovne predikcie

Väčšina predikcií sa vytvára na úrovni zákazníkov. V niektorých situáciách to nemusí byť dostatočne podrobné na vyriešenie potrieb vašej firmy. Túto funkciu použite na predpovedanie odchodu napríklad pre pobočku zákazníka, a nie pre zákazníka ako celok.

1. Vyberte **Vyberte entitu pre sekundárnu úroveň**. Ak táto možnosť nie je k dispozícii, uistite sa, že ste vyplnili predchádzajúcu časť.

1. Rozbaľte entity, z ktorých by ste chceli vybrať sekundárnu úroveň, alebo použite pole filtra vyhľadávania na filtrovanie vybraných možností.

1. Vyberte atribút, ktorý chcete použiť ako sekundárnu úroveň, a potom vyberte **Pridať**.

1. Vyberte **Ďalej**.

> [!NOTE]
> Entity dostupné v tejto sekcii sa zobrazujú, pretože majú vzťah k entite, ktorú ste vybrali v predchádzajúcej sekcii. Ak nevidíte entitu, ktorú chcete pridať, uistite sa, že má platný vzťah v položke **Vzťahy**. Pre túto konfiguráciu sú platné iba vzťahy typu jeden k jednému alebo mnohé k jednému.

### <a name="add-additional-data-optional"></a>Pridanie ďalších údajov (voliteľné)

1. Vyberte **Pridajte údaje** pre **Zákaznícke aktivity**.

1. Vyberte typ sémantickej aktivity, ktorý obsahuje údaje, ktoré chcete použiť. Ak aktivita nebola nastavená, vyberte **tu** a vytvorte ho.

1. Pod **Aktivity**, ak boli atribúty aktivity pri vytváraní aktivity sémanticky mapované, vyberte konkrétne atribúty alebo entitu, na ktoré sa má výpočet zamerať. Ak sémantické mapovanie nenastalo, vyberte **Upraviť** a zmapovať svoje údaje.

1. Vyberte **Ďalšie** a skontrolujte atribúty požadované pre tento model.

1. Vyberte **Uložiť**.

1. Vyberte **Ďalej**

1. Voliteľne vyberte **Pridať údaje** pre **Údaje o zákazníkoch**.

1. Mapujte sémantické atribúty na polia vo vašich vlastných údajoch o zákazníkoch podľa identifikácie. Údaje v použitých poliach by sa nemali často meniť, aby bol zaistený najlepší výkon modelu. Napríklad výber poľa pre položku „Klasifikácia“, ktorá sa mení každý mesiac, bude mať iba poslednú hodnotu použitú v predikcii, aj keď sa historicky rovnaká hodnota nemusí vzťahovať na zákazníka pri vytváraní vzorov predikcie.

1. Vyberte **Ďalej**.

### <a name="provide-an-optional-list-of-benchmark-accounts"></a>Poskytnite voliteľný zoznam referenčných obchodných vzťahov

Pridajte zoznam svojich firemných zákazníkov a obchodných vzťahov, ktoré chcete použiť ako referenčné hodnoty. The [podrobnosti o týchto benchmarkových účtoch](#view-prediction-results) zahŕňajú ich skóre churn a najvplyvnejšie funkcie, ktoré ovplyvnili ich churn predikcia.

1. Vyberte **+ Pridať zákazníkov**.

1. Vyberte zákazníkov, ktorí slúžia ako referenční.

1. Vyberte **Ďalej**.

---

### <a name="set-update-schedule"></a>Nastavenie plánu aktualizácie

1. Pre **Aktualizácie údajov** krok, vyberte frekvenciu pretrénovania vášho modelu. Toto nastavenie je dôležité na aktualizáciu presnosti predpovedí pri prijímaní nových údajov do Customer Insights. Väčšina firiem môže preškoľovať raz mesačne a získať dobrú presnosť pre svoju predikciu.

1. Vyberte **Ďalej**.

### <a name="review-and-run-the-model-configuration"></a>Skontrolujte a spustite konfiguráciu modelu

The **Skontrolujte a spustite** krok zobrazuje súhrn konfigurácie a poskytuje možnosť vykonať zmeny pred vytvorením predikcia.

1. Vyberte **Upraviť** pri ktoromkoľvek z krokov na kontrolu a vykonanie akýchkoľvek zmien.

1. Ak ste s výberom spokojní, vyberte si **Uložiť a spustiť** na spustenie modelu. Vyberte položku **Hotovo**. The **Moje predpovede** karta sa zobrazí počas vytvárania predikcia. Proces môže trvať niekoľko hodín, v závislosti od množstva údajov použitých v predikcii.

[!INCLUDE [progress-details](includes/progress-details-pane.md)]

## <a name="view-prediction-results"></a>Zobraziť výsledky predikcia

1. Ísť do **Inteligencia** > **Predpovede**.

1. V **Moje predpovede** vyberte predikcia, ktorý chcete zobraziť.

# <a name="individual-consumers-b-to-c"></a>[Jednotliví spotrebitelia (firma a spotrebiteľ)](#tab/b2c)

Na stránke s výsledkami sú tri základné sekcie údajov:

[!INCLUDE [predict-transaction-results](includes/predict-transaction-results.md)]

# <a name="business-accounts-b-to-b"></a>[Firemné obchodné vzťahy (firma a firma)](#tab/b2b)

Na stránke s výsledkami sú tri základné sekcie údajov:

[!INCLUDE [predict-transaction-results](includes/predict-transaction-results.md)]

An **Analýza vplyvných vlastností** informačná stránka obsahuje štyri časti údajov:

- Na pravej table vyberte položku z **Top zákazníci** alebo **Porovnanie zákazníkov**. Oba zoznamy sú zoradené podľa klesajúcej hodnoty skóre odchodu, či už je skóre len pre zákazníka alebo kombinované skóre pre zákazníkov a sekundárnej úrovne, ako je kategória produktu. Vybraná položka určuje obsah na tejto stránke.

  - **Najvýznamnejší zákazníci**: Zoznam 10 zákazníkov, u ktorých je najvyššie riziko odchodu a najnižšie riziko odchodu na základe ich skóre odchodu.
  - **Benchmarkoví zákazníci**: Zoznam až 10 zákazníkov, ktorí boli vybratí pri konfigurácii modelu.

- **Skóre odchodu:** Na pravej table zobrazuje skóre odchodu pre vybrané položky.

- **Rozdelenie rizika odchodu:** Zobrazuje rozdelenie rizika odchodu medzi zákazníkov a percentil, v ktorom sa vybraný zákazník nachádza.

- **Hlavné funkcie zvyšujúce a znižujúce riziko odchodu:** Uvádza päť hlavných funkcií, ktoré zvýšili a znížili riziko straty pre vybratú položku v pravom paneli. Zobrazuje hodnotu funkcie pre danú položku a jej vplyv na skóre odchodu pre každú vplyvnú funkciu. Tiež je zobrazená priemerná hodnota každej funkcie v segmentoch zákazníkov s nízkym, stredným a vysokým rizikom odchodu. Pomáha lepšie kontextualizovať hodnoty najdôležitejších ovplyvňujúcich funkcií pre vybranú položku a porovnať ich so segmentmi zákazníkov s nízkym, stredným a vysokým rizikom odchodu.

  - Nízka: účty alebo kombinácie účtu a sekundárnej úrovne so skóre odchodu medzi 0 a 0,33.
  - Stredná: účty alebo kombinácie účtov a sekundárnych úrovní so skóre odchodu medzi 0,33 a 0,66.
  - Vysoká: účty alebo kombinácie účtov a sekundárnych úrovní so skóre odchodu vyšším ako 0,66.

  Keď predikujete odchod na úrovni obchodného vzťahu, všetky obchodné vzťahy sa zohľadňujú pri odvodení priemerných hodnôt funkcií pre segmenty odchodu. V prípade predikcií odchodu na sekundárnej úrovni pre každý obchodný vzťah závisí odvodenie segmentov odchodu od sekundárnej úrovne položky vybratej na bočnej table. Napríklad, ak má položka sekundárnu úroveň kategórie produktu (kancelárske potreby), potom sa pri odvodzovaní priemerných hodnôt vlastností pre segmenty vracania zohľadňujú iba položky, ktoré majú ako kategóriu produktu kancelárske potreby. Táto logika sa používa na zaistenie spravodlivého porovnania hodnôt vlastností položky s priemernými hodnotami v segmentoch s nízkym, stredným a vysokým rizikom odchodu.

  V niektorých prípadoch je priemerná hodnota segmentov nízkeho, stredného alebo vysokého rizika odchodu prázdna alebo nie je k dispozícii, pretože na základe vyššie uvedenej definície neexistujú žiadne položky, ktoré by patrili do zodpovedajúcich segmentov odchodu.

  Interpretácia hodnôt v stĺpcoch priemerná nízka, stredná a vysoká je odlišná pre kategorické prvky, ako je krajina alebo odvetvie. Keďže pojem „priemerná“ hodnota funkcie sa nevzťahuje na kategorické funkcie, hodnoty v týchto stĺpcoch predstavujú podiel zákazníkov v segmentoch s nízkou, strednou alebo vysokou mierou odchodu zákazníkov, ktorí majú rovnakú hodnotu kategorickej funkcie v porovnaní s položkou vybranou na bočnom paneli.

---

 > [!NOTE]
 > Vo výstupnej entite pre tento model *ChurnScore* ukazuje predpokladanú pravdepodobnosť miznutia a *IsChurn* je binárne označenie založené na *ChurnScore* s prahom 0,5. Ak tento predvolený prah pre váš scenár nefunguje, [vytvoriť nový segment](segments.md#create-a-segment) s vami preferovaným prahom. Nie všetci zákazníci sú nevyhnutne aktívni zákazníci. Niektoré z nich nemuseli dlho vykonávať žiadnu činnosť a na základe vašej definície churn sa už považujú za churn. Predikcia rizika odchodu pre zákazníkov, ktorí už odišli, nie je užitočná, pretože nie sú cieľovou skupinou, ktorá vás zaujíma.
>
> Ak chcete zobraziť skóre straty, prejdite na **Údaje** > **entity** a zobrazte kartu údajov pre výstupnú entitu, ktorú ste definovali pre tento model.

[!INCLUDE [footer-include](includes/footer-banner.md)]
