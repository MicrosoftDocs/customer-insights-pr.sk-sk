---
title: Export údajov služby Customer Insights Azure Data Lake Storage Gen2
description: Zistite, ako môžete nakonfigurovať pripojenie k Azure Data Lake Storage Gen2.
ms.date: 02/04/2021
ms.reviewer: sthe
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: b00c3d6178150cbc93fe800779f094809d4dc67b
ms.sourcegitcommit: 0260ed244b97c2fd0be5e9a084c4c489358e8d4f
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 02/18/2021
ms.locfileid: "5477198"
---
# <a name="connector-for-azure-data-lake-storage-gen2-preview"></a>Konektor pre Azure Data Lake Storage Gen2 (ukážka)

Uložte si údaje zo služby Customer Insights do služby Azure Data Lake Storage Gen2 alebo ju použite na prenos údajov do iných aplikácií.

## <a name="configure-the-connector-for-azure-data-lake-storage-gen2"></a>Nakonfigurujte konektor pre Azure Data Lake Storage Gen2

1. V prehľadoch cieľových skupín prejdite na **Správca** > **Ciele exportu**.

1. V časti **Azure Data Lake Storage Gen2** vyberte položku **Nastaviť**.

1. Do poľa **Zobrazovaný názov** zadajte rozpoznateľný názov cieľa.

1. Zadajte **Názov účtu**, **Kľúč účtu** a **Kontajner** pre svoje Azure Data Lake Storage Gen2.
    - Naučte sa, ako vytvoriť účet úložiska na použitie s Azure Data Lake Storage Gen2, pozri [Vytvorte si účet úložiska](https://docs.microsoft.com/azure/storage/blobs/create-data-lake-storage-account). 
    - Ak sa chcete dozvedieť viac o tom, ako nájsť názov a kľúč účtu úložiska Azure Data Lake Gen2, prečítajte si [Spravujte nastavenia účtu úložiska na portáli Azure](https://docs.microsoft.com/azure/storage/common/storage-account-manage).

1. Vyberte **Ďalej**.

1. Vyberte si políčko vedľa každej entity, ktorú chcete exportovať do tohto cieľa.

1. Vyberte položku **Uložiť**.

## <a name="export-the-data"></a>Export údajov

Môžete [exportovať údaje na vyžiadanie](export-destinations.md#export-data-on-demand). Export sa spustí aj pri každej [plánovanej obnove](system.md#schedule-tab).
