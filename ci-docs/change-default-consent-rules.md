---
title: Spravujte predvolené pravidlá súhlasu pre segmenty
description: Pomocou funkcie správy súhlasu môžete zakázať alebo zmeniť predvolené pravidlá súhlasu, ak sú povolené prepísania.
ms.date: 12/01/2021
ms.topic: how-to
author: anubhav-t
ms.author: antando
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 764eeca9d99c95a34d9bd4c11d79f8b8e90701e2
ms.sourcegitcommit: 4ae316c856b8de0f08a4605f73e75a8c2cf51c4e
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 05/13/2022
ms.locfileid: "8755235"
---
# <a name="disable-or-change-default-consent-rules"></a>Zakázať alebo zmeniť predvolené pravidlá súhlasu

Ak vaše organizácie používajú [schopnosť správy súhlasu](consent-management/overview.md) s Dynamics 365 Customer Insights,[správcovia môžu presadzovať pravidlá súhlasu](activate-consent.md) pre segmenty. 

Vďaka vynúteným pravidlám súhlasu v segmentovej oblasti každý segment informuje o stave kontroly súhlasu a pravidlách. Ak sú povolené prepísania, predvolené pravidlá súhlasu sú pre konkrétne segmenty vypnuté. Každý tvorca segmentu môže okrem predvolených pravidiel do segmentu pridať ďalšie pravidlá na získanie súhlasu. 

## <a name="for-administrators"></a>Pre správcov

:::image type="content" source="consent-management/media/consent-rules-segment.png" alt-text="Nástroj na tvorbu segmentov s možnosťami pravidla súhlasu.":::

**Deaktivácia predvolených pravidiel súhlasu:**

1. V **Pravidlá súhlasu** upozornenie, vyberte **Pozri detaily**. 

1. Nastaviť **Predvolené pravidlá súhlasu** prepnúť na **Vypnuté**.

**Ak chcete pridať ďalšie pravidlá súhlasu:**

1. V **Pravidlá súhlasu** upozornenie, vyberte **Pozri detaily**. 

1. Vyberte **Pridajte pravidlá súhlasu** a vyberte pravidlo súhlasu z **Vyberte typ údajov súhlasu** rozbaľovacia ponuka.

1. Vyberte **Uložiť** na uplatnenie nového pravidla na segment.

## <a name="for-contributors"></a>Pre prispievateľov

Ak chcete vytvoriť segment bez pravidiel vynúteného súhlasu, musíte ich v segmente deaktivovať v spolupráci so správcom. Do segmentov, ktoré vlastníte a spravujete, však môžete pridať svoje vlastné pravidlá súhlasu.

Ide o trojkrokový proces: 
1. [Vytvorte segment](segments.md) v Customer Insights a uložte ho. 

1. Zdieľajte názov segmentu so svojím správcom a požiadajte ho o to [povoliť prepísania pre váš segment](activate-consent.md). 

1. Znova otvorte svoje segmenty. V **Pravidlá súhlasu** upozornenie, vyberte **Pozri detaily** a pridajte pravidlá súhlasu, ktoré chcete použiť. potom **Uložiť** a **Bežať** váš segment.



[!INCLUDE [footer-include](includes/footer-banner.md)] 
