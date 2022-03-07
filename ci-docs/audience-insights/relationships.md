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
ms.openlocfilehash: db8822aa9e89afb9dc16428af6ca202de789ba1c
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 02/25/2022
ms.locfileid: "8355724"
---
# <a name="relationships-between-entities"></a>Vzťahy medzi entitami

Vzťahy spájajú entity a definujú graf vašich údajov, keď entity zdieľajú spoločný identifikátor, cudzí kľúč. Tento cudzí kľúč je možné odkazovať z jednej entity na druhú. Pripojené entity vám umožňujú definovať segmenty a miery na základe viacerých zdrojov údajov.

Existujú tri typy vzťahov: 
- Needitovateľné systémové vzťahy, ktoré vytvoril systém ako súčasť procesu zjednotenia údajov
- Needitovateľné zdedené vzťahy, ktoré sa vytvárajú automaticky z prijímania zdrojov údajov 
- Editovateľné vlastné vzťahy, vytvorené a nakonfigurované používateľmi

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

1. V prehľadoch cieľových skupín prejdite na **Údaje** > **Vzťahy**.

2. Vyberte **Nový vzťah**.

3. Na table **Nový vzťah** zadajte nasledovné informácie:

   :::image type="content" source="media/relationship-add.png" alt-text="Bočná tabla nového vzťahu s prázdnymi vstupnými poľami.":::

   - **Názov vzťahu**: Názov, ktorý odráža účel vzťahu. Príklad: CustomerToSupportCase.
   - **Popis**: Popis vzťahu.
   - **Zdrojová entita**: Entita, ktorá sa vo vzťahu používa ako zdroj. Príklad: SupportCase.
   - **Cieľová entita**: Entita, ktorá sa vo vzťahu používa ako cieľ. Príklad: Zákazník.
   - **Kardinalita zdroja**: Zadajte kardinalitu zdrojovej entity. Kardinalita popisuje počet možných prvkov v množine. Vždy súvisí s cieľovou kardinalitou. Môžete si vybrať **Jeden** a **Mnoho**. Podporované sú iba vzťahy „mnoho k jednému“ a „jeden k jednému“.  
     - Mnohé k jednému: Na jeden cieľový záznam sa môže vzťahovať viac zdrojových záznamov. Príklad: Viaceré prípady podpory od jedného zákazníka.
     - Jeden k jednému: Jeden zdrojový záznam sa týka jedného cieľového záznamu. Príklad: Jedno vernostné ID pre jedného zákazníka.

     > [!NOTE]
     > Vzťahy typu mnohé k mnohým je možné vytvoriť pomocou dvoch vzťahov typu mnohé k jednému a prepojovacej entity, ktorá spája zdrojovú entitu a cieľovú entitu.

   - **Kardinalita cieľa**: Vyberte kardinalitu záznamov cieľovej entity. 
   - **Pole zdrojového kľúča**: Pole cudzieho kľúča v zdrojovej entite. Príklad: SupportCase môže používať CaseID ako pole cudzieho kľúča.
   - **Pole cieľového kľúča**: Pole kľúča cieľovej entity. Príklad Zákazník môže použiť kľúčové pole **CustomerID**.

4. Výberom položky **Uložiť** vytvorte vlastný vzťah.

## <a name="set-up-account-hierarchies"></a>Nastavenie hierarchií obchodných vzťahov

Prostredia, ktoré sú nakonfigurované na používanie firemných obchodných vzťahov ako primárnej cieľovej skupiny môžu konfigurovať hierarchie obchodných vzťahov pre súvisiace obchodné podnikové vzťahy. Napríklad spoločnosť, ktorá má oddelené obchodné jednotky. 

Organizácie vytvárajú hierarchie obchodných vzťahov, aby lepšie spravovali obchodné vzťahy a ich vzájomné vzťahy. Funkcia prehľadov cieľových skupín podporuje hierarchie obchodných vzťahov nadradený/podradený, ktoré už v prijatých údajoch o zákazníkoch existujú. Napríklad obchodné vzťahy z Dynamics 365 Sales. Tieto hierarchie je možné nakonfigurovať na stránke **Vzťahy** v prehľadoch publika na karte hierarchia obchodného vzťahu.

1. Prejdite na **Údaje** > **Vzťahy**.
1. Vyberte kartu **Hierarchia obchodných vzťahov**.
1. Vyberte **Nová hierarchia obchodných vzťahov**. 
1. Na table **Hierarchia obchodných vzťahov** zadajte názov hierarchie. Systém vytvorí názov pre výstupnú entitu. Môžete zmeniť názov entity názvu výstupu.
1. Vyberte entitu, ktorá obsahuje hierarchiu vášho obchodného vzťahu. Obvykle je to v tej istej entite, ktorá obsahuje obchodné vzťahy.
1. Vyberte položku **ID obchodného vzťahu** a **ID nadradeného obchodného vzťahu** z vybranej entity 
1. Vyberte **Uložiť**, použite nastavenia a dokončite hierarchiu obchodného vzťahu.

## <a name="view-relationships"></a>Zobrazenie vzťahov

