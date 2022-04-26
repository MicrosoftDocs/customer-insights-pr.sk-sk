---
title: Nové a prichádzajúce funkcie
description: Informácie o nových funkciách, vylepšeniach a opravách chýb.
ms.date: 04/05/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: skumm
manager: shellyha
ms.openlocfilehash: 2f081306271a170cf3e250fc1a193cedb70aeec6
ms.sourcegitcommit: 0363559a1af7ae16da2a96b09d6a4a8a53a8cbb8
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 04/05/2022
ms.locfileid: "8547691"
---
# <a name="whats-new-in-the-audience-insights-capability-of-dynamics-365-customer-insights"></a>Čo je nové v oblasti prehľadov cieľových skupín v Dynamics 365 Customer Insights

Sme radi, že môžeme oznámiť naše najnovšie aktualizácie! Tento článok sumarizuje funkcie verejnej ukážky, vylepšenia všeobecnej dostupnosti a aktualizácie funkcií. Ak chcete zobraziť dlhodobé plány pre funkcie, pozrite si [Plány vydaní Dynamics 365 a Power Platform](/dynamics365/release-plans/).

Aktualizácie zavádzame na základe jednotlivých regiónov. Do niektorých regiónov sa teda môžu niektoré funkcie dostať skôr než do ostatných. Pokiaľ nie je uvedené inak, nemusíte podniknúť žiadne kroky a my aplikáciu automaticky aktualizujeme bez prestojov.

