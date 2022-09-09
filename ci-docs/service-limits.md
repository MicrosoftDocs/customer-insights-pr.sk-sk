---
title: Limity služieb v Customer Insights
description: Pochopte limity a obmedzenia v službe Customer Insights SaaS.
ms.date: 08/30/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 7f38b7d9985368fc38107f1f360f0603a7fcc8e6
ms.sourcegitcommit: 3c7cdfc8bd83ca236e4777240e08a541dc955d34
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 09/07/2022
ms.locfileid: "9411759"
---
# <a name="service-limits-in-customer-insights"></a>Limity služieb v Customer Insights

 Customer Insights má zabudované limity navrhnuté tak, aby zabezpečili spoľahlivosť a stabilitu služby. Akékoľvek žiadosti o zmeny je možné podať prostredníctvom [Fóra nápadov](https://go.microsoft.com/fwlink/?linkid=2074172).

## <a name="customer-insights"></a>Customer Insights

| Plocha  | Limity  | Poznámky |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| Segmenty, miery a predpovede | 300  | Celkový počet [segmentov](segments.md),[Opatrenia](measures.md), a [predpovede](predictions-overview.md) spolu nesmie presiahnuť 300.  |
| Vzťahy  | 20 úrovní hĺbky vzťahov v cestách entít. | Pri vytváraní [segmentov](segments.md) alebo [opatrení](measures.md) pomocou rozhrania Builder môžu mať cesty entít až 20 skokov vzťahov medzi počiatočnou entitou a cieľovou entitou.  |

## <a name="fair-scheduling-of-jobs"></a>Spravodlivé rozvrhnutie pracovných miest

Customer Insights je služba SaaS, ktorá využíva zdieľané prostriedky Azure. Zákazníci majú tendenciu mať pracovnú záťaž s rôznou intenzitou a v rôznych harmonogramoch. Aby sme zabezpečili spravodlivý prístup k základným zdrojom, zabezpečujeme, aby sa systémové procesy vykonávali v spravodlivom poradí. Príkladmi systémových procesov sú úlohy súvisiace so zjednotením údajov, aktualizáciou segmentov alebo výpočtom opatrení. Spravodlivé plánovanie vás chráni pred čakaním na zdroje, ak dôjde k prudkému nárastu požadovaných úloh. Customer Insights zároveň nezaručuje, že všetky úlohy, ktoré zaradíte do frontu, budú spracované paralelne.

[!INCLUDE [footer-include](includes/footer-banner.md)]
