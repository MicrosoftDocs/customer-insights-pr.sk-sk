---
title: Vytváranie a úprava udalostí
description: Vytvorenie a úprava udalostí.
ms.reviewer: mhart
ms.author: jefhar
author: mochimochi016
ms.date: 10/01/2021
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: dbafa2231daa82c34ee2ec8292111575e95af675
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 02/16/2022
ms.locfileid: "8228222"
---
# <a name="create-and-modify-events"></a>Vytváranie a úprava udalostí

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Udalosťou sú údaje, ktoré predstavujú správanie používateľa, napríklad aktivitu na webe.

- *Základná* udalosť sa zaznamená, keď používateľ zobrazí stránku (aktivita zobrazenia) alebo interaguje s obsahom (aktivita akcie).
- *Spresnená* udalosť je virtuálny pohľad na základnú udalosť. Spresnené udalosti definujete odstránením a pridaním vlastností alebo filtrovaním udalostí na základe hodnôt vlastnosti.

## <a name="prerequisites"></a>Predpoklady

Ak chcete získať udalosti, údaje vašej webovej lokality treba najprv pripojiť k prehľadom interakcií pomocou úryvku kódu. Ďalšie informácie nájdete v časti [Inštalácie webovej súpravy SDK na webovej lokalite](instrument-website.md).

 :::image type="content" source="media/new-events-connect-data.png" alt-text="Najprv pripojte svoje údaje.":::

## <a name="create-refined-events"></a>Vytvoriť spresnené udalosti

Použite spresnené udalosti na zníženie rozsahu základnej udalosti na účely [exportu](export-events.md) alebo na odstránenie vlastností z udalosti, ktoré nie sú potrebné na vystavenie.

> [!NOTE]
> Keď na svoju webovú lokalitu pridáte webovú súpravu SDK, budete si môcť prezerať svoje základné udalosti a vytvárať prepracované udalosti. 

Ak chcete zobraziť svoje základné udalosti:

1. Na ľavej navigačnej table prejdite na **Údaje**.

1. Vyberte **Udalosti** na zobrazenie zoznamu všetkých udalostí v pracovnom priestore.

    :::image type="content" source="media/data-events.png" alt-text="Zobrazenie udalostí.":::

Ak chcete vytvoriť spresnenú udalosť zo základnej udalosti: 

1. Prejdite na **Údaje** > **Udalosti** a vyberte **+ Nové udalosti** v hornej časti obrazovky.

1. V dialógovom okne **Nové udalosti** vyberte **Vytvoriť spresnené udalosti** a potom vyberte **Ďalšie**.
   
     :::image type="content" source="media/new-events-wizard.png" alt-text="Sprievodca novými udalosťami.":::
     
1. V dialógovom okne **Nové udalosti** zadajte nasledujúce informácie:

   - Vyberte udalosť z rozbaľovacieho zoznamu **Základné udalosti**.
   - Zadajte názov do poľa **Zobrazovaný názov spresnených udalostí**.
   - Voliteľne možno bez použitia medzier aktualizovať navrhovaný **Skutočný názov**.

1. Stlačte možnosť **Vytvoriť** na použitie vašich nastavení.

Upravená udalosť sa teraz zobrazí vo vašom zozname **Udalosti**.

### <a name="edit-event-name"></a>Úprava názvu udalosti

Môžete zmeniť názov a vlastnosti základnej alebo spresnenej udalosti.

1. Prejdite na **Údaje** > **Udalosti**. 

1. Pri udalosti stlačte možnosť **Viac [...]** a stlačte možnosť **Upraviť názov**.
    
     :::image type="content" source="media/create-refined-events-options.png" alt-text="Možnosti na vytvorenie vylepšených udalostí.":::

3. Aktualizujte názov udalosti a vyberte možnosť **Premenovať**.

### <a name="view-the-details-of-a-refined-event"></a>Pozrite si podrobnosti o upravenej udalosti:

1. V zozname **Udalosť** vyberte svoju základnú alebo spresnenú udalosť. 

1. Vyberte **Pridať a odstrániť vlastnosti** v hornej časti obrazovky a otvorte tablu **Upraviť vlastnosti**. 

     :::image type="content" source="media/add-remove-properties.png" alt-text="Pridať a odstrániť vlastnosti.":::

1. Pomocou začiarkavacích políčok vyberte vlastnosti, ktoré chcete zobraziť, a tie, ktoré chcete skryť. 

   :::image type="content" source="media/edit-properties-refined-events.png" alt-text="Upravte vlastnosti pre spresnené udalosti.":::

1. Vyberte **Potvrdiť** na použitie svojho výberu a potom vyberte **Uložiť**.


### <a name="edit-selected-properties-for-a-refined-event"></a>Úprava vybraných vlastností pre spresnenú udalosť

1. Prejdite na **Údaje** > **Udalosti** a výberom spresnených udalostí otvoríte podrobné zobrazenie.
1. Stlačte možnosť **Pridať a odstrániť vlastnosti**. 
1. Upravte výber začiarkavacích políčok.
1. Stlačte možnosť **Potvrdiť** a potom stlačením položky **Uložiť** uplatnite zmeny.

Informácie o exportovaní udalostí nájdete v časti [Exportovať udalosti](export-events.md).
[!INCLUDE[footer-include](../includes/footer-banner.md)]
