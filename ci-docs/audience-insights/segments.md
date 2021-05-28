---
title: Segmenty v prehľade cieľových skupín
description: Prehľad o segmentoch a o tom, ako ich vytvárať a spravovať.
ms.date: 05/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: a7fa6515bd6e79dedfb21aa0f0b8e24b873a6771
ms.sourcegitcommit: 8341fa964365c185b65bc4b71fc0c695ea127dc0
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 05/14/2021
ms.locfileid: "6034031"
---
# <a name="segments-overview"></a>Prehľad segmentov

Segmenty vám umožňujú zoskupiť zákazníkov na základe demografických, transakčných alebo behaviorálnych atribútov. Segmenty môžete použiť na zacielenie reklamných kampaní, predajných aktivít a akcií podpory zákazníkov na dosiahnutie vašich obchodných cieľov.

Profily zákazníkov, ktoré zodpovedajú filtrom definície segmentu, sa označujú ako *členovia* segmentu. Platia niektoré [obmedzenia služby](service-limits.md).

## <a name="create-a-new-segment"></a>Vytvorenie nového segmentu

Existuje niekoľko spôsobov, ako vytvoriť nový segment: 

- Komplexný segment s nástrojom na tvorbu segmentov: [Prázdny segment](segment-builder.md#create-a-new-segment)
- Jednoduché segmenty s jedným operátorom: [Rýchly segment](segment-builder.md#quick-segments)
- Spôsob hľadania podobných zákazníkov pomocou technológie AI: [Podobní zákazníci](find-similar-customer-segments.md)
- Návrhy založené na AI založené na opatreniach alebo atribútoch: [Navrhované segmenty na zlepšenie opatrení](suggested-segments.md)
- Návrhy založené na činnostiach: [Navrhované segmenty na základe aktivity zákazníka](suggested-segments-activity.md)

## <a name="get-insights-on-existing-segments"></a>Získajte prehľad o existujúcich segmentoch

Objavte ďalšie informácie o svojich existujúcich segmentoch pomocou [Prehľadov segmentov](segment-insights.md). Zistite, čo odlišuje dva segmenty alebo čo majú spoločné.

## <a name="find-similar-customers"></a>Nájsť podobných zákazníkov

Vyhľadajte pomocou umelej inteligencie zákazníkov, ktorí sú podobní členom vybraného segmentu. Ďalšie informácie nájdete v téme [podobní zákazníci](find-similar-customer-segments.md).

## <a name="manage-existing-segments"></a>Spravovanie existujúcich segmentov

Choďte na stránku **Segmenty** a zobrazte si všetky svoje uložené segmenty a spravujte ich.

Každý segment je reprezentovaný radom, ktorý obsahuje ďalšie informácie o segmente.

> [!div class="mx-imgBorder"]
> ![Možnosti správy existujúceho segmentu](media/segments-selected-segment.png "Možnosti správy existujúceho segmentu")

Po výbere segmentu sú k dispozícii nasledujúce akcie:

- **Zobrazenie** podrobností o segmente vrátane trendu počtu členov a ukážky členov segmentu.
- **Úprava** segmentu na zmenu jeho vlastností.
- **Vytvorte duplikát** segmentu. Môžete sa rozhodnúť okamžite upraviť jeho vlastnosti alebo duplikát jednoducho uložiť.
- **Obnova** segmentu, ktorý obsahuje najnovšie údaje.
- **Aktivácia** alebo **deaktivácia** segmentu. Segmenty majú dva možné stavy – aktívny alebo neaktívny. Tieto stavy sa hodia pri úprave segmentu. Pre neaktívne segmenty existuje definícia segmentu, zatiaľ však neobsahuje žiadnych zákazníkov. Keď aktivujete segment, jeho stav sa zmení z „neaktívneho“ na „aktívny“ a začne hľadať zákazníkov, ktorí zodpovedajú definícii segmentu. Ak je [plánované obnovenie](system.md#schedule-tab) nakonfigurované, neaktívne segmenty majú **Postavenie** uvedené ako **Preskočené**, čo naznačuje, že k obnoveniu ani nedošlo. Keď je neaktívny segment aktivovaný, obnoví sa a bude zahrnutý do plánovaných aktualizácií.
  Prípadne môžete použiť funkciu **Naplánovať neskôr** v rozbaľovacej ponuke **Aktivácia/Deaktivácia** na určenie budúceho dátumu a času aktivácie a deaktivácie konkrétneho segmentu.
- **Premenovanie** segmentu.
- **Stiahnutie** zoznam členov ako súbor .CSV.
- Možnosť **Pridať do** odošle zoznam ID zákazníkov v segmente na spracovanie v inej aplikácii.
- **Odstránenie** segmentu.

## <a name="refresh-segments"></a>Obnovenie segmentov

Výberom možnosti **Obnoviť všetko** na stránke **Segmenty** môžete obnoviť všetky segmenty naraz alebo môžete jeden alebo viac segmentov, keď ich vyberiete a následne vyberiete **Obnoviť** z možností. Prípadne môžete nakonfigurovať opakujúce sa obnovovanie v ponuke **Správca** > **Systém** > **Plán**.

> [!TIP]
> Existuje [šesť druhov stavov](system.md#status-types) pre úlohy/procesy. Okrem toho väčšina procesov [závisí na ďalších nadväzujúcich procesoch](system.md#refresh-policies). Môžete si vybrať stav procesu a zobraziť podrobnosti o priebehu celej úlohy. Po výbere **Pozrieť detaily** pre jednu z úloh úlohy nájdete ďalšie informácie: čas spracovania, posledný dátum spracovania a všetky chyby a varovania spojené s úlohou.

## <a name="view-processing-history-and-segment-members"></a>Zobrazenie histórie spracovania a členov segmentu

Ak chcete zobraziť konsolidované údaje o segmente, prečítajte si podrobnosti.

Na stránke **Segmenty** vyberte segment, ktorý chcete skontrolovať.

Horná časť stránky obsahuje graf trendov, ktorý vizualizuje zmeny v počte členov. Ak umiestnite kurzor myši nad údajové body, zobrazí sa počet členov k určitému dátumu.

Môžete aktualizovať časový rámec vizualizácie.

> [!div class="mx-imgBorder"]
> ![Časový rozsah segmentu](media/segment-time-range.png "Časový rozsah segmentu")

Spodná časť obsahuje zoznam členov segmentu.

> [!NOTE]
> Polia, ktoré sa nachádzajú v tomto zozname, sú založené na atribútoch entít vášho segmentu.
>
>Zoznam predstavuje ukážku zodpovedajúcich členov segmentu a zobrazuje prvých 100 záznamov segmentu, aby ste ho mohli rýchlo vyhodnotiť a podľa potreby skontrolovať jeho definície. Ak chcete zobraziť všetky zodpovedajúce záznamy, musíte [exportovať segment](export-destinations.md).

[!INCLUDE[footer-include](../includes/footer-banner.md)] 
