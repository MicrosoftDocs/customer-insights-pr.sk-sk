---
title: Ukončenie transakcie predikcia (obsahuje video)
description: Predikujte, či bude zákazník ohrozený, keď prestane nakupovať produkty alebo služby vašej spoločnosti.
ms.date: 01/13/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: e55ca8c6926fa0bda05aaf52fd799ca25f7f585f
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 04/27/2022
ms.locfileid: "8643978"
---
# <a name="transaction-churn-prediction"></a>Predikcia odchodov založená na transakciách

Predikcia odchodov založená na transakciách pomáha predvídať, že zákazník v danom časovom období nebude kupovať vaše produkty alebo služby. Môžete vytvoriť nové predikcie odchodov v časti **Analýza** > **Predikcie**. Vyberte **Moje predikcie**, aby ste videli ďalšie predikcie, ktoré ste vytvorili. 

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWN6Eg]

V prostrediach založených na firemných obchodných vzťahoch môžeme predikovať odchody založené na transakciách pre obchodný vzťah a tiež kombináciu obchodného vzťahu a ďalšej úrovne informácií, ako je kategória produktu. Pridanie dimenzie pomôže zistiť, aká je pravdepodobnosť, že obchodný vzťah „Contoso“ prestane kupovať kategóriu produktov „kancelárske potreby“. Okrem toho v prípade firemných obchodných vzťahov môžeme AI použiť aj na generovanie zoznamu potenciálnych dôvodov, prečo je pravdepodobné, že v prípade obchodného vzťahu dôjde k odchodu v prípade kategórie informácií sekundárnej úrovne.

> [!TIP]
> Vyskúšajte návod na zmenu transakcie predikcia pomocou vzorových údajov: [Vzorový sprievodca vrátením transakcií predikcia](sample-guide-predict-transactional-churn.md).

## <a name="prerequisites"></a>Požiadavky

# <a name="individual-consumers-b-to-c"></a>[Jednotliví spotrebitelia (firma a spotrebiteľ)](#tab/b2c)

- Minimálne [povolenia prispievateľa](permissions.md) v Customer Insights.
- Obchodné znalosti, aby ste pochopili, čo znamená pre vaše podnikanie riziko straty predplatného. Podporujeme definície odchodov založených na čase, čo znamená, že zákazník sa považuje za odídeného po určitom období bez nákupu.
- Údaje o vašich transakciách/nákupoch a ich histórii:
    - Identifikátory transakcií na odlíšenie nákupov/transakcií.
    - Identifikátory zákazníkov, aby sa transakcie spojili s vašimi zákazníkmi.
    - Dátumy transakčných udalostí, ktoré určujú dátumy, ku ktorým došlo k transakcii.
    - Schéma sémantických údajov pre nákupy/transakcie vyžaduje nasledujúce informácie:
        - **ID transakcie**: Jedinečný identifikátor nákupu alebo transakcie.
        - **Dátum transakcie**: Dátum nákupu alebo transakcie.
        - **Hodnota transakcie**: Mena/číselná hodnota čiastky transakcie/položky.
        - (Voliteľné) **Jedinečné ID produktu**: ID zakúpeného produktu alebo služby, ak sú vaše údaje na úrovni riadkovej položky.
        - (Voliteľné) **Či bola táto transakcia návratom**: Pole pravda/nepravda, ktoré identifikuje, či transakcia bola návratom alebo nie. Ak je **Hodnota transakcie** negatívna, tieto informácie použijeme tiež na odvodenie návratu.
