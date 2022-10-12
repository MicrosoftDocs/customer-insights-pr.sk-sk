---
title: Prehľad zdrojov údajov
description: Zistite, ako importovať alebo prijímať údaje z rôznych zdrojov.
ms.date: 09/29/2022
ms.subservice: audience-insights
ms.topic: overview
author: mukeshpo
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-data-sources
- ci-create-data-source
- customerInsights
ms.openlocfilehash: f89da3cf5b56e367bd673740f80cd82ec0907b28
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610071"
---
# <a name="data-sources-overview"></a>Prehľad zdrojov údajov

Dynamics 365 Customer Insights poskytuje pripojenia na prenos údajov zo širokej škály zdrojov. Pripojenie k zdroju údajov sa často označuje ako proces *prijímania údajov*. Po prijatí údajov môžete [zjednotiť](data-unification.md), generovať štatistiky a aktivovať údaje na vytváranie prispôsobených skúseností.

## <a name="add-or-edit-data-sources"></a>Pridajte alebo upravte zdroje údajov

Do Customer Insights môžete pripojiť alebo importovať zdroje údajov. Nižšie uvedené odkazy poskytujú pokyny na pridávanie a úpravu zdrojov údajov.

**Pripojte zdroj údajov**

Ak máte dáta pripravené v jednej z dátových služieb Azure od Microsoftu, Customer Insights sa môže jednoducho pripojiť k zdroj údajov bez toho, aby ste museli dáta znova prijímať. Vyberte jednu z nasledujúcich možností:
- [Azure Data Lake Storage(súbory csv alebo parkety v priečinku Common Data Model)](connect-common-data-model.md)
- [Azure Synapse Analytics(databázy jazier)](connect-synapse.md)
- [Microsoft Dataverse dátové jazero](connect-dataverse-managed-lake.md)

**Importovať a transformovať**

Ak používate lokálne zdroje údajov, Microsoft alebo údaje tretích strán, importujte a transformujte údaje pomocou Power Query konektory.
- [Power Query konektory](connect-power-query.md)

## <a name="review-data-sources"></a>Skontrolujte zdroje údajov

Ak bolo vaše prostredie nakonfigurované na používanie úložiska Customer Insights a používate lokálne zdroje údajov, použite Power Platform dátové toky. s Power Platform dátové toky, môžete zobraziť zdieľané dátové zdroje a dátové zdroje spravované inými. The **Zdroje dát** stránka uvádza zdroje údajov v troch sekciách:
- **Zdieľané** : Zdroje údajov, ktoré môžu spravovať všetci správcovia Customer Insights. Power Platform dátové toky, váš vlastný úložný účet a pripojenie k a Dataverse -managed data lake sú príklady zdieľaných zdrojov údajov.
- **Spravované mnou** :Power Platform dátové toky vytvorené a spravované iba vami. Ostatní správcovia Customer Insights môžu tieto toky údajov iba zobraziť, ale nemôžu ich upravovať, obnovovať ani odstraňovať.
- **Spravované inými** :Power Platform dátové toky vytvorené inými administrátormi. Môžete si ich iba prezerať. Uvádza vlastníka toku údajov, na ktorého sa môžete obrátiť so žiadosťou o pomoc.
> [!NOTE]
> Všetky entity môžu prezerať a používať iní používatelia. Zatiaľ čo zdroje údajov vlastní používateľ, ktorý ich vytvoril, výsledné entity z príjmu údajov môže použiť každý používateľ Customer Insights.

Ak vaše prostredie nepoužíva Power Platform dátové toky, **Zdroje dát** obsahuje iba zoznam všetkých zdrojov údajov. Nezobrazujú sa žiadne sekcie.

## <a name="manage-existing-data-sources"></a>Spravujte existujúce zdroje údajov

Ísť do **Údaje** > **Zdroje dát** zobraziť názov každého prijatého zdroj údajov, jeho stav a čas poslednej aktualizácie údajov pre daný zdroj. Zoznam zdrojov údajov môžete zoradiť podľa ľubovoľného stĺpca alebo pomocou vyhľadávacieho poľa nájsť zdroj údajov, ktorý chcete spravovať.

Ak chcete zobraziť dostupné akcie, vyberte zdroj údajov.

:::image type="content" source="media/data_sources_showmore.png" alt-text="Pridaný zdroj údajov.":::

