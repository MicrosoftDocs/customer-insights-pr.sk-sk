---
title: Segmenty v Customer Insights
description: Prehľad o segmentoch a o tom, ako ich vytvárať a spravovať.
ms.date: 05/20/2022
ms.subservice: audience-insights
ms.topic: overview
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-customers-page
- ci-enrichment-details
- ci-segments
- ci-segment-details
- customerInsights
ms.openlocfilehash: d616ec8273115203dddb59334a348c66e72fa678
ms.sourcegitcommit: b515120bebd2638f2639004422cee3cff42fbdf7
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 05/24/2022
ms.locfileid: "8800761"
---
# <a name="segments-overview"></a>Prehľad segmentov

Segmenty vám umožňujú zoskupiť zákazníkov na základe demografických, transakčných alebo behaviorálnych atribútov. Segmenty môžete použiť na zacielenie reklamných kampaní, predajných aktivít a akcií podpory zákazníkov na dosiahnutie vašich obchodných cieľov.

Profily zákazníkov, ktoré zodpovedajú filtrom definície segmentu, sa označujú ako *členovia* segmentu. Platia niektoré [obmedzenia služby](/dynamics365/customer-insights/service-limits).

## <a name="create-a-new-segment"></a>Vytvorenie nového segmentu

Existuje niekoľko spôsobov, ako vytvoriť nový segment: 

# <a name="individual-consumers-b-to-c"></a>[Jednotliví spotrebitelia (firma a spotrebiteľ)](#tab/b2c)

