---
title: Export segmentov do Dynamics 365 Marketing (ukážka)
description: Zistite ako nakonfigurovať pripojenie a realizovať exportovanie do Dynamics 365 Marketing.
ms.date: 08/24/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
searchScope:
- ci-export
- customerInsights
ms.openlocfilehash: fed4ae1b017cca2b6060c4dda155859cd77e0daf
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 06/29/2022
ms.locfileid: "9054635"
---
# <a name="export-segments-to-dynamics-365-marketing-preview"></a>Export segmentov do Dynamics 365 Marketing (ukážka)

Dynamics 365 Marketing umožňuje pomocou [segmentov](segments.md) generovať kampane a kontaktovať konkrétne skupiny zákazníkov. Viac informácií nájdete v článku [Použitie segmentov z Dynamics 365 Customer Insights s Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments).

Ak používate nové možnosti Dynamics 365 Marketing na orchestráciu činnosť zákazníka v reálnom čase v organizácii Dataverse, nemusíte vytvárať štandardný export do Dynamics 365 Marketing. Kontakty a segmenty z Customer Insights sú dostupné priamo v Dynamics 365 Marketing po prepojení Marketing a Customer Insights. Pred odstránením existujúcich exportov si prečítajte dokumentáciu na [ako prepojiť Customer Insights a Dynamics 365 Marketing činnosť zákazníka orchestráciu](/dynamics365/marketing/real-time-marketing-ci-profile).

## <a name="prerequisite-for-a-connection"></a>Predpoklad na pripojenie

- Pred exportom segmentu z Customer Insights do Sales Marketing byť záznamy kontaktov v Dynamics 365 Marketing. Prečítajte si viac o tom, ako prijímať kontakty v [Dynamics 365 Marketing pomocou Microsoft Dataverse](connect-dataverse-managed-lake.md).

  > [!NOTE]
  > Export segmentov z Customer Insights do Marketing nevytvorí nové záznamy kontaktov v inštanciách Marketing. Záznamy kontaktov z Marketingu musia byť prijaté v Customer Insights a použité ako zdroj údajov. Pred exportom segmentov je ich tiež potrebné ich zahrnúť do zjednotenej entity zákazníka na mapovanie ID zákazníkov na ID kontaktov.

## <a name="set-up-connection-to-marketing"></a>Nastavenie pripojenia k Marketing

1. Prejdite do časti **Správca** > **Pripojenia**.

1. Stlačte možnosť **Pridať pripojenie** a stlačením možnosti **Dynamics 365 Marketing** nakonfigurujte pripojenie.

1. Do poľa **Zobrazovaný názov** zadajte rozpoznateľný názov pripojenia. Zobrazovaný názov a typ spojenia, ktoré popisuje toto spojenie. Odporúčame zvoliť názov, ktorý vysvetľuje účel a cieľ tohto spojenia.

1. Vyberte používateľov, ktorí môžu používať toto pripojenie. Ak neurobíte nič, predvolená hodnota bude Správcovia. Viac informácií nájdete v časti [Umožnite prispievateľom použiť pripojenie na export](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Zadajte marketingovú adresu URL svojej organizácie do poľa **Adresa servera**.

1. V sekcii **Konto správcu servera** vyberte **Prihlásiť sa** a vyberte Dynamics 365 Marketing.

1. Mapujte pole ID kontaktu v entite zákazníka na ID kontaktu Dynamics 365.

1. Stlačte možnosť **Uložiť** a dokončite pripojenie. 

## <a name="configure-an-export"></a>Nakonfigurujte export

Tento export môžete nakonfigurovať, ak máte prístup k pripojeniu tohto typu. Viac informácií nájdete na stránke [Na konfiguráciu exportu sú potrebné povolenia](export-destinations.md#set-up-a-new-export).

1. Prejdite na **Údaje** > **Exporty**.

1. Na vytvorenie nového exportu stlačte možnosť **Pridať cieľ**.

1. V poli **Pripojenie na export** vyberte pripojenie v časti Dynamics 365 Marketing. Ak nevidíte názov tejto sekcie, nemáte k dispozícii žiadne spojenia tohto typu.

1. Vyberte jeden alebo viac segmentov.

1. Vyberte položku **Uložiť**.

Uloženie exportu nespustí export okamžite.

Export prebieha s každým [plánovaným obnovením](system.md#schedule-tab). Môžete tiež [exportovať údaje na požiadanie](export-destinations.md#run-exports-on-demand). 

[!INCLUDE [footer-include](includes/footer-banner.md)]
