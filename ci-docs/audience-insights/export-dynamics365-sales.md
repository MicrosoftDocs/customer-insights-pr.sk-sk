---
title: Export údajov služby Customer Insights do Dynamics 365 Sales
description: Naučte sa, ako nakonfigurovať pripojenie k Dynamics 365 Sales.
ms.date: 02/01/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 39ecdf528c6be4d8fb420a52a6ed998317e43bcd
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598128"
---
# <a name="connector-for-dynamics-365-sales-preview"></a>Konektor pre Dynamics 365 Sales (ukážka)

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Dynamics 365 Sales umožňuje pomocou zákazníckych údajov vytvárať marketingové zoznamy, sledovať pracovné postupy a odosielať propagačné akcie.

## <a name="prerequisite"></a>Predpoklady

1. Pred exportom segmentu z Customer Insights do Sales musia byť záznamy kontaktov v Dynamics 365 Sales. Prečítajte si viac o tom, ako prijímať kontakty v [Dynamics 365 Sales pomocou Common Data Services](connect-power-query.md).

   > [!NOTE]
   > Export segmentov z prehľadov cieľových skupín do Sales nevytvorí nové záznamy kontaktov v inštanciách Sales. Záznamy kontaktov zo Sales musia byť obsiahnuté v prehľadoch cieľových skupín a použité ako zdroj údajov. Pred exportom segmentov je ich tiež potrebné ich zahrnúť do zjednotenej entity zákazníka na mapovanie ID zákazníkov na ID kontaktov.

## <a name="configure-the-connector-for-sales"></a>Nakonfigurujte konektor pre Predaj

1. V prehľadoch cieľových skupín prejdite na **Správca** > **Ciele exportu**.

1. Pod **Dynamics 365 Sales** vyberte **Nastaviť**.

1. Do poľa **Zobrazovaný názov** zadajte rozpoznateľný názov cieľa exportu.

1. Zadajte marketingovú adresu Predaj URL svojej organizácie do poľa **Adresa servera**.

1. V sekcii **Konto správcu servera** vyberte **Prihlásiť sa** a vyberte konto Dynamics 365 Sales.

1. Namapujte pole ID zákazníka k ID kontaktu služby Dynamics 365.

1. Vyberte **Ďalej**.

1. Vyberte jeden alebo viac segmentov.

1. Vyberte položku **Uložiť**.

## <a name="export-the-data"></a>Export údajov

Môžete [exportovať údaje na vyžiadanie](export-destinations.md). Export sa spustí aj pri každej [plánovanej obnove](system.md#schedule-tab).


[!INCLUDE[footer-include](../includes/footer-banner.md)]