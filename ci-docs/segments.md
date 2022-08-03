---
title: Prehľad segmentov
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
ms.openlocfilehash: 4bcfbb50b893ca7e6ec4607d3c156a3c6979f775
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 07/18/2022
ms.locfileid: "9170700"
---
# <a name="segments-overview"></a>Prehľad segmentov

Segmenty vám umožňujú zoskupiť zákazníkov na základe demografických, transakčných alebo behaviorálnych atribútov. Segmenty môžete použiť na zacielenie reklamných kampaní, predajných aktivít a akcií podpory zákazníkov na dosiahnutie vašich obchodných cieľov.

Profily zákazníkov, ktoré zodpovedajú filtrom definície segmentu, sa označujú ako *členov* segmentu. Platia niektoré [obmedzenia služby](/dynamics365/customer-insights/service-limits).

## <a name="create-a-segment"></a>Vytvoriť segment

Vyberte spôsob vytvorenia segmentu na základe vášho cieľového publika.

# <a name="individual-consumers-b-to-c"></a>[Jednotliví spotrebitelia (firma a spotrebiteľ)](#tab/b2c)

- Komplexné segmenty s nástrojom na tvorbu segmentov: [Zostavte si svoj vlastný](segment-builder.md)
- Jednoduché segmenty s jedným operátorom: [Rýchly segment](segment-quick.md)
- Spôsob, ako nájsť podobných zákazníkov pomocou AI: [Podobní zákazníci](find-similar-customer-segments.md)
- Návrhy založené na AI založené na mierach alebo atribútoch: [Navrhované segmenty na základe meraní](suggested-segments.md)
- Návrhy založené na činnostiach: [Navrhované segmenty na základe aktivity zákazníka](suggested-segments-activity.md)

# <a name="business-accounts-b-to-b"></a>[Firemné obchodné vzťahy (firma a firma)](#tab/b2b)

- Jednoduché alebo zložité segmenty s nástrojom na tvorbu segmentov: [Zostavte si svoj vlastný](segment-builder.md)

---

## <a name="manage-existing-segments"></a>Spravovanie existujúcich segmentov

Choďte na **Segmenty** zobrazíte segmenty, ktoré ste vytvorili, ich stav a stav, počet členov a čas poslednej aktualizácie údajov. Zoznam segmentov môžete zoradiť podľa ľubovoľného stĺpca alebo pomocou vyhľadávacieho poľa nájsť segment, ktorý chcete spravovať.

Ak chcete zobraziť dostupné akcie, vyberte segment.

:::image type="content" source="media/segments-selected-segment.png" alt-text="Vybratý segment s rozbaľovacím zoznamom možností a dostupnými možnosťami." lightbox="media/segments-selected-segment.png":::

