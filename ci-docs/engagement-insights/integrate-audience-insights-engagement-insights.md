---
title: Vytvorte prepojenie medzi prehľadmi cieľových skupín a prehľadmi interakcií
description: Vytvorte aktívne prepojenie medzi prehľadmi cieľovej skupiny a prehľadmi interakcií a povoľte obojsmerné zdieľanie údajov.
ms.date: 09/08/2021
ms.topic: conceptual
author: mkisel
ms.author: mkisel
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 56adc206d83bc6e34a55f11383393b5ac66da531
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 02/16/2022
ms.locfileid: "8229891"
---
# <a name="create-a-link-between-audience-insights-and-engagement-insights"></a>Vytvorte prepojenie medzi prehľadmi cieľových skupín a prehľadmi interakcií

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Integrácia medzi prehľadmi interakcií a prehľadmi cieľovej skupiny prepája prostredia z oboch funkcií a umožňuje obojsmerné zdieľanie údajov medzi nimi.

Použite zjednotené profily a segmenty z prehľadov cieľovej skupiny na získanie ďalších možností analýzy v prehľadoch interakcií. Exportujte udalosti, ktoré majú vysokú obchodnú hodnotu, z prehľadov interakcií. Tieto udalosti použite na pridanie údajov do zjednotených profilov v prehľadoch cieľovej skupiny.

## <a name="prerequisites"></a>Predpoklady

- Profily prehľadov cieľovej skupiny musia byť uložené v účte Azure Data Lake Storage, ktorý vlastníte, alebo v spravovanom dátovom jazere [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro)&ndash;. 
- Prostredie vašej cieľovej skupiny by malo mať tiež priradené prostredie Dataverse. A ak toto prostredie taktiež používa Dataverse ako úložisko údajov, určite označte začiarkavacie políčko **Povoliť zdieľanie údajov** v prehľadoch cieľovej skupiny. Ďalšie informácie nájdete v časti [Vytvorenie a konfigurácia prostredia v prehľadoch cieľových skupín](../audience-insights/create-environment.md).
- Na prostredie prehľadov interakcií a prehľadov cieľovej skupiny potrebujete povolenia správcu.
- Prepojené prostredia musia byť v rovnakej geografickej oblasti.

> [!NOTE]
> - Ak je predplatné vašich prehľadov cieľovej skupiny skúšobné, ktoré používa interne spravované data lake prehľadov cieľovej skupiny, požiadajte o pomoc [pirequest@microsoft.com](mailto:pirequest@microsoft.com). 
> - Ak vaše prostredie pre prehľady cieľovej skupiny používa vaše vlastné Azure Data Lake Storage na ukladanie údajov, musíte do svojho účtu úložiska pridať objekt služby Azure prehľadov cieľovej skupiny. Podrobnosti nájdete na [Pripojenie k účtu Azure Data Lake Storage pomocou objektu služby Azure pre prehľady cieľovej skupiny](../audience-insights/connect-service-principal.md). 


## <a name="create-an-environment-link"></a>Vytvorenie odkazu na prostredie

Odkaz na prostredie môžete vytvoriť aktualizáciou nastavenia **Správca** > **Prostredie** v prehľadoch interakcií.

**Nadviazanie aktívneho prepojenia medzi prehľadmi cieľových skupín a prehľadmi interakcií**

1. Na stránke **Správca prostredia** vyberte kartu **Prepojiť prostredia**.

    :::image type="content" source="media/integrate1.png" alt-text="Nastavenie prostredia.":::

1. Vyberte **Nastaviť prostredia** v ľavom hornom rohu alebo v spodnej časti obrazovky.

     :::image type="content" source="media/integrate2.png" alt-text="Výber prostredia s prehľadmi cieľovej skupiny.":::

1. Vyberte prostredie s prehľadmi cieľovej skupiny a potom vyberte **Ďalej** na dokončenie. Teraz si môžete vybrať voliteľné funkcie pre prepojené prostredia.
 
## <a name="enable-audience-insights-unified-profiles-attributes-and-segments"></a>Povoliť atribúty a segmenty prehľadov cieľových skupín zjednotených profilov

Po prepojení prostredí môžete vybrať voliteľné funkcie pre prepojené prostredia. Tieto funkcie umožňujú zjednotené atribúty profilu a segmenty z prehľadov cieľovej skupiny pre interaktívnu analýzu údajov o zákazníkoch.

> [!IMPORTANT]
> Aby sa segmenty prehľadov cieľovej skupiny zobrazovali v prehľadoch interakcií, musíte najskôr [spustiť procesy zlúčenia a nadväzujúce procesy](../audience-insights/merge-entities.md). Následné procesy sú dôležité, pretože generujú jedinečnú tabuľku, ktorá pripravuje segmenty prehľadov cieľovej skupiny na zdieľanie s prehľadmi interakcií. (Ak je naplánovaná aktualizácia systému, bude automaticky zahŕňať následné procesy.)

**Analýza webových údajov v prehľadoch interakcií**

1. Na stránke **Správca prostredia** zapnite prepínač **Zdieľajte údaje z prehľadov cieľovej skupiny s prehľadmi interakcií** a potom vyberte **Ďalej**.

    :::image type="content" source="media/integrate4.png" alt-text="Výber funkcií.":::

