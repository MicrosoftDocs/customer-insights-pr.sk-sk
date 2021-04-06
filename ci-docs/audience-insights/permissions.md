---
title: Správa povolení používateľov
description: Ďalšie informácie povoleniach a rolách používateľov.
ms.date: 10/27/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: e58bb1a3bd4c0920ff984daffabbf16162185f3d
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 03/15/2021
ms.locfileid: "5595721"
---
# <a name="user-permissions"></a>Povolenia používateľa

Stránka **Povolenia** je miesto, kde nastavíte roly a povolenia na používanie prehľadov o cieľovej skupine.

Ak chcete stránku zobraziť, musíte mať oprávnenie správcu. Ak chcete prejsť na stránku povolení v prehľadoch cieľovej skupiny, prejdite na **Správca** > **Povolenia**.

Existujú tri typy rol:

## <a name="viewer"></a>Divák

- Preskúmajte prehľady a segmenty v rámci stránok **Domov** a **Segmenty**.
- Vyhľadávajte a filtrujte profily zákazníkov pomocou stránky **Zákazníci**. Polia sa musia dať prehľadávať.
- Zobrazte si a preskúmajte stránku **Rozšírenie**.
- Preskúmajte a exportujte entity pomocou stránky **Entity**.
- Zobrazte stav systémových procesov pomocou stránky **Systém**.
- Exportujte segmenty zo stránky **Segmenty**.
- Nainštalujte a používajte tabuľu **Power BI Customer Insights**.

## <a name="contributor"></a>Prispievateľ

- Všetky povolenia, ktoré má Zobrazovač k dispozícii.
- Načítanie a transformácia údajov pomocou stránky **Zdroje údajov**.
- Vyplňte sekcie *Zjednotenie údajov* (**Mapovanie**, **Zosúladenie** a **Zlúčenie**), ktoré vedú k jednotnej entite profilu zákazníka.
- Definujte **Vzťahy** a **Aktivity**.
- Vytvárajte segmenty pomocou stránky **Segmenty**.
- Vytvárajte miery pomocou stránky **Miery**.
- Spravujte konfiguráciu a obohacujte profily zákazníkov zo stránky **Obohatenie** (iba pre obohatenie prvej strany).

## <a name="administrator"></a>Správca

- Všetky povolenia, ktoré má Prispievateľ k dispozícii.
- Zmeňte nastavenia na stránke **Systém** vrátane pracovného jazyka a plánov obnovy pre vaše systémové procesy.
- Zobrazujte a pridávajte povolenia pomocou stránky **Povolenia**.
- Nastavte definície vyhľadávania a filtrovania pre stránku Zákazníci pomocou stránky **Index vyhľadávania a filtrovania**(prístupná cez stránku **Zákazníci**).
- Definujte ciele segmentu predaja Dynamics 365 Sales pomocou stránky **Ciele exportu**.
- Spravujte konfiguráciu a obohacujte profily zákazníkov zo stránky **Obohatenie** (pre všetky obohatenia).
- Inštalácia a používanie **doplnku Karta zákazníka**.
- Pridajte a použite **konektor Power Apps**.
- Povoľte použitie [rozhraní rozhrania API v službe Customer Insights](apis.md).

## <a name="assign-roles-and-permissions"></a>Priradenie rolí a povolení

1. V prehľadoch cieľových skupín prejdite na **Správa** > **Povolenia**.

1. Výberom možnosti **Pridať používateľov** otvorte tablu **Pridať/upraviť povolenia**.

1. Použite pole **Vyhľadávanie** na vyhľadanie používateľa alebo skupiny Azure Active Directory, ktorých povolenia chcete upraviť. Vyberte a **Rolu** na priradenie k tomuto používateľovi alebo skupine.

1. Vyberte položku **Uložiť**. Aktuálne prostredie sa bude automaticky zdieľať s používateľom alebo členmi skupiny, ktorých povolenia ste zmenili. Používatelia majú prístup k aplikácii Customer Insights a môžu pracovať podľa svojej zadanej roly.

## <a name="view-current-permissions"></a>Zobrazenie aktuálnych povolení

V prehľadoch cieľovej skupiny prejdite na **Správca** > **Povolenia**, aby ste videli, ktoré priradenia rolí sú momentálne aktívne.

- Stĺpec **Typ** určuje jedného používateľa, skupinu alebo aplikáciu. Systém podporuje jednotlivých používateľov a skupiny.
- Roly sú špecifikované v stĺpci **Rola**.
- Ak chcete zoradiť výsledky podľa hodnoty v tomto stĺpci, vyberte ľubovoľný názov stĺpca.
- Pomocou poľa **Vyhľadať** v hornej časti stránky vyhľadajte konkrétnych používateľov.


[!INCLUDE[footer-include](../includes/footer-banner.md)]