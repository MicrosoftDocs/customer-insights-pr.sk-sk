---
title: Konektor služby Power Apps
description: Pripojte sa k Power Apps a Power Automate.
ms.date: 01/19/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: Nils-2m
ms.author: nikeller
manager: shellyha
ms.openlocfilehash: 2ab5a9059991611a2959a19cc688d232ec782e1e
ms.sourcegitcommit: dab2cbf818fafc9436e685376df94c5e44e4b144
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 07/13/2021
ms.locfileid: "6554132"
---
# <a name="microsoft-power-apps-connector-preview"></a>Konektor Microsoft Power Apps (ukážka)

Prineste zjednotené profily zákazníkov do svojich prispôsobených aplikácií pomocou Power Apps.

## <a name="connect-power-apps-and-dynamics-365-customer-insights"></a>Pripojenie k Power Apps a Dynamics 365 Customer Insights

Customer Insights sú jedným z mnohých [dostupných zdrojov údajov v Power Apps](/powerapps/maker/canvas-apps/working-with-data-sources).

Prečítajte si dokumentáciu k Power Apps, kde sa dozviete, ako [pridať dátové pripojenie k aplikácii](/powerapps/maker/canvas-apps/add-data-connection). Odporúčame tiež si prečítať článok [ako Power Apps využíva delegovanie na spracovanie veľkých množín údajov v aplikáciách plátna](/powerapps/maker/canvas-apps/delegation-overview).

## <a name="available-entities"></a>Dostupné entity

Po pridaní Customer Insights ako dátového pripojenia si môžete vybrať nasledujúce entity v systéme Power Apps:

- Zákazník: použitie údajov zo [zjednoteného profilu zákazníka](customer-profiles.md).
- UnifiedActivity: na zobrazenie [časovej osi aktivity](activities.md) v aplikácii.

## <a name="limitations"></a>Obmedzenia

### <a name="retrievable-entities"></a>Získateľné entity

Entity **Zákazník**, **Zjednotená aktivita** a **Segmenty** môžete získať len prostredníctvom konektora Power Apps. Ostatné entity sa zobrazujú, pretože podkladový konektor ich podporuje prostredníctvom spúšťačov v Power Automate.  

### <a name="delegation"></a>Delegovanie

Delegovanie funguje pre entitu Zákazník a entitu Zjednotená aktivita. 

- Delegovanie pre entitu **Zákazník**: Ak chcete použiť delegovanie pre túto entitu, polia musia byť indexované v [indexe vyhľadávania a filtrovania](search-filter-index.md).  

- Delegovanie pre entitu **Zjednotená aktivita**: Delegovanie pre túto entitu funguje iba pre polia **ActivityId** a **CustomerId**.  

- Ďalšie informácie o delegovaní nájdete v časti [Delegovateľné funkcie a operácie Power Apps](/connectors/commondataservice/#power-apps-delegable-functions-and-operations-for-the-cds-for-apps). 

## <a name="example-gallery-control"></a>Príklad ovládacieho prvku galérie

Napríklad pridáte profily zákazníkov do [ovládacieho prvku galérie](/powerapps/maker/canvas-apps/add-gallery).

1. Pridajte ovládací prvok **Galéria** do aplikácie, ktorú vytvárate.

> [!div class="mx-imgBorder"]
> ![Pridanie prvku galérie.](media/connector-powerapps9.png "Pridanie prvku galérie")

1. Vyberte **Zákazník** ako zdroj údajov pre položky.

    > [!div class="mx-imgBorder"]
    > ![Výber zdroja údajov.](media/choose-datasource-powerapps.png "Výber zdroja údajov")

1. Na pravej strane môžete zmeniť dátový panel a zvoliť, ktoré pole pre entitu zákazníka sa má zobraziť v galérii.

1. Ak chcete v galérii zobraziť akékoľvek pole od vybraného zákazníka, vyplňte vlastnosť Text štítka: **{Name_of_the_gallery}.Selected.{property_name}**

    Príklad: Gallery1.Selected.address1_city

1. Ak chcete zobraziť jednotnú časovú os pre zákazníka, pridajte prvok Galéria a pridajte vlastnosť Položky: **Filter ('UnifiedActivity', CustomerId = {Customer_Id})**

    Príklad: Filter('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)


[!INCLUDE[footer-include](../includes/footer-banner.md)]