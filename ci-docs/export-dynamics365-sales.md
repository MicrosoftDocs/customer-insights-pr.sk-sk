---
title: Export segmentov do Dynamics 365 Sales (ukážka)
description: Zistite ako nakonfigurovať pripojenie a realizovať exportovanie do Dynamics 365 Sales.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
searchScope:
- ci-export
- customerInsights
ms.openlocfilehash: c3497f4625cada49ae33c6987e58994a15536f9b
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196000"
---
# <a name="export-segments-to-dynamics-365-sales-preview"></a>Export segmentov do Dynamics 365 Sales (ukážka)

Dynamics 365 Sales umožňuje pomocou zákazníckych údajov vytvárať marketingové zoznamy, sledovať pracovné postupy a odosielať propagačné akcie.

## <a name="prerequisites"></a>Požiadavky

Pred exportom segmentu z Customer Insights do Sales musia byť záznamy kontaktov v Dynamics 365 Sales. Prečítajte si viac o tom, ako prijímať kontakty z [Dynamics 365 Sales pomocou Microsoft Dataverse](connect-dataverse-managed-lake.md).

   > [!NOTE]
   > Export segmentov z Customer Insights do Sales nevytvorí nové záznamy kontaktov v inštanciách predaja. Záznamy kontaktov z predaja musia byť prijaté v Customer Insights a použité ako zdroj údajov. Pred exportom segmentov je ich tiež potrebné ich zahrnúť do zjednotenej entity zákazníka na mapovanie ID zákazníkov na ID kontaktov.

## <a name="known-limitations"></a>Známe obmedzenia

Exporty do Dynamics 365 Sales sú obmedzené na 100 000 na segment, čo môže trvať až 3 hodiny.

## <a name="set-up-connection-to-sales"></a>Nastavte pripojenie k Sales

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Prejdite do časti **Správca** > **Pripojenia**.

1. Vyberte **Pridať pripojenie** a vyberte si **Dynamics 365 Sales**.

1. Do poľa **Zobrazovaný názov** zadajte rozpoznateľný názov pripojenia. Zobrazovaný názov a typ spojenia, ktoré popisuje toto spojenie. Odporúčame zvoliť názov, ktorý vysvetľuje účel a cieľ tohto spojenia.

1. Vyberte používateľov, ktorí môžu používať toto pripojenie. Predvolene sú to iba správcovia. Viac informácií nájdete v časti [Umožnite prispievateľom použiť pripojenie na export](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Zadajte marketingovú adresu Predaj URL svojej organizácie do poľa **Adresa servera**.

1. V sekcii **Konto správcu servera** vyberte **Prihlásiť sa** a vyberte konto Dynamics 365 Sales.

1. Namapujte pole ID zákazníka k ID kontaktu služby Dynamics 365.

1. Skontrolujte [ochrana osobných údajov a dodržiavanie predpisov](connections.md#data-privacy-and-compliance) a vyberte **Súhlasím**.

1. Stlačte možnosť **Uložiť** a dokončite pripojenie.

## <a name="configure-an-export"></a>Nakonfigurujte export

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Prejdite na **Údaje** > **Exporty**.

1. Vyberte **Pridať export**.

1. V poli **Pripojenie na export** vyberte pripojenie v časti Dynamics 365 Sales. Ak nie je k dispozícii pripojenie, kontaktujte správcu.

1. Zadajte názov exportu.

1. Vyberte pole ID kontaktu v entite zákazníka, ktoré sa zhoduje s ID kontaktu Dynamics 365.

1. Vyberte segmenty, ktoré chcete exportovať.

1. Stlačte možnosť **Uložiť**

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
