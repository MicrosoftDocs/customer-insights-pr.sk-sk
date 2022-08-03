---
title: Entity v Customer Insights
description: Zobrazujte údaje na stránke Entity.
ms.date: 12/06/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-entities
- customerInsight
ms.openlocfilehash: 0beaa46d47545ac195ced876b509dfc57821bfaf
ms.sourcegitcommit: ad74ace653db9a25fce4343adef7db1c9b0d8904
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 07/21/2022
ms.locfileid: "9183604"
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

- The **Atribúty** karta je predvolene vybratá a zobrazuje podrobnosti o vybratej entite, ako sú názvy polí, typy údajov a typy. Stĺpec **Typ** zobrazuje typy asociované s modelom Common Data Model, ktoré sú buď automaticky identifikované systémom alebo [manuálne priradené](map-entities.md) používateľmi. Tieto typy sú sémantické typy, ktoré sa môžu líšiť od dátových typov atribútov. Napríklad pole *Email* nižšie má typ údajov *Reťazec* ale jeho (sémantický) typ Common Data Model môže byť *Email*, *adresa*, alebo *Identity.Service.E-mail*.

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

## <a name="entity-specific-information"></a>Informácie konkrétnej entity

Nasledujúca časť uvádza údaje o niektorých systémom vytvorených entitách.

### <a name="corrupted-data-sources"></a>Zdroje údajov sú poškodené

Polia z prijatého zdroja údajov možno obsahujú poškodené údaje. Záznamy s poškodenými poľami sú vystavené v entitách vytvorených systémom. Znalosť poškodených záznamov vám pomôže identifikovať, ktoré údaje je treba overiť a aktualizovať v zdrojovom systéme. Po ďalšom obnovení zdroja údajov sa opravené záznamy prijmú v nástroji Customer Insights a odošlú sa do následných procesov. 

V stĺpci „deň narodenia“ je napríklad nastavený dátový typ ako „dátum“. Záznam zákazníka má dátum narodenia zapísaný ako „01/01/19777“. Systém označí tento záznam ako poškodený. Niekto môže teraz zmeniť deň narodenia v zdrojovom systéme na „1977“. Po automatickom obnovení zdrojov údajov má pole teraz platný formát a záznam sa z poškodeného subjektu odstráni.

Prejdite k položke **Údaje** > **Entity** a vyhľadajte poškodené entity v časti **Systém**. Schéma pomenovania poškodených entít: „DataSourceName_EntityName_corrupt“. Vyberte poškodenú entitu, aby ste identifikovali poškodené polia a dôvod na úrovni jednotlivých záznamov.

   :::image type="content" source="media/corruption-reason.png" alt-text="Dôvod korupcie.":::

Služba Customer Insights stále spracúva poškodené záznamy. Pri práci s jednotnými údajmi však môžu spôsobovať problémy.

Nasledujúce kontroly overujú prijaté údaje, či neobsahujú poškodené záznamy:

- Hodnota poľa sa nezhoduje s dátovým typom jeho stĺpca.
- Polia obsahujú znaky, pre ktoré sa stĺpce nezhodujú s očakávanou schémou. Príklad: nesprávne formátované úvodzovky, neukončené úvodzovky alebo znaky nového riadku.
- Ak existujú stĺpce dátum/dátum/odstup dátumu a času, ich formát musí byť špecifikovaný v modeli, ak nezodpovedá štandardnému formátu ISO.

[!INCLUDE [footer-include](includes/footer-banner.md)]
