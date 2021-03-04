---
title: Pokusy so strojovým učením Studio (klasické)
description: Používajte modely strojového učenia Studio (klasické) v službe Dynamics 365 Customer Insights.
ms.date: 12/03/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: mhart
ms.reviewer: ameetj
manager: shellyha
ms.openlocfilehash: 8a861d62bdfee6a3a82468fe1ab4a3fbbdad43d4
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 02/15/2021
ms.locfileid: "5270223"
---
# <a name="use-models-based-on-azure-machine-learning-studio-classic"></a>Používajte modely založené na strojovom učení Azure Studio (klasické)

Zjednotené údaje v službe Dynamics 365 Customer Insights sú zdrojom pre vytváranie modelov strojového učenia, ktoré môžu generovať ďalšie obchodné prehľady. Customer Insights sa integruje do služby strojového učenia Studio (klasickej), aby ste mohli používať svoje vlastné modely. Ak sa chcete dozvedieť, ako sa modely vyvinuté cez strojové učenie platformy Azure integrujú do nástroja Customer Insights, prečítajte si sekciu [Pokusy so strojovým učením platformy Azure](azure-machine-learning-experiments.md).

## <a name="prerequisites"></a>Predpoklady

- Prístup do Customer Insights
- Aktívne predplatné Azure Enterprise
- [Zjednotené profily zákazníka](data-unification.md)
- Konfigurácia [exportu entity do úložiska Azure Blob](export-azure-blob-storage.md)

## <a name="set-up-machine-learning-studio-classic"></a>Nastavenie klasického strojového učenia Studio

V rámci prvého kroku musíme vytvoriť pracovný priestor a otvoriť Strojové učenie Studio (klasické).