- [**Upraviť**](#add-or-edit-data-sources) zdroj údajov na zmenu jeho vlastností.
- [**Obnoviť**](#refresh-data-sources) zdroj údajov na zahrnutie najnovších údajov.
- [**Obohatiť**](data-sources-enrichment.md) zdroj údajov pred zjednotením.
- **Odstrániť** zdroj údajov. Zdroj údajov je možné vymazať iba vtedy, ak sa údaje nepoužívajú pri žiadnom spracovaní, ako je zjednotenie, prehľady, aktivácie alebo exporty.

## <a name="refresh-data-sources"></a>Obnovenie zdrojov údajov

Zdroje údajov je možné obnovovať automaticky alebo podľa potreby manuálne. [Miestne zdroje údajov](connect-power-query.md#add-data-from-on-premises-data-sources) obnovovať podľa vlastných plánov, ktoré sú nastavené počas prijímania údajov. Tipy na riešenie problémov nájdete v časti [Riešenie problémov s PPDF Power Query -založené zdroj údajov problémy s obnovením](connect-power-query.md#troubleshoot-ppdf-power-query-based-data-source-refresh-issues).

V prípade pripojených zdrojov údajov prijíma príjem údajov najnovšie údaje dostupné z tohto zdroj údajov.

Ísť do **Admin** > **systém** > [**Rozvrh**](schedule-refresh.md) na konfiguráciu systémovo naplánovaných obnovení vašich prijatých zdrojov údajov.

Ak chcete obnoviť zdroj údajov na požiadanie:

1. Prejdite do **Údaje** > **Zdroje údajov**.

1. Vyberte zdroj údajov, ktorý chcete obnoviť, a vyberte **Obnoviť**. Zdroj údajov je teraz spustený na účely manuálneho obnovenia. Obnovením zdroja údajov sa aktualizuje schéma entity aj údaje pre všetky entity uvedené v zdroji údajov.

1. Vyberte stav, ktorý chcete otvoriť **Podrobnosti o pokroku** panel a zobraziť priebeh. Ak chcete úlohu zrušiť, vyberte **Zrušiť úlohu** v spodnej časti tabule.

## <a name="corrupt-data-sources"></a>Poškodené zdroje údajov

Prijímané údaje môžu mať poškodené záznamy, ktoré môžu spôsobiť dokončenie procesu prijímania údajov s chybami alebo upozorneniami.

> [!NOTE]
> Ak sa príjem údajov dokončí s chybami, následné spracovanie (napríklad zjednotenie alebo vytvorenie aktivity), ktoré využíva toto zdroj údajov, bude preskočené. Ak je príjem ukončený s upozorneniami, následné spracovanie pokračuje, ale niektoré záznamy nemusia byť zahrnuté.

Tieto chyby je možné vidieť v detailoch úlohy.

:::image type="content" source="media/corrupt-task-error.png" alt-text="Podrobnosti úlohy zobrazujúce chybu poškodených údajov.":::

Poškodené záznamy sa zobrazujú v entitách vytvorených systémom.

### <a name="fix-corrupt-data"></a>Opravte poškodené údaje

1. Ak chcete zobraziť poškodené údaje, prejdite na **Údaje** > **entity** a hľadajte poškodené entity v **Systém** oddiele. Schéma pomenovania poškodených entít: 'Názov_zdroja_Entity_corrupt'.

1. Vyberte skorumpovanú entitu a potom **Údaje** tab.

1. Identifikujte poškodené polia v zázname a dôvod.

   :::image type="content" source="media/corruption-reason.png" alt-text="Dôvod korupcie." lightbox="media/corruption-reason.png":::

   > [!NOTE]
   > **Údaje** > **entity** zobraziť iba časť poškodených záznamov. Ak chcete zobraziť všetky poškodené záznamy, exportujte súbory do kontajnera v účte úložiska pomocou [Proces exportu Customer Insights](export-destinations.md). Ak ste použili svoj vlastný účet úložiska, môžete sa tiež pozrieť do priečinka Customer Insights vo svojom účte úložiska.

1. Opravte poškodené údaje. Napríklad pre zdroje údajov Azure Data Lake, [opravte údaje v Data Lake Storage alebo aktualizujte typy údajov v súbore manifest/model.json](connect-common-data-model.md#common-reasons-for-ingestion-errors-or-corrupt-data). Pre Power Query zdroje údajov, opravte údaje v zdrojovom súbore a [opravte typ údajov krok transformácie](connect-power-query.md#data-type-does-not-match-data) na **Power Query - Upraviť otázky** stránku.

Po ďalšom obnovení zdroja údajov sa opravené záznamy prijmú v nástroji Customer Insights a odošlú sa do následných procesov.

V stĺpci „deň narodenia“ je napríklad nastavený dátový typ ako „dátum“. Záznam zákazníka má dátum narodenia zapísaný ako „01/01/19777“. Systém označí tento záznam ako poškodený. Zmeňte dátum narodenia v zdrojovom systéme na „1977“. Po automatickom obnovení zdrojov údajov má pole teraz platný formát a záznam sa odstráni z poškodenej entity.

[!INCLUDE [footer-include](includes/footer-banner.md)]
