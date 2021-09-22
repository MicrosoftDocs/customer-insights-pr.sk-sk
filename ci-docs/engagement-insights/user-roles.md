---
title: Roly a povolenia
description: Prehľad dostupných rol a povolení pre členov pracovného priestoru.
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 07/06/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 6d7f4db4a130fc15a69b380c892538db5492d96d8e13f3c070c6a6b9bd098371
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036712"
---
# <a name="roles-and-permissions"></a>Roly a povolenia

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Pracovný priestor je priestor na ukladanie a správu udalostí a správ. Člen je používateľ, ktorý má prístup do pracovného priestoru. Členom môžete priradiť svoj pracovný priestor a definovať ich roly a oprávnenia. Roly správcu spravujú pracovné priestory a prostredia a prehľady konfigurácie zapojenia pre ostatných používateľov. Roly prispievateľov sa zameriavajú na analytikov, ktorí nepotrebujú nakonfigurovať prehľady interakcií, ale potrebujú vytvárať vlastné prehľady, lieviky alebo segmenty.

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