Na stránke Vzťahy sú uvedené všetky vzťahy, ktoré boli vytvorené. Každý riadok predstavuje vzťah, ktorý obsahuje aj podrobnosti o zdrojovej entite, cieľovej entite a kardinalite. 

:::image type="content" source="media/relationships-list.png" alt-text="Zoznam vzťahov a možností na paneli akcií na stránke Vzťahy.":::

Táto stránka ponúka súbor možností pre existujúce a nové vzťahy: 
- **Nový vzťah**: [Vytvorenie vlastného vzťahu](#create-a-custom-relationship).
- **Vizualizér**: [Preskúmajte vizualizér vzťahov](#explore-the-relationship-visualizer), aby ste videli sieťový diagram existujúcich vzťahov a ich kardinalitu.
- **Spôsob filtrovania**: Vyberte typ vzťahov, ktoré sa majú zobraziť v zozname.
- **Hľadať vzťahy**: Použite textové vyhľadávanie vlastností vzťahov.

### <a name="explore-the-relationship-visualizer"></a>Preskúmanie vizualizéra vzťahov

Vizualizér vzťahov zobrazuje sieťový diagram existujúcich vzťahov medzi prepojenými entitami a ich kardinalitou. Vizualizuje aj postup vzťahu.

Ak chcete prispôsobiť zobrazenie, môžete zmeniť polohu políčok ich presunutím na plátno.

:::image type="content" source="media/relationship-visualizer.png" alt-text="Snímka obrazovky sieťového diagramu vizualizátora vzťahov s prepojeniami medzi súvisiacimi entitami.":::

Dostupné možnosti: 
- **Exportovať ako obrázok**: Uložiť aktuálne zobrazenie ako obrazový súbor.
- **Zmena na vodorovné/zvislé rozloženie**: Zmena zarovnania entít a vzťahov.
- **Úprava**: Aktualizujte vlastnosti vlastných vzťahov na paneli úprav a uložte zmeny.

## <a name="relationship-paths"></a>Cesty vyjadrujúce vzťah

Cesta vyjadrujúca vzťah popisuje entity, ktoré sú prepojené so vzťahmi medzi zdrojovou entitou a cieľovou entitou. Používa sa pri vytváraní segmentu alebo miery, ktorá obsahuje iné entity ako entitu zjednoteného profilu, a existuje niekoľko možností, ako dosiahnuť entitu zjednoteného profilu. 

Cesta vyjadrujúca vzťah informuje systém, cez ktorý vzťah má pristupovať k entite zjednoteného profilu. Rôzne postupy vzťahov môžu priniesť rôzne výsledky.

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

*Viacskokový vzťah* je *nepriamy vzťah*, ktorý umožňuje pripojiť zdrojovú entitu k cieľovej entite prostredníctvom jednej alebo viacerých ďalších sprostredkovateľských entít.

Ak sa napríklad entita aktivity s názvom *eCommerce_eCommercePurchasesWest* pripája k sprostretkovateľskej entite s názvom *eCommerce_eCommercePurchasesEast* a potom sa pripojí k cieľovej entite s názvom *eCommerce_eCommerceContacts*, ide o viacskokový vzťah.

:::image type="content" source="media/multi-hop_relationship.png" alt-text="Zdrojová entita sa pripája priamo k cieľovej entite so sprostretkovateľskou entitou.":::

### <a name="multi-hop-multi-path-relationship"></a>Viacskokový vzťah, vzťah s viacerými postupmi

Viacskokový vzťah a vzťah s viacerými postupmi je možné použiť spoločne na vytvorenie **viacskokového vzťahu, vzťahu s viacerými postupmi**. Tento špeciálny typ kombinuje funkcie **viacskokového vzťahu** a **vzťahu s viacerými postupmi**. Umožňuje pripojiť sa k viac ako jednej cieľovej entite pri použití sprostredkovateľských entít.

Ak sa napríklad entita aktivity s názvom *eCommerce_eCommercePurchasesWest* pripája k sprostretkovateľskej entite s názvom *eCommerce_eCommercePurchasesEast* a potom sa pripojí k dvom cieľovým entitám *eCommerce_eCommerceContacts* a *loyaltyScheme_loyCustomers*, ide o viacskokový vzťah, vzťah s viacerými postupmi.

:::image type="content" source="media/multi-hop_multi-path_relationship.png" alt-text="Zdrojová entita sa pripája priamo k jednej cieľovej entite a pripája sa k inej cieľovej entite prostredníctvom sprostredkovateľskej entity.":::

## <a name="manage-existing-relationships"></a>Spravovanie existujúcich vzťahov 

Na stránke Vzťahy je každý vzťah predstavovaný riadkom. 

Vyberte vzťah a jednu z nasledujúcich možností: 
 
- **Úprava**: Aktualizujte vlastnosti vlastných vzťahov na paneli úprav a uložte zmeny.
- **Odstrániť**: Odstrániť vlastné vzťahy.
- **Zobraziť**: Zobraziť vzťahy vytvorené systémom a zdedené. 

## <a name="next-step"></a>Nasledujúci krok

Systémové a vlastné vzťahy sa používajú na [vytváranie segmentov](segments.md) a [opatrení](measures.md) na základe viacerých zdrojov údajov, ktoré už nie sú vypnuté.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
