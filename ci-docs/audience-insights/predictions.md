---
title: Doplnenie čiastkových údajov pomocou predikcií
description: Použite predikcie na vyplnenie neúplných údajov o zákazníkoch.
ms.date: 05/05/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
ms.reviewer: zacook
manager: shellyha
ms.openlocfilehash: 577232c7e901dfd54a195c3e9cfac5d1f0f866e6
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268291"
---
# <a name="complete-your-partial-data-with-predictions"></a>Doplňte svoje predbežné údaje o predikcie

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Predikcie vám umožňujú ľahko vytvárať predikované hodnoty, ktoré môžu zlepšiť vaše pochopenie zákazníka. Na stránke **Analýza** > **Predikcie** môžete vybrať **Moje predikcie** a zobraziť predikcie, ktoré ste nakonfigurovali v iných častiach štatistík o cieľovej skupine, a môžete ich ďalej prispôsobovať.

> [!NOTE]
> Túto funkciu nemôžete použiť, ak vaše prostredie používa úložisko Azure Data Lake Gen 2.
>
> Funkcia predikcii využíva automatizované prostriedky na vyhodnotenie údajov a predikcie na základe týchto údajov, a preto sa dá použiť ako metóda profilovania, pretože tento pojem je definovaný všeobecným nariadením o ochrane údajov („GDPR“). Použitie tejto funkcie zákazníkom na spracovanie údajov môže podliehať GDPR alebo iným zákonom alebo predpisom. Ste zodpovední za zabezpečenie toho, že vaše používanie služby Dynamics 365 Customer Insights vrátane predikcií bude v súlade so všetkými platnými zákonmi a nariadeniami vrátane zákonov týkajúcich sa ochrany súkromia, osobných údajov, biometrických údajov, ochrany údajov a dôvernosti komunikácií.

## <a name="prerequisites"></a>Predpoklady

Predtým ako bude vaša organizácia môcť používať funkciu predikcií, skontrolujte, či sú splnené nasledujúce predpoklady:

