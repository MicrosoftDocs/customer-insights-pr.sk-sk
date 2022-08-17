---
title: Exportovať údaje do Azure Synapse Analytics (Náhľad)
description: Zistite, ako nakonfigurovať pripojenie k Azure Synapse Analytics.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 0e953cfff12df433d033717d58b28c2834468916
ms.sourcegitcommit: 086f75136132d561cd78a4c2cb1e1933e2301f32
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 08/11/2022
ms.locfileid: "9259863"
---
# <a name="export-data-to-azure-synapse-analytics-preview"></a>Exportovať údaje do Azure Synapse Analytics (Náhľad)

Azure Synapse je analytická služba, ktorá urýchľuje čas na získanie prehľadu o dátových skladoch a systémoch veľkých údajov. Údaje služby Customer Insights môžete prijímať a používať v aplikácii [Azure Synapse](/azure/synapse-analytics/overview-what-is).

## <a name="prerequisites"></a>Požiadavky

> [!NOTE]
> Nezabudnite nastaviť všetky **priradenia rolí**, ako je opísané.

- V Customer Insights, vaše Azure Active Directory (AD) používateľský účet musí mať [Rola správcu](permissions.md#add-users).

V Azure:

- Aktívne predplatné služieb Azure.

- Ak používate nový Azure Data Lake Storage účet Gen2, [principál služby pre Customer Insights](connect-service-principal.md) má **Storage Blob Data Contributor** povolenia. Úložisko Data Lake Storage Gen2 **musí mať** povolenú možnosť [hierarchický názov](/azure/storage/blobs/data-lake-storage-namespace).

- V skupine prostriedkov, kde je Azure Synapse sa nachádza pracovný priestor, *objednávateľ služby* a *Azure AD používateľ s oprávneniami správcu v Customer Insights* musí byť pridelené min **Čitateľ**[povolenia](/azure/role-based-access-control/role-assignments-portal).

- The *Azure AD používateľ s oprávneniami správcu v Customer Insights* má **Storage Blob Data Contributor** povolenia na Azure Data Lake Storage Účet Gen2, v ktorom sú údaje umiestnené a prepojené s Azure Synapse pracovnom priestore. Prečítajte si viac o [používaní portálu Azure Portal na priradenie roly Azure pre prístup k údajom blob a frontu](/azure/storage/common/storage-auth-aad-rbac-portal) a [Povolenia Prispievateľ údajov do objektu BLOB úložiska](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- The *[Azure Synapse identita spravovaná pracovným priestorom](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* má **Storage Blob Data Contributor** povolenia na Azure Data Lake Storage Účet Gen2, v ktorom sú údaje umiestnené a prepojené s Azure Synapse pracovnom priestore. Prečítajte si viac o [používaní portálu Azure Portal na priradenie roly Azure pre prístup k údajom blob a frontu](/azure/storage/common/storage-auth-aad-rbac-portal) a [Povolenia Prispievateľ údajov do objektu BLOB úložiska](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- Na Azure Synapse pracovný priestor, *principál služby pre Customer Insights* má **Správca Synapse**[pridelená rola](/azure/synapse-analytics/security/how-to-set-up-access-control).

- Ak vaše prostredie Customer Insights ukladá údaje vo vašom [vlastné Azure Data Lake Storage](own-data-lake-storage.md), používateľ, ktorý nastavuje pripojenie k Azure Synapse Analytics potrebuje aspoň vstavaný **Čitateľ** rolu na účte Data Lake Storage. Viac informácií nájdete v časti [Priradiť roly Azure pomocou portálu Azure Portal](/azure/role-based-access-control/role-assignments-portal).

## <a name="set-up-connection-to-azure-synapse"></a>Nastaviť pripojenie k Azure Synapse

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Prejdite do časti **Správca** > **Pripojenia**.

1. Vyberte **Pridať pripojenie** a vyberte si **Azure Synapse Analytics**.

1. Do poľa **Zobrazovaný názov** zadajte rozpoznateľný názov pripojenia. Zobrazovaný názov a typ spojenia, ktoré popisuje toto spojenie. Odporúčame zvoliť názov, ktorý vysvetľuje účel a cieľ tohto spojenia.

1. Vyberte používateľov, ktorí môžu používať toto pripojenie. Predvolene sú to iba správcovia. Viac informácií nájdete v časti [Umožnite prispievateľom použiť pripojenie na export](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Vyberte alebo vyhľadajte predplatné, v ktorom chcete použiť údaje Customer Insights. Hneď ako vyberiete predplatné, môžete tiež zvoliť **Pracovný priestor**, **Účet úložiska** a **Kontajner**.

1. Skontrolujte [ochrana osobných údajov a dodržiavanie predpisov](connections.md#data-privacy-and-compliance) a vyberte **Súhlasím**.

1. Stlačte možnosť **Uložiť** a dokončite pripojenie.

## <a name="configure-an-export"></a>Nakonfigurujte export

[!INCLUDE [export-permission-include](includes/export-permission.md)] Na konfiguráciu exportu so zdieľaným pripojením potrebujete min **Prispievateľ** povolenia v Customer Insights.

1. Prejdite na **Údaje** > **Exporty**.

1. Vyberte **Pridať export**.

1. V **Pripojenie na export** vyberte spojenie z poľa Azure Synapse Analytics oddiele. Ak nie je k dispozícii pripojenie, kontaktujte správcu.

1. Poskytnite rozoznateľný **Zobrazovaný názov** pre váš export a **Názov databázy**. Exportom sa vytvorí nový [Azure Synapse databáza jazier](/azure/synapse-analytics/database-designer/concepts-lake-database) v pracovnom priestore definovanom v pripojení.

1. Vyberte entity, do ktorých chcete exportovať Azure Synapse Analytics.
   > [!NOTE]
   > Zdroje údajov založené na [priečinku Common Data Model](connect-common-data-model.md) nie sú podporované.

1. Vyberte **Uložiť**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

Ak chcete dopytovať údaje, ktoré boli exportované do Synapse Analytics, potrebujete **Storage Blob Data Reader** prístup k cieľovému úložisku na pracovnom priestore exportov.

## <a name="update-an-export"></a>Aktualizujte export

1. Prejdite na **Údaje** > **Exporty**.

1. Pri export, ktorý chcete aktualizovať, stlačte možnosť **Upraviť**.

   - **Pridajte** alebo **Odstráňte** entity z výberu. Ak sú entity z výberu odstránené, neodstránia sa z databázy Synapse Analytics. Budúce obnovenie údajov však neaktualizuje odstránené entity v tejto databáze.

   - **Zmena názvu databázy** vytvára novú databázu Synapse Analytics. Databáza s názvom, ktorý bol nakonfigurovaný predtým, nebude v budúcich aktualizáciách dostávať žiadne aktualizácie.

[!INCLUDE [footer-include](includes/footer-banner.md)]
