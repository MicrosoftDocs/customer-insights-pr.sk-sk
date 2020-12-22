---
title: Entity a množiny údajov
description: Zobrazujte údaje na stránke Entity.
ms.date: 04/16/2020
ms.reviewer: mukeshpo
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: e3f41c0424b2cd756d72ae6af9d5225ebba92628
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406901"
---
# <a name="entities-in-audience-insights"></a>Entity v prehľadoch cieľových skupín

Po [nakonfigurovaní zdrojov údajov](data-sources.md) prejdite na stránku **Entity** a vyhodnoťte kvalitu údajov, ktoré boli prijaté. Entity sa považujú za množiny údajov. Ďalšie funkcie služby Dynamics 365 Customer Insights súvisia s týmito entitami. Ich dôkladná revízia vám môže pomôcť overiť výstup týchto funkcií.

Stránka **Entity** uvádza entity a obsahuje niekoľko stĺpcov:

- **Názov**: Názov entity údajov. Ak sa vedľa názvu entity zobrazí výstražný symbol, znamená to, že údaje pre danú entitu sa nenačítali úspešne.
- **Zdroj**: Typ zdroja údajov, ktorý prijímala entita
- **Autor**: Meno osoby, ktorá vytvorila entitu
- **Vytvorené**: Dátum a čas vytvorenia entity
- **Aktualizoval používateľ**: Meno osoby, ktorá aktualizovala entitu
- **Naposledy aktualizované**: Dátum a čas poslednej aktualizácie entity
- **Posledné obnovenie**: Dátum a čas posledného obnovenia údajov

## <a name="exploring-a-specific-entitys-data"></a>Skúmanie údajov konkrétnej entity

Vyberte entitu a preskúmajte rôzne polia a záznamy zahrnuté v tejto entite.

> [!div class="mx-imgBorder"]
> ![Vyberte entitu](media/data-manager-entities-data.png "Vyberte entitu")

- Karta **Údaje** je predvolene vybratá a zobrazuje tabuľku so zoznamom podrobností o jednotlivých záznamoch entity.

> [!div class="mx-imgBorder"]
> ![Tabuľka Polia](media/data-manager-entities-fields.PNG "Tabuľka Polia")

- Karta **Polia** zobrazuje tabuľku na kontrolu podrobností vybratej entity, ako sú napríklad názvy polí, typy údajov a typy. Stĺpec **Typ** zobrazuje typy asociované s modelom Common Data Model, ktoré sú buď automaticky identifikované systémom alebo [manuálne priradené](map-entities.md) používateľmi. Ide o sémantické typy, ktoré sa môžu odlišovať od typov údajov atribútov, napríklad pole *E-mail* nižšie má typ údajov *Text*, ale jeho (sémantický) typ modelu Common Data Model môže byť *E-mail* alebo *EmailAddress*.

> [!NOTE]
> Obidve tabuľky zobrazujú iba vzorku údajov entity. Ak chcete zobraziť celú množinu údajov, prejdite na stránku **Zdroje údajov**, vyberte entitu, vyberte položku **Upraviť** a potom zobrazte údaje tejto entity pomocou editora Power Query, ako je vysvetlené v [zdrojoch údajov](data-sources.md).

Ak sa chcete dozvedieť viac o údajoch prijatých v entite, stĺpec **Súhrn** vám poskytuje niektoré dôležité vlastnosti údajov, ako sú napríklad hodnoty null, chýbajúce údaje, jedinečné hodnoty, počty a rozdelenia, ktoré sa vzťahujú na vaše dáta.

Ak chcete zobraziť súhrn údajov, vyberte ikonu grafu.

> [!div class="mx-imgBorder"]
> ![Súhrnný symbol](media/data-manager-entities-summary.png "Tabuľka so zhrnutím údajov")

### <a name="next-step"></a>Nasledujúci krok

Pozrite si tému [Zjednotenie](data-unification.md), kde sa dozviete ,ako *mapovať*, *zosúladiť* a *zlúčiť* prijaté údaje.
