---
title: Roly a povolenia
description: Prehľad dostupných rol a povolení pre členov pracovného priestoru.
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 10/01/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 68e28caf1c14c23acd506da5f7b441f1e3b72e8b
ms.sourcegitcommit: 53b133a716c73cb71e8bcbedc6273cec70ceba6c
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 10/15/2021
ms.locfileid: "7645556"
---
# <a name="roles-and-permissions"></a>Roly a povolenia

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Pracovný priestor je miesto, kde môžete ukladať a spravovať udalosti a zostavy. Ďalšie informácie nájdete v časti [Vytvorte pracovný priestor a pridajte členov](create-workspace.md). 

Pracovný priestor môže obsahovať nasledujúce roly a povolenia:

- Roly *Člen* sú používatelia, ktorí majú prístup do pracovného priestoru. Členom môžete priradiť svoj pracovný priestor a definovať ich roly a oprávnenia. 
- Roly *Správca* spravujú pracovné priestory a prostredia a konfigurujú prehľady interakcií pre ostatných používateľov. 
- Roly *Prispievateľ* sú zamerané na analytikov, ktorí nepotrebujú konfigurovať prehľady interakcií, ale chcú vytvárať vlastné zostavy, lieviky alebo segmenty.

## <a name="permissions"></a>Povolenia
  
Nasledujúca tabuľka identifikuje povolenia pre každú rolu. 

| Povolenie | Správca prostredia | Správca pracovného priestoru | Prispievateľ prostredia | Prispievateľ pracovného priestoru | 
|--|--|--|--|--|
| Vytváranie prostredí (tvorca sa automaticky stáva správcom prostredia) | X* | X* | X* | X* |  
| Konfigurácia prostredia (členovia prostredia, odstránenie prostredia) | X |  |  |  |  
| Vytvorenie pracovných priestorov | X |  |  |  |  
| Konfigurovať pracovné priestory (členovia pracovného priestoru, odstrániť pracovný priestor) | X | X |  |  |  
| Konfigurujte udalosti a vylepšené udalosti | X | X | |  |  
| Zobrazenie udalostí pracovného priestoru a vylepšených udalostí | X | X | |  |  
| Zobrazenie zdrojov pracovného priestoru (prehľady, segmenty a metriky)| X | X | X | X |  
| Vytvorenie vlastných zostáv a lievikov | X | X | X | X |  
| Vytvoriť základnú metriku a dimenzie| X | X |  |  |  
| Vytvorenie segmentov| X | X | X | X |  

* Skúšobné prostredia je možné vytvárať iba vo verzii Preview. 

## <a name="add-members"></a>Pridať členov

Môžete pridávať a odstraňovať členov z pracovných priestorov a prostredí. Viac informácií nájdete v časti [Prostredia a pracovné priestory](manage-environments-workspaces.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
