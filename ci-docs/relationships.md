---
title: Vzťahy medzi entitami a cestami entít
description: Vytvárajte a spravujte vzťahy medzi entitami z viacerých zdrojov údajov.
ms.date: 09/27/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: CadeSanthaMSFT
ms.author: cadesantha
manager: shellyha
searchScope:
- ci-semantic-mapping
- ci-entities
- ci-relationships
- ci-activities
- ci-activities-wizard
- ci-measures
- ci-segments
- ci-segment-builder
- ci-measure-builder
- ci-measure-template
- ci-permissions
- customerInsights
ms.openlocfilehash: e622e5fa0b5738e31db1c668d95312adbc4f7d36
ms.sourcegitcommit: ad74ace653db9a25fce4343adef7db1c9b0d8904
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 07/21/2022
ms.locfileid: "9183591"
---
# <a name="relationships-between-entities-and-entity-paths"></a>Vzťahy medzi entitami a cestami entít

Vzťahy spájajú entity a definujú graf vašich údajov, keď entity zdieľajú spoločný identifikátor, cudzí kľúč. Tento cudzí kľúč je možné odkazovať z jednej entity na druhú. Pripojené entity vám umožňujú definovať segmenty a miery na základe viacerých zdrojov údajov.

Existujú tri typy vzťahov: 
- Neupraviteľné systémové vzťahy vytvára systém ako súčasť procesu zjednocovania údajov
- Neupraviteľné zdedené vzťahy sa vytvárajú automaticky z prijímania zdrojov údajov
- Upraviteľné vlastné vzťahy vytvárajú a konfigurujú používatelia

## <a name="non-editable-system-relationships"></a>Needitovateľné systémové vzťahy

Počas zjednotenia údajov sa systémové vzťahy vytvárajú automaticky na základe inteligentného párovania. Tieto vzťahy pomáhajú priraďovať záznamy profilu zákazníka k zodpovedajúcim záznamom. Nasledujúci diagram ilustruje vytvorenie troch systémových vzťahov. Entita zákazníka sa páruje s inými entitami, aby sa vytvorila zjednotená entita *Zákazník*.

:::image type="content" source="media/relationships-entities-merge.png" alt-text="Diagram s cestami vzťahov pre entitu zákazníka s troma vzťahmi 1-n.":::

- **Vzťah *CustomerToContact*** bol vytvorený medzi entitou *Zákazník* a entitou *Kontakt*. Entita *Zákazník* získa kľúčové pole **Contact_contactID**, ktoré sa bude vzťahovať na kľúčové pole entity *Kontakt* **contactID**.
- **Vzťah *CustomerToAccount*** bol vytvorený medzi entitou *Zákazník* a entitou *Obchodný vzťah*. Entita *Zákazník* získa kľúčové pole **Account_accountID**, ktoré sa bude vzťahovať na kľúčové pole entity *Obchodný vzťah* **accountId**.
- **Vzťah *CustomerToWebAccount*** bol vytvorený medzi entitou *Zákazník* a entitou *WebAccount*. Entita *Zákazník* získa kľúčové pole **WebAccount_webaccountID**, ktoré sa bude vzťahovať na kľúčové pole entity *WebAccount* **webaccountId**.

## <a name="non-editable-inherited-relationships"></a>Needitovateľné zdedené vzťahy

Počas procesu prijímania údajov systém kontroluje existujúce vzťahy v zdrojoch údajov. Ak neexistuje žiadny vzťah, systém ich automaticky vytvorí. Tieto vzťahy sa tiež používajú v následných procesoch.

## <a name="create-a-custom-relationship"></a>Vytvorenie vlastného vzťahu

Vzťah pozostáva zo *zdrojovej entity*, ktorá obsahuje cudzí kľúč a z *cieľovej entity*, na ktorú cudzí kľúč zdrojovej entity ukazuje. 

1. Prejdite na **Údaje** > **Vzťahy**.

2. Vyberte **Nový vzťah**.

3. Na table **Nový vzťah** zadajte nasledovné informácie:

   :::image type="content" source="media/relationship-add.png" alt-text="Bočná tabla nového vzťahu s prázdnymi vstupnými poľami.":::

   - **Názov vzťahu**: Názov, ktorý odráža účel vzťahu. Príklad: CustomerToSupportCase.
   - **Popis**: Popis vzťahu.
   - **Zdrojová entita**: Entita, ktorá sa vo vzťahu používa ako zdroj. Príklad: SupportCase.
   - **Cieľová entita**: Entita, ktorá sa vo vzťahu používa ako cieľ. Príklad: Zákazník.
   - **Kardinalita zdroja** : Mohutnosť zdrojovej entity. Kardinalita popisuje počet možných prvkov v množine. Vždy súvisí s cieľovou kardinalitou. Môžete si vybrať **Jeden** a **Mnoho**. Podporované sú iba vzťahy „mnoho k jednému“ a „jeden k jednému“.  
     - Mnohé k jednému: Na jeden cieľový záznam sa môže vzťahovať viac zdrojových záznamov. Príklad: Viaceré prípady podpory od jedného zákazníka.
     - Jeden k jednému: Jeden zdrojový záznam sa týka jedného cieľového záznamu. Príklad: Jedno vernostné ID pre jedného zákazníka.

     > [!NOTE]
     > Vzťahy typu mnohé k mnohým je možné vytvoriť pomocou dvoch vzťahov typu mnohé k jednému a prepojovacej entity, ktorá spája zdrojovú entitu a cieľovú entitu.

   - **Cieľová kardinalita** : Mohutnosť záznamov cieľovej entity.
   - **Pole zdrojového kľúča** : Pole cudzieho kľúča v zdrojovej entite. Príklad: SupportCase používa **CaseID** ako pole cudzieho kľúča.
   - **Cieľové kľúčové pole** : Kľúčové pole cieľovej entity. Príklad: Zákazník používa **CustomerID** ako kľúčové pole.