- (Nepovinné) Údaje o aktivitách zákazníka:
    - Identifikátory aktivity na rozlíšenie aktivít rovnakého typu.
    - Identifikátory zákazníka na mapovanie aktivít vašich zákazníkov.
    - Informácie o činnosti obsahujúce názov a dátum aktivity.
    - Schéma sémantických údajov pre aktivity zákazníka obsahuje:
        - **Primárny kľúč:** Jedinečný identifikátor aktivity. Napríklad návšteva webu alebo záznam o použití, ktorý ukazuje, že zákazník vyskúšal vzorku vášho produktu.
        - **Časová značka:** Dátum a čas udalosti identifikovaný primárnym kľúčom.
        - **Udalosť:** Názov skupiny udalosti, ktorú chcete použiť. Napríklad pole s názvom „UserAction“ v obchode s potravinami môže byť kupónom, ktorý zákazník použije.
        - **Podrobnosti:** Podrobné informácie o udalosti. Hodnota poľa kupónu môže byť napríklad pole s názvom „CouponValue“ v obchode s potravinami.

# <a name="business-accounts-b-to-b"></a>[Firemné obchodné vzťahy (firma a firma)](#tab/b2b)

- Minimálne [povolenia prispievateľa](permissions.md) v Customer Insights.
- Obchodné znalosti, aby ste pochopili, čo znamená pre vaše podnikanie riziko straty predplatného. Podporujeme definície odchodov založených na čase, čo znamená, že zákazník sa považuje za odídeného po určitom období bez nákupu.
- Údaje o vašich transakciách/nákupoch a ich histórii:
    - Identifikátory transakcií na odlíšenie nákupov/transakcií.
    - Identifikátory zákazníkov, aby sa transakcie spojili s vašimi zákazníkmi.
    - Dátumy transakčných udalostí, ktoré určujú dátumy, ku ktorým došlo k transakcii.
    - Schéma sémantických údajov pre nákupy/transakcie vyžaduje nasledujúce informácie:
        - **ID transakcie**: Jedinečný identifikátor nákupu alebo transakcie.
        - **Dátum transakcie**: Dátum nákupu alebo transakcie.
        - **Hodnota transakcie**: Mena/číselná hodnota čiastky transakcie/položky.
        - (Voliteľné) **Jedinečné ID produktu**: ID zakúpeného produktu alebo služby, ak sú vaše údaje na úrovni riadkovej položky.
        - (Voliteľné) **Či bola táto transakcia návratom**: Pole pravda/nepravda, ktoré identifikuje, či transakcia bola návratom alebo nie. Ak je **Hodnota transakcie** negatívna, tieto informácie použijeme tiež na odvodenie návratu.
- (Nepovinné) Údaje o aktivitách zákazníka:
    - Identifikátory aktivity na rozlíšenie aktivít rovnakého typu.
    - Identifikátory zákazníka na mapovanie aktivít vašich zákazníkov.
    - Informácie o činnosti obsahujúce názov a dátum aktivity.
    - Schéma sémantických údajov pre aktivity zákazníka obsahuje:
        - **Primárny kľúč:** Jedinečný identifikátor aktivity. Napríklad návšteva webu alebo záznam o použití, ktorý ukazuje, že zákazník vyskúšal vzorku vášho produktu.
        - **Časová značka:** Dátum a čas udalosti identifikovaný primárnym kľúčom.
        - **Udalosť:** Názov skupiny udalosti, ktorú chcete použiť. Napríklad pole s názvom „UserAction“ v obchode s potravinami môže byť kupónom, ktorý zákazník použije.
        - **Podrobnosti:** Podrobné informácie o udalosti. Hodnota poľa kupónu môže byť napríklad pole s názvom „CouponValue“ v obchode s potravinami.
- (Voliteľné) Údaje o vašich zákazníkoch:
    - Tieto údaje by mali by byť zarovnané so statickejšími atribútmi, aby sa zaistilo, že model bude fungovať najlepšie.
    - Schéma sémantických údajov pre údaje o zákazníkoch obsahuje:
        - **CustomerID:** Jedinečný identifikátor zákazníka.
        - **Dátum vytvorenia:** Dátum, kedy bol zákazník pôvodne pridaný.
        - **Štát alebo provincia:** Poloha štátu alebo provincie zákazníka.
        - **Krajina:** Krajina zákazníka.
        - **Odvetvie:** Typ odvetvia zákazníka. Napríklad pole s názvom „Odvetvie“ u pražiča kávy môže napríklad indikovať, či bol zákazník maloobchodný.
        - **Klasifikácia:** Kategorizácia zákazníka pre vašu firmu. Napríklad pole s názvom „ValueSegment“ u pražiča kávy môže byť vrstvou zákazníka na základe jeho veľkosti.

