---
title: Sémantické mapovanie (verzia Preview)
description: Prehľad sémantických mapovaní a ich použitie.
ms.date: 12/01/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: CadeSanthaMSFT
ms.author: cadesantha
manager: shellyha
ms.openlocfilehash: 08b257b97704b219bb3277042516e00deb886a49
ms.sourcegitcommit: 58651d33e0a7d438a2587c9ceeaf7ff58ae3b648
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 12/02/2021
ms.locfileid: "7881849"
---
# <a name="semantic-mappings-preview"></a>Sémantické mapovanie (verzia Preview)

Sémantické mapovania vám umožňujú mapovať údaje o vašej neaktivite do vopred definovaných schém. Tieto schémy pomáhajú prehľadom cieľových skupín lepšie porozumieť vašim atribútom údajov. Sémantické mapovanie a poskytnuté údaje umožňujú nové prehľady a funkcie v prehľadoch cieľových skupín. Ak chcete mapovať údaje o svojej aktivite na schémy, prečítajte si dokumentáciu k [aktivitám](activities.md).

**Sémantické mapovania sú v súčasnosti povolené pre prostredia založené na firemných obchodných vzťahoch**. *ContactProfile* je jediným typom sémantického mapovania, ktorý je v súčasnosti k dispozícii v prehľadoch cieľových skupín.

## <a name="define-a-contactprofile-semantic-entity-mapping"></a>Definícia sémantického mapovania entity ContactProfile

1. V prehľadoch cieľových skupín prejdite na **Údaje** > **Sémantické mapovania (verzia Preview)**.

1. Vyberte **Pridať sémantické mapovanie** a postupujte podľa pokynov.

1. V kroku **Údaje entity** nastavte hodnoty pre nasledujúce polia:

   - **Názov priradenia sémantickej entity**: Zadajte názov pre svoje priradenie sémantickej entity.
   - **Zdrojová entita**: Vyberte entitu, ktorá obsahuje kontaktné údaje.
   - **Primárny kľúč**: Slúži na výber poľa, ktoré jedinečne identifikuje záznam kontaktu. Nemalo by obsahovať duplicitné hodnoty, prázdne ani chýbajúce hodnoty.

   :::image type="content" source="media/Semantic_Mapping_Wizard1.png" alt-text="Nastavte mapovanie sémantickej entity s názvom, zdrojovou entitou a primárnym kľúčom.":::

1. Na pokračovanie zvoľte možnosť **Ďalej**.

