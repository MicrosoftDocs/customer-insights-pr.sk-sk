---
title: Doplňte svoje predbežné údaje o predikcie
description: Použite predikcie na vyplnenie neúplných údajov o zákazníkoch.
ms.date: 11/01/2021
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-predictions
- ci-custom-models
- customerInsights
ms.openlocfilehash: 7e93670007db27d13b84d7516f56830988da083e
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 06/29/2022
ms.locfileid: "9082521"
---
# <a name="complete-your-partial-data-with-predictions-deprecated"></a>Doplňte svoje čiastočné údaje o predpovede (ukončená podpora)

> [!IMPORTANT]
> Táto funkcia bude **zastarané** ku dňu **5. novembra 2021**. Súčasné implementácie budú fungovať až do odstránenia funkcie, ale podľa pokynov nižšie nebudete môcť vytvárať nové integrácie.

Predikcie vám umožňujú ľahko vytvárať predikované hodnoty, ktoré môžu zlepšiť vaše pochopenie zákazníka. Na stránke **Inteligencia** > **Predikcie** môžete vybrať **Moje predikcie**, aby ste videli predikcie, ktoré ste nakonfigurovali v iných častiach Customer Insights, a umožňujú vám ich ďalšie prispôsobenie.

> [!NOTE]
> Túto funkciu nemôžete použiť, ak vaše prostredie používa úložisko Azure Data Lake Gen 2.
>
> Funkcia predikcii využíva automatizované prostriedky na vyhodnotenie údajov a predikcie na základe týchto údajov, a preto sa dá použiť ako metóda profilovania, pretože tento pojem je definovaný všeobecným nariadením o ochrane údajov („GDPR“). Použitie tejto funkcie zákazníkom na spracovanie údajov môže podliehať GDPR alebo iným zákonom alebo predpisom. Ste zodpovední za zabezpečenie toho, že vaše používanie služby Dynamics 365 Customer Insights vrátane predikcií bude v súlade so všetkými platnými zákonmi a nariadeniami vrátane zákonov týkajúcich sa ochrany súkromia, osobných údajov, biometrických údajov, ochrany údajov a dôvernosti komunikácií.

## <a name="prerequisites"></a>Predpoklady

Predtým ako bude vaša organizácia môcť používať funkciu predikcií, skontrolujte, či sú splnené nasledujúce predpoklady:

