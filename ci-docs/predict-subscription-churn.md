---
title: Predpovedať ukončenie odberu (obsahuje video)
description: Predikuje, či hrozí riziko, že zákazník prestane používať predplatené produkty alebo služby vašej spoločnosti.
ms.date: 09/30/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 7464707864c418bfcc625ddfd245622131434b33
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610255"
---
# <a name="predict-subscription-churn"></a>Predikcia straty predplatného

Predikuje, či hrozí riziko, že zákazník prestane používať predplatené produkty alebo služby vašej spoločnosti. Údaje o predplatnom zahŕňajú aktívne a neaktívne predplatné pre každého zákazníka, takže na každé ID zákazníka existuje viacero záznamov.

Musíte mať obchodné znalosti, aby ste pochopili, čo znamená churn pre vaše podnikanie. Podporujeme definície odchodu zákazníkov na základe času, čo znamená, že sa má za to, že zákazník prestal nakupovať určitý čas po skončení predplatného.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWOKNQ]

> [!TIP]
> Vyskúšajte predplatné churn predikcia pomocou vzorových údajov: [Vzorový sprievodca zrušenie odberu predikcia](sample-guide-predict-subscription-churn.md).

## <a name="prerequisites"></a>Požiadavky

- Minimálne [povolenia prispievateľa](permissions.md).
- Minimálne 10 zákazníckych profilov, najlepšie viac ako 1 000 unikátnych zákazníkov.
- Customer Identifier, jedinečný identifikátor na priradenie odberov k vašim zákazníkom.
- Údaje o predplatnom minimálne na dvojnásobok zvoleného časového okna. Najlepšie dva až tri roky predplatných údajov. História odberov musí obsahovať:
  - **ID predplatného:** Jedinečný identifikátor predplatného.
  - **Dátum ukončenia predplatného:** Dátum uplynutia platnosti predplatného pre zákazníka.
  - **Dátum začiatku predplatného:** Dátum začiatku predplatného pre zákazníka.
  - **Dátum transakcie:** Dátum zmeny odberu. Napríklad zákazník kupujúci alebo rušiaci odber.
  - **Je to opakované predplatné:** Booleovské pole true/false, ktoré určuje, či sa predplatné obnoví s rovnakým ID predplatného bez zásahu zákazníka.
  - **Frekvencia opakovania (v mesiacoch):** Pri opakujúcich sa odberoch mesiac, kedy sa odber obnoví. Napríklad ročné predplatné, ktoré sa automaticky obnovuje pre zákazníka každý rok na ďalší rok, má hodnotu 12.
  - **Suma predplatného** : Suma meny, ktorú zákazník zaplatí za obnovenie predplatného. Môže pomôcť identifikovať vzory pre rôzne úrovne predplatného.
- Aspoň dva záznamy o činnosti pre 50 % zákazníkov, pre ktorých chcete vypočítať odchod. Činnosti zákazníka musia zahŕňať:
  - **Primárny kľúč:** Jedinečný identifikátor aktivity. Napríklad návšteva webovej stránky alebo záznam o použití ukazujúci, že si zákazník pozrel epizódu televíznej show.
  - **Časová značka:** Dátum a čas udalosti identifikovaný primárnym kľúčom.
  - **Udalosť:** Názov udalosti, ktorú chcete použiť. Napríklad pole s názvom „UserAction“ v streamovanej video službe by mohlo mať hodnotu „Zobrazené“.
  - **Podrobnosti:** Podrobné informácie o udalosti. Napríklad pole s názvom „ShowTitle“ v streamovanej video službe by mohlo mať hodnotu videa, ktoré si prezeral zákazník.
- Menej ako 20 % chýbajúcich hodnôt v dátovom poli poskytnutej entity.

## <a name="create-a-subscription-churn-prediction"></a>Vytvorenie predikcia rizika straty predplatného

