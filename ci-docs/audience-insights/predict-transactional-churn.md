---
title: Predikcia odchodov založená na transakciách
description: Predikujte, či bude zákazník ohrozený, keď prestane nakupovať produkty alebo služby vašej spoločnosti.
ms.date: 11/12/2020
ms.reviewer: zacook
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: af461d290c69687fb47bacfcff446a0c62978383
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268337"
---
# <a name="transactional-churn-prediction-preview"></a>Predikcia odchodov založená na transakciách (ukážka)

Predikcia odchodov založená na transakciách pomáha predvídať, že zákazník v danom časovom období nebude kupovať vaše produkty alebo služby. Môžete vytvoriť nové predikcie odchodov v časti **Analýza** > **Predikcie**. Vyberte **Moje predikcie**, aby ste videli ďalšie predikcie, ktoré ste vytvorili.

> [!TIP]
> Vyskúšajte kurz pre predikciu odchodov založenú na transakciách pomocou vzorových údajov: [Predikcia odchodov založená na transakciách (ukážka) – vzorový sprievodca](sample-guide-predict-transactional-churn.md).

## <a name="prerequisites"></a>Predpoklady

- Minimálne [povolenia prispievateľa](permissions.md) v Customer Insights.
- Obchodné znalosti, aby ste pochopili, čo znamená pre vaše podnikanie riziko straty predplatného. Podporujeme definície odchodov založených na čase, čo znamená, že zákazník sa považuje za odídeného po určitom období bez nákupu.
- Údaje o vašich transakciách/nákupoch a ich histórii:
    - Identifikátory transakcií na odlíšenie nákupov/transakcií.
    - Identifikátory zákazníkov, aby sa transakcie spojili s vašimi zákazníkmi.
    - Dátumy transakčných udalostí, ktoré určujú dátumy, ku ktorým došlo k transakcii.
    - Schéma sémantických údajov pre nákupy/transakcie vyžaduje nasledujúce informácie:
        - **ID transakcie:** Jedinečný identifikátor nákupu alebo transakcie.
        - **Dátum transakcie:** Dátum nákupu alebo transakcie.
        - **Hodnota transakcie:** Mena/číselná hodnota čiastky transakcie/položky.
        - (Voliteľné) **Jedinečné ID produktu:** ID zakúpeného produktu alebo služby, ak sú vaše údaje na úrovni riadkovej položky.
        - (Voliteľné) **Či bola táto transakcia návratom:** Pole pravda/nepravda, ktoré identifikuje, či transakcia bola návratom alebo nie. Ak je **Hodnota transakcie** negatívna, tieto informácie použijeme tiež na odvodenie návratu.
- (Nepovinné) Údaje o aktivitách zákazníka:
    - Identifikátory aktivity na rozlíšenie aktivít rovnakého typu.
    - Identifikátory zákazníka na mapovanie aktivít vašich zákazníkov.
    - Informácie o činnosti obsahujúce názov a dátum aktivity.
    - Schéma sémantických údajov pre aktivity zákazníka obsahuje:
        - **Primárny kľúč:** Jedinečný identifikátor aktivity. Napríklad návšteva webu alebo záznam o použití, ktorý ukazuje, že zákazník vyskúšal vzorku vášho produktu.
        - **Časová značka:** Dátum a čas udalosti identifikovaný primárnym kľúčom.
        - **Udalosť:** Názov skupiny udalosti, ktorú chcete použiť. Napríklad pole s názvom „UserAction“ v obchode s potravinami môže byť kupónom, ktorý zákazník použije.
        - **Podrobnosti:** Podrobné informácie o udalosti. Hodnota poľa kupónu môže byť napríklad pole s názvom „CouponValue“ v obchode s potravinami.

## <a name="create-a-transactional-churn-prediction"></a>Vytvorenie predikcie odchodov založenej na transakciách

1. V Customer Insights prejdite na stránku **Analýza** > **Predikcie**.

