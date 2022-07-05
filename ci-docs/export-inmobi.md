---
title: Exportujte údaje Customer Insights do InMobi
description: Zistite, ako nakonfigurovať pripojenie a exportovať do InMobi.
ms.date: 06/27/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 8261c8adfe231792e70fc85432237cf73d5cd5a7
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 06/29/2022
ms.locfileid: "9059619"
---
# <a name="export-segment-list-and-other-data-to-inmobi-preview"></a>Export zoznamu segmentov a iných údajov do InMobi (ukážka)

Exportujte zoznamy segmentov alebo iné údaje z vašej inštancie Customer Insights do [InMobi](https://www.inmobi.com/).

## <a name="prerequisites"></a>Požiadavky

1. Máte [účet InMobi](https://www.inmobi.com/) a poverenia správcu.
1. Máte názov účtu úložiska Azure Blob a zodpovedajúci kľúč účtu. Viac informácií nájdete v časti [Spravujte nastavenia účtu úložiska na portáli Azure](/azure/storage/common/storage-account-manage). V účte úložiska je kontajner na export údajov inMobi. Viac informácií nájdete v časti [Vytvorte kontajner](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).
1. InMobi vytvorí priame pripojenie k vášmu úložisku Blob a nakonfiguruje automatický import vašich údajov do InMobi. Ak chcete spustiť proces, kontaktujte svojho zástupcu InMobi.

## <a name="known-limitations"></a>Známe obmedzenia

1. V prípade Azure Blob Storage si môžete vybrať medzi [Úroveň štandardného výkonu a prémiového výkonu](/azure/storage/blobs/storage-blob-performance-tiers). Ak si vyberiete úroveň prémiového výkonu, vyberte [blob prémiových blokov ako typ účtu](/azure/storage/common/storage-account-overview#types-of-storage-accounts).

## <a name="set-up-the-connection-to-azure-blob-storage-and-configure-an-export"></a>Nastavte pripojenie k službe Azure Blob Storage a nakonfigurujte export

1. Postupujte podľa pokynov na [nastavte pripojenie k vášmu ukladaciemu priestoru Azure Blob Storage](export-azure-blob-storage.md).
2. Postupujte podľa pokynov na [nakonfigurovať export](export-azure-blob-storage.md#configure-an-export).

[!INCLUDE [footer-include](includes/footer-banner.md)]
