---
title: Prehľad zdrojov údajov
description: Zistite, ako importovať alebo prijímať údaje z rôznych zdrojov.
ms.date: 05/18/2022
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
ms.openlocfilehash: fbe44f655bdbc20ef7f0956022395e2dcb570adf
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 06/29/2022
ms.locfileid: "9051472"
---
# <a name="data-sources-overview"></a>Prehľad zdrojov údajov

Dynamics 365 Customer Insights poskytuje pripojenia na prenos údajov zo širokej škály zdrojov. Pripojenie k zdroju údajov sa často označuje ako proces *prijímania údajov*. Po prijatí údajov môžete [zjednotiť](data-unification.md), generovať štatistiky a aktivovať údaje na vytváranie prispôsobených skúseností.

## <a name="add-data-sources"></a>Pridať zdroje údajov

Do Customer Insights môžete pripojiť alebo importovať zdroje údajov. Nižšie uvedené odkazy poskytujú pokyny na pridávanie zdrojov údajov.

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
- **Spravované inými** :Power Platform dátové toky vytvorené inými administrátormi. Môžete si ich len prezerať. Uvádza vlastníka toku údajov, na ktorého sa môžete obrátiť so žiadosťou o pomoc.
> [!NOTE]
> Všetky entity môžu prezerať a používať iní používatelia. Zatiaľ čo zdroje údajov vlastní používateľ, ktorý ich vytvoril, výsledné entity z príjmu údajov môže použiť každý používateľ Customer Insights.

Ak vaše prostredie nepoužíva Power Platform dátové toky, **Zdroje dát** obsahuje iba zoznam všetkých zdrojov údajov. Nezobrazujú sa žiadne sekcie.

Ísť do **Údaje** > **Zdroje dát** zobraziť názov každého prijatého zdroj údajov, jeho stav a čas poslednej aktualizácie údajov pre daný zdroj. Zoznam zdrojov údajov môžete zoradiť podľa každého stĺpca.

:::image type="content" source="media/configure-data-datasource-added.png" alt-text="Pridaný zdroj údajov.":::

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

Načítanie údajov môže chvíľu trvať. Po úspešnom obnovení môžu byť prijaté údaje preskúmané na stránke **Entity**. Ďalšie informácie nájdete v časti [Entity](entities.md).

## <a name="refresh-data-sources"></a>Obnovenie zdrojov údajov

Zdroje údajov je možné obnovovať automaticky alebo podľa potreby manuálne. [Miestne zdroje údajov](connect-power-query.md#add-data-from-on-premises-data-sources) obnovovať podľa vlastných plánov, ktoré sú nastavené počas prijímania údajov. V prípade pripojených zdrojov údajov prijíma príjem údajov najnovšie údaje dostupné z tohto zdroj údajov.

Ísť do **Admin** > **Systém** > [**Rozvrh**](system.md#schedule-tab) na konfiguráciu systémovo naplánovaných obnovení vašich prijatých zdrojov údajov.

Ak chcete obnoviť zdroj údajov na požiadanie, postupujte takto:

1. Prejdite do **Údaje** > **Zdroje údajov**.

1. Vyberte zvislú elipsu (&vellip;) vedľa zdroj údajov, ktorý chcete obnoviť a vybrať **Obnoviť** z rozbaľovacieho zoznamu. Zdroj údajov je teraz spustený na účely manuálneho obnovenia. Obnovením zdroja údajov sa aktualizuje schéma entity aj údaje pre všetky entity uvedené v zdroji údajov.

1. Vyberte položku **Zastaviť obnovovanie**, ak chcete zrušiť existujúce obnovenie a zdroj údajov sa vráti do posledného stavu obnovenia.

## <a name="delete-a-data-source"></a>Odstránenie zdroja údajov

Zdroj údajov je možné vymazať iba vtedy, ak sa údaje nepoužívajú pri žiadnom spracovaní, ako je zjednotenie, prehľady, aktivácie alebo exporty.

1. Prejdite do **Údaje** > **Zdroje údajov**.

2. Vyberte zvislú elipsu (&vellip;) vedľa zdroj údajov, ktorý chcete odstrániť a vybrať **Odstrániť** z rozbaľovacej ponuky.

3. Potvrďte odstránenie.


[!INCLUDE [footer-include](includes/footer-banner.md)]
