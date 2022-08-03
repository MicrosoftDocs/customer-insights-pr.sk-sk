---
title: Exportovať segmenty do Adobe Experience Platform (Náhľad)
description: Zistite, ako používať segmenty Customer Insights v Adobe Experience Platform.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: fcb43e0956c6d1f0ef36b222dd2b718906364244
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195309"
---
# <a name="export-segments-to-adobe-experience-platform-preview"></a>Exportovať segmenty do Adobe Experience Platform (Náhľad)

Exportujte segmenty zacielené na relevantné publikum na Adobe Experience Platform.

:::image type="content" source="media/AEP-flow.png" alt-text="Schéma postupu krokov uvedených v tomto článku.":::

## <a name="prerequisites"></a>Požiadavky

- An Adobe Experience Platform licenciu.
- An Adobe Štandardná licencia kampane.
- An [Účet Azure Blob Storage](/azure/storage/blobs/create-data-lake-storage-account) meno a kľúč účtu. Ak chcete nájsť meno a kľúč, pozrite si časť [Spravujte nastavenia účtu úložiska na portáli Azure](/azure/storage/common/storage-account-manage).
- An [Kontajner Azure Blob Storage](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

## <a name="campaign-overview"></a>Prehľad kampane

Aby ste lepšie pochopili, ako môžete použiť segmenty z Customer Insights v Adobe Experience Platform, pozrime sa na fiktívnu ukážkovú kampaň.

Predpokladajme, že vaša spoločnosť ponúka svojim zákazníkom v USA mesačnú službu na základe predplatného. Chcete identifikovať zákazníkov, ktorých predplatné sa má predĺžiť počas nasledujúcich ôsmich dní, ale ešte si ich predplatné neobnovili. Aby ste si udržali týchto zákazníkov, chcete im poslať propagačnú ponuku e-mailom pomocou Adobe Experience Platform.

V tomto príklade chceme propagačnú e-mailovú kampaň spustiť raz. Tento článok sa nevzťahuje na prípady použitia kampane viac ako raz.

## <a name="identify-your-target-audience"></a>Identifikujte svoje cieľové publikum

V našom scenári predpokladáme, že e-mailové adresy zákazníkov sú dostupné v Customer Insights a ich propagačné preferencie boli analyzované s cieľom identifikovať členov segmentu.

The [segment, ktorý ste definovali v Customer Insights](segments.md) sa volá **ChurnProneCustomers** a plánujete poslať týmto zákazníkom e-mailovú propagáciu.

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Snímka obrazovky stránky segmentov s vytvoreným segmentom ChurnProneCustomers.":::

E-mail s ponukou, ktorý chcete poslať, bude obsahovať krstné meno, priezvisko, a dátum ukončenia predplatného zákazníka. Informuje zákazníkov o zľave, ktorú dostanú, ak si obnovia predplatné skôr, ako skončí.

## <a name="export-your-target-audience"></a>Exportujte svoje cieľové publikum

Nakonfigurujeme export z Customer Insights do účtu Azure Blob Storage.

### <a name="set-up-connection-to-azure-blob-storage"></a>Nastavte pripojenie k službe Azure Blob Storage

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Prejdite do časti **Správca** > **Pripojenia**.

1. Vyberte **Pridať pripojenie** a vyberte si **Azure Blob Storage**.

1. Do poľa **Zobrazovaný názov** zadajte rozpoznateľný názov pripojenia. Zobrazovaný názov a typ spojenia, ktoré popisuje toto spojenie. Odporúčame zvoliť názov, ktorý vysvetľuje účel a cieľ tohto spojenia.

1. Vyberte používateľov, ktorí môžu používať toto pripojenie. Predvolene sú to iba správcovia. Viac informácií nájdete v časti [Umožnite prispievateľom použiť pripojenie na export](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Zadajte znak **Názov účtu**, **Kľúč účtu** a **Kontajner** pre váš účet úložiska Blob Storage, kam chcete exportovať segment.  

   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Snímka obrazovky konfigurácií účtu úložiska.":::

1. Skontrolujte [ochrana osobných údajov a dodržiavanie predpisov](connections.md#data-privacy-and-compliance) a vyberte **Súhlasím**.

1. Stlačte možnosť **Uložiť** a dokončite pripojenie.

### <a name="configure-an-export"></a>Nakonfigurujte export

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Prejdite na **Údaje** > **Exporty**.

1. Vyberte **Pridať export**.

1. V poli **Pripojenie na export** vyberte pripojenie v časti úložiska Azure Blob. Ak nie je k dispozícii pripojenie, kontaktujte správcu.

1. Zadajte názov exportu.

1. Vyberte segment, ktorý chcete exportovať. V tomto príklade ide o **ChurnProneCustomers**.

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Snímka obrazovky používateľského rozhrania výberu segmentu s vybraným segmentom ChurnProneCustomers.":::

1. Vyberte **Uložiť**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

> [!NOTE]
> Zaistite, aby bol počet záznamov v exportovanom segmente v rámci povoleného limitu vašej licencie Adobe Campaign Standard.

Exportované údaje sú uložené v kontajneri Azure Blob Storage, ktorý ste nakonfigurovali. Vo vašom kontajneri sa automaticky vytvoria nasledujúce cesty k priečinkom:

- Pre zdrojové entity a entity generované systémom: 

  *%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*

  Príklad: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv

- *Model.json* pre exportované entity bude uložené na úrovni *%ExportDestinationName%*.

  Príklad: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json

## <a name="define-experience-data-model-xdm-in-adobe-experience-platform"></a>Definujte dátový model (XDM) prostredia v Adobe Experience Platform

Pred použitím exportovaných údajov z Customer Insights Adobe Experience Platform, definujte schému Experience Data Model a [konfigurovať údaje pre profil zákazníka v reálnom čase](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).

Zistite, [čo je XDM](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) a oboznámte sa so [základmi kompozície schémy](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).

## <a name="import-data-into-adobe-experience-platform"></a>Importovanie údajov do Adobe Experience Platform

Importujte pripravené údaje o publiku z Customer Insights do Adobe Experience Platform.

1. [Vytvorte pripojenie zdroja Azure Blob Storage](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).

1. [Nakonfigurujte tok údajov](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) pre dávkové pripojenie cloudového úložiska na importovanie segmentového výstupu z Customer Insights do Adobe Experience Platform.

## <a name="create-an-audience-in-adobe-campaign-standard"></a>Vytvorte cieľovú skupinu v Adobe Campaign Standard

Na odoslanie e-mailu pre túto kampaň použijeme program Adobe Campaign Standard.

1. [Vytvorte publikum](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) v Adobe Štandardná kampaň využívajúca údaje v Adobe Experience Platform.

1. [Použite nástroj na tvorbu segmentov](https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/adobe-experience-platform/audience-destinations/aep-using-segment-builder.html) v Adobe Štandardná kampaň na definovanie publika na základe údajov v Adobe Experience Platform.

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>Vytvorte a odošlite e-mail pomocou Adobe Campaign Standard

Vytvorte e-mailový obsah a potom [otestujte a odošlite](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) svoj e-mail.

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Vzorový e-mail s ponukou na obnovenie z Adobe Campaign Standard.":::

[!INCLUDE [footer-include](includes/footer-banner.md)]
