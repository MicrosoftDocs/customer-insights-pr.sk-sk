---
title: Používanie zdrojov údajov na príjem údajov
description: Prečítajte si, ako importovať údaje z rôznych zdrojov.
ms.date: 03/18/2022
ms.subservice: audience-insights
ms.topic: overview
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-data-sources
- ci-create-data-source
- customerInsights
ms.openlocfilehash: 9cf97c3e30d7501ba1f188a0e25a1a103299aa7f
ms.sourcegitcommit: a8e99cf8b23ccc00d76c1dee22afd808a160a5c8
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 03/22/2022
ms.locfileid: "8464093"
---
# <a name="data-sources-overview"></a>Prehľad zdrojov údajov



Funkcia prehľadov cieľových skupín v službe Dynamics 365 Customer Insights sa pripája sa k údajom zo širokej množiny zdrojov. Pripojenie k zdroju údajov sa často označuje ako proces *prijímania údajov*. Po prijatí údajov ich môžete [zjednotiť](data-unification.md) a podniknúť s nimi kroky.

## <a name="add-a-data-source"></a>Pridať zdroj údajov

V podrobných článkoch nájdete informácie o tom, ako pridať zdroj údajov v závislosti od zvolenej možnosti.

Môžete pridať nasledujúce zdroje údajov:

- [Cez desiatky Power Query konektory](connect-power-query.md)
- [Z priečinka Common Data Model](connect-common-data-model.md)
- [Z jazera Microsoft Dataverse](connect-dataverse-managed-lake.md)
- [Od an Azure Synapse Analytics databázy](connect-synapse.md)

> [!NOTE]
> Ak používate skúšobnú verziu, sekcia metód importu obsahuje a **Knižnica údajov Customer Insights** možnosť. Túto možnosť vyberte, ak chcete vybrať vzorovú množinu údajov dostupnú pre rôzne odvetvia. Viac informácií nájdete v časti [Dynamics 365 Customer Insights súdny proces](../trial-signup.md).

## <a name="add-data-from-on-premises-data-sources"></a>Pridajte údaje z lokálny zdrojov údajov

Na základe je podporované prijímanie údajov z lokálnych zdrojov údajov v prehľadoch cieľovej skupiny tokov údajov Microsoft Power Platform. Dátové toky môžete povoliť v Customer Insights pomocou [poskytovanie Microsoft Dataverse URL prostredia](create-environment.md) pri nastavovaní prostredia.

Zdroje údajov, ktoré sa vytvoria po priradení a Dataverse prostredie s využitím Customer Insights [Power Platform dátové toky](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) predvolene. Dátové toky podporujú lokálne pripojenie pomocou brány údajov. Môžete odstrániť a znova vytvoriť zdroje údajov, ktoré existovali pred a Dataverse prostredie bolo spojené [pomocou dátových brán lokálny](/data-integration/gateway/service-gateway-app).

Dátové brány z existujúceho prostredia Power BI alebo Power Apps bude viditeľné a môžete ho znova použiť v nástroji Customer Insights. Na stránke zdrojov údajov sú zobrazené odkazy smerujúce do prostredia Microsoft Power Platform, v ktorom si môžete prezerať a konfigurovať lokálne brány údajov.

> [!IMPORTANT]
> Uistite sa, že sú vaše brány aktualizované na najnovšiu verziu. Môžete nainštalovať aktualizáciu a prekonfigurovať bránu z výzvy zobrazenej na obrazovke brány priamo alebo [stiahnite si najnovšiu verziu](https://powerapps.microsoft.com/downloads/). Ak nepoužívate najnovšiu verziu brány, obnovenie toku údajov zlyhá s chybovými hláseniami, ako napr **Kľúčové slovo nie je podporované: konfiguračné vlastnosti. Názov parametra: kľúčové slovo**.

## <a name="review-ingested-data"></a>Kontrola prijatých údajov
Ak vaše prostredie obsahuje Power Platform dátové toky, **Zdroje dát** stránka obsahuje tri sekcie: 
- **Zdieľané** : Zdroje údajov, ktoré môžu spravovať všetci správcovia Customer Insights. Power BI dátové toky, váš vlastný úložný účet a pripojenie k a Dataverse -managed data lake sú príklady zdieľaných zdrojov údajov.
- **Spravované mnou** :Power Platform dátové toky vytvorené a môžete ich spravovať iba vy. Ostatní správcovia Customer Insights môžu tieto toky údajov iba zobraziť, ale nemôžu ich upravovať, obnovovať ani odstraňovať.
- **Spravované inými** :Power Platform dátové toky vytvorené inými správcami. Môžete si ich iba prezerať. Uvádza vlastníka toku údajov, na ktorého sa môžete obrátiť so žiadosťou o pomoc.
> [!NOTE]
> Všetky entity môžu prezerať a používať iní používatelia. Používateľský kontext sa vzťahuje iba na zdroje údajov a nie na entity, ktoré sú výsledkom týchto tokov údajov.

Ak nie Power Platform sa používajú toky údajov, neuvidíte žiadne skupiny ani sekcie. The **Zdroje dát** obsahuje iba zoznam všetkých zdrojov údajov.

Uvidíte názov každého prijatého zdroj údajov, jeho stav a poslednú aktualizáciu údajov pre tento zdroj. Zoznam zdrojov údajov môžete zoradiť podľa každého stĺpca.

> [!div class="mx-imgBorder"]
> ![Pridaný zdroj údajov.](media/configure-data-datasource-added.png "Pridaný zdroj údajov")

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

Načítanie údajov môže chvíľu trvať. Po úspešnom obnovení môžu byť prijaté údaje preskúmané na stránke **Entity**. Ďalšie informácie nájdete v časti [Entity](entities.md).

## <a name="refresh-a-data-source"></a>Obnovte zdroj údajov

Zdroje údajov je možné obnovovať automaticky alebo podľa potreby manuálne. 

Prejdite na časť **Správca** > **Systém** > [**Plánovať**](system.md#schedule-tab) a nakonfigurujte plánované obnovenie všetkých vašich prijatých zdrojov údajov.

Ak chcete obnoviť zdroj údajov na požiadanie, postupujte takto:

1. V prehľadoch cieľových skupín prejdite na **Údaje** > **Zdroje údajov**.

2. Vyberte zvislé tri bodky vedľa zdroja údajov, ktorý chcete obnoviť, a z rozbaľovacieho zoznamu vyberte položku **Obnoviť**.

3. Zdroj údajov je teraz spustený na účely manuálneho obnovenia. Obnovením zdroja údajov sa aktualizuje schéma entity aj údaje pre všetky entity uvedené v zdroji údajov.

4. Vyberte položku **Zastaviť obnovovanie**, ak chcete zrušiť existujúce obnovenie a zdroj údajov sa vráti do posledného stavu obnovenia.

## <a name="delete-a-data-source"></a>Odstránenie zdroja údajov

1. V prehľadoch cieľových skupín prejdite na **Údaje** > **Zdroje údajov**.

2. Vyberte zvislé tri bodky vedľa zdroja údajov, ktorý chcete odstrániť, a z rozbaľovacieho zoznamu vyberte položku **Odstrániť**.

3. Potvrďte odstránenie.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
