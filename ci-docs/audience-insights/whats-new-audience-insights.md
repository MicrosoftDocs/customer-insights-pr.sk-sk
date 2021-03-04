---
title: Nové a prichádzajúce funkcie
description: Informácie o nových funkciách, vylepšeniach a opravách chýb.
ms.date: 02/02/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: midevane
manager: shellyha
ms.openlocfilehash: 9183c8af4fb9f9f08ac63d8d0cd37c6868bba310
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 02/15/2021
ms.locfileid: "5270451"
---
# <a name="whats-new-in-the-audience-insights-capability-of-dynamics-365-customer-insights"></a>Čo je nové v oblasti prehľadov cieľových skupín v Dynamics 365 Customer Insights

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Sme radi, že môžeme oznámiť naše najnovšie aktualizácie! Tento článok sumarizuje funkcie verejnej ukážky, vylepšenia všeobecnej dostupnosti a aktualizácie funkcií. Ak chcete zobraziť dlhodobé plány pre funkcie, pozrite si [Plány vydaní Dynamics 365 a Power Platform](https://docs.microsoft.com/dynamics365/release-plans/).

Môžete si tiež pozrieť nasledujúce video, kde sa dozviete viac o možnostiach plánovaných na posledných šesť mesiacov.

> [!VIDEO https://www.youtube.com/embed/jQh-7pscH30]

Aktualizácie zavádzame na základe jednotlivých regiónov. Do niektorých regiónov sa teda môžu niektoré funkcie dostať skôr než do ostatných. Pokiaľ nie je uvedené inak, nemusíte podniknúť žiadne kroky a my aplikáciu automaticky aktualizujeme bez prestojov.

> [!TIP]
> Ak chcete odoslať hlas pre požadované funkcie a návrhy produktov, prejdite na [portál aplikačných nápadov Dynamics 365](https://experience.dynamics.com/ideas/categories/?forum=79a8c474-4e35-e911-a971-000d3a4f3343&forumName=Dynamics%20365%20Customer%20Insights).

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


## <a name="december-2020-updates"></a>Aktualizácie systému z decembra 2020

Aktualizácie z decembra 2020 zahŕňajú niekoľko funkcií, vylepšenia výkonu a opravy chýb.

### <a name="new-and-updated-features-in-december-2020"></a>Nové a aktualizované funkcie v decembri 2020

#### <a name="data-enrichment"></a>Obohatenie údajov

- **Vylepšené obohatenie afinity značky a záujmov**
  
  Zjednodušili sme naše skóre afinity, aby sa dalo lepšie pochopiť a používať. Teraz môžete rýchlo identifikovať zákazníkov na základe afinity k danej značke alebo záujmu.

  Ďalej sme pridali nové možnosti konfigurácie, aby ste lepšie ovládali, akým spôsobom chcete obohatiť svoje profily zákazníkov. 

  Ďalšie informácie nájdete v sekcii [Obohatenie profilov zákazníkov o značky a záujmy](enrichment-microsoft-graph.md).

- **Kontrolujte, ktoré profily sa majú obohatiť**

  Teraz môžete obohatiť iba podmnožinu svojich profilov zákazníkov možnosťou vybrať entitu segmentu namiesto predvolenej entity zákazníka. Vytvorte segment s profilmi zákazníkov, ktoré chcete obohatiť, a vyberte ho v konfigurácii obohatenia pre svoju množinu údajov o zákazníkoch.
  Táto funkcia je v súčasnosti k dispozícii iba pre obohatenia poskytované spoločnosťami Experian a HERE Technologies. Túto schopnosť čoskoro sprístupníme pre ďalšie obohatenia.

  Viac informácií nájdete v časti [Obohatenie profilov zákazníkov o demografické údaje od spoločnosti Experian](enrichment-experian.md) alebo [Obohatenie profilov zákazníkov pomocou HERE Technologies](enrichment-here.md).

#### <a name="extensibility"></a>Rozšíriteľnosť

- **Aktivujte svoje segmenty prostredníctvom služby Autopilot**

  Exportujte segmenty do služby Autopilot a použite ich na marketingové účely. Ďalšie informácie nájdete v časti [Konektor pre Autopilot (verzia Preview)](export-autopilot.md).

- **Aktivujte svoje segmenty prostredníctvom služby SendGrid**

  Exportujte segmenty do služby SendGrid a použite ich na marketingové účely. Ďalšie informácie nájdete v časti [Konektor pre SendGrid](export-sendgrid.md).

#### <a name="system-administration"></a>Správa systému

- **Aktualizované rozhranie na riadenie prostredia**
  
  Teraz môžete vytvárať, upravovať, mazať a resetovať prostredia priamo z nástroja na výber prostredia v hlavičke aplikácie. 
  
  Prostredie, ktoré používate, bude navyše pripnuté v hornej časti panela s prostredím, takže ho už nemusíte hľadať.

  Ďalšie informácie nájdete v článku [Správa prostredí](manage-environments.md).

## <a name="november-2020-updates"></a>Aktualizácie z novembra 2020

Aktualizácie z novembra 2020 zahŕňajú niekoľko funkcií, vylepšenia výkonu a opravy chýb.

### <a name="new-and-updated-features-in-november-2020"></a>Nové a aktualizované funkcie v novembri 2020

#### <a name="data-enrichment"></a>Obohatenie údajov

- **Prineste si svoje vlastné údaje na obohatenie pomocou vlastného importu pomocou protokolu Secure File Transfer Protocol (SFTP)**
  
  Vlastný import pomocou protokolu SFTP vám umožňuje importovať údaje obohatenia, ktoré nemusia prechádzať procesom zjednotenia údajov. Prečítajte si viac o vlastnom importe prostredníctvom SFTP.

  Viac informácií nájdete v článku [Obohaťte profily zákazníkov o vlastné údaje (ukážka)](enrichment-SFTP-custom-import.md).
 
- **Obohaťte svoje zákaznícke údaje o údaje o polohe od spoločnosti HERE Technologies**

  So službami obohatenia údajov HERE Technologies môžete dosiahnuť presnejšie pochopenie polohy vašich zákazníkov pomocou normalizácie adresy, extrakcie zemepisnej šírky a dĺžky a ďalších údajov. Získajte ďalšie informácie obohacovaní pomocou HERE Technologies.

  Viac informácií nájdete v článku [Obohatenie profilov zákazníkov pomocou HERE Technologies](enrichment-here.md).

#### <a name="data-unification"></a>Zjednotenie údajov

- **Flexibilita na povolenie profilovania údajov u vybraných entít a polí z vášho konta úložiska**

  Môžete určiť, ktorým dátovým entitám a poliam z priečinka Common Data Model vo vašom konte úložiska Azure Data Lake chcete povoliť profilovanie údajov ako súčasť procesu prijímania údajov.

  Viac informácií nájdete v časti [Pripojte sa k priečinku Common Data Model](connect-common-data-model.md#connect-to-a-common-data-model-folder).

#### <a name="extensibility"></a>Rozšíriteľnosť

- **Aktivujte svoje segmenty prostredníctvom služby Google Ads**

  Exportujte segmenty zo zoznamov cieľových skupín Google Ads a použite tieto profily na inzerciu v službách Vyhľadávanie Google, Obsahová sieť Google, YouTube a Gmail. Získajte viac informácií o aktivácii vašich segmentov prostredníctvom služby Reklamy Google.

  Ďalšie informácie nájdete v časti [Konektor pre Reklamy Google](export-google-ads.md).

- **Aktivujte svoje segmenty prostredníctvom služby Marketo**

  Exportujte segmenty do cieľových skupín Marketo a použite ich na marketingovú automatizáciu. Získajte viac informácií o aktivácii vašich segmentov prostredníctvom služby Marketo. 

  Ďalšie informácie nájdete v časti [Konektor pre Marketo](export-marketo.md).

- **Aktivujte svoje segmenty prostredníctvom služby DotDigital**

  Exportujte segmenty do služby DotDigital a použite ich na marketingové účely. Získajte viac informácií o aktivácii vašich segmentov prostredníctvom služby DotDigital. 

  Ďalšie informácie nájdete v časti [Konektor pre DotDigital](export-dotdigital.md).

#### <a name="predictions"></a>Predikcie

- **Predikujte odchod založený na transakciách**

  Funkcia predikcie odchodov založených na transakciách vám umožňuje bez pomoci dátového vedca predpovedať pravdepodobnosť, že zákazník prestane kupovať produkty alebo služby.  Pomocou skóre predikcie môžete kombinovať ďalšie informácie o svojich zákazníkoch, napríklad hodnotu zákazníka, a vytvoriť tak segmenty s vysokým rizikom odchodu alebo zákazníkmi s vysokou hodnotou. Tento segment použite na priame zacielenie na zákazníkov prostredníctvom marketingových aktivít, podpory zákazníkov a ďalšie scenárov, aby ste znížili riziko odchodu.
 
  Nakonfigurujte definíciu odchodu ako časové okno špecifické pre vaše podnikanie a definujte, aký stav budete považovať za úbytok zákazníkov. Napríklad obchod s potravinami môže chcieť považovať zákazníka za odídeného, ak si za posledných 30 dní nič nekúpil.
 
  Keď budete pokračovať vo vytváraní predikcie, prevedieme vás potrebnými údajmi a umožníme vám namapovať údaje o vašej firme do polí požadovaných na predikovanie odchodu vašich zákazníkov. Môžete tiež nastaviť plán preškolenia modelu na základe nových informácií vo vašom systéme, aby sa prispôsobil meniacim sa obchodným okolnostiam.
 
  Viac informácií nájdete v článku [Predikcia odchodu založeného na transakciách (ukážka)](predict-transactional-churn.md).

#### <a name="system-administration"></a>Správa systému

- **Resetovať prostredie**

  Obnovte všetko v prostredí vybranej inštancie a začnite znova.

  Ďalšie informácie nájdete v téme [Obnovenie existujúceho prostredia](manage-environments.md#reset-an-existing-environment).


- **Pripojte sa k svojmu účtu úložiska Azure Data Lake pomocou objektu služby**

  Zapisujte dátový výstup a čítajte údaje z vášho účtu úložiska pomocou objektu služby Azure. Existujúce pripojenia konta úložiska môžu naďalej používať kľúč konta. Ponúkajú tiež možnosť inovácie na ďalšie použitie objektu služby. Nové pripojenia budú založené na metóde overovania objektu služby pre váš účet úložiska.

  Ďalšie informácie sa dozviete v článku [Pripojenie k účtu Azure Data Lake Storage Gen2 pomocou objektu služby Azure pre prehľady cieľových skupín](connect-service-principal.md).

## <a name="october-2020-updates"></a>Aktualizácie z októbra 2020

Aktualizácie z októbra 2020 zahŕňajú niekoľko funkcií, vylepšenia výkonu a opravy chýb.

### <a name="new-and-updated-features-in-october-2020"></a>Nové a aktualizované funkcie v októbri 2020

#### <a name="extensibility"></a>Rozšíriteľnosť

- **Export do Mailchimp**

Exportujte segmenty do existujúcich zoznamov cieľových skupín v aplikácii Mailchimp, aby ste svojim zákazníkom poskytli osobné e-mailové prostredie.

Ďalšie informácie nájdete v časti [Konektor pre Mailchimp](export-mailchimp.md).

#### <a name="data-enrichment"></a>Obohatenie údajov

- **Deduplikujte zdrojové záznamy v entite Párovanie**

Zadajte pravidlá deduplikácie pre entity použité v procese párovania na identifikáciu duplicitných záznamov. Zlúčte ich do jedného záznamu a prepojte všetky zdrojové záznamy s týmto zlúčeným záznamom. Tento deduplikovaný záznam sa potom použije v procese priraďovania medzi entitami.

Viac informácií nájdete v časti [Definícia deduplikácie v entite párovania](match-entities.md#define-deduplication-on-a-match-entity).

#### <a name="system-administration"></a>Správa systému

- **Orchestrácia: Nová možnosť obnovenia v zlúčení**

Až do dnešného dňa, keď spustíte proces zlúčenia, systém spustil všetky následné procesy, ktoré závisia od zlúčenia a nasledujúcich procesov. Teraz môžete overiť výstup procesu zlúčenia (zjednotená entita zákazníka) pred použitím v následnom spracovaní, ako sú napr. segmenty alebo miery.
Na stránke zlúčenia si teraz môžete zvoliť spustenie iba kroku zlúčenia a spustenie iba tohto procesu. Ak chcete obnoviť aj všetky následné procesy, môžete zvoliť spustenie zlúčenia a následných procesov. 

## <a name="september-2020-updates"></a>Aktualizácie zo septembra 2020

Aktualizácie zo septembra 2020 zahŕňajú niekoľko funkcií, vylepšenia výkonu a opravy chýb.

### <a name="new-and-updated-features-in-september-2020"></a>Nové a aktualizované funkcie v septembri 2020

#### <a name="activities"></a>Aktivity

- **Inteligentná predikcia sémantiky atribútov**

Táto nová funkcia predikuje sémantické typy vstupných atribútov, ktoré sa odovzdávajú procesu zjednotenia údajov. Používa modely strojového učenia, ktoré zlepšujú presnosť a šetria čas.

#### <a name="enrichments"></a>Obohatenia

- **Obohatenie demografických údajov od spoločnosti Experian**

Demografické obohatenie od spoločnosti Experian je teraz k dispozícii ako ukážka. Experian je svetový líder v oblasti marketingových služieb a zisťovania kreditu spotrebiteľov a firiem. So [službami obohacovania údajov od spoločnosti Experian](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage) môžete hlbšie porozumieť svojim zákazníkom obohatením profilov svojich zákazníkov o demografické údaje, ako sú veľkosť domácnosti, príjem a ďalšie.

Ak chcete používať túto funkciu, musíte mať aktívne predplatné u spoločnosti Experian.

Ďalšie informácie nájdete v článku [Obohatenie profilov zákazníkov o demografické údaje od spoločnosti Experian](enrichment-experian.md)


#### <a name="system-administration"></a>Správa systému

- **Tabla podrobností úlohy**

Tabla podrobností úlohy vám umožňuje zobraziť podrobnosti o úlohách, ktoré systém spúšťa. Je to praktický spôsob identifikácie problémov s konfiguráciou a hľadania riešení.
Skontrolujte chybové správy a zistite, ako riešite potenciálne problémy.
 
- **Informácie o spracovaní boli pridané na ďalšie stránky**

Toto vylepšenie pridáva informácie o stave vašich entít na stránke **Entity** a **Zákazníci**.
 
Ďalej môžete nájsť na oboch týchto stránkach podrobnosti o priebehu procesov spolu s podrobnosťami úloh.

- **Vylepšenia na stránke stavu systému**

Vylepšili sme štruktúru tabuľky podrobností o stave v časti **Systém** > **Stav** pri kontrole exportov údajov.
 
Ďalej chyby v stĺpci **Detaily** sú teraz podrobnejšie a využiteľnejšie. 
 
- **Zrušenie vráti úlohu späť do predchádzajúceho stavu**

Keď zrušíte úlohu, napríklad v procese párovania, vráti sa späť do posledného stavu. Napríklad ak bol proces párovania dokončený včera a dnes ho zrušíte, vráti sa do včerajšieho úspešného stavu.


## <a name="august-2020-updates"></a>Aktualizácie z augusta 2020

Aktualizácie z augusta 2020 zahŕňajú niekoľko funkcií, vylepšenia výkonu a opravy chýb.

### <a name="new-and-updated-features-in-august-2020"></a>Nové a aktualizované funkcie v auguste 2020

#### <a name="data-unification"></a>Zjednotenie údajov

- **Vylepšené prostredie pre etapu mapovania počas zjednotenia údajov**

  Prostredie s etapou mapovania v procese zjednocovania údajov vám umožňuje plynulejšie vyberať entity, atribúty a definovať sémantiku.

  Zmeny zahŕňajú:
  
  - na pridanie entít a polí je potrebných menej interakcií
  - vylepšené možnosti vyhľadávania na stránke mapovania
  - vizuálna a ľahká identifikácia navrhovaného typu poľa

#### <a name="enrichment"></a>Obohatenie

- **Obohatenie o afinity záujmov je k dispozícii na viacerých trhoch**

  Rozširujeme dostupnosť obohacovania afinít záujmov mimo USA na päť ďalších trhov: Kanada, Austrália, Spojené kráľovstvo, Francúzsko a Nemecko. Vďaka tomuto rozšíreniu môžete obohatiť svoje údaje o zákazníkoch o ďalšie záujmy uplatniteľné na týchto trhoch. Taktiež obohatíme vaše zákaznícke profily, ktoré sa nachádzajú na týchto trhoch, pomocou miestnych vlastníckych údajov z programu Microsoft Graph.
  Ďalšie informácie nájdete v sekcii [Obohatenie profilov zákazníkov o značky a záujmy](enrichment-microsoft-graph.md)


## <a name="july-2020-updates"></a>Aktualizácie z júla 2020

Aktualizácie pre z júla 2020 zahŕňajú niekoľko funkcií, aktualizácií výkonu a opráv chýb.

### <a name="new-and-updated-features-in-july-2020"></a>Nové a aktualizované funkcie v júli 2020

#### <a name="extensibility"></a>Rozšíriteľnosť

- Spúšťač **Power Automate pre dokončený proces zjednotenia**

  Rozšírili sme naše spúšťače pre Power Automate a po dokončení obnovenia procesu zjednotenia (priradenie, párovanie, zlúčenie) môžete vytvoriť oznámenie alebo akciu.    
  Ďalšie informácie nájdete v [konektore Power Automate](export-power-automate.md)

#### <a name="enrichment"></a>Obohatenie

- **Obohatenie o afinity značiek je k dispozícii na viacerých trhoch**

  Rozširujeme dostupnosť obohacovania afinít značiek mimo USA na päť ďalších trhov: Kanada, Austrália, Spojené kráľovstvo, Francúzsko a Nemecko. Vďaka tomuto rozšíreniu môžete na týchto trhoch obohatiť svoje zákaznícke údaje o miestne značky. Taktiež obohatíme vaše zákaznícke profily, ktoré sa nachádzajú na týchto trhoch, pomocou miestnych vlastníckych údajov z programu Microsoft Graph.
  Ďalšie informácie nájdete v sekcii [Obohatenie profilov zákazníkov o značky a záujmy](enrichment-microsoft-graph.md)

## <a name="june-2020-updates"></a>Aktualizácie z júna 2020

Aktualizácie pre z júna 2020 zahŕňajú niekoľko funkcií, aktualizácií výkonu a opráv chýb.

### <a name="new-and-updated-features-in-june-2020"></a>Nové a aktualizované funkcie v júni 2020

#### <a name="enrichment"></a>Rozšírenie

- **Obohatenie o údaje spoločnosti z Leadspace**
  
  Definujte polia v zjednotených profiloch zákazníkov, ktoré sa používajú na vyhľadávanie súvisiacich údajov z Leadspace. Po spustení procesu obohacovania sú profily B2B obohatené o ďalšie atribúty vrátane veľkosti spoločnosti, umiestnenia, odvetvia a ďalšie.    
  Táto spolupráca vám umožňuje zlepšiť kvalitu vašich údajov vďaka vstupu od služieb tretích strán. Na použitie tohto obohatenia potrebujete licenciu od Leadspace na prístup k firemným údajom B2B. Systém použije túto licenciu na to, aby vaše údaje boli neustále obohacované.    
  Ďalšie informácie nájdete v sekcii [Obohatenie o údaje spoločnosti s pomocou Leadspace](enrichment-leadspace.md).

- **Stránka centra obohatenia**

  Všetky dostupné obohatenia údajov od poskytovateľov obohatenia prvých a tretích strán sa nakonfigurujú na rovnakom mieste. Konfigurácia obohatenia údajov je plynulý zážitok, ktorý je spravovaný z jedného miesta.    
  Ďalšie informácie nájdete v sekcii [Obohatenie pre profily zákazníkov](enrichment-hub.md).

- **Oddelené obohatenie značiek a záujmov**

  Značky a záujmy sú teraz k dispozícii ako dva nezávislé druhy obohatenia. Oddelené obohatenia vám poskytujú flexibilitu pri ich individuálnej konfigurácii a správe v závislosti od vašich obchodných požiadaviek alebo potrieb.    
  Ďalšie informácie nájdete v sekcii [Obohatenie profilov zákazníkov o značky a záujmy](enrichment-microsoft-graph.md).

#### <a name="extensibility"></a>Rozšíriteľnosť

- **Adresy URL, na ktoré je možné kliknúť, pre zjednotené aktivity v doplnku Karta zákazníka pre Dynamics 365**

  Zjednotené aktivity v doplnku Karta zákazníka teraz zobrazujú klikateľné adresy URL, ak boli tieto adresy URL definované počas konfigurácie aktivít.    
  Ďalšie informácie nájdete v článku [Doplnok Karta zákazníka](customer-card-add-in.md).

- **Značky a záujmy dostupné v rámci doplnku Karta zákazníka pre Dynamics 365**

  Nová kontrola doplnku Karta zákazníka pre Dynamics 365 vám umožňuje zobraziť obohatenia značiek a záujmov o vašich kontaktoch v aplikáciách zapojenia zákazníkov v Dynamics 365.    
  Ďalšie informácie nájdete v článku [Doplnok Karta zákazníka](customer-card-add-in.md).

- **Viac spúšťačov Power Automate**

  Rozšírili sme spúšťače pre Power Automate a pridali sme tieto spúšťače:
  - Získajte oznámenie alebo vykonajte akciu po dokončení automatickej plnej obnovy (zdroje údajov, zjednotenie, segmenty, opatrenia, export)
  - Definujte prahovú hodnotu pre podnikové opatrenie. Môžete napríklad vytvoriť upozornenie, ktoré sa odošle po prekročení definovaného limitu. Spúšťač navyše prináša informácie, ktoré vám umožňujú vytvárať komplexnejšie pracovné postupy v Power Automate.    
  Ďalšie informácie nájdete v [konektore Power Automate](export-power-automate.md)

- **Exportovať do správcu reklám pre Facebook**
  
  Táto funkcia umožňuje exportovať segmenty do Správcu reklám Facebook. Segmenty sa exportujú ako vlastné publiká, aby sa v nich mohli používať zjednotené profily zákazníkov marketingových kampaniach a reklamách Facebook. Vlastné cieľové skupiny sú tiež použiteľné na vytváranie kampaní na Instagrame prostredníctvom správcu reklám pre Facebook.    
  Ďalšie informácie nájdete v [Konektore správcu reklám pre Facebook](export-facebook.md).

#### <a name="predictions"></a>Predikcie

- **Predikcia straty predplatného**

  Postupujte podľa sprievodcu a vytvorte kanál predikcie straty v oblastiach predplatného, ako sú cloudové služby, členstvo zákazníkov a ďalšie sektory. 

  Funkcia predikcie straty predplatného vám umožňuje predpovedať pravdepodobnosť toho, že zákazník prestane používať produkty alebo služby založené na predplatnom bez zapojenia odborníka na prácu s údajmi. Pomocou skóre predikcie môžete skombinovať ďalšie informácie o svojich zákazníkoch a vytvoriť tak segmenty s vysokým rizikom straty. Pomocou tohto segmentu môžete priamo zacieliť na zákazníkov v oblasti marketingu, podpory zákazníkov a ďalších scenárov, aby ste znížili riziko odchodu pre konkrétnych zákazníkov, zvýšili výnosy a znížili náklady.

  V rámci tejto skúsenosti môžete nakonfigurovať definíciu straty ako časové okno špecifické pre váš podnik. Napríklad spoločnosť poskytujúca streamované videá, ktorá má mesačný proces predplatného, by mohla uvažovať, že stratí zákazníka po 15 dňoch od vypršania platnosti predplatného.

  Pri pokračovaní v predikcii vás prevedieme potrebnými údajmi a umožníme vám priradiť údaje o vašej firme do polí potrebných na predpovedanie straty vašich zákazníkov. Ako sa obchodné informácie menia, môžete tiež nastaviť plán preškolenia o nových informáciách vo vašom systéme, aby sa prispôsobili meniacim sa obchodným okolnostiam.    
  Ďalšie informácie nájdete v sekcii [Predikcia straty predplatného (ukážka)](predict-subscription-churn.md).

#### <a name="segments"></a>Segmenty

- **Nájsť podobných zákazníkov**
  
  Nájdite podobných zákazníkov vo svojej zákazníckej základni pomocou umelej inteligencie. Model strojového učenia na základe binárnej klasifikácie priraďuje zákazníkom v rozšírenom segmente skóre podobnosti. Skóre je založené na podobnosti so zákazníkmi v segmente zdrojov. V závislosti od skóre podobnosti sa profily zákazníkov pridávajú do novovytvoreného segmentu.

  V digitálnom marketingu sa niekedy označuje ako dvojité modelovanie. Používa model AI na vyhľadanie zákazníkov, ktorí sú podobní inému segmentu vašich zákazníkov, a to tak, že zohľadní viac atribútov. Umožňuje vám to nielen výber atribútov, ale zároveň vám to umožňuje určiť maximálny počet zákazníkov, ktorí by sa mali nachádzať v tomto novom segmente. Model AI potom vypočíta skóre podobnosti pre každého zákazníka na základe vybratých atribútov a nájde zákazníkov s vyšším priemerným skóre podobnosti. Výsledný segment bude zahŕňať zákazníkov, ktorí vyzerajú podobne ako zákazníci vo vašom pôvodnom segmente.    
  Ďalšie informácie nájdete v téme [Podobní zákazníci](find-similar-customer-segments.md).

- **Prekrývanie segmentov a rozdiely**

  Prekrývanie segmentov vám umožňuje zistiť, koľko zákazníkov je spoločných pre dva alebo viac segmentov. Napríklad: ako sa segment s vysokými ziskami prekrýva so segmentom zákazníkov s vysokou spokojnosťou alebo ako sa segment stratených zákazníkov prekrýva so segmentom zákazníkov s nízkou spokojnosťou. Ďalej môžete analyzovať, ako sa prekrývanie mení, na základe dodatočného atribútu podľa vášho výberu.

  Rozdiely segmentov odhaľujú, čo odlišuje jeden segment od zvyšku vašich zákazníkov alebo od iného segmentu. Všetko, čo musíte urobiť, je identifikovať segment a systém potom identifikuje atribúty profilu a opatrenia, ktoré ho odlíšia vo forme klasifikovaného zoznamu rozdielov - od najsilnejšieho rozdielu až po najslabší.    
  Ďalšie informácie nájdete v sekcii [Prehľady o segmentoch (ukážka)](segment-insights.md).

- **Životnosť segmentu**
  
  Definujte plán a aktivujte alebo deaktivujte segment.    
  Ďalšie informácie nájdete v článku [Správa existujúcich segmentov](segments.md#manage-existing-segments).

## <a name="may-2020-updates"></a>Aktualizácie z mája 2020

Aktualizácie z mája 2020 zahŕňajú niekoľko funkcií, aktualizácií výkonu a opráv chýb.

### <a name="new-and-updated-features-in-may-2020"></a>Nové a aktualizované funkcie v máji 2020

#### <a name="data-ingestion"></a>Prijímanie údajov

- **Príjem údajov v reálnom čase: zobrazenia histórie**

  Pri používaní nášho rozhrania API na príjem aktualizácií v reálnom čase môžete zobraziť až 30 dní súhrnnej histórie týchto aktualizácií. Máte prístup k agregátom všetkých úspešných alebo neúspešných hovorov API vrátane ich výsledku, zdrojového systému a ďalších užitočných metaúdajov.    
  Ďalšie informácie sa dozviete v téme [Prijímanie údajov v reálnom čase](real-time-data-ingestion.md).

- **Príjem údajov v reálnom čase: aktualizácie profilu**

  Toto rozšírenie prijímania údajov v reálnom čase umožňuje zobraziť v priebehu niekoľkých sekúnd zmeny konkrétnych polí profilu používateľa.    
  Okrem funkcií v reálnom čase pre aktivity podporuje systém aj aktualizácie polí profilu s nízkou latenciou. Aktualizácie polí profilu v reálnom čase majú čas uplynutia platnosti, a preto nenahrádzajú plánované obnovenia.    
  Ďalšie informácie sa dozviete v téme [Prijímanie údajov v reálnom čase](real-time-data-ingestion.md).

#### <a name="extensibility"></a>Rozšíriteľnosť

- **Aktualizovaná časová os a stránkovanie na doplnku karty zákazníka**

  Časová os riešenia doplnku Karta zákazníka sa zhoduje s časovou osou aktivity. Stránkovanie časovej osi sa zlepšilo a ukázalo sa až 50 aktivít naraz. Umožňuje tiež načítať viac aktivít na časovú os.    
  Ďalšie informácie nájdete v článku [Doplnok Karta zákazníka](customer-card-add-in.md).

- **Spúšťač Power Automate pre zmeny segmentov**

  Spúšťače pre Power Automate definujú, z čoho môžete vytvoriť tok. Novo pridaný spúšťač vám umožňuje definovať prahovú hodnotu pre segment. Môžete napríklad vytvoriť upozornenie, ktoré sa odošle po prekročení definovaného limitu.    
  Ďalšie informácie nájdete v [konektore Power Automate](export-power-automate.md).

- **Podpora viacerých klientov pre vlastné modely**

  Nakonfigurujte pracovné postupy pre vlastné modely pomocou webovej služby iného nájomníka strojového učenia Azure. Pri vytváraní nového pracovného toku pre vlastné modely sa môžete prihlásiť do nájomníka Azure Machine Learning. Táto schopnosť je doplnkom existujúcej schopnosti integrácie s vašou vlastnou webovou službou strojového učenia Azure.    
  Viac informácií nájdete v časti [Vlastné modely strojového učenia](custom-models.md).

#### <a name="segments"></a>Segmenty

- **Automatizácia cesty entít**

  Pri vytváraní segmentu musia používatelia definovať cestu entity. Táto schopnosť predstavuje prvý krok v automatizácii definície cesty entity, aby ste sa mohli zamerať na kritériá segmentácie, ktoré máte na mysli.    
  Ak entita, podľa ktorej chcete segmentovať svojich zákazníkov, priamo súvisí s jednotnou entitou zákazníka, už nebudete musieť definovať cestu entity. Ak však existuje viac ako jedna možná cesta entity, stále ju musíte definovať ručne.

- **Akcie vo viacerých segmentoch**
  
  Používatelia si môžu vybrať viac segmentov a vykonať s nimi akcie, napríklad obnoviť segmenty jediným kliknutím.    

- **Obnovenie segmentov**

  Používatelia môžu obnoviť jeden segment alebo vybrať iba segmenty, ktoré chcú obnoviť.    

  
- **Vylepšenia zložených segmentov**

  Používatelia môžu vytvárať, upravovať a odstraňovať segmenty založené na iných segmentoch. Napríklad segment konštruovaný na inom segmente, ktorý bol skonštruovaný na treťom segmente.    

- **Stránka zoznamu segmentov**

  Nový dizajn stránky segmentov používa formát zoznamu, ktorý umožňuje zobraziť viac segmentov naraz. Pridá sa vyhľadávacie pole na rýchle vyhľadanie segmentov. Používatelia teraz môžu vykonávať akcie, ako je sťahovanie alebo odstránenie, na viacerých segmentoch naraz. Zavádza sa nové rozhranie trendu s cieľom rýchlo identifikovať významné zmeny v segmentoch.    
  Ďalšie informácie nájdete v téme [Tvorba a správa segmentov](segments.md).

#### <a name="system-administration"></a>Správa systému

- **Customer Insights dostupné v Microsoft Dynamics 365 Online Government**

  S čoraz väčším počtom kanálov pre interakcie sú údaje o občanoch rozptýlené v nespočetných systémoch, čo vedie k osamoteným údajom a k fragmentovanému pohľadu na informácie o interakciách občanov. Bez úplného prehľadu o interakciách každého občana s rôznymi kanálmi je nemožné, aby sa dochádzalo k rozsiahlym modernizáciám v štátnej správe. Spoločnosť Microsoft sa zaviazala podporovať technologické potreby vlád, aby držala krok s očakávaniami občanov, pokiaľ ide o konzistentné a pohotové rozhrania.    
  S vlnou vydania 1 pre rok 2020 bude Dynamics 365 Customer Insights k dispozícii pre cloud vládneho spoločenstva (GCC), prostredie vytvorené tak, aby vyhovovalo vyšším potrebám vládnych agentúr Spojených štátov v oblasti dodržiavania predpisov. Agentúry získavajú jednotný pohľad na občanov a využívajú vopred pripravenú umelú inteligenciu na získavanie poznatkov, ktoré zlepšujú interakcie, posilňujú zamestnancov a transformujú komunity, pričom znižujú komplexnosť IT a spĺňajú normy a bezpečnostné normy USA. Dynamics 365 Government spĺňa náročné požiadavky Federálneho programu riadenia rizika a autorizácie USA (FedRAMP), čo federálnym agentúram Spojených štátov umožňuje využívať úspory nákladov a dôslednú bezpečnosť služby Microsoft Cloud.

## <a name="april-2020-updates"></a>Aktualizácie pre apríl 2020

Aktualizácie z apríla 2020 zahŕňajú niekoľko funkcií, aktualizácií výkonu a opráv chýb.

### <a name="new-and-updated-features-in-april-2020"></a>Nové a aktualizované funkcie v apríli 2020

#### <a name="activities"></a>Aktivity

- **Mapovanie entity aktivity na štandardný typ aktivity**
  
  Konfigurácia a ukladanie aktivít sú v súčasnosti založené na statickom návrhu, aby sa dali zobraziť na časovej osi. Sémantický význam aktivít, ktoré majú potenciál pre viacnásobné prípady použitia v modeloch AI, sa v súčasnosti v súčasnosti nevyužíva úplne. Plánujeme zvýšiť dynamiku časovej osi aktivity na základe typu aktivity a lepšieho sémantického porozumenia aktivitám. Cieľom tejto funkcie je identifikovať typ činnosti podľa definície v Common Data Model pre každú prijatú aktivitu.
  Ďalšie informácie nájdete v článku [Aktivity zákazníka](activities.md).

#### <a name="data-ingestion"></a>Prijímanie údajov

- **Príjem údajov v reálnom čase: aktivity**
  
  Príjem údajov v reálnom čase poskytuje údaje okamžite na spotrebu, až kým nasledujúce naplánované obnovenie nevytiahne tieto údaje zo zdroja údajov.    
  Ďalšie informácie sa dozviete v téme [Prijímanie údajov v reálnom čase](real-time-data-ingestion.md).

- **Zlepšenia v príprave údajov**
  
  Prečítajte si viac informácií o údajoch prijatých v entite. V súhrne údajov môžete porozumieť charakteristikám kvality údajov, ktoré môžu pomôcť podniknúť príslušné kroky.    
  Ďalšie informácie nájdete v téme [Skúmanie údajov entity](entities.md#exploring-a-specific-entitys-data).

- **Získanie analytických údajov z Dynamics 365 pomocou Common Data Service**
  
  Common Data Service je k dispozícii ako spôsob vytvárania zdrojov údajov. Existujúci zákazníci Dynamics 365 môžu prijímať analytické entity z Common Data Service do Customer Insights. Jeden zdroj údajov môže súčasne používať to isté spravované jazero Common Data Service v prostredí Customer Insights.    
  Viac informácií nájdete v časti [Pripojte sa k údajom v dátovom jazere spravovanom pomocou Common Data Service](connect-common-data-service-lake.md).

#### <a name="extensibility"></a>Rozšíriteľnosť

- **Export do LiveRamp**

  Aktivujte svoje údaje v riešení LiveRamp® a spojte sa s viac ako 500 platformami naprieč digitálnymi, sociálnymi a televíznymi ekosystémami. Použite svoje údaje v službe LiveRamp na zacielenie, potlačenie a prispôsobenie reklamných kampaní.    
  Ďalšie informácie nájdete v [konektore LiveRamp&reg;](export-liveramp.md).

- **Doplnok Customer Insights Teams**
  
  Bot poskytuje možnosti vyhľadávania pre zjednotené profily zákazníkov. Z výsledného profilu zákazníka sa zobrazí karta s až 15 poľami. Viaceré zhody vrátia zoznam výsledkov, kde si môžete vybrať profil.    
  Viac informácií nájdete v časti [Bot Teams pre Customer Insights](export-teams-bot.md).

#### <a name="measures"></a>Miery

- **Stránka zoznamu mier**
  
  Vylepšenia na stránke s mierami zahŕňajú podporu pre akcie týkajúce sa jednej miery a viacerých mier naraz. Ďalej nájdete vyhľadávacie pole na rýchle vyhľadanie a sledovanie mier.    
  Ďalšie informácie nájdete v téme [Tvorba a správa segmentov](segments.md).

- **Vylepšenia zložených mier**
  
  Používatelia môžu vytvárať, upravovať a odstraňovať miery založené na iných mierach. Napríklad miera konštruovaná na inej miere, ktorá bola skonštruovaná na tretej miere.

#### <a name="segments"></a>Segmenty

- **Iný operátor**
  
  Operátor In-set umožňuje segmentáciu pre zákazníkov podľa niekoľkých možných hodnôt reťazca. Predtým, ako bol tento operátor pridaný, ste museli skonštruovať takéto segmenty s viacerými podmienkami ALEBO. Operátor In-set vám to umožní s jedinou podmienkou.    
  Ďalšie informácie nájdete v téme [Tvorba a správa segmentov](segments.md).

#### <a name="system-administration"></a>Správa systému

- **Skopírujte nastavenia konfigurácie do nového prostredia**
  
  Skopírujte svoju konfiguráciu z jedného prostredia do druhého. Pri vytváraní nového prostredia môžete vybrať existujúce prostredie, z ktorého chcete skopírovať konfiguráciu. V súčasnosti podporujeme zdroje údajov, zjednotenie údajov, vzťahy, miery a segmenty, ktoré sa majú skopírovať. Poverenia zdroja údajov a skutočné údaje sa neskopírujú.    
  Ďalšie informácie nájdete v článku [Správa prostredí](manage-environments.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]