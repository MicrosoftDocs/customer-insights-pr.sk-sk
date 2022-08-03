---
title: Exportujte segmenty Customer Insights do Adobe Štandardná kampaň (ukážka)
description: Zistite, ako používať segmenty Customer Insights v Adobe Štandardná kampaň.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: 834880cac9c5023157983081ff2513d9b051491f
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195539"
---
# <a name="export-customer-insights-segments-to-adobe-campaign-standard-preview"></a>Exportujte segmenty Customer Insights do Adobe Štandardná kampaň (ukážka)

Exportujte segmenty, ktoré sú zacielené na relevantné publikum Adobe Štandardná kampaň.

:::image type="content" source="media/ACS-flow.png" alt-text="Schéma postupu krokov uvedených v tomto článku.":::

## <a name="prerequisites"></a>Požiadavky

- An Adobe Štandardná licencia kampane.
- An [Účet Azure Blob Storage](/azure/storage/blobs/create-data-lake-storage-account) meno a kľúč účtu. Ak chcete nájsť meno a kľúč, pozrite si časť [Spravujte nastavenia účtu úložiska na portáli Azure](/azure/storage/common/storage-account-manage).
- An [Kontajner Azure Blob Storage](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

## <a name="campaign-overview"></a>Prehľad kampane

Aby ste lepšie pochopili, ako môžete použiť segmenty z Customer Insights v Adobe Experience Platform, pozrime sa na fiktívnu ukážkovú kampaň.

Predpokladajme, že vaša spoločnosť ponúka svojim zákazníkom v USA mesačnú službu na základe predplatného. Chcete identifikovať zákazníkov, ktorých predplatné sa má predĺžiť počas nasledujúcich ôsmich dní, ale ešte si ich predplatné neobnovili. Aby ste si udržali týchto zákazníkov, chcete im poslať propagačnú ponuku e-mailom pomocou Adobe Campaign Standard.

V tomto príklade chceme propagačnú e-mailovú kampaň spustiť raz. Tento článok sa nevzťahuje na prípady použitia kampane viac ako raz. Avšak, Customer Insights a Adobe Campaign Standard môže byť nakonfigurovaný tak, aby fungoval aj pre scenár opakujúcej sa kampane.

## <a name="identify-your-target-audience"></a>Identifikujte svoje cieľové publikum

V našom scenári predpokladáme, že e-mailové adresy zákazníkov sú dostupné v Customer Insights a ich propagačné preferencie boli analyzované s cieľom identifikovať členov segmentu.

The [segment, ktorý ste definovali v Customer Insights](segments.md) sa volá **ChurnProneCustomers** a plánujete poslať týmto zákazníkom e-mailovú propagáciu.

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Snímka obrazovky stránky segmentov s vytvoreným segmentom ChurnProneCustomers.":::

E-mail s ponukou, ktorý chcete poslať, bude obsahovať krstné meno, priezvisko, a dátum ukončenia predplatného zákazníka. Informuje zákazníkov o zľave, ktorú dostanú, ak si obnovia predplatné skôr, ako skončí.

## <a name="export-your-target-audience"></a>Exportujte svoje cieľové publikum

### <a name="set-up-connection-to-adobe-campaign"></a>Nastaviť pripojenie k Adobe kampaň

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Prejdite do časti **Správca** > **Pripojenia**.

1. Vyberte **Pridať pripojenie** a vyberte si **Adobe kampaň**.

1. Do poľa **Zobrazovaný názov** zadajte rozpoznateľný názov pripojenia. Zobrazovaný názov a typ spojenia, ktoré popisuje toto spojenie. Odporúčame zvoliť názov, ktorý vysvetľuje účel a cieľ tohto spojenia.

1. Vyberte používateľov, ktorí môžu používať toto pripojenie. Predvolene sú to iba správcovia. Viac informácií nájdete v časti [Umožnite prispievateľom použiť pripojenie na export](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Zadajte **Názov účtu**, **účtu**, a **Kontajner** pre váš účet Blob Storage.  

   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Snímka obrazovky konfigurácií účtu úložiska.":::

1. Skontrolujte [ochrana osobných údajov a dodržiavanie predpisov](connections.md#data-privacy-and-compliance) a vyberte **Súhlasím**.

1. Stlačte možnosť **Uložiť** a dokončite pripojenie.

### <a name="configure-an-export"></a>Nakonfigurujte export

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Prejdite na **Údaje** > **Exporty**.

1. Vyberte **Pridať export**.

1. V poli **Pripojenie na export** vyberte pripojenie zo sekcie Adobe Campaign. Ak nie je k dispozícii pripojenie, kontaktujte správcu.

1. Zadajte názov exportu.

1. Vyberte segment, ktorý chcete exportovať. V tomto príklade ide o **ChurnProneCustomers**.

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Snímka obrazovky používateľského rozhrania výberu segmentu s vybraným segmentom ChurnProneCustomers.":::

1. Vyberte **Ďalej**.

1. Zmapovať **Zdroj** polia zo segmentu Customer Insights do **Cieľ** názvy polí v Adobe Schéma štandardného profilu kampane.

   :::image type="content" source="media/ACS-field-mapping.png" alt-text="Mapovanie polí pre konektor Adobe Campaign Standard.":::

   Ak chcete pridať ďalšie atribúty, stlačte možnosť **Pridať atribút**. Cieľový názov sa môže líšiť od názvu zdrojového poľa, takže stále môžete mapovať výstup segmentu z Customer Insights na Adobe Štandardná kampaň, ak polia nemajú rovnaký názov v týchto dvoch systémoch.

   > [!NOTE]
   > E-mailová adresa sa používa ako pole identity, ale na mapovanie údajov môžete použiť akýkoľvek iný identifikátor z profilu zákazníka Adobe Štandardná kampaň.

1. Vyberte **Uložiť**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

> [!NOTE]
> Zaistite, aby bol počet záznamov v exportovanom segmente v rámci povoleného limitu vašej licencie Adobe Campaign Standard.

Exportované údaje sú uložené v kontajneri úložiska Azure Blob Storage, ktorý ste nakonfigurovali vyššie. Vo vašom kontajneri sa automaticky vytvorí nasledujúca cesta k priečinku: *%ContainerName% /CustomerInsights_%instanceID% /% exportdestination-name%_%segmentname%_%timestamp% .csv*

Príklad: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv

## <a name="configure-adobe-campaign-standard"></a>Nakonfigurujte Adobe Campaign Standard

Exportované segmenty obsahujú stĺpce, ktoré ste vybrali pri konfigurácii exportu. Tieto údaje je možné použiť na [vytváranie profilov v Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).

Ak chcete použiť segment v Adobe Campaign Standard, [rozšíriť schému profilu](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) v Adobe Štandardná kampaň na zahrnutie dvoch ďalších polí.

V našom príklade sú to polia Názov segmentu a Dátum segmentu. Tieto polia použijeme na identifikáciu profilov v programe Adobe Campaign Standard, na ktoré chceme túto kampaň zacieliť.

Ak v ňom nie sú žiadne ďalšie záznamy Adobe Campaign Standard, okrem toho, čo sa chystáte importovať, tento krok preskočte.

## <a name="import-data-into-adobe-campaign-standard"></a>Importovanie údajov do Adobe Campaign Standard

Importujte pripravené údaje o publiku z Customer Insights do Adobe Štandardná kampaň do [vytvárať profily pomocou pracovného postupu](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences).

Pracovný postup importu na obrázku nižšie bol nakonfigurovaný tak, aby sa spúšťal každých osem hodín a hľadal exportované segmenty Customer Insights (súbor .csv v Azure Blob Storage). Pracovný postup extrahuje obsah súboru .csv v určenom poradí stĺpcov. Tento pracovný postup bol vytvorený tak, aby vykonával základné spracovanie chýb a zaistil, aby každý záznam mal e-mailovú adresu pred hydratáciou údajov v programe Adobe Campaign Standard. Pracovný postup tiež extrahuje názov segmentu z názvu súboru pred jeho zavedením do údajov profilu riešenia Adobe Campaign Standard.

:::image type="content" source="media/ACS-import-workflow.png" alt-text="Snímka obrazovky pracovného postupu importu v používateľskom rozhraní Adobe Campaign Standard.":::

## <a name="retrieve-the-audience-in-adobe-campaign-standard"></a>Získajte cieľovú skupinu v Adobe Campaign Standard

Po importovaní údajov do Adobe Campaign Standard, [vytvoriť pracovný postup](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) a [dopyt](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) zákazníkov na základe názvu segmentu a dátumu segmentu na výber profilov, ktoré boli identifikované pre našu vzorovú kampaň.

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>Vytvorte a odošlite e-mail pomocou Adobe Campaign Standard

Vytvorte e-mailový obsah a potom [otestujte a odošlite](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) svoj e-mail.

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Vzorový e-mail s ponukou na obnovenie z Adobe Campaign Standard.":::

[!INCLUDE [footer-include](includes/footer-banner.md)]
