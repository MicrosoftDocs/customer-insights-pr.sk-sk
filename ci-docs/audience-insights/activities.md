---
title: Aktivity zákazníkov
description: Definujte zákaznícke aktivity a zobrazte ich na časovej osi v zákazníckych profiloch.
ms.date: 09/27/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: CadeSanthaMSFT
ms.author: cadesantha
manager: shellyha
ms.openlocfilehash: c250efcd54ec126c0726b22a971cdedd89760d6b
ms.sourcegitcommit: 23c8973a726b15050e368cc6e0aab78b266a89f6
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 10/08/2021
ms.locfileid: "7617988"
---
# <a name="customer-activities"></a>Aktivity zákazníkov

Spojte aktivity zákazníkov z [rôznych zdrojov údajov](data-sources.md) v Dynamics 365 Customer Insights a vytvorte časovú os s chronologickým zoznamom aktivít. Zahrňte časovú os do aplikácií Dynamics 365 pomocou [doplnku Zákaznícka karta](customer-card-add-in.md) riešenie, alebo na tabuľu Power BI.

## <a name="define-an-activity"></a>Definícia aktivity

Vaše zdroje údajov môžu zahŕňať entity s údajmi o transakciách a aktivitách z viacerých zdrojov údajov. Identifikujte tieto entity a vyberte aktivity, ktoré chcete zobraziť na časovej osi zákazníka. Vyberte entitu, ktorá obsahuje vašu cieľovú aktivitu alebo aktivity.

Entita musí mať aspoň jeden atribút typu **Dátum**, aby ste boli zahrnutí do časovej osi zákazníka a bez polí **Dátum** nemôžete pridávať entity. Ovládací prvok **Pridať aktivitu** nie je povolená, ak takáto entita nie je nájdená.

1. V prehľadoch cieľových skupín prejdite na **Údaje** > **Aktivity**.

1. Stlačte možnosť **Pridať aktivitu** na spustenie riadeného zážitku pre proces nastavenia aktivity.

1. V kroku **Údaje o aktivite** nastavte hodnoty pre nasledujúce polia:

   - **Názov aktivity**: Vyberte názov svojej aktivity.
   - **Entita**: Vyberte entitu, ktorá obsahuje údaje o transakciách alebo aktivitách.
   - **Primárny kľúč**: Slúži na výber poľa, ktoré jedinečne identifikuje záznam. Nemalo by obsahovať duplicitné hodnoty, prázdne ani chýbajúce hodnoty.

   :::image type="content" source="media/Activity_Wizard1.PNG" alt-text="Nastavte údaje o činnosti pomocou názvu, entity a primárneho kľúča.":::

1. Stlačte možnosť **Ďalej** a prejdite na ďalší krok.

1. V kroku **Vzťah** nakonfigurujte podrobnosti tak, aby boli údaje o vašej aktivite prepojené s príslušným záznamom zákazníka. Tento krok vizualizuje spojenie medzi entitami.  

   - **Prvé**: Cudzie pole vo vašej entite aktivity, ktoré sa použije na nadviazanie vzťahu s inou entitou.
   - **Druhé**: Zodpovedajúca zdrojová entita zákazníka, s ktorou bude vaša entita aktivity vo vzťahu. Môžete sa týkať iba zdrojových entít zákazníka, ktoré sa používajú v procese zjednotenia údajov.
   - **Tretie**: Ak vzťah medzi touto entitou aktivity a vybranou entitou zdrojového zákazníka už existuje, názov vzťahu bude v režime iba na čítanie. Ak taký vzťah neexistuje, vytvorí sa nový vzťah s menom, ktoré uvediete v tomto poli.

   :::image type="content" source="media/Activity_Wizard2.PNG" alt-text="Definovanie vzťahu entity.":::

   > [!TIP]
   > V prostrediach B2B si môžete vyberať medzi entitami obchodných vzťahov a inými entitami. Ak vyberiete entitu obchodného vzťahu, cesta vzťahu sa nastaví automaticky. Pre ostatné entity musíte definovať cestu vzťahu cez jednu alebo viac medziľahlých entít, kým sa nedostanete k entite obchodného vzťahu.

1. Stlačte možnosť **Ďalej** a prejdite na ďalší krok. 

1. V kroku **Zjednotenie činnosti** vyberte udalosť aktivity a čas začiatku vašej aktivity. 
   - **Povinné polia**
      - **Aktivita udalosti**: Pole, ktoré je udalosťou pre túto aktivitu.
      - **Časová značka**: Pole, ktoré predstavuje začiatočný čas vašej aktivity.

   - **Voliteľné polia**
      - **Ďalšie podrobnosti**: Pole s relevantnými informáciami pre túto aktivitu.
      - **Ikona**: Ikona, ktorá najlepšie vystihuje tento typ aktivity.
      - **Webová adresa**: Pole obsahujúce adresu URL s informáciami o tejto aktivite. Napríklad transakčný systém, ktorý poskytuje zdroje tejto aktivity. Táto adresa URL môže byť ľubovoľným poľom zo zdroja údajov alebo môže byť vytvorená ako nové pole pomocou transformácie Power Query. Údaje adresy URL budú uložené v entite *Zjednotená aktivita*, ktorú je možné spotrebovať v následnom použití [API](apis.md).

   - **Zobraziť na časovej osi**
      - Zvoľte, či sa má táto aktivita zobraziť na časovej osi profilov vašich zákazníkov. Vyberte **Áno** na zobrazenie aktivity na časovej osi alebo možnosť **Nie** na jej skrytie.

      :::image type="content" source="media/Activity_Wizard3.PNG" alt-text="Zadajte údaje o aktivite zákazníka v entite zjednotenej aktivity.":::

