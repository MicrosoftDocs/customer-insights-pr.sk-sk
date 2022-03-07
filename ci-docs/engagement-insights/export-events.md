---
title: Exportujte spresnené udalosti
description: Ako exportovať spresnené a základné udalosti.
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 10/01/2021
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: d062e2982c1041454b083630404f2b68f0da9669
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 02/16/2022
ms.locfileid: "8232907"
---
# <a name="export-events"></a>Export udalostí

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Udalosť predstavuje správanie používateľa. Zaznamená sa, keď používateľ zobrazí stránku (aktivita zobrazenia) alebo interaguje s obsahom (aktivita akcie). Keď sa môžete rozhodnúť, ktoré vlastnosti údajov sa budú zobrazovať v prehľade, toto virtuálne zobrazenie údajov sa nazýva *spresnená udalosť*. Ďalšie informácie nájdete v téme [Tvorba a úprava udalostí](refined-events.md).

- Udalosti a spresnené udalosti môžete exportovať do externého úložiska. 
- Exporty sú priamym dátovým postupom. Prehľad nemôžete znova naplniť. 
- Export má pevné schémy. Ak k udalosti pridáte vlastné vlastnosti, nebudú zahrnuté. Budete musieť vytvoriť nový export.

## <a name="prerequisites"></a>Predpoklady

Pred nastavením exportu musíte mať prístup a aktívne predplatné na portáli Azure. Počas procesu exportu budete potrebovať informácie o účte úložiska. 

### <a name="create-an-azure-data-lake-storage-gen-2-accounts"></a>Vytvorte si účty Azure Data Lake Storage Gen 2

1. Prihláste sa na portál Azure a [vytvoriť si nový účet úložiska](/azure/storage/common/storage-account-create). 

1. Uistite sa, že ste aktivovali možnosť **Hierarchický názov** na karte **Rozšírený**. 

   :::image type="content" source="media/enable-hierarchical-namespace.png" alt-text="Aktivácia hierarchického názvu na karte Rozšírené.":::

1. Po nasadení prejdite do novovytvoreného účtu úložiska. Na navigačnej table stlačte možnosť **Nastavenia** > **Prístupové kľúče**. 

1. Skopírujte **Názov účtu** a **Kľúč** na použitie pri vytváraní nového exportu.
   :::image type="content" source="media/storage-account-access-keys.png" alt-text="Prístupové kľúče v účte úložiska.":::

## <a name="export-events"></a>Exportovať udalosti

Existujú dva spôsoby, ako vyvolať dialógové okno **Exportovať udalosti**: 
- Prejdite do **Údaje** > **Exporty** a stlačte možnosť **Nový export**.
- Prejdite na **Údaje** > **Udalosti**, vyberte možnosť **Viac [...]** vedľa udalosti, ktorú chcete exportovať, a vyberte možnosť **Exportovať** z rozbaľovacej ponuky. 

:::image type="content" source="media/new-export.png" alt-text="Vytvorenie nového exportu.":::

Prevedieme vás krokmi, ako vytvoriť export:

1. Zadajte **Názov exportu** a potom vyberte **Ďalej**.

1. Z rozbaľovacieho zoznamu **Výber udalostí** si vyberte základné udalosti a vylepšené udalosti, ktoré sa majú zahrnúť do exportu. 

1. V sekcii **Štruktúra súboru** vyberte kadenciu (hodinovú alebo dennú) na vytváranie nových súborov v cieľovom úložisku a potom vyberte **Ďalšie**. Udalosti sa exportujú nepretržite, keď prídu.

1. V dialógovom okne **Vyberte formát** vyberte formát exportu. Vyberte z formátov **Common Data Model**, **CSV** a **JSON**. Ak chcete použiť export s inými aplikáciami Dynamics 365, odporúčame formát **Common Data Model**.

1. V dialógovom okne **Vyberte destináciu** zadajte polohu Azure Data Lake Storage Gen 2.
    1. **Názov účtu ADLS Gen 2** je názov účtu úložiska, do ktorého chcete uložiť export. 
    1. **Cesta k priečinku** definuje, kam sa má uložiť export v súborovom systéme a adresárovej štruktúre účtu úložiska.
    1. **Zdieľaný kľúč** je k dispozícii na portáli Azure pre účet úložiska.

1. Dokončite kontrolou a potvrdením svojich výberov.

## <a name="view-and-manage-exports"></a>Prehľad a spravovanie exportov

Po nastavení exportu prejdite na **Údaje** > **Export** a zobrazte si ho. Stlačte **Viac [...]** na úpravu alebo odstránenie ktoréhokoľvek exportu.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
