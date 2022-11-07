---
title: Zákaznícke alebo obchodné kontaktné aktivity
description: Definujte aktivity zákazníkov alebo obchodných kontaktov a zobrazte ich na časovej osi v profiloch zákazníkov.
ms.date: 10/26/2022
ms.subservice: audience-insights
ms.reviewer: v-wendysmith
ms.topic: conceptual
author: srivas15
ms.author: shsri
manager: shellyha
searchScope:
- ci-entities
- ci-customer-card
- ci-relationships
- ci-activities
- ci-activities-wizard
- ci-measures
- ci-segment-suggestions
- customerInsights
ms.openlocfilehash: d8caa477278f04c3a0a95ced15f4bea2a22aa8cd
ms.sourcegitcommit: da6a2d189edacc8f2c0f2abedcb28245f26fe74c
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 10/27/2022
ms.locfileid: "9723800"
---
# <a name="customer-or-business-contact-activities"></a>Zákaznícke alebo obchodné kontaktné aktivity

Zákaznícke aktivity sú akcie alebo udalosti vykonávané zákazníkmi alebo obchodnými kontaktmi. Napríklad transakcie, trvanie hovoru podpory, recenzie webových stránok, nákupy alebo vrátenia tovaru. Tieto aktivity sú obsiahnuté v jednom alebo viacerých zdrojoch údajov. Pomocou Customers Insights konsolidujte svoje zákaznícke aktivity z nich [zdroje dát](data-sources.md) a priradiť ich k profilom zákazníkov. Tieto aktivity sa zobrazujú chronologicky v časovej osi v profile zákazníka. Zahrňte časovú os do aplikácií Dynamics 365 s [Doplnok Zákazníckej karty](customer-card-add-in.md) Riešenie.

## <a name="define-a-customer-activity"></a>Definujte aktivitu zákazníka

Entita musí mať aspoň jeden atribút typu **Dátum** byť zahrnuté do časovej osi zákazníka. Ovládací prvok **Pridať aktivitu** nie je povolená, ak takáto entita nie je nájdená.

1. Ísť do **Údaje** > **Aktivity**.

1. Vyberte **Pridať aktivitu** začať so sprievodcom.

1. V **Údaje o činnosti** krok, zadajte nasledujúce informácie:

   - **Názov aktivity**: Vyberte názov svojej aktivity.
   - **Subjekt činnosti** : Vyberte entitu, ktorá obsahuje údaje o transakciách alebo aktivitách.
   - **Primárny kľúč**: Slúži na výber poľa, ktoré jedinečne identifikuje záznam. Nemalo by obsahovať duplicitné hodnoty, prázdne ani chýbajúce hodnoty.

     > [!NOTE]
     > Primárny kľúč pre každý riadok musí zostať konzistentný počas obnovovania zdroj údajov. Ak sa pri obnovení zdroj údajov aktualizuje primárny kľúč pre riadok, vytvorí sa duplikáty vo výstupnej entite aktivity. 

   :::image type="content" source="media/Activity_Wizard1.PNG" alt-text="Nastavte údaje o činnosti pomocou názvu, entity a primárneho kľúča.":::

1. Vyberte **Ďalej**.

1. V **Vzťah** krok, vyberte **Pridať vzťah** na prepojenie údajov o vašej aktivite s príslušným záznamom zákazníka. Tento krok vizualizuje spojenie medzi entitami.  

   - **Cudzí kľúč** : Cudzie pole v entite vašej činnosti, ktoré sa použije na vytvorenie vzťahu s inou entitou.
   - **K názvu entity** : Zodpovedajúca entita zdrojového zákazníka, s ktorou bude vaša entita aktivity vo vzťahu. Môžete sa týkať iba zdrojových entít zákazníka, ktoré sa používajú v procese zjednotenia údajov.
   - **Názov vzťahu** : Ak vzťah medzi touto entitou aktivity a vybratou zdrojovou entitou zákazníka už existuje, názov vzťahu bude v režime len na čítanie. Ak taký vzťah neexistuje, vytvorí sa nový vzťah s menom, ktoré uvediete v tomto poli.

   :::image type="content" source="media/Activity_Wizard2.PNG" alt-text="Definovanie vzťahu entity.":::

   > [!TIP]
   > V prostrediach so scenármi „firma a firma“ si môžete vyberať medzi entitami obchodných vzťahov a inými entitami. Ak vyberiete entitu obchodného vzťahu, cesta vzťahu sa nastaví automaticky. Pre ostatné entity musíte definovať cestu vzťahu cez jednu alebo viac medziľahlých entít, kým sa nedostanete k entite obchodného vzťahu.

1. Vyberte **Použiť** na vytvorenie vzťahu.

