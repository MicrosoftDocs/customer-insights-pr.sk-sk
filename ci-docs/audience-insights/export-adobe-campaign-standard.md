---
title: Exportujte údaje Customer Insights do aplikácie Adobe Campaign Standard
description: Naučte sa, ako používať segmenty štatistík publika v aplikácii Adobe Campaign Standard.
ms.date: 02/26/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: a5d0154c3d7c473dcba03fac0847bafcf97de2f2
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596334"
---
# <a name="use-customer-insights-segments-in-adobe-campaign-standard-preview"></a>Naučte sa, ako používať segmenty Customer Insights v aplikácii Adobe Campaign Standard (ukážka)

Ako používateľ štatistík cieľovej skupiny pre Dynamics 365 Customer Insights ste možno vytvorili segmenty na zefektívnenie svojich marketingových kampaní zacielením na relevantné publikum. Ak chcete použiť segment z prehľadov cieľovej skupiny v platforme Adobe Experience Platform a aplikáciách, ako je Adobe Campaign Standard, musíte postupovať podľa niekoľkých krokov uvedených v tomto článku.

:::image type="content" source="media/ACS-flow.png" alt-text="Schéma postupu krokov uvedených v tomto článku.":::

## <a name="prerequisites"></a>Predpoklady

-   Licencia Dynamics 365 Customer Insights
-   Licencia Adobe Campaign Standard
-   Účet úložiska Azure Blob

## <a name="campaign-overview"></a>Prehľad kampane

Aby sme lepšie pochopili, ako môžete použiť segmenty z prehľadov publika v platforme Adobe Experience Platform, pozrime sa na fiktívnu ukážkovú kampaň.

Predpokladajme, že vaša spoločnosť ponúka svojim zákazníkom v USA mesačnú službu na základe predplatného. Chcete identifikovať zákazníkov, ktorých predplatné sa má predĺžiť počas nasledujúcich ôsmich dní, ale ešte si ich predplatné neobnovili. Ak si chcete týchto zákazníkov udržať, chcete im poslať propagačnú ponuku e-mailom pomocou programu Adobe Campaign Standard.

V tomto príklade chceme propagačnú e-mailovú kampaň spustiť raz. Tento článok sa nevzťahuje na prípady použitia kampane viac ako raz. Štatistiky publika a Adobe Campaign Standard je však možné nakonfigurovať tak, aby fungovali aj pre scenár opakujúcich sa kampaní.

## <a name="identify-your-target-audience"></a>Identifikujte svoje cieľové publikum

V našom scenári predpokladáme, že e-mailové adresy zákazníkov sú k dispozícii v štatistikách publika a ich propagačné preferencie boli analyzované s cieľom identifikovať členov segmentu.

[Segment, ktorý ste definovali v štatistikách cieľovej skupiny](segments.md) sa volá **ChurnProneCustomers** a týmto zákazníkom plánujete poslať e-mailovú propagáciu.

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Snímka obrazovky stránky segmentov s vytvoreným segmentom ChurnProneCustomers.":::

E-mail s ponukou, ktorý chcete poslať, bude obsahovať krstné meno, priezvisko, a dátum ukončenia predplatného zákazníka. Informuje zákazníkov o zľave, ktorú dostanú, ak si obnovia predplatné skôr, ako skončí.

## <a name="export-your-target-audience"></a>Exportujte svoje cieľové publikum

Po identifikácii nášho cieľového publika môžeme nakonfigurovať export z prehľadov cieľovej skupiny do účtu úložiska Azure Blob.

1. V prehľadoch cieľových skupín prejdite na **Správca** > **Ciele exportu**.

1. Na dlaždici **Kampaň Adobe** vyberte položku **Nastaviť**.

   :::image type="content" source="media/adobe-campaign-standard-tile.png" alt-text="Konfiguračná dlaždica pre Adobe Campaign Standard.":::