1. Vaša organizácia má nastavenú inštanciu [v Common Data Service](https://docs.microsoft.com/ai-builder/build-model#prerequisites) a nachádza sa v rovnakej organizácii ako Customer Insights.

2. Vaše prostredie je spojené s vašou inštanciou Common Data Service.

Keď [vytvárate nové prostredie](manage-environments.md), nakonfigurujte ho v dialógovom okne **Vytvorenie prostredia** a vyberte možnosť **Pokročilé**. Ak ste už vytvorili prostredie, prejdite na jeho nastavenia a vyberte položku **Pokročilé**. V každom prípade v sekcii **Používať predikcie** zadajte adresu URL inštancie Common Data Service, ku ktorej chcete pripojiť svoje prostredie.

## <a name="create-a-prediction-in-the-customer-entity"></a>Vytvorenie predikcie v entite Zákazník

1. V prehľadoch cieľových skupín prejdite na **Údaje** > **Entity**.

2. Vyberte entitu **Zákazník**.

3. V entite **Zákazník: Customer Insights** vyberte kartu **Polia**.

4. Nájdite názov atribútu, pre ktorý chcete predpovedať hodnoty, a potom vyberte ikonu **Prehľad** v stĺpci **Zhrnutie**.
   > [!div class="mx-imgBorder"]
   > ![Ikona prehľadu](media/intelligence-overviewicon.png "Ikona prehľadu")

5. Ak existuje vysoký počet chýbajúcich hodnôt pre váš atribút, vyberte položku **Predpovedať chýbajúce hodnoty** a pokračujte v predikcii.
   > [!div class="mx-imgBorder"]
   > ![Stav prehľadu so zobrazeným tlačidlom predikcie chýbajúcich hodnôt](media/intelligence-overviewpredictmissingvalues.png "Stav prehľadu so zobrazeným tlačidlom predikcie chýbajúcich hodnôt")

6. Uveďte **Zobrazované meno** a **Názov výstupnej entity** pre výsledky predikcie.

7. Zobrazí sa predvyplnený zoznam možností, kde môžete namapovať hodnoty na predikovanú kategóriu. V takom prípade budú vašou jedinou možnosťou kategórie 0 alebo 1, pretože mapujú na pravdivú/nepravdivú alebo binárnu povahu predikcie. V stĺpci Kategória, priraďte hodnoty polí, ktoré chcete nechať klasifikovať ako „0“ v konečnej predikcii, na „0“ a položky, ktoré by ste chceli klasifikovať ako „1“ v konečnej predikcii na „1“.
   > [!div class="mx-imgBorder"]
   > ![Príklad, ktorý zobrazuje hodnoty mapovaných hodnôt polí do kategórií](media/intelligence-categorymapping.png "Príklad, ktorý zobrazuje hodnoty mapovaných hodnôt polí do kategórií")

8. Vyberte **Hotovo** a predikcia sa spracuje. Spracovanie bude nejaký čas trvať, v závislosti od veľkosti a zložitosti údajov. Výsledky budú k dispozícii v novej entite založenej na predikcii **Názve výstupnej entity**, ktorú ste vytvorili.

## <a name="create-a-prediction-while-creating-a-segment"></a>Vytvorenie predikcie pri vytváraní segmentu

Pri vytváraní segmentu je tiež možné predikovať chýbajúce hodnoty pre konkrétny zvolený atribút. Konkrétne, keď rýchlo vytvoríte segment založený na zjednotenej entite Zákazník alebo entite Miera_zákazníka.

V rámci tohto toku vyberiete konkrétny atribút, ktorý bude základom vášho segmentu, napríklad Spokojnosť zákazníka alebo Suma nákupu. Po vytvorení segmentu systém navrhne metódu predpovedania akýchkoľvek chýbajúcich hodnôt pre tento atribút.

1. V prehľadoch cieľových skupín prejdite na **Segmenty** a vyberte dlaždicu **Profily**.

2. Vyberte **Pole** na vytvorenie segmentu a vyberte **Operátor** a potom **Skontrolovať**.

3. Uveďte **Názov** a **Zobrazovaný názov** pre segment.

4. Vyberte položku **Uložiť**.

5. Ak segment, ktorý ste vytvorili, obsahuje neúplné údaje v zdrojovom poli, môžete predikovať chýbajúce hodnoty.
   > [!div class="mx-imgBorder"]
   > ![Tlačidlo predikcie](media/segments-predictoption.png "Tlačidlo predikcie")

6. Uveďte **Zobrazované meno** a **Názov výstupnej entity** pre výsledky predikcie.

7. Vyberte **Hotovo**. Vaša predikcia bude vygenerovaná čoskoro v novej entite s názvom, ktorý ste zadali pre **Názov výstupnej entity**.

## <a name="view-a-prediction"></a>Zobrazenie predikcie

1. V prehľadoch cieľových skupín prejdite na **Analýza** > **Predikcie** > **Moje predikcie**.

2. Vyberte predikciu, ktorú chcete skontrolovať.

3. Vyberte tri bodky v stĺpci **Akcie** a vyberte **Zobraziť**.

4. V zobrazení predikcie sa zobrazí niekoľko údajových bodov.
   > [!div class="mx-imgBorder"]
   > ![Stránka predikcie](media/intelligence-predictionsviewpage.png "Stránka predikcie")

   - **Hodnoty predikcie** zobrazujú mapovanie, ktoré ste vytvorili počas fázy mapovania hodnoty poľa do kategórie. Toto sú hodnoty vo vašom súbore údajov, ktoré boli mapované do konkrétnej kategórie.
   -**Top vplyvné osoby** sú faktory v rámci vášho súboru údajov, ktoré najpravdepodobnejšie ovplyvnili dôveru v predikciu, že hodnota vášho poľa bude mapovaná na konkrétnu kategóriu.
   - **Výkon** označuje, ako sa darí predikciám. Ak chcete získať viac informácií, kliknite na odkaz.
   - **Náhľad** zobrazuje ukážky súboru výstupných údajov z vašej predikcie a pravdepodobnosť alebo spoľahlivosť predikovanej hodnoty, kde 0 je neistota a 1 je istota.

## <a name="update-a-prediction"></a>Aktualizácia predikcie

1. V prehľadoch cieľových skupín prejdite na **Analýza** > **Predikcie** > **Moje predikcie**.

2. Vyberte predikciu, ktorú chcete aktualizovať, a vyberte ikonu **Aktualizovať**.

3. Predikcia bude naplánovaná na spracovanie. Čas poslednej aktualizácie sa zobrazuje v stĺpci **Aktualizované** stránky **Predikcie**.

## <a name="edit-a-prediction"></a>Úprava predikcie

Po vytvorení predikcie môžete model v nástroji AI Builder prispôsobiť tak, aby sa zvýšila jeho účinnosť.  

1. V prehľadoch cieľových skupín prejdite na **Analýza** > **Predikcie** > **Moje predikcie**.

2. Vyberte predikciu, ktorú chcete upraviť.

3. Vyberte tri bodky v stĺpci **Akcie** a vyberte **Zobraziť**.

4. Vyberte **Prispôsobiť v nástroji AI Builder**.

5. Aktualizujte svoj model v nástroji AI Builder. [Prečítajte si viac informácií o správe modelov v nástroji AI Builder](https://docs.microsoft.com/ai-builder/manage-model#retrain-and-republish-existing-models).

Pri ďalšom spustení predikcie sa použije aktualizovaný model, ktorý ste vytvorili.

> [!NOTE]
> Nové modely vytvorené v aplikácii AI Builder sa nebudú zobrazovať v štatistikách publika, pokiaľ nebol model vytvorený z vyššie uvedených prostredí.

## <a name="remove-a-prediction"></a>Odstránenie predikcie

1. V prehľadoch cieľových skupín prejdite na **Analýza** > **Predikcie** > **Moje predikcie**.

2. Vyberte predikciu, ktorú chcete odstrániť.

3. Vyberte tri bodky v stĺpci **Akcie** a vyberte **Odstrániť**.

4. Potvrďte vymazanie.

## <a name="troubleshooting"></a>Riešenie problémov

Ak nemôžete dokončiť proces pripojenia Common Data Service kvôli chybe, môžete skúsiť dokončiť proces ručne. V procese pripájania sa môžu vyskytnúť dva známe problémy:

- Nie je nainštalované riešenie doplnku Karta zákazníka.
    1. Vykonajte pokyny podľa pokynov [nainštalujte a nakonfigurujte riešenie](customer-card-add-in.md).

- Povolenia aplikácií nie sú udelené.
    1. Prejdite do systému [https://admin.powerplatform.microsoft.com](https://admin.powerplatform.microsoft.com).
    1. Vyberte položku **Prostredia**.
    1. Vyberte tri bodky vedľa prostredia, do ktorého chcete pridať povolenie, a vyberte **Nastavenia**.
    1. Rozbaľte **Používatelia + povolenia** a vyberte **Používatelia**.
    1. Vyberte možnosť **+ Nové** a zvoľte možnosť **Používateľ**.
    1. Vyberte **Používateľ aplikácie**, ak ešte nie je vybraté, zadajte nasledujúce informácie:
        - **Meno používateľa:** cihelp@microsoft.com
        - **ID aplikácie:** 38c77d00-5fcb-4cce-9d93-af4738258e3c
        - **Krstné meno:** Zákazník
        - **Priezvisko:** Insights
        - **Hlavný e-mail:** cihelp@microsoft.com
    1. Vyberte položku **Uložiť a zavrieť**.
    1. Vyberte používateľa, ktorého ste práve vytvorili.
    1. V hornej ponuke vyberte možnosť **Spravovať roly**.
    1. Vyberte **Správca systému** a potom **OK**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]