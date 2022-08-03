---
title: Konektor Power BI (ukážka)
description: Informácie o používaní konektora Dynamics 365 Customer Insights v Power BI.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 656a695b8b3f1ec2b5fbaad69feba7f1f0b73dee
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196689"
---
# <a name="power-bi-connector-preview"></a>Konektor Power BI (ukážka)

Vytvorte vizualizácie pre svoje údaje pomocou Microsoft Power BI Desktop. Vytvárajte ďalšie informácie a zostavujte prehľady s vašimi zjednotenými údajmi o zákazníkoch.

## <a name="prerequisites"></a>Požiadavky

- Zjednotené profily zákazníkov.
- Najnovšia verzia [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) je nainštalovaná vo vašom počítači. [Ďalšie informácie o Power BI Desktop](/power-bi/desktop-what-is-desktop)

## <a name="configure-the-connector-for-power-bi"></a>Nakonfigurujte konektor pre Power BI

1. V Power BI Desktop vyberte **Súbor** > **Získať údaje**.

1. Vyberte **Zobraziť viac** and vyhľadajte **Dynamics 365 Customer Insights**

1. Vyberte možnosť **Pripojiť**.

1. **Prihláste sa** s účtom tej istej organizácie, ktorý používate pre Customer Insights a vyberte **Pripojiť sa**.
   > [!NOTE]
   > Účet, ktorý v tomto kroku uvediete, sa použije na načítanie údajov zo služby Customer Insights a nemusí byť totožný s tým, do ktorého ste prihlásení v Power BI. Ak chcete resetovať účet, ktorý sa používa na načítanie údajov, otvorte Power BI a prejdite na **Súbor** > **Možnosti** > **Nastavenia** > **Nastavenia zdroja údajov**. V zozname zdrojov údajov vyberte **Prihlásiť sa do Dynamics 365 Customer Insights** a vyberte **Vymazať povolenia**.  

1. V **Navigátor** v dialógovom okne zobrazte zoznam všetkých prostredí, ku ktorým máte prístup. Rozbaľte prostredie a otvorte ktorýkoľvek z priečinkov (entity, miery, segmenty, obohatenia). Napríklad otvorte priečinok **Entity**, aby ste videli všetky entity, ktoré môžete importovať.

   :::image type="content" source="media/power-bi-navigator.png" alt-text="Navigátor konektora Power BI.":::

1. Začiarknite políčka vedľa entít, ktoré chcete zahrnúť, a vyberte **Načítať**. Môžete zvoliť viacero entít z viacerých prostredí.

   Počas načítania entít sa zobrazí dialógové okno načítania. Po načítaní všetkých vybratých entít použite možnosti Power BI na vizualizáciu údajov.

## <a name="large-data-sets"></a>Veľké množiny údajov

Konektor Customer Insights pre Power BI je navrhnutý tak, aby fungoval pre súbory údajov, ktoré obsahujú až 1 milión profilov zákazníkov. Import väčších množín údajov môže fungovať, ale trvá dlho a môže uplynúť časový limit Power BI obmedzenia. Viac informácií nájdete v časti [Power BI: Odporúčania pre veľké množiny údajov](/power-bi/admin/service-premium-what-is#large-datasets).

### <a name="work-with-a-subset-of-data"></a>Práca s podmnožinou údajov

Zvážte prácu s podmnožinou svojich údajov. Napríklad vytvorte [segmentov](segments.md) namiesto exportu všetkých záznamov zákazníkov do Power BI.

## <a name="troubleshooting"></a>Riešenie problémov

### <a name="customer-insights-environment-doesnt-show-in-power-bi"></a>Prostredie Customer Insights sa nezobrazuje v Power BI

Prostredia, ktoré majú viac ako jeden [vzťah](relationships.md) definované medzi dvoma identickými entitami v Customer Insights nebudú dostupné v Power BI konektor.

Identifikujte a odstráňte duplicitné vzťahy.

1. Ísť do **Údaje** > **Vzťahy** na prostredie, v ktorom vám chýba Power BI.
1. Identifikujte duplicitné vzťahy:
   - Skontrolujte, či je medzi rovnakými dvoma entitami definovaných viac ako jeden vzťah.
   - Skontrolujte, či existuje vzťah medzi dvoma entitami, ktoré sú obe zahrnuté v procese zjednotenia. Existuje implicitný vzťah definovaný medzi všetkými entitami zahrnutými do procesu zjednotenia.
1. Odstráňte všetky zistené duplicitné vzťahy.

Po odstránení duplicitných vzťahov sa pokúste konektor Power BI nakonfigurovať znova.

### <a name="errors-on-date-fields-when-loading-entities-in-power-bi-desktop"></a>Pri načítaní entít do aplikácie Power BI Desktop sa vyskytli chyby v poliach dátumu

Pri načítavaní entít, ktoré obsahujú polia s formátom dátumu ako MM/DD/RRRR, sa môžu vyskytnúť chyby v dôsledku nezhodujúcich sa formátov miestnych nastavení. Tento nesúlad nastane, keď váš Power BI Desktop súbor je nastavený na iné miestne nastavenie ako angličtina (Spojené štáty), pretože polia dátumu v Customer Insights sú uložené v americkom formáte.

Súbor aplikácie Power BI Desktop má jedno miestne nastavenie, ktoré sa používa pri získavaní údajov. Ak chcete opraviť chyby dátumu, [nastaviť miestne nastavenie súboru .BPI](/power-bi/fundamentals/supported-languages-countries-regions#choose-the-language-or-locale-of-power-bi-desktop) do angličtiny (Spojené štáty americké).

[!INCLUDE [footer-include](includes/footer-banner.md)]
