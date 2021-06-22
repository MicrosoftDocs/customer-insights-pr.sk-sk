---
title: Vzťahy medzi entitami a cestami entít
description: Vytvárajte a spravujte vzťahy medzi entitami z viacerých zdrojov údajov.
ms.date: 06/01/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.openlocfilehash: d5b9566ec88096fec31d8e164a51598159ec26d4
ms.sourcegitcommit: ece48f80a7b470fb33cd36e3096b4f1e9190433a
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 06/03/2021
ms.locfileid: "6171183"
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

## <a name="view-relationships"></a>Zobrazenie vzťahov

Na stránke Vzťahy sú uvedené všetky vzťahy, ktoré boli vytvorené. Každý riadok predstavuje vzťah, ktorý obsahuje aj podrobnosti o zdrojovej entite, cieľovej entite a kardinalite. 

:::image type="content" source="media/relationships-list.png" alt-text="Zoznam vzťahov a možností na paneli akcií na stránke Vzťahy.":::

Táto stránka ponúka súbor možností pre existujúce a nové vzťahy: 
- **Nový vzťah**: [Vytvorenie vlastného vzťahu](#create-a-custom-relationship).
- **Vizualizér**: [Preskúmajte vizualizér vzťahov](#explore-the-relationship-visualizer), aby ste videli sieťový diagram existujúcich vzťahov a ich kardinalitu.
- **Spôsob filtrovania**: Vyberte typ vzťahov, ktoré sa majú zobraziť v zozname.
- **Hľadať vzťahy**: Použite textové vyhľadávanie vlastností vzťahov.

### <a name="explore-the-relationship-visualizer"></a>Preskúmanie vizualizéra vzťahov

Vizualizér vzťahov zobrazuje sieťový diagram existujúcich vzťahov medzi prepojenými entitami a ich kardinalitou.

Ak chcete prispôsobiť zobrazenie, môžete zmeniť polohu políčok ich presunutím na plátno.

:::image type="content" source="media/relationship-visualizer.png" alt-text="Snímka obrazovky sieťového diagramu vizualizátora vzťahov s prepojeniami medzi súvisiacimi entitami.":::

Dostupné možnosti: 
- **Exportovať ako obrázok**: Uložiť aktuálne zobrazenie ako obrazový súbor.
- **Zmena na vodorovné/zvislé rozloženie**: Zmena zarovnania entít a vzťahov.
- **Úprava**: Aktualizujte vlastnosti vlastných vzťahov na paneli úprav a uložte zmeny.

## <a name="manage-existing-relationships"></a>Spravovanie existujúcich vzťahov 

Na stránke Vzťahy je každý vzťah predstavovaný riadkom. 

Vyberte vzťah a jednu z nasledujúcich možností: 
 
- **Úprava**: Aktualizujte vlastnosti vlastných vzťahov na paneli úprav a uložte zmeny.
- **Odstrániť**: Odstrániť vlastné vzťahy.
- **Zobraziť**: Zobraziť vzťahy vytvorené systémom a zdedené. 

## <a name="next-step"></a>Nasledujúci krok

Systémové a vlastné vzťahy sa používajú na [vytváranie segmentov](segments.md) založených na viacerých zdrojoch údajov, ktoré už nie sú v silách.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
