---
title: Zlučovanie entít pri zjednotení údajov
description: Zlučujte entity na účely vytvorenia jednotných profilov zákazníkov.
ms.date: 11/01/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-merge
ms.openlocfilehash: c218f9c1a1b7711ee48419470bf6c352450ffc0c
ms.sourcegitcommit: 834651b933b1e50e7557d44f926a3fb757c1f83a
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 11/02/2021
ms.locfileid: "7732791"
---
# <a name="merge-entities"></a>Zlúčenie entít

Fáza zlúčenia je posledná fáza v procese zjednocovania údajov. Jeho účelom je zosúladenie protichodných údajov. Medzi príklady konfliktných údajov môže patriť meno zákazníka, ktoré sa nachádza v dvoch vašich množinách údajov, ale v každom sa zobrazuje trochu inak („Grant Marshall“ verzus „Grant Marshal“), alebo telefónne číslo, ktoré sa líši vo formáte (617-803-091X verzus 617803091X). Zlúčenie týchto kolidujúcich údajových bodov sa vykonáva na základe atribútov.

:::image type="content" source="media/merge-fields-page.png" alt-text="Stránka zlúčenia v procese zjednotenia údajov zobrazujúca tabuľku so zlúčenými poľami, ktoré definujú zjednotený profil zákazníka.":::

Po dokončení [porovnávacej fázy](match-entities.md) môžete začať fázu zlúčenia výberom dlaždice [Zlúčiť](match-entities.md) na stránke [Zjednotiť](match-entities.md).

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

1. Označte zlúčené pole.
  
1. Stlačte možnosť **Zobraziť viac** a stlačte možnosť **Vylúčiť**.

1. Potvrďte vylúčenie.

1. Stlačte možnosť **Uložiť** a **Spustiť** na spracovanie zmien. 

Na stránke **Zlúčiť** zvoľte možnosť **Vylúčené polia** a zobrazte si zoznam všetkých vylúčených polí. Táto tabla vám umožňuje pridať vylúčené polia späť.

## <a name="edit-a-merged-field"></a>Upravte zlúčené pole

1.  Označte zlúčené pole.

1.  Stlačte možnosť **Zobraziť viac** a stlačte možnosť **Upraviť**.

1.  Určte jednu z troch možností, ako sa majú polia zlúčiť:
    - **Dôležitosť**: Určuje výslednú hodnotu podľa stupňa dôležitosti daného pre zúčastnené polia. Toto je predvolená možnosť zlučovania. Vyberaním možnosti **Pohyb nahor/nadol** nastavte stupeň dôležitosti.
    :::image type="content" source="media/importance-merge-option.png" alt-text="Možnosť dôležitosti v dialógovom okne zlúčenia polí."::: 
    - **Najnovšie** : Určuje výslednú hodnotu na základe aktuálnosti. Aby bolo možné definovať aktuálnosť, je potrebné dátumové alebo numerické pole pre všetky zúčastnené entity v rozsahu zlúčenia polí.
    :::image type="content" source="media/recency-merge-option.png" alt-text="Možnosť aktuálnosti v dialógovom okne zlúčenia polí.":::
    - **Najstaršie** : Určuje výslednú hodnotu na základe zastaranosti. Aby bolo možné definovať aktuálnosť, je potrebné dátumové alebo numerické pole pre všetky zúčastnené entity v rozsahu zlúčenia polí.

1.  Do procesu zlúčenia môžete pridať ďalšie polia.

1.  Je možné zmeniť názov zlúčeného poľa.

1. Ak chcete zmeny použiť, vyberte položku **Hotovo**.

1. Stlačte možnosť **Uložiť** a **Spustiť** na spracovanie zmien. 

## <a name="manually-combine-fields"></a>Ručne spojené polia

Zadajte zlúčený atribút manuálne. 

1. Na stránke **Zlúčiť** stlačte možnosť **Kombinovať polia**.

1. V rozbaľovacom zozname **Skombinovať polia podľa** určte zásady pre výslednú hodnotu.

1. Zvoľte si pole na pridanie. Stlačte možnosť **Pridať polia** a skombinujte ďalšie polia.

1. Zadajte **Názov** a **Názov výstupného poľa**.

1. Ak chcete zmeny použiť, vyberte položku **Hotovo**.

1. Stlačte možnosť **Uložiť** a **Spustiť** na spracovanie zmien. 

## <a name="change-the-order-of-fields"></a>Zmena poradia polí

Niektoré entity obsahujú viac podrobností ako iné. Ak entita obsahuje najnovšie údaje o poli, môžete ju pri zlučovaní hodnôt uprednostniť pred inými entitami.

1. Vybrať zlúčené polia.
  
1. Stlačte možnosť **Zobraziť viac** a stlačte možnosť **Upraviť**.

1. Na table **Kombinovať polia** stlačte možnosť **Premiestniť nahor/nadol** a nastavte poradie alebo ich presuňte na požadované miesto.

1. Potvrďte zmenu.

1. Stlačte možnosť **Uložiť** a **Spustiť** na spracovanie zmien.

## <a name="configure-customer-id-generation"></a>Konfigurácia vytvorenia ID zákazníka 

