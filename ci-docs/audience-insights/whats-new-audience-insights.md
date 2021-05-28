---
title: Nové a prichádzajúce funkcie
description: Informácie o nových funkciách, vylepšeniach a opravách chýb.
ms.date: 05/06/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: midevane
manager: shellyha
ms.openlocfilehash: c66b37d6e4d6ed830238566fbc09934832892b34
ms.sourcegitcommit: 3f9981df97fa7b1f432a446d3f11936ea4cfbde5
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 05/06/2021
ms.locfileid: "5988939"
---
# <a name="whats-new-in-the-audience-insights-capability-of-dynamics-365-customer-insights"></a>Čo je nové v oblasti prehľadov cieľových skupín v Dynamics 365 Customer Insights

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Sme radi, že môžeme oznámiť naše najnovšie aktualizácie! Tento článok sumarizuje funkcie verejnej ukážky, vylepšenia všeobecnej dostupnosti a aktualizácie funkcií. Ak chcete zobraziť dlhodobé plány pre funkcie, pozrite si [Plány vydaní Dynamics 365 a Power Platform](/dynamics365/release-plans/).

Aktualizácie zavádzame na základe jednotlivých regiónov. Do niektorých regiónov sa teda môžu niektoré funkcie dostať skôr než do ostatných. Pokiaľ nie je uvedené inak, nemusíte podniknúť žiadne kroky a my aplikáciu automaticky aktualizujeme bez prestojov.

