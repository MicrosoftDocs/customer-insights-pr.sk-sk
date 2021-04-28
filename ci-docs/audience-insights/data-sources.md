---
title: Používanie zdrojov údajov na príjem údajov
description: Prečítajte si, ako importovať údaje z rôznych zdrojov.
ms.date: 04/12/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 0fc13d3ac0a5176637b6fe481dabe0b2aec11649
ms.sourcegitcommit: d89b19b2a3497722b78362aeee688ae7e94915d9
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 04/13/2021
ms.locfileid: "5887913"
---
# <a name="data-sources-overview"></a>Prehľad zdrojov údajov

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Funkcia prehľadov cieľových skupín v službe Dynamics 365 Customer Insights sa pripája sa k údajom zo širokej množiny zdrojov. Pripojenie k zdroju údajov sa často označuje ako proces *prijímania údajov*. Po prijatí údajov ich môžete [zjednotiť](data-unification.md) a podniknúť s nimi kroky.

## <a name="add-a-data-source"></a>Pridať zdroj údajov

Prečítajte si podrobné články o tom, ako pridať zdroj údajov, podľa toho, ktorú možnosť si vyberiete.

Zdroj údajov môžete pridať tromi hlavnými spôsobmi:

- [Prostredníctvom množstva konektorov Power Query](connect-power-query.md)
- [Z priečinka Common Data Model](connect-common-data-model.md)
- [Z jazera Common Data Service](connect-common-data-service-lake.md)

## <a name="add-data-from-on-premises-data-sources"></a>Pridajte údaje z lokálny zdrojov údajov

Na základe je podporované prijímanie údajov z lokálnych zdrojov údajov v prehľadoch cieľovej skupiny tokov údajov Power Platform. Toky údajov je možné v nástroji Customer Insights povoliť používateľom [poskytuje adresu URL prostredia Microsoft Dataverse](manage-environments.md#create-an-environment-in-an-existing-organization) pri nastavovaní prostredia.

Zdroje údajov, ktoré sa predvolene vytvoria po priradení a prostredí Dataverse s nástrojom Customer Insights [Toky údajov Power Platform](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365). Dátové toky podporujú lokálne pripojenie pomocou brány údajov. Odstrániť a znovu vytvoriť zdroje údajov, ktoré existovali pred prostredím Dataverse bolo spojené s používaním lokálnych dátových brán.

Dátové brány z existujúceho prostredia Power BI alebo Power Apps bude viditeľné a môžete ho znova použiť v nástroji Customer Insights. Na stránke zdrojov údajov sú zobrazené odkazy, pomocou ktorých môžete prejsť do prostredia Power Platform, kde môžete zobraziť a nakonfigurovať lokálne dátové brány.

:::image type="content" source="media/data-sources-onpremises-gateways.png" alt-text="Snímka obrazovky zo stránky zdrojov údajov zobrazujúci odkazy smerujúce do prostredia Power Platform.":::

## <a name="review-ingested-data"></a>Kontrola prijatých údajov

Uvidíte názov každého prijatého zdroj údajov, jeho stav a poslednú aktualizáciu údajov pre tento zdroj. Zoznam zdrojov údajov môžete zoradiť podľa každého stĺpca.

> [!div class="mx-imgBorder"]
> ![Pridaný zdroj údajov](media/configure-data-datasource-added.png "Pridaný zdroj údajov")

|Status  |Popis  |
|---------|---------|
|Úspešné   |Zdroj údajov bol úspešne prijatý, ak je v stĺpci **Obnovené** uvedený čas.
|Nespustené   |Zdroj údajov zatiaľ nemá žiadne prijaté údaje alebo je stále v režime konceptu.         |
|Obnovuje sa    |Prebieha prijímanie údajov. Túto operáciu môžete zrušiť tak, že v stĺpci **Akcie** vyberiete **Zastaviť obnovovanie**. Zastavenie obnovovania zdroja údajov sa obnoví do posledného stavu obnovenia.       |
|Zlyhalo     |Pri prijímaní údajov nastali chyby.         |

Vyberte hodnotu v stĺpci **Stav** ľubovoľného zdroja údajov, aby ste skontrolovali ďalšie podrobnosti. V table **Podrobnosti o postupe** rozbaľte **Zdroje údajov**. Výberom položky **Zobraziť podrobnosti** zobrazíte viac informácií o stave obnovenia vrátane podrobností o chybách a následných aktualizáciách procesu.

Načítanie údajov môže chvíľu trvať. Po úspešnom obnovení môžu byť prijaté údaje preskúmané na stránke **Entity**. Ďalšie informácie nájdete v časti [Entity](entities.md).

## <a name="refresh-a-data-source"></a>Obnovte zdroj údajov

Zdroje údajov je možné obnovovať automaticky alebo podľa potreby manuálne. 

Prejdite na časť **Správca** > **Systém** > [**Plánovať**](system.md#schedule-tab) a nakonfigurujte plánované obnovenie všetkých vašich prijatých zdrojov údajov.

Ak chcete obnoviť zdroj údajov na požiadanie, postupujte takto:

1. V prehľadoch cieľových skupín prejdite na **Údaje** > **Zdroje údajov**

2. Vyberte zvislé tri bodky vedľa zdroja údajov, ktorý chcete obnoviť, a vyberte položku **Obnoviť** z rozbaľovacieho zoznamu.

3. Zdroj údajov je teraz spustený na účely manuálneho obnovenia. Obnovením zdroja údajov sa aktualizuje schéma entity aj údaje pre všetky entity uvedené v zdroji údajov.

4. Vyberte položku **Zastaviť obnovovanie**, ak chcete zrušiť existujúce obnovenie a zdroj údajov sa vráti do posledného stavu obnovenia.

## <a name="delete-a-data-source"></a>Odstránenie zdroja údajov

1. V prehľadoch cieľových skupín prejdite na **Údaje** > **Zdroje údajov**.

2. Vyberte zvislé tri bodky vedľa zdroja údajov, ktorý chcete odstrániť, a vyberte **Odstrániť** z rozbaľovacej ponuky.

3. Potvrďte odstránenie.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
