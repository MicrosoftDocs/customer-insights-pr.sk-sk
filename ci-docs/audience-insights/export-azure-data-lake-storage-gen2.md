---
title: Export údajov služby Customer Insights Azure Data Lake Storage Gen2
description: Zistite, ako môžete nakonfigurovať pripojenie k Azure Data Lake Storage Gen2.
ms.date: 10/06/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 934c396559d4c4be8e640917d2265805753eb62d
ms.sourcegitcommit: 693458e13e4b4d94b6205093559912f6a4dc4a1c
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 10/06/2021
ms.locfileid: "7605922"
---
# <a name="export-segment-list-and-other-data-to-azure-data-lake-storage-gen2-preview"></a>Export zoznamu segmentov a ďalších údajov do Azure Data Lake Storage Gen2 (verzia Preview)

Ukladajte svoje údaje zo služby Customer Insights do účtu Azure Data Lake Storage Gen2 alebo ho použite na prenesenie údajov do iných aplikácií.

## <a name="known-limitations"></a>Známe obmedzenia

1. Pre Azure Data Lake Storage Gen2 si môžete zvoliť medzi [úrovňou štandardného a prémiového výkonu](/azure/storage/blobs/create-data-lake-storage-account), keď vytvárate účet úložiska pre svoje dátové jazero. Ak si vyberiete úroveň výkonu Premium, vyberte blob prémiových blokov ako typ účtu. 


## <a name="set-up-the-connection-to-azure-data-lake-storage-gen2"></a>Nastavenie pripojenia k Azure Data Lake Storage Gen2 


1. Prejdite do časti **Správca** > **Pripojenia**.

1. Stlačte možnosť **Pridať pripojenie** a stlačením možnosti **Azure Data Lake Gen 2** nakonfigurujte pripojenie.

1. Do poľa **Zobrazovaný názov** zadajte rozpoznateľný názov pripojenia. Zobrazovaný názov a typ spojenia, ktoré popisuje toto spojenie. Odporúčame zvoliť názov, ktorý vysvetľuje účel a cieľ tohto spojenia.

1. Vyberte používateľov, ktorí môžu používať toto pripojenie. Ak neurobíte nič, predvolená hodnota bude Správcovia. Viac informácií nájdete v časti [Umožnite prispievateľom použiť pripojenie na export](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Zadajte **Názov účtu**, **Kľúč účtu** a **Kontajner** pre svoje Azure Data Lake Storage Gen2.
    - Naučte sa, ako vytvoriť účet úložiska na použitie s Azure Data Lake Storage Gen2, pozri [Vytvorte si účet úložiska](/azure/storage/blobs/create-data-lake-storage-account). 
    - Ak sa chcete dozvedieť viac o názve a kľúči účtu úložiska Azure Data Lake Gen2, prečítajte si časť [Správa nastavení účtu v portáli Azure](/azure/storage/common/storage-account-manage).

1. Stlačte možnosť **Uložiť** a dokončite pripojenie. 

## <a name="configure-an-export"></a>Nakonfigurujte export

Tento export môžete nakonfigurovať, ak máte prístup k pripojeniu tohto typu. Viac informácií nájdete na stránke [Na konfiguráciu exportu sú potrebné povolenia](export-destinations.md#set-up-a-new-export).

1. Prejdite na **Údaje** > **Exporty**.

1. Na vytvorenie nového exportu stlačte možnosť **Pridať export**.

1. V poli **Pripojenie na export** vyberte pripojenie v časti **Azure Data Lake**. Ak nevidíte názov tejto sekcie, nemáte k dispozícii žiadne spojenia tohto typu.

1. Vyberte si políčko vedľa každej entity, ktorú chcete exportovať do tohto cieľa.

1. Vyberte položku **Uložiť**.

Uloženie exportu nespustí export okamžite.

Export prebieha s každým [plánovaným obnovením](system.md#schedule-tab). Môžete tiež [exportovať údaje na požiadanie](export-destinations.md#run-exports-on-demand). 

Exportované údaje sú uložené v kontajneri úložiska Azure Data Lake Gen 2, ktorý ste nakonfigurovali. 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