1. Vyberte ikonu **Model odchodu zákazníkov (ukážka)** a vyberte **Použiť tento model**.
   
1. Na table **Model odchodu zákazníkov** vyberte **Transakčný** a vyberte **Začať**.

:::image type="content" source="media/select-transaction-churn.PNG" alt-text="Snímka obrazovky s vybranou možnosťou transakcie na table modelu Odchod zákazníkov.":::

### <a name="name-model"></a>Názov modelu

1. Zadajte názov modelu, ktorý ho odlíši od ostatných modelov.

1. Zadajte názov výstupnej entity iba pomocou písmen a číslic, bez medzier. Toto je názov, ktorý bude používať modelová entita. 

1. Vyberte **Ďalej**.

### <a name="define-customer-churn"></a>Definujte odídených zákazníkov

1. Nastavte časový interval v dňoch na predikovanie odchodu v poli **Identifikujte zákazníkov, ktorí môžu odísť v priebehu nasledujúcich:**. Napríklad predikujte riziko odchodu zákazníkov počas nasledujúcich 90 dní, aby ste sa prispôsobili svojmu marketingovému úsiliu o udržanie. Predikcia rizika odchodu pre dlhšie alebo kratšie obdobie môže sťažiť riešenie faktorov vo vašom profile rizika odchodov, ale záleží to na vašich konkrétnych obchodných požiadavkách. 
   >[!TIP]
   > Môžete si vybrať **Uložiť a zavrieť** kedykoľvek a predikciu uložiť ako koncept. Draft predikcie nájdete na karte **Moje predikcie**, kde môžete pokračovať.

1. Zadajte počet dní na definovanie odchodu v poli **Zákazník sa považuje za odídeného, ak neuskutočnil žiadne nákupy v priebehu:**. Ak napríklad zákazník za posledných 30 dní neuskutočnil žiadne nákupy, môže sa považovať pre vašu firmu za odídeného. 

1. Na pokračovanie zvoľte možnosť **Ďalej**

### <a name="add-required-data"></a>Pridajte požadované údaje

