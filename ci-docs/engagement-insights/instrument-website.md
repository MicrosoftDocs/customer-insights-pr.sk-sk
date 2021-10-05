---
title: Pridanie kódu k vašej webovej lokalite
description: Ako pridať úryvok kódu a zaznamenať udalosti Dynamics 365 Customer Insights na vašej webovej lokalite.
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 09/27/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: ad835f762226d62fdb0f544627f2a76ff09a1ffd
ms.sourcegitcommit: f1e3cc51ea4cf68210eaf0210ad6e14b15ac4fe8
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 09/27/2021
ms.locfileid: "7558912"
---
# <a name="install-the-web-sdk-on-a-website"></a>Nainštalujte si webovú súpravu SDK na webovú lokalitu

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Tento článok opisuje postup, akým správca nainštaluje súpravu nástrojov pre vývoj webového softvéru (SDK) na webovú lokalitu. Udalosti sa vám začnú zobrazovať vo vašom pracovnom priestore krátko po vytvorení inštancie na vašom webe. Viac informácií nájdete v časti [Správa pracovných priestorov a prostredia](manage-environments-workspaces.md). Ak chcete zaznamenávať udalosti v mobilných aplikáciách, prečítajte si [Prehľad zdrojov pre vývojárov](developer-resources.md).


### <a name="prerequisites"></a>Predpoklady

* Na ukladanie údajov musíte mať povolenie správcu pracovného priestoru.
* Vaša webová lokalita alebo projekt musia byť hosťované online, aby mohli posielať údaje o činnosti. Server nebude akceptovať údaje odoslané z lokálneho súboru.


## <a name="add-web-sdk-to-your-website"></a>Pridajte súpravu SDK na svoju webovú lokalitu!

Prejdite do ponuky **Správca** > **Pracovný priestor** a potom stlačte možnosť **Návod na inštaláciu**. Existujú dve možnosti inštalácie webovej súpravy SDK: Prvým je použitie odkazu na stiahnutie a druhým je nainštalovanie balíka správcu balíkov uzlov (NPM).

### <a name="option-1-using-the-download-link"></a>1. možnosť: Použitie odkazu na stiahnutie

1. Stlačte možnosť **Kopírovať kód** a skopírujte úryvok kódu. Predvolene je pre váš pracovný priestor kľúč príjmu vložený do úryvku kódu.
  :::image type="content" source="media/copy-code.png" alt-text="Snímka obrazovky stránky úryvku kódu.":::

1. Pridajte skopírovaný kód na svoj web neďaleko <head> značky a pred akýmkoľvek iným skriptom alebo značkami CSS.
1. Zverejnite svoj aktualizovaný web a počkajte niekoľko minút, kým zachytíte prichádzajúci prenos na webe.
1. Ak chcete zobraziť svoje údaje, vyberte svoj pracovný priestor z prepínača pracovného priestoru na navigačnej table. Potom vyberte jeden z prehľadov v priečinku sekcii **Objavovať**.

### <a name="option-2-using-the-npm-package-recommended-for-javascript-based-web-apps"></a>2. možnosť: Použite balík NPM (odporúča sa pre webové aplikácie založené na JavaScripte)

1. Prejdite na našu [webovú lokalitu NPM](https://www.npmjs.com/package/engagementinsights-web) a nainštalujte a nastavte balík web SDK NPM a postupujte podľa týchto pokynov.
1. Zverejnite svoj aktualizovaný web a počkajte niekoľko minút, kým zachytíte prichádzajúci prenos na webe.
1. Ak chcete zobraziť svoje údaje, vyberte svoj pracovný priestor z prepínača pracovného priestoru na navigačnej table. Potom vyberte jeden z prehľadov v priečinku sekcii **Objavovať**.

## <a name="configuration-options"></a>Možnosti konfigurácie

V úryvku kódu môžete zmeniť nasledujúce možnosti konfigurácie:

- **ingestionKey**: Kľúč príjmu používaný na odosielanie udalostí do vášho pracovného priestoru. Kľúč prijatia je možné zmeniť na odosielanie udalostí do iného pracovného priestoru. Pre každý pracovný priestor existuje jedinečný kľúč prijatia.
- **autoCapture**: Určuje, či sa majú zaznamenávať zobrazenia stránky a interakcie s webovou lokalitou. Má dve možnosti:
    - **zobrazenie**: Nastavené na *True* na zachytenie zobrazení stránky. Zobrazenia stránok sú zachytené ako *Zobrazenie* [udalosti](glossary.md#event), typ [základná udalosť](glossary.md#base-event).
    - **kliknutie**: Nastavené na *True* na zachytenie interakcií návštevníkov na webovej lokalite. Interakcie sú zaznamenané ako *Akcia* [udalosti](glossary.md#event), typ [základná udalosť](glossary.md#base-event).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