4. Výberom položky **Uložiť** vytvorte vlastný vzťah.

## <a name="set-up-account-hierarchies"></a>Nastavenie hierarchií obchodných vzťahov

Prostredia, ktoré sú nakonfigurované na používanie obchodných účtov ako primárnej cieľovej skupiny, môžu konfigurovať hierarchie účtov pre súvisiace obchodné účty. Napríklad spoločnosť, ktorá má oddelené obchodné jednotky.

Organizácie vytvárajú hierarchie obchodných vzťahov, aby lepšie spravovali obchodné vzťahy a ich vzájomné vzťahy. Customer Insights podporuje hierarchie nadradených a podradených účtov, ktoré už existujú v prijatých zákazníckych údajoch. Napríklad obchodné vzťahy z Dynamics 365 Sales. Tieto hierarchie je možné konfigurovať na **Vzťahy** stránku.

1. Prejdite na **Údaje** > **Vzťahy**.
1. Vyberte kartu **Hierarchia obchodných vzťahov**.
1. Vyberte **Nová hierarchia obchodných vzťahov**.
1. Na table **Hierarchia obchodných vzťahov** zadajte názov hierarchie. Systém vytvorí názov pre výstupnú entitu, ale môžete ho zmeniť.
1. Vyberte entitu, ktorá obsahuje hierarchiu vášho obchodného vzťahu. Obvykle je to v tej istej entite, ktorá obsahuje obchodné vzťahy.
1. Vyberte **UID účtu** a **UID rodiča** z vybranej entity.
1. Vyberte **Uložiť** na dokončenie hierarchie účtov.

## <a name="manage-existing-relationships"></a>Spravovanie existujúcich vzťahov

Choďte na **Vzťahy** zobrazíte všetky vzťahy, ktoré boli vytvorené, ich zdrojovú entitu, cieľovú entitu a mohutnosť.

:::image type="content" source="media/relationships-list.png" alt-text="Zoznam vzťahov a možností na paneli akcií na stránke Vzťahy.":::

