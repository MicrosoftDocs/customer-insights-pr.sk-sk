---
title: Exportujte údaje Customer Insights do InMobi
description: Zistite, ako nakonfigurovať pripojenie a exportovať do InMobi.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: ef486ad6786ef01be977f3d6bda69ce8a2b081c7
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195907"
---
# <a name="export-customer-insights-data-to-inmobi-preview"></a>Export údajov Customer Insights do InMobi (ukážka)

Exportujte zoznamy segmentov alebo iné údaje z vašej inštancie Customer Insights do [InMobi](https://www.inmobi.com/).

## <a name="prerequisites"></a>Požiadavky

- An [účet InMobi](https://www.inmobi.com/) a poverenia správcu.
- An [Účet Azure Blob Storage](/azure/storage/blobs/create-data-lake-storage-account) meno a kľúč účtu. Ak chcete nájsť meno a kľúč, pozrite si časť [Spravujte nastavenia účtu úložiska na portáli Azure](/azure/storage/common/storage-account-manage).
- An [Kontajner Azure Blob Storage](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container) na export údajov InMobi.
- InMobi vytvorí priame pripojenie k vášmu úložisku Blob a nakonfiguruje automatický import vašich údajov do InMobi. Ak chcete spustiť proces, kontaktujte svojho zástupcu InMobi.

## <a name="known-limitations"></a>Známe obmedzenia

- Pre Azure Blob Storage si vyberte medzi [Úroveň štandardného výkonu a prémiového výkonu](/azure/storage/blobs/storage-blob-performance-tiers). Ak si vyberiete úroveň prémiového výkonu, vyberte [blob prémiových blokov ako typ účtu](/azure/storage/common/storage-account-overview#types-of-storage-accounts).

## <a name="set-up-connection-to-azure-blob-storage"></a>Nastavte pripojenie k službe Azure Blob Storage

[Nastavte pripojenie k úložisku objektov Azure Blob](export-azure-blob-storage.md).

## <a name="configure-an-export"></a>Nakonfigurujte export

[Nakonfigurujte export](export-azure-blob-storage.md#configure-an-export).

[!INCLUDE [footer-include](includes/footer-banner.md)]