1. Zadajte **Zobrazovacie meno** pre tento nový cieľ exportu a potom zadajte **Názov účtu**, **Kľúč účtu** a **Kontajner** účtu úložiska Azure Blob, do ktorého chcete segment exportovať.  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Snímka obrazovky konfigurácií účtu úložiska."::: 

   - Ďalšie informácie o tom, ako nájsť názov a kľúč účtu úložiska Azure Blob nájdete na stránke [Správa nastavení účtu úložiska na portáli Azure](/azure/storage/common/storage-account-manage).

   - Informácie o tom, ako vytvoriť kontajner, nájdete v časti [Vytvorenie kontajnera](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

1. Vyberte **Ďalej**.

1. Vyberte segment, ktorý chcete exportovať. V tomto príklade ide o **ChurnProneCustomers**.

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Snímka obrazovky používateľského rozhrania výberu segmentu s vybraným segmentom ChurnProneCustomers.":::

1. Vyberte **Ďalej**.

1. Teraz namapujme polia **Zdroj** od segmentu štatistík cieľovej skupiny do poľa **Cieľ** v schéme profilu služby Adobe Campaign Standard.

   :::image type="content" source="media/ACS-field-mapping.png" alt-text="Mapovanie polí pre konektor Adobe Campaign Standard.":::

   Ak chcete pridať ďalšie atribúty, stlačte možnosť **Pridať atribút**. Cieľový názov sa môže líšiť od názvu zdrojového poľa, takže výstup segmentov z prehľadov publika môžete aj naďalej mapovať do štandardu Adobe Campaign Standard, ak polia nemajú v týchto dvoch systémoch rovnaký názov.

   > [!NOTE]
   > E-mailová adresa sa používa ako pole identity, ale na priradenie údajov k štandardu Adobe Campaign Standard môžete použiť akýkoľvek iný identifikátor z profilu zákazníka s prehľadmi publika.

1. Vyberte položku **Uložiť**.

Po uložení cieľu exportu ho nájdete na v časti **Správca** > **Exporty** > **Moje ciele exportu**.

:::image type="content" source="media/export-destination-adobe-campaign-standard.png" alt-text="Snímka obrazovky so zvýrazneným zoznamom exportov a ukážkovým segmentom.":::

Teraz môžete [exportovať segment na požiadanie](export-destinations.md#export-data-on-demand). Export sa spustí aj pri každej [plánovanej obnove](system.md).

> [!NOTE]
> Zaistite, aby počet záznamov v exportovanom segmente bol v rámci povoleného limitu vašej licencie Adobe Campaign Standard.

Exportované údaje sú uložené v kontajneri úložiska Azure Blob, ktorý ste nakonfigurovali vyššie. Vo vašom kontajneri sa automaticky vytvorí nasledujúca cesta k priečinku:

*%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*

Príklad: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv

## <a name="configure-adobe-campaign-standard"></a>Konfigurácia Adobe Campaign Standard

Keď sa exportuje segment z prehľadov publika, obsahuje stĺpce, ktoré ste vybrali pri definovaní cieľa exportu v predchádzajúcom kroku. Tieto údaje možno použiť na [vytváranie profilov v aplikácii Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).

Ak chcete použiť segment v aplikácii Adobe Campaign Standard, musíme rozšíriť schému profilu v aplikácii Adobe Campaign Standard tak, aby obsahovala ďalšie dve polia. Zistite, ako [rozšíriť zdroj profilu](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) o nové polia v aplikácii Adobe Campaign Standard.

V našom príklade sú to tieto polia *Názov segmentu a dátum segmentu (voliteľné).*

Tieto polia použijeme na identifikáciu profilov v štandarde Adobe Campaign Standard, na ktoré chceme pre túto kampaň zacieliť.

Ak v aplikácii Adobe Campaign Standard neexistujú žiadne ďalšie záznamy okrem tých, ktoré sa chystáte importovať, môžete tento krok preskočiť.

## <a name="import-data-into-adobe-campaign-standard"></a>Importujte údaje do aplikácie Adobe Campaign Standard

Teraz, keď je všetko na svojom mieste, musíme na vytvorenie profilov importovať pripravené údaje o publiku z prehľadov publika do štandardu Adobe Campaign Standard. Zistite [ako importovať profily v aplikácii Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences) pomocou pracovného postupu.

Pracovný postup importu na obrázku nižšie bol nakonfigurovaný tak, aby sa spúšťal každých 8 hodín, a vyhľadáva exportované segmenty štatistík cieľovej skupiny (súbor .csv v úložisku Azure Blob). Pracovný postup extrahuje obsah súboru .csv v určenom poradí stĺpcov. Tento pracovný postup bol zostavený tak, aby vykonával základné spracovanie chýb a zabezpečil, aby mal každý záznam e-mailovú adresu pred hydratáciou údajov v aplikácii Adobe Campaign Standard. Pracovný postup tiež extrahuje názov segmentu z názvu súboru pred aktualizáciou do údajov profilu ACS.

:::image type="content" source="media/ACS-import-workflow.png" alt-text="Snímka obrazovky z pracovného postupu importu v používateľskom rozhraní služby Adobe Campaign Standard.":::

## <a name="retrieve-the-audience-in-adobe-campaign-standard"></a>Získajte cieľovú skupinu v službe Adobe Campaign Standard

Po importovaní údajov do aplikácie Adobe Campaign Standard [môžete vytvoriť pracovný postup](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) a [dopyt](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) zákazníkov na základe polí *Názov segmentu* a *Dátum segmentu* na výber profilov, ktoré boli identifikované pre našu vzorovú kampaň.

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>Vytvorte a odošlite e-mail pomocou aplikácie Adobe Campaign Standard

Vytvorte e-mailový obsah a potom [otestujte a odošlite](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) svoj e-mail.

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Vzorový e-mail s ponukou na obnovenie od spoločnosti Adobe Campaign Standard.":::