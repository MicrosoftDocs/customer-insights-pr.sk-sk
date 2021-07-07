---
title: Zlučovanie entít pri zjednotení údajov
description: Zlučujte entity na účely vytvorenia jednotných profilov zákazníkov.
ms.date: 05/10/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 86ab3cefa70e5fab4bdb27cde363adee26efee4c
ms.sourcegitcommit: 0b754d194d765afef70d1008db7b347dd1f0ee40
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305673"
---
# <a name="merge-entities"></a>Zlúčenie entít

Fáza zlúčenia je posledná fáza v procese zjednocovania údajov. Jeho účelom je zosúladenie protichodných údajov. Medzi príklady konfliktných údajov môže patriť meno zákazníka, ktoré sa nachádza v dvoch vašich množinách údajov, ale v každom sa zobrazuje trochu inak („Grant Marshall“ verzus „Grant Marshal“), alebo telefónne číslo, ktoré sa líši vo formáte (617-803-091X verzus 617803091X). Zlúčenie týchto kolidujúcich údajových bodov sa vykonáva na základe atribútov.

:::image type="content" source="media/merge-fields-page.png" alt-text="Stránka zlúčenia v procese zjednotenia údajov zobrazujúca tabuľku so zlúčenými poľami, ktoré definujú zjednotený profil zákazníka.":::

Po dokončení [porovnávacej fázy](match-entities.md) môžete začať fázu zlúčenia výberom dlaždice **Zlúčiť** na stránke **Zjednotiť**.

## <a name="review-system-recommendations"></a>Kontrola systémových odporúčaní

V časti **Údaje** > **Zjednotiť** > **Zlúčiť** vyberáte a vylučujete atribúty, ktoré sa majú zlúčiť v rámci vašej entity zjednoteného profilu zákazníka. Zjednotený profil zákazníka je výsledkom procesu zjednotenia údajov. Niektoré atribúty sú zlúčené systémom automaticky.

Ak chcete zobraziť atribúty, ktoré sú obsiahnuté v jednom z vašich automaticky zlúčených atribútov, vyberte tento zlúčený atribút na karte **Zákaznícke polia** tabuľky. Dva atribúty, ktoré tvoria zlúčený atribút, sa zobrazia v dvoch nových riadkoch pod zlúčeným atribútom.

## <a name="separate-rename-exclude-and-edit-merged-fields"></a>Zlúčené polia môžete oddeľovať, premenovávať, vylučovať a upravovať

Môžete zmeniť spôsob, akým systém spracováva zlúčené atribúty, aby sa vytvoril jednotný profil zákazníka. Stlačte možnosť **Zobraziť viac** a vyberte, čo chcete zmeniť.

:::image type="content" source="media/manage-merged-attributes.png" alt-text="Možnosti v rozbaľovacej ponuke Zobraziť viac na správu zlúčených atribútov.":::

Ďalšie informácie nájdete v nasledovných sekciách.

## <a name="separate-merged-fields"></a>Oddelenie zlúčených polí

Ak chcete oddeliť zlúčené polia, vyhľadajte atribút v tabuľke. Oddelené polia sa zobrazujú ako jednotlivé údajové body v zjednotenom profile zákazníka. 

1. Vybrať zlúčené polia.
  
1. Stlačte možnosť **Zobraziť viac** a stlačte možnosť **Oddeliť polia**.
 
1. Potvrďte oddelenie.

1. Stlačte možnosť **Uložiť** a **Spustiť** na spracovanie zmien.

## <a name="rename-merged-fields"></a>Premenovať zlúčené polia

Zmeňte zobrazovaný názov zlúčených atribútov. Názov výstupnej entity nemožno zmeniť.

1. Vybrať zlúčené polia.
  
1. Stlačte možnosť **Zobraziť viac** a stlačte možnosť **Premenovať**.

1. Potvrďte zmenený zobrazovaný názov. 

1. Stlačte možnosť **Uložiť** a **Spustiť** na spracovanie zmien.

## <a name="exclude-merged-fields"></a>Vylúčiť zlúčené polia