- Komplexný segment s nástrojom na tvorbu segmentov: [Zostavte si vlastný](segment-builder.md#create-a-new-segment) 
- Jednoduché segmenty s jedným operátorom: [Rýchly segment](segment-builder.md#quick-segments) 
- Spôsob hľadania podobných zákazníkov pomocou technológie AI: [Podobní zákazníci](find-similar-customer-segments.md) 
- Návrhy založené na AI založené na opatreniach alebo atribútoch: [Navrhované segmenty na zlepšenie opatrení](suggested-segments.md) 
- Návrhy založené na činnostiach: [Navrhované segmenty na základe aktivity zákazníka](suggested-segments-activity.md) 

# <a name="business-accounts-b-to-b"></a>[Firemné obchodné vzťahy (firma a firma)](#tab/b2b)

- Komplexný segment s nástrojom na tvorbu segmentov: [Zostavte si vlastný](segment-builder.md#create-a-new-segment)

---

## <a name="manage-existing-segments"></a>Spravovanie existujúcich segmentov

Choďte na **Segmenty** zobrazíte všetky svoje uložené segmenty a spravujete ich.

Každý segment je reprezentovaný radom, ktorý obsahuje ďalšie informácie o segmente.

:::image type="content" source="media/segments-selected-segment.png" alt-text="Vybratý segment s rozbaľovacím zoznamom možností a dostupnými možnosťami." lightbox="media/segments-selected-segment.png":::

Keď vyberiete segment, sú k dispozícii nasledujúce akcie:

- **Zobrazenie** podrobností o segmente vrátane trendu počtu členov a ukážky členov segmentu.
- **Stiahnutie** zoznam členov ako súbor .CSV.
- **Úprava** segmentu na zmenu jeho vlastností.
- **Vytvorte duplikát** segmentu. Môžete sa rozhodnúť upraviť jeho vlastnosti ihneď alebo uložiť duplikát.
- **Obnova** segmentu, ktorý obsahuje najnovšie údaje.
- **Aktivácia** alebo **deaktivácia** segmentu. Pre neaktívne segmenty existuje definícia segmentu, zatiaľ však neobsahuje žiadnych zákazníkov. Aktívny segment hľadá zákazníkov, ktorí zodpovedajú definícii segmentu. Ak je [plánované obnovenie](system.md#schedule-tab) nakonfigurované, neaktívne segmenty majú **Postavenie** uvedené ako **Preskočené**, čo naznačuje, že k obnoveniu ani nedošlo. Keď je neaktívny segment aktivovaný, obnoví sa a bude zahrnutý do plánovaných aktualizácií.
  Prípadne môžete použiť funkciu **Naplánovať neskôr** v rozbaľovacej ponuke **Aktivácia/Deaktivácia** na určenie budúceho dátumu a času aktivácie a deaktivácie konkrétneho segmentu.
- **[Nájdite podobných zákazníkov](find-similar-customer-segments.md)** zo segmentu.
- **Premenovanie** segmentu.
- **Tag** do [spravovať značky](work-with-tags-columns.md#manage-tags) pre segment.
- **Stiahnutie** zoznam členov ako súbor .CSV.
- **Spravujte exporty**, ak chcete zobraziť segmenty súvisiace s exportom a spravovať ich. [Ďalšie informácie o exportoch.](export-destinations.md)
- **Odstránenie** segmentu.
- **Stĺpce** do [prispôsobiť stĺpce](work-with-tags-columns.md#customize-columns) ten displej.
- **Filter** do [filtrovať podľa značiek](work-with-tags-columns.md#filter-on-tags).
- **Vyhľadať meno** na vyhľadávanie podľa názvu segmentu.

## <a name="refresh-segments"></a>Obnovenie segmentov

Výberom možnosti **Obnoviť všetko** na stránke **Segmenty** môžete obnoviť všetky segmenty naraz alebo môžete jeden alebo viac segmentov, keď ich vyberiete a následne vyberiete **Obnoviť** z možností. Prípadne môžete nakonfigurovať opakujúce sa obnovovanie v ponuke **Správca** > **Systém** > **Plán**. Keď je nakonfigurované opakované obnovenie, platia nasledujúce pravidlá:

- Všetky segmenty s typom **Dynamický** alebo **Rozšírenie** sa automaticky obnoví pri nastavenej kadencii. Po dokončení obnovy **Postavenie** označuje, či sa vyskytli nejaké problémy pri obnovovaní segmentu. The **Naposledy obnovené** zobrazuje časovú pečiatku posledného úspešného obnovenia. Ak sa vyskytne chyba, výberom chyby zobrazíte podrobnosti o tom, čo sa stalo.
- Segmenty s typom **Statické** *nebude* automaticky obnovovať. The **Naposledy obnovené** zobrazuje časovú pečiatku posledného spustenia alebo manuálnej obnovy statických segmentov.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="export-segments"></a>Segmenty exportu

Segment môžete exportovať zo stránky so segmentmi alebo zo [stránky s exportom](export-destinations.md). 

1. Prejdite na stránku **Segmenty**.

1. Vyberte zvislú elipsu (&vellip;) pre segment, ktorý chcete exportovať.

1. Z rozbaľovacieho zoznamu akcií si vyberte možnosť **Spravovať exporty**.

1. Otvorí sa stránka **Exporty (verzia Preview) pre segment**. Všetky nakonfigurované exporty môžete vidieť zoskupené podľa toho, či obsahujú aktuálny segment alebo nie.

   1. Ak chcete vybratý segment pridať do exportu, **Upravte** príslušný export, vyberte príslušný segment a potom ho uložte. V prostrediach pre jednotlivých zákazníkov môžete namiesto toho vybrať export v zozname a vybrať **Pridať segment** dosiahnuť rovnaký výsledok.

   1. Ak chcete vytvoriť nový export s vybraným segmentom, vyberte **Pridať export**. Ďalšie informácie o vytváraní exportu nájdete v článku [Nastavenie nového exportu](export-destinations.md#set-up-a-new-export).

1. Vyberte **Späť** na návrat na hlavnú stránku pre segmenty.

## <a name="track-usage-of-a-segment"></a>Sledujte využitie segmentu

Ak v aplikáciách používate segmenty, ktoré sú založené na tom istom Microsoft Dataverse organizácie, ktorá je prepojená s Customer Insights, môžete sledovať využitie segmentu. Pre [Segmenty Customer Insights používané na cestách zákazníkov Dynamics 365 Marketing](/dynamics365/marketing/real-time-marketing-ci-profile), systém vás informuje o využití daného segmentu.

Pri úprave segmentu, ktorý sa používa v prostredí Customer Insights alebo v činnosť zákazníka v marketingu, sa banner v [tvorca segmentov](segment-builder.md) vás informuje o závislostiach. Podrobnosti závislosti môžete skontrolovať priamo z bannera alebo výberom **Použitie** v nástroji na tvorbu segmentov.

The **Použitie segmentu** panel zobrazuje podrobnosti o použití tohto segmentu v Dataverse -založené aplikácie. Pre segmenty používané v cestách zákazníkov nájdete odkaz na kontrolu cesty v Marketingu, kde sa tento segment používa. Ak máte povolenia na prístup k aplikácii Marketing, môžete tam získať ďalšie podrobnosti.

:::image type="content" source="media/segment-usage-pane.png" alt-text="Bočný panel s podrobnosťami o použití segmentu v nástroji na tvorbu segmentov.":::

Systém vás informuje o použití sledovaného segmentu, keď sa ho pokúsite odstrániť. Ak sa segment, ktorý sa chystáte odstrániť, použije v činnosť zákazníka v marketingu, táto cesta sa zastaví pre všetkých používateľov v segmente. Ak je cesta súčasťou marketingovej kampane, vymazanie ovplyvní samotnú kampaň. Napriek upozorneniam však stále môžete segment odstrániť.

:::image type="content" source="media/segment-usage-delete.png" alt-text="Dialógové okno na potvrdenie vymazania segmentu, keď sa segment používa v a Dataverse aplikácie.":::

### <a name="supported-apps"></a>Podporované aplikácie

Využitie je momentálne sledované nasledovne Dataverse aplikácie založené na:

- [Cesty zákazníkov v Dynamics 365 Marketing](/dynamics365/marketing/real-time-marketing-ci-profile)

## <a name="view-processing-history-and-segment-members"></a>Zobrazenie histórie spracovania a členov segmentu

Ak chcete zobraziť konsolidované údaje o segmente, prečítajte si podrobnosti.

Na stránke **Segmenty** vyberte segment, ktorý chcete skontrolovať.

Horná časť stránky obsahuje graf trendov, ktorý vizualizuje zmeny v počte členov. Ak umiestnite kurzor myši nad údajové body, zobrazí sa počet členov k určitému dátumu.

Môžete aktualizovať časový rámec vizualizácie.

> [!div class="mx-imgBorder"]
> ![Časový rozsah segmentu.](media/segment-time-range.png "Časový rozsah segmentu")

Spodná časť obsahuje zoznam členov segmentu.

> [!NOTE]
> Polia, ktoré sa nachádzajú v tomto zozname, sú založené na atribútoch entít vášho segmentu.
>
>Zoznam predstavuje ukážku zodpovedajúcich členov segmentu a zobrazuje prvých 100 záznamov segmentu, aby ste ho mohli rýchlo vyhodnotiť a podľa potreby skontrolovať jeho definície. Ak chcete zobraziť všetky zodpovedajúce záznamy, musíte [exportovať segment](export-destinations.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
