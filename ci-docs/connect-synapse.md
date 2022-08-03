---
title: Pripojte Azure Synapse zdroj údajov (ukážka)
description: Použite databázu v Azure Synapse ako zdroj údajov v Dynamics 365 Customer Insights.
ms.date: 07/26/2022
ms.reviewer: v-wendysmith
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: 54247fbcdc27f6ed8314e0755164083eb461aa64
ms.sourcegitcommit: 5807b7d8c822925b727b099713a74ce2cb7897ba
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 07/28/2022
ms.locfileid: "9206926"
---
# <a name="connect-an-azure-synapse-analytics-data-source-preview"></a>Pripojte Azure Synapse Analytics zdroj údajov (ukážka)

Azure Synapse Analytics je podniková analytická služba, ktorá urýchľuje čas potrebný na získanie prehľadov naprieč dátovými skladmi a veľkými dátovými systémami. Azure Synapse Analytics spája to najlepšie z SQL technológií používaných v podnikových dátových skladoch, technológie Spark používané pre veľké dáta, Data Explorer pre analýzu protokolov a časových radov, Pipelines pre integráciu dát a ETL/ELT a hlbokú integráciu s ďalšími službami Azure, ako napr.Power BI,Cosmos DB a AzureML.

Ďalšie informácie nájdete v časti [Azure Synapse prehľad](/azure/synapse-analytics/overview-what-is).

## <a name="prerequisites"></a>Požiadavky

> [!IMPORTANT]
> Nezabudnite nastaviť všetky **priradenia rolí**, ako je opísané.  

**In Customer Insights**:

* Máte **správca** úlohu v Customer Insights. Naučiť sa viac o [používateľské povolenia v Customer Insights](permissions.md#assign-roles-and-permissions).

**V Azure**:

- Aktívne predplatné služieb Azure.

- Ak používate nový Azure Data Lake Storage účet Gen2, *principál služby pre Customer Insights* potreby **Storage Blob Data Contributor** povolenia. Naučiť sa viac o [pripojenie k an Azure Data Lake Storage s principálom služby pre Customer Insights](connect-service-principal.md). Úložisko Data Lake Storage Gen2 **musí mať** povolenú možnosť [hierarchický názov](/azure/storage/blobs/data-lake-storage-namespace).

- V skupine prostriedkov Azure Synapse sa nachádza pracovný priestor, *objednávateľ služby* a *používateľa pre Customer Insights* je potrebné prideliť minimálne **Čitateľ** povolenia. Viac informácií nájdete v časti [Priradiť roly Azure pomocou portálu Azure Portal](/azure/role-based-access-control/role-assignments-portal).

- *Používateľ* potrebuje povolenia **Prispievateľ údajov do objektu BLOB úložiska** v účte Azure Data Lake Storage Gen2, kde sa nachádzajú údaje a sú prepojené s účtom pracovného priestoru Azure Synapse. Prečítajte si viac o [používaní portálu Azure Portal na priradenie roly Azure pre prístup k údajom blob a frontu](/azure/storage/common/storage-auth-aad-rbac-portal) a [Povolenia Prispievateľ údajov do objektu BLOB úložiska](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- *[Spravovaná identita pracovného priestoru Azure Synapse](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* potrebuje povolenia **Prispievateľ údajov do objektu BLOB úložiska** v účte Azure Data Lake Storage Gen2, kde sa údaje nachádzajú a sú prepojené na pracovisko Azure Synapse. Prečítajte si viac o [používaní portálu Azure Portal na priradenie roly Azure pre prístup k údajom blob a frontu](/azure/storage/common/storage-auth-aad-rbac-portal) a [Povolenia Prispievateľ údajov do objektu BLOB úložiska](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- Na Azure Synapse pracovný priestor, *principál služby pre Customer Insights* potreby **Správca Synapse** pridelená rola. Viac informácií nájdete v časti [Ako nastaviť riadenie prístupu pre váš pracovný priestor služby Synapse](/azure/synapse-analytics/security/how-to-set-up-access-control).

## <a name="connect-to-the-data-lake-database-in-azure-synapse-analytics"></a>Pripojte sa k databáze dátového jazera v Azure Synapse Analytics

1. Prejdite do **Údaje** > **Zdroje údajov**.

1. Vyberte položku **Pridať zdroj údajov**.

1. Vyber **Azure Synapse Analytics (Náhľad)** metóda.

   :::image type="content" source="media/data_sources_synapse.png" alt-text="Dialógové okno na pripojenie k údajom Synapse Analytics":::
  
1. Zadajte a **názov** pre zdroj údajov a voliteľné **Popis**.

1. Vyberte si [dostupné pripojenie](connections.md) do Azure Synapse Analytics alebo vytvorte nový.

1. Vyber **Databáza** z pracovného priestoru pripojeného vo vybranom Azure Synapse Analytics pripojenie a vyberte **Ďalšie**. V súčasnosti podporujeme iba typ databázy *Databáza jazera*.

1. Vyberte entity na príjem z pripojenej databázy a vyberte **Ďalšie**.

1. Voliteľne vyberte dátové entity, na ktorých chcete povoliť profilovanie údajov.

1. Vyberte **Uložiť** aby ste použili svoj výber a začali prijímať údaje z vášho novovytvoreného zdroj údajov prepojeného s tabuľkami databázy Lake v Azure Synapse Analytics. The **Zdroje dát** otvorí sa stránka s novým zdroj údajov v **Osviežujúce** postavenie.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

Načítanie údajov môže chvíľu trvať. Po úspešnom obnovení môžu byť prijaté údaje skontrolované z [**entity**](entities.md) stránku.

[!INCLUDE [footer-include](includes/footer-banner.md)]
