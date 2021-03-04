---
title: Export údajov služby Customer Insights do Dynamics 365 Marketing
description: Naučte sa, ako nakonfigurovať pripojenie k Dynamics 365 Marketing.
ms.date: 02/01/2021
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: a06920b8ff25d7102ccd14ae68cf42fe91fa1ee6
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269073"
---
# <a name="connector-for-dynamics-365-marketing-preview"></a>Konektor pre Dynamics 365 Marketing (ukážka)

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Dynamics 365 Marketing umožňuje pomocou [segmentov](segments.md) generovať kampane a kontaktovať konkrétne skupiny zákazníkov. Viac informácií nájdete v článku [Použitie segmentov z Dynamics 365 Customer Insights s Dynamics 365 Marketing](https://docs.microsoft.com/dynamics365/marketing/customer-insights-segments)

## <a name="prerequisite"></a>Predpoklady

- Pred exportom segmentu z Customer Insights do Sales Marketing byť záznamy kontaktov v Dynamics 365 Marketing. Prečítajte si viac o tom, ako prijímať kontakty v [Dynamics 365 Marketing pomocou Common Data Services](connect-power-query.md).

  > [!NOTE]
  > Export segmentov z prehľadov cieľových skupín do Marketing nevytvorí nové záznamy kontaktov v inštanciách Marketing. Záznamy kontaktov z Marketing musia byť obsiahnuté v prehľadoch cieľových skupín a použité ako zdroj údajov. Pred exportom segmentov je ich tiež potrebné ich zahrnúť do zjednotenej entity zákazníka na mapovanie ID zákazníkov na ID kontaktov.

## <a name="configure-the-connector-for-marketing"></a>Nakonfigurujte konektor pre Marketing

1. V prehľadoch cieľových skupín prejdite na **Správca** > **Ciele exportu**.

1. Pod **Dynamics 365 Marketing** vyberte **Nastaviť**.

1. Do poľa **Zobrazovaný názov** zadajte rozpoznateľný názov cieľa exportu.

1. Zadajte marketingovú adresu URL svojej organizácie do poľa **Adresa servera**.

1. V sekcii **Konto správcu servera** vyberte **Prihlásiť sa** a vyberte Dynamics 365 Marketing.

1. Namapujte pole ID zákazníka k ID kontaktu služby Dynamics 365.

1. Vyberte **Ďalej**.

1. Vyberte jeden alebo viac segmentov.

1. Vyberte položku **Uložiť**.

## <a name="export-the-data"></a>Export údajov

Môžete [exportovať údaje na vyžiadanie](export-destinations.md). Export sa spustí aj pri každej [plánovanej obnove](system.md#schedule-tab).


[!INCLUDE[footer-include](../includes/footer-banner.md)]