1. Vyberte **Ďalej**.

1. V kroku **Zjednotenie činnosti** vyberte udalosť aktivity a čas začiatku vašej aktivity.
   - **Povinné polia**
      - **Aktivita udalosti**: Pole, ktoré je udalosťou pre túto aktivitu.
      - **Časová značka**: Pole, ktoré predstavuje začiatočný čas vašej aktivity.

   - **Voliteľné polia**
      - **Ďalšie podrobnosti**: Pole s relevantnými informáciami pre túto aktivitu.
      - **Ikona**: Ikona, ktorá najlepšie vystihuje tento typ aktivity.
      - **Webová adresa**: Pole obsahujúce adresu URL s informáciami o tejto aktivite. Napríklad transakčný systém, ktorý poskytuje zdroje tejto aktivity. Táto adresa URL môže byť ľubovoľné pole z zdroj údajov, alebo môže byť vytvorená ako nové pole pomocou Power Query transformácia. Údaje adresy URL budú uložené v entite *Zjednotená aktivita*, ktorú je možné spotrebovať v následnom použití [API](apis.md).

   - **Zobraziť na časovej osi**
      - Zvoľte, či sa má táto aktivita zobraziť na časovej osi profilov vašich zákazníkov. Vyberte **Áno** na zobrazenie aktivity na časovej osi alebo možnosť **Nie** na jej skrytie.

      :::image type="content" source="media/Activity_Wizard3.PNG" alt-text="Zadajte údaje o aktivite zákazníka v entite zjednotenej aktivity.":::

1. Vyberte **Ďalšie** vyberte typ aktivity alebo vyberte **Dokončiť a skontrolovať** na uloženie aktivity s nastaveným typom aktivity **Iné**.

1. V kroku **Typ aktivity** vyberte typ aktivity a prípadne vyberte, či chcete sémanticky mapovať niektoré typy aktivít pre použitie v iných oblastiach Customer Insights. V súčasnosti *Spätná väzba*, *·*, *objednávky*, *·*, a *Predplatné* typy aktivít podporujú sémantiku po súhlase s mapovaním polí. Ak typ aktivity nie je pre novú aktivitu relevantný, môžete stlačiť možnosť *Iné* alebo *Vytvoriť nový* pre vlastný typ aktivity.

1. Vyberte **Ďalej**.

1. V kroku **Revízia** overte svoje výbery. Vráťte sa k niektorému z predchádzajúcich krokov a v prípade potreby aktualizujte informácie.

1. Stlačte možnosť **Uložiť aktivitu** a použite svoje zmeny a stlačením možnosti **Hotovo** sa vráťte späť do časti **Údaje** > **Činnosti**. Zobrazí sa vytvorená aktivita.

1. Po vytvorení všetkých aktivít vyberte **Bežať** na ich spracovanie.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="manage-existing-customer-activities"></a>Spravujte aktivity existujúcich zákazníkov

Ísť do **Údaje** > **Aktivity** na zobrazenie vašich uložených aktivít, ich zdrojovej entity, typu aktivity a či sú zahrnuté v časovej osi zákazníka. Zoznam aktivít môžete zoradiť podľa ľubovoľného stĺpca alebo pomocou vyhľadávacieho poľa nájsť aktivitu, ktorú chcete spravovať.

Výberom aktivity zobrazíte dostupné akcie.

- **Upraviť** aktivitu na zmenu jej konfigurácie. Konfigurácia sa otvorí v kroku kontroly. Po zmene konfigurácie stlačte možnosť **Uložiť aktivitu** a potom stlačením možnosti **Spustiť** spracujte zmeny.
- **Premenovať** aktivita. Zmeny vykonajte výberom položky **Uložiť**.
- **Odstrániť** aktivita. Ak chcete odstrániť viac ako jednu aktivitu naraz, vyberte aktivity a potom **Odstrániť**. Potvrďte vymazanie.

## <a name="view-activity-timelines-on-customer-profiles"></a>Zobrazte časové harmonogramy aktivít v profiloch zákazníkov

1. Ak ste vybrali **Zobraziť na časovej osi aktivity** v konfigurácii aktivity prejdite na **zákazníkov** a vyberte profil zákazníka na zobrazenie aktivít zákazníka v **Časová os aktivity** oddiele.

   :::image type="content" source="media/Activity_Timeline1.PNG" alt-text="Zobrazte nakonfigurované aktivity v profiloch zákazníkov.":::

