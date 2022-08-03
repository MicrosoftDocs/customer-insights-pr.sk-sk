---
title: Export údajov do Azure Blob Storage (ukážka)
description: Zistite ako nakonfigurovať pripojenie a realizovať exportovanie do úložiska Blob.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 22593ed05f403a40fe494e30f807b57658594f01
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195723"
---
# <a name="export-data-to-an-azure-blob-storage-preview"></a>Export údajov do Azure Blob Storage (ukážka)

Uložte si údaje zo služby Customer Insights do služby Blob alebo ju použite na prenos údajov do iných aplikácií.

## <a name="prerequisites"></a>Požiadavky

- An [Účet Azure Blob Storage](/azure/storage/blobs/create-data-lake-storage-account) meno a kľúč účtu. Ak chcete nájsť meno a kľúč, pozrite si časť [Spravujte nastavenia účtu úložiska na portáli Azure](/azure/storage/common/storage-account-manage).
- An [Kontajner Azure Blob Storage](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

## <a name="known-limitations"></a>Známe obmedzenia

- Pre Azure Blob Storage si vyberte medzi [Úroveň štandardného výkonu a prémiového výkonu](/azure/storage/blobs/storage-blob-performance-tiers). Ak si vyberiete úroveň prémiového výkonu, vyberte [blob prémiových blokov ako typ účtu](/azure/storage/common/storage-account-overview#types-of-storage-accounts).

## <a name="set-up-connection-to-blob-storage"></a>Nastavte pripojenie k úložisku Blob Storage

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Prejdite do časti **Správca** > **Pripojenia**.

1. Vyberte **Pridať pripojenie** a vyberte si **Azure Blob Storage**.

1. Do poľa **Zobrazovaný názov** zadajte rozpoznateľný názov pripojenia. Zobrazovaný názov a typ spojenia, ktoré popisuje toto spojenie. Odporúčame zvoliť názov, ktorý vysvetľuje účel a cieľ tohto spojenia.

1. Vyberte používateľov, ktorí môžu používať toto pripojenie. Predvolene sú to iba správcovia. Viac informácií nájdete v časti [Umožnite prispievateľom použiť pripojenie na export](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Zadajte **Názov účtu**, **Kľúč účtu** a **Kontajner** pre váš účet úložiska Blob.

1. Skontrolujte [ochrana osobných údajov a dodržiavanie predpisov](connections.md#data-privacy-and-compliance) a vyberte **Súhlasím**.

1. Stlačte možnosť **Uložiť** a dokončite pripojenie.

## <a name="configure-an-export"></a>Nakonfigurujte export

Ak chcete nakonfigurovať tento export, musíte mať [povolenie](export-destinations.md#set-up-a-new-export) pre tento typ pripojenia.

> [!IMPORTANT]
> Ak ste zapli [nastavenie mäkkého odstránenia](/azure/storage/blobs/soft-delete-blob-enable) pre účet Azure Blob Storage exporty zlyhajú. Ak chcete exportovať údaje do úložiska Blob, vypnite obnoviteľné odstránenie.

1. Prejdite na **Údaje** > **Exporty**.

1. Vyberte **Pridať export**.

1. V poli **Pripojenie na export** vyberte pripojenie v časti úložiska Azure Blob. Ak nie je k dispozícii pripojenie, kontaktujte správcu.

1. Zadajte názov exportu.

1. Zadajte názov priečinka pre úložisko objektov Blob.

1. Vyberte si políčko vedľa každej entity, ktorú chcete exportovať do tohto cieľa.

1. Vyberte **Uložiť**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

Exportované údaje sú uložené v kontajneri úložiska Blob, ktorý ste nakonfigurovali. Vo vašom kontajneri sa automaticky vytvoria nasledujúce cesty k priečinkom:

- Pre zdrojové entity a entity generované systémom:  
  *%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*  

  Príklad: Dynamics365CustomerInsights/CustomerInsights_ abcd1234-4312-11f4-93dc-24f72f43e7d5 /BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv
  
  > [!TIP]
  > Export entít, ktoré obsahujú veľké množstvo údajov, môže viesť k viacerým súborom CSV v rovnakom priečinku pre každý export. K rozdeleniu exportov dochádza z dôvodov výkonu, aby sa minimalizoval čas potrebný na dokončenie exportu.

- Model.json pre exportované entity sa nachádza na adrese *%ExportDestinationName%* úrovni.  
  
  Príklad: Dynamics365CustomerInsights/CustomerInsights_ abcd1234-4312-11f4-93dc-24f72f43e7d5 /BlobExport/model.json

[!INCLUDE [footer-include](includes/footer-banner.md)]
