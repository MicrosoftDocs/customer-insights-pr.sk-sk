---
title: Integrácia webových údajov z prehľadov o interakcii s prehľadmi cieľových skupín
description: Prineste webové informácie o zákazníkoch z prehľadov o interakcii do prehľadov cieľových skupín.
ms.date: 06/24/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: c2789a7d1379e0cf56511b272a763c904d8a3d347058ea9e029aaff0f723a028
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 08/10/2021
ms.locfileid: "7033788"
---
# <a name="integrate-web-data-from-engagement-insights-with-audience-insights"></a>Integrácia webových údajov z prehľadov o interakcii s prehľadmi cieľových skupín

Zákazníci často vykonávajú svoje každodenné transakcie online pomocou webových lokalít. Funkcia prehľadov interakcií (verzia Preview) v službe Dynamics 365 Customer Insights predstavuje užitočné riešenie na integráciu webových údajov ako zdroja. Okrem transakčných, demografických údajov alebo údajov o správaní vidíme aktivity na webe v zjednotených zákazníckych profiloch. Tieto profily môžeme použiť na získanie ďalších prehľadov, ako sú segmenty, miery alebo predikcie aktivácie cieľových skupín.

Tento článok popisuje kroky, pomocou ktorých je možné preniesť údaje o aktivitách na webe vašich zákazníkov z prehľadov o interakcii do vášho existujúceho prostredia prehľadov cieľových skupín.

V tomto príklade predpokladáme prostredie, ktoré obsahuje zjednotené profily zákazníkov. Profily boli zjednotené so zdrojmi z prieskumov, maloobchodného predaja a systému predaja lístkov. Ukazuje tiež súvisiace aktivity zákazníkov. 

Teraz by sme chceli vedieť, či zákazník navštívi naše webové vlastnosti a porozumie ich aktivitám. Medzi aktivity patria napríklad navštívené webové stránky alebo zobrazené stránky produktov z odkazu prijatého v e-maile.

## <a name="prerequisites"></a>Predpoklady

Ak chcete integrovať údaje z prehľadov o interakcii, je potrebné splniť niekoľko predpokladov: 

- Integrovať súpravu SDK prehľadov o interakcii so svojím webom. Ďalšie informácie nájdete v téme [Prehľad zdrojov pre vývojárov](../engagement-insights/developer-resources.md).
- Export webových udalostí z prehľadov interakcií si vyžaduje prístup k účtu Azure Data Lake Storage, ktorý sa použije na prijatie údajov z webových udalostí do prehľadov cieľových skupín. Ďalšie informácie nájdete v téme [Export udalostí](../engagement-insights/export-events.md).

## <a name="configure-refined-events-in-engagement-insights"></a>Konfigurácia prepracovaných udalostí v prehľadoch o interakcii

Keď správca vybaví web pomocou prehľadov interakcií súpravy SDK, *základné udalosti* sa zhromaždia, keď si používateľ pozrie webovú stránku alebo niekde klikne. Základné udalosti zvyknú obsahovať početné podrobnosti. V závislosti od vášho prípadu použitia potrebujete iba podmnožinu údajov v základnej udalosti. Prehľady interakcií vám umožňujú vytvárať *prepracované udalosti* ktoré obsahujú iba vlastnosti základnej udalosti, ktorú vyberiete.     

Viac informácií nájdete v časti [Vytváranie a úprava spresnených udalostí](../engagement-insights/refined-events.md).

Čo treba zohľadniť pri vytváraní spresnených udalostí: 

- Zadajte zmysluplný názov pre spresnenú udalosť. V prehľadoch cieľových skupín sa použije ako názov aktivity.
- Vyberte aspoň nasledujúce vlastnosti na vytvorenie aktivity v prehľadoch cieľovej skupiny: 
    - Signal.Action.Name – označuje podrobnosti o aktivite.
    - Signal.User.Id – slúži na mapovanie s ID zákazníka.
    - Signal.View.Uri – používa sa ako webová adresa ako základ pre segmenty alebo miery.
    - Signal.Export.Id – používa sa ako primárny kľúč pre udalosti.
    - Signal.Timestamp – určuje dátum a čas pre aktivitu.

Vyberte filtre a zamerajte sa na udalosti a stránky, ktoré sú dôležité pre váš prípad použitia. V tomto príklade použijeme názov akcie „Zvýšenie úrovne e-mailu“.

