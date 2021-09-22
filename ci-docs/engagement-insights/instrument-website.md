---
title: Pridanie kódu k vašej webovej lokalite
description: Ako pridať úryvok kódu na zaznamenanie udalostí na vašej webovej lokalite.
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 04/30/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: b5467da775a621c436bd9ddedb272506acc1e2b31dcf7c87feb5dd11e2daae2b
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 08/10/2021
ms.locfileid: "7035113"
---
# <a name="install-the-code-snippet-on-a-website"></a>Inštalácia úryvku kódu na webovej lokalite

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Tento článok popisuje, ako správca inštaluje úryvok kódu na webovú lokalitu. Krátko po pridaní skriptu na webovú lokalitu sa začnú vo vašom pracovnom priestore zobrazovať udalosti. Viac informácií nájdete v časti [Správa pracovných priestorov a prostredia](manage-environments-workspaces.md). Ak chcete zaznamenávať udalosti v mobilných aplikáciách, prečítajte si [Prehľad zdrojov pre vývojárov](developer-resources.md).


### <a name="prerequisites"></a>Predpoklady

* Na ukladanie údajov musíte mať povolenie správcu pracovného priestoru.
* Vaša webová lokalita alebo projekt musia byť hosťované online, aby mohli posielať údaje o činnosti. Server nebude akceptovať údaje odoslané z lokálneho súboru.


## <a name="add-code-to-your-website"></a>Pridanie kódu k vašej webovej lokalite
1.  Prejdite do ponuky **Správca** > **Pracovný priestor** a potom stlačte možnosť **Návod na inštaláciu**.
1. Stlačte možnosť **Kopírovať kód** a skopírujte úryvok kódu. Predvolene je pre váš pracovný priestor kľúč príjmu vložený do úryvku kódu.
:::image type="content" source="media/copy-code.png" alt-text="Snímka obrazovky stránky úryvku kódu.":::
3. Pridajte skopírovaný úryvok kódu na svoju webovú lokalitu v blízkosti <head> značky a pred akýmkoľvek iným skriptom alebo značkami CSS.
4.  Zverejnite svoj aktualizovaný web a počkajte niekoľko minút, kým zachytíte prichádzajúci prenos na webe.
5.  Ak chcete zobraziť svoje údaje, vyberte svoj pracovný priestor z prepínača pracovného priestoru na navigačnej table. Potom vyberte jeden z prehľadov v priečinku sekcii **Objavovať**.

## <a name="configuration-options"></a>Možnosti konfigurácie

V úryvku kódu môžete zmeniť nasledujúce možnosti konfigurácie:

- **ingestionKey**: Kľúč príjmu používaný na odosielanie udalostí do vášho pracovného priestoru. Kľúč prijatia je možné zmeniť na odosielanie udalostí do iného pracovného priestoru. Pre každý pracovný priestor existuje jedinečný kľúč prijatia. 
- **autoCapture**: Určuje, či sa majú zaznamenávať zobrazenia stránky a interakcie s webovou lokalitou. Má dve možnosti:
    - **zobrazenie**: Nastavené na *True* na zachytenie zobrazení stránky. Zobrazenia stránok sú zachytené ako *Zobrazenie* [udalosti](glossary.md#event), typ [základná udalosť](glossary.md#base-event).
    - **kliknutie**: Nastavené na *True* na zachytenie interakcií návštevníkov na webovej lokalite. Interakcie sú zaznamenané ako *Akcia* [udalosti](glossary.md#event), typ [základná udalosť](glossary.md#base-event).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
