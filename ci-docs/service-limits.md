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
ms.openlocfilehash: 9bf8f03b785fb3035e3fc979a3304d4e98fd8d28
ms.sourcegitcommit: 1946d7af0bd2ca216885bec3c5c95009996d9a28
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 02/25/2022
ms.locfileid: "8350426"
---
# <a name="service-limits-in-customer-insights-capabilities"></a>Limity služieb vo funkciách služby Customer Insights

Tento článok popisuje vstavané limity služby Customer Insights, ktoré sú navrhnuté tak, aby zabezpečili spoľahlivosť a stabilitu služby. Akékoľvek žiadosti o zmeny je možné podať prostredníctvom [Fóra nápadov](https://go.microsoft.com/fwlink/?linkid=2074172). 

## <a name="audience-insights"></a>Prehľady cieľových skupín

| Plocha  | Limity  | Poznámky |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| Segmenty, miery a predpovede | 300  | Celkový počet [segmentov](audience-insights/segments.md),[Opatrenia](audience-insights/measures.md) a [predpovede](audience-insights/predictions.md) spolu nesmie presiahnuť 300.  |
| Vzťahy  | 20 úrovní hĺbky vzťahov v cestách entít. | Pri vytváraní [segmentov](audience-insights/segments.md) alebo [opatrení](audience-insights/measures.md) pomocou rozhrania Builder môžu mať cesty entít až 20 skokov vzťahov medzi počiatočnou entitou a cieľovou entitou.  |

<!--
## Engagement insights

### Workspace and event quotas

Engagement insights is a highly scalable application that can support millions of events per second. During public preview, events have a volume threshold. There's also a limit to the number of workspaces in an organization.

### Engagement insights limits

- Maximum event volume per workspace  = 100 events per second

- Maximum number of workspaces per organization = 100

When events exceed the threshold, it can lead to loss of data in reports based on those events. You can [contact support](https://go.microsoft.com/fwlink/?linkid=2145734) to request a volume increase before you exceed limits. We'll work with you to determine your need for a volume increase and support your request.
-->

[!INCLUDE[footer-include](includes/footer-banner.md)]
