---
title: Správa povolení používateľov
description: Ďalšie informácie povoleniach a rolách používateľov.
ms.date: 02/09/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
searchScope:
- ci-permissions
- ci-system-security
- customerInsights
ms.openlocfilehash: b80f07dfa734f4dd762bd711151a7045f24bed7d
ms.sourcegitcommit: cf74b8c20d88eb96e1ac86e18cd44fe27aad5ab9
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 04/28/2022
ms.locfileid: "8653587"
---
# <a name="user-permissions"></a>Povolenia používateľa

The **Povolenia** je to, kde nastavíte roly a povolenia na používanie Customer Insights.

Ak chcete stránku zobraziť, musíte mať oprávnenie správcu. Ak chcete získať prístup na stránku povolení, prejdite na **Admin** > **Bezpečnosť** > **Používatelia**.

Existujú tri typy rol:

## <a name="viewer"></a>Divák

- Preskúmajte prehľady a segmenty v rámci stránok **Domov** a **Segmenty**.
- Vyhľadávajte a filtrujte profily zákazníkov pomocou stránky **Zákazníci**. Polia sa musia dať prehľadávať.
- Zobrazte si a preskúmajte stránku **Rozšírenie**.
- Preskúmajte a exportujte entity pomocou stránky **Entity**.
- Zobrazte stav systémových procesov pomocou stránky **Systém**.
- Zobrazenie exportov na stránke **Exporty**.
- Nainštalujte a používajte tabuľu **Power BI Customer Insights**.

## <a name="contributor"></a>Prispievateľ

- Všetky povolenia, ktoré má Zobrazovač k dispozícii.
- Načítanie a transformácia údajov pomocou stránky **Zdroje údajov**.
- Vyplňte sekcie *Zjednotenie údajov* (**Mapovanie**, **Zosúladenie** a **Zlúčenie**), ktoré vedú k jednotnej entite profilu zákazníka.
- Definujte **Vzťahy** a **Aktivity**.
- Vytvárajte segmenty pomocou stránky **Segmenty**.
- Vytvárajte miery pomocou stránky **Miery**.
- Spravujte konfiguráciu a obohacujte profily zákazníkov zo stránky **Obohatenie** (iba pre obohatenie prvej strany).
- Spravujte a vytvárajte exporty na základe pripojení zdieľaných s prispievateľmi. [Získajte viac informácií o tom, ako správcovia umožňujú prispievateľom používať pripojenie na export](connections.md#allow-contributors-to-use-a-connection-for-exports).

## <a name="admin"></a>Správca

- Všetky povolenia, ktoré má Prispievateľ k dispozícii.
- Zmeňte nastavenia na stránke **Systém** vrátane pracovného jazyka a plánov obnovy pre vaše systémové procesy.
- Zobrazujte a pridávajte povolenia pomocou stránky **Povolenia**.
- Nastavte definície vyhľadávania a filtrovania pre stránku Zákazníci pomocou stránky **Index vyhľadávania a filtrovania**(prístupná cez stránku **Zákazníci**).
- Spravujte pripojenia a povoľte ich pre ďalšie roly používateľov na stránke **Pripojenia**.
- Spravujte konfiguráciu a obohacujte profily zákazníkov zo stránky **Obohatenie** (pre všetky obohatenia).
- Spravujte a vytvárajte exporty na stránke **Exporty**.
- Inštalácia a používanie **doplnku Karta zákazníka**.
- Pridajte a použite **konektor Power Apps**.
- Povoľte použitie [rozhraní rozhrania API v službe Customer Insights](apis.md).
- [Priraďte vlastníctvo prostredia](manage-environments.md#change-the-owner-of-an-environment) inému správcovi.

## <a name="admin-owner"></a>Správca (majiteľ)

- Všetky povolenia dostupné pre správcu.
- [Obnoviť a odstrániť](manage-environments.md#reset-an-existing-environment) prostredie.

## <a name="assign-roles-and-permissions"></a>Priradenie rolí a povolení

1. Ísť do **Admin** > **Bezpečnosť** > **Používatelia***.

1. Výberom možnosti **Pridať používateľov** otvorte tablu **Pridať/upraviť povolenia**.

1. Použite pole **Vyhľadávanie** na vyhľadanie používateľa alebo skupiny Azure Active Directory, ktorých povolenia chcete upraviť. Vyberte a **Rolu** na priradenie k tomuto používateľovi alebo skupine.

1. Vyberte položku **Uložiť**. Aktuálne prostredie sa bude automaticky zdieľať s používateľom alebo členmi skupiny, ktorých povolenia ste zmenili. Používatelia majú prístup k aplikácii Customer Insights a môžu pracovať podľa svojej zadanej roly.

## <a name="view-current-permissions"></a>Zobrazenie aktuálnych povolení

Ísť do **Admin** > **Bezpečnosť** > **Používatelia** aby ste videli, aké roly sú momentálne aktívne.

- Stĺpec **Typ** určuje jedného používateľa, skupinu alebo aplikáciu. Systém podporuje jednotlivých používateľov a skupiny.
- Roly sú špecifikované v stĺpci **Rola**.
- Ak chcete zoradiť výsledky podľa hodnoty v tomto stĺpci, vyberte ľubovoľný názov stĺpca.
- Pomocou poľa **Vyhľadať** v hornej časti stránky vyhľadajte konkrétnych používateľov.


[!INCLUDE [footer-include](includes/footer-banner.md)]
