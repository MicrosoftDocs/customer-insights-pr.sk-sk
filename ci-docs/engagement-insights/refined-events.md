---
title: Vytvorenie a úprava spresnených udalostí
description: Postup vytvárania a úpravy spresnených udalostí.
ms.reviewer: mhart
ms.author: jefhar
author: mochimochi016
ms.date: 04/30/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 0344bac5f4d43df853309f43c94d95f962937f77c936ed7305c5de4a08835f04
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 08/10/2021
ms.locfileid: "7034793"
---
# <a name="create-and-modify-refined-events"></a>Vytvorenie a úprava spresnených udalostí

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]


Udalosťou sú údaje, ktoré predstavujú správanie používateľa, napríklad aktivitu na webe.

- *Základná* udalosť sa zaznamená, keď používateľ zobrazí stránku (aktivita zobrazenia) alebo interaguje s obsahom (aktivita akcie).
- *Spresnená* udalosť je virtuálny pohľad na základnú udalosť. Spresnené udalosti definujete odstránením a pridaním vlastností alebo filtrovaním udalostí na základe hodnôt vlastnosti.

Použite spresnené udalosti na zníženie rozsahu základnej udalosti na účely [exportu](export-events.md) alebo na odstránenie vlastností z udalosti, ktoré nie sú potrebné na vystavenie.

## <a name="create-refined-events"></a>Vytváranie prepracovaných udalostí

Existujú tri spôsoby, ako vytvoriť vylepšenú udalosť zo základnej udalosti. 

1. Prejdite do ponuky **Údaje** > **Udalosti** a vyberte si jednu z nasledovných možností:
    - Zvoľte možnosť **Nové udalosti** a potom stlačte možnosť **Vytvoriť spresnené udalosti**.
    - Vyberte základnú udalosť, aby ste otvorili podrobné zobrazenie, a stlačte možnosť **Vytvoriť spresnené udalosti** z hornej ponuky.
    - Stlačte možnosť **Viac [...]** a otvorte miestnu ponuku základnej udalosti. Potom stlačte možnosť **Vytvoriť spresnené udalosti**.
    
    :::image type="content" source="media/create-refined-events-options.png" alt-text="Možnosti na vytvorenie vylepšených udalostí.":::

1. V dialógovom okne **Vytvoriť spresnené udalosti** zadajte nasledujúce informácie:

- Vyberte udalosť z rozbaľovacej ponuke **Základné udalosti**, ak vytvárate novú udalosť.
- Zadajte názov do poľa **Zobrazovaný názov spresnených udalostí**.
- Voliteľne možno bez použitia medzier aktualizovať navrhovaný **Skutočný názov**.

3. Stlačte možnosť **Vytvoriť** na použitie vašich nastavení.

1. V podrobnom zobrazení svojej rafinovanej udalosti vyberte možnosť **Pridať a odstrániť vlastnosti**, čím otvoríte tablu **Upraviť vlastnosti**. 

1. Pomocou začiarkavacích políčok vyberte vlastnosti, ktoré chcete zobraziť, a tie, ktoré chcete skryť. 
   :::image type="content" source="media/edit-properties-refined-events.png" alt-text="Upravte vlastnosti pre spresnené udalosti.":::

1. Stlačte možnosť **Potvrdiť** a použite svoj výber.

1. Stlačením možnosti **Uložiť** uložte konfiguráciu.

## <a name="edit-refined-events"></a>Upravte spresnené udalosti

Môžete zmeniť názov a vlastnosti spresnenej udalosti.

### <a name="edit-event-name"></a>Úprava názvu udalosti

1. Prejdite na **Údaje** > **Udalosti**. 
1. Pri udalosti stlačte možnosť **Viac [...]** a stlačte možnosť **Upraviť názov**.
1. Aktualizujte názov udalosti a vyberte možnosť **Premenovať**.

### <a name="edit-selected-properties"></a>Upraviť vybraté vlastnosti

1. Prejdite na **Údaje** > **Udalosti** a výberom spresnených udalostí otvoríte podrobné zobrazenie.
1. Stlačte možnosť **Pridať a odstrániť vlastnosti**. 
1. Upravte výber začiarkavacích políčok.
1. Stlačte možnosť **Potvrdiť** a potom stlačením položky **Uložiť** uplatnite zmeny.

Informácie o exportovaní udalostí nájdete v časti [Exportovať udalosti](export-events.md).
[!INCLUDE[footer-include](../includes/footer-banner.md)]
