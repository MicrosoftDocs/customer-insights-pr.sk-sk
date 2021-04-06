---
title: Vzťahy medzi entitami a cestami entít
description: Vytvárajte a spravujte vzťahy medzi entitami z viacerých zdrojov údajov.
ms.date: 04/14/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: c25bfcb8e2a8223498dd1a5e8cfb3712a40ab85e
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 03/15/2021
ms.locfileid: "5595231"
---
# <a name="relationships-between-entities"></a>Vzťahy medzi entitami

Vzťahy vám pomôžu prepojiť entity a vygenerovať graf vašich údajov, keď entity zdieľajú spoločný identifikátor (cudzí kľúč), na ktorý je možné odkazovať z jednej entity na druhú. Pripojené entity vám umožňujú definovať segmenty a miery na základe viacerých zdrojov údajov.

Existujú dva typy vzťahov. Neupraviteľné systémové vzťahy, ktoré sa vytvárajú automaticky, a vlastné vzťahy vytvárané a konfigurované používateľmi.

Počas procesov zosúlaďovania a zlúčenia sa vytvárajú systémové vzťahy za scénami na základe inteligentného zosúlaďovania. Tieto vzťahy pomáhajú priraďovať záznamy profilu zákazníka k záznamom iných zodpovedajúcich entít. Nasledujúca schéma ilustruje vytvorenie troch systémových vzťahov, keď sa entita zákazníka zosúladí s ďalšími entitami, aby sa vytvorila konečná entita profilu zákazníka.

> [!div class="mx-imgBorder"]
> ![Vytváranie vzťahu](media/relationships-entities-merge.png "Vytváranie vzťahu")

- **Vzťah *CustomerToContact*** bol vytvorený medzi entitou zákazníka a entitou kontaktu. Entita zákazníka získa kľúčové pole **Contact_contactId**, ktoré sa bude vzťahovať na kľúčové pole entity kontaktu **contactID**.
- **Vzťah *CustomerToAccount*** bol vytvorený medzi entitou zákazníka a entitou obchodného vzťahu. Entita zákazníka získa kľúčové pole **ccount_accountId**, ktoré sa bude vzťahovať na kľúčové pole entity obchodného vzťahu **accountId**.
- **Vzťah *CustomerToWebAccount*** bol vytvorený medzi entitou zákazníka a entitou WebAccount. Entita zákazníka získa kľúčové pole **WebAccount_webaccountId**, ktoré sa bude vzťahovať na kľúčové pole entity WebAccount **webaccountId**.

## <a name="create-a-relationship"></a>Vytvorenie vzťahu

Definujte vlastné vzťahy na stránke **Vzťahy**. Každý vzťah pozostáva zo zdrojovej entity (entity, ktorá má cudzí kľúč) a cieľovej entity (entity, na ktorú cudzí kľúč zdrojovej entity odkazuje).

1. V prehľadoch cieľových skupín prejdite na **Údaje** > **Vzťahy**.

2. Vyberte **Nový vzťah**.

3. Na table **Pridať vzťah** zadajte nasledovné informácie:

   > [!div class="mx-imgBorder"]
   > ![Zadajte podrobnosti vzťahu](media/relationships-add.png "Zadajte podrobnosti vzťahu")

   - **Názov vzťahu**: Názov, ktorý odráža účel vzťahu (napr. **AccountWebLogs**).
   - **Popis**: Popis vzťahu.
   - **Zdrojová entita**: Vyberte entitu, ktorá sa použije ako zdroj vo vzťahu (napríklad WebLog).
   - **Kardinalita**: Vyberte kardinalitu záznamov zdrojovej entity. Napríklad „veľa“ znamená, že viac záznamov Weblog súvisí s jedným WebAccount.
   - **Pole zdrojového kľúča**: Toto predstavuje pole cudzieho kľúča v zdrojovej entite. WebLog má napríklad pole cudzieho kľúča **accountId**.
   - **Cieľová entita**: Vyberte entitu, ktorá sa použije ako cieľ vo vzťahu (napríklad WebAccount).
   - **Kardinalita cieľa**: Vyberte kardinalitu záznamov cieľovej entity. Napríklad „jeden“ znamená, že viac záznamov Weblog súvisí s jedným WebAccount.
   - **Pole cieľového kľúča**: Toto pole predstavuje kľúčové pole cieľovej entity. WebAccount má napríklad pole cudzieho kľúča **accountId**.

> [!NOTE]
> Podporované sú iba vzťahy „mnoho k jednému“ a „jeden k jednému“. Vzťahy „mnoho k mnohým“ sa môžu vytvoriť pomocou dvoch vzťahov „mnoho k mnohým“ viacerými a entity prepojenia (entita, ktorá sa používa na prepojenie zdrojovej a cieľovej entity).

## <a name="delete-a-relationship"></a>Odstránenie vzťahu

1. V prehľadoch cieľových skupín prejdite na **Údaje** > **Vzťahy**.

2. Začiarknite políčka vzťahov, ktoré chcete odstrániť.

3. Vyberte **Odstrániť** v hornej časti tabuľky **Vzťahy**.

4. Potvrďte odstránenie.

## <a name="next-step"></a>Nasledujúci krok

Systémové a vlastné vzťahy sa používajú na vytváranie segmentov založených na viacerých zdrojoch údajov, ktoré už nie sú zastrešené. Ďalšie informácie nájdete v časti [Segmenty](segments.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]