---

- Navrhované charakteristiky údajov:
    - Dostatočné historické údaje: Údaje o transakcii minimálne na dvojnásobok zvoleného časového okna. Ideálne dva až tri roky histórie transakcií. 
    - Viac nákupov na zákazníka: Ideálne aspoň dve transakcie pre zákazníka.
    - Počet zákazníkov: Minimálne 10 zákazníckych profilov, najlepšie viac ako 1 000 jedinečných zákazníkov. Model zlyhá s menej ako 10 zákazníkmi a nedostatkom historických údajov.
    - Úplnosť údajov: Menej ako 20 % chýbajúcich hodnôt v údajovom poli poskytnutej entity.

> [!NOTE]
> Pre firmy s vysokou frekvenciou nákupu zákazníkov (každých pár týždňov) sa odporúča zvoliť kratšie okno predikcie a definíciu zmeny. Pre nízku frekvenciu nákupov (každých pár mesiacov alebo raz ročne) vyberte dlhšie predikcia okno a definíciu churn.

## <a name="create-a-transaction-churn-prediction"></a>Vytvorenie predikcie odchodov založených na transakciách

1. V Customer Insights prejdite na stránku **Analýza** > **Predikcie**.

1. Vyberte **Model odchodu zákazníkov** dlaždice a vyberte **Použite tento model**.

1. Na table **Model odchodu zákazníkov** vyberte **Transakcia** a vyberte **Začíname**.

:::image type="content" source="media/select-transaction-churn.PNG" alt-text="Snímka obrazovky s vybratou možnosťou transakcie na table modelu Odchod zákazníkov.":::
 
### <a name="name-model"></a>Názov modelu

1. Zadajte názov modelu, ktorý ho odlíši od ostatných modelov.

1. Zadajte názov výstupnej entity iba pomocou písmen a číslic, bez medzier. Toto je názov, ktorý bude používať modelová entita. 

1. Vyberte **Ďalej**.

### <a name="define-customer-churn"></a>Definujte odídených zákazníkov

1. Nastaviť **predikcia okno**. Napríklad predikujte riziko odchodu zákazníkov počas nasledujúcich 90 dní, aby ste sa prispôsobili svojmu marketingovému úsiliu o udržanie. Predikcia rizika odchodu pre dlhšie alebo kratšie obdobie môže sťažiť riešenie faktorov vo vašom profile rizika odchodov, ale záleží to na vašich konkrétnych obchodných požiadavkách.
   >[!TIP]
   > Môžete si vybrať **Uložiť koncept** kedykoľvek uložiť predikcia ako koncept. Draft predikcie nájdete na karte **Moje predikcie**, kde môžete pokračovať.

1. Zadajte počet dní, počas ktorých sa má definovať odchod **Definícia míňania** lúka. Ak napríklad zákazník za posledných 30 dní neuskutočnil žiadne nákupy, môže sa považovať pre vašu firmu za odídeného. 

1. Na pokračovanie zvoľte možnosť **Ďalej**.

### <a name="add-required-data"></a>Pridanie požadovaných údajov

1. Označte položku **Pridať údaje** a na bočnej tabli označte typ aktivity obsahujúci požadované údaje o histórii transakcií alebo nákupov.

1. Pod **Vyberte aktivity**, vyberte konkrétne aktivity z vybraného typu aktivity, na ktoré sa má výpočet zamerať.

   :::image type="content" source="media/transaction-churn-select-activity.PNG" alt-text="Bočná tabla zobrazujúca výber daných činností v rámci sémantického typu.":::

   Pokiaľ ste aktivitu ešte nenamapovali na sémantický typ, označte položku **Upraviť** a spravte to teraz. Budete prevedení procesom mapovania sémantických činnosti. Namapujte svoje údaje na príslušné polia vo vybranom type aktivity.

