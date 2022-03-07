---
title: Vytvoriť nové prostredie
description: Účel prostredia a spôsob, ako vytvoriť nové.
author: jusali
ms.reviewer: mhart
ms.author: jusali
ms.date: 10/04/2021
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 1f82ff588c2ffbe82c3ee7df2498ac2cca2bad31
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 02/16/2022
ms.locfileid: "8225466"
---
# <a name="create-a-new-environment"></a>Vytvoriť nové prostredie 

## <a name="overview"></a>Prehľad

Prostredie je priestor, v ktorom spravujete svoje pracovné priestory a pripojenia. To, ako používate prostredia, závisí od vašej organizácie a prípadu použitia. Môžete napríklad vytvárať:

- Jedno prostredie.
- Samostatné prostredia pre testovanie a výrobu.
- Samostatné prostredia pre konkrétne tímy alebo oddelenia vo vašej organizácii, ktoré obsahujú relevantné udalosti pre každé publikum.
- Samostatné prostredia pre rôzne globálne pobočky vašej spoločnosti.
- Možnosť pripojenia k Customer Insights audience insights

## <a name="create-a-new-environment"></a>Vytvoriť nové prostredie

1. Na pravej strane hlavného bannera vyberte nástroj na výber prostredia a potom **+Nové**.

   :::image type="content" source="media/environment-picker.png" alt-text="Vyberte nástroj na výber prostredia.":::

1. Na table **Nastavenie** zadajte príkaz **Názov prostredia**.

1. Vyberte **Typ** obchodného vzťahu, v závislosti od typu vášho plánu.

1. Zvoľte položku **Región** a označte **Ďalšie**. 

1. Typ a **Názov pracovného priestoru**, ktorá vám umožňuje zhromažďovať údaje pre konkrétne webové stránky alebo aplikácie. Ďalšie informácie nájdete v téme [Vytvorenie pracovného priestoru](create-workspace.md).

1. Vyber **Typ pracovného priestoru** (web alebo mobil), ktorý chcete vytvoriť. 

1. Vyberte **Ukázať pokročilé nastavenia** a povoľte alebo zakážte tieto voliteľné nastavenia:

   - Prepnite **Neznáme na známe** na „povolené“ na priradenie webových udalostí k používateľom, ktorí sa predtým autentifikovali. Ďalšie informácie nájdete v časti [Rozpoznajte webové udalosti od predtým overených návštevníkov](unknown-to-known.md).
   - Prepnite **Filtrovať prenos botov** na „povolené“, aby sa z tohto pracovného priestoru odstránili webovú návštevnosť botov. 

1. Po skončení vyberte možnosť **Dokončiť**. 

1. Nainštalujte úryvok kódu, aby ste mohli začať prijímať údaje, a potom vyberte **Dokončiť** na vytvorenie pracovného priestoru. Ďalšie informácie nájdete v téme [Prehľad zdrojov pre vývojárov](developer-resources.md).

> [!NOTE]
> Teraz môžete pridávať členov a priraďovať im úroveň povolení zo zoznamu **Úloha**. Ďalšie informácie nájdete v téme o [Roliach a povoleniach](user-roles.md). 

Viac informácií nájdete v časti [Správa prostredí a pracovných priestorov](manage-environments-workspaces.md).

## <a name="work-with-your-new-environment"></a>Pracujte vo svojom novom prostredí

- [Vytvorenie pracovného priestoru](../engagement-insights/create-workspace.md) a pridanie členov.
- [Pridajte kód na svoju webovú lokalitu](../engagement-insights/instrument-website.md) alebo [mobilnú aplikáciu](../engagement-insights/developer-resources.md#capture-events-from-mobile-apps).
- Prezerajte si [zostavu v reálnom čase](../engagement-insights/view-reports.md) alebo vytvárajte [vlastné zostavy](../engagement-insights/custom-reports.md).
- [Vytvorte spresnené udalosti](../engagement-insights/refined-events.md) pre export.
- [Exportujte údaje](../engagement-insights/export-events.md) do Data Lake Storage.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