## <a name="export-the-refined-web-events"></a>Export spresnených webových udalostí 

Po definovaní spresnenej udalosti musíte nakonfigurovať export údajov udalosti do úložiska Azure Data Lake Storage, ktoré je možné nastaviť ako zdroj údajov na prijatie prehľadov interakcií. Exporty prebiehajú neustále, keď udalosti prúdia z webu.

Ďalšie informácie nájdete v téme [Export udalostí](../engagement-insights/export-events.md).

## <a name="ingest-event-data-to-audience-insights"></a>Príjem údajov udalosti do prehľadov cieľových skupín

Teraz, keď ste definovali prepracovanú udalosť a nakonfigurovali jej export, pokračujeme k prijímaniu údajov do prehľadov publika. Musíte vytvoriť nový zdroj údajov na základe priečinka Common Data Model. Zadajte podrobnosti o účte úložiska, do ktorého udalosti exportujete. V súbore *default.cdm.json* vyberte prepracovanú udalosť, ktorú chcete prijať, a vytvorte entitu v prehľadoch cieľových skupín.

Ďalšie informácie nájdete v časti [Pripojenie k priečinku Common Data Model pomocou účtu Azure Data Lake](connect-common-data-model.md).


## <a name="relate-refined-event-data-as-an-activity-of-a-customer-profile"></a>Prepojenie prepracovaných údajov udalostí ako aktivity v profile zákazníka

Po dokončení príjmu entity môžete nakonfigurovať aktivitu pre profil zákazníka.

Ďalšie informácie nájdete v článku [Aktivity zákazníka](activities.md).

:::image type="content" source="media/web-event-activity.png" alt-text="Stránka Aktivity s rozbaleným panelom Upraviť aktivitu a vyplnenými poľami.":::

Nakonfigurujte novú aktivitu pomocou nasledujúceho mapovania: 

- **Primárny kľúč**: Signal.Export.Id, jedinečný identifikátor, ktorý je k dispozícii pre každý záznam udalosti v prehľadoch interakcií. Táto vlastnosť sa generuje automaticky.

- **Časová pečiatka**: Signal.Timestamp vo vlastnosti udalosti.

- **Udalosť**: Signal.Name, názov udalosti, ktorý chcete sledovať.

- **Webová adresa**: Signal.View.Uri s odkazom na URI stránky, ktorá udalosť vytvorila.

- **Detaily**: Signal.Action.Name na zastupovanie informácií, ktoré sa dajú priradiť k udalosti. Vybraná vlastnosť v tomto prípade indikuje, že udalosť je určená na zvýšenie úrovne e-mailov.

- **Typ aktivity**: V tomto príklade zvolíme existujúci typ aktivity WebLog. Tento výber ponúka užitočnú možnosť filtrovania na spustenie modelov predikcie alebo na vytvorenie segmentov na základe tohto typu aktivity.

- **Nastavenie vzťahu**: Toto dôležité nastavenie viaže aktivitu na existujúce profily zákazníkov. **Signal.User.Id** je identifikátor nakonfigurovaný v súprave SDK, ktorý sa má zhromažďovať, a ktorý sa týka ID používateľa v iných zdrojoch údajov, ktoré sú nakonfigurované v prehľadoch cieľovej skupiny. V tomto príklade konfigurujeme vzťah medzi Signal.User.Id a RetailCustomers:CustomerRetailId, čo je primárny kľúč, ktorý bol identifikovaný v rámci kroku mapy procesu zjednotenia údajov.

Po spracovaní aktivít môžete skontrolovať záznamy zákazníkov a otvoriť kartu zákazníka, aby ste si na časovej osi mohli pozrieť prehľady z prehľadov o interakcii. 

> [!TIP]
> Ak chcete nájsť ID zákazníka, ktorý má aktivitu v prehľadoch o interakcii, prejdite na položku **Entity** a zobrazte údaje pre entitu UnifiedActivity. ActivityTypeDisplay = WebLog obsahuje aktivitu prehľadov interakcií nakonfigurovanú v príklade vyššie. Skopírujte ID zákazníka pre jeden z týchto záznamov a pre toto ID na stránku **Zákazníci**.

## <a name="next-steps"></a>Ďalšie kroky

Teraz môžete vytvárať [segmenty](segments.md), [miery](measures.md) a [predikcie](predictions.md) a vytvoriť zmysluplné spojenie so svojimi zákazníkmi.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