1. Ak chcete filtrovať aktivity na časovej osi aktivity:

   - Výberom jednej alebo viacerých ikon aktivity upravíte svoje výsledky tak, aby zahŕňali iba vybraté typy.

     :::image type="content" source="media/Activity_Timeline2.PNG" alt-text="Filtrujte aktivity podľa typu pomocou ikon.":::

   - Vyberte **Filter** otvorte panel filtrov na konfiguráciu filtrov časovej osi. Triediť podľa *Typ aktivity* a/alebo *Dátum*. Vyberte **Použiť**.

     :::image type="content" source="media/Activity_Timeline3.PNG" alt-text="Na konfiguráciu podmienok filtra použite panel filtra.":::

> [!NOTE]
> Filtre aktivít sa odstránia, keď opustíte profil zákazníka. Musíte ich použiť pri každom otvorení zákazníckeho profilu.

## <a name="define-a-contact-activity"></a>Definujte kontaktnú aktivitu

Pre podnikateľské účty (B-to-B) použite a *Kontaktný profil* subjekt na zachytenie aktivít kontaktov. Na časovej osi aktivity pre účet môžete vidieť, ktorý kontakt bol zodpovedný za jednotlivé aktivity. Väčšina krokov sa riadi konfiguráciou mapovania aktivít zákazníka.

   > [!NOTE]
   > Ak chcete definovať aktivitu na úrovni kontaktu, a *Kontaktný profil* musí byť vytvorená entita, buď ako a [jednotný kontaktný profil](data-unification-contacts.md) alebo cez [sémantické mapovanie](semantic-mappings.md#define-a-contactprofile-semantic-entity-mapping).
   >
   > Musíte mať oboje **Číslo účtu** a **ContactID** atribúty pre každý záznam v rámci údajov o vašej aktivite.
  
1. Ísť do **Údaje** > **Aktivity**.

1. Vyberte **Pridať aktivitu**.

1. V **Údaje o činnosti** krok, zadajte nasledujúce informácie:

   - **Názov aktivity**: Vyberte názov svojej aktivity.
   - **Subjekt činnosti** : Vyberte entitu, ktorá obsahuje údaje o transakciách alebo aktivitách.
   - **Primárny kľúč**: Slúži na výber poľa, ktoré jedinečne identifikuje záznam. Nemalo by obsahovať duplicitné hodnoty, prázdne ani chýbajúce hodnoty.

     > [!NOTE]
     > Primárny kľúč pre každý riadok musí zostať konzistentný počas obnovovania zdroj údajov. Ak sa pri obnovení zdroj údajov aktualizuje primárny kľúč pre riadok, vytvorí sa duplikáty vo výstupnej entite aktivity. 


1. V **Vzťahy** krok, vytvorte nepriamy vzťah medzi vašimi zdrojmi aktivít a účtami pomocou vašich kontaktných údajov ako sprostredkovateľskej entity. Viac informácií nájdete v časti [cesty priamych a nepriamych vzťahov](relationships.md#relationship-paths).
   - Príklad vzťahu pre aktivitu tzv *Nákupy*:
      - **Údaje o aktivite zdroja nákupov** > **Kontaktné údaje** na atribúte **ContactID**
      - **Kontaktné údaje** > **Údaje o účte** na atribúte **Číslo účtu**

   :::image type="content" source="media/Contact_Activities1.png" alt-text="Príklad nastavenia vzťahu.":::

1. Po nastavení vzťahov vyberte **Ďalšie** a dokončite konfiguráciu mapovania aktivít. Podrobné kroky na vytvorenie aktivity nájdete v časti [definovať aktivitu zákazníka](#define-a-customer-activity).

1. Spustite svoje mapovania aktivít.

1. Vaše aktivity na úrovni kontaktu budú teraz viditeľné na vašej časovej osi zákazníka.

   :::image type="content" source="media/Contact_Activities2.png" alt-text="Konečný výsledok po konfigurácii kontaktných aktivít":::

## <a name="contact-level-activity-timeline-filtering"></a>Filtrovanie časovej osi aktivity na úrovni kontaktu

Po nakonfigurovaní mapovania aktivít na úrovni kontaktu a jeho spustení sa časová os aktivít vašich zákazníkov aktualizuje. Zahŕňa ich ID alebo mená, v závislosti od vás *Kontaktný profil* konfiguráciu pre činnosti, na ktorých pôsobili. Aktivity môžete filtrovať podľa kontaktov na časovej osi, aby ste videli konkrétne kontakty, o ktoré máte záujem. Okrem toho môžete výberom vidieť všetky aktivity, ktoré nie sú priradené ku konkrétnemu kontaktu **Aktivity nie sú priradené ku kontaktu**.

   :::image type="content" source="media/Contact_Activities3.png" alt-text="Dostupné možnosti filtrovania pre aktivity na úrovni kontaktu.":::

[!INCLUDE [footer-include](includes/footer-banner.md)]
