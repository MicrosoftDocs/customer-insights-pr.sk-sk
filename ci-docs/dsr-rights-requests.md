---
title: Žiadosti dotknutých osôb (DSR) podľa GDPR | Dokumentácia spoločnosti Microsoft
description: Odpovedajte na žiadosti dotknutých osôb pre funkciu prehľadov cieľových skupín v službe Dynamics 365 Customer Insights.
ms.date: 08/11/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: e095eb4f8e194f314d7d6baf6fa6a7a319319d2a
ms.sourcegitcommit: 1946d7af0bd2ca216885bec3c5c95009996d9a28
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 02/25/2022
ms.locfileid: "8350288"
---
# <a name="data-subject-rights-dsr-requests-under-gdpr"></a>Žiadosti o práva dotknutých osôb (DSR) podľa GDPR

Všeobecné nariadenie Európskej únie o ochrane údajov (GDPR) je účinné od 25. mája 2018. Poskytuje jednotlivcom významné práva týkajúce sa ich údajov. GDPR je o ochrane a uplatňovaní práv na súkromie osôb. Viac informácií o záväzku spoločnosti Microsoft k bezpečnosti a zhode s predpismi sa dozviete v [Centre dôveryhodnosti spoločnosti Microsoft](https://www.microsoft.com/trust-center).

Zaviazali sme sa pomôcť našim zákazníkom splniť ich požiadavky v zmysle smernice GDPR. Zahŕňa právo na odstránenie a export údajov, ktoré zahŕňajú osobné informácie, ako sú identifikácie používateľov, telefónne čísla a e-mailové adresy. Správcovia môžu implementovať žiadosti používateľov o odstránenie alebo export osobných údajov.

## <a name="audience-insights"></a>Prehľady cieľových skupín

### <a name="responding-to-gdpr-data-subject-delete-requests-for-dynamics-365-customer-insights-audience-insights-capability"></a>Odpovede na žiadosti dotknutých osôb o odstránenie podľa nariadenia GRPR pre funkciu prehľadov cieľových skupín v službe Dynamics 365 Customer Insights

„Právo na vymazanie“ odstránením osobných údajov z údajov o zákazníkoch organizácie je kľúčovou ochranou podľa všeobecného nariadenia o ochrane údajov (GDPR). Odstránenie osobných údajov zahŕňa odstránenie všetkých osobných údajov a protokolov generovaných systémom, okrem informácií z denníkov auditu.

#### <a name="manage-data-subject-delete-requests"></a>Správa požiadaviek na odstránenie dotknutej osoby

Prehľady cieľových skupín ponúkajú nasledujúce integrované rozhranie na vymazanie osobných údajov pre konkrétneho zákazníka alebo používateľa:

- **Spravovať žiadosti o vymazanie údajov zákazníkov**: Údaje zákazníkov v Customer Insights sa získavajú z pôvodných zdrojov údajov, ktoré nepochádzajú z Customer Insights. Všetky žiadosti o vymazanie GDPR musia byť vykonané v pôvodnom zdroji údajov.
- **Spravovanie žiadostí o vymazanie používateľských údajov v Customer Insights**: Údaje pre používateľov vytvára služba Customer Insights. Všetky žiadosti o vymazanie GDPR sa musia vykonať v Customer Insights.

##### <a name="manage-requests-to-delete-customer-data"></a>Spravovanie žiadostí o vymazanie údajov o zákazníkoch

Správca Customer Insights môže podľa týchto krokov odstrániť zákaznícke údaje, ktoré boli odstránené v zdroji údajov:

1. Prihlásiť sa do Dynamics 365 Customer Insights.
2. V prehľadoch cieľových skupín prejdite na **Údaje** > **Zdroje údajov**
3. Pre každý zdroj údajov v zozname, ktorý obsahuje odstránené údaje o zákazníkoch:
   1. Vyberte (...) a potom možnosť **Obnoviť**.
   2. Skontrolujte stav zdroja údajov v časti **Stav**. Začiarknutie znamená, že obnovenie bolo úspešné. Výstražný trojuholník znamená, že sa niečo pokazilo. Ak sa zobrazí výstražný trojuholník, kontaktujte D365CI@microsoft.com.

> [!div class="mx-imgBorder"]
> ![Spravovanie žiadostí o vymazanie údajov o zákazníkoch podľa GDPR.](audience-insights/media/gdpr-data-sources.png "Spravovanie žiadostí o vymazanie údajov o zákazníkoch podľa GDPR")

##### <a name="manage-delete-requests-for-user-data"></a>Spravovanie žiadostí o vymazanie údajov o používateľoch

Správca Customer Insights môže podľa týchto krokov odstrániť používateľské údaje Customer Insights:

1. Prihlásiť sa do Dynamics 365 Customer Insights.
2. V prehľadoch cieľových skupín prejdite na **Správa** > **Povolenia**.
3. Začiarknite políčka používateľa, ktorého chcete odstrániť.
4. Vyberte možnosť **Odstrániť**.

### <a name="responding-to-gdpr-data-subject-export-requests"></a>Odpovedanie na žiadosti o export dotknutých osôb pre podľa nariadenia GDPR

Ako súčasť nášho záväzku voči partnerovi s vami na vašej ceste k všeobecnému nariadeniu o ochrane údajov (GDPR) sme vyvinuli dokumentáciu, ktorá vám pomôže pripraviť sa. Táto dokumentácia popisuje kroky, ktoré dnes môžete podniknúť na podporu súladu s GDPR pri používaní prehľadov cieľových skupín.

#### <a name="manage-export-and-view-requests"></a>Spravovanie žiadostí o export a zobrazenie

Právo na prenosnosť údajov umožňuje dotknutým osobám požiadať o kópiu svojich osobných údajov v elektronickom formáte („štruktúrovaný, bežne používaný, strojovo čitateľný a interoperabilný formát“), ktorý sa môže preniesť inému prevádzkovateľovi údajov.

##### <a name="export-customer-data-tenant-admin"></a>Export údajov o zákazníkoch (správca nájomníka)

Správca nájomníka môže exportovať údaje podľa týchto krokov:

1. Pošlite e-mail na D365CI@microsoft.com, v ktorom je uvedená e-mailová adresa požadovaného zákazníka. Tím služby Customer Insights pošle e-mail na zaregistrovanú e-mailovú adresu správcu nájomníka a požiada o potvrdenie exportu údajov.
2. Potvrďte potvrdenie na exportovanie údajov pre požadovaného zákazníka.
3. Exportované údaje dostanete prostredníctvom e-mailovej adresy správcu nájomníka.

##### <a name="export-user-data-tenant-admin"></a>Export údajov o používateľoch (správca nájomníka)

1. Pošlite e-mail na D365CI@microsoft.com, v ktorom je uvedená e-mailová adresa požadovaného používateľa. Tím služby Customer Insights pošle e-mail na zaregistrovanú e-mailovú adresu správcu nájomníka a požiada o potvrdenie exportu údajov.
2. Potvrďte potvrdenie na exportovanie údajov pre požadovaného používateľa.
3. Exportované údaje dostanete prostredníctvom e-mailovej adresy správcu nájomníka.

## <a name="consent-management-preview"></a>Správa súhlasu (ukážka)

Funkcia správy súhlasu nezhromažďuje údaje používateľov priamo. Importuje a spracováva iba údaje o súhlase, ktoré poskytujú používatelia v iných aplikáciách.

Ak chcete odstrániť údaje o súhlase o konkrétnych používateľoch, odstráňte ich zo zdrojov údajov prijatých do funkcie správy súhlasu. Po obnovení zdroj údajov budú odstránené údaje vymazané aj v Centre súhlasu. Aplikácie, ktoré používajú entitu súhlasu, tiež odstránia údaje, ktoré boli odstránené zo zdroja po a [Obnoviť](audience-insights/system.md#refresh-processes). Odporúčame rýchlo obnoviť zdroje údajov po odpovedi na žiadosť dotknutej osoby, aby sa odstránili údaje používateľa zo všetkých ostatných procesov a aplikácií.


<!-- ## Engagement insights (preview)

### Deleting and exporting event data containing end user identifiable information

The following sections describe how to delete and export event data that might contain personal data.

To delete or export data:

1. Tag event properties that contain data with personal information.
2. Delete or export data associated with specific values (for example: a specified user ID).

#### Tag and update event properties

Personal data is tagged on an event property level. First, tag the properties being considered for deletion or export.

To tag an event property as containing personal information, follow these steps:

1. Open the workspace containing the event.

1. Go to **Data** > **Events** to see the list of events in the selected workspace.
  
1. Select the event you want to tag.

1. Select **Edit properties** to open the pane listing all properties of the selected event.
     
1. Select **...** and then choose **Edit** to reach the **Update property** dialog.

   ![Edit event.](engagement-insights/media/edit-event.png "Edit event")

1. In the **Update Property** window, choose **...** in the upper right corner, and then choose the **Contains EUII** box. Choose **Update** to save your changes.

   ![Save your changes.](engagement-insights/media/update-property.png "Save your changes")

   > [!NOTE]
   > Every time the event schema changes or you create a new event, it's recommended that you evaluate the associated event properties and tag or untag them as containing personal data, if necessary.

#### Delete or export tagged event data

If all event properties have been tagged appropriately as described in the previous step, an environment admin can issue a deletion request against the tagged event data.

To manage EUII deletion or export requests

1. Go to **Admin** > **Environment** > **Settings**.

1. In the **Manage end user identifiable information (EUII)** section, select **Manage EUII**.

##### Deletion

For deletion, you can enter a list of comma-separated user IDs in the **Delete end user identifiable information (EUII)** section. These IDs will then be compared with all tagged event properties of all projects in the current environment via exact string matching. 

If a property value matches one of the provided IDs, the associated event will be permanently deleted. Due to the irreversibility of this action, you must confirm the deletion after selecting **Delete**.

##### Export

The export process is identical to the deletion process when it comes to defining event property values in the **Export end user identifiable information (EUII)** section. Additionally, you'll need to provide an **Azure blob storage URL** to specify the export destination. The Azure Blob URL must include a [Shared Access Signature (SAS)](/azure/storage/common/storage-sas-overview).

After selecting **Export**, all events of the current team that contain matching tagged properties will be exported in CSV format to the export destination.

### Good practices

* Try to avoid sending any events that contain personal data.
* If you need to send events containing EUII data, limit the number of events and event properties that contain EUII data. Ideally, limit yourself to one such event.
* Make sure that as few people as possible have access to the sent personal data.
* For events containing personal data, make sure that you set one property to emit a unique identifier that can easily be linked to a specific user (for example, a user ID). This makes it easier to segregate data and to export or delete the right data.
* Only tag one property per event as containing personal data. Ideally one that only contains a unique identifier.
* Do not tag properties containing verbose values (for example, an entire request body). Engagement insights capability uses exact string matching when deciding which events to delete or export. -->

[!INCLUDE[footer-include](includes/footer-banner.md)]