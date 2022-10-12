---
title: Naplánujte obnovenie systému
description: Naplánujte si čas, kedy sa má systém obnoviť
ms.date: 09/27/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-system-schedule
- customerInsights
ms.openlocfilehash: 4aac02b570357d2086f7a9d7340b0e4837157a0b
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610347"
---
# <a name="schedule-system-refresh"></a>Naplánujte obnovenie systému

Naplánujte si automatické obnovy všetkých vašich [prehltnuté zdroje údajov](data-sources.md). Automatické obnovovanie pomáha zaistiť, aby sa aktualizácie z vašich zdrojov údajov prejavili vo vašich zjednotených profiloch zákazníkov.

> [!NOTE]
> Power Query vami spravované zdroje údajov sa obnovujú podľa vlastných plánov. Ak chcete naplánovať obnovenie týchto položiek Power Query zdroje údajov, nakonfigurujte nastavenia obnovenia na tomto konkrétnom zdroj údajov z **Zdroje dát** stránku. Zosúlaďte načasovanie s plánom obnovy údajov upstream tak, aby k obnovám nedošlo naraz.
> :::image type="content" source="media/PPDF-edit-refresh.png" alt-text="Power Platform Nastavenia obnovenia toku údajov.":::

## <a name="set-system-refresh-schedule"></a>Nastavte plán obnovy systému

1. Ísť do **Admin** > **Systém** a vyberte **Rozvrh** tab.

   :::image type="content" source="media/schedule_refresh.png" alt-text="Naplánujte kartu obnovenia zo stránky Systém.":::

1. Predvolený stav plánovanej obnovy je **Vyp.** Ak chcete povoliť naplánované obnovovanie, zmeňte prepínač v hornej časti obrazovky na **Zap.**

1. Vyberte si medzi **Týždenné** (predvolené) a **Denné** obnovenie. Ak chcete naplánovať týždenné obnovovanie, vyberte jeden alebo viac dní, v ktorých chcete obnovenie spustiť.

1. Nastavte si **Časové pásmo**, potom použite rozbaľovaciu ponuku **Čas** a nastavte časovanie obnovenia. Ak chcete naplánovať viac aktualizácií za jeden deň, vyberte položku **Pridať ďalší čas**. Môžete pridať až štyri obnovenia.

1. Zmeny vykonajte výberom položky **Uložiť**.

[!INCLUDE [footer-include](includes/footer-banner.md)]
