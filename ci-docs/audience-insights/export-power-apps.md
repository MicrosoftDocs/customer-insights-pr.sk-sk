---
title: Konektor služby Power Apps
description: Pripojte sa k Power Apps a Power Automate.
ms.date: 10/01/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: Nils-2m
ms.author: nikeller
manager: shellyha
ms.openlocfilehash: 18cc32a169e79794d2d3203d462620ab41efaafe
ms.sourcegitcommit: d168a738a08adb8b4b2e410bdaa3716d7b63cc9b
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 03/17/2022
ms.locfileid: "8455971"
---
# <a name="microsoft-power-apps-connector-preview"></a>Konektor Microsoft Power Apps (ukážka)

Prineste zjednotené profily zákazníkov do svojich prispôsobených aplikácií pomocou Power Apps.

## <a name="connect-power-apps-and-dynamics-365-customer-insights"></a>Pripojenie k Power Apps a Dynamics 365 Customer Insights

Customer Insights sú jedným z mnohých [dostupných zdrojov údajov v Power Apps](/powerapps/maker/canvas-apps/working-with-data-sources).

Prečítajte si dokumentáciu k Power Apps, kde sa dozviete, ako [pridať dátové pripojenie k aplikácii](/powerapps/maker/canvas-apps/add-data-connection). Odporúčame tiež si prečítať článok [ako Power Apps využíva delegovanie na spracovanie veľkých množín údajov v aplikáciách plátna](/powerapps/maker/canvas-apps/delegation-overview).

## <a name="available-entities"></a>Dostupné entity

Po pridaní Customer Insights ako dátového pripojenia si môžete vybrať nasledujúce entity v systéme Power Apps:

- **Zákazník**: použitie údajov zo [zjednoteného profilu zákazníka](customer-profiles.md).
- **UnifiedActivity**: na zobrazenie [časovej osi aktivity](activities.md) v aplikácii.
- **ContactProfile**: na zobrazenie kontaktov zákazníka. Entita je k dispozícii ba v prostrediach prehľadov cieľových skupín pre firemné obchodné vzťahy.

## <a name="limitations"></a>Obmedzenia

### <a name="retrievable-entities"></a>Získateľné entity

Môžete získať iba entity **Zákazník**, **UnifiedActivity**, **Segmenty** a **ContactProfile** prostredníctvom konektora Power Apps. ContactProfile je k dispozícii iba v inštancii prehľadov cieľových skupín pre firemné obchodné vzťahy. Ostatné entity sa zobrazujú, pretože podkladový konektor ich podporuje prostredníctvom spúšťačov v Power Automate.

Môžete uskutočniť maximálne 100 hovorov za 60 sekúnd. Koncový bod API môžete volať viackrát pomocou parametra $skip. [Prečítajte si viac o parametri $skip](/connectors/customerinsights/#get-items-from-an-entity).

### <a name="delegation"></a>Delegovanie

Delegovanie funguje pre entitu **Zákazník** a entitu **UnifiedActivity**. 

- Delegovanie pre entitu **Zákazník**: Ak chcete použiť delegovanie pre túto entitu, polia musia byť indexované v [indexe vyhľadávania a filtrovania](search-filter-index.md).  
- Delegovanie pre entitu **Zjednotená aktivita**: Delegovanie pre túto entitu funguje iba pre polia **ActivityId** a **CustomerId**.  
- Delegovanie pre **ContactProfile**: Delegovanie pre túto entitu funguje iba pre polia **ContactId** a **CustomerId**. ContactProfile je k dispozícii iba v prostrediach prehľadov cieľových skupín pre firemné obchodné vzťahy.

Ďalšie informácie o delegovaní nájdete v článku [Delegovateľné funkcie a operácie Power Apps](/powerapps/maker/canvas-apps/delegation-overview). 

## <a name="example-gallery-control"></a>Príklad ovládacieho prvku galérie

Profily zákazníkov môžete pridať do [ovládacieho prvku galérie](/powerapps/maker/canvas-apps/add-gallery).

1. Pridajte ovládací prvok **galéria** do aplikácie, ktorú vytvárate.

    > [!div class="mx-imgBorder"]
    > ![Pridanie prvku galérie.](media/connector-powerapps9.png "Pridanie prvku galérie.")

2. Vyberte **Zákazník** ako zdroj údajov pre položky.

    > [!div class="mx-imgBorder"]
    > ![Výber zdroja údajov.](media/choose-datasource-powerapps.png "Vyberte zdroj údajov.")

3. Na pravej strane môžete zmeniť dátový panel a zvoliť, ktoré pole pre entitu zákazníka sa má zobraziť v galérii.

4. Ak chcete v galérii zobraziť akékoľvek pole od vybraného zákazníka, vyplňte vlastnosť **Text** označenia pomocou **{Name_of_the_gallery}.Selected.{property_name}**  
    - Príklad: _Gallery1.Selected.address1_city_

5. Ak chcete zobraziť zjednotenú časovú os pre zákazníka, pridajte prvok Galéria a pridajte vlastnosť **Položky** pomocou **Filter ('UnifiedActivity', CustomerId = {Customer_Id})**  
    - Príklad: _Filter('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)_


[!INCLUDE[footer-include](../includes/footer-banner.md)]