> [!TIP]
> Ak chcete odoslať hlas pre požadované funkcie a návrhy produktov, prejdite na [portál aplikačných nápadov Dynamics 365](https://experience.dynamics.com/ideas/categories/?forum=79a8c474-4e35-e911-a971-000d3a4f3343&forumName=Dynamics%20365%20Customer%20Insights).

## <a name="april-2021-updates"></a>Aktualizácie pre apríl 2021

Aktualizácie z apríla 2021 obsahujú niekoľko funkcií, vylepšenia výkonu a opravy chýb.

### <a name="data-unification"></a>Zjednotenie údajov
 
- **Vylepšené možnosti zlúčenia pre zjednotenie údajov**    
  
   Teraz máme vylepšenú používateľskú skúsenosť s konfiguráciou zlúčenia procesu zjednotenia údajov. Zmeny zahŕňajú intuitívne usporiadanie zlúčených polí a podrobné štatistiky kombinovaných a singletových polí.

- **Zmena poradia entít a konfigurácia všetkých zdrojových záznamov do entity Zákazník**  
      
   Teraz môžete v procese zjednotenia údajov zmeniť poradie a odstrániť entity z existujúceho plánu zhody. Poskytuje flexibilitu na zmenu poradia entít v procese párovania podľa obchodných potrieb. Ďalej povoľujeme zahrnúť všetky nezhodné záznamy do finálnej entity *Zákazník*, ktorá im umožňuje definovať definíciu súboru údajov o profile zákazníka.

### <a name="enrichments"></a>Obohatenia

 - **Nové obohatenie: vylepšené adresy**    
  
   Sme radi, že môžeme predstaviť nové obohatenie, ktoré vylepšuje adresy vo vašich zákazníckych údajoch. Adresy vo vašich údajoch môžu byť neštruktúrované, neúplné alebo nesprávne. Táto funkcia využíva modely spoločnosti Microsoft na normalizáciu a obohatenie vašich adries do formátu Common Data Model, aby bola zaistená lepšia presnosť a prehľad.
 
   Viac informácií nájdete v časti [Obohatenie zákazníckych profilov vylepšenými adresami](enrichment-enhanced-addresses.md).

- **Riadená konfiguračná skúsenosť pre obohatenia**    
  
   Vrátili sme sa do konfiguračného zážitku pre obohatenia pomocou jednoduchého, riadeného zážitku. Teraz máte jasný postupný postup vytvárania a úpravy obohatení.
 
   Ďalej sme oddelili konfiguráciu pripojení pre obohatenia tretích strán, aby sme umožnili použitie toho istého pripojenia viacerými obohateniami. Iba správcovia môžu konfigurovať nové pripojenia, ale vytvorené pripojenia sú vždy k dispozícii správcom aj prispievateľom.    

   Ďalšie informácie nájdete v téme [Prehľad pripojení](connections.md).

- **Viacnásobné obohatenie rovnakého typu**    
  
   Teraz používateľom povoľujeme vytvárať a spravovať viac obohatení rovnakého typu obohatenia. Napríklad teraz môžete vytvoriť dve samostatné obohatenia adries a obohatiť tak dva rôzne segmenty zákazníkov. Limity sa vzťahujú na to, koľko obohatení rovnakého typu je možné vytvoriť, a líšia sa v závislosti od typu obohatenia.
  
   Ďalšie informácie nájdete v sekcii [Obohatenie pre profily zákazníkov](enrichment-hub.md).

## <a name="march-2021-updates"></a>Aktualizácia z marca 2021

Aktualizácie z marca 2021 obsahujú niekoľko funkcií, vylepšenia výkonu a opravy chýb.

### <a name="activities"></a>Aktivity

- **Sprievodca aktivitou a sémantické typy**

   Vylepšili sme a aktualizovali sme naše skúsenosti s mapovaním aktivít, aby sme usmernili a zjednodušili vytváranie mapovania aktivít. V tomto novom prostredí dostanú používatelia komentované skúsenosti, ktoré im pomôžu dokončiť každý krok procesu. V kroku mapovania aktivity si používateľ môže okrem výberu z mnohých typov aktivít zvoliť aj sémantické mapovanie údajov pre *Predplatné* a/alebo *SalesOrderLine* na priemyselné štandardné schémy, ktoré sa dajú použiť na následnú spotrebu.   

   Ďalšie informácie nájdete v článku [Aktivity zákazníka](activities.md).

### <a name="data-ingestion"></a>Prijímanie údajov

- **Pripojte sa k lokálny zdrojom údajov pomocou tokov údajov a brán Power Platform** S potešením oznamujeme ukážku toku údajov Power Platform a lokálne pripojenie pomocou brán v nástroji Customer Insights s pridruženým prostredím Power Platform alebo Dataverse. Všetky nové zdroje údajov vytvorené v prostredí Customer Insights s prepojením prostredia Dataverse predvolené toky údajov Power Platform prinášajúce lokálny dátové pripojenie a bohatú sadu konektorov a transformačných schopností.

### <a name="extensibility"></a>Rozšíriteľnosť

- **Exporty organizované v spojeniach a exportoch** Zmenili sme názov stránky **Ciele exportu** na **Pripojenia** a pridali sme samostatnú stránku pre **Exporty**. V rámci tejto aktualizácie prevedieme existujúci export na páry spojenia a export pomocou tohto spojenia. Správcovia majú teraz viac prehľadu o odchádzajúcich údajoch na stránke **Pripojenia**. Všetky užívateľské roly majú prístup k stránke **Exporty**, ale iba správcovia sa môžu rozhodnúť, že prispievateľom umožnia upravovať konkrétne exporty so zdieľanými pripojeniami.     
  Viac informácií nájdete v časti [Prehľad pripojení](connections.md) a [Prehľad exportov](export-destinations.md).

- **Export segmentov do Campaign Monitor** Naše cieľové miesta exportu sme rozšírili o Campaign Monitor. Teraz môžete exportovať segmenty z Customer Insights do Campaign Monitor do zoznamov monitorov kampaní a použiť ich ako základ pre svoje marketingové kampane.    
   Ďalšie informácie nájdete v článku [Export do Campaign Monitor](export-campaign-monitor.md).

- **Export segmentov do Constant Contact** Naše cieľové miesta exportu sme rozšírili o Constant Contact. Teraz môžete exportovať segmenty z Customer Insights do zoznamov Constant Contact do zoznamov monitorov kampaní a použiť ich ako základ pre svoje marketingové kampane.   
   Ďalšie informácie nájdete v článku [Export do Constant Contact](export-constant-contact.md).

- **Export segmentov do RollWorks** Naše cieľové miesta exportu sme rozšírili o RollWorks. Teraz môžete exportovať segmenty z Customer Insights do cieľovej skupiny RollWorks do zoznamov monitorov kampaní a použiť ich ako základ pre svoje reklamy B2B.    
   Ďalšie informácie nájdete v článku [Export do RollWorks](export-rollworks.md).

- **Export segmentov do Snapchat** Naše cieľové miesta exportu sme rozšírili o Snapchat. Teraz môžete exportovať segmenty z Customer Insights do cieľovej skupiny Snapchat do zoznamov monitorov kampaní a použiť ich ako základ pre svoje reklamy.     
   Ďalšie informácie nájdete v článku [Export do Snapchat](export-snapchat.md).

### <a name="predictions"></a>Predikcie

- **Filtre produktu používajte v prediktívnych odporúčaniach produktov** Do nášho modelu odporúčania produktu sme pridali možnosť používať produktové filtre. Teraz môžete vytvoriť predikciu, ktorú používa iba podmnožinu vašich produktov.    
   Viac informácií nájdete v časti [Konfigurácia produktových filtrov](predict-product-recommendation.md#configure-product-filters).

- **Vytvárajte segmenty z predpovedí modelu** Pridali sme rýchly spôsob vytvárania segmentov pomocou výsledkov modelu predikcie. Na stránke s výsledkami modelu môžete ľahko vytvoriť nový segment výberom možnosti nového **Vytvorenia segmentu**.    
  Viac informácií nájdete v časti [Vytvorte segment na základe predikcia modelu](prediction-based-segment.md).

- **Vysvetlivky k odporúčaniu výrobkov** Pridali sme informácie vysvetľujúce kľúčové faktory, ktoré sa model AI naučil pri generovaní produktových odporúčaní, a mieru, do akej tieto faktory prispievajú k odporúčaniam produktu. Tieto informácie sa pridajú na obrazovku s výsledkami modelu.    
   Viac informácií nájdete v článku [Kontrola stavu predikcie a výsledkov](predict-product-recommendation.md#review-a-prediction-status-and-results).

## <a name="february-2021-updates"></a>Aktualizácie z februára 2021

Aktualizácie z februára 2021 zahŕňajú niekoľko funkcií, aktualizácií výkonu a opráv chýb.

#### <a name="extensibility"></a>Rozšíriteľnosť

- **Export segmentov do aplikácie AdRoll**

  Naše exportné destinácie sme rozšírili o AdRoll. Teraz môžete exportovať segmenty z Customer Insights príjemcom v AdRoll a použiť ich ako základ pre svoju reklamu. Ďalšie informácie nájdete v časti [Konektor pre AdRoll](export-adroll.md).

#### <a name="segments"></a>Segmenty
 
- **Duplikovať segment**
  
  Ak chcete vytvoriť nový segment na základe existujúceho, môžete teraz duplikovať segment a upraviť ho tak, aby ste ho ďalej spresnili. 

- **Pridajte k segmentu ďalšie atribúty**

  Teraz môžete do výstupu segmentu zahrnúť atribúty, aj keď tieto atribúty nie sú súčasťou profilu zákazníka. Napríklad zahrňte ID predplatného do segmentu, aj keď je súčasťou entity predplatného, ktorá má vzťah M:1 s entitou zákazníka. Pokiaľ atribút patrí entite súvisiacej s entitou zákazníka, môžete teraz zahrnúť tieto atribúty.  

#### <a name="predictions"></a>Predikcie

- **Vytvorenie predikcie odporúčania produktu**

  Pochopenie toho, čo zákazníci majú záujem o kúpu, je jedným z prvých krokov potrebných na zlepšenie obchodných výnosov a budovanie lojality zákazníkov prostredníctvom personalizácie a angažovanosti. Poskytovanie odporúčaní pre produkty, ktoré nie sú v súlade so záujmami vašich zákazníkov, môže vytvoriť pocit odpojenia medzi zákazníkom a vašim podnikaním a v konečnom dôsledku obmedziť celkové potenciálne príjmy a skúsenosti zákazníka. 

  Pomocou vlastných údajov môžete teraz vytvárať predpovede pre produkty, ktoré si zákazníci v budúcnosti pravdepodobne kúpia. Viac informácií nájdete v časti [Predikcia odporúčania produktov](predict-product-recommendation.md).

#### <a name="system-administration"></a>Správa systému

- **Kopírovacie prostredie podporuje viac typov zdrojov údajov**

  Správcovia môžu kopírovať konfigurácie prostredia do nového prostredia v tej istej organizácii. Táto vlastnosť rozširuje funkčnosť prostredia kopírovania pre prípady, v ktorých sa využívajú zdroje údajov založené na data lake Common Data Service alebo priečinku Common Data Model.

## <a name="january-2021-updates"></a>Aktualizácie z januára 2021

Aktualizácie z januára 2021 zahŕňajú niekoľko funkcií, aktualizácií výkonu a opráv chýb.

#### <a name="extensibility"></a>Rozšíriteľnosť

- **Rozšírená funkčnosť a zvýšený výkon pre export SFTP** Teraz môžete exportovať všetky výstupné entity z nástroja Customer Insights do hostiteľa SFTP. Predtým bol export obmedzený na segmentové entity. Výkon exportu SFTP navyše umožňuje väčší objem dát za kratší čas, v závislosti od výkonu vášho hostiteľa SFTP.    
  Ďalšie informácie nájdete v časti [Konektor pre SFTP (verzia Preview)](export-sftp.md).  

#### <a name="segments"></a>Segmenty

- **Návrh segmentov s podporou strojového učenia na zlepšenie metrík** Existuje nový spôsob, ako objavovať a vytvárať segmenty. Systém pomocou modelu AI navrhuje segmenty, ktoré môžu pomôcť zlepšiť KPI (mieru), ktorú už sledujete. Ukazujeme mieru vplyvu atribútov, ktoré vyberiete v miere, alebo iného primárneho atribútu. Tieto informácie pomáhajú nájsť potenciálne segmenty, ktoré predstavujú príležitosti.    
  Ďalšie informácie nájdete v časti [Navrhované segmenty (verzia Preview)](suggested-segments.md).

#### <a name="data-unification"></a>Zjednotenie údajov

- **Vylepšené prostredie priraďovania** V oblasti zjednotenia údajov bolo aktualizované prostredie priraďovania. Umožňuje vám nakonfigurovať a zobraziť pravidlá priraďovania vrátane podrobných štatistík, aby ste ďalej vysvetlili, ako funguje priraďovanie. Existujú možnosti zakázania pravidla priraďovania, aby už nebolo aktívne pri zachovaní konfigurácie, pravidlá priraďovania myšou a ďalšie.
  Ďalšie informácie nájdete v téme [Priraďovanie entít](match-entities.md).

- **Výstup deduplikácie z procesu priraďovania je k dispozícii ako entita** Výstup procesu deduplikácie z procesu priraďovania je teraz zapísaný do samostatnej entity na ďalšiu analýzu. Táto entita pozostáva z polí použitých v procese deduplikácie a záznamu víťaza a zodpovedajúcich alternatívnych záznamov, ktoré sa zlúčia so záznamom víťaza.
  Viac informácií nájdete v časti [Výstup deduplikácie ako entita](match-entities.md#deduplication-output-as-an-entity).

#### <a name="system-administration"></a>Správa systému

- **Bezproblémové zdieľanie údajov do Microsoft Dataverse** Teraz môžete zdieľať výstup zo služby Customer Insights s aplikáciami Microsoft Dataverse využívajúcimi spravované Data Lake Microsoft Dataverse. Keď priradíte prostredie Dataverse s Customer Insights, získate možnosť povoliť zdieľanie údajov.
  Ďalšie informácie nájdete v článku [Správa prostredí](manage-environments.md).




[!INCLUDE[footer-include](../includes/footer-banner.md)]