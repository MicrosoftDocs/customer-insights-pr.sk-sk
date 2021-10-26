---
title: Vytvorenie nového pracovného priestoru
description: Účel pracovného priestoru a spôsob, ako vytvoriť nový.
author: jusali
ms.reviewer: mhart
ms.author: jusali
ms.date: 10/01/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 816f948331a06794c15000eb779f93cc7fdda202
ms.sourcegitcommit: 53b133a716c73cb71e8bcbedc6273cec70ceba6c
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 10/15/2021
ms.locfileid: "7645329"
---
# <a name="create-a-new-workspace-and-add-members"></a>Vytvorte nový pracovný priestor a pridajte členov

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Pracovný priestor predstavuje spôsob, ako môžete zobraziť aktivitu používateľov v reálnom čase, aby ste lepšie porozumeli svojmu publiku. Je to miesto, kde ukladáte a spravujete udalosti a prehľady.

Pri vytváraní pracovného priestoru vyberiete typ údajov, na ktoré sa chcete zamerať. Do existujúceho pracovného priestoru môžete kedykoľvek pridať ďalších používateľov alebo členov. 

## <a name="create-a-new-workspace"></a>Vytvorenie nového pracovného priestoru

Proces vytvárania pracovného priestoru zahŕňa vytvorenie *prostredia* na usporiadanie pracovného priestoru. Prostredie je priestor, ktorý môže obsahovať jeden alebo viac pracovných priestorov. Prostredie môžete použiť na správu svojich pracovných priestorov a pripojení k možnostiam prehľadov o cieľovej skupine Customer Insights.

1. Stlačte možnosť **Nový** z prepínača pracovného priestoru.

   :::image type="content" source="media/new-workspace.png" alt-text="Stránka Customer insights s popisom na navigačnom paneli a popisom.":::

1. Na table **Pracovný priestor** zadajte **Názov pracovného priestoru**.

   :::image type="content" source="media/workspace-name.png" alt-text="Zadajte názov pracovného priestoru.":::

1. Vyberte typ platformy (webovú alebo mobilnú), ktorú chcete merať.

1. Vyberte **Ukázať pokročilé nastavenia** a povoľte alebo zakážte tieto voliteľné nastavenia:

   - Prepnite **Neznáme na známe** na „povolené“ na priradenie webových udalostí k používateľom, ktorí sa predtým autentifikovali. Ďalšie informácie nájdete v časti [Rozpoznajte webové udalosti od predtým overených používateľov](unknown-to-known.md)
   - Prepnite **Filtrovať prenos botov** na „povolené“, aby sa z tohto pracovného priestoru odstránili webovú návštevnosť botov. 

1. Po skončení vyberte možnosť **Dokončiť**. 

1. Nainštalujte úryvok kódu, aby ste mohli začať prijímať údaje, a potom vyberte **Dokončiť** na vytvorenie pracovného priestoru. Ďalšie informácie nájdete v téme [Prehľad zdrojov pre vývojárov](developer-resources.md).

> [!NOTE]
> Teraz môžete pridávať členov a priraďovať im úroveň povolení zo zoznamu **Úloha**. Ďalšie informácie nájdete v téme o [Roliach a povoleniach](user-roles.md). 

Viac informácií nájdete v časti [Správa prostredí a pracovných priestorov](manage-environments-workspaces.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
