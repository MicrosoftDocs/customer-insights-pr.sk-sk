---
title: Konektor služby Power BI
description: Informácie o používaní konektora Dynamics 365 Customer Insights v Power BI.
ms.date: 09/21/2020
ms.reviewer: sthe
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: d497ca779a337c512a7254524f597cff226bcb45
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406895"
---
# <a name="connector-for-power-bi-preview"></a>Konektor pre Power BI (ukážka)

Vytvorte vizualizácie svojich údajov cez Power BI Desktop. Vytvárajte ďalšie informácie a zostavujte prehľady s vašimi zjednotenými údajmi o zákazníkoch.

## <a name="prerequisites"></a>Predpoklady

- Máte zjednotené profily zákazníkov.
- Najnovšia verzia [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) je nainštalovaná vo vašom počítači. [Ďalšie informácie o Power BI Desktop](https://docs.microsoft.com/power-bi/desktop-what-is-desktop)

## <a name="configure-the-connector-for-power-bi"></a>Nakonfigurujte konektor pre Power BI

1. V Power BI Desktop vyberte **Súbor** > **Získať údaje**.

1. Vyberte **Zobraziť viac** and vyhľadajte **Dynamics 365 Customer Insights**

1. Vyberte výsledok a položku **Pripojiť**.

1. **Prihláste sa** s účtom tej istej organizácie, ktorý používate pre Customer Insights a vyberte **Pripojiť sa**.
   > [!NOTE]
   > Účet, ktorý v tomto kroku uvediete, sa použije na načítanie údajov zo služby Customer Insights a nemusí byť totožný s tým, do ktorého ste prihlásení v Power BI. Ak chcete resetovať účet, ktorý sa používa na načítanie údajov, otvorte Power BI a prejdite na **Súbor** > **Možnosti** > **Nastavenia** > **Nastavenia zdroja údajov**. V zozname zdrojov údajov vyberte **Prihlásiť sa do Dynamics 365 Customer Insights** a vyberte **Vymazať povolenia**.  

1. V dialógovom okne **Navigátor**. zobrazí zoznam všetkých prostredí, ku ktorým máte prístup. Rozbaľte prostredie a otvorte ktorýkoľvek z priečinkov (entity, miery, segmenty, obohatenia). Napríklad otvorte priečinok **Entity**, aby ste videli všetky entity, ktoré môžete importovať.

   ![Navigátor konektora Power BI](media/power-bi-navigator.png "Navigátor konektora Power BI")

1. Začiarknite políčka vedľa entít, ktoré chcete zahrnúť, a vyberte **Načítať**. Môžete zvoliť viacero entít z viacerých prostredí.

1. Pri načítaní entít sa zobrazí dialógové okno načítania. Po načítaní všetkých vybratých entít môžete využívať možnosti služby Power BI na vizualizáciu údajov.

## <a name="large-data-sets"></a>Veľké množiny údajov

Konektor Customer Insights pre Power BI je navrhnutý tak, aby fungoval pre súbory údajov, ktoré obsahujú až 1 milión profilov zákazníkov. Import väčších množín údajov môže fungovať, ale trvá to dlho. Proces by navyše mohol vypršať kvôli časovému limitu Power BI. Viac informácií nájdete v časti [Power BI: Odporúčania pre veľké množiny údajov](https://docs.microsoft.com/power-bi/admin/service-premium-what-is#large-datasets). 

### <a name="work-with-a-subset-of-data"></a>Práca s podmnožinou údajov

Zvážte prácu s podmnožinou svojich údajov. Môžete napríklad vytvárať [segmenty](segments.md) namiesto exportovania všetkých záznamov zákazníkov do služby Power BI.
