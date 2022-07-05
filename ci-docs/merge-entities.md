---
title: Zjednoťte zákaznícke polia pre zjednotenie údajov
description: Zlučujte entity na účely vytvorenia jednotných profilov zákazníkov.
recommendations: false
ms.date: 05/04/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: v-wendysmith
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-merge
- ci-match
- ci-relationships
- customerInsights
ms.openlocfilehash: ceb2724ad490c1ba44fd9b7ff2be04721892fca4
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 06/29/2022
ms.locfileid: "9082962"
---
# <a name="unify-customer-fields-for-data-unification"></a>Zjednoťte zákaznícke polia pre zjednotenie údajov

[!INCLUDE [m3-prod-trial-note](includes/m3-prod-trial-note.md)]

V tomto kroku procesu zjednotenia vyberte a vylúčte atribúty, ktoré sa majú zlúčiť v rámci entity zjednoteného profilu. Napríklad, ak tri entity mali e-mailové údaje, možno budete chcieť ponechať všetky tri samostatné e-mailové polia alebo ich zlúčiť do jedného e-mailového poľa pre zjednotený profil. Niektoré atribúty systém automaticky kombinuje. Môžete vytvoriť stabilné a jedinečné ID zákazníkov a zoskupiť súvisiace profily do klastra.

:::image type="content" source="media/m3_unify.png" alt-text="Stránka zlúčenia v procese zjednotenia údajov zobrazujúca tabuľku so zlúčenými poľami, ktoré definujú zjednotený profil zákazníka.":::

## <a name="review-and-update-the-customer-fields"></a>Skontrolujte a aktualizujte polia zákazníkov

