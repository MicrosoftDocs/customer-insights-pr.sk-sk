---
title: Aktivity zákazníkov
description: Definujte aktivity zákazníkov a zobrazte ich na časovej osi zákazníkov.
ms.date: 10/13/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.openlocfilehash: fbfa9d7e00859cc80c24b98bd2dc806f1fda7803
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596748"
---
# <a name="customer-activities"></a>Aktivity zákazníkov

Spojte aktivity zákazníkov z [rôznych zdrojov údajov](data-sources.md) v službe Dynamics 365 Customer Insights na vytvorenie časovej osi zákazníkov, ktorá ukazuje aktivity v chronologickom poradí. Časovú os môžete zahrnúť do aplikácií pre zapojenie zákazníkov v Dynamics 365 cez [doplnok karty zákazníka](customer-card-add-in.md) alebo v tabuli Power BI.

## <a name="define-an-activity"></a>Definícia aktivity

Vaše zdroje údajov zahŕňajú entity s údajmi o transakciách a aktivitách z viacerých zdrojov údajov. Identifikujte tieto entity a vyberte aktivity, ktoré chcete zobraziť na časovej osi zákazníka. Vyberte entitu, ktorá obsahuje vašu cieľovú aktivitu alebo aktivity.

1. V prehľadoch cieľových skupín prejdite na **Údaje** > **Aktivity**.

1. Vyberte **Pridať aktivitu**.

   > [!NOTE]
   > Entita musí mať aspoň jeden atribút typu **Dátum**, aby ste boli zahrnutí do časovej osi zákazníka a bez polí **Dátum** nemôžete pridávať entity. Ovládací prvok **Pridať aktivitu** nie je povolená, ak takáto entita nie je nájdená.

1. V table **Pridať aktivitu** nastavte hodnoty pre nasledujúce polia:

   - **Entita**: Vyberte entitu, ktorá obsahuje údaje o transakciách alebo aktivitách.
   - **Primárny kľúč**: Slúži na výber poľa, ktoré jedinečne identifikuje záznam. Nemalo by obsahovať duplicitné hodnoty, prázdne ani chýbajúce hodnoty.
   - **Časová značka**: Vyberte pole, ktoré predstavuje začiatočný čas vašej aktivity.
   - **Udalosť**: Vyberte pole, ktoré je udalosťou aktivity.
   - **Webová adresa**: Vyberte pole, ktoré predstavuje adresu URL a poskytuje ďalšie informácie o tejto aktivite. Napríklad transakčný systém, ktorý poskytuje zdroje tejto aktivity. Táto adresa URL môže byť ľubovoľným poľom zo zdroja údajov alebo môže byť vytvorená ako nové pole pomocou transformácie Power Query. Tieto údaje URL sa uložia v entite Unified Activity, ktorú je možné následne konzumovať pomocou rozhraní API.
   - **Podrobnosti**: Voliteľne vyberte pole, ktoré sa pridá pre ďalšie podrobnosti.
   - **Ikona**: Voliteľne, vyberte ikonu, ktorá predstavuje túto aktivitu.
   - **Typ aktivity**: Definujte odkaz na typ aktivity na Common Data Model, ktorý najlepšie popisuje sémantickú definíciu aktivity.

1. V sekcii **Nastavenie vzťahu** nakonfigurujte podrobnosti na pripojenie údajov o vašej aktivite k príslušnému zákazníkovi.

    - **Pole entity Aktivita**: Vyberte pole v entite aktivity, ktoré sa použije na nadviazanie vzťahu s inou entitou.
    - **Entita Zákazník**: Vyberte zodpovedajúcu zdrojovú entitu zákazníka, s ktorou bude vaša entita aktivity vo vzťahu. Môžete sa vzťahovať iba na tie zdrojové entity zákazníkov, ktoré sa používajú v procese zjednotenia údajov.
    - **Pole entity zákazníka**: Toto pole zobrazuje primárny kľúč zdrojovej entity zákazníka vybratý v procese mapovania. Toto pole primárneho kľúča v zdrojovej entite zákazníka sa používa na vytvorenie vzťahu s entitou aktivity.
    - **Názov**: Ak už existuje vzťah medzi touto entitou aktivity a vybranou zdrojovou entitou zákazníka, názov vzťahu bude v režime len na čítanie. Ak takýto vzťah neexistuje, vytvorí sa nový vzťah s tu uvedeným menom.
   
   > [!div class="mx-imgBorder"]
   > ![Definovanie vzťahu entity](media/activities-entities-define.png "Definovanie vzťahu entity")

1. Zmeny vykonajte výberom položky **Uložiť**.

1. Na stránke **Aktivity** vyberte položku **Spustiť**.

> [!TIP]
> Existuje [šesť druhov stavov](system.md#status-types) pre úlohy/procesy. Okrem toho väčšina procesov [závisí na ďalších nadväzujúcich procesoch](system.md#refresh-policies). Môžete si vybrať stav procesu a zobraziť podrobnosti o priebehu celej úlohy. Po výbere **Pozrieť detaily** pre jednu z úloh úlohy nájdete ďalšie informácie: čas spracovania, posledný dátum spracovania a všetky chyby a varovania spojené s úlohou.

## <a name="edit-an-activity"></a>Úprava aktivity

1. V prehľadoch cieľových skupín prejdite na **Údaje** > **Aktivity**.

2. Vyberte entity aktivity, ktorú chcete upraviť a potom položku **Upraviť**. Alebo môžete umiestniť kurzor nad riadok entity a vybrať ikonu **Upraviť**.

3. Kliknite na ikonu **Upraviť**.

4. Na table **Upraviť aktivitu** aktualizujte hodnoty a vyberte položku **Uložiť**.

5. Na stránke **Aktivity** vyberte položku **Spustiť**.

## <a name="delete-an-activity"></a>Odstránenie aktivity

1. V prehľadoch cieľových skupín prejdite na **Údaje** > **Aktivity**.

2. Vyberte entitu aktivity, ktorú chcete odstrániť a potom položku **Odstrániť**. Alebo môžete umiestniť kurzor nad riadok entity a vybrať ikonu **Odstrániť**. Okrem toho môžete vybrať viac entít aktivity, ktoré sa majú odstrániť naraz.
   > [!div class="mx-imgBorder"]
   > ![Úprava alebo odstránenie vzťahu entity](media/activities-entities-edit-delete.png "Úprava alebo odstránenie vzťahu entity")

3. Vyberte ikonu **Odstrániť**.

4. Potvrďte odstránenie.


[!INCLUDE[footer-include](../includes/footer-banner.md)]