---
title: Používanie zdrojov údajov na príjem údajov
description: Prečítajte si, ako importovať údaje z rôznych zdrojov.
ms.date: 11/01/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: 27cbd0346b1219c7812f4b90327dd27b645c2b8e
ms.sourcegitcommit: 834651b933b1e50e7557d44f926a3fb757c1f83a
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 11/02/2021
ms.locfileid: "7732174"
---
# <a name="data-sources-overview"></a>Prehľad zdrojov údajov

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Funkcia štatistík publika v Dynamics 365 Customer Insights sa pripája k údajom zo širokej škály zdrojov. Pripojenie k zdroju údajov sa často označuje ako proces *prijímania údajov*. Po prijatí údajov ich môžete [zjednotiť](data-unification.md) a podniknúť s nimi kroky.

## <a name="add-a-data-source"></a>Pridať zdroj údajov

Prečítajte si podrobné články o tom, ako pridať zdroj údajov, podľa toho, ktorú možnosť si vyberiete.

Zdroj údajov môžete pridať tromi hlavnými spôsobmi:

- [Prostredníctvom množstva konektorov Power Query](connect-power-query.md)
- [Z priečinka Common Data Model](connect-common-data-model.md)
- [Z vlastného jazera Microsoft Dataverse](connect-dataverse-managed-lake.md)

## <a name="add-data-from-on-premises-data-sources"></a>Pridajte údaje z lokálny zdrojov údajov

Prijímanie údajov z lokálny zdrojov údajov v štatistikách publika je podporované na základe Microsoft Power Platform tokov údajov. Dátové toky je možné povoliť v Customer Insights pomocou [poskytnutie adresy URL prostredia Microsoft Dataverse](create-environment.md) pri nastavovaní prostredia.

Zdroje údajov, ktoré sa vytvoria po priradení Dataverse prostredia k Customer Insights, budú používať [Power Platform toky údajov](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) predvolene. Dátové toky podporujú lokálne pripojenie pomocou brány údajov. Odstráňte a znova vytvorte zdroje údajov, ktoré existovali pred pridružením prostredia Dataverse [použite dátové brány lokálny](/data-integration/gateway/service-gateway-app).

Dátové brány z existujúceho prostredia Power BI alebo Power Apps budú viditeľné a môžete ich znova použiť v Customer Insights. Stránka zdrojov údajov zobrazuje prepojenia na prechod do prostredia Microsoft Power Platform, kde si môžete zobraziť a nakonfigurovať brány údajov lokálny.

## <a name="review-ingested-data"></a>Kontrola prijatých údajov

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