1. Vyberte **Pridať údaje** pre **Históriu nákupov** a vyberte entitu, ktorá poskytuje informácie o histórii transakcií/nákupov, ako je to opísané v [predpokladoch](#prerequisites).

1. Mapujte sémantické polia na atribúty v entite histórie nákupu a vyberte **Ďalej**. Pre popis polí sa pozrite na [požiadavky](#prerequisites).

   :::image type="content" source="media/model-map-purchase-entity.PNG" alt-text="Mapujte sémantické polia entity nákupu.":::

1. Ak polia uvedené nižšie nie sú vyplnené, nakonfigurujte vzťah medzi entitou histórie nákupov a entitou Zákazník.
    1. Vyberte **entitu histórie nákupov**.
    1. Vyberte **Pole**, ktoré identifikuje zákazníka v entite histórie nákupov. Musí sa vzťahovať na ID primárneho zákazníka vašej entity Zákazník.
    1. Vyberte **Entitu zákazníka**, ktorá sa zhoduje s vašou primárnou entitou zákazníka.
    1. Zadajte názov, ktoré opisuje vzťah.

    :::image type="content" source="media/model-purchase-join.PNG" alt-text="Stránka histórie nákupov zobrazujúca vytvorenie vzťahu so zákazníkom.":::
   
1. Vyberte **Ďalej**.

1. Voliteľne vyberte **Pridať údaje** pre **Aktivity zákazníkov**. Vyberte entitu, ktorá poskytuje informácie o aktivite zákazníka, ako je opísané v nevyhnutných podmienkach.

1. Mapujte sémantické polia na atribúty v entite aktivity zákazníka a vyberte **Ďalej**. Pre popis polí sa pozrite na [požiadavky](#prerequisites).

   :::image type="content" source="media/map-transaction-data-fields.png" alt-text="Mapujte polia zákazníkov s transakčnými údajmi.":::

1. Vyberte typ aktivity, ktorý sa zhoduje s typom aktivity zákazníka, ktorú konfigurujete. Vyberte **Vytvoriť nový** a vyberte dostupný typ aktivity alebo vytvorte nový typ.

1. Budete musieť nakonfigurovať vzťah medzi vašou entitou aktivity zákazníka a entitou Zákazník.
    1. Vyberte pole, ktoré identifikuje zákazníka v tabuľke aktivity zákazníkov. Môže to priamo súvisieť s primárnym ID zákazníka vašej entity Zákazník.
    1. Vyberte entitu Zákazníka, ktorá sa zhoduje s vašou primárnou entitou Zákazník
    1. Zadajte názov, ktoré opisuje vzťah.

1. Vyberte položku **Uložiť**.

1. Ak máte v úmysle zahrnúť ďalšie aktivity zákazníkov, zopakujte kroky uvedené vyššie.

1. Vyberte **Ďalej**.

### <a name="set-schedule-and-review-configuration"></a>Nastavenie plánu a kontrola konfigurácie

1. Nastavte frekvenciu na preškolenie modelu. Toto nastavenie je dôležité na aktualizáciu presnosti predikcií pri prijímaní nových údajov. Väčšina firiem môže preškoľovať raz mesačne a získať dobrú presnosť pre svoju predikciu.

1. Vyberte **Ďalej**.

1. Skontrolujte konfiguráciu predikcie. Výberom možnosti **Upraviť** pod zobrazenou hodnotou sa môžete vrátiť k predchádzajúcim krokom. Alebo si môžete vybrať krok konfigurácie z indikátora priebehu.

1. Ak sú všetky hodnoty správne nakonfigurované, vyberte položku **Uložiť a spustiť** a začnite proces predikcie. Na karte **Moje predikcie** sa zobrazuje stav vašich predikcií. Proces môže trvať niekoľko hodín, v závislosti od množstva údajov použitých v predikcii.

## <a name="review-a-prediction-status-and-results"></a>Skontrolujte stav a výsledky predikcie

1. Prejdite do ponuky **Analýza** > **Predikcie** a vyberte kartu **Moje predikcie**.

1. Vyberte predikciu, ktorú chcete skontrolovať.
   - **Názov predikcie:** Názov predikcie zadaný pri jej vytváraní.
   - **Typ predikcie** Typ modelu použitého pre predikciu
   - **Entita Výstup:** Názov entity, do ktorej sa má uložiť výstup predikcie. Entitu s týmto názvom nájdete v časti **Údaje** > **Entity**.
   - **Predikované pole:** Toto pole je vyplnené iba pre niektoré typy predikcií a nepoužíva sa v predikcie odchodov.
   - **Stav:** Stav spustenia predikcie.
        - **Vo fronte:** Predikcia čaká na spustenie ďalších procesov.
        - **Obnovuje sa:** Predikcia momentálne beží, aby produkovala výsledky, ktoré budú prúdiť do výstupnej entity.
        - **Zlyhanie:** Spustenie predikcie zlyhalo. Viac informácií získate [kontrolou záznamov](#troubleshoot-a-failed-prediction).
        - **Úspech:** Predikcia prebehla úspešne. Vyberte **Zobrazenie** pod zvislými troma bokami na kontrolu predikcie
   - **Upravené:** Dátum zmeny konfigurácie pre predikciu sa zmenil.
   - **Posledná aktualizácia:** Dátum obnovenia výsledkov predikcie vo výstupnej entite.

1. Vyberte zvislé tri bodky vedľa predikcie, pre ktorú chcete skontrolovať výsledky, a vyberte **Zobraziť**.

   :::image type="content" source="media/model-subs-view.PNG" alt-text="Zobrazením ovládacieho prvku zobrazíte výsledky predikcie.":::   

1. Na stránke s výsledkami sú tri základné sekcie údajov:
    1. **Výkon tréningového modelu:** A, B alebo C sú možné skóre. Toto skóre označuje výkon predikcie a môže vám pomôcť pri rozhodovaní o použití výsledkov uložených vo výstupnej entite. Skóre sa určujú na základe nasledujúcich pravidiel:
         
         - **A** keď model presne predikoval najmenej 50 % celkových predikcií a keď percento presných predikcií pre zákazníkov, ktorí odišli, je väčšie ako základná miera najmenej o 10 %.
            
         - **B** keď model presne predikoval najmenej 50 % celkových predikcií a keď percento presných predikcií pre zákazníkov, ktorí odišli, je väčšie ako základná miera o hodnotu do 10 %.
            
         - **C** keď model presne predikoval menej ako 50 % celkových predikcií, alebo keď percento presných predikcií pre zákazníkov, ktorí odišli, je menej ako základná miera.
               
         - **Základná miera** použije vstup časového rozsahu predikcie pre model (napríklad jeden rok) a model vytvorí rôzne zlomky času tak, že ho bude deliť 2, kým nedosiahne jeden mesiac alebo menej. Pomocou týchto zlomkov vytvára obchodné pravidlo pre zákazníkov, ktorí si v tomto časovom rámci nenakúpili. Títo zákazníci sa považujú za odídených. Ako model základnej miery je vybrané obchodné pravidlo založené na čase s najvyššou schopnosťou predpovedať, kto pravdepodobne odíde.
            
    1. **Pravdepodobnosť straty (počet zákazníkov):** Skupiny zákazníkov na základe ich predpokladaného rizika straty. Tieto údaje vám môžu pomôcť neskôr, ak chcete vytvoriť segment zákazníkov s vysokým rizikom straty. Takéto segmenty pomáhajú pochopiť, kde by malo byť vaše obmedzenie pre členstvo v segmente.
       
    1. **Najvýznamnejšie faktory:** Pri vytváraní vašej predikcie sa zohľadňuje veľa faktorov. Každý z faktorov má svoju dôležitosť vypočítanú pre agregované predpovede, ktoré model vytvára. Tieto faktory môžete použiť na overenie výsledkov svojich predikcií. Alebo môžete tieto informácie použiť neskôr na [vytváranie segmentov](segments.md), ktoré by mohli pomôcť ovplyvniť riziko straty zákazníkov.

## <a name="troubleshoot-a-failed-prediction"></a>Riešenie problémov so zlyhaním predikcie

1. Prejdite do ponuky **Analýza** > **Predikcie** a vyberte kartu **Moje predikcie**.

1. Vyberte zvislé tri bodky vedľa predikcie, pre ktorú chcete zobraziť protokoly chýb.

1. Vyberte **Záznamy**.

1. Skontrolujte všetky chyby. Môže sa vyskytnúť niekoľko typov chýb, ktoré popisujú, ktorý stav chybu spôsobil. Napríklad chyba, že nie je dostatok údajov na presnú predikciu, sa zvyčajne vyrieši načítaním ďalších údajov do Customer Insights.

## <a name="refresh-a-prediction"></a>Obnovenie predikcie

Predikcie sa automaticky obnovujú v rovnakom [harmonogram, ako vaše údaje](system.md#schedule-tab), ako je nakonfigurované v nastaveniach. Môžete ich tiež obnoviť ručne.

1. Prejdite do ponuky **Analýza** > **Predikcie** a vyberte kartu **Moje predikcie**.

1. Vyberte zvislé tri bodky vedľa predikcie, ktorú chcete obnoviť.

1. Vyberte **Obnoviť**.

## <a name="delete-a-prediction"></a>Odstránenie predikcie

Odstránenie predikcie tiež odstráni jeho výstupnú entitu.

1. Prejdite do ponuky **Analýza** > **Predikcie** a vyberte kartu **Moje predikcie**.

1. Vyberte zvislé tri bodky vedľa predikcie, ktorú chcete odstrániť.

1. Vyberte **Odstrániť**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]