Po nakonfigurovaní polí zlúčenia je možné definovať, ako generovať hodnoty CustomerId, jedinečné identifikátory profilov zákazníkov. Krok zlúčenia pri zjednocovaní vytvára jedinečný identifikátor zákazníckeho profilu. Tento identifikátor je CustomerId v entite *Zákazník*, ktorá je výsledok zjednotených údajov. 

CustomerId v entite Customer je založený na hodnote hash prvej hodnoty nenulových primárnych výsledných kľúčov. Tieto kľúče sú z entít, ktoré sa použili vo fáze párovania a zlúčenia, a ktoré sú dané poradím zhody.Vytvorený CustomerID sa preto môže zmeniť, ak sa zmení hodnota primárneho kľúča v primárnej entite poradia zhody. Hodnota primárneho kľúča teda nemusí vždy predstavovať rovnakého zákazníka.

Konfiguráciou stabilného ID zákazníka sa vyhnete takémuto správaniu.

**Konfigurácia jedinečného ID zákazníka**

1. Prejdite do položky **Zjednotiť** > **Zlúčiť**.

1. Vyberte kartu **Kľúče**. 

1. Umiestnite kurzor na riadok **CustomerId** a vyberte možnosť **Konfigurovať**.
   :::image type="content" source="media/customize-stable-id.png" alt-text="Ovládací prvok na prispôsobenie vytvárania ID.":::

1. Označte najviac päť polí, ktoré budú obsahovať ID zákazníka, a budú mať vyššiu stabilitu. Záznamy, ktoré sa nezhodujú s vašou konfiguráciou, namiesto toho použijú ID nakonfigurované systémom.  

1. Vyberte položku **Hotovo** a spusťte zlučovanie, aby sa použili vami vykonané zmeny.

## <a name="group-profiles-into-households-or-clusters"></a>Zoskupte profily do domácností alebo klastrov

V rámci procesu konfigurácie generovania profilu zákazníka môžete definovať pravidlá pre zoskupenie príbuzných profilov do klastra. V súčasnosti sú k dispozícii dva typy klastrov – domácnosti a vlastné klastre. Systém automaticky vyberie domácnosť s preddefinovanými pravidlami, ak entita *Zákazník* obsahuje sémantické polia *Person.LastName* a *Location.Address*. Môžete tiež vytvoriť klaster s vlastnými pravidlami a podmienkami podobný [pravidlám zhody](match-entities.md#define-rules-for-match-pairs).

**Definícia domácnosti alebo klastra**

1. Prejdite do položky **Zjednotiť** > **Zlúčiť**.

1. Na karte **Zlúčiť** vyberte **Pokročilé** > **Vytvoriť klaster**.

   :::image type="content" source="media/create-cluster.png" alt-text="Ovládací prvok na vytvorenie nového klastra.":::

1. Vyberte si medzi klastrom **Domácnosť** alebo **Vlastný**. Ak sémantické polia *Person.LastName* a *Location.Address* existujú v entite *Zákazník*, automaticky sa vyberie domácnosť.

1. Zadajte názov klastra a vyberte **Hotovo**.

1. Vyberte kartu **Klastre** a vyhľadajte klaster, ktorý ste vytvorili.

1. Zadajte pravidlá a podmienky na definovanie klastra.

1. Vyberte **Spustiť** a spustite proces zlúčenia a vytvorte klaster.

Po spustení procesu zlúčenia sa identifikátory klastra pridajú ako nové polia do entity *Zákazník*.

## <a name="run-your-merge"></a>Spustenie zlúčenia

Či už atribúty zlúčite ručne alebo necháte, aby ich zlúčil systém, môžete zlúčenie kedykoľvek spustiť. Vyberte **Spustiť** na stránke **Zlúčiť** a začnite s procesom.

> [!div class="mx-imgBorder"]
> ![Uloženie a spustenie zlúčenia údajov.](media/configure-data-merge-save-run.png "Uloženie a spustenie zlúčenia údajov")

Stlačte možnosť **Zlúčiť položky určené len na spustenie** ak chcete iba vidieť výstup odrážajúci sa v jednotnej entite zákazníka. Následné procesy sa obnovia ako [definované v rozvrhu obnovy](system.md#schedule-tab).

Stlačte možnosť **Spustiť procesy zlučovania a tie, ktoré prebiehajú zo servera ku klientovi**, aby ste obnovili systém svojimi zmenami. Všetky procesy vrátane obohatenia, segmentov a opatrení sa znova spustia automaticky. Po dokončení všetkých následných procesov budú profily zákazníkov odrážať všetky vykonané zmeny.

Ak chcete vykonať ďalšie zmeny a znova krok zopakovať, môžete zrušiť prebiehajúce zlúčenie. Vyberte **Obnovuje sa…** a vyberte **Zrušiť úlohu** na zobrazenej bočnej table.

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

:::image type="content" source="media/process-detail-path.png" alt-text="Vnorte sa do tejto cesty, aby ste získali prístup k podrobnostiam procesu z odkazu na stav úlohy.":::

## <a name="next-step"></a>Nasledujúci krok

Konfigurujte [Aktivity](activities.md), [Obohatenie](enrichment-hub.md) alebo [Vzťahy](relationships.md) a získajte viac informácií o svojich zákazníkoch.

Ak ste už nakonfigurovali aktivity, obohatenie alebo segmenty, budú automaticky spracované, aby sa použili najnovšie údaje o zákazníkoch.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
