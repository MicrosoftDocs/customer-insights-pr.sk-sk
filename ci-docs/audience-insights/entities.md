---
title: Entity a množiny údajov
description: Zobrazujte údaje na stránke Entity.
ms.date: 04/16/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: f81128183b6e20e1078ad38c42c771d343909270
ms.sourcegitcommit: c1841ab91fbef9ead9db0f63fbc669cc3af80c12
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 05/17/2021
ms.locfileid: "6049413"
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
> ![Výber entity](media/data-manager-entities-data.png "Vyberte entitu")

- Karta **Údaje** zobrazuje tabuľku s podrobnosťami o jednotlivých záznamoch entity.

> [!div class="mx-imgBorder"]
> ![Tabuľka Polia](media/data-manager-entities-fields.PNG "Tabuľka Polia")

- Karta **Atribúty** je predvolene vybratá a zobrazuje tabuľku na kontrolu podrobností o vybranej entite, ako sú názvy polí, typy údajov a typy. Stĺpec **Typ** zobrazuje typy asociované s modelom Common Data Model, ktoré sú buď automaticky identifikované systémom alebo [manuálne priradené](map-entities.md) používateľmi. Ide o sémantické typy, ktoré sa môžu odlišovať od typov údajov atribútov, napríklad pole *E-mail* nižšie má typ údajov *Text*, ale jeho (sémantický) typ modelu Common Data Model môže byť *E-mail* alebo *EmailAddress*.

> [!NOTE]
> Obidve tabuľky zobrazujú iba vzorku údajov entity. Ak chcete zobraziť celú množinu údajov, prejdite na stránku **Zdroje údajov**, vyberte entitu, vyberte položku **Upraviť** a potom zobrazte údaje tejto entity pomocou editora Power Query, ako je vysvetlené v [zdrojoch údajov](data-sources.md).

Ak sa chcete dozvedieť viac o údajoch prijatých v entite, stĺpec **Súhrn** vám poskytuje niektoré dôležité vlastnosti údajov, ako sú napríklad hodnoty null, chýbajúce údaje, jedinečné hodnoty, počty a rozdelenia, ktoré sa vzťahujú na vaše dáta.

Ak chcete zobraziť súhrn údajov, vyberte ikonu grafu.

> [!div class="mx-imgBorder"]
> ![Súhrnný symbol](media/data-manager-entities-summary.png "Tabuľka so zhrnutím údajov")

### <a name="next-step"></a>Nasledujúci krok

Pozrite si tému [Zjednotenie](data-unification.md), kde sa dozviete ,ako *mapovať*, *zosúladiť* a *zlúčiť* prijaté údaje.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
