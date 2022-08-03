---
title: Exportovať údaje do Azure Data Lake Storage Gen2 (ukážka)
description: Zistite, ako môžete nakonfigurovať pripojenie k Azure Data Lake Storage Gen2.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 55a61e4d9166df7809a64aeb1168a730402aaed6
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196459"
---
# <a name="export-data-to-azure-data-lake-storage-gen2-preview"></a>Exportovať údaje do Azure Data Lake Storage Gen2 (ukážka)

Ukladajte svoje údaje zo služby Customer Insights do účtu Azure Data Lake Storage Gen2 alebo ho použite na prenesenie údajov do iných aplikácií.

## <a name="prerequisites"></a>Požiadavky

- A [účet úložiska na použitie s Azure Data Lake Gen2](/azure/storage/blobs/create-data-lake-storage-account). Ak chcete nájsť názov účtu úložiska a kľúč, pozrite si časť [Spravujte nastavenia účtu úložiska na portáli Azure](/azure/storage/common/storage-account-manage).
- An [Kontajner Azure Blob Storage](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

## <a name="known-limitations"></a>Známe obmedzenia

- Pre Azure Data Lake Storage Gen2, vyberte si medzi [Úroveň štandardného výkonu a prémiového výkonu](/azure/storage/blobs/create-data-lake-storage-account). Ak si vyberiete úroveň prémiového výkonu, vyberte [blob prémiových blokov ako typ účtu](/azure/storage/common/storage-account-overview#types-of-storage-accounts).

## <a name="set-up-connection-to-azure-data-lake-storage-gen2"></a>Nastaviť pripojenie k Azure Data Lake Storage Gen2

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Prejdite do časti **Správca** > **Pripojenia**.

1. Vyberte **Pridať pripojenie** a vyberte si **Azure Data Lake Gen 2**.

1. Do poľa **Zobrazovaný názov** zadajte rozpoznateľný názov pripojenia. Zobrazovaný názov a typ spojenia, ktoré popisuje toto spojenie. Odporúčame zvoliť názov, ktorý vysvetľuje účel a cieľ tohto spojenia.

1. Vyberte používateľov, ktorí môžu používať toto pripojenie. Predvolene sú to iba správcovia. Viac informácií nájdete v časti [Umožnite prispievateľom použiť pripojenie na export](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Zadajte **Názov účtu**, **Kľúč účtu** a **Kontajner** pre svoje Azure Data Lake Storage Gen2.

1. Skontrolujte [ochrana osobných údajov a dodržiavanie predpisov](connections.md#data-privacy-and-compliance) a vyberte **Súhlasím**.

1. Stlačte možnosť **Uložiť** a dokončite pripojenie.

## <a name="configure-an-export"></a>Nakonfigurujte export

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Prejdite na **Údaje** > **Exporty**.

1. Vyberte **Pridať export**.

1. V **Pripojenie na export** vyberte pripojenie zo sekcie Azure Data Lake. Ak nie je k dispozícii pripojenie, kontaktujte správcu.

1. Zadajte názov exportu.

1. Zadajte názov priečinka pre Azure Data Lake Storage Úložisko Gen2.

1. Vyberte si políčko vedľa každej entity, ktorú chcete exportovať do tohto cieľa.

1. Vyberte **Uložiť**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

Exportované údaje sú uložené v kontajneri úložiska Azure Data Lake Gen 2, ktorý ste nakonfigurovali.

> [!TIP]
> Export entít, ktoré obsahujú veľké množstvo údajov, môže viesť k viacerým súborom CSV v rovnakom priečinku pre každý export. K rozdeleniu exportov dochádza z dôvodov výkonu, aby sa minimalizoval čas potrebný na dokončenie exportu.

[!INCLUDE [footer-include](includes/footer-banner.md)]
