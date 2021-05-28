---
title: Export údajov služby Customer Insights do úložiska Azure Blob Storage
description: Zistite ako nakonfigurovať pripojenie a realizovať exportovanie do úložiska Blob.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 3c19dc6d4956a33a5bd3cea706f8a154198d487f
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976200"
---
# <a name="export-segment-list-and-other-data-to-azure-blob-storage-preview"></a>Exportujte zoznam segmentov a ďalšie údaje do Azure Blob Storage (ukážka)

Uložte si údaje zo služby Customer Insights do služby Blob alebo ju použite na prenos údajov do iných aplikácií.

## <a name="set-up-the-connection-to-blob-storage"></a>Príprava pripojenia do úložiska Blob

1. Prejdite do časti **Správca** > **Pripojenia**.

1. Stlačte možnosť **Pridať pripojenie** a stlačením možnosti **úložiska Azure Blob** nakonfigurujte pripojenie.

1. Do poľa **Zobrazovaný názov** zadajte rozpoznateľný názov pripojenia. Zobrazovaný názov a typ spojenia, ktoré popisuje toto spojenie. Odporúčame zvoliť názov, ktorý vysvetľuje účel a cieľ tohto spojenia.

1. Vyberte používateľov, ktorí môžu používať toto pripojenie. Ak neurobíte nič, predvolená hodnota bude Správcovia. Viac informácií nájdete v časti [Umožnite prispievateľom použiť pripojenie na export](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Zadajte **Názov účtu**, **Kľúč účtu** a **Kontajner** pre váš účet úložiska Blob.
    - Ak sa chcete dozvedieť viac o názve a kľúči účtu úložiska Blob, prečítajte si časť [Správa nastavení účtu v portáli Azure](/azure/storage/common/storage-account-manage).
    - Informácie o tom, ako vytvoriť kontajner, nájdete v časti [Vytvorenie kontajnera](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

1. Stlačte možnosť **Uložiť** a dokončite pripojenie. 

## <a name="configure-an-export"></a>Nakonfigurujte export

Tento export môžete nakonfigurovať, ak máte prístup k pripojeniu tohto typu. Viac informácií nájdete na stránke [Na konfiguráciu exportu sú potrebné povolenia](export-destinations.md#set-up-a-new-export).

1. Prejdite na **Údaje** > **Exporty**.

1. Na vytvorenie nového exportu stlačte možnosť **Pridať cieľ**.

1. V poli **Pripojenie na export** vyberte pripojenie v časti úložiska Azure Blob. Ak nevidíte názov tejto sekcie, nemáte k dispozícii žiadne spojenia tohto typu.

1. Vyberte si políčko vedľa každej entity, ktorú chcete exportovať do tohto cieľa.

1. Vyberte položku **Uložiť**.

Uloženie exportu nespustí export okamžite.

Export prebieha s každým [plánovaným obnovením](system.md#schedule-tab).     
Môžete tiež [exportovať údaje na požiadanie](export-destinations.md#run-exports-on-demand). 

Exportované údaje sú uložené v kontajneri úložiska Blob, ktorý ste nakonfigurovali. Vo vašom kontajneri sa automaticky vytvoria nasledujúce cesty k priečinkom:

- Pre zdrojové entity a entity generované systémom: `%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv`
  - Príklad: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv`
- Model.json pre exportované entity bude na úrovni %ExportDestinationName%
  - Príklad: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json`

[!INCLUDE[footer-include](../includes/footer-banner.md)]
