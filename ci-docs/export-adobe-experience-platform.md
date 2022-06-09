---
title: Export údajov z Customer Insights do Adobe Experience Platform
description: Zistite, ako používať segmenty Customer Insights v Adobe Experience Platform.
ms.date: 03/29/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: 42a4e0c6bce67a63b449a541299620ef2f4a3259
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 04/27/2022
ms.locfileid: "8643738"
---
# <a name="use-customer-insights-segments-in-adobe-experience-platform-preview"></a>Použite segmenty z aplikácie Customer Insights v aplikácii Adobe Experience Platform (náhľad)

Ako používateľ Dynamics 365 Customer Insights, možno ste vytvorili segmenty na zefektívnenie svojich marketingových kampaní zacielením na relevantné publikum. Ak chcete použiť segment zo služby Customer Insights v Adobe Experience Platform a aplikácie ako Adobe Campaign Standard, musíte postupovať podľa niekoľkých krokov uvedených v tomto článku.

:::image type="content" source="media/AEP-flow.png" alt-text="Schéma postupu krokov uvedených v tomto článku.":::

## <a name="prerequisites"></a>Predpoklady

-   Licencia Dynamics 365 Customer Insights
-   Licencia Adobe Experience Platform
-   Licencia Adobe Campaign Standard
-   Účet úložiska Azure Blob

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

Po identifikovaní nášho cieľového publika môžeme nakonfigurovať export z Customer Insights do účtu Azure Blob Storage.

### <a name="configure-a-connection"></a>Konfigurácia a pripojenie

1. Prejdite do časti **Správca** > **Pripojenia**.

1. Vyberte **Pridať pripojenie** a zvoľte možnosť **Azure Blob Storage** alebo vyberte možnosť **Nastaviť** na dlaždici **Azure Blob Storage** na konfiguráciu pripojenia.

   :::image type="content" source="media/export-azure-blob-storage-tile.png" alt-text="Konfiguračná dlaždica pre úložisko Azure Blob."::: 

1. Do poľa **Zobrazovaný názov** zadajte rozpoznateľný názov pripojenia. Zobrazovaný názov a typ spojenia, ktoré popisuje toto spojenie. Odporúčame zvoliť názov, ktorý vysvetľuje účel a cieľ tohto spojenia.

1. Vyberte používateľov, ktorí môžu používať toto pripojenie. Ak neurobíte nič, predvolená hodnota bude Správcovia. Viac informácií nájdete v časti [Umožnite prispievateľom použiť pripojenie na export](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Zadajte znak **Názov účtu**, **Kľúč účtu** a **Kontajner** pre váš účet úložiska Blob Storage, kam chcete exportovať segment.  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Snímka obrazovky konfigurácií účtu úložiska."::: 
   
    - Ak sa chcete dozvedieť viac o názve a kľúči účtu úložiska Blob Storage, prečítajte si časť [Správa nastavení účtu v portáli Azure](/azure/storage/common/storage-account-manage).
    - Informácie o tom, ako vytvoriť kontajner, nájdete v časti [Vytvorenie kontajnera](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

1. Stlačte možnosť **Uložiť** a dokončite pripojenie. 

### <a name="configure-an-export"></a>Nakonfigurujte export

Tento export môžete nakonfigurovať, ak máte prístup k pripojeniu tohto typu. Viac informácií nájdete na stránke [Na konfiguráciu exportu sú potrebné povolenia](export-destinations.md#set-up-a-new-export).

1. Prejdite na **Údaje** > **Exporty**.

1. Na vytvorenie nového exportu stlačte možnosť **Pridať export**.

1. V poli **Pripojenie na export** vyberte pripojenie v časti úložiska Azure Blob. Ak nevidíte názov tejto sekcie, nemáte k dispozícii žiadne pripojenia tohto typu.

1. Vyberte segment, ktorý chcete exportovať. V tomto príklade ide o **ChurnProneCustomers**.

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Snímka obrazovky používateľského rozhrania výberu segmentu s vybraným segmentom ChurnProneCustomers.":::

1. Vyberte položku **Uložiť**.

Po uložení cieľu exportu ho nájdete v časti **Údaje** > **Exporty**.

Teraz môžete [exportovať segment na požiadanie](export-destinations.md#run-exports-on-demand). Export sa spustí aj pri každej [plánovanej obnove](system.md).

> [!NOTE]
> Zaistite, aby bol počet záznamov v exportovanom segmente v rámci povoleného limitu vašej licencie Adobe Campaign Standard.

Exportované údaje sú uložené v kontajneri úložiska Azure Blob Storage, ktorý ste nakonfigurovali vyššie. Vo vašom kontajneri sa automaticky vytvorí nasledujúca cesta k priečinku:

*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*

Príklad: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv

*Model.json* pre exportované entity bude uložené na úrovni *%ExportDestinationName%*.

Príklad: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json

## <a name="define-experience-data-model-xdm-in-adobe-experience-platform"></a>Definujte dátový model (XDM) prostredia v Adobe Experience Platform

Pred použitím exportovaných údajov z Customer Insights Adobe Experience Platform, musíme definovať schému Experience Data Model a [konfigurovať údaje pre profil zákazníka v reálnom čase](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).

Zistite, [čo je XDM](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) a oboznámte sa so [základmi kompozície schémy](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).

## <a name="import-data-into-adobe-experience-platform"></a>Importovanie údajov do Adobe Experience Platform

Teraz, keď je všetko na svojom mieste, musíme importovať pripravené údaje o publiku z Customer Insights do Adobe Experience Platform.

Najprv [vytvorte pripojenie zdroja úložiska Azure Blob](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).    

Po definovaní zdrojového pripojenia [nakonfigurovať tok údajov](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) pre dávkové pripojenie cloudového úložiska na importovanie segmentového výstupu z Customer Insights do Adobe Experience Platform.

## <a name="create-an-audience-in-adobe-campaign-standard"></a>Vytvorte cieľovú skupinu v Adobe Campaign Standard

Na odoslanie e-mailu pre túto kampaň použijeme program Adobe Campaign Standard. Po importe údajov do Adobe Experience Platform, musíme [vytvoriť cieľovú skupinu](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) v Adobe Campaign Standard použitím údajov v Adobe Experience Platform.


Zistite, ako [použiť nástroj na tvorbu segmentov](https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/adobe-experience-platform/audience-destinations/aep-using-segment-builder.html) v Adobe Campaign Standard na definovanie cieľovej skupiny na základe údajov v Adobe Experience Platform.

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>Vytvorte a odošlite e-mail pomocou Adobe Campaign Standard

Vytvorte e-mailový obsah a potom [otestujte a odošlite](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) svoj e-mail.

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Vzorový e-mail s ponukou na obnovenie z Adobe Campaign Standard.":::