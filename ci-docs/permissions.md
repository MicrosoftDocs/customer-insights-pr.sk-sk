---
title: Priradenie používateľských povolení
description: Ďalšie informácie povoleniach a rolách používateľov.
ms.date: 08/08/2022
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
ms.openlocfilehash: a59a672b6f7e1e67c2162ea14bb9860df0d551aa
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 08/10/2022
ms.locfileid: "9245438"
---
# <a name="assign-user-permissions"></a>Priradenie používateľských povolení

Prístup k Customer Insights je obmedzený na používateľov vo vašej organizácii, ktorých do aplikácie pridá správca. Správca môže pridávať, upravovať alebo odstraňovať používateľov. Používateľom môže byť jeden používateľ, skupina alebo aplikácia. Používateľ môže mať tri typy rolí:

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
- Dokončiť **Zjednotenie údajov** ktorých výsledkom je jednotná entita profilu zákazníka.
- Definujte **Vzťahy** a **Aktivity**.
- Vytvárajte segmenty pomocou stránky **Segmenty**.
- Vytvárajte miery pomocou stránky **Miery**.
- Spravujte konfiguráciu a obohacujte profily zákazníkov zo stránky **Obohatenie** (iba pre obohatenie prvej strany).
- Spravujte a vytvárajte exporty založené na [pripojenia zdieľané s prispievateľmi](connections.md#allow-contributors-to-use-a-connection-for-exports).

## <a name="admin"></a>Správa

- Všetky povolenia, ktoré má Prispievateľ k dispozícii.
- Zmeňte nastavenia na **Systém** stránku vrátane pracovného jazyka, plány obnovy pre vaše systémové procesy a exportovanie diagnostických protokolov.
- Zmeňte nastavenia na **Bezpečnosť** vrátane používateľov, kľúčov API, súkromných odkazov a trezoru kľúčov.
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
- [Obnoviť a odstrániť](manage-environments.md#reset-an-existing-environment-preview) prostredie.

## <a name="add-users"></a>Pridanie používateľov

1. Ísť do **Admin** > **Bezpečnosť** a vyberte **Používatelia** tab.

1. Výberom možnosti **Pridať používateľov** otvorte tablu **Pridať/upraviť povolenia**.

1. Použi **Vyhľadávanie** pole nájsť Azure Active Directory používateľa alebo skupinu, ktorú chcete pridať. Vyberte a **Rolu** na priradenie k tomuto používateľovi alebo skupine.

1. Vyberte **Uložiť**. Aktuálne prostredie sa automaticky zdieľa s používateľom alebo členmi skupiny. Používatelia majú prístup k aplikácii Customer Insights a môžu pracovať podľa svojej zadanej roly.

## <a name="view-current-permissions"></a>Zobrazenie aktuálnych povolení

Ísť do **Admin** > **Bezpečnosť** a vyberte **Používatelia** zobrazíte zoznam aktívnych používateľov a ich priradenia rolí. Zoznam používateľov môžete zoradiť podľa ľubovoľného stĺpca alebo pomocou vyhľadávacieho poľa nájsť konkrétneho používateľa.

## <a name="manage-current-users"></a>Spravujte aktuálnych používateľov

Ísť do **Admin** > **Bezpečnosť** a vyberte **Používatelia** tab. Zoznam používateľov môžete zoradiť podľa ľubovoľného stĺpca alebo pomocou vyhľadávacieho poľa nájsť používateľa, ktorého chcete spravovať.

Ak chcete zobraziť dostupné akcie, vyberte používateľa.

- **Upraviť** upraviť rolu používateľa v Customer Insights. Vyberte **Uložiť** na potvrdenie zmeny.
- **Odstrániť** na odstránenie používateľa z prístupu k Customer Insights. Vyberte možnosť **Odstrániť** a potvrďte odstránenie.

[!INCLUDE [footer-include](includes/footer-banner.md)]
