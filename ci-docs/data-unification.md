---
title: Vytvorte si zjednotené zobrazenie svojich zákazníkov
description: Prejdite procesom zjednotenia údajov s vašimi údajmi a vytvorte jeden hlavný súbor údajov z účtov alebo profilov zákazníkov.
ms.date: 08/12/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: overview
author: Scott-Stabbert
ms.author: sstabbert
manager: shellyha
searchScope:
- ci-map
- customerInsights
ms.openlocfilehash: c2a81776eab147c4b5209a6fbf89c0f4c9853d1d
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304446"
---
# <a name="data-unification-overview"></a>Prehľad zjednotenia údajov

Po [nastavení zdrojov údajov](data-sources.md) môžete údaje zjednotiť. Zjednotenie údajov vám umožňuje zjednotiť kedysi nesúrodé zdroje údajov do jedného hlavného súboru údajov, ktorý poskytuje jednotný pohľad na tieto údaje.

Pre individuálnych spotrebiteľov (B-to-C), kde sú údaje sústredené okolo jednotlivcov, zjednotenie poskytuje jednotný pohľad na vašich zákazníkov. Pre firemné účty (B-to-B), kde sú údaje sústredené okolo účtov, zjednotenie poskytuje jednotný pohľad na vaše účty. [Zjednotenie kontaktov (ukážka)](data-unification-contacts.md) umožňuje, aby boli kontakty pre tieto účty oddelene zjednotené a spojené s účtami.

Dáta môžu byť zjednotené na jednej entite alebo viacerých entitách.

# <a name="individual-consumers-b-to-c"></a>[Jednotliví spotrebitelia (firma a spotrebiteľ)](#tab/b2c)

Proces zjednotenia mapuje údaje zákazníkov z vašich zdrojov údajov, odstraňuje duplikáty, porovnáva údaje medzi entitami a vytvára jednotný profil. Zjednotenie sa vykonáva v nasledujúcom poradí:

1. [Zdrojové polia](map-entities.md) (predtým nazývané Mapa): V kroku zdrojových polí vyberte entity a polia, ktoré chcete zahrnúť do procesu zjednotenia. Mapujte polia na spoločný sémantický typ, ktorý popisuje účel poľa.

1. [Duplicitné záznamy](remove-duplicates.md) (predtým súčasť Match): V kroku duplicitných záznamov voliteľne definujte pravidlá na odstránenie duplicitných záznamov zákazníkov z každej entity.

1. [Zodpovedajúce podmienky](match-entities.md) (predtým nazývané Match): V kroku podmienok párovania definujte pravidlá, ktoré priraďujú záznamy zákazníkov medzi entitami. Keď sa zákazník nájde v dvoch alebo viacerých entitách, vytvorí sa jeden konsolidovaný záznam so všetkými stĺpcami a údajmi z každej entity.

1. [Zjednotené zákaznícke polia](merge-entities.md) (predtým nazývané Zlúčiť): V kroku zjednotených zákazníckych polí určite, ktoré zdrojové polia by mali byť zahrnuté, vylúčené alebo zlúčené do jednotného zákazníckeho profilu.  

1. [Preskúmanie](review-unification.md) a vytvorte jednotný profil.

# <a name="business-accounts-b-to-b"></a>[Firemné obchodné vzťahy (firma a firma)](#tab/b2b)

Proces zjednotenia mapuje údaje účtu z vašich zdrojov údajov, odstraňuje duplikáty, porovnáva údaje medzi entitami a vytvára jednotný profil. Zjednotenie sa vykonáva v nasledujúcom poradí:

1. [Zdrojové polia](map-entities.md) (predtým nazývané Mapa): V kroku zdrojových polí vyberte entity a polia, ktoré chcete zahrnúť do procesu zjednotenia účtu. Mapujte polia na spoločný sémantický typ, ktorý popisuje účel poľa.

1. [Duplicitné záznamy](remove-duplicates.md) (predtým súčasť Match): V kroku duplicitných záznamov voliteľne definujte pravidlá na odstránenie duplicitných záznamov účtov z každej entity.

1. [Zodpovedajúce podmienky](match-entities.md) (predtým nazývané Match): V kroku podmienok priraďovania definujte pravidlá, ktoré priraďujú záznamy účtov medzi entitami. Keď sa účet nájde v dvoch alebo viacerých entitách, vytvorí sa jeden konsolidovaný záznam so všetkými stĺpcami a údajmi z každej entity.

1. [Zjednotené zákaznícke polia](merge-entities.md) (predtým nazývané Zlúčiť): V kroku zjednotených zákazníckych polí určite, ktoré zdrojové polia by mali byť zahrnuté, vylúčené alebo zlúčené do jednotného zákazníckeho profilu.  

1. [Preskúmanie](review-unification.md) a vytvorte jednotný profil.

Po zjednotení účtov môžete voliteľne [zjednotiť kontakty (ukážka)](data-unification-contacts.md) pre tieto účty a prepojte zjednotené kontakty so zjednotenými účtami.

---

Po dokončení zjednotenia údajov môžete voliteľne:

- [Nastavte vzťahy medzi entitami](relationships.md) vytvárať sofistikované segmenty.
- [Obohaťte svoje dáta](enrichment-hub.md) aby ste získali širší prehľad o svojich zákazníkoch.
- [Definujte činnosti](activities.md) z niektorých požitých atribútov.
- [Vytvorte opatrenia](measures.md) lepšie porozumieť správaniu zákazníkov a výkonnosti podniku.

[!INCLUDE [footer-include](includes/footer-banner.md)]