1. Vaša organizácia má inštanciu [vytvorenú v časti Microsoft Dataverse](/ai-builder/build-model#prerequisites) a nachádza sa v rovnakej organizácii ako služba Customer Insights.

2. Vaše prostredie Customer Insights je pripojené k vašej inštancii Dataverse.

Ďalšie informácie nájdete v téme [Vytvorenie nového prostredia](create-environment.md).

## <a name="create-a-prediction-in-the-customer-entity"></a>Vytvorenie predikcie v entite Zákazník

1. Ísť do **Údaje** > **entity**.

2. Vyberte entitu **Zákazník**.

3. V entite **Zákazník: Customer Insights** vyberte kartu **Polia**.

4. Nájdite názov atribútu, pre ktorý chcete predpovedať hodnoty, a potom vyberte ikonu **Prehľad** v stĺpci **Zhrnutie**.
   > [!div class="mx-imgBorder"]
   > ![Ikona prehľadu.](media/intelligence-overviewicon.png "Ikona prehľadu")

5. Ak existuje vysoký počet chýbajúcich hodnôt pre váš atribút, vyberte položku **Predpovedať chýbajúce hodnoty** a pokračujte v predikcii.
   > [!div class="mx-imgBorder"]
   > ![Stav prehľadu so zobrazeným tlačidlom predikcie chýbajúcich hodnôt.](media/intelligence-overviewpredictmissingvalues.png "Stav prehľadu so zobrazeným tlačidlom predikcie chýbajúcich hodnôt")

6. Uveďte **Zobrazované meno** a **Názov výstupnej entity** pre výsledky predikcie.

7. Zobrazí sa predvyplnený zoznam možností, kde môžete namapovať hodnoty na predikovanú kategóriu. V takom prípade budú vašou jedinou možnosťou kategórie 0 alebo 1, pretože mapujú na pravdivú/nepravdivú alebo binárnu povahu predikcie. V stĺpci Kategória, priraďte hodnoty polí, ktoré chcete nechať klasifikovať ako „0“ v konečnej predikcii, na „0“ a položky, ktoré by ste chceli klasifikovať ako „1“ v konečnej predikcii na „1“.
   > [!div class="mx-imgBorder"]
   > ![Príklad, ktorý zobrazuje hodnoty mapovaných hodnôt polí do kategórií.](media/intelligence-categorymapping.png "Príklad, ktorý zobrazuje hodnoty mapovaných hodnôt polí do kategórií")

8. Vyberte **Hotovo** a predikcia sa spracuje. Spracovanie bude nejaký čas trvať, v závislosti od veľkosti a zložitosti údajov. Výsledky budú k dispozícii v novej entite založenej na predikcii **Názve výstupnej entity**, ktorú ste vytvorili.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="create-a-prediction-while-creating-a-segment"></a>Vytvorenie predikcie pri vytváraní segmentu

Pri vytváraní segmentu je tiež možné predikovať chýbajúce hodnoty pre konkrétny zvolený atribút. Konkrétne, keď rýchlo vytvoríte segment založený na zjednotenej entite Zákazník alebo entite Miera_zákazníka.

V rámci tohto toku vyberiete konkrétny atribút, ktorý bude základom vášho segmentu, napríklad Spokojnosť zákazníka alebo Suma nákupu. Po vytvorení segmentu systém navrhne metódu predpovedania akýchkoľvek chýbajúcich hodnôt pre tento atribút.

1. Ísť do **Segmenty** a vyberte **Profily** dlaždica.

2. Vyberte **Pole** na vytvorenie segmentu a vyberte **Operátor** a potom **Skontrolovať**.

3. Uveďte **Názov** a **Zobrazovaný názov** pre segment.

4. Vyberte položku **Uložiť**.

5. Ak segment, ktorý ste vytvorili, obsahuje neúplné údaje v zdrojovom poli, môžete predikovať chýbajúce hodnoty.
   > [!div class="mx-imgBorder"]
   > ![Tlačidlo predikcie.](media/segments-predictoption.png "Tlačidlo predikcie")

6. Uveďte **Zobrazované meno** a **Názov výstupnej entity** pre výsledky predikcie.

7. Vyberte **Hotovo**. Vaša predikcia bude vygenerovaná čoskoro v novej entite s názvom, ktorý ste zadali pre **Názov výstupnej entity**.

## <a name="view-a-prediction"></a>Zobrazenie predikcie

1. Ísť do **Inteligencia** > **Predpovede** > **Moje predpovede**.

2. Vyberte predikciu, ktorú chcete skontrolovať.

3. Vyberte zvislú elipsu (&vellip;) v **Akcie** stĺpec a vyberte si **vyhliadka**.

4. V zobrazení predikcie sa zobrazí niekoľko údajových bodov.
   > [!div class="mx-imgBorder"]
   > ![Stránka predikcie.](media/intelligence-predictionsviewpage.png "Stránka predikcie")

   - **Hodnoty predikcie** zobrazujú mapovanie, ktoré ste vytvorili počas fázy mapovania hodnoty poľa do kategórie. Toto sú hodnoty vo vašom súbore údajov, ktoré boli mapované do konkrétnej kategórie.
   -**Top vplyvné osoby** sú faktory v rámci vášho súboru údajov, ktoré najpravdepodobnejšie ovplyvnili dôveru v predikciu, že hodnota vášho poľa bude mapovaná na konkrétnu kategóriu.
   - **Výkon** označuje, ako sa darí predikciám. Ak chcete získať viac informácií, kliknite na odkaz.
   - **Náhľad** zobrazuje ukážky súboru výstupných údajov z vašej predikcie a pravdepodobnosť alebo spoľahlivosť predikovanej hodnoty, kde 0 je neistota a 1 je istota.

## <a name="update-a-prediction"></a>Aktualizácia predikcie

1. Ísť do **Inteligencia** > **Predpovede** > **Moje predpovede**.

2. Vyberte predikciu, ktorú chcete aktualizovať, a vyberte ikonu **Aktualizovať**.

3. Predikcia bude naplánovaná na spracovanie. Čas poslednej aktualizácie sa zobrazuje v stĺpci **Aktualizované** stránky **Predikcie**.

## <a name="edit-a-prediction"></a>Úprava predikcie

Po vytvorení predikcia si môžete prispôsobiť model v AI Builder na zvýšenie efektivity vášho modelu.  

1. Ísť do **Inteligencia** > **Predpovede** > **Moje predpovede**.

2. Vyberte predikciu, ktorú chcete upraviť.

3. Vyberte zvislú elipsu (&vellip;) v **Akcie** stĺpec a vyberte si **vyhliadka**.

4. Vyberte **Prispôsobiť v AI Builder**.

5. Aktualizujte svoj model v AI Builder. [Prečítajte si viac informácií o správe modelov v nástroji AI Builder](/ai-builder/manage-model#retrain-and-republish-existing-models).

Pri ďalšom spustení predikcie sa použije aktualizovaný model, ktorý ste vytvorili.

> [!NOTE]
> Nové modely vytvorené v r AI Builder sa v Customer Insights nezobrazia, pokiaľ model nebol vytvorený na základe skúseností uvedených vyššie.

## <a name="remove-a-prediction"></a>Odstránenie predikcie

1. Ísť do **Inteligencia** > **Predpovede** > **Moje predpovede**.

2. Vyberte predikciu, ktorú chcete odstrániť.

3. Vyberte zvislú elipsu (&vellip;) v **Akcie** stĺpec a vyberte si **Odstrániť**.

4. Potvrďte vymazanie.

## <a name="troubleshooting"></a>Riešenie problémov

Ak nemôžete dokončiť proces pripojenia Dataverse kvôli chybe, môžete skúsiť dokončiť proces ručne. V procese pripájania sa môžu vyskytnúť dva známe problémy:

- Nie je nainštalované riešenie doplnku Karta zákazníka.
    1. Vykonajte pokyny podľa pokynov [nainštalujte a nakonfigurujte riešenie](customer-card-add-in.md).

- Povolenia aplikácií nie sú udelené.
    1. Prejdite do systému [https://admin.powerplatform.microsoft.com](https://admin.powerplatform.microsoft.com).
    1. Vyberte položku **Prostredia**.
    1. Vyberte zvislú elipsu (&vellip;) vedľa prostredia, do ktorého chcete pridať povolenie a vybrať ho **nastavenie**.
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


[!INCLUDE [footer-include](includes/footer-banner.md)]
