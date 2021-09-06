---
title: Žiadosti dotknutých osôb (DSR) podľa GDPR | Dokumentácia spoločnosti Microsoft
description: Odpovedajte na žiadosti dotknutých osôb pre funkciu prehľadov cieľových skupín v službe Dynamics 365 Customer Insights.
ms.date: 05/14/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: 891794321f20954533ec0374b397eaf6b30445c2b0c95f601009912b3c3950a7
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 08/10/2021
ms.locfileid: "7034527"
---
# <a name="data-subject-rights-dsr-requests-under-gdpr"></a>Žiadosti o práva dotknutých osôb (DSR) podľa GDPR

## <a name="responding-to-gdpr-data-subject-delete-requests-for-dynamics-365-customer-insights-audience-insights-capability"></a>Odpovede na žiadosti dotknutých osôb o odstránenie podľa nariadenia GRPR pre funkciu prehľadov cieľových skupín v službe Dynamics 365 Customer Insights

„Právo na vymazanie“ odstránením osobných údajov z údajov o zákazníkoch organizácie je kľúčovou ochranou podľa všeobecného nariadenia o ochrane údajov (GDPR). Odstránenie osobných údajov zahŕňa odstránenie všetkých osobných údajov a protokolov generovaných systémom, okrem informácií z denníkov auditu.

### <a name="manage-data-subject-delete-requests"></a>Správa požiadaviek na odstránenie dotknutej osoby

Prehľady cieľových skupín ponúkajú nasledujúce integrované rozhranie na vymazanie osobných údajov pre konkrétneho zákazníka alebo používateľa:

- **Spravovať žiadosti o vymazanie údajov zákazníkov**: Údaje zákazníkov v Customer Insights sa získavajú z pôvodných zdrojov údajov, ktoré nepochádzajú z Customer Insights. Všetky žiadosti o vymazanie GDPR musia byť vykonané v pôvodnom zdroji údajov.
- **Spravovanie žiadostí o vymazanie používateľských údajov v Customer Insights**: Údaje pre používateľov vytvára služba Customer Insights. Všetky žiadosti o vymazanie GDPR sa musia vykonať v Customer Insights.

#### <a name="manage-delete-requests-for-customer-data"></a>Spravovanie žiadostí o vymazanie údajov o zákazníkoch

Správca Customer Insights môže podľa týchto krokov odstrániť zákaznícke údaje, ktoré boli odstránené v zdroji údajov:

1. Prihlásiť sa do Dynamics 365 Customer Insights.
2. V prehľadoch cieľových skupín prejdite na **Údaje** > **Zdroje údajov**
3. Pre každý zdroj údajov v zozname, ktorý obsahuje odstránené údaje o zákazníkoch:
   1. Vyberte (...) a potom možnosť **Obnoviť**.
   2. Skontrolujte stav zdroja údajov v časti **Stav**. Začiarknutie znamená, že obnovenie bolo úspešné. Výstražný trojuholník znamená, že sa niečo pokazilo. Ak sa zobrazí výstražný trojuholník, kontaktujte D365CI@microsoft.com.

> [!div class="mx-imgBorder"]
> ![Spravovanie žiadostí o vymazanie údajov o zákazníkoch podľa GDPR.](media/gdpr-data-sources.png "Spravovanie žiadostí o vymazanie údajov o zákazníkoch podľa GDPR")

#### <a name="manage-delete-requests-for-user-data"></a>Spravovanie žiadostí o vymazanie údajov o používateľoch

Správca Customer Insights môže podľa týchto krokov odstrániť používateľské údaje Customer Insights:

1. Prihlásiť sa do Dynamics 365 Customer Insights.
2. V prehľadoch cieľových skupín prejdite na **Správa** > **Povolenia**.
3. Začiarknite políčka používateľa, ktorého chcete odstrániť.
4. Vyberte možnosť **Odstrániť**.

> [!div class="mx-imgBorder"]
> ![Vybavovanie žiadostí o vymazanie údajov o používateľoch podľa nariadenia GDPR.](media/gdpr-permissions.png "Vybavovanie žiadostí o vymazanie údajov o používateľoch podľa nariadenia GDPR")

## <a name="responding-to-gdpr-data-subject-export-requests"></a>Odpovedanie na žiadosti o export dotknutých osôb pre podľa nariadenia GDPR

Ako súčasť nášho záväzku voči partnerovi s vami na vašej ceste k všeobecnému nariadeniu o ochrane údajov (GDPR) sme vyvinuli dokumentáciu, ktorá vám pomôže pripraviť sa. Táto dokumentácia popisuje kroky, ktoré dnes môžete podniknúť na podporu súladu s GDPR pri používaní prehľadov cieľových skupín.

### <a name="manage-export-and-view-requests"></a>Spravovanie žiadostí o export a zobrazenie

Právo na prenosnosť údajov umožňuje dotknutým osobám požiadať o kópiu svojich osobných údajov v elektronickom formáte („štruktúrovaný, bežne používaný, strojovo čitateľný a interoperabilný formát“), ktorý sa môže preniesť inému prevádzkovateľovi údajov.

#### <a name="export-customer-data-tenant-admin"></a>Export údajov o zákazníkoch (správca nájomníka)

Správca nájomníka môže exportovať údaje podľa týchto krokov:

1. Pošlite e-mail na D365CI@microsoft.com, v ktorom je uvedená e-mailová adresa požadovaného zákazníka. Tím služby Customer Insights pošle e-mail na zaregistrovanú e-mailovú adresu správcu nájomníka a požiada o potvrdenie exportu údajov.
2. Potvrďte potvrdenie na exportovanie údajov pre požadovaného zákazníka.
3. Exportované údaje dostanete prostredníctvom e-mailovej adresy správcu nájomníka.

#### <a name="export-user-data-tenant-admin"></a>Export údajov o používateľoch (správca nájomníka)

1. Pošlite e-mail na D365CI@microsoft.com, v ktorom je uvedená e-mailová adresa požadovaného používateľa. Tím služby Customer Insights pošle e-mail na zaregistrovanú e-mailovú adresu správcu nájomníka a požiada o potvrdenie exportu údajov.
2. Potvrďte potvrdenie na exportovanie údajov pre požadovaného používateľa.
3. Exportované údaje dostanete prostredníctvom e-mailovej adresy správcu nájomníka.


[!INCLUDE[footer-include](../includes/footer-banner.md)]