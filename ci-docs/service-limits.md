---
title: Servisné limity v Dynamics 365 Customer Insights
description: Porozumenie limitom a obmedzeniam.
ms.date: 09/03/2021
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: e2e7fc3033c25646693831d4c4c800d84ae6d6da
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 04/27/2022
ms.locfileid: "8641781"
---
# <a name="service-limits-in-customer-insights"></a>Limity služieb v Customer Insights

Tento článok popisuje vstavané limity služby Customer Insights, ktoré sú navrhnuté tak, aby zabezpečili spoľahlivosť a stabilitu služby. Akékoľvek žiadosti o zmeny je možné podať prostredníctvom [Fóra nápadov](https://go.microsoft.com/fwlink/?linkid=2074172). 

## <a name="customer-insights"></a>Customer Insights

| Plocha  | Limity  | Poznámky |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| Segmenty, miery a predpovede | 300  | Celkový počet [segmentov](segments.md),[Opatrenia](measures.md) a [predpovede](predictions.md) spolu nesmie presiahnuť 300.  |
| Vzťahy  | 20 úrovní hĺbky vzťahov v cestách entít. | Pri vytváraní [segmentov](segments.md) alebo [opatrení](measures.md) pomocou rozhrania Builder môžu mať cesty entít až 20 skokov vzťahov medzi počiatočnou entitou a cieľovou entitou.  |


[!INCLUDE [footer-include](includes/footer-banner.md)]