1. Skontrolujte zoznam polí, ktoré budú zjednotené pod **Zákaznícke polia** záložka tabuľky. Vykonajte prípadné zmeny.

   1. Pre akékoľvek kombinované polia môžete:
      - [Upraviť](#edit-a-merged-field)
      - [Premenovať](#rename-fields)
      - [Oddeliť](#separate-merged-fields)
      - [Vylúčiť](#exclude-fields)
      - [Pohybujte sa nahor alebo nadol](#change-the-order-of-fields)

   1. Pre ľubovoľné jednotlivé polia môžete:
      - [Kombinovať polia](#combine-fields-manually)
      - [Skombinujte skupinu polí](#combine-a-group-of-fields)
      - [Premenovať](#rename-fields)
      - [Vylúčiť](#exclude-fields)
      - [Pohybujte sa nahor alebo nadol](#change-the-order-of-fields)

1. voliteľne [vygenerovať konfiguráciu ID zákazníka](#configure-customer-id-generation).

1. voliteľne [skupinové profily do domácností alebo klastrov](#group-profiles-into-households-or-clusters).

> [!div class="nextstepaction"]
> [Ďalší krok: Skontrolujte zjednotenie](review-unification.md)

### <a name="edit-a-merged-field"></a>Upravte zlúčené pole

1. Vyberte zlúčené pole a vyberte **Upraviť**. Zobrazí sa tabla Kombinovať polia.

1. Určte jednu z troch možností, ako sa majú polia zlúčiť:
    - **Dôležitosť**: Určuje výslednú hodnotu podľa stupňa dôležitosti daného pre zúčastnené polia. Toto je predvolená možnosť zlučovania. Vyberaním možnosti **Pohyb nahor/nadol** nastavte stupeň dôležitosti.

      :::image type="content" source="media/importance-merge-option.png" alt-text="Možnosť dôležitosti v dialógovom okne zlúčenia polí.":::

    - **Najnovšie** : Určuje výslednú hodnotu na základe aktuálnosti. Aby bolo možné definovať aktuálnosť, je potrebné dátumové alebo numerické pole pre všetky zúčastnené entity v rozsahu zlúčenia polí.

      :::image type="content" source="media/recency-merge-option.png" alt-text="Možnosť aktuálnosti v dialógovom okne zlúčenia polí.":::

    - **Najstaršie** : Určuje výslednú hodnotu na základe zastaranosti. Aby bolo možné definovať aktuálnosť, je potrebné dátumové alebo numerické pole pre všetky zúčastnené entity v rozsahu zlúčenia polí.

1. Do procesu zlúčenia môžete pridať ďalšie polia.

1. Je možné zmeniť názov zlúčeného poľa.

1. Ak chcete zmeny použiť, vyberte položku **Hotovo**.

### <a name="rename-fields"></a>Premenovanie polí

Zmeňte zobrazovaný názov zlúčených alebo samostatných polí. Názov výstupnej entity nemožno zmeniť.

1. Vyberte pole a vyberte si **Premenovať**.

1. Zadajte nový zobrazovaný názov.

1. Vyberte položku **Hotovo**.

### <a name="separate-merged-fields"></a>Oddelenie zlúčených polí

Ak chcete oddeliť zlúčené polia, vyhľadajte atribút v tabuľke. Oddelené polia sa zobrazujú ako jednotlivé údajové body v zjednotenom profile zákazníka.

1. Vyberte zlúčené pole a vyberte **Samostatné polia**.

1. Potvrďte oddelenie.

### <a name="exclude-fields"></a>Vylúčiť polia

Vylúčte zlúčené alebo samostatné pole z jednotného profilu zákazníka. Ak sa pole používa v iných procesoch, napríklad v segmente, pred vylúčením z profilu zákazníka ho z týchto procesov odstráňte.

1. Vyberte pole a vyberte si **Vylúčiť**.

1. Potvrďte vylúčenie.

Ak chcete zobraziť zoznam všetkých vylúčených polí, vyberte **Vylúčené polia**. V prípade potreby môžete vylúčené pole prečítať.

### <a name="change-the-order-of-fields"></a>Zmena poradia polí

Niektoré entity obsahujú viac podrobností ako iné. Ak entita obsahuje najnovšie údaje o poli, môžete ju pri zlučovaní hodnôt uprednostniť pred inými entitami.

1. Vyberte pole.
  
1. Vyberte si **Pohyb hore/dole** na nastavenie poradia alebo ich presuňte na požadovanú pozíciu.

### <a name="combine-fields-manually"></a>Skombinujte polia ručne

Skombinujte oddelené polia a vytvorte zlúčený atribút.

1. Vyberte **Skombinujte** > **Polia**. Zobrazí sa tabla Kombinovať polia.

1. V rozbaľovacom zozname **Skombinovať polia podľa** určte zásady pre výslednú hodnotu.

1. Vyberte **Pridať pole** spojiť viac polí.

1. Zadajte **Názov** a **Názov výstupného poľa**.

1. Ak chcete zmeny použiť, vyberte položku **Hotovo**.

### <a name="combine-a-group-of-fields"></a>Skombinujte skupinu polí

So skupinou polí zaobchádzajte ako s jednou jednotkou. Ak napríklad naše záznamy obsahujú polia Adresa1, Adresa2, Mesto, Štát a PSČ, nechceme sa zlúčiť do adresy2 iného záznamu, pretože si myslíme, že by tým boli naše údaje úplnejšie.

1. Vyberte **Skombinujte** > **Skupina polí**.

1. Zadajte politiku víťaza zlúčenia v **Zoraďte skupiny podľa** rozbaľovacia ponuka.

1. Vyberte **Pridať** a vyberte, či chcete do polí pridať ďalšie polia alebo skupiny.

1. Poskytnúť **názov** a **Názov výstupu** pre každý kombinovaný odbor.

1. Poskytnúť **názov** pre skupinu polí.

1. Ak chcete zmeny použiť, vyberte položku **Hotovo**.

## <a name="configure-customer-id-generation"></a>Nakonfigurujte generovanie ID zákazníka

Definujte, ako generovať hodnoty ID zákazníka, jedinečné identifikátory profilu zákazníka. Krok zjednotenia polí v procese zjednotenia údajov vygeneruje jedinečný identifikátor profilu zákazníka. Identifikátor je *CustomerId* v *Zákazník* subjekt, ktorý je výsledkom procesu zjednocovania údajov.

The *CustomerId*  je založený na hashe prvej hodnoty primárnych kľúčov víťaza, ktoré nie sú nulové. Tieto kľúče pochádzajú z entít používaných pri zjednocovaní údajov a sú ovplyvnené poradím zhody.Takže vygenerované ID zákazníka sa môže zmeniť, keď sa zmení hodnota primárneho kľúča v primárnej entite priraďovacej objednávky. Hodnota primárneho kľúča nemusí vždy predstavovať toho istého zákazníka.

Konfiguráciou stabilného ID zákazníka sa vyhnete takémuto správaniu.

1. Vyberte kartu **Kľúče**.

1. Umiestnite kurzor myši na **CustomerId** riadok a vyberte **Konfigurovať**.
   :::image type="content" source="media/customize-stable-id.png" alt-text="Ovládací prvok na prispôsobenie vytvárania ID.":::

1. Označte najviac päť polí, ktoré budú obsahovať ID zákazníka, a budú mať vyššiu stabilitu. Záznamy, ktoré sa nezhodujú s vašou konfiguráciou, namiesto toho použijú ID nakonfigurované systémom.  

1. Vyberte položku **Hotovo**.

## <a name="group-profiles-into-households-or-clusters"></a>Zoskupte profily do domácností alebo klastrov

Môžete definovať pravidlá na zoskupenie súvisiacich profilov do klastra. V súčasnosti sú k dispozícii dva typy klastrov – domácnosti a vlastné klastre. Systém automaticky vyberie domácnosť s preddefinovanými pravidlami, ak entita *Zákazník* obsahuje sémantické polia *Person.LastName* a *Location.Address*. Môžete tiež vytvoriť klaster s vlastnými pravidlami a podmienkami podobný [pravidlám zhody](match-entities.md#define-rules-for-match-pairs).

1. Vyberte **Pokročilé** > **Vytvorte klaster**.

   :::image type="content" source="media/create-cluster.png" alt-text="Ovládací prvok na vytvorenie nového klastra.":::

1. Vyberte si medzi klastrom **Domácnosť** alebo **Vlastný**. Ak sémantické polia *Person.LastName* a *Location.Address* existujú v entite *Zákazník*, automaticky sa vyberie domácnosť.

1. Zadajte názov klastra a vyberte **Hotovo**.

1. Vyberte kartu **Klastre** a vyhľadajte klaster, ktorý ste vytvorili.

1. Zadajte pravidlá a podmienky na definovanie klastra.

1. Vyberte položku **Hotovo**. Klaster sa vytvorí po dokončení procesu zjednotenia. Identifikátory klastra sa pridajú ako nové polia do *Zákazník* subjekt.

> [!div class="nextstepaction"]
> [Ďalší krok: Skontrolujte zjednotenie](review-unification.md)

[!INCLUDE [footer-include](includes/footer-banner.md)]
