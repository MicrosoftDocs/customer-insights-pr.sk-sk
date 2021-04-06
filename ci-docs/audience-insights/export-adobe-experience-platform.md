---
title: Exportujte údaje Customer Insights do aplikácie Adobe Experience Platform
description: Naučte sa, ako používať segmenty štatistík publika v aplikácii Adobe Experience Platform.
ms.date: 02/26/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: d1856861562be55c6d1d051050fe965560fa42f8
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596288"
---
# <a name="use-customer-insights-segments-in-adobe-experience-platform-preview"></a>Naučte sa, ako používať segmenty Customer Insights v Adobe Experience Platform (ukážka)

Ako používateľ štatistík cieľovej skupiny pre Dynamics 365 Customer Insights ste možno vytvorili segmenty na zefektívnenie svojich marketingových kampaní zacielením na relevantné publikum. Ak chcete použiť segment z prehľadov cieľovej skupiny v platforme Adobe Experience Platform a aplikáciách, ako je Adobe Campaign Standard, musíte postupovať podľa niekoľkých krokov uvedených v tomto článku.

:::image type="content" source="media/AEP-flow.png" alt-text="Schéma postupu krokov uvedených v tomto článku.":::

## <a name="prerequisites"></a>Predpoklady

-   Licencia Dynamics 365 Customer Insights
-   Licencia platformy Adobe Experience
-   Licencia Adobe Campaign Standard
-   Účet úložiska Azure Blob

## <a name="campaign-overview"></a>Prehľad kampane

Aby sme lepšie pochopili, ako môžete použiť segmenty z prehľadov publika v platforme Adobe Experience Platform, pozrime sa na fiktívnu ukážkovú kampaň.

Predpokladajme, že vaša spoločnosť ponúka svojim zákazníkom v USA mesačnú službu na základe predplatného. Chcete identifikovať zákazníkov, ktorých predplatné sa má predĺžiť počas nasledujúcich ôsmich dní, ale ešte si ich predplatné neobnovili. Ak si chcete týchto zákazníkov udržať, chcete im poslať propagačnú ponuku e-mailom pomocou programu Adobe Experience Platform.

V tomto príklade chceme propagačnú e-mailovú kampaň spustiť raz. Tento článok sa nevzťahuje na prípady použitia kampane viac ako raz.

## <a name="identify-your-target-audience"></a>Identifikujte svoje cieľové publikum

V našom scenári predpokladáme, že e-mailové adresy zákazníkov sú k dispozícii v štatistikách publika a ich propagačné preferencie boli analyzované s cieľom identifikovať členov segmentu.

[Segment, ktorý ste definovali v štatistikách cieľovej skupiny](segments.md) sa volá **ChurnProneCustomers** a týmto zákazníkom plánujete poslať e-mailovú propagáciu.

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Snímka obrazovky stránky segmentov s vytvoreným segmentom ChurnProneCustomers.":::

E-mail s ponukou, ktorý chcete poslať, bude obsahovať krstné meno, priezvisko, a dátum ukončenia predplatného zákazníka. Informuje zákazníkov o zľave, ktorú dostanú, ak si obnovia predplatné skôr, ako skončí.

## <a name="export-your-target-audience"></a>Exportujte svoje cieľové publikum

Po identifikácii nášho cieľového publika môžeme nakonfigurovať export z prehľadov cieľovej skupiny do účtu úložiska Azure Blob.

1. V prehľadoch cieľových skupín prejdite na **Správca** > **Ciele exportu**.

1. V dlaždici **Úložisko Azure Blob** stlačte možnosť **Nastaviť**.

   :::image type="content" source="media/export-azure-blob-storage-tile.png" alt-text="Konfiguračná dlaždica pre úložisko Azure Blob.":::

