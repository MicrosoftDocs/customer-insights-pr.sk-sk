---
title: Exportovať údaje do Azure Synapse Analytics (Náhľad)
description: Zistite, ako nakonfigurovať pripojenie k Azure Synapse Analytics.
ms.date: 06/29/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 60bacb313e0426564310f3c1339bf3b732e17489
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 06/29/2022
ms.locfileid: "9082878"
---
# <a name="export-data-to-azure-synapse-analytics-preview"></a>Exportovať údaje do Azure Synapse Analytics (Náhľad)

Azure Synapse je analytická služba, ktorá urýchľuje čas na získanie prehľadu o dátových skladoch a systémoch veľkých údajov. Údaje služby Customer Insights môžete prijímať a používať v aplikácii [Azure Synapse](/azure/synapse-analytics/overview-what-is).

## <a name="prerequisites"></a>Predpoklady

Nasledujúce predpoklady musia byť splnené, aby bolo možné nakonfigurovať pripojenie od Customer Insights k Azure Synapse.

> [!NOTE]
> Nezabudnite nastaviť všetky **priradenia rolí**, ako je opísané.  

## <a name="prerequisites-in-customer-insights"></a>Požiadavky v Customer Insights

* Váš Azure Active Directory (AD) používateľský účet má **správca** úlohu v Customer Insights. Naučiť sa viac o [nastavenie používateľských oprávnení](permissions.md#assign-roles-and-permissions).

V Azure: 

- Aktívne predplatné služieb Azure.

- Ak používate nový Azure Data Lake Storage účet Gen2, *principál služby pre Customer Insights* potreby **Storage Blob Data Contributor** povolenia. Viac sa dozviete na [pripojenie k an Azure Data Lake Storage Účet Gen2 s principálom služby Azure pre Customer Insights](connect-service-principal.md). Úložisko Data Lake Storage Gen2 **musí mať** povolenú možnosť [hierarchický názov](/azure/storage/blobs/data-lake-storage-namespace).

- V skupine prostriedkov, kde je Azure Synapse sa nachádza pracovný priestor, *objednávateľ služby* a *Azure AD používateľ s oprávneniami správcu v Customer Insights* je potrebné prideliť minimálne **Čitateľ** povolenia. Viac informácií nájdete v časti [Priradiť roly Azure pomocou portálu Azure Portal](/azure/role-based-access-control/role-assignments-portal).

- The *Azure AD používateľ s oprávneniami správcu v Customer Insights* potreby **Storage Blob Data Contributor** povolenia na Azure Data Lake Storage Účet Gen2, v ktorom sú údaje umiestnené a prepojené s Azure Synapse pracovnom priestore. Prečítajte si viac o [používaní portálu Azure Portal na priradenie roly Azure pre prístup k údajom blob a frontu](/azure/storage/common/storage-auth-aad-rbac-portal) a [Povolenia Prispievateľ údajov do objektu BLOB úložiska](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- *[Spravovaná identita pracovného priestoru Azure Synapse](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* potrebuje povolenia **Prispievateľ údajov do objektu BLOB úložiska** v účte Azure Data Lake Storage Gen2, kde sa údaje nachádzajú a sú prepojené na pracovisko Azure Synapse. Prečítajte si viac o [používaní portálu Azure Portal na priradenie roly Azure pre prístup k údajom blob a frontu](/azure/storage/common/storage-auth-aad-rbac-portal) a [Povolenia Prispievateľ údajov do objektu BLOB úložiska](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- Na Azure Synapse pracovný priestor, *principál služby pre Customer Insights* potreby **Správca Synapse** pridelená rola. Viac informácií nájdete v časti [Ako nastaviť riadenie prístupu pre váš pracovný priestor služby Synapse](/azure/synapse-analytics/security/how-to-set-up-access-control).

## <a name="set-up-the-connection-and-export-to-azure-synapse"></a>Príprava pripojenia a exportovania do Azure Synapse

### <a name="configure-a-connection"></a>Konfigurácia a pripojenie

Na vytvorenie pripojenia je potrebný principál služby a používateľský účet v Customer Insights **Čitateľ** povolenia na *skupina zdrojov* kde sa nachádza pracovný priestor Synapse Analytics. Okrem toho potrebuje principál služby a používateľ v pracovnom priestore Synapse Analytics **Správca Synapse** povolenia. 

1. Prejdite do časti **Správca** > **Pripojenia**.

1. Vyberte **Pridať pripojenie** a vyberte si **Azure Synapse Analytics** alebo vyberte **Nastaviť** na **Azure Synapse Analytics** dlaždice na konfiguráciu pripojenia.

1. Do poľa Zobrazovaný názov zadajte rozpoznateľný názov pripojenia. Zobrazovaný názov a typ spojenia, ktoré popisuje toto spojenie. Odporúčame zvoliť názov, ktorý vysvetľuje účel a cieľ tohto spojenia.

1. Vyberte používateľov, ktorí môžu používať toto pripojenie. Ak neurobíte nič, predvolená hodnota bude Správcovia. Viac informácií nájdete v časti [Umožnite prispievateľom použiť pripojenie na export](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Vyberte alebo vyhľadajte predplatné, v ktorom chcete použiť údaje Customer Insights. Hneď ako vyberiete predplatné, môžete tiež zvoliť **Pracovný priestor**, **Účet úložiska** a **Kontajner**.

1. Stlačením možnosti **Uložiť** uložíte pripojenie.

### <a name="configure-an-export"></a>Nakonfigurujte export

Tento export môžete nakonfigurovať, ak máte prístup k pripojeniu tohto typu. Na konfiguráciu exportu so zdieľaným pripojením potrebujete min **Prispievateľ** povolenia v Customer Insights. Viac informácií nájdete na stránke [Na konfiguráciu exportu sú potrebné povolenia](export-destinations.md#set-up-a-new-export).

1. Prejdite na **Údaje** > **Exporty**.

1. Na vytvorenie nového exportu stlačte možnosť **Pridať export**.

1. V **Pripojenie na export** vyberte spojenie z poľa **Azure Synapse Analytics** oddiele. Ak nevidíte názov tejto sekcie, nemáte k dispozícii žiadne [spojenia](connections.md) tohto typu.

1. Poskytnite rozoznateľný **Zobrazovaný názov** pre váš export a **Názov databázy**. Exportom sa vytvorí nový [Azure Synapse databáza jazier](/azure/synapse-analytics/database-designer/concepts-lake-database) v pracovnom priestore definovanom v pripojení.

1. Vyberte entity, do ktorých chcete exportovať Azure Synapse Analytics.
   > [!NOTE]
   > Zdroje údajov založené na [priečinku Common Data Model](connect-common-data-model.md) nie sú podporované.

1. Vyberte položku **Uložiť**.

Uloženie exportu nespustí export okamžite.

Export prebieha s každým [plánovaným obnovením](system.md#schedule-tab). Môžete tiež [exportovať údaje na požiadanie](export-destinations.md#run-exports-on-demand).

Ak chcete dopytovať údaje, ktoré boli exportované do Synapse Analytics, potrebujete **Storage Blob Data Reader** prístup k cieľovému úložisku na pracovnom priestore exportov. 

### <a name="update-an-export"></a>Aktualizujte export

1. Prejdite na **Údaje** > **Exporty**.

1. Pri export, ktorý chcete aktualizovať, stlačte možnosť **Upraviť**.

   - **Pridajte** alebo **Odstráňte** entity z výberu. Ak sú entity z výberu odstránené, neodstránia sa z databázy Synapse Analytics. Budúce obnovenie údajov však neaktualizuje odstránené entity v tejto databáze.

   - **Zmena názvu databázy** vytvára novú databázu Synapse Analytics. Databáza s názvom, ktorý bol nakonfigurovaný predtým, nebude v budúcich aktualizáciách dostávať žiadne aktualizácie.
