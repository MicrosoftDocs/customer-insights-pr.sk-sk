---
title: Vytváranie a spravovanie mier
description: Definujte miery na analýzu a zobrazovanie výkonnosti vášho podnikania.
ms.date: 02/02/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: wameng
manager: shellyha
ms.openlocfilehash: 5bcee3b4c51880740715575b18fd7a4dbf87e6d0
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269947"
---
# <a name="define-and-manage-measures"></a>Definovanie a spravovanie mier

Miery vám pomôžu lepšie pochopiť správanie zákazníkov a výkonnosť podnikania načítaním relevantných hodnôt zo [zjednotených profilov](data-unification.md). Napríklad firma chce vidieť *celkové výdavky na zákazníka* a pochopiť tak históriu nákupu jednotlivých zákazníkov. Alebo zmerať *celkový predaj spoločnosti* a porozumieť agregovaným výnosom v celom podnikaní.  

Miery sa vytvárajú pomocou nástroja na tvorbu mier, platformy na dotazovanie údajov s rôznymi operátormi a jednoduchými možnosťami mapovania. Umožňujú vám filtrovať údaje, zoskupovať výsledky, zisťovať [cesty vzťahov medzi entitami](relationships.md) a zobrazovať ukážku výstupu.

Použite nástroj na tvorbu mier na plánovanie obchodných aktivít dotazovaním na údaje o zákazníkoch a získavaním prehľadov. Napríklad vytvorenie miery *celkové výdavky na zákazníka* a *celková návratnosť na zákazníka* pomáha identifikovať skupinu zákazníkov s vysokými výdavkami, ale s vysokou návratnosťou. Môžete [vytvoriť segment](segments.md) na podporu ďalších najvhodnejších akcií. 

## <a name="create-a-measure"></a>Vytvorenie miery

Táto sekcia vás prevedie vytvorením novej miery od nuly. Môžete vytvoriť mieru s atribútmi údajov z údajových entít, ktoré majú nastavený vzťah na spojenie s entitou Zákazník. 

1. V prehľadoch cieľových skupín prejdite na **Miery**.

1. Vyberte **Nové**.

1. Vyberte **Upraviť názov** a zadajte **Názov** miery. 
   > [!NOTE]
   > Ak má vaša nová konfigurácia mier iba dve polia, napríklad CustomerID a jeden výpočet, výstup sa pridá ako nový stĺpec do systémovo generovanej entity s názvom Customer_Measure. Hodnotu miery uvidíte v zjednotenom profile zákazníka. Ostatné miery vytvoria svoje vlastné entity.

1. V konfiguračnej oblasti vyberte agregačnú funkciu z rozbaľovacej ponuky **Vyberte funkciu**. Medzi agregačné funkcie patria: 
   - **Sum**
   - **Priemer**
   - **Obchodný vzťah**
   - **Počet jedinečných**
   - **Max**
   - **Minimum**
   - **Prvé**: berie prvú hodnotu dátového záznamu
   - **Posledné**: berie poslednú hodnotu, ktorá bola pridaná do dátového záznamu

   :::image type="content" source="media/measure-operators.png" alt-text="Operátory výpočtov miery.":::

1. Vyberte **Pridať atribút** a vyberte údaje, ktoré potrebujete na vytvorenie tejto miery.
   
   1. Vyberte karty **Atribúty**. 
   1. Dátová entita: Vyberte entitu, ktorá obsahuje atribút, ktorý chcete merať. 
   1. Atribút údajov: Vyberte atribút, ktorý chcete použiť vo funkcii agregácie na výpočet miery. Môžete vybrať iba jeden atribút naraz.
   1. Atribút údajov môžete vybrať aj z existujúcej miery výberom karty **Miery**. Alebo môžete vyhľadať názov entity alebo miery. 
   1. Vyberte **Pridať** na pridanie vybraného atribútu k miere.

   :::image type="content" source="media/measure-attribute-selection.png" alt-text="Vyberte atribút, ktorý sa má použiť pri výpočtoch.":::

1. Ak chcete vytvoriť zložitejšie miery, môžete pridať ďalšie atribúty alebo použiť matematické operátory svojej funkcie miery.

   :::image type="content" source="media/measure-math-operators.png" alt-text="Vytvorte komplexné miery s matematickými operátormi.":::

