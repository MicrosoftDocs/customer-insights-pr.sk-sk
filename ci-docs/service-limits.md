---
title: Servisné limity v Dynamics 365 Customer Insights
description: Porozumenie limitom a obmedzeniam.
ms.date: 09/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: eba7871faf304d5945191b5b9bc215243b4f8a05
ms.sourcegitcommit: 5704002484cdf85ebbcf4e7e4fd12470fd8e259f
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 09/08/2021
ms.locfileid: "7483707"
---
# <a name="service-limits-in-customer-insights-capabilities"></a>Limity služieb vo funkciách služby Customer Insights

Tento článok popisuje vstavané limity služby Customer Insights, ktoré sú navrhnuté tak, aby zabezpečili spoľahlivosť a stabilitu služby. Akékoľvek žiadosti o zmeny je možné podať prostredníctvom [Fóra nápadov](https://go.microsoft.com/fwlink/?linkid=2074172). 

## <a name="audience-insights"></a>Prehľady cieľových skupín

### <a name="service-limits-in-dynamics-365-customer-insights-audience-insights-capability"></a>Obmedzenia služby vo funkcii prehľadov cieľových skupín v Dynamics 365 Customer Insights

| Plocha  | Limity  | Poznámky |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| Segmenty a miery | 100 segmentov alebo mier. | Celkový počet aktívnych [segmentov](audience-insights/segments.md) a [mier](audience-insights/measures.md) nemôže prekročiť 100.  |
| Vzťahy | 20 úrovní hĺbky vzťahov v cestách entít. | Pri vytváraní [segmentov](audience-insights/segments.md) alebo [opatrení](audience-insights/measures.md) pomocou rozhrania Builder môžu mať cesty entít až 20 skokov vzťahov medzi počiatočnou entitou a cieľovou entitou.  |


## <a name="engagement-insights"></a>Prehľady interakcií

### <a name="workspace-and-event-quotas"></a>Kvóty pracovného priestoru a udalostí

Prehľad interakcií je vysoko škálovateľná aplikácia, ktorá dokáže podporovať milióny udalostí za sekundu. Počas verejnej verzie Preview má objemový limit udalostí. Existuje tiež obmedzenie počtu pracovných prehľadov v organizácii.

### <a name="engagement-insights-limits"></a>Limity prehľadov interakcií

- Maximálny objem udalostí na pracovný priestor = 100 udalostí za sekundu

- Maximálny počet pracovných priestorov na organizáciu = 100

Keď udalosti prekročia prahovú hodnotu, môže to viesť k strate údajov v prehľadoch založených na týchto udalostiach. Môžete [kontaktovať podporu](https://go.microsoft.com/fwlink/?linkid=2145734) a požiadať o zvýšenie objemu skôr, ako prekročíte limity. Budeme s vami spolupracovať na zistení vašej potreby zvýšenia objemu a podporíme vašu požiadavku.


[!INCLUDE[footer-include](includes/footer-banner.md)]