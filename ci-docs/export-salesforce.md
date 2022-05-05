---
title: Export údajov z Customer Insights do služby Salesforce Marketing Cloud
description: Zistite, ako nakonfigurovať pripojenie a exportovať do služby Salesforce Marketing Cloud.
ms.date: 07/23/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: aaf5c2607099bbfccf7ed75330267da8c3c5fe1b
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 04/27/2022
ms.locfileid: "8643878"
---
# <a name="export-segments-and-other-data-to-salesforce-marketing-cloud-preview"></a>Export segmentov a ďalších údajov do služby Salesforce Marketing Cloud (verzia Preview)

Použite svoje údaje o zákazníkoch v službe Salesforce Marketing Cloud tým, že ich exportujete prostredníctvom umiestnenia Secure File Transfer Protocol (SFTP).

## <a name="prerequisites-for-connection"></a>Predpoklad na pripojenie

- Dostupnosť hostiteľa SFTP a zodpovedajúcich poverení správcu. [Ako nastaviť umiestnenia SFTP pre Salesforce Marketing Cloud](https://help.salesforce.com/articleView?id=sf.mc_es_configure_enhanced_ftp.htm&type=5) 

## <a name="set-up-the-connection-to-salesforce-marketing-cloud"></a>Nastavenie pripojenia k službe Salesforce Marketing Cloud

1. Prejdite do časti **Správca** > **Pripojenia**.

1. Vyberte možnosť **Pridať pripojenie** a výberom položky **Salesforce Marketing Cloud** nakonfigurujte pripojenie.

1. Do poľa **Zobrazovaný názov** zadajte rozpoznateľný názov pripojenia. Zobrazovaný názov a typ spojenia, ktoré popisuje toto spojenie. Odporúčame zvoliť názov, ktorý vysvetľuje účel a cieľ tohto spojenia.

1. Vyberte používateľov, ktorí môžu používať toto pripojenie. Ak neurobíte nič, predvolená hodnota bude Správcovia. Viac informácií nájdete v časti [Umožnite prispievateľom použiť pripojenie na export](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Uveďte **Používateľské meno**, **Heslo**, **Meno hostiteľa** a **Priečinok na export** pre váš účet SFTP.

1. Na otestovanie pripojenia vyberte **Overiť**.

1. Vyberte **Súhlasím** na potvrdenie **Ochrany osobných údajov a dodržiavanie súladu s nariadeniami**.

1. Stlačte možnosť **Uložiť** a dokončite pripojenie.

## <a name="configure-an-export"></a>Nakonfigurujte export

Tento export môžete nakonfigurovať, ak máte prístup k pripojeniu tohto typu. Viac informácií nájdete na stránke [Na konfiguráciu exportu sú potrebné povolenia](export-destinations.md#set-up-a-new-export).

1. Prejdite na **Údaje** > **Exporty**.

1. Na vytvorenie nového exportu stlačte možnosť **Pridať cieľ**.

1. V poli **Pripojenie na export** vyberte pripojenie v časti SFTP. Ak nevidíte názov tejto sekcie, nemáte k dispozícii žiadne spojenia tohto typu.

1. Vyberte, či chcete exportovať svoje údaje **Zbalené** alebo **Rozbalené** a **oddeľovač polí** pre exportované súbory.

1. Vyberte entity, napríklad segmenty, ktoré chcete exportovať.

   > [!NOTE]
   > Každá vybraná entita sa pri exportovaní rozdelí až na päť výstupných súborov. 

1. Vyberte položku **Uložiť**.

Uloženie exportu nespustí export okamžite.

Export prebieha s každým [plánovaným obnovením](system.md#schedule-tab). Môžete tiež [exportovať údaje na požiadanie](export-destinations.md#run-exports-on-demand). 

## <a name="import-customer-insights-data-from-sftp-location-to-salesforce-marketing-cloud"></a>Import údajov z Customer Insights z umiestnenia SFTP do služby Salesforce Marketing Cloud

1. Vytvárajte [dátové rozšírenia v službe Salesforce Marketing Cloud](https://help.salesforce.com/articleView?id=sf.mc_es_create_data_extension.htm&type=5) na import dátového súboru Customer Insights z umiestnenia SFTP.

2. [Importujte údaje z umiestnenia SFTP](https://help.salesforce.com/articleView?id=sf.mc_es_import_data_extension_classic.htm&type=5) do dátového rozšírenia Salesforce Marketing Cloud. 

3. Nastavte automatizáciu na import údajov do dátových rozšírení. Zistite viac o [automatizácii ukladania súborov a plánovaných automatizáciách](https://help.salesforce.com/articleView?id=sf.mc_as_triggered_automations.htm&type=5).

   Definujte [automatizáciu ukladania súborov](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_triggered_automation.htm&type=5) alebo [plánovanú automatizáciu](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_scheduled_automation.htm&type=5). 

Tu je príklad [automatizácie pomocou SFTP](https://help.salesforce.com/articleView?id=sf.mc_as_ftp_and_triggered_automation_scenario.htm&type=5).

## <a name="data-privacy-and-compliance"></a>Ochrana osobných údajov a dodržiavanie súladu s nariadeniami

Keď povolíte prenos údajov spoločnosti SFTP v službe Dynamics 365 Customer Insights, povoľujete tým prenos údajov mimo hranice súladu so službou Dynamics 365 Customer Insights vrátane potenciálne citlivých údajov, ako sú napríklad osobné údaje. Spoločnosť Microsoft prenesie tieto údaje na váš pokyn, ale vy ste zodpovední za zabezpečenie toho, aby cieľ exportu plnil všetky prípadné povinnosti týkajúce sa ochrany vašich osobných údajov alebo zabezpečenia. Ďalšie informácie nájdete vo [vyhlásení o ochrane súkromia spoločnosti Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Váš správca služby Dynamics 365 Customer Insights môže túto funkciu kedykoľvek prestať používať odstránením tohto cieľového umiestnenia exportu.

[!INCLUDE [footer-include](includes/footer-banner.md)]