1. Prejdite do [https://www.portal.azure.com](https://www.portal.azure.com/) a prihláste sa.

1. Vyberte **Vytvoriť zdroj**.

1. Vyhľadajte **Pracovný priestor štúdia strojového učenia** a vyberte **Vytvoriť**.

1. Zadajte požadované podrobnosti na [vytvorenie pracovného priestoru](https://docs.microsoft.com/azure/machine-learning/studio/create-workspace). Vyberte položku **Cenová úroveň plánu webových služieb** na základe množstva údajov, ktoré plánujete importovať. Ak chcete dosiahnuť najlepší výkon, vyberte **Umiestnenie**, ktoré je vám geograficky najbližšie.

1. Po vytvorení zdroja sa zobrazí hlavný panel štúdia strojového učenia. Vyberte **Spustiť štúdio strojového učenia**.

   ![Používateľské rozhranie štúdia strojového učenia Azure](media/azure-machine-learning-studio.png)

## <a name="work-with-azure-machine-learning-studio"></a>Práca so štúdiom strojového učenia Azure

Teraz môžete vytvoriť nový experiment alebo importovať existujúcu šablónu experimentu z ukážkovej galérie. Existujú ukážkové pokusy pre tri štandardné scenáre:

- [Predikcia straty](#churn-analysis)

- [Hodnota životnosti zákazníka](#customer-lifetime-value-prediction)

- [Odporúčanie produktu alebo najbližšia najlepšia akcia](#productrecommendation-or-next-best-action)

1. Ak vytvoríte nový experiment alebo použijete šablónu experimentu z galérie, musíte nakonfigurovať vlastnosti **Importovať údaje**. Použite sprievodcu alebo priamo poskytnite údaje na prístup k ukladaciemu priestoru BLOB platformy Azure, ktoré obsahuje vaše údaje.  

   ![Experiment so štúdiom strojového učenia Azure](media/azure-machine-learning-studio-experiment.png)

1. Teraz môžete zostaviť vlastný spracovateľský kanál na čistenie a predspracovanie údajov, extrahovanie charakteristických znakov a vyškolenie vhodného modelu.

1. Otestujte a optimalizujte výkon modelu.

1. Ak ste spokojní s kvalitou modelu, vyberte položku **Nastaviť webovú službu** > **Prediktívna webová služba**. Táto možnosť importuje vycvičený model a kanál charakterizácie z výcvikového experimentu do prediktívnej služby. Prediktívna služba môže vziať ďalšiu množinu vstupných údajov so schémou použitou vo výcvikovom experimente na vytváranie predikcií.

   ![Konfigurácia prediktívnej webovej služby](media/predictive-webservice-control.png)

1. Keď experiment prediktívnej webovej služby prebehol úspešne, môžete ho nasadiť na automatické plánovanie. Ak chcete, aby webová služba pracovala s Customer Insights, zvoľte **Nasadiť webovú službu** > **Ukážka Nasadiť webovú službu [nová]**. [Ďalšie informácie o nasadení webovej služby](https://docs.microsoft.com/azure/machine-learning/studio/deploy-a-machine-learning-web-service).

   ![Nasadenie prediktívnej webovej služby](media/predictive-webservice-deploy.png)

## <a name="sample-models-from-the-gallery"></a>Vzorové modely z galérie

Pre modely v tomto článku použijeme fiktívny scenár spoločnosti Contoso Hotel. Contoso Hotel zhromažďuje nasledujúce údaje:

- CRM údaje pozostávajúce z aktivity pobytov v hoteli. Súbor údajov obsahuje informácie o dátumoch pobytu pre každého registrovaného zákazníka. Obsahuje tiež informácie o rezervácii, typoch izieb, podrobnostiach o útratách atď. Údaje pokrývajú štyri roky, od januára 2014 do januára 2018.
- Profily zákazníkov hotelových hostí. Tieto profily obsahujú informácie o každom zákazníkovi vrátane jeho mena, dátumu narodenia, poštovej adresy, pohlavia a telefónneho čísla.
- Využitie služieb ponúkaných hotelom, ako sú kúpele, práčovňa, Wi-Fi alebo kuriér. Tieto informácie sa zaznamenávajú pre každého registrovaného zákazníka. Typicky je použitie služieb spojené s pobytom. V niektorých prípadoch môžu služby využívať zákazníci bez pobytu v hoteli.

## <a name="churn-analysis"></a>Analýza straty

Analýza straty sa vzťahuje na rôzne oblasti podnikania. V rámci tohto príkladu sa pozrieme na stratu služieb, konkrétne v súvislosti s hotelovými službami, ako je opísané vyššie. Poskytuje to funkčný príklad komplexného modelového kanála, ktoré sa môže použiť ako východiskový bod pre akýkoľvek iný typ modelu straty.

### <a name="definition-of-churn"></a>Definícia straty

Definícia straty sa môže líšiť v závislosti od scenára. V rámci tohto príkladu by mal byť hosť, ktorý nenavštívil hotel v minulom roku, označený ako stratený.  

Šablónu pokusu je možné importovať z galérie. Najskôr sa uistite, že ste importovali údaje **Aktivita pobytov v hoteli**, **Údaje o zákazníkovi** a **Údaje o využití služieb** z ukladacieho priestoru BLOB platformy Azure.

   ![Import údajov pre model straty](media/import-data-azure-blob-storage.png)

### <a name="featurization"></a>Charakterizácia

Na základe definície straty najskôr identifikujeme prvotné charakteristické vlastnosti, ktoré budú mať vplyv na označenie. Tieto nespracované charakteristické vlastnosti potom spracujeme do podoby číselnej podoby, ktorú je možné použiť v modeloch strojového učenia. K integrácii údajov dochádza v službe Customer Insights, aby sme sa k týmto tabuľkám mohli pripojiť pomocou *ID zákazníka*.

   ![Pripojenie sa k importovaným údajom](media/join-imported-data.png)

Charakterizácia pre vytvorenie modelu pri analýze straty môže byť trochu zložitejšia. Dáta sú funkciou času a každý deň sa zaznamenáva nová hotelová aktivita. Počas charakterizácie chceme generovať statické charakteristické vlastnosti z dynamických údajov. V tomto prípade z činnosti hotela generujeme viac charakteristických vlastností s posuvným oknom v trvaní jedného roka. Kategorické charakteristické vlastnosti, ako je typ izby alebo typ rezervácie, tiež rozširujeme na samostatné charakteristické vlastnosti pomocou jednorazového kódovania.  

Konečný zoznam charakteristických vlastností:

| **Číslo**  | **Pôvodný_stĺpec**          | **Odvodené charakteristické vlastnosti**                                                                                                                      |
|-------------|------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------|
| 1           | Typ izby                    | RoomTypeLargeCount, RoomTypeSmallCount                                                                                                    |
| 2           | Typ rezervácie                 | BookingTypeOnlineCount, BookingTypePhoneCallCount                                                                                         |
| 3           | Kategória cestovania              | TravelCategoryBusinessCount, TravelCategoryLeisureCount                                                                                   |
| 4           | Utratená suma                | TotalDollarSpent                                                                                                                          |
| 5           | Dátumy príchodu a odchodu  | StayDayCount, StayDayCount2016, StayDayCount2015, StayDayCount2014, StayCount, StayCount2016. StayCount2015, StayCount2014                |
| 6           | Využité služby                | UsageTenure, ConciergeUsage, CourierUsage, DryCleaningUsage, GymUsage, PhoneUsage, RestaurantUsage, SpaUsage, TelevisionUsage, WifiUsage  |

### <a name="model-selection"></a>Výber modelu

Teraz musíme zvoliť optimálny algoritmus, ktorý sa má použiť. V tomto prípade je väčšina funkcií založená na kategorických charakteristických vlastnostiach. Spravidla dobre fungujú modely založené na rozhodovacích stromoch. Ak existujú iba numerické vlastnosti, lepšou voľbou by mohli byť neurónové siete. V takýchto situáciách je tiež dobrým kandidátom pomocný vektorový stroj (SVM); na získanie najlepšieho výkonu je však potrebné ho trochu vyladiť. Vyberáme **Dvojtriedny vylepšený rozhodovací strom** ako prvý vybraný model, po ktorom nasleduje **Dvojtriedny SVM** ako druhý model. Štúdio strojového učenia Azure vám umožňuje vykonávať testy A/B, takže je užitočné začať s dvoma modelmi, a nie s jedným.

Na nasledujúcom obrázku je znázornený kanál trénovania a vyhodnocovania modelu zo štúdia strojového učenia Azure:

![Model straty v štúdiu strojového učenia Azure](media/azure-machine-learning-model.png)

Používame tiež techniku s názvom **Dôležitosť charakteristickej vlastnosti permutácie**, dôležitý aspekt optimalizácie modelu. Vstavané modely majú malý až žiadny prehľad o vplyve akejkoľvek konkrétnej charakteristickej vlastnosti na výslednú predikciu. Kalkulačka dôležitosti funkcie používa vlastný algoritmus na výpočet vplyvu jednotlivých charakteristických vlastností na výsledok konkrétneho modelu. Dôležitosť charakteristickej vlastnosti je normalizovaná medzi +1 a -1. Negatívny vplyv znamená, že zodpovedajúci prvok má kontraintuitívny vplyv na výsledok a mal by sa z modelu odstrániť. Pozitívny vplyv naznačuje, že charakteristická vlastnosť výrazne prispieva k predikcii. Tieto hodnoty nie sú korelačnými koeficientmi, pretože ide o rôzne metriky. Viac informácií nájdete v časti [Dôležitosť charakteristickej vlastnosti permutácie](https://docs.microsoft.com/azure/machine-learning/studio-module-reference/permutation-feature-importance).

Celý [experiment straty je k dispozícii v galérii Azure AI](https://gallery.azure.ai/Experiment/Hotel-Churn-Predictive-Exp).

## <a name="customer-lifetime-value-prediction"></a>Predikcia hodnoty životnosti zákazníka

Výpočet hodnoty životnosti zákazníka (CLTV) je jednou z kľúčových metrík, ktoré môže spoločnosť použiť na hodnotenie a segmentáciu svojich zákazníkov. Pre hotelierstvo je dôležité poznať svojich zákazníkov. Kľúčovými informáciami sú napríklad faktory porozumenia, ktoré tvoria dobrých zákazníkov. Pomáhajú manažmentu hotela posúdiť, na ktoré charakteristické vlastnosti sa musia zamerať a zlepšiť, aby uspokojili svojich vysoko platiacich zákazníkov. Tieto rozhodnutia môžu mať priamy vplyv na tržby a zisky.  

### <a name="definition-of-cltv"></a>Definícia CLTV

V tomto príklade definujeme CLTV zákazníka ako celkovú sumu v dolároch, ktorú zákazník odhadom utratí počas nasledujúcich 365 dní. Na predpovedanie tejto hodnoty použijeme údaje za posledné tri roky pre všetkých zákazníkov.

### <a name="featurization"></a>Charakterizácia

V tomto prípade bude charakterizácia podobná scenáru straty. Označenia a predpokladané hodnoty sa však líšia od tých, ktoré sú definované vyššie.

### <a name="model-selection"></a>Výber modelu

Predikcia CLTV je regresný problém, pretože predikovaná hodnota je pozitívne hodnotená kontinuálna premenná. Na základe vlastností charakteristickej vlastnosti vyberieme položku **Zvýšená regresia rozhodovacieho stromu** ako jeden algoritmus a **Regresia neurónovej siete** ako ďalší algoritmus na trénovanie modelu.

## <a name="product-recommendation-or-next-best-action"></a>Odporúčanie produktu alebo najbližšia najlepšia akcia

Odporúčanie produktu v scenári hotela sa interpretuje ako odporúčanie služieb, ktoré hotel ponúka zákazníkom. Cieľom je vybrať si vhodné služby pre zákazníkov tak, aby sa maximalizovalo ich využívanie. Je to podobné odporúčaniam filmov pre používateľov služieb streamovania videa.

### <a name="definition-of-product-recommendation-or-next-best-action"></a>Definovanie odporúčania produktu alebo najbližšej najlepšej akcie

Cieľ definujeme ako maximalizáciu objemu využívania služieb v dolároch tým, že zákazníkom hotelov poskytneme najlepšie služby podľa ich záujmu.

### <a name="featurization"></a>Charakterizácia

Podobne ako model straty, sa pripájame k ServiceCustomerID hotela s ID zákazníka, aby sme mohli vytvárať odporúčania konzistentne podľa ID zákazníka.

![Charakterizácia modelu odporúčania](media/azure-machine-learning-model-featurization.png)

Údaje pochádzajú z troch rôznych entít a z nich sú odvodené charakteristické vlastnosti. Charakterizácia problému odporúčania sa v porovnaní so scenármi straty alebo CLTV líši. Model odporúčaní vyžaduje vstupné údaje vo forme troch súborov funkcií.

### <a name="model-selection"></a>Výber modelu

Predikujeme produkty alebo služby pomocou volaného algoritmu s názvom **Train Matchbox Recommender** na školenie modelu odporúčaní.

![Algoritmus odporúčania produktov](media/azure-machine-learning-model-recommendation-algorithm.png)

Tri vstupné porty pre model **Train Matchbox Recommender** sa použijú pri trénovaní údajov o využití služieb, opisu zákazníka (voliteľné) a opisu služby. Existujú tri rôzne spôsoby hodnotenia modelu. Jedna je pre hodnotenie modelu, kde sa skóre NDCG (Normalized Discounted Cumulative Gain) vypočíta tak, aby sa hodnotili hodnotené položky. V tomto experimente máme skóre NDCG vo výške 0,97. Ďalšie dve možnosti sú hodnotenie modelu v celom odporúčanom katalógu služieb alebo hodnotenie iba položiek, ktoré používatelia predtým nepoužili.

Ak sa pozrieme ďalej na distribúciu odporúčaní v celom katalógu služieb, všimneme si, že najlepšie služby, ktoré sa odporúčajú, sú telefón, Wi-Fi a kuriér. Je to v súlade s tým, čo sme zistili z distribúcie údajov o spotrebe služieb:

![Výstup modelu odporúčaní](media/azure-machine-learning-model-output.png)

Celý [pokus s odporúčaním produktu je prístupný v galérii Azure AI.](https://gallery.azure.ai/Experiment/Recommendation-4)

## <a name="integrate-custom-models"></a>Integrácia vlastných modelov

Ak chcete tieto predikcie použiť v Customer Insights, musíte **exportovať** predikcie spolu s ID zákazníkov. [Exportujte ich do rovnakého umiestnenia ukladacieho priestoru BLOB platformy Azure](https://docs.microsoft.com/azure/storage/common/storage-import-export-data-from-blobs), do ktorého exportujete zdrojové údaje. Prediktívne webové služby môžu byť naplánované tak, aby sa spúšťali pravidelne a aktualizovali skóre.

Údaje vygenerované vlastným modelom možno použiť na ďalšie obohatenie údajov vašich zákazníkov. Viac informácií nájdete v časti [Vlastné modely strojového učenia](custom-models.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]