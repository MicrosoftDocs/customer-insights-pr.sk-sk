---
title: Prijímať údaje z Azure Synapse Analytics
description: Použite databázu v Azure Synapse ako zdroj údajov v Dynamics 365 Customer Insights.
ms.date: 02/24/2022
ms.reviewer: v-wendysmith
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: 163bef897880f0497bf00e90fd095621a2d14378
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 02/25/2022
ms.locfileid: "8356055"
---
# <a name="connect-an-azure-synapse-data-source-preview"></a>Pripojte Azure Synapse zdroj údajov (ukážka)

Azure Synapse Analytics je podniková analytická služba, ktorá urýchľuje čas potrebný na získanie prehľadov naprieč dátovými skladmi a veľkými dátovými systémami. Azure Synapse Analytics spája to najlepšie z SQL technológií používaných v podnikových dátových skladoch, technológie Spark používané pre veľké dáta, Data Explorer pre analýzu protokolov a časových radov, Pipelines pre dátovú integráciu a ETL/ELT a hlbokú integráciu s ďalšími službami Azure, ako napr.Power BI,Cosmos DB a AzureML.

Viac informácií nájdete v časti [Azure Synapse prehľad](/azure/synapse-analytics/overview-what-is).

## <a name="prerequisites"></a>Požiadavky

Nasledujúce predpoklady musia byť splnené, aby bolo možné nakonfigurovať pripojenie od Customer Insights k Azure Synapse.

> [!IMPORTANT]
> Nezabudnite nastaviť všetky **priradenia rolí**, ako je opísané.  

## <a name="prerequisites-in-customer-insights"></a>Požiadavky v Customer Insights

* Máte **správca** úlohu v Customer Insights. Prečítajte si viac o [povoleniach používateľov v prehľadoch cieľovej skupiny](permissions.md#assign-roles-and-permissions).

V Azure: 

- Aktívne predplatné služieb Azure.

- Ak používate nový účet Azure Data Lake Storage Gen2, *vedúci služby pre prehľady cieľovej skupiny* potrebuje povolenia **Prispievateľ údajov do objektu BLOB úložiska**. Naučiť sa viac o [pripojenie k Azure Data Lake Storage s princípom služby pre štatistiky publika](connect-service-principal.md). Úložisko Data Lake Storage Gen2 **musí mať** povolenú možnosť [hierarchický názov](/azure/storage/blobs/data-lake-storage-namespace).

- V skupine zdrojov Azure Synapse sa nachádza pracovný priestor, *objekt služby* a *používateľ pre prehľady cieľovej skupiny* musia mať priradené minimálne povolenie **Čitateľ**. Viac informácií nájdete v časti [Priradiť roly Azure pomocou portálu Azure Portal](/azure/role-based-access-control/role-assignments-portal).

- *Používateľ* potrebuje povolenia **Prispievateľ údajov do objektu BLOB úložiska** v účte Azure Data Lake Storage Gen2, kde sa nachádzajú údaje a sú prepojené s účtom pracovného priestoru Azure Synapse. Prečítajte si viac o [používaní portálu Azure Portal na priradenie roly Azure pre prístup k údajom blob a frontu](/azure/storage/common/storage-auth-aad-rbac-portal) a [Povolenia Prispievateľ údajov do objektu BLOB úložiska](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- *[Spravovaná identita pracovného priestoru Azure Synapse](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* potrebuje povolenia **Prispievateľ údajov do objektu BLOB úložiska** v účte Azure Data Lake Storage Gen2, kde sa údaje nachádzajú a sú prepojené na pracovisko Azure Synapse. Prečítajte si viac o [používaní portálu Azure Portal na priradenie roly Azure pre prístup k údajom blob a frontu](/azure/storage/common/storage-auth-aad-rbac-portal) a [Povolenia Prispievateľ údajov do objektu BLOB úložiska](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- V pracovnom priestore Azure Synapse musí mať *objekt služby pre prehľady cieľových skupín* priradenú rolu **Správca služby Synapse**. Viac informácií nájdete v časti [Ako nastaviť riadenie prístupu pre váš pracovný priestor služby Synapse](/azure/synapse-analytics/security/how-to-set-up-access-control).

## <a name="connect-to-data-lake-databases-in-azure-synapse-analytics"></a>Pripojte sa k databázam dátového jazera v Azure Synapse Analytics

1. Prejdite do **Údaje** > **Zdroje údajov**.

1. Vyberte položku **Pridať zdroj údajov**.

1. Vyber **Azure Synapse Analytics (Náhľad)** metóda.

1. Zadajte **Názov** pre zdroj údajov a vyberte **Ďalej** na vytvorenie zdroja údajov. 

1. Vyberte si [dostupné pripojenie](connections.md) do Azure Synapse Analytics alebo vytvorte nový.

1. Vyber **Databáza jazera** z pracovného priestoru pripojeného vo vybranom Azure Synapse Analytics pripojenie a vyberte **Ďalšie**.

1. Vyberte entity na príjem z pripojenej databázy. 

1. Voliteľne vyberte dátové entity, na ktorých chcete povoliť profilovanie údajov. 

1. Vyberte **Uložiť** aby ste použili svoj výber a začali prijímať údaje z vášho novovytvoreného zdroj údajov prepojeného s tabuľkami databázy Lake v Azure Synapse Analytics.
