---
title: Prehľad opatrení
description: Zistite, ako opatrenia pomáhajú analyzovať a odrážať výkonnosť vášho podnikania.
ms.date: 03/24/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: v-wendysmith
ms.author: wameng
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-measures
- ci-measure-builder
- ci-measure-template
- ci-enrichment-details
- customerInsights
ms.openlocfilehash: ead57ccbdcaf9f86ee54d1f15de71a63f2e1081b
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 07/18/2022
ms.locfileid: "9170868"
---
# <a name="measures-overview"></a>Prehľad opatrení

Opatrenia vám pomôžu lepšie pochopiť správanie zákazníkov a výkonnosť podniku. Pozerajú sa na príslušné hodnoty zo [zjednotených profilov](data-unification.md). Firma chce napríklad vidieť *celkové výdavky na zákazníka*, aby pochopila históriu nákupov tohto zákazníka alebo zistila *celkové predaje spoločnosti* s cieľom porozumieť agregovaným výnosom v celej firme.

Vytvorte opatrenia na plánovanie obchodných aktivít dotazovaním sa na údaje o zákazníkoch a extrahovaním štatistík. Vytvorte napríklad mieru *celkové výdavky na zákazníka* a *celková návratnosť na zákazníka* pomôcť identifikovať skupinu zákazníkov s vysokými výdavkami a zároveň vysokou návratnosťou. potom [vytvoriť segment](segments.md) na základe týchto opatrení riadiť ďalšie najlepšie akcie.

## <a name="create-a-measure"></a>Vytvorenie miery

Vyberte spôsob vytvorenia miery na základe vašej cieľovej skupiny.

# <a name="individual-consumers-b-to-c"></a>[Jednotliví spotrebitelia (firma a spotrebiteľ)](#tab/b2c)

- Od začiatku s nástrojom na tvorbu opatrení: [Zostavte si svoj vlastný](measure-builder.md).
- Z bežne používaných opatrení: [Použite preddefinované šablóny](measure-templates.md).

# <a name="business-accounts-b-to-b"></a>[Firemné obchodné vzťahy (firma a firma)](#tab/b2b)

Od začiatku s nástrojom na tvorbu opatrení: [Zostavte si svoj vlastný](measure-builder.md).

---

## <a name="manage-existing-measures"></a>Spravujte existujúce opatrenia

Choďte na **Opatrenia** zobrazíte miery, ktoré ste vytvorili, ich stav, typ merania a čas poslednej aktualizácie údajov. Zoznam mier môžete zoradiť podľa ľubovoľného stĺpca alebo pomocou vyhľadávacieho poľa nájsť mieru, ktorú chcete spravovať.

Výberom položky vedľa miery zobrazíte dostupné akcie. Ak chcete zobraziť ukážku výstupu a stiahnuť súbor CSV, vyberte názov merania.

:::image type="content" source="media/measures-actions.png" alt-text="Akcie na spravovanie jednotlivých opatrení."lightbox="media/measures-actions.png":::

- **Upraviť** opatrenie na zmenu jeho vlastností.
- **Obnoviť** opatrenie obsahuje najnovšie údaje.
- **Premenujte** mieru.
- **Aktivovať** alebo **Deaktivovať** opatrenie. Neaktívne opatrenia sa počas a [plánované obnovenie](system.md#schedule-tab) a mať **Postavenie** uvedené ako **Preskočené**, čo naznačuje, že sa ani nepokúsili o obnovenie.
- **Tag** do [spravovať značky](work-with-tags-columns.md#manage-tags) za opatrenie.
- **Odstráňte** mieru.
- **Stĺpce** do [prispôsobiť stĺpce](work-with-tags-columns.md#customize-columns) ten displej.
- **Filter** do [filtrovať podľa značiek](work-with-tags-columns.md#filter-on-tags).
- **Vyhľadať meno** na vyhľadávanie podľa názvu miery.

## <a name="refresh-measures"></a>Obnoviť opatrenia

Opatrenia môžu byť obnovené podľa automatického plánu alebo manuálne na požiadanie. Ak chcete manuálne obnoviť jedno alebo viac taktov, vyberte ich a vyberte **Obnoviť**. Komu [naplánovať automatické obnovenie](system.md#schedule-tab), ísť do **Admin** > **Systém** > **Rozvrh**.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
