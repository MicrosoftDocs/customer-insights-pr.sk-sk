---
title: Export údajov služby Customer Insights do Dynamics 365 Sales
description: Zistite ako nakonfigurovať pripojenie a realizovať exportovanie do Dynamics 365 Sales.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 9f11ab189117da5bcc1aee843b73962ec6615e82
ms.sourcegitcommit: 8cc70f30baaae13dfb9c4c201a79691f311634f5
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 07/30/2021
ms.locfileid: "6692362"
---
# <a name="use-segments-in-dynamics-365-sales-preview"></a>Použitie segmentov v Dynamics 365 Sales (ukážka)

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Dynamics 365 Sales umožňuje pomocou zákazníckych údajov vytvárať marketingové zoznamy, sledovať pracovné postupy a odosielať propagačné akcie.

## <a name="prerequisite-for-connection"></a>Predpoklad na pripojenie

1. Pred exportom segmentu z Customer Insights do Sales musia byť záznamy kontaktov v Dynamics 365 Sales. Prečítajte si viac o tom, ako prijímať kontakty v [Dynamics 365 Sales pomocou Microsoft Dataverse](connect-power-query.md).

   > [!NOTE]
   > Export segmentov z prehľadov cieľových skupín do Sales nevytvorí nové záznamy kontaktov v inštanciách Sales. Záznamy kontaktov zo Sales musia byť obsiahnuté v prehľadoch cieľových skupín a použité ako zdroj údajov. Pred exportom segmentov je ich tiež potrebné ich zahrnúť do zjednotenej entity zákazníka na mapovanie ID zákazníkov na ID kontaktov.

## <a name="set-up-the-connection-to-sales"></a>Nastavenie pripojenia k Sales

1. Prejdite do časti **Správca** > **Pripojenia**.

1. Stlačte možnosť **Pridať pripojenie** a stlačením možnosti **Dynamics 365 Sales** nakonfigurujte pripojenie.

1. Do poľa **Zobrazovaný názov** zadajte rozpoznateľný názov pripojenia. Zobrazovaný názov a typ spojenia, ktoré popisuje toto spojenie. Odporúčame zvoliť názov, ktorý vysvetľuje účel a cieľ tohto spojenia.

1. Vyberte používateľov, ktorí môžu používať toto pripojenie. Ak neurobíte nič, predvolená hodnota bude Správcovia. Viac informácií nájdete v časti [Umožnite prispievateľom použiť pripojenie na export](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Zadajte marketingovú adresu Predaj URL svojej organizácie do poľa **Adresa servera**.

1. V sekcii **Konto správcu servera** vyberte **Prihlásiť sa** a vyberte konto Dynamics 365 Sales.

1. Namapujte pole ID zákazníka k ID kontaktu služby Dynamics 365.

1. Stlačte možnosť **Uložiť** a dokončite pripojenie. 

## <a name="configure-an-export"></a>Nakonfigurujte export

Tento export môžete nakonfigurovať, ak máte prístup k pripojeniu tohto typu. Viac informácií nájdete na stránke [Na konfiguráciu exportu sú potrebné povolenia](export-destinations.md#set-up-a-new-export).

1. Prejdite na **Údaje** > **Exporty**.

1. Na vytvorenie nového exportu stlačte možnosť **Pridať cieľ**.

1. V poli **Pripojenie na export** vyberte pripojenie v časti Dynamics 365 Sales. Ak nevidíte názov tejto sekcie, nemáte k dispozícii žiadne spojenia tohto typu.

1. Vyberte jeden alebo viac segmentov.

1. Stlačte možnosť **Uložiť**

Uloženie exportu nespustí export okamžite.

Export prebieha s každým [plánovaným obnovením](system.md#schedule-tab). Môžete tiež [exportovať údaje na požiadanie](export-destinations.md#run-exports-on-demand). 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
