---
title: Konektor služby Power Apps
description: Pripojte sa k Power Apps a Power Automate.
ms.date: 01/19/2021
ms.reviewer: nikeller
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 5a8bbb9a09218d54228589d43c21c8894680b56e
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268935"
---
# <a name="microsoft-power-apps-connector-preview"></a>Konektor Microsoft Power Apps (ukážka)

Prineste zjednotené profily zákazníkov do svojich prispôsobených aplikácií pomocou Power Apps.

## <a name="connect-power-apps-and-dynamics-365-customer-insights"></a>Pripojenie k Power Apps a Dynamics 365 Customer Insights

Customer Insights sú jedným z mnohých [dostupných zdrojov údajov v Power Apps](https://docs.microsoft.com/powerapps/maker/canvas-apps/working-with-data-sources).

Prečítajte si dokumentáciu k Power Apps, kde sa dozviete, ako [pridať dátové pripojenie k aplikácii](https://docs.microsoft.com/powerapps/maker/canvas-apps/add-data-connection). Odporúčame tiež si prečítať článok [ako Power Apps využíva delegovanie na spracovanie veľkých množín údajov v aplikáciách plátna](https://docs.microsoft.com/powerapps/maker/canvas-apps/delegation-overview).

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

- Ďalšie informácie o delegovaní nájdete v časti [Delegovateľné funkcie a operácie Power Apps](https://docs.microsoft.com/connectors/commondataservice/#power-apps-delegable-functions-and-operations-for-the-cds-for-apps). 

## <a name="example-gallery-control"></a>Príklad ovládacieho prvku galérie

Napríklad pridáte profily zákazníkov do [ovládacieho prvku galérie](https://docs.microsoft.com/powerapps/maker/canvas-apps/add-gallery).

1. Pridajte ovládací prvok **Galéria** do aplikácie, ktorú vytvárate.

> [!div class="mx-imgBorder"]
> ![Pridanie prvku galérie](media/connector-powerapps9.png "Pridanie prvku galérie")

1. Vyberte **Zákazník** ako zdroj údajov pre položky.

    > [!div class="mx-imgBorder"]
    > ![Výber zdroja údajov](media/choose-datasource-powerapps.png "Výber zdroja údajov")

1. Na pravej strane môžete zmeniť dátový panel a zvoliť, ktoré pole pre entitu zákazníka sa má zobraziť v galérii.

1. Ak chcete v galérii zobraziť akékoľvek pole od vybraného zákazníka, vyplňte vlastnosť Text štítka: **{Name_of_the_gallery}.Selected.{property_name}**

    Príklad: Gallery1.Selected.address1_city

1. Ak chcete zobraziť jednotnú časovú os pre zákazníka, pridajte prvok Galéria a pridajte vlastnosť Položky: **Filter ('UnifiedActivity', CustomerId = {Customer_Id})**

    Príklad: Filter('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)


[!INCLUDE[footer-include](../includes/footer-banner.md)]