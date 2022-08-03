---
title: Prehľad zjednotenia údajov
description: Prejdite procesom zjednotenia údajov s vašimi údajmi a vytvorte jednu množinu údajov zjednotených zákazníckych profilov.
ms.date: 05/10/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: overview
author: v-wendysmith
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-map
- customerInsights
ms.openlocfilehash: 766e688cb80c50a0d620943f87b76eb84a2fb89a
ms.sourcegitcommit: 3c5b0b40b2b45e420015bbdd228ce0e610245e6f
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 07/12/2022
ms.locfileid: "9139537"
---
# <a name="data-unification-overview"></a>Prehľad zjednotenia údajov

Po [nastavení zdrojov údajov](data-sources.md) môžete údaje zjednotiť. Zjednotenie údajov vám umožňuje zjednotiť kedysi nesúrodé zdroje údajov do jedného hlavného súboru údajov, ktorý poskytuje jednotný pohľad na tieto údaje. Pre individuálnych spotrebiteľov (B-to-C), kde sú údaje sústredené okolo jednotlivcov, zjednotenie poskytuje jednotný pohľad na vašich zákazníkov. Pre firemné účty (B-to-B), kde sú údaje sústredené okolo účtov, zjednotenie poskytuje jednotný pohľad na vaše účty.

Dáta môžu byť zjednotené na jednej entite alebo viacerých entitách. Zjednotenie sa vykonáva v nasledujúcom poradí:

1. [Zdrojové polia](map-entities.md) (predtým nazývané Mapa): V kroku zdrojových polí vyberte entity a polia, ktoré chcete zahrnúť do procesu zjednotenia. Mapujte polia na spoločný sémantický typ, ktorý popisuje účel poľa.

1. [Duplicitné záznamy](remove-duplicates.md) (predtým súčasť Match): V kroku duplicitných záznamov voliteľne definujte pravidlá na odstránenie duplicitných záznamov zákazníkov z každej entity.

1. [Zodpovedajúce podmienky](match-entities.md) (predtým nazývané Match): V kroku podmienok párovania definujte pravidlá, ktoré priraďujú záznamy zákazníkov medzi entitami. Keď sa zákazník nájde v dvoch alebo viacerých entitách, vytvorí sa jeden konsolidovaný záznam so všetkými stĺpcami a údajmi z každej entity.

1. [Zjednotené zákaznícke polia](merge-entities.md) (predtým nazývané Zlúčiť): V kroku zjednotených zákazníckych polí určite, ktoré zdrojové polia by mali byť zahrnuté, vylúčené alebo zlúčené do jednotného zákazníckeho profilu.  

1. [Preskúmanie](review-unification.md) a vytvorte jednotný profil.

Po dokončení zjednotenia údajov môžete voliteľne:

- [Nastavte vzťahy medzi entitami](relationships.md) vytvárať sofistikované segmenty.
- [Obohaťte svoje dáta](enrichment-hub.md) aby ste získali širší prehľad o svojich zákazníkoch.
- [Definujte činnosti](activities.md) z niektorých požitých atribútov.
- [Vytvorte opatrenia](measures.md) lepšie porozumieť správaniu zákazníkov a výkonnosti podniku.

[!INCLUDE [footer-include](includes/footer-banner.md)]
