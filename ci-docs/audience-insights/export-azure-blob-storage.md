---
title: Export údajov služby Customer Insights do úložiska Azure Blob
description: Naučte sa, ako nakonfigurovať pripojenie k úložisku Azure Blob.
ms.date: 09/18/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 0986ee5caf5fa079994ca584fb2c4d9294ddb80b
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596196"
---
# <a name="connector-for-azure-blob-storage-preview"></a>Konektor pre úložisko Azure Blob (ukážka)

Ukladajte svoje údaje zo služby Customer Insights do úložiska Azure Blob alebo ju používajte na prenos svojich údajov do iných aplikácií.

## <a name="configure-the-connector-for-azure-blob-storage"></a>Konfigurácia konektora pre úložisko Azure Blob

1. V prehľadoch cieľových skupín prejdite na **Správca** > **Ciele exportu**.

1. Pod **Úložisko Azure Blob** vyberte **Nastaviť**.

1. Zadajte **Názov konta**, **Kľúč konta** a **Kontajner** pre váš účet úložiska Azure Blob.
    - Ďalšie informácie o tom, ako nájsť názov a kľúč účtu úložiska Azure Blob nájdete na stránke [Správa nastavení účtu úložiska na portáli Azure](/azure/storage/common/storage-account-manage).
    - Informácie o tom, ako vytvoriť kontajner, nájdete v časti [Vytvorenie kontajnera](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

1. Do poľa **Zobrazovaný názov** zadajte rozpoznateľný názov cieľa.

1. Vyberte **Ďalej**.

1. Vyberte si políčko vedľa každej entity, ktorú chcete exportovať do tohto cieľa.

1. Vyberte položku **Uložiť**.

Exportované údaje sa ukladajú do kontajnera úložiska Azure Blob, ktorý ste nakonfigurovali. Vo vašom kontajneri sa automaticky vytvoria nasledujúce cesty k priečinkom:

- Pre zdrojové entity a entity generované systémom: `%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv`
  - Príklad: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv`
- Model.json pre exportované entity bude uložené na úrovni %ExportDestinationName%
  - Príklad: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json`

## <a name="export-the-data"></a>Export údajov

Môžete [exportovať údaje na vyžiadanie](export-destinations.md#export-data-on-demand). Export sa spustí aj pri každej [plánovanej obnove](system.md#schedule-tab).


[!INCLUDE[footer-include](../includes/footer-banner.md)]