Vylúčte atribút z jednotného profilu zákazníka. Ak sa pole používa v iných procesoch, napríklad v segmente, pred vylúčením z profilu zákazníka ho z týchto procesov odstráňte. 

1. Vybrať zlúčené polia.
  
1. Stlačte možnosť **Zobraziť viac** a stlačte možnosť **Vylúčiť**.

1. Potvrďte vylúčenie.

1. Stlačte možnosť **Uložiť** a **Spustiť** na spracovanie zmien. 

Na stránke **Zlúčiť** zvoľte možnosť **Vylúčené polia** a zobrazte si zoznam všetkých vylúčených polí. Táto tabla vám umožňuje pridať vylúčené polia späť.

## <a name="manually-combine-fields"></a>Ručne spojené polia

Zadajte zlúčený atribút manuálne. 

1. Na stránke **Zlúčiť** stlačte možnosť **Kombinovať polia**.

1. Zadajte **Názov** a **Názov výstupného poľa**.

1. Zvoľte si pole na pridanie. Stlačte možnosť **Pridať polia** a skombinujte ďalšie polia.

1. Potvrďte vylúčenie.

1. Stlačte možnosť **Uložiť** a **Spustiť** na spracovanie zmien. 

## <a name="change-the-order-of-fields"></a>Zmena poradia polí

Niektoré entity obsahujú viac podrobností ako iné. Ak entita obsahuje najnovšie údaje o poli, môžete ju pri zlučovaní hodnôt uprednostniť pred inými entitami.

1. Vybrať zlúčené polia.
  
1. Stlačte možnosť **Zobraziť viac** a stlačte možnosť **Upraviť**.

1. Na table **Kombinovať polia** stlačte možnosť **Premiestniť nahor/nadol** a nastavte poradie alebo ich presuňte na požadované miesto.

1. Potvrďte zmenu.

1. Stlačte možnosť **Uložiť** a **Spustiť** na spracovanie zmien.

## <a name="run-your-merge"></a>Spustenie zlúčenia

Či už atribúty zlúčite ručne alebo necháte, aby ich zlúčil systém, môžete zlúčenie kedykoľvek spustiť. Vyberte **Spustiť** na stránke **Zlúčiť** a začnite s procesom.

> [!div class="mx-imgBorder"]
> ![Uloženie a spustenie zlúčenia údajov](media/configure-data-merge-save-run.png "Uloženie a spustenie zlúčenia údajov")

Stlačte možnosť **Zlúčiť položky určené len na spustenie** ak chcete iba vidieť výstup odrážajúci sa v jednotnej entite zákazníka. Následné procesy sa obnovia ako [definované v rozvrhu obnovy](system.md#schedule-tab).

Stlačte možnosť **Spustiť procesy zlučovania a tie, ktoré prebiehajú zo servera ku klientovi**, aby ste obnovili systém svojimi zmenami. Všetky procesy vrátane obohatenia, segmentov a opatrení sa znova spustia automaticky. Po dokončení všetkých následných procesov budú profily zákazníkov odrážať všetky vykonané zmeny.

Ak chcete vykonať ďalšie zmeny a znova krok zopakovať, môžete zrušiť prebiehajúce zlúčenie. Vyberte **Obnovuje sa…** a vyberte **Zrušiť úlohu** na zobrazenej bočnej table.

> [!TIP]
> Existuje [šesť druhov stavov](system.md#status-types) pre úlohy/procesy. Okrem toho väčšina procesov [závisí na ďalších nadväzujúcich procesoch](system.md#refresh-policies). Môžete si vybrať stav procesu a zobraziť podrobnosti o priebehu celej úlohy. Po výbere **Pozrieť detaily** pre jednu z úloh úlohy nájdete ďalšie informácie: čas spracovania, posledný dátum spracovania a všetky chyby a varovania spojené s úlohou.

## <a name="next-step"></a>Nasledujúci krok

Konfigurujte [Aktivity](activities.md), [Obohatenie](enrichment-hub.md) alebo [Vzťahy](relationships.md) a získajte viac informácií o svojich zákazníkoch.

Ak ste už nakonfigurovali aktivity, obohatenie alebo segmenty, budú automaticky spracované, aby sa použili najnovšie údaje o zákazníkoch.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
