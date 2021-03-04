---
title: Export údajov služby Customer Insights do ukladacieho priestoru BLOB platformy Azure
description: Naučte sa, ako nakonfigurovať pripojenie k úložisku Azure Blob.
ms.date: 09/18/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: ecacf20365e78ced8859dfa54b1b16cb923c00eb
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269211"
---
# <a name="connector-for-azure-blob-storage-preview"></a>Konektor pre úložisko Azure Blob (ukážka)

Ukladajte svoje údaje zo služby Customer Insights do ukladacieho priestoru BLOB platformy Azure alebo ju používajte na prenos svojich údajov do iných aplikácií.

## <a name="configure-the-connector-for-azure-blob-storage"></a>Konfigurácia konektora pre úložisko Azure Blob

1. V prehľadoch cieľových skupín prejdite na **Správca** > **Ciele exportu**.

1. Pod **Úložisko Azure Blob** vyberte **Nastaviť**.

1. Zadajte **Názov konta**, **Kľúč konta** a **Kontajner** pre váš účet úložiska Azure Blob.
    - Ďalšie informácie o tom, ako nájsť názov a kľúč účtu úložiska objektov Blob platformy Azure nájdete na stránke [Správa nastavení účtu úložiska na portáli Azure](https://docs.microsoft.com/azure/storage/common/storage-account-manage).
    - Informácie o tom, ako vytvoriť kontajner, nájdete v časti [Vytvorenie kontajnera](https://docs.microsoft.com/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

1. Do poľa **Zobrazovaný názov** zadajte rozpoznateľný názov cieľa.

1. Vyberte **Ďalej**.

1. Vyberte si políčko vedľa každej entity, ktorú chcete exportovať do tohto cieľa.

1. Vyberte položku **Uložiť**.

Exportované údaje sa ukladajú do kontajnera úložiska Azure Blob, ktorý ste nakonfigurovali. Vo vašom kontajneri sa automaticky vytvoria nasledujúce cesty k priečinkom:

- Pre zdrojové entity a entity generované systémom: `%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv`
  - Príklad: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv`
- Model.json pre exportované entity bude sídliť na úrovni %ExportDestinationName%
  - Príklad: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json`

## <a name="export-the-data"></a>Export údajov

Môžete [exportovať údaje na vyžiadanie](export-destinations.md#export-data-on-demand). Export sa spustí aj pri každej [plánovanej obnove](system.md#schedule-tab).


[!INCLUDE[footer-include](../includes/footer-banner.md)]