1. Namapujte atribúty sémantiky na polia, ktoré sú nutné na to, aby sa model spustil. Ak polia uvedené nižšie nie sú vyplnené, nakonfigurujte vzťah medzi entitou histórie nákupov a entitou *Zákazník*. Vyberte **Uložiť**.

1. V **Pridajte požadované údaje** krok, vyberte **Ďalšie** pokračovať, ak nechcete pridávať ďalšie aktivity.


# <a name="individual-consumers-b-to-c"></a>[Jednotliví spotrebitelia (firma a spotrebiteľ)](#tab/b2c)

### <a name="add-additional-data-optional"></a>Pridanie ďalších údajov (voliteľné)

Nakonfigurujte vzťah medzi entitou aktivity zákazníkov a entitou *Zákazník*.

1. Vyberte pole, ktoré identifikuje zákazníka v tabuľke aktivity zákazníkov. Môže to priamo súvisieť s primárnym ID zákazníka vašej entity *Zákazník*.

1. Vyberte entitu, ktorá je vašou primárnou entitou *Zákazník*.

1. Zadajte názov, ktoré opisuje vzťah.

#### <a name="customer-activities"></a>Aktivity zákazníkov

1. Voliteľne vyberte **Pridať údaje** pre **Aktivity zákazníkov**.

1. Vyberte typ sémantickej aktivity, ktorý obsahuje údaje, ktoré by ste chceli použiť, a potom vyberte jednu alebo viac aktivít v sekcii **Aktivity**.

1. Vyberte typ aktivity, ktorý sa zhoduje s typom aktivity zákazníka, ktorú konfigurujete. Vyberte **Vytvoriť nový** a vyberte dostupný typ aktivity alebo vytvorte nový typ.

1. Vyberte **Ďalej** a potom **Uložiť**.

1. Ak máte v úmysle zahrnúť ďalšie aktivity zákazníkov, zopakujte kroky uvedené vyššie.

# <a name="business-accounts-b-to-b"></a>[Firemné obchodné vzťahy (firma a firma)](#tab/b2b)

### <a name="select-prediction-level"></a>Výber úrovne predikcie

Väčšina predikcií sa vytvára na úrovni zákazníkov. V niektorých situáciách to nemusí byť dostatočne podrobné na vyriešenie potrieb vašej firmy. Túto funkciu môžete použiť na predikovanie odchodu napríklad pre pobočku zákazníka, nie pre zákazníka ako celok.

1. Ak chcete vytvoriť predikciu na podrobnejšej úrovni ako na úrovni zákazníka, vyberte **Vyberte entitu pre sekundárnu úroveň**. Ak táto možnosť nie je k dispozícii, uistite sa, že ste vyplnili predchádzajúcu časť.

1. Rozbaľte entity, z ktorých by ste chceli vybrať sekundárnu úroveň, alebo použite pole filtra vyhľadávania na filtrovanie vybraných možností.

1. Vyberte atribút, ktorý chcete použiť ako sekundárnu úroveň, a potom vyberte **Pridať**.

1. Vyberte **Ďalej**.

> [!NOTE]
> Entity dostupné v tejto sekcii sa zobrazujú, pretože majú vzťah k entite, ktorú ste vybrali v predchádzajúcej sekcii. Ak nevidíte entitu, ktorú chcete pridať, uistite sa, že má platný vzťah v položke **Vzťahy**. Pre túto konfiguráciu sú platné iba vzťahy typu jeden k jednému alebo mnohé k jednému.

### <a name="add-additional-data-optional"></a>Pridanie ďalších údajov (voliteľné)

Nakonfigurujte vzťah medzi entitou aktivity zákazníkov a entitou *Zákazník*.

