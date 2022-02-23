---
title: Obmedzenia služieb v Dynamics 365 Customer Insights
description: Porozumenie limitom a obmedzeniam.
ms.date: 09/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: eb25e050b8aa768e6e1d8d4c5adce6095cccc346
ms.sourcegitcommit: 31a9b531dacd3a6465b3030c704ff5c085b7e122
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 11/10/2021
ms.locfileid: "7791999"
---
# <a name="service-limits-in-customer-insights-capabilities"></a>Limity služieb vo funkciách služby Customer Insights

Tento článok popisuje vstavané limity služby Customer Insights, ktoré sú navrhnuté tak, aby zabezpečili spoľahlivosť a stabilitu služby. Akékoľvek žiadosti o zmeny je možné podať prostredníctvom [Fóra nápadov](https://go.microsoft.com/fwlink/?linkid=2074172). 

## <a name="audience-insights"></a>Prehľady cieľových skupín

### <a name="service-limits-in-dynamics-365-customer-insights-audience-insights-capability"></a>Obmedzenia služieb v Dynamics 365 Customer Insights schopnosti štatistiky publika

| Plocha  | Limity  | Poznámky |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| Segmenty, miery a predpovede | 300  | Celkový počet [segmentov](audience-insights/segments.md),[Opatrenia](audience-insights/measures.md) a [predpovede](audience-insights/predictions.md) spolu nesmie presiahnuť 300.  |
| Vzťahy  | 20 úrovní hĺbky vzťahov v cestách entít. | Pri vytváraní [segmentov](audience-insights/segments.md) alebo [opatrení](audience-insights/measures.md) pomocou rozhrania Builder môžu mať cesty entít až 20 skokov vzťahov medzi počiatočnou entitou a cieľovou entitou.  |


## <a name="engagement-insights"></a>Prehľady interakcií

### <a name="workspace-and-event-quotas"></a>Kvóty pracovného priestoru a udalostí

Prehľad interakcií je vysoko škálovateľná aplikácia, ktorá dokáže podporovať milióny udalostí za sekundu. Počas verejnej verzie Preview má objemový limit udalostí. Existuje tiež obmedzenie počtu pracovných prehľadov v organizácii.

### <a name="engagement-insights-limits"></a>Limity prehľadov interakcií

- Maximálny objem udalostí na pracovný priestor = 100 udalostí za sekundu

- Maximálny počet pracovných priestorov na organizáciu = 100

Keď udalosti prekročia prahovú hodnotu, môže to viesť k strate údajov v prehľadoch založených na týchto udalostiach. Môžete [kontaktovať podporu](https://go.microsoft.com/fwlink/?linkid=2145734) a požiadať o zvýšenie objemu skôr, ako prekročíte limity. Budeme s vami spolupracovať na zistení vašej potreby zvýšenia objemu a podporíme vašu požiadavku.


[!INCLUDE[footer-include](includes/footer-banner.md)]
