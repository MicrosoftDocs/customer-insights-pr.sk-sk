---
title: Vytvorte si zjednotené zobrazenie svojich zákazníkov
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
ms.openlocfilehash: bb8da6f4b9f92f2b265ff9807e04638edae4f814
ms.sourcegitcommit: 4ae316c856b8de0f08a4605f73e75a8c2cf51c4e
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 05/13/2022
ms.locfileid: "8755753"
---
# <a name="data-unification-overview"></a>Prehľad zjednotenia údajov

[!INCLUDE [m3-prod-trial-note](includes/m3-prod-trial-note.md)]

Po [nastavení zdrojov údajov](data-sources.md) môžete údaje zjednotiť. Zjednotenie údajov vám umožňuje zjednotiť kedysi nesúrodé zdroje údajov do jedného hlavného súboru údajov, ktorý poskytuje jednotný pohľad na tieto údaje. Pre individuálnych spotrebiteľov (B-to-C), kde sú údaje sústredené okolo jednotlivcov, zjednotenie poskytuje jednotný pohľad na vašich zákazníkov. Pre firemné účty (B-to-B), kde sú údaje sústredené okolo účtov, zjednotenie poskytuje jednotný pohľad na vaše účty.

Dáta môžu byť zjednotené na jednej entite alebo viacerých entitách. Zjednotenie sa vykonáva v nasledujúcom poradí:

1. [Zdrojové polia](map-entities.md) (predtým nazývané Mapa): V kroku zdrojových polí vyberte entity a polia, ktoré chcete zahrnúť do procesu zjednotenia. Mapujte polia na spoločný sémantický typ, ktorý popisuje účel poľa.

1. [Duplicitné záznamy](remove-duplicates.md) (predtým súčasť Match): V kroku duplicitných záznamov voliteľne definujte pravidlá na odstránenie duplicitných záznamov zákazníkov z každej entity.

1. [Zodpovedajúce podmienky](match-entities.md) (predtým nazývané Match): V kroku podmienok priraďovania definujte pravidlá, ktoré priraďujú záznamy zákazníkov medzi entitami. Keď sa zákazník nájde v dvoch alebo viacerých entitách, vytvorí sa jeden konsolidovaný záznam so všetkými stĺpcami a údajmi z každej entity.

1. [Zjednotené zákaznícke polia](merge-entities.md) (predtým nazývané Zlúčiť): V kroku zjednotených zákazníckych polí určite, ktoré zdrojové polia by mali byť zahrnuté, vylúčené alebo zlúčené do jednotného zákazníckeho profilu.  

1. [Preskúmanie](review-unification.md) a vytvorte jednotný profil.

Po dokončení zjednotenia údajov môžete voliteľne:

- [Nastavte vzťahy medzi entitami](relationships.md) vytvárať sofistikované segmenty.
- [Obohaťte svoje dáta](enrichment-hub.md) aby ste získali širší prehľad o svojich zákazníkoch.
- [Definujte činnosti](activities.md) z niektorých požitých atribútov.
- [Vytvorte opatrenia](measures.md) lepšie porozumieť správaniu zákazníkov a výkonnosti podniku.

[!INCLUDE [footer-include](includes/footer-banner.md)]
