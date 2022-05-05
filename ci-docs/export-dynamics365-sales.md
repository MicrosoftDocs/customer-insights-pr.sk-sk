---
title: Export údajov služby Customer Insights do Dynamics 365 Sales
description: Zistite ako nakonfigurovať pripojenie a realizovať exportovanie do Dynamics 365 Sales.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
searchScope:
- ci-export
- customerInsights
ms.openlocfilehash: 987690283090ec83ca75f50bf8f3cd8da9295887
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 04/27/2022
ms.locfileid: "8643319"
---
# <a name="use-segments-in-dynamics-365-sales-preview"></a>Použitie segmentov v Dynamics 365 Sales (ukážka)



Dynamics 365 Sales umožňuje pomocou zákazníckych údajov vytvárať marketingové zoznamy, sledovať pracovné postupy a odosielať propagačné akcie.

## <a name="known-limitations"></a>Známe obmedzenia

- Exporty do Dynamics 365 Sales sú obmedzené na 100 000 členov na segment.
- Dokončenie exportov segmentov do Dynamics 365 Sales môže trvať až 3 hodiny. 

## <a name="prerequisite-for-connection"></a>Predpoklad na pripojenie

1. Pred exportom segmentu z Customer Insights do Sales musia byť záznamy kontaktov v Dynamics 365 Sales. Prečítajte si viac o tom, ako prijímať kontakty z [Dynamics 365 Sales pomocou Microsoft Dataverse](connect-dataverse-managed-lake.md).

   > [!NOTE]
   > Export segmentov z Customer Insights do Sales nevytvorí nové záznamy kontaktov v inštanciách predaja. Záznamy kontaktov z predaja musia byť prijaté v Customer Insights a použité ako zdroj údajov. Pred exportom segmentov je ich tiež potrebné ich zahrnúť do zjednotenej entity zákazníka na mapovanie ID zákazníkov na ID kontaktov.

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

[!INCLUDE [footer-include](includes/footer-banner.md)]
