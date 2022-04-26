---
title: Pochopte a spravujte opatrenia
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
ms.openlocfilehash: ef10f480086ccac4fa5c6c58818e35ecae67532c
ms.sourcegitcommit: 9ef2cf99b847e7bd8f890f83d84b3a4045aaf8cc
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 04/01/2022
ms.locfileid: "8529696"
---
# <a name="measures-overview"></a>Prehľad opatrení

Opatrenia vám pomôžu lepšie pochopiť správanie zákazníkov a výkonnosť podniku. Pozerajú sa na príslušné hodnoty zo [zjednotených profilov](data-unification.md). Firma chce napríklad vidieť *celkové výdavky na zákazníka*, aby pochopila históriu nákupov tohto zákazníka alebo zistila *celkové predaje spoločnosti* s cieľom porozumieť agregovaným výnosom v celej firme.  

Opatrenia sú vytvorené [pomocou nástroja na tvorbu opatrení](measure-builder.md), platforma na dopytovanie údajov s rôznymi operátormi a jednoduchými možnosťami mapovania. Umožňujú vám filtrovať údaje, zoskupovať výsledky, zisťovať [cesty vzťahov medzi entitami](relationships.md) a zobrazovať ukážku výstupu. Môžeš [použiť preddefinované šablóny](measure-templates.md) efektívne konfigurovať bežne používané opatrenia.

Použite nástroj na tvorbu mier na plánovanie obchodných aktivít dotazovaním na údaje o zákazníkoch a získavaním prehľadov. Napríklad vytvorenie miery *celkové výdavky na zákazníka* a *celková návratnosť na zákazníka* pomáha identifikovať skupinu zákazníkov s vysokými výdavkami, ale s vysokou návratnosťou. Môžeš [vytvoriť segment](segments.md) na základe týchto opatrení riadiť ďalšie najlepšie akcie.

## <a name="manage-your-measures"></a>Spravovanie mier

Zoznam opatrení nájdete na stránke **Miery**.

Nájdete informácie o type miery, jej tvorcovi, dátume vytvorenia, statuse a stave. Keď vyberiete opatrenie zo zoznamu, môžete si pozrieť verziu Preview výstupu a stiahnuť súbor vo formáte CSV.

:::image type="content" source="media/measures-actions.png" alt-text="Akcie na spravovanie jednotlivých opatrení."lightbox="media/measures-actions.png":::

Keď vyberiete mieru, sú k dispozícii nasledujúce akcie:

- **Upravte** konfiguráciu miery.
- **Duplicitné** opatrenie. Môžete sa rozhodnúť okamžite upraviť jeho vlastnosti alebo duplikát jednoducho uložiť.
- **Obnovte** mieru na základe najnovších údajov. Ak chcete obnoviť všetky merania súčasne, vyberte všetky opatrenia a potom **Obnoviť**.
- **Premenujte** mieru.
- **Aktivujte** alebo **Deaktivujte**. Neaktívne miery sa počas [plánovaného obnovenia](system.md#schedule-tab) neobnovujú.
- **Tag** do [spravovať značky](work-with-tags-columns.md#manage-tags) pre segment.
- **Odstráňte** mieru.

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

## <a name="next-step"></a>Ďalší krok

Existujúce opatrenia môžete použiť na vytvorenie [zákazníckeho segmentu](segments.md).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