1. Vyberte pole, ktoré identifikuje zákazníka v tabuľke aktivity zákazníkov. Môže to priamo súvisieť s primárnym ID zákazníka vašej entity *Zákazník*.

1. Vyberte entitu, ktorá je vašou primárnou entitou *Zákazník*.

1. Zadajte názov, ktoré opisuje vzťah.

#### <a name="customer-activities"></a>Aktivity zákazníkov

1. Voliteľne vyberte **Pridať údaje** pre **Aktivity zákazníkov**.

1. Vyberte typ sémantickej aktivity, ktorý obsahuje údaje, ktoré by ste chceli použiť, a potom vyberte jednu alebo viac aktivít v sekcii **Aktivity**.

1. Vyberte typ aktivity, ktorý sa zhoduje s typom aktivity zákazníka, ktorú konfigurujete. Vyberte **Vytvoriť nový** a vyberte dostupný typ aktivity alebo vytvorte nový typ.

1. Vyberte **Ďalej** a potom **Uložiť**.

1. Ak máte v úmysle zahrnúť ďalšie aktivity zákazníkov, zopakujte kroky uvedené vyššie.

#### <a name="customers-data"></a>Údaje o zákazníkoch

1. Voliteľne vyberte **Pridať údaje** pre **Údaje o zákazníkoch**.

1. Mapujte sémantické atribúty na polia vo vašich vlastných údajoch o zákazníkoch podľa identifikácie. Údaje v použitých poliach by sa nemali často meniť, aby bol zaistený najlepší výkon modelu. Napríklad výber poľa pre položku „Klasifikácia“, ktorá sa mení každý mesiac, bude mať iba poslednú hodnotu použitú v predikcii, aj keď sa historicky rovnaká hodnota nemusí vzťahovať na zákazníka pri vytváraní vzorov predikcie.

1. Vyberte **Ďalej**.

### <a name="provide-an-optional-list-of-benchmark-accounts"></a>Poskytnite voliteľný zoznam referenčných obchodných vzťahov

