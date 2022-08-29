---
title: Vytvorenie jednotného profilu kontaktu (ukážka)
description: Prejdite procesom zjednotenia údajov a vytvorte jeden hlavný súbor údajov kontaktov.
ms.date: 08/12/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: overview
author: Scott-Stabbert
ms.author: sstabbert
manager: shellyha
searchScope:
- ci-map
- ci-match
- ci-merge
- customerInsights
ms.openlocfilehash: 721f47563582a94b5b8244ca5d5d7d1350695512
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 08/16/2022
ms.locfileid: "9305092"
---
# <a name="create-a-unified-contact-profile-preview"></a>Vytvorenie jednotného profilu kontaktu (ukážka)

Po [zjednotenie obchodných účtov](map-entities.md), môžete voliteľne zjednotiť kontakty pre tieto účty a prepojiť zjednotené kontakty so zjednotenými účtami. Proces zjednotenia kontaktov mapuje kontaktné údaje z viacerých zdrojov údajov, odstraňuje duplikáty, porovnáva údaje naprieč entitami, nastavuje sémantické mapovanie, vytvára vzťahy medzi kontaktmi a účtami a následne vytvára jednotný profil kontaktu.

[!INCLUDE [m3-first-run-note](includes/m3-first-run-note.md)]

Prvých pár krokov je rovnakých ako pri zjednocovaní účtov.

## <a name="prerequisites"></a>Požiadavky

Záznamy účtov a kontaktov musia mať jedinečný kľúč (nazývaný cudzí kľúč), ktorý ich spája. Napríklad ID účtu, ktoré existuje v zázname účtu a zázname kontaktu, ktorý spája účet a kontakt.

## <a name="preview-limitations"></a>Obmedzenia ukážky

- Kontakty bez prepojenia na účet budú zrušené.
- Ak je účet deduplikovaný, víťazný záznam sa identifikuje na základe preferencií zlúčenia. Porazené záznamy nie sú vybrané, a preto sú vypustené. Kontakty spojené so stratou záznamov budú zrušené.
- Účet môže mať viacero kontaktov, ale kontakt je prepojený s jedným účtom.
- Atribúty kontaktu mapované v kroku sémantického mapovania sú jediné atribúty, ktoré sa môžu zobraziť na karte zákazníka. K dispozícii je však 17 atribútov.

## <a name="select-source-fields"></a>Vyberte zdrojové polia

1. Pod **Zjednotiť kontakty (ukážka)**, vyberte **Začať**.

1. [Vyberte entity a polia](map-entities.md) pre vaše zdroje kontaktných údajov vrátane primárnych kľúčov a typov atribútov.

1. Vyberte **Ďalej**.

## <a name="remove-duplicate-records"></a>Odstráňte duplicitné záznamy

1. voliteľne [definovať pravidlá deduplikácie](remove-duplicates.md) pre vami vybrané subjekty.

1. Vyberte **Ďalej**.

## <a name="match-conditions"></a>Podmienky zápasu

1. [Definujte poradie a pravidlá zápasu](match-entities.md) na párovanie medzi entitami.

1. Vyberte **Ďalej**.

## <a name="unify-contact-fields"></a>Zjednotiť polia kontaktov

1. [Skombinujte a vylúčte kontaktné polia](merge-entities.md).

1. Vyberte **Ďalej**.

## <a name="define-the-semantic-fields-for-unified-contacts"></a>Definovanie sémantických polí pre zjednotené kontakty

Tento krok v procese zjednotenia mapuje vaše zjednotené kontaktné polia na sémantické typy. V B-to-B sa na zákazníckych kartách zobrazujú účty. Po výbere karty sa zobrazia všetky kontakty spojené s účtom. Polia, ktoré mapujete v tomto kroku, sú polia, ktoré sa zobrazia na kartách.

1. Vyberte sémantický typ, ktorý sa mapuje na každé zjednotené pole. Vyberte **žiadne** ak sémantický typ nie je k dispozícii.

   :::image type="content" source="media/semantic_mapping.png" alt-text="Snímka obrazovky stránky sémantických polí na definovanie sémantických typov." lightbox="media/semantic_mapping.png":::

1. Po namapovaní všetkých zjednotených polí vyberte **Ďalšie**.

## <a name="set-the-relationship-between-contacts-and-accounts"></a>Nastavte vzťah medzi kontaktmi a účtami

Tento krok v procese zjednotenia prepojí vaše kontaktné údaje s príslušnými údajmi o účte.

1. Pre každú entitu zadajte nasledujúce informácie:

   - **Cudzí kľúč od kontaktnej entity** : Vyberte atribút, ktorý spája vašu kontaktnú entitu s účtom.
   - **Do účtovnej jednotky** : Vyberte entitu účtu priradenú ku kontaktu.

   :::image type="content" source="media/contact_relationship.png" alt-text="Snímka obrazovky stránky Vzťah na prepojenie entít kontaktu a účtu.":::

1. Vyberte **Ďalej**.

