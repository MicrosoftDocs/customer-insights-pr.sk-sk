---
title: Žiadosti dotknutých osôb (DSR) podľa GDPR | Dokumentácia spoločnosti Microsoft
description: Odpovedanie na žiadosť dotknutej osoby Dynamics 365 Customer Insights.
ms.date: 05/23/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: c71305ab835b0f4f75adcce716e795959f898e47
ms.sourcegitcommit: 8e9f0a9693fd8d91ad0227735ff03688fef5406f
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 06/10/2022
ms.locfileid: "8947387"
---
# <a name="data-subject-rights-dsr-requests-under-gdpr"></a>Žiadosti o práva dotknutých osôb (DSR) podľa GDPR

Všeobecné nariadenie Európskej únie o ochrane údajov (GDPR) je účinné od 25. mája 2018. Poskytuje jednotlivcom významné práva týkajúce sa ich údajov. GDPR je o ochrane a uplatňovaní práv na súkromie osôb. Viac informácií o záväzku spoločnosti Microsoft k bezpečnosti a zhode s predpismi sa dozviete v [Centre dôveryhodnosti spoločnosti Microsoft](https://www.microsoft.com/trust-center).

Zaviazali sme sa pomôcť našim zákazníkom splniť ich požiadavky v zmysle smernice GDPR. Zahŕňa právo na odstránenie a export údajov, ktoré zahŕňajú osobné informácie, ako sú identifikácie používateľov, telefónne čísla a e-mailové adresy. Správcovia môžu implementovať žiadosti používateľov o odstránenie alebo export osobných údajov.

## <a name="dynamics-365-customer-insights"></a>Dynamics 365 Customer Insights

### <a name="responding-to-gdpr-data-subject-delete-requests-for-dynamics-365-customer-insights"></a>Odpovedanie na žiadosti o odstránenie dotknutých osôb GDPR pre Dynamics 365 Customer Insights

„Právo na vymazanie“ odstránením osobných údajov z údajov o zákazníkoch organizácie je kľúčovou ochranou podľa všeobecného nariadenia o ochrane údajov (GDPR). Odstránenie osobných údajov zahŕňa odstránenie všetkých osobných údajov a protokolov generovaných systémom, okrem informácií z denníkov auditu.

#### <a name="manage-data-subject-delete-requests"></a>Správa požiadaviek na odstránenie dotknutej osoby

Customer Insights ponúka nasledujúce možnosti v rámci produktu na odstránenie osobných údajov konkrétneho zákazníka alebo používateľa:

- **Spravovať žiadosti o vymazanie údajov zákazníkov**: Údaje zákazníkov v Customer Insights sa získavajú z pôvodných zdrojov údajov, ktoré nepochádzajú z Customer Insights. Všetky žiadosti o vymazanie GDPR musia byť vykonané v pôvodnom zdroji údajov.
- **Spravovanie žiadostí o vymazanie používateľských údajov v Customer Insights**: Údaje pre používateľov vytvára služba Customer Insights. Všetky žiadosti o vymazanie GDPR sa musia vykonať v Customer Insights.

##### <a name="manage-requests-to-delete-customer-data"></a>Spravovanie žiadostí o vymazanie údajov o zákazníkoch

Správca Customer Insights môže podľa týchto krokov odstrániť zákaznícke údaje, ktoré boli odstránené v zdroji údajov:

1. Prihlásiť sa do Dynamics 365 Customer Insights.
2. Ísť do **Údaje** > **Zdroje dát**
3. Pre každý zdroj údajov v zozname, ktorý obsahuje odstránené údaje o zákazníkoch:
   1. Vyberte zvislú elipsu (&vellip;) a potom vyberte **Obnoviť**.
   2. Skontrolujte stav zdroja údajov v časti **Stav**. Začiarknutie znamená, že obnovenie bolo úspešné. Výstražný trojuholník znamená, že sa niečo pokazilo. Ak sa zobrazí výstražný trojuholník, kontaktujte D365CI@microsoft.com.

> [!div class="mx-imgBorder"]
> ![Spravovanie žiadostí o vymazanie údajov o zákazníkoch podľa GDPR.](media/gdpr-data-sources.png "Spravovanie žiadostí o vymazanie údajov o zákazníkoch podľa GDPR")

##### <a name="manage-delete-requests-for-user-data"></a>Spravovanie žiadostí o vymazanie údajov o používateľoch

Správca Customer Insights môže podľa týchto krokov odstrániť používateľské údaje Customer Insights:

1. Prihlásiť sa do Dynamics 365 Customer Insights.
2. Ísť do **Admin** > **Bezpečnosť** > **Povolenia**.
3. Začiarknite políčka používateľa, ktorého chcete odstrániť.
4. Vyberte možnosť **Odstrániť**.

### <a name="responding-to-gdpr-data-subject-export-requests"></a>Odpovedanie na žiadosti o export dotknutých osôb pre podľa nariadenia GDPR

Ako súčasť nášho záväzku spolupracovať s vami na vašej ceste k všeobecnému nariadeniu o ochrane údajov (GDPR) sme vytvorili dokumentáciu, ktorá vám pomôže reagovať na žiadosti dotknutých osôb.

#### <a name="manage-export-and-view-requests"></a>Spravovanie žiadostí o export a zobrazenie

Právo na prenosnosť údajov umožňuje dotknutým osobám požiadať o kópiu svojich osobných údajov v elektronickom formáte („štruktúrovaný, bežne používaný, strojovo čitateľný a interoperabilný formát“), ktorý sa môže preniesť inému prevádzkovateľovi údajov.

##### <a name="export-customer-data-tenant-admin"></a>Export údajov o zákazníkoch (správca nájomníka)

Správca nájomníka môže exportovať údaje podľa týchto krokov:

1. Pošlite e-mail na D365CI@microsoft.com, v ktorom je uvedená e-mailová adresa požadovaného zákazníka. Tím služby Customer Insights pošle e-mail na zaregistrovanú e-mailovú adresu správcu nájomníka a požiada o potvrdenie exportu údajov.
2. Potvrďte potvrdenie na exportovanie údajov pre požadovaného zákazníka.
3. Exportované údaje dostanete prostredníctvom e-mailovej adresy správcu nájomníka.

##### <a name="export-user-data-tenant-admin"></a>Export údajov o používateľoch (správca nájomníka)

1. Pošlite e-mail na D365CI@microsoft.com, v ktorom je uvedená e-mailová adresa požadovaného používateľa. Tím služby Customer Insights pošle e-mail na zaregistrovanú e-mailovú adresu správcu nájomníka a požiada o potvrdenie exportu údajov.
2. Potvrďte potvrdenie na exportovanie údajov pre požadovaného používateľa.
3. Exportované údaje dostanete prostredníctvom e-mailovej adresy správcu nájomníka.

[!INCLUDE [footer-include](includes/footer-banner.md)]