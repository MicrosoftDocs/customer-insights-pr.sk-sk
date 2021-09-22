---
title: Exportujte spresnené udalosti
description: Ako exportovať spresnené a základné udalosti.
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 04/30/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: faa0c3afb08d1c0282b2164ed914637ce9aad88117af37ba44fdb81e7610e574
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 08/10/2021
ms.locfileid: "7032404"
---
# <a name="export-events"></a>Export udalostí

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Udalosť predstavuje správanie používateľa. Zaznamená sa, keď používateľ zobrazí stránku (aktivita zobrazenia) alebo interaguje s obsahom (aktivita akcie). Keď sa môžete rozhodnúť, ktoré vlastnosti údajov sa budú zobrazovať v prehľade, toto virtuálne zobrazenie údajov sa nazýva *spresnená udalosť*. 

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

Existujú dva spôsoby exportovania udalostí: 
- Prejdite do **Údaje** > **Exporty** a stlačte možnosť **Nový export**.
- Prejdite na **Údaje** > **Udalosti**, vyberte možnosť **Viac [...]** vedľa udalosti, ktorú chcete exportovať, a vyberte možnosť **Exportovať** z rozbaľovacej ponuky. 

Prevedieme vás krokmi, ako vytvoriť export:

1. Zadajte **Názov exportu**.

1. Z rozbaľovacieho zoznamu **Výber udalostí** si vyberte základné udalosti a vylepšené udalosti, ktoré sa majú zahrnúť do exportu. 

1. V časti **Štruktúra súborov** vyberte kadenciu a vytvorte nové súbory v cieľovom úložisku. Udalosti sa exportujú nepretržite, keď prídu.

1. Vyberte formát exportu. Môžete si vybrať medzi formátmi **Common Data Model**, **CSV** a **JSON**. Ak chcete použiť export s inými aplikáciami Dynamics 365, odporúčame vám použiť formát Common Data Model.

1. V kroku **Vybrať cieľ** zadajte umiestnenie Azure Data Lake Storage Gen 2.
    1. **Názov účtu ADLS Gen 2** je názov účtu úložiska, do ktorého chcete uložiť export. 
    1. **Cesta k priečinku** definuje, kam sa má uložiť export v súborovom systéme a adresárovej štruktúre účtu úložiska.
    1. **Zdieľaný kľúč** je k dispozícii na portáli Azure pre účet úložiska.

1. Skontrolujte a potvrďte svoj výber.

## <a name="view-and-manage-exports"></a>Prehľad a spravovanie exportov

Po nastavení exportu prejdite na **Údaje** > **Export** a zobrazte si ho. Stlačte **Viac [...]** na úpravu alebo odstránenie ktoréhokoľvek exportu.


[!INCLUDE[footer-include](../includes/footer-banner.md)]