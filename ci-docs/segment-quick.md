---
title: Vytvorte jednoduché segmenty pomocou rýchlych segmentov
description: Vytvorte jednoduché segmenty zákazníkov a zoskupte ich na základe rôznych atribútov.
ms.date: 03/25/2022
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-segments
- ci-segment-builder
- ci-segment-details
- customerInsights
ms.openlocfilehash: 98260371a17ff8a05912cc1bc08c67fbe9755727
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 07/18/2022
ms.locfileid: "9171166"
---
# <a name="create-simple-segments-with-quick-segments"></a>Vytvorte jednoduché segmenty pomocou rýchlych segmentov

Rýchle segmenty vám umožňujú rýchlo vytvárať jednoduché segmenty pomocou jedného operátora a získať tak rýchlejší prehľad. Rýchle segmenty sú podporované iba v prostrediach pre **individuálnych zákazníkov**.

## <a name="create-a-new-segment-with-quick-segments"></a>Vytvorte nový segment s rýchlymi segmentmi

1. Prejdite na **Segmenty**.

1. Vyberte **Nový** > **Vytvoriť z**.
   - Vyberte možnosť **Profily** na vytvorenie segmentu, ktorý je založený na *zjednotenej entite zákazníka*.
   - Stlačte možnosť **Opatrenia** a vytvorte segment okolo opatrení, ktoré ste predtým vytvorili.
   - Vyberte možnosť **Analýza** na zostavenie segmentu okolo jednej z výstupných entít, ktoré ste vygenerovali pomocou funkcií **Predpovede** alebo **Vlastné modely**.

1. V dialógovom okne **Nový rýchly segment** vyberte atribút z rozbaľovacej ponuky **Pole**. Na základe vášho výberu systém poskytuje rôzne hodnoty.
   - Pre kategorické polia sa zobrazí 10 najväčších počtov zákazníkov. Vyberte **Hodnota** a potom **Skontrolovať**.
   - Pre číselný atribút systém ukazuje, aká hodnota atribútu spadá pod percentil každého zákazníka. Vyberte **Operátor** a **Hodnota**, potom vyberte **Skontrolovať**.

1. Systém poskytuje **Odhadovaná veľkosť segmentu**. Vyberte, či chcete vygenerovať segment, ktorý ste definovali, alebo sa vráťte a vyberte iné pole.

   :::image type="content" source="media/quick-segment-name.png" alt-text="Názov a odhad rýchleho segmentu.":::

1. Poskytnúť **názov** a **Názov výstupnej entity** pre váš segment. Prípadne pridajte [značky](work-with-tags-columns.md#manage-tags).

1. Výberom položky **Uložiť** vytvorte segment. The **Segmenty** zobrazí stránka.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="next-steps"></a>Ďalšie kroky

[Exportujte segment](export-destinations.md) a preskúmajte časť [Integrácia karty zákazníka](customer-card-add-in.md) na používanie segmentov v iných aplikáciách.

[!INCLUDE [footer-include](includes/footer-banner.md)]