Pridajte zoznam svojich firemných zákazníkov a obchodných vzťahov, ktoré chcete použiť ako referenčné hodnoty. Dostanete [podrobnosti pre tieto referenčné obchodné vzťahy](#review-a-prediction-status-and-results) vrátane skóre ich odchodov a najvplyvnejších vlastností, ktoré ovplyvnili ich predikciu odchodov.

1. Vyberte **+ Pridať zákazníkov**.

1. Vyberte zákazníkov, ktorí slúžia ako referenční.

1. Na pokračovanie zvoľte možnosť **Ďalej**.

---

### <a name="set-schedule-and-review-configuration"></a>Nastavenie plánu a kontrola konfigurácie

1. Nastavte frekvenciu na preškolenie modelu. Toto nastavenie je dôležité na aktualizáciu presnosti predikcií pri prijímaní nových údajov. Väčšina firiem môže preškoľovať raz mesačne a získať dobrú presnosť pre svoju predikciu.

1. Vyberte **Ďalej**.

1. Skontrolujte konfiguráciu predikcie. Výberom možnosti **Upraviť** pod zobrazenou hodnotou sa môžete vrátiť k predchádzajúcim krokom. Alebo si môžete vybrať krok konfigurácie z indikátora priebehu.

1. Ak sú všetky hodnoty správne nakonfigurované, vyberte položku **Uložiť a spustiť** a začnite proces predikcie. Na karte **Moje predikcie** sa zobrazuje stav vašich predikcií. Proces môže trvať niekoľko hodín, v závislosti od množstva údajov použitých v predikcii.

## <a name="review-a-prediction-status-and-results"></a>Skontrolujte stav a výsledky predikcie

1. Prejdite do ponuky **Analýza** > **Predikcie** a vyberte kartu **Moje predikcie**.

1. Vyberte predikciu, ktorú chcete skontrolovať.
   - **Názov predikcie**: Názov predikcie zadaný pri jej vytváraní.
   - **Typ predikcie**: Typ modelu použitého pre predikciu
   - **Výstupná entita**: Názov entity, do ktorej sa má uložiť výstup predikcie. Entitu s týmto názvom nájdete v časti **Údaje** > **Entity**.
     Vo výstupnej entite *ChurnScore* je predpovedaná pravdepodobnosť churn a *IsChurn* je binárny štítok založený na *ChurnScore* s prahom 0,5. Predvolená hranica nemusí pre váš scenár fungovať. [Vytvorte nový segment](segments.md#create-a-new-segment) s vami preferovaným prahom.
     Nie všetci zákazníci sú nevyhnutne aktívni zákazníci. Niektoré z nich nemuseli dlho vykonávať žiadnu činnosť a na základe vašej definície churn sa už považujú za churn. Predikcia rizika odchodu pre zákazníkov, ktorí už odišli, nie je užitočná, pretože nie sú cieľovou skupinou, ktorá vás zaujíma.
   - **Predikované pole**: Toto pole je vyplnené iba pre niektoré typy predikcií a nepoužíva sa pri predikcii odchodov.
   - **Stav**: Stav spustenia predikcie.
        - **Vo fronte**: Predikcia čaká na spustenie ďalších procesov.
        - **Obnovuje sa**: Predikcia momentálne beží, aby produkovala výsledky, ktoré budú prúdiť do výstupnej entity.
        - **Zlyhanie**: Spustenie predikcie zlyhalo. Viac informácií získate [kontrolou záznamov](manage-predictions.md#troubleshoot-a-failed-prediction).
        - **Úspech**: Predikcia prebehla úspešne. Vyberte **Zobrazenie** pod zvislými troma bokami na kontrolu predikcie
   - **Upravené**: Dátum zmeny konfigurácie pre predikciu sa zmenil.
   - **Posledná aktualizácia**: Dátum obnovenia výsledkov predikcie vo výstupnej entite.

1. Vyberte zvislé tri bodky vedľa predikcie, pre ktorú chcete skontrolovať výsledky, a vyberte **Zobraziť**.

   :::image type="content" source="media/model-subs-view.PNG" alt-text="Zobrazením ovládacieho prvku zobrazíte výsledky predikcie.":::

# <a name="individual-consumers-b-to-c"></a>[Jednotliví spotrebitelia (firma a spotrebiteľ)](#tab/b2c)

1. Na stránke s výsledkami sú tri základné sekcie údajov:
   - **Výkon tréningového modelu**: A, B alebo C sú možné skóre. Toto skóre označuje výkon predikcie a môže vám pomôcť pri rozhodovaní o použití výsledkov uložených vo výstupnej entite. Skóre sa určujú na základe nasledujúcich pravidiel: 
        - **A** keď model presne predikoval najmenej 50 % celkových predikcií a keď percento presných predikcií pre zákazníkov, ktorí odišli, je väčšie ako základná miera najmenej o 10 %.
            
        - **B** keď model presne predikoval najmenej 50 % celkových predikcií a keď percento presných predikcií pre zákazníkov, ktorí odišli, je väčšie ako základná miera o hodnotu do 10 %.
            
        - **C** keď model presne predikoval menej ako 50 % celkových predikcií, alebo keď percento presných predikcií pre zákazníkov, ktorí odišli, je menej ako základná miera.
               
        - **Základná miera** použije vstup časového rozsahu predikcie pre model (napríklad jeden rok) a model vytvorí rôzne zlomky času tak, že ho bude deliť 2, kým nedosiahne jeden mesiac alebo menej. Pomocou týchto zlomkov vytvára obchodné pravidlo pre zákazníkov, ktorí si v tomto časovom rámci nenakúpili. Títo zákazníci sa považujú za odídených. Ako model základnej miery je vybrané obchodné pravidlo založené na čase s najvyššou schopnosťou predpovedať, kto pravdepodobne odíde.
            
    - **Pravdepodobnosť odchodu (počet zákazníkov)**: Skupiny zákazníkov na základe ich predpokladaného rizika odchodu. Tieto údaje vám môžu pomôcť neskôr, ak chcete vytvoriť segment zákazníkov s vysokým rizikom straty. Takéto segmenty pomáhajú pochopiť, kde by malo byť vaše obmedzenie pre členstvo v segmente.
       
    - **Najvýznamnejšie faktory**: Pri vytváraní vašej predikcie sa zohľadňuje veľa faktorov. Každý z faktorov má svoju dôležitosť vypočítanú pre agregované predpovede, ktoré model vytvára. Tieto faktory môžete použiť na overenie svojich výsledkov predikcie, alebo tieto informácie môžete použiť neskôr [na vytvorenie segmentov](segments.md), ktoré by mohlo pomôcť ovplyvniť riziko odchodu zákazníkov.


# <a name="business-accounts-b-to-b"></a>[Firemné obchodné vzťahy (firma a firma)](#tab/b2b)

1. Na stránke s výsledkami sú tri základné sekcie údajov:
   - **Výkon tréningového modelu**: A, B alebo C sú možné skóre. Toto skóre označuje výkon predikcie a môže vám pomôcť pri rozhodovaní o použití výsledkov uložených vo výstupnej entite. Skóre sa určujú na základe nasledujúcich pravidiel: 
        - **A** keď model presne predikoval najmenej 50 % celkových predikcií a keď percento presných predikcií pre zákazníkov, ktorí odišli, je väčšie ako základná miera najmenej o 10 %.
            
        - **B** keď model presne predikoval najmenej 50 % celkových predikcií a keď percento presných predikcií pre zákazníkov, ktorí odišli, je väčšie ako základná miera o hodnotu do 10 %.
            
        - **C** keď model presne predikoval menej ako 50 % celkových predikcií, alebo keď percento presných predikcií pre zákazníkov, ktorí odišli, je menej ako základná miera.
               
        - **Základná miera** použije vstup časového rozsahu predikcie pre model (napríklad jeden rok) a model vytvorí rôzne zlomky času tak, že ho bude deliť 2, kým nedosiahne jeden mesiac alebo menej. Pomocou týchto zlomkov vytvára obchodné pravidlo pre zákazníkov, ktorí si v tomto časovom rámci nenakúpili. Títo zákazníci sa považujú za odídených. Ako model základnej miery je vybrané obchodné pravidlo založené na čase s najvyššou schopnosťou predpovedať, kto pravdepodobne odíde.
            
    - **Pravdepodobnosť odchodu (počet zákazníkov)**: Skupiny zákazníkov na základe ich predpokladaného rizika odchodu. Tieto údaje vám môžu pomôcť neskôr, ak chcete vytvoriť segment zákazníkov s vysokým rizikom straty. Takéto segmenty pomáhajú pochopiť, kde by malo byť vaše obmedzenie pre členstvo v segmente.
       
    - **Najvýznamnejšie faktory**: Pri vytváraní vašej predikcie sa zohľadňuje veľa faktorov. Každý z faktorov má svoju dôležitosť vypočítanú pre agregované predpovede, ktoré model vytvára. Tieto faktory môžete použiť na overenie svojich výsledkov predikcie, alebo tieto informácie môžete použiť neskôr [na vytvorenie segmentov](segments.md), ktoré by mohlo pomôcť ovplyvniť riziko odchodu zákazníkov.


1. V prípade firemných obchodných vzťahov nájdete informačnú stránku **Analýza vplyvných funkcií**. Obsahuje štyri sekcie údajov:

    - Položka vybraná na pravej table určuje obsah na tejto stránke. Vyberte položku z ponuky **Najvýznamnejší zákazníci** alebo **Benchmarkoví zákazníci**. Oba zoznamy sú zoradené podľa klesajúcej hodnoty skóre odchodu, či už je skóre len pre zákazníka alebo kombinované skóre pre zákazníkov a sekundárnej úrovne, ako je kategória produktu.
        
        - **Najvýznamnejší zákazníci**: Zoznam 10 zákazníkov, u ktorých je najvyššie riziko odchodu a najnižšie riziko odchodu na základe ich skóre odchodu. 
        - **Benchmarkoví zákazníci**: Zoznam až 10 zákazníkov, ktorí boli vybratí pri konfigurácii modelu.
 
    - **Skóre odchodu:** Na pravej table zobrazuje skóre odchodu pre vybrané položky.
    
    - **Rozdelenie rizika odchodu:** Ukazuje rozdelenie rizika odchodu medzi zákazníkmi a percentil, v ktorom sa vybraný zákazník nachádza. 
    
    - **Najvýznamnejšie funkcie, ktoré zvyšujú a znižujú riziko odchodu:** Pre vybratú položku na pravej table je uvedených päť najvýznamnejších funkcií, ktoré zvýšili a znížili riziko odchodu. U každej vplyvnej funkcie nájdete hodnotu funkcie pre túto položku a jej vplyv na skóre odchodu. Tiež je zobrazená priemerná hodnota každej funkcie v segmentoch zákazníkov s nízkym, stredným a vysokým rizikom odchodu. Pomáha lepšie kontextualizovať hodnoty najdôležitejších ovplyvňujúcich funkcií pre vybranú položku a porovnať ich so segmentmi zákazníkov s nízkym, stredným a vysokým rizikom odchodu.

       - Nízke: obchodné vzťahy alebo kombinácie obchodných vzťahov a sekundárnej úrovne so skóre odchodu medzi 0 a 0,33
       - Stredné: obchodné vzťahy alebo kombinácie obchodných vzťahov a sekundárnej úrovne so skóre odchodu medzi 0,33 a 0,66
       - Vysoké: obchodné vzťahy alebo kombinácie obchodných vzťahov a sekundárnej úrovne so skóre odchodu vyšším ako 0,66
    
       Keď predikujete odchod na úrovni obchodného vzťahu, všetky obchodné vzťahy sa zohľadňujú pri odvodení priemerných hodnôt funkcií pre segmenty odchodu. V prípade predikcií odchodu na sekundárnej úrovni pre každý obchodný vzťah závisí odvodenie segmentov odchodu od sekundárnej úrovne položky vybratej na bočnej table. Ak má napríklad položka sekundárnu úroveň kategórie produktu = kancelárske potreby, potom sa pri odvodzovaní priemerných hodnôt funkcií pre segmenty odchodu zohľadňujú iba položky, ktoré majú ako kategóriu produktov kancelárske potreby. Táto logika sa používa na zaistenie spravodlivého porovnania hodnôt vlastností položky s priemernými hodnotami v segmentoch s nízkym, stredným a vysokým rizikom odchodu.

       V niektorých prípadoch je priemerná hodnota segmentov nízkeho, stredného alebo vysokého rizika odchodu prázdna alebo nie je k dispozícii, pretože na základe vyššie uvedenej definície neexistujú žiadne položky, ktoré by patrili do zodpovedajúcich segmentov odchodu.
       
       > [!NOTE]
       > Interpretácia hodnôt v stĺpcoch priemerná nízka, stredná a vysoká je odlišná pre kategorické prvky, ako je krajina alebo odvetvie. Keďže pojem „priemerná“ hodnota funkcie sa nevzťahuje na kategorické funkcie, hodnoty v týchto stĺpcoch predstavujú podiel zákazníkov v segmentoch s nízkou, strednou alebo vysokou mierou odchodu zákazníkov, ktorí majú rovnakú hodnotu kategorickej funkcie v porovnaní s položkou vybranou na bočnom paneli.

---

## <a name="manage-predictions"></a>Spravovanie predikcií

Je možné optimalizovať, odstraňovať problémy, obnovovať alebo mazať predikcie. V prehľade použiteľnosti vstupných údajov nájdete informácie o tom, ako urobiť predikciu rýchlejšou a spoľahlivejšou. Ďalšie informácie získate na stránke [Spravovanie odchodov](manage-predictions.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