Vyberte **Uložiť koncept** kedykoľvek uložiť predikcia ako koncept. Koncept predikcia sa zobrazí v **Moje predpovede** tab.

1. Ísť do **Inteligencia** > **Predpovede**.

1. Na **Vytvorte** kartu, vyberte **Použite model** na **Model odchodu zákazníkov** dlaždica.

1. Vyberte **Predplatné** pre typ churn a potom **Začať**.

1. **Pomenujte tento model** a **Názov výstupnej entity**, aby ste ich odlíšili od iných modelov alebo entít.

1. Vyberte **Ďalej**.

### <a name="define-customer-churn"></a>Definujte odídených zákazníkov

1. Zadajte číslo **Dni od skončenia predplatného**, po ktorých bude vaša firma považovať zákazníka za strateného. Toto obdobie je zvyčajne spojené s obchodnými aktivitami, ako sú ponuky alebo iné marketingové snahy, ktoré sa snažia zabrániť strate zákazníka.

1. Zadajte počet **Dni na skúmanie budúcnosti, aby sa predpovedalo miznutie**. Napríklad predikujte riziko odchodu zákazníkov počas nasledujúcich 90 dní, aby ste sa prispôsobili svojmu marketingovému úsiliu o udržanie. Predpovedanie rizika churn na dlhšie alebo kratšie časové obdobia môže sťažiť riešenie faktorov vo vašom profile rizika churn, v závislosti od vašich konkrétnych obchodných požiadaviek.

1. Vyberte **Ďalej**.

### <a name="add-required-data"></a>Pridajte požadované údaje

1. Vyberte **Pridajte údaje** pre **História predplatného**.

1. Vyberte typ sémantickej aktivity **Predplatné** ktorý obsahuje požadované informácie o histórii predplatného. Ak aktivita nebola nastavená, vyberte **tu** a vytvorte ho.

1. Pod **Aktivity**, ak boli atribúty aktivity pri vytváraní aktivity sémanticky mapované, vyberte konkrétne atribúty alebo entitu, na ktoré sa má výpočet zamerať. Ak sémantické mapovanie nenastalo, vyberte **Upraviť** a zmapovať svoje údaje.
  
   :::image type="content" source="media/subscription-churn-required.png" alt-text="Pridajte požadované údaje pre model ukončenia odberu":::

1. Vyberte **Ďalšie** a skontrolujte atribúty požadované pre tento model.

1. Vyberte **Uložiť**.

1. Vyberte **Pridajte údaje** pre **Zákaznícke aktivity**.

1. Vyberte typ sémantickej aktivity, ktorý poskytuje informácie o aktivite zákazníka. Ak aktivita nebola nastavená, vyberte **tu** a vytvorte ho.

1. Pod **Aktivity**, ak boli atribúty aktivity pri vytváraní aktivity sémanticky mapované, vyberte konkrétne atribúty alebo entitu, na ktoré sa má výpočet zamerať. Ak sémantické mapovanie nenastalo, vyberte **Upraviť** a zmapovať svoje údaje.

1. Vyberte **Ďalšie** a skontrolujte atribúty požadované pre tento model.

1. Vyberte **Uložiť**.

1. Pridajte ďalšie aktivity alebo vyberte **Ďalšie**.

### <a name="set-update-schedule"></a>Nastavenie plánu aktualizácie

1. Vyberte frekvenciu preškolenia svojho modelu. Toto nastavenie je dôležité na aktualizáciu presnosti predpovedí pri prijímaní nových údajov do Customer Insights. Väčšina firiem môže preškoľovať raz mesačne a získať dobrú presnosť pre svoju predikciu.

1. Vyberte **Ďalej**.

### <a name="review-and-run-the-model-configuration"></a>Skontrolujte a spustite konfiguráciu modelu

The **Skontrolujte a spustite** krok zobrazuje súhrn konfigurácie a poskytuje možnosť vykonať zmeny pred vytvorením predikcia.

