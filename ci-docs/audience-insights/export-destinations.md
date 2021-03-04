---
title: Ciele exportu
description: Exportujte údaje a spravujte ciele exportu.
ms.date: 07/21/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 63caa2ebdd7d637d14ac9c9cc7972095803aee2f
ms.sourcegitcommit: 0260ed244b97c2fd0be5e9a084c4c489358e8d4f
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 02/18/2021
ms.locfileid: "5477152"
---
# <a name="export-destinations-preview-overview"></a>Ciele exportu (verzia Preview) – prehľad

Stránka **Ciele exportu** zobrazuje všetky lokality, ktoré ste nastavili na export údajov. Môžete tiež pridať nové ciele na export. Ďalej sa zobrazujú možnosti exportu, ktoré sú v súčasnosti k dispozícii. Získajte rýchly prehľad, popis a zistite, čo môžete robiť s každou možnosťou rozšírenia. Exportujte zjednotené profily, miery a segmenty do podporovaných aplikácií relevantných pre vaše podnikanie.

Prejdite do ponuky **Správca** > **Ciele exportu** a nájdite nasledujúce možnosti rozšírenia:

- [Doplnok Karta Dynamics 365 Customer](customer-card-add-in.md)
- [Konektor správcu reklám Facebook](export-facebook.md)
- [Konektor Power Automate](export-power-automate.md)
- [Konektor Power Apps](export-power-apps.md)
- [Konektor Power BI](export-power-bi.md)
- [Autopilot](export-autopilot.md)
- [DotDigital](export-dotdigital.md)
- [Dynamics 365 Sales](export-dynamics365-sales.md)
- [Dynamics 365 Marketing](export-dynamics365-marketing.md)
- [Ukladací priestor objektu BLOB platformy Azure](export-azure-blob-storage.md)
- [Azure Data Lake Storage Gen2](export-azure-data-lake-storage-gen2.md)
- [SendGrid](export-sendgrid.md)
- [Konektor LiveRamp&reg;](export-liveramp.md)
- [Bot pre Microsoft Teams](export-teams-bot.md)
- [Mailchimp](export-mailchimp.md)
- [Customer Insights API](apis.md)

## <a name="add-a-new-export-destination"></a>Pridanie nového cieľa exportu

Ak chcete pridať ciele exportu, máte na to [povolenia správcu](permissions.md). Ak exportujete do služieb Microsoft, predpokladáme, že obidve služby sú v rovnakej organizácii.

1. Prejdite do ponuky **Správca** > **Ciele exportu**.

1. Prepnite na kartu **Moje ciele exportu**.

1. Vyberte **Pridať cieľ** a vytvorte si nový cieľ exportu.

1. V table **Pridať cieľ** zvoľte **Typ** exportu v rozbaľovacej ponuke cieľa exportu.

1. Zadajte požadované podrobnosti a vyberte položku **Ďalej** na vytvorenie cieľa exportu.

Môžete tiež vybrať **Nastaviť** na dlaždici na karte **Objavovať**.

## <a name="view-export-destinations"></a>Zobrazenie cieľov exportu

Po vytvorení cieľov exportu ich nájdete v tabuľke na karte **Moje ciele exportu** Táto tabuľka má tri stĺpce:

- **Zobrazovaný názov**: Názov, ktorý ste zadali pri vytváraní cieľa.
- **Typ**: Typ cieľa exportu, ktorý ste nastavili pri vytváraní cieľa.
- **Vytvorené**: Dátum vytvorenia cieľa.

## <a name="edit-an-export-destination"></a>Úprava cieľa exportu

1. Vyberte zvislé tri bodky pri cieli exportu, ktorý chcete upraviť.

   > [!div class="mx-imgBorder"]
   > ![Zvislé tri bodky](media/export-destinations-page-ellipsis.png "Zvislé tri bodky")

1. V rozbaľovacej ponuke vyberte položku **Upraviť**.

1. Zmeňte hodnoty, ktoré si vyžadujú aktualizáciu, a vyberte **Uložiť**.

## <a name="export-data-on-demand"></a>Export údajov na vyžiadanie

Po nakonfigurovaní konektora pre cieľ exportu sa export spustí pri každej [plánovanej obnove](system.md#schedule-tab).

Ak chcete exportovať údaje bez čakania na plánovanú obnovu, prejdite na kartu **Moje ciele exportu** v časti **Správca** > **Ciele exportu**.

> [!div class="mx-imgBorder"]
> ![Zvislé tri bodky](media/export-destinations-page-ellipsis.png "Zvislé tri bodky")

- Vyberte **Exportovať** nad zoznamom na spustenie exportu do všetkých cieľov exportu súčasne.
- Vyberte tri bodky (…) za položkou zoznamu a potom vyberte možnosť **Exportovať** na spustenie exportu pre jeden cieľ exportu.

## <a name="remove-an-export-destination"></a>Odstránenie cieľa exportu

Ak chcete odstrániť cieľ exportu, začnite na hlavnej stránke **Ciele exportu**.

1. Vyberte zvislé tri bodky pri cieli exportu, ktorý chcete odstrániť.

   > [!div class="mx-imgBorder"]
   > ![Zvislé tri bodky](media/export-destinations-page-ellipsis.png "Zvislé tri bodky")

2. Vyberte položku **Odstrániť** z rozbaľovacej ponuky.

3. Odstránenie potvrďte výberom položky **Odstrániť** na obrazovke s potvrdením.


[!INCLUDE[footer-include](../includes/footer-banner.md)]