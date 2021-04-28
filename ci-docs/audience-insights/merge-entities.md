---
title: Zlučovanie entít pri zjednotení údajov
description: Zlučujte entity na účely vytvorenia jednotných profilov zákazníkov.
ms.date: 04/16/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 4ad06a0baf57e612fc0e0214dfd23d28e7d2b6be
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896530"
---
# <a name="merge-entities"></a>Zlúčenie entít

Fáza zlúčenia je posledná fáza v procese zjednocovania údajov. Jeho účelom je zosúladenie protichodných údajov. Medzi príklady konfliktných údajov môže patriť meno zákazníka, ktoré sa nachádza v dvoch vašich množinách údajov, ale v každom sa zobrazuje trochu inak („Grant Marshall“ verzus „Grant Marshal“), alebo telefónne číslo, ktoré sa líši vo formáte (617-803-091X verzus 617803091X). Zlúčenie týchto kolidujúcich údajových bodov sa vykonáva na základe atribútov.

Po dokončení [porovnávacej fázy](match-entities.md) môžete začať fázu zlúčenia výberom dlaždice **Zlúčiť** na stránke **Zjednotiť**.

## <a name="review-system-recommendations"></a>Kontrola systémových odporúčaní

Na stránke **Zlúčiť** môžete vybrať a vylúčiť atribúty, ktoré sa majú zlúčiť v rámci jednotnej entity profilu zákazníka (výsledok procesu konfigurácie). Niektoré atribúty sú zlúčené systémom automaticky.

### <a name="view-merged-attributes"></a>Zobrazenie zlúčených atribútov

Ak chcete zobraziť atribúty, ktoré sú súčasťou jedného z automaticky zlúčených atribútov, vyberte tento zlúčený atribút. Dva atribúty, ktoré tvoria zlúčený atribút, sa zobrazia v dvoch nových riadkoch pod zlúčeným atribútom.

> [!div class="mx-imgBorder"]
> ![Výber zlúčeného atribútu](media/configure-data-merge-profile-attributes.png "Výber zlúčeného atribútu")

### <a name="separate-merged-attributes"></a>Oddelenie zlúčených atribútov

Ak chcete oddeliť alebo zrušiť zlúčenie všetkých automaticky zlúčených atribútov, vyhľadajte tento atribút v tabuľke **Atribúty profilu**.

1. Stlačte tlačidlo troch bodiek (...).
  
2. V rozbaľovacej ponuke vyberte položku **Oddeliť polia**.

### <a name="remove-merged-attributes"></a>Odstránenie zlúčených atribútov

Ak chcete vylúčiť atribút z entity profilu konečného zákazníka, nájdite ho v tabuľke **Atribúty profilu**.

1. Stlačte tlačidlo troch bodiek (...).
  
2. V rozbaľovacom zozname vyberte položku **Nezlúčiť**.

   Atribút sa presunie do sekcie **Odstránené zo záznamu zákazníka**.

## <a name="manually-add-a-merged-attribute"></a>Ručné pridanie zlúčeného atribútu

Ak chcete pridať zlúčený atribút, prejdite na stránku **Zlúčiť**.

1. Vyberte **Pridať zlúčený atribút**.

2. Zadajte **Názov** jeho neskoršiu identifikáciu na stránke **Zlúčiť**.

3. Voliteľne uveďte **Zobrazované meno**, ktoré sa objaví v zjednotenej entite Profil zákazníka.

4. Nakonfigurujte **Výber duplicitných atribútov** na výber atribútov, ktoré chcete zlúčiť zo zosúladených entít. Môžete tiež hľadať atribúty.

5. Nastavte **Zoradiť podľa dôležitosti** na uprednostnenie jedného atribútu pred ostatnými. Napríklad, ak entita *WebAccountCSV* obsahuje najpresnejšie údaje o atribúte *Celé mená*, mali by ste uprednostniť túto entitu pred *ContactCSV* výberom *WebAccountCSV*. Ako výsledok, *WebAccountCSV* prejde na prvú prioritu, zatiaľ čo *ContactCSV* prejde na druhú prioritu pri posúvaní hodnôt pre atribút *Celé meno*.

## <a name="run-your-merge"></a>Spustenie zlúčenia

Či už atribúty zlúčite ručne alebo necháte, aby ich zlúčil systém, môžete zlúčenie kedykoľvek spustiť. Vyberte **Spustiť** na stránke **Zlúčiť** a začnite s procesom.

> [!div class="mx-imgBorder"]
> ![Uloženie a spustenie zlúčenia údajov](media/configure-data-merge-save-run.png "Uloženie a spustenie zlúčenia údajov")

Ak chcete vykonať ďalšie zmeny a zopakovať krok, môžete zrušiť prebiehajúcu zlúčenie. Vyberte **Obnovuje sa…** a vyberte **Zrušiť úlohu** na zobrazenej bočnej table.

Keď sa text **Obnovuje sa…** zmení na **Úspešný**, zlúčenie bolo dokončené a vyriešilo rozpory vo vašich údajoch podľa pravidiel, ktoré ste definovali. Zlúčené a nezlúčené atribúty sú zahrnuté v entite zjednoteného profilu. Vylúčené atribúty nie sú zahrnuté v entite zjednoteného profilu.

Ak to nebolo prvýkrát, keď ste úspešne vykonali zlúčenie, všetky následné procesy vrátane obohatenia, segmentácie a mier, sa automaticky znovu spustia. Po opätovnom spustení všetkých následných procesov profily zákazníkov odrážajú všetky zmeny, ktoré ste vykonali.

> [!TIP]
> Existuje [šesť druhov stavov](system.md#status-types) pre úlohy/procesy. Okrem toho väčšina procesov [závisí na ďalších nadväzujúcich procesoch](system.md#refresh-policies). Môžete si vybrať stav procesu a zobraziť podrobnosti o priebehu celej úlohy. Po výbere **Pozrieť detaily** pre jednu z úloh úlohy nájdete ďalšie informácie: čas spracovania, posledný dátum spracovania a všetky chyby a varovania spojené s úlohou.

## <a name="next-step"></a>Nasledujúci krok

Konfigurujte [Aktivity](activities.md), [Obohatenie](enrichment-hub.md) alebo [Vzťahy](relationships.md) a získajte viac informácií o svojich zákazníkoch.

Ak ste už nakonfigurovali činnosti, obohatenie alebo vzťahy alebo ak ste zadefinovali segmenty, automaticky sa spracujú, aby sa použili najnovšie údaje o zákazníkoch.




[!INCLUDE[footer-include](../includes/footer-banner.md)]