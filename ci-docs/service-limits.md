---
title: Limity služieb v Customer Insights
description: Pochopte limity a obmedzenia v službe Customer Insights SaaS.
ms.date: 05/28/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 6d1b761a5c9f67bfdc7c5b152132c618db3ea36a
ms.sourcegitcommit: 78ef22cd39a1ebd7525f96829cd79d95f34438b9
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 06/07/2022
ms.locfileid: "8940687"
---
# <a name="service-limits-in-customer-insights"></a>Limity služieb v Customer Insights

Tento článok popisuje vstavané limity služby Customer Insights, ktoré sú navrhnuté tak, aby zabezpečili spoľahlivosť a stabilitu služby. Akékoľvek žiadosti o zmeny je možné podať prostredníctvom [Fóra nápadov](https://go.microsoft.com/fwlink/?linkid=2074172).

## <a name="customer-insights"></a>Customer Insights

| Plocha  | Limity  | Poznámky |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| Segmenty, miery a predpovede | 300  | Celkový počet [segmentov](segments.md),[Opatrenia](measures.md) a [predpovede](predictions.md) spolu nesmie presiahnuť 300.  |
| Vzťahy  | 20 úrovní hĺbky vzťahov v cestách entít. | Pri vytváraní [segmentov](segments.md) alebo [opatrení](measures.md) pomocou rozhrania Builder môžu mať cesty entít až 20 skokov vzťahov medzi počiatočnou entitou a cieľovou entitou.  |

## <a name="fair-scheduling-of-jobs"></a>Spravodlivé rozvrhnutie pracovných miest

Customer Insights je služba SaaS, ktorá využíva zdieľané prostriedky Azure. Zákazníci majú tendenciu mať pracovné zaťaženie rôznej intenzity a rôzneho rozvrhu. Aby sme zabezpečili spravodlivý prístup k základným zdrojom, zabezpečujeme, aby sa systémové procesy vykonávali v spravodlivom poradí. Príkladmi systémových procesov sú úlohy súvisiace so zjednotením údajov, aktualizáciami segmentov alebo výpočtom opatrení. Spravodlivé plánovanie vás chráni pred čakaním na zdroje, ak dôjde k prudkému nárastu požadovaných úloh. Customer Insights zároveň nezaručuje, že všetky úlohy, ktoré zaradíte do frontu, budú spracované paralelne.

[!INCLUDE [footer-include](includes/footer-banner.md)]
