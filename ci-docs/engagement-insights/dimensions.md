---
title: Zobrazenie a vytváranie dimenzií
description: Ako vytvárať, upravovať a odstraňovať dimenzie.
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 06/09/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: b575c5e84197d76f53a722bac60c5af928c917f9671720ede1de38c4a7478be4
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 08/10/2021
ms.locfileid: "7034016"
---
# <a name="view-and-create-dimensions"></a>Zobrazenie a vytváranie dimenzií

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Dimenzia je atribút udalosti, ktorý môže popisovať, filtrovať alebo zoskupovať údaje. Ak na svojom webe prevádzkujete marketingovú propagáciu, môžete pomocou dimenzií zoradiť návštevníkov podľa nových a vracajúcich sa používateľov.  

Prehľady interakcií zahŕňajú vopred pripravené dimenzie pre vlastnosti udalosti. Napríklad:

- Názov prehliadača
- Názov stránky
- Model zariadenia
- Operačný systém
- Krajina/oblasť

## <a name="view-dimensions"></a>Prezeranie dimenzií

Dimenzie sú založené na existujúcich vlastnostiach udalosti. Keď pre prehľady interakcií použijete kód sledovania, automaticky sa vytvoria dimenzie systému.

1. Na ľavej navigačnej table prejdite na **Údaje**. 
1. Vyberte **Dimenzie** na zobrazenie zoznamu všetkých dimenzií v pracovnom priestore. 
   > [!NOTE]
   > Dimenzie generované systémom sú iba na čítanie. Nemôžete ich upravovať. Môžete iba vytvárať a upravovať vlastné dimenzie.

## <a name="create-a-dimension"></a>Vytvorenie dimenzie

Okrem dimenzií generovaných systémom môžu správcovia prostredia a pracovných priestorov vytvárať aj vlastné dimenzie. Vlastné dimenzie sú založené na predvolených vlastnostiach základných udalostí alebo ich môžu použiť [vlastné vlastnosti udalosti](advanced-SDK-implementation.md).

1. Prejdite na **Údaje** > **Dimenzie**.
1. Vyberte **Pridať dimenziu**.

   :::image type="content" source="media/add-dimension.png" alt-text="Pridanie dimenzie k udalosti.":::

1. Na table **Vytvorenie dimenzie** vyberte vlastnosť, na ktorej bude založená dimenzia. V zozname vlastností sa zobrazia všetky vlastnosti v pracovnom priestore, ktoré nie sú priradené k dimenzii.
1. Do poľa **Zobrazovaný názov** zadajte názov. Voliteľne môžete pridať opis.
1. Výberom položky **Vytvoriť** uložte dimenziu. Môže trvať až jednu minútu, kým budete môcť dimenziu použiť vo [vlastnej zostave](custom-reports.md) alebo [segmente](segments.md). 

## <a name="edit-a-dimension"></a>Úprava dimenzie

Môžete zmeniť názov a popis dimenzie.

1. Prejdite na **Údaje** > **Dimenzie**.
1. Vyberte dimenziu, ktorú chcete odstrániť.
1. Na table **Upraviť dimenziu** aktualizujte dimenziu.
1. Zmeny uložte stlačením možnosti **Uložiť**.

## <a name="delete-a-dimension"></a>Odstránenie dimenzie

Odstrániť môžete iba dimenzie vytvorené používateľom, ale nemôžete odstrániť dimenzie systému.

Odstránenie dimenzie je trvalé. Zostavy a segmenty, ktoré používajú odstránenú dimenziu, nebudú viac fungovať. 

1. Prejdite na **Údaje** > **Dimenzie**.
1. Vyberte dimenziu, ktorú chcete odstrániť.
1. Na table **Upraviť dimenziu** vyberte **Odstrániť dimenziu**.

   :::image type="content" source="media/delete-dimension.png" alt-text="Odstránenie dimenzie k udalosti.":::

1. Zadajte **POTVRDIŤ ODSTRÁNENIE** (veľkými písmenami) na potvrdenie odstránenia. 
1. Vyberte **Odstrániť**.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