1. Ak chcete pridať filtre, vyberte **Filtrovať** v konfiguračnej oblasti. 
  
   1. V sekcii **Pridať atribút** tably **Filtre** vyberte atribút, ktorý chcete použiť na vytvorenie filtrov.
   1. Nastavte operátory filtra tak, aby definovali filter pre každý vybraný atribút.
   1. Vyberte **Použiť** na pridanie filtrov k miere.

1. Ak chcete pridať dimenzie, vyberte **Dimenzie** v konfiguračnej oblasti. Dimenzie sa zobrazia ako stĺpce v entite výstupu miery.
   1. Vyberte **Upraviť dimenzie**, ak chcete pridať atribúty údajov, podľa ktorých chcete zoskupiť namerané hodnoty. Napríklad mesto alebo pohlavie. V predvolenom nastavení je vybraná dimenzia *CustomerID* na vytvorenie *mier na úrovni zákazníka*. Ak chcete vytvoriť *miery na úrovni podniku*, môžete odstrániť predvolenú dimenziu.
   1. Vyberte **Hotovo** na pridanie dimenzie k miere.

1. Ak existuje viac postupov medzi dátovou entitou, ktorú ste mapovali, a entitou zákazníka, musíte zvoliť jednu z identifikovaných [postupov vzťahov medzi entitami](relationships.md). Výsledky mier sa môžu líšiť v závislosti od zvoleného postupu.
   1. Vyberte **Predvoľby údajov** a vyberte postup entity, ktorý by sa mal použiť na identifikáciu vašej miery.
   1. Výberom možnosti **Hotovo** použite svoj výber. 

   :::image type="content" source="media/measures-data-preferences.png" alt-text="Vyberte postup entity pre mieru.":::

1. Ak chcete pridať ďalšie výpočty miery, vyberte položku **Nový výpočet**. Na nové výpočty môžete použiť iba entity v tom istom postupe entity. Ďalšie výpočty sa zobrazia ako nové stĺpce v entite výstupu miery.

1. Vyberte **...** vo výpočte na **Duplikovanie**, **Premenovanie** alebo **Odstránenie** výpočtu z miery.

1. V oblasti **Ukážka** uvidíte dátovú schému entity výstupu miery vrátane filtrov a dimenzií. Ukážka dynamicky reaguje na zmeny v konfigurácii.

1. Vyberte **Spustiť** na výpočet výsledkov pre nakonfigurovanú mieru. Vyberte **Uložiť a zavrieť**, ak si chcete ponechať aktuálnu konfiguráciu a mieru spustiť neskôr.

1. Prechodom na možnosť **Miery** zobrazíte novovytvorenú mieru v zozname.

## <a name="manage-your-measures"></a>Spravovanie mier

Po [vytvorení miery](#create-a-measure) sa zobrazí zoznam mier na stránke **Miery**.

Nájdete informácie o type miery, jej tvorcovi, dátume vytvorenia, statuse a stave. Keď vyberiete mieru zo zoznamu, môžete si pozrieť ukážku výstupu a stiahnuť súbor .CSV.

Ak chcete obnoviť všetky svoje miery naraz, vyberte položku **Obnoviť všetko** bez výberu konkrétnej miery.

> [!div class="mx-imgBorder"]
> ![Akcie na spravovanie jednotlivých mier](media/measure-actions.png "Akcie na spravovanie jednotlivých mier")

Vyberte mieru zo zoznamu a zobrazte nasledujúce možnosti:

- Kliknutím na názov miery zobrazíte podrobnosti.
- **Upravte** konfiguráciu miery.
- **Obnovte** mieru na základe najnovších údajov.
- **Premenujte** mieru.
- **Odstráňte** mieru.
- **Aktivujte** alebo **Deaktivujte**. Neaktívne miery sa počas [plánovaného obnovenia](system.md#schedule-tab) neobnovujú.

> [!TIP]
> Existuje [šesť druhov stavov](system.md#status-types) pre úlohy/procesy. Okrem toho väčšina procesov [závisí na ďalších nadväzujúcich procesoch](system.md#refresh-policies). Môžete si vybrať stav procesu a zobraziť podrobnosti o priebehu celej úlohy. Po výbere **Pozrieť detaily** pre jednu z úloh úlohy nájdete ďalšie informácie: čas spracovania, posledný dátum spracovania a všetky chyby a varovania spojené s úlohou.

## <a name="next-step"></a>Nasledujúci krok

Môžete použiť existujúce miery na vytvorenie [vlastného segmentu](segments.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]