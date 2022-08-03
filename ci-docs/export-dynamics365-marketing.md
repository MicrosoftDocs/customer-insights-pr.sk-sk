---
title: Export segmentov do Dynamics 365 Marketing (ukážka)
description: Zistite ako nakonfigurovať pripojenie a realizovať exportovanie do Dynamics 365 Marketing.
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
ms.openlocfilehash: 123b565421a7d096e7341a8f600f91e59aefe8d0
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196643"
---
# <a name="export-segments-to-dynamics-365-marketing-preview"></a>Export segmentov do Dynamics 365 Marketing (ukážka)

Použite [segmentov](segments.md) vytvárať kampane a kontaktovať konkrétne skupiny zákazníkov [Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments).

Ak používate nové možnosti Dynamics 365 Marketing na orchestráciu činnosť zákazníka v reálnom čase v organizácii Dataverse, nemusíte vytvárať štandardný export do Dynamics 365 Marketing. Kontakty a segmenty z Customer Insights sú dostupné priamo v Dynamics 365 Marketing po prepojení Marketing a Customer Insights. Pred odstránením existujúcich exportov si prečítajte dokumentáciu na [ako prepojiť Customer Insights a Dynamics 365 Marketing činnosť zákazníka orchestráciu](/dynamics365/marketing/real-time-marketing-ci-profile).

## <a name="prerequisite"></a>Predpoklady

Pred exportom segmentu z Customer Insights do Sales Marketing byť záznamy kontaktov v Dynamics 365 Marketing. Prečítajte si viac o tom, ako prijímať kontakty v [Dynamics 365 Marketing pomocou Microsoft Dataverse](connect-dataverse-managed-lake.md).

> [!NOTE]
> Export segmentov z Customer Insights do Marketing nevytvorí nové záznamy kontaktov v inštanciách Marketing. Záznamy kontaktov z Marketingu musia byť prijaté v Customer Insights a použité ako zdroj údajov. Pred exportom segmentov je ich tiež potrebné ich zahrnúť do zjednotenej entity zákazníka na mapovanie ID zákazníkov na ID kontaktov.

## <a name="set-up-connection-to-marketing"></a>Nastavenie pripojenia k Marketing

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Prejdite do časti **Správca** > **Pripojenia**.

1. Vyberte **Pridať pripojenie** a vyberte si **Dynamics 365 Marketing**.

1. Do poľa **Zobrazovaný názov** zadajte rozpoznateľný názov pripojenia. Zobrazovaný názov a typ spojenia, ktoré popisuje toto spojenie. Odporúčame zvoliť názov, ktorý vysvetľuje účel a cieľ tohto spojenia.

1. Vyberte používateľov, ktorí môžu používať toto pripojenie. Predvolene sú to iba správcovia. Viac informácií nájdete v časti [Umožnite prispievateľom použiť pripojenie na export](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Zadajte marketingovú adresu URL svojej organizácie do poľa **Adresa servera**.

1. V sekcii **Konto správcu servera** vyberte **Prihlásiť sa** a vyberte Dynamics 365 Marketing.

1. Mapujte pole ID kontaktu v entite zákazníka na ID kontaktu Dynamics 365.

1. Skontrolujte [ochrana osobných údajov a dodržiavanie predpisov](connections.md#data-privacy-and-compliance) a vyberte **Súhlasím**.

1. Stlačte možnosť **Uložiť** a dokončite pripojenie.

## <a name="configure-an-export"></a>Nakonfigurujte export

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Prejdite na **Údaje** > **Exporty**.

1. Vyberte **Pridať export**.

1. V poli **Pripojenie na export** vyberte pripojenie v časti Dynamics 365 Marketing. Ak nie je k dispozícii pripojenie, kontaktujte správcu.

1. Zadajte názov exportu.

1. Vyberte pole ID kontaktu v entite zákazníka, ktoré sa zhoduje s ID kontaktu Dynamics 365.

1. Vyberte segmenty, ktoré chcete exportovať.

1. Vyberte **Uložiť**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