- [**vyhliadka**](#view-segment-details) podrobnosti o segmente vrátane trendu počtu členov a náhľadu členov segmentu.
- **Stiahnutie** zoznam členov ako súbor .CSV.
- **Úprava** segmentu na zmenu jeho vlastností.
- **Vytvorte duplikát** segmentu. Môžete sa rozhodnúť upraviť jeho vlastnosti ihneď alebo uložiť duplikát.
- [**Obnoviť**](#refresh-segments) segment, ktorý obsahuje najnovšie údaje.
- **Aktivácia** alebo **deaktivácia** segmentu. Neaktívne segmenty sa počas a [plánované obnovenie](system.md#schedule-tab) a mať **Postavenie** uvedené ako **Preskočené**, čo naznačuje, že sa ani nepokúsili o obnovenie. Aktívne segmenty sa obnovujú podľa ich typu: statické alebo dynamické.
- **Urobte statické** alebo **Urobte dynamický** typ segmentu. Statické segmenty sa musia obnoviť manuálne. Dynamické segmenty sa automaticky obnovujú počas obnovovania systému.
- [**Nájdite podobných zákazníkov**](find-similar-customer-segments.md) zo segmentu.
- **Premenovanie** segmentu.
- **Tag** do [spravovať značky](work-with-tags-columns.md#manage-tags) pre segment.
- [**Spravujte exporty**](#export-segments) zobraziť segmenty súvisiace s exportom a spravovať ich. [Ďalšie informácie o exportoch.](export-destinations.md)
- **Odstránenie** segmentu.
- **Stĺpce** do [prispôsobiť stĺpce](work-with-tags-columns.md#customize-columns) ten displej.
- **Filter** do [filtrovať podľa značiek](work-with-tags-columns.md#filter-on-tags).
- **Vyhľadať meno** na vyhľadávanie podľa názvu segmentu.

## <a name="view-segment-details"></a>Zobraziť podrobnosti segmentu

Na **Segmenty** vyberte segment na zobrazenie histórie spracovania a členov segmentu.

Horná časť stránky obsahuje graf trendov, ktorý vizualizuje zmeny v počte členov. Ak umiestnite kurzor myši nad údajové body, zobrazí sa počet členov k určitému dátumu. Zmeňte časový rámec vizualizácie.

:::image type="content" source="media/segment-time-range.png" alt-text="Časový rozsah segmentu.":::

Spodná časť obsahuje zoznam členov segmentu.

> [!NOTE]
> Polia, ktoré sa nachádzajú v tomto zozname, sú založené na atribútoch entít vášho segmentu.
>
>Zoznam predstavuje ukážku zodpovedajúcich členov segmentu a zobrazuje prvých 100 záznamov segmentu, aby ste ho mohli rýchlo vyhodnotiť a podľa potreby skontrolovať jeho definície. Ak chcete zobraziť všetky zodpovedajúce záznamy, [exportovať segment](export-destinations.md).

## <a name="refresh-segments"></a>Obnovenie segmentov

Segmenty je možné obnoviť podľa automatického plánu alebo manuálne na požiadanie. Ak chcete manuálne obnoviť jeden alebo viac segmentov, vyberte ich a vyberte **Obnoviť**.

Komu [naplánovať automatické obnovenie](system.md#schedule-tab), ísť do **Admin** > **Systém** > **Rozvrh**. Platia nasledujúce pravidlá:

- Všetky segmenty s typom **Dynamický** alebo **Rozšírenie** sa automaticky obnoví pri nastavenej kadencii. Po dokončení obnovy sa **Postavenie** označuje, či sa vyskytli nejaké problémy pri obnovovaní segmentu. The **Naposledy obnovené** zobrazuje časovú pečiatku posledného úspešného obnovenia. Ak sa vyskytne chyba, výberom chyby zobrazíte podrobnosti o tom, čo sa stalo.
- Segmenty s typom **Statické** *nebude* automaticky obnovovať. The **Naposledy obnovené** zobrazuje časovú pečiatku posledného manuálneho spustenia alebo obnovenia statický segment.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="export-segments"></a>Segmenty exportu

Ak chcete údaje ďalej využívať, exportujte segmenty do iných aplikácií. Exportujte segment zo stránky segmentov alebo [stránku exportu](export-destinations.md).

1. Choďte na **Segmenty** a vyberte segment, ktorý chcete exportovať.

1. Vyberte **Spravujte exporty**. Otvorí sa stránka **Exporty (verzia Preview) pre segment**. Zobrazte všetky nakonfigurované exporty zoskupené podľa toho, či obsahujú aktuálny segment alebo nie.

   1. Ak chcete vybratý segment pridať do exportu, **Upravte** príslušný export, vyberte príslušný segment a potom ho uložte. V prostrediach pre jednotlivých zákazníkov vyberte export v zozname a vyberte **Pridať segment** dosiahnuť rovnaký výsledok.

   1. Ak chcete vytvoriť nový export s vybraným segmentom, vyberte **Pridať export**. Ďalšie informácie o vytváraní exportu nájdete v článku [Nastavenie nového exportu](export-destinations.md#set-up-a-new-export).

1. Vyberte **Späť** na návrat na hlavnú stránku pre segmenty.

## <a name="track-usage-of-a-segment"></a>Sledujte využitie segmentu

Ak používate segmenty v aplikáciách, ktoré sú založené na tom istom Microsoft Dataverse organizácie, ktorá je prepojená s Customer Insights, môžete sledovať využitie segmentu. Pre [Segmenty Customer Insights používané na cestách zákazníkov Dynamics 365 Marketing](/dynamics365/marketing/real-time-marketing-ci-profile), systém vás informuje o využití daného segmentu.

Pri úprave segmentu, ktorý sa používa v prostredí Customer Insights alebo v činnosť zákazníka v marketingu, sa banner v [tvorca segmentov](segment-builder.md) vás informuje o závislostiach. Skontrolujte podrobnosti o závislosti priamo z bannera alebo výberom **Použitie** v nástroji na tvorbu segmentov.

The **Použitie segmentu** panel zobrazuje podrobnosti o použití tohto segmentu v Dataverse -založené aplikácie. Pre segmenty používané v cestách zákazníkov nájdete odkaz na kontrolu cesty v Marketingu, kde sa tento segment používa. Ak máte povolenia na prístup k aplikácii Marketing, pozrite si tam ďalšie podrobnosti.

:::image type="content" source="media/segment-usage-pane.png" alt-text="Bočný panel s podrobnosťami o použití segmentu v nástroji na tvorbu segmentov.":::

Systém vás informuje o použití sledovaného segmentu, keď sa ho pokúsite odstrániť. Ak sa segment, ktorý sa chystáte odstrániť, použije v činnosť zákazníka v marketingu, táto cesta sa zastaví pre všetkých používateľov v segmente. Ak je cesta súčasťou marketingovej kampane, odstránenie ovplyvní samotnú kampaň. Napriek upozorneniam však stále môžete segment odstrániť.

:::image type="content" source="media/segment-usage-delete.png" alt-text="Dialógové okno na potvrdenie vymazania segmentu, keď sa segment používa v a Dataverse aplikácie.":::

### <a name="supported-apps"></a>Podporované aplikácie

Využitie je momentálne sledované nasledovne Dataverse aplikácie založené na:

- [Cesty zákazníkov v Dynamics 365 Marketing](/dynamics365/marketing/real-time-marketing-ci-profile)

[!INCLUDE [footer-include](includes/footer-banner.md)]
