---
title: Konektor služby Power BI
description: Informácie o používaní konektora Dynamics 365 Customer Insights v Power BI.
ms.date: 07/23/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: dccc069a355725bae09c1fece9292b9aee374e6d
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 02/16/2022
ms.locfileid: "8225544"
---
# <a name="connector-for-power-bi-preview"></a>Konektor pre Power BI (ukážka)

Vytvorte vizualizácie svojich údajov cez Power BI Desktop. Vytvárajte ďalšie informácie a zostavujte prehľady s vašimi zjednotenými údajmi o zákazníkoch.

## <a name="prerequisites"></a>Predpoklady

- Máte zjednotené profily zákazníkov.
- Najnovšia verzia [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) je nainštalovaná vo vašom počítači. [Ďalšie informácie o Power BI Desktop](/power-bi/desktop-what-is-desktop)

## <a name="configure-the-connector-for-power-bi"></a>Nakonfigurujte konektor pre Power BI

1. V Power BI Desktop vyberte **Súbor** > **Získať údaje**.

1. Vyberte **Zobraziť viac** and vyhľadajte **Dynamics 365 Customer Insights**

1. Vyberte možnosť **Pripojiť**.

1. **Prihláste sa** s účtom tej istej organizácie, ktorý používate pre Customer Insights a vyberte **Pripojiť sa**.
   > [!NOTE]
   > Účet, ktorý v tomto kroku uvediete, sa použije na načítanie údajov zo služby Customer Insights a nemusí byť totožný s tým, do ktorého ste prihlásení v Power BI. Ak chcete resetovať účet, ktorý sa používa na načítanie údajov, otvorte Power BI a prejdite na **Súbor** > **Možnosti** > **Nastavenia** > **Nastavenia zdroja údajov**. V zozname zdrojov údajov vyberte **Prihlásiť sa do Dynamics 365 Customer Insights** a vyberte **Vymazať povolenia**.  

1. V dialógovom okne **Navigátor**. zobrazí zoznam všetkých prostredí, ku ktorým máte prístup. Rozbaľte prostredie a otvorte ktorýkoľvek z priečinkov (entity, miery, segmenty, obohatenia). Napríklad otvorte priečinok **Entity**, aby ste videli všetky entity, ktoré môžete importovať.

   ![Navigátor konektora Power BI.](media/power-bi-navigator.png "Navigátor konektora Power BI")

1. Začiarknite políčka vedľa entít, ktoré chcete zahrnúť, a vyberte **Načítať**. Môžete zvoliť viacero entít z viacerých prostredí.

1. Pri načítaní entít sa zobrazí dialógové okno načítania. Po načítaní všetkých vybratých entít môžete využívať možnosti služby Power BI na vizualizáciu údajov.

## <a name="large-data-sets"></a>Veľké množiny údajov

Konektor Customer Insights pre Power BI je navrhnutý tak, aby fungoval pre súbory údajov, ktoré obsahujú až 1 milión profilov zákazníkov. Import väčších množín údajov môže fungovať, ale trvá to dlho. Proces by navyše mohol vypršať kvôli časovému limitu Power BI. Viac informácií nájdete v časti [Power BI: Odporúčania pre veľké množiny údajov](/power-bi/admin/service-premium-what-is#large-datasets). 

### <a name="work-with-a-subset-of-data"></a>Práca s podmnožinou údajov

Zvážte prácu s podmnožinou svojich údajov. Môžete napríklad vytvárať [segmenty](segments.md) namiesto exportovania všetkých záznamov zákazníkov do služby Power BI.

## <a name="troubleshooting"></a>Riešenie problémov

### <a name="customer-insights-environment-doesnt-show-in-power-bi"></a>Prostredie Customer Insights sa nezobrazuje v Power BI

Prostredia, ktoré majú viac ako jeden [vzťah](relationships.md) definovaný medzi dvoma rovnakými entitami v prehľadoch cieľových skupín, nebudú k dispozícii v konektore Power BI.

Môžete identifikovať a odstrániť duplicitné vzťahy.

1. V prehľadoch cieľových skupín choďte na **Údaje** > **Vzťahy** v prostredí, v ktorom vám chýba v Power BI.
2. Identifikujte duplicitné vzťahy:
   - Skontrolujte, či je medzi rovnakými dvoma entitami definovaných viac ako jeden vzťah.
   - Skontrolujte, či existuje vzťah medzi dvoma entitami, ktoré sú obe zahrnuté v procese zjednotenia. Existuje implicitný vzťah definovaný medzi všetkými entitami zahrnutými do procesu zjednotenia.
3. Odstráňte všetky zistené duplicitné vzťahy.

Po odstránení duplicitných vzťahov sa pokúste konektor Power BI nakonfigurovať znova. Prostredie by malo byť dostupné hneď.

### <a name="errors-on-date-fields-when-loading-entities-in-power-bi-desktop"></a>Pri načítaní entít do aplikácie Power BI Desktop sa vyskytli chyby v poliach dátumu

Pri načítavaní entít obsahujúcich polia s formátom dátumu, ako je MM/DD/RRRR, sa môžu vyskytnúť chyby v dôsledku nezhodných formátov miestnych nastavení. Tento nesúlad nastane vtedy, keď súbor aplikácie Power BI Desktop bol nastavený na iné miestne nastavenie ako je angličtina (USA), pretože polia dátumu v prehľadoch cieľovej skupiny sú uložené v americkom formáte.

Súbor aplikácie Power BI Desktop má jedno miestne nastavenie, ktoré sa používa pri získavaní údajov. Ak chcete, aby boli tieto polia dátumu interpretované správne, nastavte miestne nastavenie súboru .BPI na angličtinu (Spojené štáty americké). [Zistite, ako môžete zmeniť miestne nastavenia súboru počítačovej aplikácie Power BI](/power-bi/fundamentals/supported-languages-countries-regions.md#choose-the-locale-for-importing-data-into-power-bi-desktop).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
