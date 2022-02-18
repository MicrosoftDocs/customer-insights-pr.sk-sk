---
title: Nové a prichádzajúce funkcie
description: Informácie o nových funkciách, vylepšeniach a opravách chýb.
ms.date: 03/02/2022
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: midevane
manager: shellyha
ms.openlocfilehash: 0e25ed4e4e25b130fda410d4ba1c78caded7f0f9
ms.sourcegitcommit: b7189b8621e66ee738e4164d4b3ce2af0def3f51
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 02/03/2022
ms.locfileid: "8088304"
---
# <a name="whats-new-in-the-audience-insights-capability-of-dynamics-365-customer-insights"></a>Čo je nové v oblasti prehľadov cieľových skupín v Dynamics 365 Customer Insights



Sme radi, že môžeme oznámiť naše najnovšie aktualizácie! Tento článok sumarizuje funkcie verejnej ukážky, vylepšenia všeobecnej dostupnosti a aktualizácie funkcií. Ak chcete zobraziť dlhodobé plány pre funkcie, pozrite si [Plány vydaní Dynamics 365 a Power Platform](/dynamics365/release-plans/).

Aktualizácie zavádzame na základe jednotlivých regiónov. Do niektorých regiónov sa teda môžu niektoré funkcie dostať skôr než do ostatných. Pokiaľ nie je uvedené inak, nemusíte podniknúť žiadne kroky a my aplikáciu automaticky aktualizujeme bez prestojov.

