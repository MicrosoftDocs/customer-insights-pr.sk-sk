---
title: Zobrazenie a vytváranie metrík
description: Ako vytvárať, upravovať a odstraňovať metriky.
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 10/01/2021
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 7e8c96f38af74f25080a40fd92e73f05c71320a8
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 02/16/2022
ms.locfileid: "8229835"
---
# <a name="view-and-create-metrics"></a>Zobrazenie a vytváranie metrík

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Metriky pomáhajú pochopiť správanie vašich návštevníkov. Agregujú vlastnosti udalostí a merajú štatistiku a výkon vašich webových aktív.  

Predpokladajme, že na svojom webe prevádzkujete marketingovú propagáciu. Pomocou metrík môžete sledovať počet jedinečných návštevníkov alebo používateľov, ktorí prišli na váš web počas propagácie. Analýza metrík vám pomôže lepšie pochopiť cieľovú skupinu vášho webu. Kombinácia metrík s [dimenziami](dimensions.md) na [vlastnej zostave](custom-reports.md) umožňuje merať správanie, aby ste pochopili svojich používateľov. Môžete napríklad rozdeliť návštevníkov do kategórií nových a vracajúcich sa, aby ste identifikovali rozdiely v záujme a zámere medzi skupinami.

## <a name="view-metrics"></a>Prezeranie metrík

Prehľady interakcií zahŕňajú bežne používané agregácie vlastností udalostí ako systémové metriky: 

- Návštevníci
- Návštevy
- Zobrazenia stránky
- Kliknutia

Tieto systémové metriky sú založené na existujúcich vlastnostiach udalostí v základných udalostiach.

1. Na ľavej navigačnej table prejdite na **Údaje**. 
1. Vyberte kartu **Metriky** na zobrazenie zoznamu všetkých metrík v pracovnom priestore. 
   > [!NOTE]
   > Metriky generované systémom sú iba na čítanie. Nemôžete ich aktualizovať ani odstrániť. Môžete iba vytvárať a upravovať vlastné metriky.

## <a name="create-a-metric"></a>Vytvorenie metriky

Správcovia prostredia a pracovných priestorov môžu vytvárať metriky. Pred vytvorením metriky je potrebné do pracovného priestoru odoslať vlastnosti udalosti. Môžete vytvoriť metriky na základe vlastností udalostí, ktoré sú odosielané základnými udalosťami, alebo použiť webovú SDK na [odoslanie vlastných vlastností udalosti](advanced-SDK-implementation.md).

1. Prejdite na **Údaje** > **Metriky**.
1. Vyberte **Nová metrika** na otvorenie položky **Knižnica zdrojov** a dialógového okna **Nová metrika bez názvu**.

   :::image type="content" source="media/new-metric.png" alt-text="Pridajte k udalosti metriku.":::

1. V dialógovom okne **Nová metrika bez názvu** vyberte **Formát** v rozbaľovacom zozname a vyberte typ údajov **Integer** alebo **Double**. Integer je celé číslo. V prípade Double môžete vybrať jedno a tri desatinné miesta.

   :::image type="content" source="media/create-new-metric.png" alt-text="Vytvorenie novej metriky.":::
   
5. Na table **Knižnica zdrojov** vyhľadajte vlastnosť udalosti, na ktorej je založená metrika.
6. Vyberte **znamienko plus (+)** vedľa vlastnosti, aby sa použilo vo vzorci. Vzorec môžete vytvoriť iba na základe jednej vlastnosti. 
7. Vyberte jednu z nasledovných funkcií agregácie. 

   - Súčet: aritmetický súčet všetkých hodnôt 
   - Priemer: stredný priemer všetkých hodnôt
   - Počet: celkový počet hodnôt
   - Jedinečný počet: celkový počet jedinečných hodnôt

   Po definovaní metriky sa zobrazí ukážka aktivity metriky za poslednú hodinu.

1. Vyberte položku **Uložiť**. 
1. Zadajte názov metriky a vyberte položku **Uložiť**.

Môže to trvať až minútu, kým ju budete môcť použiť na [vytváranie vlastných zostáv](custom-reports.md).

## <a name="edit-a-metric"></a>Úprava metriky

Môžete upravovať iba vlastné metriky.

1. Prejdite na **Údaje** > **Metriky**.
1. Vyberte metriku v zozname.
1. Zmena definície metriky
1. Vyberte položku **Uložiť**.

## <a name="change-the-name-of-a-metric"></a>Zmena názvu metriky

Môžete zmeniť iba názov vlastných metrík.

1. Prejdite na **Údaje** > **Metriky**.
1. Vyberte **Viac [...]** pre metriku a následne **Upraviť názov**.
1. Zmeňte názov. 
1. Vyberte **Premenovať**.

## <a name="delete-a-metric"></a>Odstránenie metriky

Môžete odstrániť iba vlastné metriky.

1. Prejdite na **Údaje** > **Metriky**.
1. Vyberte **Viac [...]** pre metriku a následne **Odstrániť**.

   :::image type="content" source="media/delete-metric.png" alt-text="Odstránenie metriky pre udalosť.":::

1. Vyberte možnosť **Odstrániť** a potvrďte odstránenie.



[!INCLUDE[footer-include](../includes/footer-banner.md)]