1. Zadajte **Zobrazovacie meno** pre tento nový cieľ exportu a potom zadajte **Názov účtu**, **Kľúč účtu** a **Kontajner** účtu úložiska Azure Blob, do ktorého chcete segment exportovať.  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Snímka obrazovky konfigurácií účtu úložiska."::: 

   - Ďalšie informácie o tom, ako nájsť názov a kľúč účtu úložiska Azure Blob nájdete na stránke [Správa nastavení účtu úložiska na portáli Azure](/azure/storage/common/storage-account-manage).

   - Informácie o tom, ako vytvoriť kontajner, nájdete v časti [Vytvorenie kontajnera](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

1. Vyberte **Ďalej**.

1. Vyberte segment, ktorý chcete exportovať. V tomto príklade ide o **ChurnProneCustomers**.

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Snímka obrazovky používateľského rozhrania výberu segmentu s vybraným segmentom ChurnProneCustomers.":::

1. Vyberte položku **Uložiť**.

Po uložení cieľu exportu ho nájdete na v časti **Správca** > **Exporty** > **Moje ciele exportu**.

:::image type="content" source="media/export-destination-azure-blob-storage.png" alt-text="Snímka obrazovky so zvýrazneným zoznamom exportov a ukážkovým segmentom.":::

Teraz môžete [exportovať segment na požiadanie](export-destinations.md#export-data-on-demand). Export sa spustí aj pri každej [plánovanej obnove](system.md).

> [!NOTE]
> Zaistite, aby počet záznamov v exportovanom segmente bol v rámci povoleného limitu vašej licencie Adobe Campaign Standard.

Exportované údaje sú uložené v kontajneri úložiska Azure Blob, ktorý ste nakonfigurovali vyššie. Vo vašom kontajneri sa automaticky vytvorí nasledujúca cesta k priečinku:

*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*

Príklad: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv

*Model.json* pre exportované entity bude uložené na úrovni *%ExportDestinationName%*.

Príklad: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json

## <a name="define-experience-data-model-xdm-in-adobe-experience-platform"></a>Definujte dátový model Experience (XDM) v platforme Adobe Experience Platform

Predtým, ako je možné exportované údaje z prehľadov cieľovej skupiny použiť v rámci platformy Adobe Experience Platform, musíme definovať schému dátového modelu Experience a [nakonfigurujte údaje pre profil zákazníka v reálnom čase](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).

Zistite, [čo je XDM](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) a oboznámte sa so [základmi kompozície schémy](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).

## <a name="import-data-into-adobe-experience-platform"></a>Importujte údaje do platformy Adobe Experience Platform

Teraz, keď je všetko na svojom mieste, musíme na vytvorenie profilov importovať pripravené údaje o publiku z prehľadov publika do štandardu Adobe Experience Platform.

Najprv [vytvorte pripojenie zdroja úložiska Azure Blob](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).    

Po definovaní zdrojového pripojenia [nakonfigurujte tok údajov](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) pre dávkové pripojenie cloudového úložiska na importovanie segmentového výstupu z prehľadov publika do platformy Adobe Experience Platform.

## <a name="create-an-audience-in-adobe-campaign-standard"></a>Vytvorte cieľovú skupinu v službe Adobe Campaign Standard

Na odoslanie e-mailu s touto kampaňou použijeme program Adobe Campaign Standard. Po importe údajov do platformy Adobe Experience Platform musíme [vytvoriť cieľovú skupinu](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) v Adobe Campaign Standard s využitím údajov v Adobe Experience Platform.

Zistite, ako [používať nástroj na tvorbu segmentov](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/working-with-adobe-experience-platform/aep-using-segment-builder.html#building-a-segment) v Adobe Campaign Standard na definovanie cieľovej skupiny na základe údajov v Adobe Experience Platform.

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>Vytvorte a odošlite e-mail pomocou aplikácie Adobe Campaign Standard

Vytvorte e-mailový obsah a potom [otestujte a odošlite](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) svoj e-mail.

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Vzorový e-mail s ponukou na obnovenie od spoločnosti Adobe Campaign Standard.":::