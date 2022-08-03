---
title: Export údajov do Salesforce Marketing Cloud (ukážka)
description: Zistite, ako nakonfigurovať pripojenie a exportovať do služby Salesforce Marketing Cloud.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 58e76e51c18c25177f9b4551b70b25b41248b142
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 07/27/2022
ms.locfileid: "9197057"
---
# <a name="export-data-to-salesforce-marketing-cloud-preview"></a>Export údajov do Salesforce Marketing Cloud (ukážka)

Použite svoje údaje o zákazníkoch v službe Salesforce Marketing Cloud tým, že ich exportujete prostredníctvom umiestnenia Secure File Transfer Protocol (SFTP).

## <a name="prerequisites"></a>Požiadavky

- An [Hostiteľ SFTP pre Salesforce Marketing Cloud](https://help.salesforce.com/articleView?id=sf.mc_es_configure_enhanced_ftp.htm&type=5) a zodpovedajúce poverenia správcu.

## <a name="set-up-connection-to-salesforce-marketing-cloud"></a>Nastavte pripojenie k Salesforce Marketing Cloud

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Prejdite do časti **Správca** > **Pripojenia**.

1. Vyberte **Pridať pripojenie** a vyberte si **Salesforce Marketing Cloud**.

1. Do poľa **Zobrazovaný názov** zadajte rozpoznateľný názov pripojenia. Zobrazovaný názov a typ spojenia, ktoré popisuje toto spojenie. Odporúčame zvoliť názov, ktorý vysvetľuje účel a cieľ tohto spojenia.

1. Vyberte používateľov, ktorí môžu používať toto pripojenie. Predvolene sú to iba správcovia. Viac informácií nájdete v časti [Umožnite prispievateľom použiť pripojenie na export](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Uveďte **Používateľské meno**, **Heslo**, **Meno hostiteľa** a **Priečinok na export** pre váš účet SFTP.

1. Na otestovanie pripojenia vyberte **Overiť**.

1. Skontrolujte [ochrana osobných údajov a dodržiavanie predpisov](connections.md#data-privacy-and-compliance) a vyberte **Súhlasím**.

1. Stlačte možnosť **Uložiť** a dokončite pripojenie.

## <a name="configure-an-export"></a>Nakonfigurujte export

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Prejdite na **Údaje** > **Exporty**.

1. Vyberte **Pridať export**.

1. V poli **Pripojenie na export** vyberte pripojenie v časti SFTP. Ak nie je k dispozícii pripojenie, kontaktujte správcu.

1. Zadajte názov exportu.

1. Vyberte, či chcete exportovať svoje údaje **Zbalené** alebo **Rozbalené** a **oddeľovač polí** pre exportované súbory.

1. Vyberte entity, napríklad segmenty, ktoré chcete exportovať.

   > [!NOTE]
   > Každá vybraná entita bude pri exporte rozdelená do maximálne piatich výstupných súborov.

1. Vyberte **Uložiť**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

## <a name="import-customer-insights-data-from-sftp-location-to-salesforce-marketing-cloud"></a>Import údajov z Customer Insights z umiestnenia SFTP do služby Salesforce Marketing Cloud

1. Vytvárajte [dátové rozšírenia v službe Salesforce Marketing Cloud](https://help.salesforce.com/articleView?id=sf.mc_es_create_data_extension.htm&type=5) na import dátového súboru Customer Insights z umiestnenia SFTP.

2. [Importujte údaje z umiestnenia SFTP](https://help.salesforce.com/articleView?id=sf.mc_es_import_data_extension_classic.htm&type=5) do dátového rozšírenia Salesforce Marketing Cloud.

3. Nastavte automatizáciu na import údajov do dátových rozšírení. Zistite viac o [automatizácii ukladania súborov a plánovaných automatizáciách](https://help.salesforce.com/articleView?id=sf.mc_as_triggered_automations.htm&type=5).

   Definujte [automatizáciu ukladania súborov](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_triggered_automation.htm&type=5) alebo [plánovanú automatizáciu](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_scheduled_automation.htm&type=5).

Tu je príklad [automatizácie pomocou SFTP](https://help.salesforce.com/articleView?id=sf.mc_as_ftp_and_triggered_automation_scenario.htm&type=5).

[!INCLUDE [footer-include](includes/footer-banner.md)]