Použi **Triediť podľa** alebo **Hľadajte vzťahy** možnosti lokalizácie konkrétneho vzťahu. Ak chcete zobraziť sieťový diagram existujúcich vzťahov a ich mohutnosti, vyberte [**Vizualizér**](#explore-the-relationship-visualizer).

Ak chcete zobraziť dostupné akcie, vyberte vzťah:
- **Úprava**: Aktualizujte vlastnosti vlastných vzťahov na paneli úprav a uložte zmeny.
- **Odstrániť**: Odstrániť vlastné vzťahy.
- **Zobraziť**: Zobraziť vzťahy vytvorené systémom a zdedené.

### <a name="explore-the-relationship-visualizer"></a>Preskúmanie vizualizéra vzťahov

Vizualizér vzťahov zobrazuje sieťový diagram existujúcich vzťahov medzi prepojenými entitami a ich kardinalitou. Vizualizuje aj postup vzťahu.

:::image type="content" source="media/relationship-visualizer.png" alt-text="Snímka obrazovky sieťového diagramu vizualizátora vzťahov s prepojeniami medzi súvisiacimi entitami.":::

Ak chcete prispôsobiť zobrazenie, môžete zmeniť polohu políčok ich presunutím na plátno. Medzi ďalšie možnosti patrí: 
- **Exportovať ako obrázok**: Uložiť aktuálne zobrazenie ako obrazový súbor.
- **Zmena na vodorovné/zvislé rozloženie**: Zmena zarovnania entít a vzťahov.
- **Úprava**: Aktualizujte vlastnosti vlastných vzťahov na paneli úprav a uložte zmeny.

## <a name="relationship-paths"></a>Cesty vyjadrujúce vzťah

Cesta vyjadrujúca vzťah popisuje entity, ktoré sú prepojené so vzťahmi medzi zdrojovou entitou a cieľovou entitou. Používa sa pri vytváraní segmentu alebo miery, ktorá zahŕňa entity iné ako entita zjednoteného profilu a existuje viacero možností, ako dosiahnuť entitu zjednoteného profilu. Rôzne postupy vzťahov môžu priniesť rôzne výsledky.

Napríklad entita *eCommerce_eCommercePurchases* má s entitou jednotného profilu *Zákazník* nasledujúce vzťahy:

- eCommerce_eCommercePurchases > Zákazník
- eCommerce_eCommercePurchases > eCommerce_eCommerceContacts > POS_posPurchases > Zákazník
- eCommerce_eCommercePurchases > eCommerce_eCommerceContacts > POS_posPurchases > loyaltyScheme_loyCustomers > Zákazník

Cesta vyjadrujúca vzťah určuje, ktoré entity môžete použiť pri vytváraní pravidiel pre miery alebo segmenty. Výber možnosti s najdlhším postupom vzťahu pravdepodobne prinesie menej výsledkov, pretože zodpovedajúce záznamy musia byť súčasťou všetkých entít. V tomto prípade musí mať zákazník zakúpený tovar prostredníctvom elektronického obchodu (eCommerce_eCommercePurchases) v mieste predaja (POS_posPurchases) a zúčastniť sa nášho vernostného programu (loyaltyScheme_loyCustomers). Pri výbere prvej možnosti by ste pravdepodobne získali viac výsledkov, pretože zákazníci musia existovať iba v jednej ďalšej entite.

### <a name="direct-relationship"></a>Priamy vzťah

Vzťah je klasifikovaný ako a **priamy vzťah** keď sa zdrojová entita týka cieľovej entity iba s jedným vzťahom.

Ak sa napríklad entita aktivity s názvom *eCommerce_eCommercePurchases* pripája k cieľovej entite *eCommerce_eCommerceContacts* iba prostredníctvom *ContactId*, ide o priamy vzťah.

:::image type="content" source="media/direct_Relationship.png" alt-text="Zdrojová entita sa pripája priamo k cieľovej entite.":::

#### <a name="multi-path-relationship"></a>Vzťah s viacerými postupmi

**Vzťah s viacerými postupmi** je špeciálny typ priameho vzťahu, ktorý spája zdrojovú entitu s viac ako jednou cieľovou entitou.

Ak sa napríklad entita aktivity s názvom *eCommerce_eCommercePurchases* týka dvoch cieľových entít, *eCommerce_eCommerceContacts* a *loyaltyScheme_loyCustomers*, ide o vzťah s viacerými postupmi.

:::image type="content" source="media/multi-path_relationship.png" alt-text="Zdrojová entita sa viackrát prepojí priamo s viac ako jednou cieľovou entitou prostredníctvom viacskokového vzťahu.":::

### <a name="indirect-relationship"></a>Nepriamy vzťah

Vzťah je klasifikovaný ako **nepriamy vzťah**, keď sa zdrojová entita týka jednej alebo viacerých ďalších entít predtým, ako sa týka cieľovej entity.

#### <a name="multi-hop-relationship"></a>Viacskokový vzťah

**Viacskokový vzťah** je *nepriamy vzťah*, ktorý umožňuje pripojiť zdrojovú entitu k cieľovej entite prostredníctvom jednej alebo viacerých ďalších sprostredkovateľských entít.

Ak sa napríklad entita aktivity s názvom *eCommerce_eCommercePurchasesWest* pripája k sprostretkovateľskej entite s názvom *eCommerce_eCommercePurchasesEast* a potom sa pripojí k cieľovej entite s názvom *eCommerce_eCommerceContacts*, ide o viacskokový vzťah.

:::image type="content" source="media/multi-hop_relationship.png" alt-text="Zdrojová entita sa pripája priamo k cieľovej entite so sprostretkovateľskou entitou.":::

### <a name="multi-hop-multi-path-relationship"></a>Viacskokový vzťah, vzťah s viacerými postupmi

Viacskokový vzťah a vzťah s viacerými postupmi je možné použiť spoločne na vytvorenie **viacskokového vzťahu, vzťahu s viacerými postupmi**. Tento špeciálny typ kombinuje funkcie **viacskokového vzťahu** a **vzťahu s viacerými postupmi**. Umožňuje pripojiť sa k viac ako jednej cieľovej entite pri použití sprostredkovateľských entít.

Ak sa napríklad entita aktivity s názvom *eCommerce_eCommercePurchasesWest* pripája k sprostretkovateľskej entite s názvom *eCommerce_eCommercePurchasesEast* a potom sa pripojí k dvom cieľovým entitám *eCommerce_eCommerceContacts* a *loyaltyScheme_loyCustomers*, ide o viacskokový vzťah, vzťah s viacerými postupmi.

:::image type="content" source="media/multi-hop_multi-path_relationship.png" alt-text="Zdrojová entita sa pripája priamo k jednej cieľovej entite a pripája sa k inej cieľovej entite prostredníctvom sprostredkovateľskej entity.":::

## <a name="next-step"></a>Ďalší krok

Systémové a vlastné vzťahy sa používajú na [vytváranie segmentov](segments.md) a [opatrení](measures.md) na základe viacerých zdrojov údajov, ktoré už nie sú vypnuté.

[!INCLUDE [footer-include](includes/footer-banner.md)]