1. V kroku **Vzťahy** nakonfigurujte podrobnosti tak, aby boli vaše kontaktné údaje prepojené s príslušnými údajmi obchodného vzťahu. Tento krok vizualizuje spojenie medzi entitami.  

   Je možné implementovať dva typy ciest vzťahov: **Priame vzťahy** a **Nepriame vzťahy**. Ak chcete získať ďalšie informácie, navštívte stránku [cesty priamych a nepriamych vzťahov](relationships.md#relationship-paths).

   1. Vyberte **Pridať vzťah** na konfiguráciu vzťahu.
   1. Vyberte atribút zo svojej zdrojovej entity, ktorý spája vašu kontaktnú entitu s inou entitou.
   1. Vyberte entitu, ku ktorej chcete pripojiť kontaktnú entitu. Entitu si môžete vybrať zo sekcie **Entity obchodných vzťahov** alebo **Sprostredkovateľská entita**. Ak vyberiete sprostredkovateľskú entitu, musíte definovať druhý vzťah na pripojenie k cieľovej entite obchodného vzťahu.

      :::image type="content" source="media/Semantic_Mapping_Wizard2.png" alt-text="Vyberte buď entitu obchodného vzťahu alebo sprostredkovateľskú entitu.":::

   1. Zadajte **Názov vzťahu**. Ak vzťah medzi vašimi entitami už existuje, názov vzťahu je len na čítanie. Ak žiadny vzťah neexistuje, vytvorí sa nový vzťah so zadaným menom.
   1. Vyberte **Použiť** na dokončenie konfigurácie vzťahu.

   > [!NOTE]
   > Môžete nakonfigurovať viac vzťahov medzi entitou kontaktu a inými entitami obchodných vzťahov so sprostredkovateľskými entitami.
   >  :::image type="content" source="media/Semantic_Mapping_Wizard4.png" alt-text="Vizualizácia rôznych vzťahov spája kontaktné entity s entitami obchodných vzťahov.":::

1. Vyberte **Ďalej**, keď skončíte s konfiguráciou vzťahu.

1. V kroku **Nastavenie sémantického typu** zvoľte **Sémantický typ**. V súčasnosti tam existuje jeden **Sémantický typ** s názvom *ContactProfile*.

1. Namapujte svoje údaje na **sémantický typ** *ContactProfile* pre zobrazené polia.
   - Požadované pole: ID kontaktu
   - Voliteľné polia: krstné meno, priezvisko, dátum narodenia, pohlavie, primárny e -mail a primárny telefón

   :::image type="content" source="media/Semantic_Mapping_Wizard5.png" alt-text="Mapujte svoje atribúty kontaktných údajov do poskytnutých povinných a voliteľných polí.":::

1. Na pokračovanie zvoľte možnosť **Ďalej**.

1. V kroku **Kontrola** sa pozrite na konfiguráciu sémantického mapovania. Vyberte **Upraviť** pre zodpovedajúca sekciu a vykonajte zmeny.

1. Vyberte **Uložiť** aby ste uložili svoje nové **Sémantické mapovanie**.

1. Po uložení môžete vybrať **Spustenie** procesu sémantického mapovania alebo môžete vybrať **Zavrieť** a uložiť svoje sémantické mapovanie bez toho, aby ste ho spracovali.

1. Ak chcete sémantické mapovanie spustiť neskôr, vyberte sémantické mapovanie a vyberte **Obnoviť**.

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

## <a name="manage-existing-semantic-mappings"></a>Spravujte existujúce sémantické mapovania

V položke **Údaje** > **Sémantické mapovania (verzia Preview)** si môžete prezrieť všetky svoje uložené sémantické mapovania a spravovať ich. Každé sémantické mapovanie je reprezentované samostatným riadkom. Nájdete tu podrobnosti o zdrojovej entite, sémantickom type, type mapovania a stave.

:::image type="content" source="media/semantic-mapping-options.png" alt-text="Možnosti správy sémantického mapovania.":::

- **Upraviť**: Otvorí konfiguráciu nastavenia sémantického mapovania v kroku kontroly. Aktuálnu konfiguráciu môžete zmeniť. Stlačte možnosť **Uložiť** a **Spustiť** na spracovanie zmien.

- **Obnoviť**: Obnoví vybraté sémantické mapovanie najaktuálnejšími údajmi z entít, ktoré sú súčasťou jeho konfigurácie. Obnovením daného sémantického mapovania sa obnovia všetky sémantické mapovania rovnakého typu.

- **Premenovať**: Otvorí dialógové okno, kde môžete zadať iný názov pre vybraté sémantické mapovanie. Zmeny vykonajte výberom položky **Uložiť**.

- **Vymazať**: Otvorí dialógové okno na potvrdenie vymazania vybratého sémantického mapovania. Môžete tiež odstrániť viac ako jedno sémantické mapovanie naraz tak, že vyberiete sémantické mapovania a ikonu odstránenia. Vyberte možnosť **Odstrániť** a potvrďte odstránenie.

## <a name="use-a-contactprofile-semantic-entity-mapping-to-create-contact-level-activities"></a>Na vytvorenie aktivít na úrovni kontaktu použite mapovanie sémantickej entity ContactProfile

Po vytvorení a *Kontaktný profil* mapovanie sémantických entít, môžete zachytiť aktivity kontaktov. Umožňuje vám vidieť na časovej osi aktivity pre účet, ktorý kontakt bol zodpovedný za jednotlivé aktivity. Väčšina krokov sa riadi typickou konfiguráciou mapovania aktivít.

   > [!NOTE]
   > Aby aktivity na úrovni kontaktu fungovali, musíte mať oboje **Číslo účtu** a **ContactID** atribúty pre každý záznam v rámci údajov o vašej aktivite.

1. [Definujte a *Kontaktný profil* mapovanie sémantických entít.](#define-a-contactprofile-semantic-entity-mapping) A spustite sémantické mapovanie.

1. V prehľadoch cieľových skupín prejdite na **Údaje** > **Aktivity**.

1. Vyberte **Pridať aktivitu** na vytvorenie novej aktivity.

1. Pomenujte aktivitu, vyberte entitu zdrojovej aktivity a vyberte primárny kľúč entity aktivity.

1. V **Vzťahy** krok, vytvorte nepriamy vzťah medzi vašimi zdrojmi aktivít a účtami pomocou vašich kontaktných údajov ako sprostredkovateľskej entity. Ďalšie informácie nájdete v časti [cesty priamych a nepriamych vzťahov](relationships.md#relationship-paths).
   - Príklad vzťahu pre aktivitu tzv *Nákupy*:
      - **Údaje o aktivite zdroja nákupov** > **Kontaktné údaje** na atribúte **ContactID**
      - **Kontaktné údaje** > **Údaje o účte** na atribúte **Číslo účtu**

   :::image type="content" source="media/Contact_Activities1.png" alt-text="Príklad nastavenia vzťahu.":::

1. Po nastavení vzťahov vyberte **Ďalšie** a dokončite konfiguráciu mapovania aktivít. Podrobné kroky na vytvorenie aktivity nájdete v časti [definovať činnosť](activities.md).

1. Spustite svoje mapovania aktivít.

1. Vaše aktivity na úrovni kontaktov budú teraz viditeľné na vašej časovej osi zákazníka.

   :::image type="content" source="media/Contact_Activities2.png" alt-text="Konečný výsledok po konfigurácii kontaktných aktivít":::

### <a name="contact-level-activity-timeline-filtering"></a>Filtrovanie časovej osi aktivity na úrovni kontaktu

Po nakonfigurovaní mapovania aktivít na úrovni kontaktu a jeho spustení sa časová os aktivít vašich zákazníkov aktualizuje. Zahŕňa ich ID alebo mená, v závislosti od vás *Kontaktný profil* konfiguráciu pre činnosti, v ktorých konali. Aktivity môžete filtrovať podľa kontaktov na časovej osi, aby ste videli konkrétne kontakty, o ktoré máte záujem. Okrem toho môžete výberom vidieť všetky aktivity, ktoré nie sú priradené ku konkrétnemu kontaktu **Aktivity nie sú priradené ku kontaktu**.

   :::image type="content" source="media/Contact_Activities3.png" alt-text="Dostupné možnosti filtrovania pre aktivity na úrovni kontaktu.":::

[!INCLUDE[footer-include](../includes/footer-banner.md)]