## <a name="review-contact-unification"></a>Skontrolujte zjednotenie kontaktov

Skontrolujte súhrn zmien, vytvorte jednotný profil a skontrolujte výsledky.

### <a name="review-and-create-contact-profiles"></a>Kontrola a vytváranie profilov kontaktov

Tento posledný krok v procese zjednotenia zobrazuje súhrn krokov v procese a poskytuje možnosť vykonať zmeny pred vytvorením profilu zjednoteného kontaktu.

:::image type="content" source="media/b2b_review_contacts.png" alt-text="Snímka obrazovky Kontrola a vytvorenie profilov kontaktov.":::

1. Vyberte **Upraviť** na ktoromkoľvek z krokov zjednotenia kontaktov, aby ste ich skontrolovali a vykonali akékoľvek zmeny.

1. Ak ste s výberom spokojní, vyberte si **Vytvorte profily kontaktov**. The **Zjednotiť** počas vytvárania jednotného profilu kontaktu.
  
   :::image type="content" source="media/b2b_unify_refreshing.png" alt-text="Snímka obrazovky stránky Zjednotiť kontakty s dlaždicami so zobrazením Zaradené do poradia alebo Obnovovanie.":::

   [!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

Dokončenie algoritmu zjednotenia nejaký čas trvá a konfiguráciu nemôžete zmeniť, kým sa nedokončí.

### <a name="view-the-results-of-contact-unification"></a>Pozrite si výsledky zjednotenia kontaktov

Po dokončení zjednotenia sa **Údaje** > **Zjednotiť** zobrazuje počet zjednotených profilov kontaktov. Výsledky každého kroku v procese zjednotenia sa zobrazia na každej dlaždici. Napríklad, **Zdrojové polia** zobrazuje počet mapovaných atribútov (polí) a **Duplicitné záznamy** zobrazuje počet nájdených duplicitných záznamov.

:::image type="content" source="media/unified_contacts.png" alt-text="Snímka obrazovky stránky Zjednotenie údajov po zjednotení kontaktov.":::

> [!TIP]
> The **Zodpovedajúce podmienky** dlaždice sa zobrazia iba vtedy, ak bolo vybratých viacero entít.

Odporúčame vám, aby ste si prezreli výsledky, najmä ich kvalitu [pravidlá zápasu](data-unification-update.md#manage-match-rules) a v prípade potreby ich upravte.

Keď treba, [vykonať zmeny v nastaveniach zjednotenia kontaktov](data-unification-update.md) a znova spustite zjednotený profil.

### <a name="verify-output-entities-from-data-unification"></a>Overte výstupné entity zo zjednotenia údajov

Ísť do **Údaje** > **entity** na overenie výstupných entít.

Entita jednotného profilu kontaktu, tzv *Kontaktný profil*, zobrazí sa v **Sémantické entity** oddiele. Prvý úspešný beh zjednotenia vytvorí zjednotené *Kontaktný profil* subjekt. Všetky nasledujúce behy rozširujú túto entitu.

The *KontaktyZákazník* entita (ukážka) sa vytvorí a zobrazí v **Profily** oddiele. Táto entita obsahuje kontaktné údaje bez prepojení na účty. Táto entita sa používa ako vstup do krokov sémantického mapovania a vzťahov pri zjednocovaní kontaktu.

Deduplikácia a konfigurácia entity sa vytvárajú a zobrazujú v **Systém** oddiele. Vytvorí sa deduplikovaná entita pre každú zo zdrojových entít s názvom **Deduplication_DataSource_Entity**. The **KontaktyConflationMatchPairs** entity obsahuje informácie o zhodách medzi entitami.

Entita deduplikovaného výstupu obsahuje nasledujúce informácie:
- ID/kľúče
  - Polia Primárny kľúč a Alternatívne ID. Pole Alternatívne ID pozostáva zo všetkých alternatívnych ID identifikovaných pre záznam.
  - Pole Deduplication_GroupId zobrazuje skupinu alebo klaster identifikovaný v rámci entity, ktorá zoskupuje všetky podobné záznamy na základe zadaných deduplikačných polí. Používa sa na účely spracovania systému. Ak nie sú zadané žiadne pravidlá manuálnej deduplikácie a uplatňujú sa pravidlá systému definované pre deduplikáciu, toto pole v entite výstupu deduplikácie nenájdete.
  - Deduplication_WinnerId: Toto pole obsahuje ID víťaza z identifikovaných skupín alebo klastrov. Ak je hodnota Deduplication_WinnerId rovnaká ako hodnota primárneho kľúča pre záznam, znamená to, že záznam je víťazným záznamom.
- Polia používané na definovanie pravidiel deduplikácie.
- Polia Pravidlo a Skóre označujú, ktoré z pravidiel deduplikácie sa použili a skóre vrátené algoritmom párovania.

## <a name="next-step"></a>Ďalší krok

Konfigurovať [činnosti](activities.md),[obohatenie](enrichment-hub.md), alebo [vzťahy](relationships.md) získať viac informácií o svojich kontaktoch.