1. Vyberte atribúty zjednotených profilov, ktoré sa stanú dimenziami v prehľadoch interakcií. (Nie všetky atribúty sú užitočnými dimenziami. Nie je napríklad pravdepodobné, že by ste potrebovali **Meno** alebo **Priezvisko** ako atribút na analýzu udalostí na vašich webových stránkach.)

    :::image type="content" source="media/integrate5.png" alt-text="Usporiadať dimenzie.":::

   >[!NOTE]
   > Všetky atribúty profilu prehľadov cieľovej skupiny, ktoré predstavujú identifikátory (ako napr. **ID** a **alternatívne ID**) sú odfiltrované z dostupných atribútov a stanú sa dimenziami v prehľadoch interakcií.

1. Keď ste skončili s výberom atribútov, vyberte **Ďalej**.
1. Pridajte používateľov, ktorí si môžu v prehľadoch interakcií pozrieť dimenzie profilu a segmenty prehľadov cieľovej skupiny.

    :::image type="content" source="media/integrate6.png" alt-text="Spravovanie prístupu k údajom zákazníka.":::

   > [!IMPORTANT]
   > Ak v tomto kroku explicitne nepridáte používateľov, údaje budú pred používateľmi prehľadov interakcií skryté.
   > Aby sa segmenty prehľadov cieľovej skupiny zobrazovali v prehľadoch interakcií, musíte najskôr [spustiť procesy zlúčenia a nadväzujúce procesy](../audience-insights/merge-entities.md). Následné procesy sú dôležité, pretože generujú jedinečnú tabuľku, ktorá pripravuje segmenty prehľadov cieľovej skupiny na zdieľanie s prehľadmi interakcií. (Ak je naplánovaná aktualizácia systému, bude automaticky zahŕňať následné procesy.)

1. Skontrolujte svoj výber a potom vyberte **Skončiť**.

    :::image type="content" source="media/integrate7.png" alt-text="Skontrolujte nastavenia údajov o zákazníkoch.":::

## <a name="export-refined-events-to-audience-insights"></a>Exportujte spresnené udalosti v prehľadoch cieľových skupín

Po vytvorení prepojenia medzi prostrediami môžete exportovať prepracované udalosti z prehľadov interakcií do prehľadov cieľovej skupiny a prijať ich ako nový zdroj údajov. 

Ak chcete získať ďalšie informácie, navštívte stránku [Integrujte webové údaje z prehľadov interakcií s prehľadmi cieľovej skupiny](../audience-insights/integrate-engagement-insights.md).

<!--
## Share engagement insights refined events with audience insights

After you create a link between environments, a new option becomes available for you to share [refined events](refined-events.md) with audience insights.

Consider the following when creating refined events for audience insights: 

- Provide a meaningful name for the refined event. It will be used as an activity name in audience insights.
- Select at least the following properties to create an activity in audience insights: 
    - Signal.Action.Name indicates the activity details.
    - Signal.User.Id maps with the customer ID.
    - Signal.View.Uri is a web address as a basis for segments or measures.
    - Signal.Export.Id is a primary key for events.
    - Signal.Timestamp determines the date and time for the activity.

To share refined events:

1. From the engagement insights menu, select **Data** and then select the **Events** tab.
2. On the **Action** menu, select **Share as activity**.

    :::image type="content" source="media/integrate8.png" alt-text="Data shared events settings.":::

3. You can view and stop actively shared events on the **Export and Sharing** tab.
4. -- per Michael K, we need a mock here (Mukesh needs to update to reflect what happens in AUI once a user shares a refined event (i.e. no longer AUI, data wrangler needs to go discover data in the storage, the shared event is available as a DS and entity, correct?)

### Attach refined events shared as activities to unified profiles in audience insights

You can bring customer web activity data from engagement insights into audience insights. In addition to transactional, demographic, or behavioral data, you can view activities on the web in unified customer profiles. You can then use these profiles to get insights such as segments, measures, and predictions for audience activation.

Follow the steps in [data unification](../audience-insights/data-unification.md) to map, match, and merge website authentication information to unified profiles in audience insights.

You can also share refined events that are now available in audience insights, identified as data sources and entities. 

Next, you can relate event data from engagement insights as unified activities in customer profiles.

### Relate refined event data as an activity of a customer profile

After unifying the data, you can configure the activity for the customer profile. For more information, go to [Customer activities](../audience-insights/activities.md).

:::image type="content" source="media/web-event-activity.png" alt-text="Activities page with expanded Edit activity pane.":::

Next, configure the new activity by using mapping elements: 

- **Primary Key**: Signal.Export.Id, a unique ID that is available for every event record in engagement insights. This property is automatically generated.

- **Timestamp**: Signal.Timestamp in the event property.

- **Event**: Signal.Name, the event name that you want to track.

- **Web address**: Signal.View.Uri that refers to the URI of the page that created the event.

- **Details**: Signal.Action.Name to represent the information to associate with the event. The selected property in this case indicates that the event is for email promotion.

- **Activity type**: In this example, we choose the existing activity type WebLog. This selection is a useful filter option to run prediction models or create segments based on this activity type.

- **Set up relationship**: This important setting ties the activity to existing customer profiles. **Signal.User.Id** is the identifier configured in the SDK to be collected. It relates to the user ID in other data sources that are configured in audience insights. 

This example configures the relationship between Signal.User.Id and RetailCustomers:CustomerRetailId, which is the primary key that was identified in the map step of the data unification process.

After processing the activities, you can review customer records and open a customer card to see activities from engagement insights in the timeline. 

> [!TIP]
> To find a customer ID that has an engagement insights activity, go to **Entities** and preview the data for the UnifiedActivity entity. **ActivityTypeDisplay = WebLog** contains the engagement insights activity configured in the preceding example. Copy the customer ID for one of those records and search<!--note from editor: Edit okay? I couldn't quite follow this.-- > for that ID on the **Customers** page.

--> 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