> [!TIP]
> Ak chcete odoslať hlas pre požadované funkcie a návrhy produktov, prejdite na [portál aplikačných nápadov Dynamics 365](https://experience.dynamics.com/ideas/categories/?forum=79a8c474-4e35-e911-a971-000d3a4f3343&forumName=Dynamics%20365%20Customer%20Insights).


## <a name="january-2022-updates"></a>Aktualizácie z januára 2022

Aktualizácie v januári 2022 zahŕňajú nové funkcie, vylepšenia výkonu a opravy chýb.

### <a name="sentiment-analysis-of-your-customers-feedback"></a>Analýza sentimentu spätnej väzby vášho zákazníka

Customer Insights poskytuje novú funkciu poháňanú umelou inteligenciou, ktorá syntetizuje sentiment zákazníkov a identifikuje špecifické obchodné aspekty ako príležitosti na cielené zlepšenia. Analýzou písomnej spätnej väzby vašich zákazníkov môžete získať presné informácie pri nízkych nákladoch. Analýza sentimentu založená na modeloch spracovania prirodzeného jazyka (NLP), ktoré generujú dva odvodené štatistiky pre každé ID zákazníka. Skóre sentimentu (od –5 do 5) a zoznam príslušných obchodných aspektov. 

Ďalšie informácie nájdete v časti [Analyzujte sentiment v spätnej väzbe zákazníkov (ukážka)](sentiment-analysis.md).


## <a name="december-2021-updates"></a>Aktualizácie systému z decembra 2021

Aktualizácie v decembri 2021 zahŕňajú nové funkcie, vylepšenia výkonu a opravy chýb.

### <a name="forward-customer-insights-logs-to-azure-monitor"></a>Preposielajte denníky Customer Insights do Azure Monitor

Customer Insights poskytuje priamu integráciu s Azure Monitor. Táto funkcia zahŕňa udalosti auditu a prevádzkové udalosti. Denníky prostriedkov Azure Monitor vám umožňujú monitorovať a odosielať denníky do Azure Storage, Azure Log Analytics alebo ich streamovať do Azure Event Hubs.

Ďalšie informácie nájdete v časti [Prihláste sa preposielanie Dynamics 365 Customer Insights s Azure Monitor (ukážka)](diagnostics.md).

### <a name="enrich-customer-profiles-with-engagement-data"></a>Obohaťte profily zákazníkov o údaje o interakciách

Použiť údaje z Microsoft Office 365 obohatiť profily svojich zákazníckych účtov o informácie o interakciách prostredníctvom Office 365 aplikácie. Údaje o interakciách pozostávajú z e-mailov a aktivít na stretnutiach, ktoré sú agregované na úrovni účtu. Napríklad počet e-mailov z obchodného účtu alebo počet stretnutí s účtom. Nezdieľajú sa žiadne údaje o jednotlivých používateľoch. Toto obohatenie je dostupné v nasledujúcich regiónoch: Spojené kráľovstvo, Európa, Severná Amerika.

Ďalšie informácie nájdete v časti [Obohaťte profily zákazníkov o údaje o interakciách (ukážka)](enrichment-office.md).

### <a name="advanced-data-unification-features"></a>Pokročilé funkcie zjednotenia údajov

#### <a name="enable-conflict-resolution-policies-at-the-individual-attribute-level"></a>Povoľte politiky riešenia konfliktov na úrovni jednotlivých atribútov

Pri deduplikácii záznamov zákazníkov v rámci entity možno nebudete chcieť, aby ste ako víťaza museli vybrať úplný záznam. Teraz vám umožňujeme zlúčiť najlepšie polia z rôznych záznamov na základe pravidiel pre každý atribút. Môžete sa napríklad rozhodnúť ponechať najnovší e-mail A najkompletnejšiu adresu z rôznych záznamov. 

Teraz môžete definovať samostatné pravidlá zlučovania pre jednotlivé atribúty pri deduplikácii a zlučovaní záznamov v rámci jednej entity. Predtým sme vám umožnili vybrať iba jedno pravidlo zlúčenia (uchovávanie záznamov na základe úplnosti údajov o aktuálnosti) a toto pravidlo sa aplikovalo na úrovni záznamu na všetky atribúty. To nie je ideálne, keď sa niektoré údaje, ktoré si chcete ponechať, nachádzajú v zázname A a iné dobré údaje v zázname B.

Viac informácií nájdete v časti [Definícia deduplikácie v entite párovania](match-entities.md#define-deduplication-on-a-match-entity).

#### <a name="custom-rules-for-matching"></a>Vlastné pravidlá pre párovanie

Sú chvíle, keď potrebujete špecifikovať výnimku zo všeobecných pravidiel, aby sa NEPREHODOVALI záznamy. To sa môže stať, keď viacerí jednotlivci zdieľajú dostatok informácií, aby ich systém priradil ako jedného jednotlivca. Napríklad dvojčatá s rovnakým priezvisko, ktoré žijú v rovnakom meste a zdieľajú dátum narodenia.

Výnimky zabezpečujú, že nesprávne zjednotenie údajov bude možné riešiť v pravidlách zjednotenia. K pravidlu môžete pridať viacero výnimiek.

Ďalšie informácie nájdete v časti [Pridajte do pravidla výnimky](match-entities.md#add-exceptions-to-a-rule).

#### <a name="provide-additional-conflict-resolution-policies-and-enable-grouping-of-attributes"></a>Poskytnite ďalšie politiky riešenia konfliktov a povoľte zoskupovanie atribútov

Táto funkcia vám umožňuje zaobchádzať so skupinou polí ako s jednou jednotkou. Napríklad, ak naše záznamy obsahujú polia Adresa1, Adresa2, Mesto, Štát a PSČ. Pravdepodobne sa nechceme zlúčiť do adresy2 iného záznamu, pretože si myslíme, že by to urobilo naše údaje úplnejšími.

Teraz môžete skombinovať skupinu súvisiacich polí a použiť na skupinu jednu politiku zlúčenia. 

Ďalšie informácie nájdete v časti [Skombinujte skupinu polí](merge-entities.md#combine-a-group-of-fields).


## <a name="november-2021-updates"></a>Aktualizácie z novembra 2021

Aktualizácie v novembri 2021 zahŕňajú nové funkcie, vylepšenia výkonu a opravy chýb.

### <a name="segment-membership-now-available-in-dataverse"></a>Členstvo v segmente je teraz k dispozícii v Dataverse

Informácie o členstve v segmentoch pre profily zákazníkov sú teraz k dispozícii v Dataverse spolu s profilmi a prehľadmi zákazníkov. Akčné aplikácie Dynamics 365 a aplikácie s podporou modelov môžu tieto údaje použiť na vyhľadávanie podrobností o členstve v segmente pre daného zákazníka.

### <a name="activities-support-contact-level-details-for-business-accounts"></a>Aktivity podporujú podrobnosti na úrovni kontaktov pre firemné účty

Teraz môžete konfigurovať, zobrazovať a filtrovať aktivity pre kontakty na časových osách aktivít vášho firemného účtu, aby ste lepšie pochopili, ktoré kontakty účtu sa zúčastnili na konkrétnych aktivitách.

## <a name="october-2021-updates"></a>Aktualizácie z októbra 2021

Aktualizácie v októbri 2021 zahŕňajú nové funkcie, vylepšenia výkonu a opravy chýb.

### <a name="b-to-b"></a>B-to-B

Od októbra 2021 môžete v Customer Insights pracovať s firemnými účtami a ich súvisiacimi kontaktmi. Predtým bola aplikácia väčšinou prispôsobená individuálnym spotrebiteľom. Niekoľko oblastí funkcií bolo aktualizovaných tak, aby podporovali scenáre B-to-B nad rámec nového typu prostredia. Prehľad podporovaných funkcií B-to-B nájdete v časti [Pracujte s firemnými účtami v štatistikách publika](work-with-business-accounts.md).

Nasledujúce časti zdôrazňujú niektoré z kľúčových oblastí, ktoré boli prispôsobené na podporu obchodných účtov a individuálnych spotrebiteľov.

#### <a name="export-segments-based-on-business-accounts"></a>Export segmentov na základe obchodných účtov

Všetky exporty segmentov v štatistikách publika sú dostupné v kontexte firemných účtov. Väčšina exportov segmentov vyžaduje dodatočnú konfiguráciu a [projektované kontaktné informácie](segment-builder.md#create-a-new-segment) v základných segmentoch, aby boli platné pre podnikateľské účty. Ďalšie informácie nájdete v časti [Export segmentov](export-destinations.md#export-segments).

#### <a name="use-the-linkedin-ads-export-with-business-accounts"></a>Použite export LinkedIn Ads s firemnými účtami

Export reklám LinkedIn je teraz k dispozícii na zacielenie na kontakt a spoločnosť v kontexte obchodných účtov. Pri výbere zacielenia na spoločnosť ako primárneho zamerania exportu LinkedIn môžete exportovať segmenty postavené na obchodných účtoch bez potreby projektovania kontaktných informácií. Ďalšie informácie nájdete v dokumentoch o [Export reklám LinkedIn](export-linkedin-ads.md) a rozdiel medzi [kontaktné cielenie](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting) a [zameranie spoločnosti](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting). 

#### <a name="create-measures-based-on-business-accounts-and-their-hierarchy"></a>Vytvárajte miery na základe obchodných účtov a ich hierarchie

Nástroj na tvorbu opatrení vám umožňuje vytvárať miery okolo obchodných účtov a voliteľne použiť informácie o hierarchii. Informácie o hierarchii sa používajú na zhrnutie výpočtu miery v rámci účtu a všetkých súvisiacich podúčtov. Môžete napríklad vytvoriť miery, ako je celkový príjem pre každú skupinu obchodných účtov identifikovaných podľa ich hierarchie. Ďalšie informácie nájdete v sekcii [Definovanie a správa mier](measures.md).

#### <a name="create-segments-based-on-business-accounts-and-their-hierarchy"></a>Vytvorte segmenty na základe obchodných účtov a ich hierarchie

Nástroj na tvorbu segmentov vám umožňuje vytvárať segmenty obchodných účtov, ktoré voliteľne obsahujú kontaktné informácie pre každý účet v segmente. Ak máte nastavenú hierarchiu účtu, pri vytváraní segmentu môžete použiť informácie o hierarchii účtu. Ďalšie informácie nájdete v časti [Vytvorte nový segment](segment-builder.md#create-a-new-segment).

#### <a name="retain-your-business-accounts-with-deep-insights-to-their-churn-tendency"></a>Udržujte svoje obchodné účty s podrobnými informáciami o ich tendencii minúť

Model zákazníckeho churn predikcia teraz podporuje aj firemné účty. Riziko straty môžete vyhodnotiť nielen pre účet, ale aj pre kombináciu účtu a kategórie produktov alebo služieb, ktoré si od vás kúpia. Tento doplnok vám pomôže pochopiť, či je pravdepodobnejšie, že účet prestane od vás nakupovať vo všeobecnosti alebo len pre určitú kategóriu tovaru alebo služieb. Aby sme vám ešte viac pomohli pri používaní tohto modelu AI, sú tu uvedené aj dôvody, prečo je pravdepodobné, že účet zanikne. Ďalšie informácie nájdete v časti [Zrušenie transakcie predikcia (ukážka)](predict-transactional-churn.md).

#### <a name="see-contacts-of-a-business-account-in-customer-view"></a>Pozrite si kontakty firemného účtu v zobrazení zákazníka

Ak sú firemné účty namapované na súvisiace účty, aplikácia Customer Insights zobrazuje tieto súvisiace kontakty ako súčasť zobrazenia podrobností o zákazníkovi. Ďalšie informácie nájdete v časti [Profily zákazníkov](customer-profiles.md).


## <a name="september-2021-updates"></a>Aktualizácie zo septembra 2021

Aktualizácie v septembri 2021 obsahujú nové funkcie, vylepšenia výkonu a opravy chýb.

### <a name="activities"></a>Aktivity

- **Vylepšenia časovej osi aktivity** V profiloch zákazníkov sme rozšírili filtre pre časovú os aktivít. Okrem toho môžete použiť novú tablu filtra použiť na filtrovanie podľa typu aktivity a podľa dátumu. Dátumy je možné filtrovať za rôznych podmienok. Ďalšie informácie nájdete v časti [Zobrazte časové harmonogramy aktivít v profiloch zákazníkov](activities.md#view-activity-timelines-on-customer-profiles).

### <a name="relationships"></a>Vzťahy 

- **Podpora viacskokových vzťahov** Pri konfigurácii aktivít a definovaní vzťahov medzi entitami používajte viacskokové vzťahy. Viacskokové vzťahy používajú medziľahlú entitu na prepojenie dvoch entít. Pri konfigurácii aktivity môžete použiť viacskokový vzťah na prepojenie entity aktivity s medziľahlou entitou a potom so zákazníckou entitou. Viacskokové vzťahy môžete kombinovať so vzťahmi s viacerými cestami. Ďalšie informácie nájdete v téme [Viacskokové vzťahy](relationships.md#multi-hop-relationship).

- **Podpora vzťahov s viacerými cestami** Pri konfigurácii aktivít a definovaní vzťahov medzi entitami používajte vzťahy s viacerými cestami. Vzťahy s viacerými cestami viažu zdrojovú entitu k viac ako jednej entite. Pri konfigurácii aktivity môžete použiť vzťah s viacerými cestami na prepojenie vašej entity aktivity s viac ako jednou zákazníckou entitou. Vzťahy s viacerými cestami môžete kombinovať s viacskokovými vzťahmi. Ďalšie informácie nájdete v téme [Vzťahy s viacerými cestami](relationships.md#multi-path-relationship).

## <a name="august-2021-updates"></a>Aktualizácie z augusta 2021

Aktualizácie v júli a auguste 2021 obsahujú novú funkciu, vylepšenia výkonu a opravy chýb.

### <a name="extensibility"></a>Rozšíriteľnosť

- **Exportujte segmenty do Klaviyo** Rozšírili sme naše [exportné destinácie o Klaviyo](export-klaviyo.md). Teraz môžete exportovať segmenty a vytvárať kampane, prevádzkovať e-mailový marketing a používať konkrétne skupiny zákazníkov v programe Klaviyo. 


## <a name="june-2021-updates"></a>Aktualizácie z júna 2021

Aktualizácie pre z júna 2021 zahŕňajú niekoľko funkcií, aktualizácií výkonu a opráv chýb.

### <a name="data-ingestion"></a>Prijímanie údajov

- **Vylepšená aktualizácia postupu zjednocovania údajov** Teraz je možné na serveri zobraziť podrobnejšie a vylepšené dynamické aktualizácie stavu v krokoch [proces zjednocovania údajov](data-unification.md). S touto funkciou budete môcť podrobne sledovať postup, rozumieť procesnému toku a urobiť potrebné opatrenia v prípade, že si niektorý z krokov vyžaduje vašu pozornosť.

### <a name="extensibility"></a>Rozšíriteľnosť

- **Exportujte segmenty a ďalšie údaje do služby Salesforce Marketing Cloud** Rozšírili sme naše ciele exportovania o[Salesforce Marketing Cloud](export-salesforce.md). Teraz máte možnosť exportovania segmentov a ďalších typov údajov do aplikácie Salesforce Marketing Cloud pomocou značkového exportu SFTP. Importovať údaje je možné v službe Salesforce plne automatizovať a použiť ich na vytváranie účinnejších marketingových kampaní.  
 
- **Exportujte segmenty do ActiveCampaign** Rozšírili sme naše exportné destinácie o[ aktívnu kampaň ](export-active-campaign.md). Teraz môžete exportovať segmenty a vytvárať kampane, prevádzkovať e-mailový marketing a spolupracovať s konkrétnymi skupinami zákazníkov v programe ActiveCampaign.
 
- **Exportujte segmenty do Sendinblue** Rozšírili sme naše exportné destinácie o [Sendinblue](export-sendinblue.md). Teraz môžete exportovať segmenty a vytvárať kampane, prevádzkovať e-mailový marketing a spolupracovať s konkrétnymi skupinami zákazníkov v programe Sendinblue.
 
### <a name="ux-updates"></a>Aktualizázcie UX 

- **Nová a vylepšená stránka Zákazníci a stránka s podrobnosťami profilu** Stránku Zákazníci a stránky s podrobnosťami profilu sme prepracovali tak, aby sa zlepšil dojem používateľov a zvýšil sa výkon. Vďaka týmto zmenám môžete zobrazovať, triediť, vyhľadávať a filtrovať zákazníkov. V adrese URL sa teraz nachádzajú filtre umožňujúce jednoduché zdieľanie výsledkov vyhľadávania s ostatnými používateľmi. Výsledky vyhľadávania je možné uložiť aj ako segment.    
  Stránka s podrobnosťami o zákazníckych profiloch teraz obsahuje skupiny údajov v rôznych častiach, ako sú demografické údaje, identifikátory a ďalšie atribúty profilu, s cieľom zlepšiť čitateľnosť. Ostatné časti na stránke podrobností profilu sú teraz interaktívnejšie. Časť aktivít napríklad teraz umožňuje filtrovanie a triedenie.


## <a name="may-2021-updates"></a>Aktualizácie z mája 2021

Aktualizácie z mája 2021 obsahujú niekoľko funkcií, vylepšenia výkonu a opravy chýb.

### <a name="data-ingestion"></a>Prijímanie údajov

- **Prezeranie alebo úprava metaúdajov alebo definície entity pri pripájaní údajov z Azure Data Lake Storage** Teraz môžete zobraziť a upraviť metaúdaje alebo definíciu entity v prehľadoch cieľovej skupiny, keď pripájate údaje z priečinka Common Data Model vo vašom Azure Data Lake Storage. Táto funkcia poskytuje odozvu v reálnom čase, validáciu modelu a kontrolu chýb. Umožňuje vám to bezproblémovo upravovať model.json aj manifest.json.

### <a name="extensibility"></a>Rozšíriteľnosť

- **Vylepšené exporty segmentov, vlastný rozvrh a duplikácia** Teraz môžete [zobraziť všetky exporty pre konkrétny segment](export-destinations.md#view-exports-and-export-details) v zozname. Toto nové zobrazenie pomáha riadiť, ako sa konkrétny segment používa, a prispôsobiť existujúce alebo vytvoriť nové exporty.    
  Môžete [definovať vlastné plány obnovenia](export-destinations.md#schedule-and-run-exports) pre jednotlivé exporty alebo niekoľko exportov naraz. Doteraz sa všetky exporty spúšťali s každou aktualizáciou systému.    
  Namiesto vytvárania nového exportu úplne od začiatku môžete ušetriť čas a začať na základe existujúceho exportu.

- **Export segmentov do Microsoft Advertising** Naše cieľové miesta exportu sme rozšírili o Microsoft Advertising. Vytvárajte cieľové skupiny súladu so zákazníkmi v Microsoft Advertising pomocou zjednotených údajov profilov zákazníkov a používajte tieto cieľové skupiny pre svoje reklamné kampane. Viac informácií nájdete v článku [Export segmentov do služby Microsoft Advertising](export-microsoft-advertising.md).

- **Export segmentov do LinkedIn Ads** Rozšírili sme naše cieľové miesta exportu tak, aby obsahovali LinkedIn Ads a umožnili vám odomknúť zacielenie na kontakty aj na spoločnosť prostredníctvom LinkedIn prostredníctvom exportu vašich údajov zjednoteného profilu zákazníka. Viac informácií nájdete v článku [Export segmentov do služby LinkedIn Ads](export-linkedin-ads.md).


- **Export segmentov do Omnisend** Naše cieľové miesta exportu sme rozšírili o Omnisend. Omnisend umožňuje pomocou segmentov vytvorených v prehľadoch cieľových skupín vytvárať kampane, poskytovať e-mailový marketing a využívať konkrétne skupiny zákazníkov. Viac informácií nájdete v článku [Export segmentov do služby Omnisend](export-omnisend.md).

### <a name="predictions"></a>Predikcie

- **Zostava o použiteľnosti vstupných údajov** Zostava o použiteľnosti vstupných údajov poskytuje konsolidovaný prehľad o chybách a varovaniach, ktoré môžu generovať vaše vopred pripravené predikcie. Poskytuje tiež odporúčania, ako zlepšiť výkon modelu.    
  Zostava je k dispozícii po dokončení tréningového procesu modelu. Je vytvorený pre každý model zvlášť, bez ohľadu na to, či bol úspešne dokončený alebo nie.
  V súčasnosti je táto funkcia k dispozícii iba pre model úbytku transakcií. Viac informácií nájdete v články [Zostava o použiteľnosti vstupných údajov](manage-predictions.md#input-data-usability-report).

### <a name="relationships"></a>Vzťahy

- **Vizualizér vzťahov** Zobrazenie vizualizátora vzťahov vám umožňuje zobraziť všetky existujúce vzťahy medzi entitami a ich kardinalitu. Vzťahy sú teraz usporiadané do skupín: vzťahy vytvorené používateľom, systémom a zdedené vzťahy. Zobrazenie môžete tiež exportovať ako obrázok. Ďalšie informácie nájdete v téme [Zobrazenie vzťahov](relationships.md#view-relationships). 

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

- **Export segmentov do RollWorks** Naše cieľové miesta exportu sme rozšírili o RollWorks. Teraz môžete exportovať segmenty z Customer Insights do cieľových skupín RollWorks a použiť ich ako základ pre vašu reklamu v rámci scenára „firma a firma“.    
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

  Správcovia môžu kopírovať konfigurácie prostredia do nového prostredia v tej istej organizácii. Vďaka tejto funkcii máte teraz k dispozícii rozširené funkcie prostredia kopírovania pre prípady, keď sa používajú zdroje údajov založené na spravovanej službe Microsoft Dataverse Data Lake alebo priečinku Common Data Model.

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