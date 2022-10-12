---
title: Entity v Customer Insights
description: Zobrazujte údaje na stránke Entity.
ms.date: 08/04/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-entities
- customerInsight
ms.openlocfilehash: e365945b27e7c985ca5371c6b72619610b6f3af1
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610117"
---
# <a name="entities-in-customer-insights"></a>Entity v Customer Insights

Po [nakonfigurovaní zdrojov údajov](data-sources.md) prejdite na stránku **Entity** a vyhodnoťte kvalitu údajov, ktoré boli prijaté. Entity sa považujú za množiny údajov. Ďalšie funkcie služby Dynamics 365 Customer Insights súvisia s týmito entitami. Ich dôkladná revízia vám môže pomôcť overiť výstup týchto funkcií.

Keď pracujete v Customer Insights, obohacujete svoje údaje alebo vytvárate segmenty, merania a aktivity, entity, ktoré sú vytvorené z týchto akcií, sa zobrazujú na **entity** stránku.

## <a name="view-a-list-of-entities"></a>Pozrite si zoznam entít

Ísť do **Údaje** > **entity** na zobrazenie zoznamu entít. Pre každú entitu sa zobrazia nasledujúce informácie.

- **názov** : Názov dátovej entity. Ak sa vedľa názvu entity zobrazí výstražný symbol, znamená to, že údaje pre danú entitu sa nenačítali úspešne.
- **Zdroj** : Typ zdroj údajov, ktorý prijal entitu.
- **Aktualizované** : Čas poslednej aktualizácie entity.
- **Postavenie** : Podrobnosti o poslednej aktualizácii entity.

## <a name="explore-a-specific-entitys-data"></a>Preskúmanie údajov konkrétnej entity

1. Ísť do **Údaje** > **entity**.
1. Výberom entity otvoríte stránku podrobností.  
1. Preskúmajte rôzne polia a záznamy zahrnuté pre túto entitu.

- The **Atribúty** karta je predvolene vybratá a zobrazuje podrobnosti o vybratej entite, ako sú názvy polí, typy údajov a typy. Stĺpec **Typ** zobrazuje typy asociované s modelom Common Data Model, ktoré sú buď automaticky identifikované systémom alebo [manuálne priradené](map-entities.md) používateľmi. Tieto typy sú sémantické typy, ktoré sa môžu líšiť od dátových typov atribútov. Napríklad pole *Email* nižšie má typ údajov *Reťazec* ale jeho (sémantický) typ Common Data Model môže byť *Email*, *adresa*, alebo *Identita.Service.E-mail*.

   :::image type="content" source="media/data-manager-entities-fields.png" alt-text="Tabuľka Polia.":::

   > [!NOTE]
   > Táto stránka zobrazuje iba vzorku údajov vašej entity. Ak chcete zobraziť celý súbor údajov, prejdite na stránku **Zdroje dát** stránka, vyberte entitu, vyberte **Upraviť** a potom zobrazte údaje tejto entity pomocou Power Query editor, ako je vysvetlené v [Zdroje dát](data-sources.md).

   Ak sa chcete dozvedieť viac o údajoch prijatých v entite, **Zhrnutie** poskytuje niektoré dôležité charakteristiky údajov, ako sú hodnoty null, chýbajúce hodnoty, jedinečné hodnoty, počty a distribúcie, bez ohľadu na to, čo sa vzťahuje na vaše údaje. Ak chcete zobraziť súhrn údajov, vyberte ikonu grafu.

   :::image type="content" source="media/data-manager-entities-summary.png" alt-text="Súhrnná tabuľka údajov.":::

- The **Údaje** záložka zobrazuje podrobnosti o jednotlivých záznamoch účtovnej jednotky. Uvedené podrobnosti závisia od typu údajov entity.

   :::image type="content" source="media/data-manager-entities-data.png" alt-text="Vyberte entitu.":::

- The **Správy** karta (dostupná pre niektoré entity) vám umožňuje vizualizovať údaje vytvorením zostavy, ktorá obsahuje tieto stĺpce:

  - **Názov prehľadu** : Názov prehľadu.
  - **Vytvoril** : Meno osoby, ktorá vytvorila entitu.
  - **Vytvorené** : Dátum a čas vytvorenia entity.
  - **Upravil** : Meno osoby, ktorá entitu upravila.
  - **Upravené** : Dátum a čas úpravy entity.

[!INCLUDE [footer-include](includes/footer-banner.md)]
