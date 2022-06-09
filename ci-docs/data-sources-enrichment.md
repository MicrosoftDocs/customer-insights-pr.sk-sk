---
title: Zdroj údajov obohatenie
description: Pred procesom zjednotenia údajov obohaťte zdroje údajov.
ms.date: 05/20/2022
ms.subservice: audience-insights
ms.topic: how-to
author: NimrodMagen
ms.author: nimagen
ms.reviewer: v-wendysmith
manager: shellyha
ms.openlocfilehash: 1225482c4bf432ed747537b2c9bec9ab0e692a51
ms.sourcegitcommit: b515120bebd2638f2639004422cee3cff42fbdf7
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 05/24/2022
ms.locfileid: "8800300"
---
# <a name="enrichment-for-data-sources-preview"></a>Obohatenie pre zdroje údajov (ukážka)

Použite údaje zo zdrojov, ako je Microsoft a ďalší partneri, na obohatenie údajov o zákazníkoch pred zjednotením údajov. Zdroj údajov obohatenia pomáhajú produkovať vyššiu úplnosť a kvalitu údajov, ktoré môžu pomôcť dosiahnuť lepšie výsledky, keď svoje údaje zjednotíte. Napríklad použitie normalizovaného a štandardizovaného formátu pre adresy zvyšuje kvalitu výsledkov zhody. Zoznam podporovaných obohatení nájdete v časti [podporované zdroj údajov možnosti obohatenia](#supported-data-source-enrichments).

## <a name="enrich-a-data-source"></a>Obohaťte zdroj údajov

Na vytváranie alebo úpravu obohatení musíte mať oprávnenia prispievateľa alebo správcu. Ďalšie informácie nájdete v časti [Povolenia](permissions.md).  

1. Ísť do **Údaje** > **Zjednotiť**. Vyberte entitu, ktorú chcete obohatiť, a vyberte jeden atribút ako primárny kľúč pre entitu. Viac informácií nájdete v časti [Vyberte primárny kľúč](map-entities.md#select-primary-key-and-semantic-type-for-attributes).

1. Prejdite do **Údaje** > **Zdroje údajov**.

1. Vyberte zvislú elipsu (&vellip;) vedľa zdroj údajov, ktorý chcete obohatiť a vybrať **Obohatiť**.

   :::image type="content" source="media/data_sources_enrich_discover.png" alt-text="Stránka obohatenia zdrojov údajov.":::

   The **Objavte** karta zobrazuje [podporované zdroj údajov možnosti obohatenia](#supported-data-source-enrichments).

1. Vyberte **Obohaťte moje údaje** na konfiguráciu obohatenia zdroj údajov. Názov výstupnej entity sa vyplní automaticky.

## <a name="supported-data-source-enrichments"></a>Podporované zdroj údajov obohatenia

Pre zdroje údajov sú v súčasnosti k dispozícii nasledujúce rozšírenia. Pozrite si podrobné kroky pre obohatenie, aby ste sa naučili, ako ho nakonfigurovať.

- [Vylepšené adresy](enrichment-enhanced-addresses.md)
- [Rozšírené firemné údaje](enrichment-enhanced-company-data.md)
- [Údaje o identite z LiveRamp](enrichment-liveramp.md)

## <a name="manage-existing-data-source-enrichments"></a>Spravujte existujúce zdroj údajov obohatenia

Prejdite na kartu **Moje obohatenia**, kde nájdete všetky nakonfigurované obohatenia.

Ak chcete zobraziť prístupné možnosti, označte položku obohatenia. Môžete tiež vybrať zvislú elipsu (&vellip;) na položke zoznamu, aby ste videli možnosti. Ak ste nakonfigurovali niekoľko obohatení, môžete ich rýchlo nájsť pomocou vyhľadávacieho poľa.

Môžete zobraziť, upraviť, spustiť alebo odstrániť obohatenie zdroj údajov. Viac informácií nájdete v časti [Spravujte existujúce obohatenia](enrichment-hub.md).