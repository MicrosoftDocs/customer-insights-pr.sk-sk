---
title: Export údajov z Customer Insights do Adobe Campaign Standard
description: Naučte sa, ako používať segmenty prehľadov cieľových skupín na platforme Adobe Campaign Standard.
ms.date: 03/29/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: 6b90ee53236fdd601ecdfd8e6117a15269a08084
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 02/16/2022
ms.locfileid: "8227777"
---
# <a name="use-customer-insights-segments-in-adobe-campaign-standard-preview"></a>Použite segmenty z aplikácie Customer Insights v aplikácii Adobe Campaign Standard (náhľad)

Ako používateľ prehľadov interakcií v službe Dynamics 365 Customer Insights ste možno vytvorili segmenty na zefektívnenie svojich marketingových kampaní tak, že ste ich zacielili na relevantné publikum. Ak chcete použiť segment z prehľadov cieľovej skupiny v Adobe Experience Platform a aplikácie ako Adobe Campaign Standard, musíte postupovať podľa niekoľkých krokov uvedených v tomto článku.

:::image type="content" source="media/ACS-flow.png" alt-text="Schéma postupu krokov uvedených v tomto článku.":::

## <a name="prerequisites"></a>Predpoklady

-   Licencia Dynamics 365 Customer Insights
-   Licencia Adobe Campaign Standard
-   Účet úložiska Azure Blob

## <a name="campaign-overview"></a>Prehľad kampane

Aby ste lepšie porozumeli tomu, ako môžete používať segmenty z prehľadov cieľových skupín v Adobe Experience Platform, pozrime sa na fiktívnu ukážkovú kampaň.

Predpokladajme, že vaša spoločnosť ponúka svojim zákazníkom v USA mesačnú službu na základe predplatného. Chcete identifikovať zákazníkov, ktorých predplatné sa má predĺžiť počas nasledujúcich ôsmich dní, ale ešte si ich predplatné neobnovili. Aby ste si udržali týchto zákazníkov, chcete im poslať propagačnú ponuku e-mailom pomocou Adobe Campaign Standard.

V tomto príklade chceme propagačnú e-mailovú kampaň spustiť raz. Tento článok sa nevzťahuje na prípady použitia kampane viac ako raz. Prehľady cieľovej skupiny a Adobe Campaign Standard je možné nakonfigurovať tak, aby fungovali aj pre scenár opakujúcej sa kampane.

## <a name="identify-your-target-audience"></a>Identifikujte svoje cieľové publikum

V našom scenári predpokladáme, že e-mailové adresy zákazníkov sú k dispozícii v štatistikách publika a ich propagačné preferencie boli analyzované s cieľom identifikovať členov segmentu.

[Segment, ktorý ste definovali v štatistikách cieľovej skupiny](segments.md) sa volá **ChurnProneCustomers** a týmto zákazníkom plánujete poslať e-mailovú propagáciu.

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Snímka obrazovky stránky segmentov s vytvoreným segmentom ChurnProneCustomers.":::

E-mail s ponukou, ktorý chcete poslať, bude obsahovať krstné meno, priezvisko, a dátum ukončenia predplatného zákazníka. Informuje zákazníkov o zľave, ktorú dostanú, ak si obnovia predplatné skôr, ako skončí.

## <a name="export-your-target-audience"></a>Exportujte svoje cieľové publikum

### <a name="configure-a-connection"></a>Konfigurácia a pripojenie

Po identifikácii nášho cieľového publika môžeme nakonfigurovať export z prehľadov cieľovej skupiny do účtu úložiska Azure Blob.

1. V prehľadoch cieľovej skupiny prejdite na **Správca** > **Pripojenia**.

1. Vyberte **Pridať pripojenie** a zvoľte možnosť **Adobe Campaign** na konfiguráciu pripojenia alebo vyberte možnosť **Nastaviť** v dlaždici **Adobe Campaign**.

   :::image type="content" source="media/adobe-campaign-standard-tile.png" alt-text="Konfiguračná dlaždica pre Adobe Campaign Standard.":::

1. Do poľa **Zobrazovaný názov** zadajte rozpoznateľný názov pripojenia. Zobrazovaný názov a typ spojenia, ktoré popisuje toto spojenie. Odporúčame zvoliť názov, ktorý vysvetľuje účel a cieľ tohto spojenia.

