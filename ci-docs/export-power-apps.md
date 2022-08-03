---
title: Konektor Power Apps (ukážka)
description: Pripojte sa k Power Apps a Power Automate.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: Nils-2m
ms.author: nikeller
manager: shellyha
ms.openlocfilehash: 8807e82e65ea20d1a7f7dc07552229f377927eed
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196919"
---
# <a name="power-apps-connector-preview"></a>Konektor Power Apps (ukážka)

Prineste zjednotené profily zákazníkov do svojich prispôsobených aplikácií pomocou Microsoft Power Apps.

## <a name="connect-power-apps-and-dynamics-365-customer-insights"></a>Pripojenie k Power Apps a Dynamics 365 Customer Insights

Customer Insights sú jedným z mnohých [dostupných zdrojov údajov v Power Apps](/powerapps/maker/canvas-apps/working-with-data-sources).

Prečítajte si dokumentáciu k Power Apps, kde sa dozviete, ako [pridať dátové pripojenie k aplikácii](/powerapps/maker/canvas-apps/add-data-connection). Odporúčame tiež si prečítať článok [ako Power Apps využíva delegovanie na spracovanie veľkých množín údajov v aplikáciách plátna](/powerapps/maker/canvas-apps/delegation-overview).

## <a name="available-entities"></a>Dostupné entity

Po pridaní Customer Insights ako dátového pripojenia vyberte nasledujúce entity v Power Apps:

- **Zákazník**: použitie údajov zo [zjednoteného profilu zákazníka](customer-profiles.md).
- **UnifiedActivity**: na zobrazenie [časovej osi aktivity](activities.md) v aplikácii.
- **ContactProfile**: na zobrazenie kontaktov zákazníka. Táto entita je dostupná iba v prostrediach Customer Insights pre firemné účty.

## <a name="limitations"></a>Obmedzenia

### <a name="retrievable-entities"></a>Získateľné entity

Môžete získať iba entity **Zákazník**, **UnifiedActivity**, **Segmenty** a **ContactProfile** prostredníctvom konektora Power Apps. ContactProfile je k dispozícii iba v prostrediach Customer Insights pre firemné účty. Ostatné entity sa zobrazujú, pretože podkladový konektor ich podporuje prostredníctvom spúšťačov v Power Automate.

Môžete uskutočniť maximálne 100 hovorov za 60 sekúnd. Koncový bod API môžete volať viackrát pomocou parametra $skip. [Prečítajte si viac o parametri $skip](/connectors/customerinsights/#get-items-from-an-entity).

### <a name="delegation"></a>Delegovanie

Delegovanie funguje pre entitu **Zákazník** a entitu **UnifiedActivity**.

- Delegácia pre **Zákazník** entita: Ak chcete použiť delegovanie pre túto entitu, polia musia byť indexované [index vyhľadávania a filtrovania](search-filter-index.md).  
- Delegovanie pre entitu **Zjednotená aktivita**: Delegovanie pre túto entitu funguje iba pre polia **ActivityId** a **CustomerId**.  
- Delegovanie pre **ContactProfile**: Delegovanie pre túto entitu funguje iba pre polia **ContactId** a **CustomerId**. ContactProfile je k dispozícii iba v prostrediach Customer Insights pre firemné účty.

Ďalšie informácie o delegovaní nájdete v článku [Delegovateľné funkcie a operácie Power Apps](/powerapps/maker/canvas-apps/delegation-overview).

## <a name="example-gallery-control"></a>Príklad ovládacieho prvku galérie

Voliteľne pridajte profily zákazníkov do a [ovládanie galérie](/powerapps/maker/canvas-apps/add-gallery).

1. Pridajte ovládací prvok **galéria** do aplikácie, ktorú vytvárate.
  
   :::image type="content" source="media/connector-powerapps9.png" alt-text="Pridanie prvku galérie.":::

1. Vyberte **Zákazník** ako zdroj údajov pre položky.

   :::image type="content" source="media/choose-datasource-powerapps.png" alt-text="Výber zdroja údajov.":::

1. Zmeňte panel s údajmi na pravej strane a vyberte, ktoré pole pre entitu Zákazníka sa má zobraziť v galérii.

1. Ak chcete v galérii zobraziť akékoľvek pole od vybraného zákazníka, vyplňte vlastnosť **Text** označenia pomocou **{Name_of_the_gallery}.Selected.{property_name}**  
    - Príklad: _Gallery1.Selected.address1_city_

1. Ak chcete zobraziť zjednotenú časovú os pre zákazníka, pridajte prvok Galéria a pridajte vlastnosť **Položky** pomocou **Filter ('UnifiedActivity', CustomerId = {Customer_Id})**  
    - Príklad: _Filter('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)_

[!INCLUDE [footer-include](includes/footer-banner.md)]