1. Výberom tlačidla **Ďalej** prejdete na ďalší krok. Môžete stlačiť možnosť **Dokončiť a skontrolovať** a uložiť aktivitu teraz s typom aktivity nastaveným na **Iné**. 

1. V kroku **Typ aktivity** vyberte typ aktivity a prípadne vyberte, či chcete sémanticky mapovať niektoré typy aktivít pre použitie v iných oblastiach Customer Insights. Aktuálne typy aktivít *Odozva*,*Lojalit*, *SalesOrder*, *SalesOrderLine* a *Predplatné* možno sémanticky mapovať po odsúhlasení mapovania polí. Ak typ aktivity nie je pre novú aktivitu relevantný, môžete stlačiť možnosť *Iné* alebo *Vytvoriť nový* pre vlastný typ aktivity.

1. Výberom tlačidla **Ďalej** prejdete na ďalší krok. 

1. V kroku **Revízia** overte svoje výbery. Vráťte sa k niektorému z predchádzajúcich krokov a v prípade potreby aktualizujte informácie.

   :::image type="content" source="media/Activity_Wizard5.PNG" alt-text="Skontrolujte aktivitu v zadaných poliach.":::
   
1. Stlačte možnosť **Uložiť aktivitu** a použite svoje zmeny a stlačením možnosti **Hotovo** sa vráťte späť do časti **Údaje** > **Činnosti**. Tu uvidíte, ktoré aktivity sú nastavené na zobrazenie na časovej osi. 

1. Na stránke **Činnosti** stlačte možnosť **Spustiť** na spracovanie činnosti. 

> [!TIP]
> Existuje [šesť druhov stavov](system.md#status-types) pre úlohy/procesy. Okrem toho väčšina procesov [závisí na ďalších nadväzujúcich procesoch](system.md#refresh-policies). Môžete si vybrať stav procesu a zobraziť podrobnosti o priebehu celej úlohy. Po výbere **Pozrieť detaily** pre jednu z úloh úlohy nájdete ďalšie informácie: čas spracovania, posledný dátum spracovania a všetky chyby a varovania spojené s úlohou.


## <a name="manage-existing-activities"></a>Spravovanie existujúcich činností

V časti **Údaje** > **Činnosti**, môžete zobraziť všetky svoje uložené aktivity a spravovať ich. Každú aktivitu predstavuje riadok, ktorý obsahuje aj podrobnosti o zdroji, entite a type aktivity.

Po výbere aktivity sú k dispozícii nasledujúce akcie. 

- **Upraviť**: Otvorí nastavenie aktivity v kroku kontroly. Od tohto kroku môžete zmeniť ktorúkoľvek alebo celú súčasnú konfiguráciu. Po zmene konfigurácie stlačte možnosť **Uložiť aktivitu** a potom stlačením možnosti **Spustiť** spracujte zmeny.

- **Premenovať**: Otvorí dialógové okno, kde môžete zadať iný názov pre vybratú aktivitu. Zmeny vykonajte výberom položky **Uložiť**.

- **Odstrániť**: Otvorí sa dialógové okno na potvrdenie odstránenia vybratej aktivity. Môžete tiež odstrániť viac ako jednu aktivitu súčasne výberom aktivít a následným výberom ikony odstránenia. Vyberte možnosť **Odstrániť** a potvrďte odstránenie.

## <a name="view-activity-timelines-on-customer-profiles"></a>Zobrazte časové harmonogramy aktivít v profiloch zákazníkov

Po nakonfigurovaní aktivít zákazníkov vyberte **Zobraziť na časovej osi aktivity** v konfigurácii aktivít na vyhľadanie všetkých aktivít vašich zákazníkov vo svojom zákazníckom profile.

Ak chcete zákazníkovi otvoriť časovú os, prejdite na **Zákazníci** a vyberte profil zákazníka, ktorý chcete zobraziť.

Ak sa zákazník zúčastnil aktivity, ktorú ste nakonfigurovali, nájdete ho v sekcii **Časová os aktivity**.

:::image type="content" source="media/Activity_Timeline1.PNG" alt-text="Zobrazte nakonfigurované aktivity v profiloch zákazníkov.":::

Existuje niekoľko spôsobov, ako filtrovať aktivity na časovej osi aktivít:

- Môžete vybrať jednu alebo viac ikon aktivít a spresniť výsledky tak, aby zahŕňali iba vybrané typy.

  :::image type="content" source="media/Activity_Timeline2.PNG" alt-text="Filtrujte aktivity podľa typu pomocou ikon.":::

- Môžete si vybrať **Filter** a otvoriť panel filtra na konfiguráciu filtrov časovej osi.

   1. Môžete filtrovať podľa *Typu aktivity* a *Dátumu*
   1. Vyberte **Použiť** a použite filtre na časovej osi aktivít.

   :::image type="content" source="media/Activity_Timeline3.PNG" alt-text="Na konfiguráciu podmienok filtra použite panel filtra.":::

Ak chcete filtre odstrániť, vyberte položku **x** vedľa každého filtra použitého na časovej osi alebo vyberte **Vymazať filtre**.


> [!NOTE]
> Filtre aktivít sa odstránia, keď opustíte profil zákazníka. Musíte ich použiť pri každom otvorení v profile zákazníka.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
