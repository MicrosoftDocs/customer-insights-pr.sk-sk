---
title: Entity a množiny údajov
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
ms.openlocfilehash: 1e1abdf49a3c1fe6f9fdd2cf5353a7723454f47b
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 02/25/2022
ms.locfileid: "8355339"
---
# <a name="entities-in-audience-insights"></a>Entity v prehľadoch cieľových skupín

Po [nakonfigurovaní zdrojov údajov](data-sources.md) prejdite na stránku **Entity** a vyhodnoťte kvalitu údajov, ktoré boli prijaté. Entity sa považujú za množiny údajov. Ďalšie funkcie služby Dynamics 365 Customer Insights súvisia s týmito entitami. Ich dôkladná revízia vám môže pomôcť overiť výstup týchto funkcií.

The **entity** stránka obsahuje entity a obsahuje tieto stĺpce:

- **názov** : Názov dátovej entity. Ak sa vedľa názvu entity zobrazí výstražný symbol, znamená to, že údaje pre danú entitu sa nenačítali úspešne.
- **Zdroj** : Typ zdroj údajov, ktorý prijal entitu.
- **Aktualizované** : Čas poslednej aktualizácie entity.
- **Postavenie** : Podrobnosti o poslednej aktualizácii entity.

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

## <a name="explore-a-specific-entitys-data"></a>Preskúmanie údajov konkrétnej entity

1. V prehľadoch cieľových skupín prejdite na **Údaje** > **Entity**.
1. Od **entity** vyberte entitu na otvorenie stránky s podrobnosťami.  
1. Preskúmajte rôzne polia a záznamy zahrnuté pre túto entitu.

- Karta **Atribúty** je predvolene vybratá a zobrazuje tabuľku na kontrolu podrobností o vybranej entite, ako sú názvy polí, typy údajov a typy. Stĺpec **Typ** zobrazuje typy asociované s modelom Common Data Model, ktoré sú buď automaticky identifikované systémom alebo [manuálne priradené](map-entities.md) používateľmi. Tieto typy sú sémantické typy, ktoré sa môžu líšiť od dátových typov atribútov. Napríklad pole *E-mail* dole má typ údajov *Text*, ale jeho (sémantický) typ dátového modelu Common Data Model môže byť *E-mail* alebo *E-mailová adresa*.

> [!div class="mx-imgBorder"]
> ![Tabuľka Polia.](media/data-manager-entities-fields.PNG "Tabuľka Polia")

> [!NOTE]
> Táto stránka zobrazuje iba vzorku údajov vašej entity. Ak chcete zobraziť celý súbor údajov, prejdite na stránku **Zdroje dát** stránka, vyberte entitu, vyberte **Upraviť** a potom zobrazte údaje tejto entity pomocou Power Query editor, ako je vysvetlené v [Zdroje dát](data-sources.md).

Ak sa chcete dozvedieť viac o údajoch prijatých v entite, stĺpec **Súhrn** vám poskytuje niektoré dôležité vlastnosti údajov, ako sú napríklad hodnoty null, chýbajúce údaje, jedinečné hodnoty, počty a rozdelenia, ktoré sa vzťahujú na vaše dáta. Ak chcete zobraziť súhrn údajov, vyberte ikonu grafu.

> [!div class="mx-imgBorder"]
> ![Súhrnný symbol.](media/data-manager-entities-summary.png "Tabuľka so zhrnutím údajov")

- Karta **Údaje** zobrazuje tabuľku s podrobnosťami o jednotlivých záznamoch entity. Uvedené podrobnosti závisia od typu údajov entity.

> [!div class="mx-imgBorder"]
> ![Vyberte entitu.](media/data-manager-entities-data.png "Výber entity")

- The **Správy** karta (dostupná pre niektoré entity) vám umožňuje vizualizovať údaje vytvorením zostavy a obsahuje tieto stĺpce:

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

Prejdite k položke **Údaje** > **Entity** a vyhľadajte poškodené entity v časti **Systém**. Schéma pomenovania poškodených entít: „DataSourceName_EntityName_corrupt“. Vyberte poškodenú entitu, aby ste identifikovali všetky poškodené polia a dôvod na úrovni jednotlivých záznamov.
> [!div class="mx-imgBorder"]
> ![Dôvod korupcie.](media/corruption-reason.png "Dôvod korupcie")

Služba Customer Insights stále spracúva poškodené záznamy. Pri práci s jednotnými údajmi však môžu spôsobovať problémy.

Nasledujúce kontroly overujú prijaté údaje, či neobsahujú poškodené záznamy: 

- Hodnota poľa sa nezhoduje s dátovým typom jeho stĺpca.
- Polia obsahujú znaky, pre ktoré sa stĺpce nezhodujú s očakávanou schémou. Príklad: nesprávne formátované úvodzovky, neukončené úvodzovky alebo znaky nového riadku.
- Ak existujú stĺpce dátum/dátum/odstup dátumu a času, ich formát musí byť špecifikovaný v modeli, ak nezodpovedá štandardnému formátu ISO.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