1. Vyberte **Upraviť** pri ktoromkoľvek z krokov na kontrolu a vykonanie akýchkoľvek zmien.

1. Ak ste s výberom spokojní, vyberte si **Uložiť a spustiť** na spustenie modelu. Vyberte položku **Hotovo**. The **Moje predpovede** karta sa zobrazí počas vytvárania predikcia. Proces môže trvať niekoľko hodín, v závislosti od množstva údajov použitých v predikcii.

[!INCLUDE [progress-details](includes/progress-details-pane.md)]

## <a name="view-prediction-results"></a>Zobraziť výsledky predikcia

1. Ísť do **Inteligencia** > **Predpovede**.

1. V **Moje predpovede** vyberte predikcia, ktorý chcete zobraziť.

Na stránke s výsledkami sú tri základné sekcie údajov:

- **Výkon tréningového modelu** : Stupne A, B alebo C označujú výkon predikcia a môžu vám pomôcť pri rozhodovaní o použití výsledkov uložených vo výstupnej entite.
  
  :::image type="content" source="media/subscription-churn-modelperformance.PNG" alt-text="Obrázok informačného poľa skóre modelu s klasifikáciou A.":::

  Klasifikácie sa určujú na základe nasledujúcich pravidiel:
  - **A** keď model presne predpovedal aspoň 50 % z celkových predpovedí a keď je percento presných predpovedí pre zákazníkov, ktorí odišli, vyššie ako historická priemerná miera odchodu aspoň o 10 %.
  - **B** keď model presne predpovedal aspoň 50 % celkových predpovedí a keď je percento presných predpovedí pre zákazníkov, ktorí odišli, až o 10 % vyššie ako historická priemerná miera odchodu.
  - **C** keď model presne predpovedal menej ako 50 % z celkových predpovedí, alebo keď percento presných predpovedí pre zákazníkov, ktorí odišli, je menšie ako historický priemerný pomer odchodu.
  
- **Pravdepodobnosť odchodu (počet zákazníkov)**: Skupiny zákazníkov na základe ich predpokladaného rizika odchodu. voliteľne [vytvárať segmenty zákazníkov](prediction-based-segment.md) s vysokým rizikom odchodu. Takéto segmenty pomáhajú pochopiť, kde by malo byť vaše obmedzenie pre členstvo v segmente.  

  :::image type="content" source="media/subscription-churn-resultdistribution.PNG" alt-text="Graf znázorňujúci distribúciu výsledkov rizika straty, rozdelený do intervalov od 0 do 100 %":::

- **Najvýznamnejšie faktory:** Pri vytváraní vašej predikcie sa zohľadňuje veľa faktorov. Každý z faktorov má svoju dôležitosť vypočítanú pre agregované predpovede, ktoré model vytvára. Použite tieto faktory na overenie vašich výsledkov predikcia. Alebo použite tieto informácie neskôr [vytvárať segmenty](.//prediction-based-segment.md) ktoré by mohli pomôcť ovplyvniť riziko odchodu zákazníkov.

  :::image type="content" source="media/subscription-churn-influentialfactors.PNG" alt-text="Zoznam ukazujúci vplyvné faktory a ich dôležitosť pri predikcii výsledkov rizika straty.":::

> [!NOTE]
> Vo výstupnej entite pre tento model *ChurnScore* je predpokladaná pravdepodobnosť miznutia a *IsChurn* je binárne označenie založené na *ChurnScore* s prahom 0,5. Ak tento predvolený prah pre váš scenár nefunguje, [vytvoriť nový segment](segments.md) s vami preferovanou hranicou. Ak chcete zobraziť skóre straty, prejdite na **Údaje** > **entity** a zobrazte kartu údajov pre výstupnú entitu, ktorú ste definovali pre tento model.

[!INCLUDE [footer-include](includes/footer-banner.md)]
