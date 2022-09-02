---
title: Žiadosti dotknutých osôb (DSR) podľa GDPR | Dokumentácia spoločnosti Microsoft
description: Odpovedanie na žiadosť dotknutej osoby Dynamics 365 Customer Insights.
ms.date: 08/31/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: 49251fb46957c4d7ec205b93c9547a3cd380eb11
ms.sourcegitcommit: 624b27bb65a0de1970dc1ac436643b493f0a31cf
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 08/31/2022
ms.locfileid: "9387130"
---
# <a name="data-subject-rights-dsr-requests-under-gdpr"></a>Žiadosti o práva dotknutých osôb (DSR) podľa GDPR

Všeobecné nariadenie Európskej únie o ochrane údajov (GDPR) je účinné od 25. mája 2018. Poskytuje jednotlivcom významné práva týkajúce sa ich údajov. GDPR je o ochrane a uplatňovaní práv na súkromie osôb. Prečítajte si viac o záväzku spoločnosti Microsoft v oblasti zabezpečenia a dodržiavania predpisov na stránke [Centrum dôveryhodnosti spoločnosti Microsoft](https://www.microsoft.com/trust-center).

Zaviazali sme sa pomôcť našim zákazníkom splniť ich požiadavky v zmysle smernice GDPR. Zahŕňa právo na vymazanie alebo export údajov, ktoré zahŕňajú osobné informácie, ako sú ID používateľov, telefónne čísla a e-mailové adresy. Správcovia môžu implementovať žiadosti používateľov o odstránenie alebo export osobných údajov.

## <a name="responding-to-gdpr-data-subject-delete-requests-for-customer-insights"></a>Reakcia na žiadosti dotknutej osoby o vymazanie údajov podľa GDPR pre Customer Insights

„Právo na vymazanie“ odstránením osobných údajov z údajov o zákazníkoch organizácie je kľúčovou ochranou podľa všeobecného nariadenia o ochrane údajov (GDPR). Odstránenie osobných údajov zahŕňa odstránenie všetkých osobných údajov a protokolov generovaných systémom, okrem informácií z denníkov auditu.

### <a name="manage-data-subject-delete-requests"></a>Správa požiadaviek na odstránenie dotknutej osoby

Customer Insights ponúka nasledujúce možnosti v rámci produktu na odstránenie osobných údajov konkrétneho zákazníka alebo používateľa:

- **Spravovať žiadosti o vymazanie údajov zákazníkov**: Údaje zákazníkov v Customer Insights sa získavajú z pôvodných zdrojov údajov, ktoré nepochádzajú z Customer Insights. Najprv vykonajte žiadosti o vymazanie GDPR v pôvodnom zdroj údajov.
- **Spravovanie žiadostí o vymazanie používateľských údajov v Customer Insights**: Údaje pre používateľov vytvára služba Customer Insights. Vykonajte všetky žiadosti o odstránenie GDPR v Customer Insights.

#### <a name="manage-requests-to-delete-customer-data"></a>Spravovanie žiadostí o vymazanie údajov o zákazníkoch

Ako správca Customer Insights odstráňte zákaznícke údaje Customer Insights, ktoré boli odstránené v zdroj údajov. Overte, či boli žiadosti o vymazanie GDPR vykonané v pôvodnom zdroj údajov.

1. Prihlásiť sa do Dynamics 365 Customer Insights.

1. Prejdite do **Údaje** > **Zdroje údajov**.

1. Pre každý zdroj údajov v zozname, ktorý obsahuje odstránené údaje o zákazníkoch:
   1. Vyberte zdroj údajov a potom vyberte **Obnoviť**.
   1. Skontrolujte stav zdroja údajov v časti **Stav**. Začiarknutie znamená, že obnovenie bolo úspešné. Výstražný trojuholník znamená, že sa niečo pokazilo. Ak sa zobrazí výstražný trojuholník, kontaktujte D365CI@microsoft.com.

   :::image type="content" source="media/gdpr-data-sources.png" alt-text="Spravovanie žiadostí o vymazanie údajov o zákazníkoch podľa GDPR.":::

1. Po úspešnom obnovení zdrojov údajov spustite aj následné aktualizácie. Najmä ak nemáte naplánované opakované úplné obnovenie štatistík zákazníkov.

   > [!IMPORTANT]
   > Statické segmenty nie sú zahrnuté v úplnom obnovení alebo spustených obnoveniach po prúde po požiadavke na odstránenie. Ak chcete zabezpečiť, aby sa údaje o zákazníkoch odstránili aj zo statických segmentov, znova vytvorte statické segmenty s obnovenými zdrojovými údajmi.

#### <a name="manage-delete-requests-for-user-data"></a>Spravovanie žiadostí o vymazanie údajov o používateľoch

Ako správca Customer Insights odstráňte používateľské údaje Customer Insights.

1. Prihlásiť sa do Dynamics 365 Customer Insights.

1. Ísť do **Admin** > **Bezpečnosť** > a vyberte **Používatelia** tab.

1. Začiarknite políčko pre používateľov, ktorých chcete odstrániť.

1. Vyberte možnosť **Odstrániť**.

1. Potvrďte vymazanie.

## <a name="responding-to-gdpr-data-subject-export-requests"></a>Odpovedanie na žiadosti o export dotknutých osôb pre podľa nariadenia GDPR

Právo na prenosnosť údajov umožňuje dotknutým osobám požiadať o kópiu svojich osobných údajov v elektronickom formáte („štruktúrovaný, bežne používaný, strojovo čitateľný a interoperabilný formát“), ktorý sa môže preniesť inému prevádzkovateľovi údajov.

### <a name="manage-export-and-view-requests"></a>Spravovanie žiadostí o export a zobrazenie

Spravujte požiadavky na export údajov o zákazníkoch alebo používateľoch.

#### <a name="export-customer-data-tenant-admin"></a>Export údajov o zákazníkoch (správca nájomníka)

Ako správca nájomníka exportujte údaje o zákazníkoch.

1. Pošlite e-mail na D365CI@microsoft.com, v ktorom je uvedená e-mailová adresa požadovaného zákazníka. Tím služby Customer Insights pošle e-mail na zaregistrovanú e-mailovú adresu správcu nájomníka a požiada o potvrdenie exportu údajov.
2. Potvrďte potvrdenie na exportovanie údajov pre požadovaného zákazníka.
3. Exportované údaje dostanete prostredníctvom e-mailovej adresy správcu nájomníka.

#### <a name="export-user-data-tenant-admin"></a>Export údajov o používateľoch (správca nájomníka)

Ako správca nájomníka exportujte údaje používateľa.

1. Pošlite e-mail na D365CI@microsoft.com, v ktorom je uvedená e-mailová adresa požadovaného používateľa. Tím Customer Insights odošle e-mail na e-mailovú adresu správcu registrovaného nájomcu so žiadosťou o potvrdenie exportu údajov.
1. Potvrďte potvrdenie na exportovanie údajov pre požadovaného používateľa.
1. Exportované údaje dostanete prostredníctvom e-mailovej adresy správcu nájomníka.

## <a name="data-deletion-handling-in-dynamics-365-customer-insights"></a>Spracovanie vymazania údajov v Dynamics 365 Customer Insights

Údaje sa vymažú (údajové oddiely a dátové snímky), ak sú dátové oddiely a dátové snímky neaktívne dlhšie ako 30 dní, čo znamená, že boli nahradené novým dátovým oddielom a snímkou prostredníctvom obnovenia zdrojov údajov.

Nie všetky údaje a snímky sa odstránia. Najnovší údajový oddiel a snímka údajov sú aktívne, pretože sa používajú v Customer Insights. V prípade najnovších údajov nezáleží na tom, či sa zdroje údajov neobnovili za posledných 30 dní.

[!INCLUDE [footer-include](includes/footer-banner.md)]