1. Vyberte používateľov, ktorí môžu používať toto pripojenie. Ak neurobíte nič, predvolená hodnota bude Správcovia. Viac informácií nájdete na stránke [Na konfiguráciu exportu sú potrebné povolenia](export-destinations.md#set-up-a-new-export).

1. Zadajte znak **Názov účtu**, **Kľúč účtu** a **Kontajner** účtu Azure Blob Storage, do ktorého chcete segment exportovať.  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Snímka obrazovky konfigurácií účtu úložiska."::: 

   - Ďalšie informácie o tom, ako nájsť názov a kľúč účtu úložiska Azure Blob Storage nájdete na stránke [Správa nastavení účtu úložiska na portáli Azure](/azure/storage/common/storage-account-manage).

   - Informácie o tom, ako vytvoriť kontajner, nájdete v časti [Vytvorenie kontajnera](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

1. Stlačte možnosť **Uložiť** a dokončite pripojenie.

### <a name="configure-an-export"></a>Nakonfigurujte export

Tento export môžete nakonfigurovať, ak máte prístup k pripojeniu tohto typu. Viac informácií nájdete na stránke [Na konfiguráciu exportu sú potrebné povolenia](export-destinations.md#set-up-a-new-export).

1. Prejdite na **Údaje** > **Exporty**.

1. Na vytvorenie nového exportu stlačte možnosť **Pridať export**.

1. V poli **Pripojenie na export** vyberte pripojenie zo sekcie Adobe Campaign. Ak nevidíte názov tejto sekcie, nemáte k dispozícii žiadne pripojenia tohto typu.

1. Vyberte segment, ktorý chcete exportovať. V tomto príklade ide o **ChurnProneCustomers**.

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Snímka obrazovky používateľského rozhrania výberu segmentu s vybraným segmentom ChurnProneCustomers.":::

1. Vyberte **Ďalej**.

1. Teraz mapujeme polia **Zdroj** zo segmentu prehľadov cieľových skupín k názvom polí **Cieľ** v schéme profilu Adobe Campaign Standard.

   :::image type="content" source="media/ACS-field-mapping.png" alt-text="Mapovanie polí pre konektor Adobe Campaign Standard.":::

   Ak chcete pridať ďalšie atribúty, stlačte možnosť **Pridať atribút**. Cieľový názov sa môže líšiť od názvu zdrojového poľa, takže môžete stále mapovať výstup segmentov z prehľadov cieľovej skupiny na Adobe Campaign Standard, ak polia v týchto dvoch systémoch nemajú rovnaký názov.

   > [!NOTE]
   > E-mailová adresa sa používa ako pole identity, ale na priradenie údajov k Adobe Campaign Standard môžete použiť akýkoľvek iný identifikátor zo zákazníckeho profilu prehľadov cieľovej skupiny.

1. Vyberte položku **Uložiť**.

Po uložení cieľu exportu ho nájdete v časti **Údaje** > **Exporty**.

Teraz môžete [exportovať segment na požiadanie](export-destinations.md#run-exports-on-demand). Export sa spustí aj pri každej [plánovanej obnove](system.md).

> [!NOTE]
> Zaistite, aby bol počet záznamov v exportovanom segmente v rámci povoleného limitu vašej licencie Adobe Campaign Standard.

Exportované údaje sú uložené v kontajneri úložiska Azure Blob Storage, ktorý ste nakonfigurovali vyššie. Vo vašom kontajneri sa automaticky vytvorí nasledujúca cesta k priečinku:

*%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*

Príklad: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv

## <a name="configure-adobe-campaign-standard"></a>Nakonfigurujte Adobe Campaign Standard

Keď sa exportuje segment z prehľadov publika, obsahuje stĺpce, ktoré ste vybrali pri definovaní cieľa exportu v predchádzajúcom kroku. Tieto údaje je možné použiť na [vytváranie profilov v Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).

Ak chcete použiť segment v Adobe Campaign Standard, musíte rozšíriť schému profilu v Adobe Campaign Standard, aby obsahovala dve ďalšie polia. Zistite, ako [rozšíriť zdroj profilu](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) o nové polia v Adobe Campaign Standard.

V našom príklade sú to tieto polia *Názov segmentu a dátum segmentu (voliteľné)*.

Tieto polia použijeme na identifikáciu profilov v programe Adobe Campaign Standard, na ktoré chceme túto kampaň zacieliť.

Ak v programe Adobe Campaign Standard neexistujú žiadne ďalšie záznamy, než tie, ktoré sa chystáte importovať, môžete tento krok preskočiť.

## <a name="import-data-into-adobe-campaign-standard"></a>Importovanie údajov do Adobe Campaign Standard

Teraz, keď je všetko na svojom mieste, musíme importovať pripravené údaje o cieľovej skupine z prehľadov cieľovej skupiny do Adobe Campaign Standard na vytvorenie profilov. Zistite, [ako importovať profily do Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences) pomocou pracovného postup.

Pracovný postup importu na obrázku nižšie bol nakonfigurovaný tak, aby sa spúšťal každých osem hodín a hľadal exportované segmenty prehľadov cieľových skupín (súbor .csv v úložisku Azure Blob Storage). Pracovný postup extrahuje obsah súboru .csv v určenom poradí stĺpcov. Tento pracovný postup bol vytvorený tak, aby vykonával základné spracovanie chýb a zaistil, aby každý záznam mal e-mailovú adresu pred hydratáciou údajov v programe Adobe Campaign Standard. Pracovný postup tiež extrahuje názov segmentu z názvu súboru pred jeho zavedením do údajov profilu riešenia Adobe Campaign Standard.

:::image type="content" source="media/ACS-import-workflow.png" alt-text="Snímka obrazovky pracovného postupu importu v používateľskom rozhraní Adobe Campaign Standard.":::

## <a name="retrieve-the-audience-in-adobe-campaign-standard"></a>Získajte cieľovú skupinu v Adobe Campaign Standard

Akonáhle sú údaje importované do Adobe Campaign Standard, [môže vytvoriť pracovný postup](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) a [dotaz](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) zákazníkov na základe možností *Názov segmentu* a *Dátum segmentu* na výber profilov, ktoré boli identifikované pre našu ukážkovú kampaň.

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>Vytvorte a odošlite e-mail pomocou Adobe Campaign Standard

Vytvorte e-mailový obsah a potom [otestujte a odošlite](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) svoj e-mail.

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Vzorový e-mail s ponukou na obnovenie z Adobe Campaign Standard.":::