> [!TIP]
> Ak chcete odoslať hlas pre požadované funkcie a návrhy produktov, prejdite na [portál aplikačných nápadov Dynamics 365](https://experience.dynamics.com/ideas/categories/?forum=79a8c474-4e35-e911-a971-000d3a4f3343&forumName=Dynamics%20365%20Customer%20Insights).


## <a name="march-2022-updates"></a>Aktualizácia z marca 2022

Aktualizácie v marci 2022 zahŕňajú nové funkcie, vylepšenia výkonu a opravy chýb.

### <a name="liveramp-abilitec-enrichment-preview"></a>LiveRamp AbiliTec obohatenie (ukážka)

LiveRamp poskytuje rozlíšenie identity a konsolidáciu údajov o zákazníkoch. Môžete mapovať osobné identifikátory vo svojich zákazníckych údajoch do grafu identity AbiliTec a prijímať AbiliTec ID. Tieto ID potom môžete použiť na lepšie zjednotenie údajov o vašich zákazníkoch.

Viac informácií nájdete v časti [Obohaťte zákaznícke profily o údaje o identite z LiveRamp (Preview)](enrichment-liveramp.md).

### <a name="organize-segments-and-measures-with-tags-and-filters"></a>Usporiadajte segmenty a miery pomocou značiek a filtrov
Ak vaša organizácia udržiava veľa segmentov alebo opatrení, nájsť ten správny môže byť niekedy náročné. Táto nová funkcia vám umožňuje organizovať zoznamy pomocou značiek a stĺpcov. Pomáha rýchlo a jednoducho nájsť údaje a prispôsobiť zobrazenia.

Viac informácií nájdete v časti [Práca so značkami a stĺpcami](work-with-tags-columns.md).

### <a name="enable-data-sharing-with-dataverse-when-using-your-own-storage-account"></a>Povoliť zdieľanie údajov s Dataverse pri používaní vlastného účtu úložiska

Ak vaše prostredie používa Azure Data Lake Storage na ukladanie údajov Customer Insights, zdieľanie údajov s Microsoft Dataverse potrebuje nejakú extra konfiguráciu.
Predtým ste mohli povoliť zdieľanie údajov iba s Dataverse keď boli vaše údaje uložené v našom jazere spravovaných údajov. 

Ďalšie informácie nájdete v časti [Povoliť zdieľanie údajov s Dataverse z vlastného Azure Data Lake Storage (Náhľad)](manage-environments.md#enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview).

### <a name="new-export-destinations-iterable-and-braze"></a>Nové exportné destinácie: Iterable a Braze

Pokračujeme v rozširovaní nášho ekosystému exportných destinácií o nové spojenia. Teraz môžete exportovať segmenty do Iterable a Braze a využívať ich aktivačné služby.

Viac informácií nájdete v časti [Exportovať segmenty do Iterable (ukážka)](export-iterable.md) a [Export segmentov do Braze (ukážka)](export-braze.md).

### <a name="improvements-to-marketo-and-google-ads-export"></a>Vylepšenia exportu Marketo a Google Ads

Zmena rozhraní API v pripojených službách vedie k aktualizáciám konektorov, aby fungovali spoľahlivo a hladko. Vydali sme niekoľko aktualizácií pre exporty do služieb Marketo a Google Ads:

- Google Ads: Nová verzia konektora na export služby Google Ads zjednodušuje overenie a teraz vám umožňuje automaticky vytvárať nové publiká Google Ads. 
- Marketo: Nová verzia exportného konektora Marketo poskytuje podporu pre Marketo ID, čo vám umožňuje vyhnúť sa duplicite údajov, aktualizovať existujúce záznamy a vytvárať nové záznamy v Marketo. 


## <a name="february-2022-updates"></a>Aktualizácie z februára 2022

Aktualizácie vo februári 2022 zahŕňajú nové funkcie, vylepšenia výkonu a opravy chýb.

### <a name="general-availability-for-prediction-models"></a>Všeobecná dostupnosť pre modely predikcia

Rozbalené predikcia modely vrátane **predplatné churn**, **churn** a **celoživotná hodnota zákazníka (CLV)** budú všeobecne dostupné ako súčasť Customer Insights. 

Ďalšie informácie nájdete v časti [Prehľad predpovedí](predictions-overview.md).

### <a name="new-data-source-integration-with-azure-synapse-analytics-preview"></a>Nové zdroj údajov: Integrácia s Azure Synapse Analytics (Náhľad)

Azure Synapse Analytics je podniková analytická služba, ktorá urýchľuje čas potrebný na získanie prehľadov naprieč dátovými skladmi a veľkými dátovými systémami.

Organizácie, ktoré už používajú Azure Synapse Analytics môže tieto údaje prijať do Customer Insights. 

Ďalšie informácie nájdete v časti [Pripojte Azure Synapse zdroj údajov (ukážka)](connect-synapse.md).

### <a name="liveramp-enrichment-preview"></a>LiveRamp obohatenie (ukážka)

LiveRamp poskytuje rozlíšenie identity a konsolidáciu údajov o zákazníkoch. Môžete mapovať osobné identifikátory vo svojich zákazníckych údajoch do grafu identity AbiliTec a prijímať AbiliTec ID. Tieto ID potom môžete použiť na lepšie zjednotenie údajov o vašich zákazníkoch.

Viac informácií nájdete v časti [Obohaťte zákaznícke profily o údaje o identite z LiveRamp (Preview)](enrichment-liveramp.md).

### <a name="enrichment-for-data-sources-preview"></a>Obohatenie pre zdroje údajov (ukážka)

Použite údaje zo zdrojov, ako je Microsoft a ďalší partneri, na obohatenie údajov o zákazníkoch pred zjednotením údajov. Zdroj údajov obohatenia pomáhajú produkovať vyššiu úplnosť a kvalitu údajov, ktoré môžu pomôcť dosiahnuť lepšie výsledky, keď svoje údaje zjednotíte.

Viac informácií nájdete v časti [Obohatenie pre zdroje údajov (ukážka)](data-sources-enrichment.md).

### <a name="change-owner-of-environment"></a>Zmeniť vlastníka prostredia

Aj keď v Customer Insights môže mať niekoľko používateľov povolenia správcu, vlastníkom prostredia je iba jeden používateľ. Vylepšené prostredie vám umožňuje zmeniť vlastníkov prostredia a nárokovať si vlastníctvo, ak bývalý vlastník opustil organizáciu. 

Viac informácií nájdete v časti [Zmeňte vlastníka prostredia](manage-environments.md#change-the-owner-of-an-environment).

### <a name="data-preparation-process-lists-corruption-reason-for-corrupted-records"></a>Proces prípravy údajov uvádza dôvod poškodenia pre poškodené záznamy

Príprava údajov teraz ukazuje dôvod poškodenia pre všetky polia s poškodenými údajmi. Informácie sa poskytujú na úrovni jednotlivých záznamov pre ľahkú identifikáciu. 

Viac informácií nájdete v časti [Poškodené zdroje údajov](entities.md#corrupted-data-sources).

### <a name="end-of-preview-for-reporting-features-in-the-engagement-insights-capability"></a>Koniec ukážky pre funkcie vytvárania prehľadov v funkcii štatistík interakcií

The Dynamics 365 Customer Insights ukážka možnosti interakcií sa skončila 15. februára 2022.  
Táto zmena znamená, že skúšobná verzia Customer Insights už nezahŕňa možnosť vytvárať zúženia ani iné funkcie vytvárania prehľadov.

Pozývame vás, aby ste preskúmali a zhodnotili mnohé ďalšie funkcie [Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/), platforma zákazníckych údajov spoločnosti Microsoft (CDP).    
 
Počas prechodného obdobia majú existujúci účastníci ukážky stále prístup k niektorým možnostiam a funkciám ukážky:

- Získanie kódu na inštrumentáciu webovej lokality alebo mobilnej aplikácie 
- Pozrite si udalosti a vlastnosti udalosti 
- Vylepšite zjednotené profily pomocou prijatých a spresnených udalostí, aby ste mohli využívať plnú hodnotu údajov o svojich zákazníkoch
  
Počas prechodného obdobia sa zachytené udalosti stále streamujú do pripojeného Data Lake. Po vypnutí tejto funkcie sa zastaví zdieľanie údajov medzi štatistikami interakcií a štatistikami publika a do pripojeného úložiska sa nebudú odosielať žiadne nové udalosti.
Ak máte otázky týkajúce sa konca ukážky funkcií, kontaktujte priamo svoj tím pre konto Microsoft. Váš účtovný tím vás bude informovať o pripravovaných spusteniach. 

## <a name="january-2022-updates"></a>Aktualizácie z januára 2022

Aktualizácie v januári 2022 zahŕňajú nové funkcie, vylepšenia výkonu a opravy chýb.

### <a name="sentiment-analysis-of-your-customers-feedback"></a>Analýza sentimentu spätnej väzby vášho zákazníka

Customer Insights poskytuje novú funkciu poháňanú umelou inteligenciou, ktorá syntetizuje sentiment zákazníkov a identifikuje špecifické obchodné aspekty ako príležitosti na cielené zlepšenia. Analýzou písomnej spätnej väzby vašich zákazníkov môžete získať presné informácie pri nízkych nákladoch. Analýza sentimentu založená na modeloch spracovania prirodzeného jazyka (NLP), ktoré generujú dva odvodené štatistiky pre každé ID zákazníka. Skóre sentimentu (od –5 do 5) a zoznam príslušných obchodných aspektov. 

Ďalšie informácie nájdete v časti [Analyzujte sentiment v spätnej väzbe zákazníkov (ukážka)](sentiment-analysis.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]