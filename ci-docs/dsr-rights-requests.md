---
title: Žiadosti dotknutých osôb (DSR) podľa GDPR | Dokumentácia spoločnosti Microsoft
description: Odpovedajte na žiadosti dotknutých osôb pre funkciu prehľadov cieľových skupín v službe Dynamics 365 Customer Insights.
ms.date: 08/11/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: 6faaeb6a1ee34c3e5c8e7d465b37cee589bc920c
ms.sourcegitcommit: 5704002484cdf85ebbcf4e7e4fd12470fd8e259f
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 09/08/2021
ms.locfileid: "7483706"
---
# <a name="data-subject-rights-dsr-requests-under-gdpr"></a>Žiadosti o práva dotknutých osôb (DSR) podľa GDPR

Všeobecné nariadenie Európskej únie o ochrane údajov (GDPR) je účinné od 25. mája 2018. Poskytuje jednotlivcom významné práva týkajúce sa ich údajov. GDPR je o ochrane a uplatňovaní práv na súkromie osôb. Viac informácií o záväzku spoločnosti Microsoft k bezpečnosti a zhode s predpismi sa dozviete v [Centre dôveryhodnosti spoločnosti Microsoft](https://www.microsoft.com/trust-center).

Zaviazali sme sa pomôcť našim zákazníkom splniť ich požiadavky v zmysle smernice GDPR. Zahŕňa právo na odstránenie a export údajov, ktoré zahŕňajú osobné informácie, ako sú identifikácie používateľov, telefónne čísla a e-mailové adresy. Správcovia môžu implementovať žiadosti používateľov o odstránenie alebo export osobných údajov.

## <a name="audience-insights"></a>Prehľady cieľových skupín

### <a name="responding-to-gdpr-data-subject-delete-requests-for-dynamics-365-customer-insights-audience-insights-capability"></a>Odpovede na žiadosti dotknutých osôb o odstránenie podľa nariadenia GRPR pre funkciu prehľadov cieľových skupín v službe Dynamics 365 Customer Insights

„Právo na vymazanie“ odstránením osobných údajov z údajov o zákazníkoch organizácie je kľúčovou ochranou podľa všeobecného nariadenia o ochrane údajov (GDPR). Odstránenie osobných údajov zahŕňa odstránenie všetkých osobných údajov a protokolov generovaných systémom, okrem informácií z denníkov auditu.

#### <a name="manage-data-subject-delete-requests"></a>Správa požiadaviek na odstránenie dotknutej osoby

Prehľady cieľových skupín ponúkajú nasledujúce integrované rozhranie na vymazanie osobných údajov pre konkrétneho zákazníka alebo používateľa:

- **Spravovať žiadosti o vymazanie údajov zákazníkov**: Údaje zákazníkov v Customer Insights sa získavajú z pôvodných zdrojov údajov, ktoré nepochádzajú z Customer Insights. Všetky žiadosti o vymazanie GDPR musia byť vykonané v pôvodnom zdroji údajov.
- **Spravovanie žiadostí o vymazanie používateľských údajov v Customer Insights**: Údaje pre používateľov vytvára služba Customer Insights. Všetky žiadosti o vymazanie GDPR sa musia vykonať v Customer Insights.

##### <a name="manage-requests-to-delete-customer-data"></a>Spravovanie žiadostí o vymazanie údajov o zákazníkoch

Správca Customer Insights môže podľa týchto krokov odstrániť zákaznícke údaje, ktoré boli odstránené v zdroji údajov:

1. Prihlásiť sa do Dynamics 365 Customer Insights.
2. V prehľadoch cieľových skupín prejdite na **Údaje** > **Zdroje údajov**
3. Pre každý zdroj údajov v zozname, ktorý obsahuje odstránené údaje o zákazníkoch:
   1. Vyberte (...) a potom možnosť **Obnoviť**.
   2. Skontrolujte stav zdroja údajov v časti **Stav**. Začiarknutie znamená, že obnovenie bolo úspešné. Výstražný trojuholník znamená, že sa niečo pokazilo. Ak sa zobrazí výstražný trojuholník, kontaktujte D365CI@microsoft.com.

> [!div class="mx-imgBorder"]
> ![Spravovanie žiadostí o vymazanie údajov o zákazníkoch podľa GDPR.](audience-insights/media/gdpr-data-sources.png "Spravovanie žiadostí o vymazanie údajov o zákazníkoch podľa GDPR")

##### <a name="manage-delete-requests-for-user-data"></a>Spravovanie žiadostí o vymazanie údajov o používateľoch

Správca Customer Insights môže podľa týchto krokov odstrániť používateľské údaje Customer Insights:

1. Prihlásiť sa do Dynamics 365 Customer Insights.
2. V prehľadoch cieľových skupín prejdite na **Správa** > **Povolenia**.
3. Začiarknite políčka používateľa, ktorého chcete odstrániť.
4. Vyberte možnosť **Odstrániť**.

### <a name="responding-to-gdpr-data-subject-export-requests"></a>Odpovedanie na žiadosti o export dotknutých osôb pre podľa nariadenia GDPR

Ako súčasť nášho záväzku voči partnerovi s vami na vašej ceste k všeobecnému nariadeniu o ochrane údajov (GDPR) sme vyvinuli dokumentáciu, ktorá vám pomôže pripraviť sa. Táto dokumentácia popisuje kroky, ktoré dnes môžete podniknúť na podporu súladu s GDPR pri používaní prehľadov cieľových skupín.

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

## <a name="engagement-insights"></a>Prehľady interakcií

### <a name="deleting-and-exporting-event-data-containing-end-user-identifiable-information"></a>Vymazanie a export údajov o udalosti obsahujúcich identifikovateľné informácie koncového používateľa

V nasledujúcich častiach je popísané, ako odstrániť a exportovať údaje udalostí, ktoré môžu obsahovať osobné údaje.

Odstránenie alebo exportovanie údajov:

1. Označte vlastnosti udalosti, ktoré obsahujú údaje, osobnými informáciami.
2. Odstráňte alebo exportujte údaje spojené s konkrétnymi hodnotami (napríklad: zadané ID používateľa).

#### <a name="tag-and-update-event-properties"></a>Označte a aktualizujte vlastnosti udalosti

Osobné údaje sú označené na úrovni vlastnosti udalosti. Najskôr označte vlastnosti, ktoré sa majú odstrániť alebo exportovať.

Ak chcete označiť vlastnosť udalosti ako obsahujúcu osobné informácie, postupujte takto:

1. Otvorte pracovný priestor obsahujúci udalosť.

1. Prejdite do **Údaje** > **Udalosti** a zobrazíte si zoznam udalostí vo vybranom pracovnom priestore.
  
1. Zvoľte udalosť, ktorú chcete označiť.

1. Stlačte možnosť **Upraviť vlastnosti** na otvorenie tably so zoznamom všetkých vlastností vybratej udalosti.
     
1. Stlačte možnosť **...** a potom stlačte možnosť **Upraviť**, čím prejdete na dialógové okno **Aktualizovať vlastnosť**.

   ![Upraviť udalosť.](engagement-insights/media/edit-event.png "Upraviť udalosť")

1. V okne **Aktualizovať vlastnosť** stlačte možnosť **...** v pravom hornom rohu a potom vyberte označte pole **Obsahuje EUII**. Stlačením možnosti **Aktualizovať** uložíte zmeny.

   ![Uloží zmeny.](engagement-insights/media/update-property.png "Uloží zmeny")

   > [!NOTE]
   > Zakaždým, keď sa zmení schéma udalosti alebo vytvoríte novú udalosť, odporúča sa vyhodnotiť súvisiace vlastnosti udalosti a v prípade potreby ich označiť alebo odznačiť ako obsahujúce osobné údaje.

#### <a name="delete-or-export-tagged-event-data"></a>Odstránenie alebo exportovanie údajov označených udalostí

Ak boli všetky vlastnosti udalosti označené primerane, ako je opísané v predchádzajúcom kroku, môže administrátor prostredia vydať žiadosť o vymazanie oproti označeným údajom udalosti.

Správa odstránenia EUII alebo požiadaviek na exportovanie

1. Prejdite do ponuky **Správca** > **Prostredie** > **Nastavenia**.

1. V sekcii **Správa identifikovateľných informácií koncového používateľa (EUII)** stlačte možnosť **Spravovať EUII**.

##### <a name="deletion"></a>Odstránenie

Na odstránenie môžete do zoznamu zadať zoznam ID používateľov oddelených čiarkou v časti **Vymazať identifikovateľné informácie koncového používateľa (EUII)**. Tieto identifikátory sa potom porovnajú so všetkými označenými vlastnosťami udalostí všetkých projektov v aktuálnom prostredí pomocou presnej zhody reťazcov. 

Ak sa hodnota vlastnosti zhoduje s jedným z poskytnutých ID, pridružená udalosť bude natrvalo odstránená. Z dôvodu nezvratnosti tejto akcie musíte po výbere vymazanie stlačiť možnosť **Odstrániť**.

##### <a name="export"></a>Export

Proces exportu je identický s procesom odstránenia, pokiaľ ide o definovanie hodnôt vlastností udalostí v sekcii **Exportovať identifikovateľné informácie koncového používateľa (EUII)**. Ďalej budete musieť poskytnúť **Adresu URL úložiska Azure Blob** na určenie miesta exportovania. Adresa URL Azure Blob musí obsahovať [Zdieľaný podpis prístupu (SAS)](/azure/storage/common/storage-sas-overview).

Po stlačení možnosti **Export**, všetky udalosti aktuálneho tímu, ktoré obsahujú zodpovedajúce označené vlastnosti, sa exportujú vo formáte CSV do cieľového miesta na export.

### <a name="good-practices"></a>Osvedčené postupy

* Snažte sa vyhnúť sa odosielaniu udalostí, ktoré obsahujú osobné údaje.
* Ak potrebujete odoslať udalosti obsahujúce údaje EUII, obmedzte počet udalostí a vlastností udalostí, ktoré obsahujú údaje EUII. V ideálnom prípade sa obmedzte na jednu takúto udalosť.
* Zaistite, aby k odoslaným osobným údajom malo prístup čo najmenej ľudí.
* V prípade udalostí obsahujúcich osobné údaje nezabudnite nastaviť jednu vlastnosť tak, aby vysielala jedinečný identifikátor, ktorý je možné ľahko prepojiť s konkrétnym používateľom (napríklad ID používateľa). To zjednodušuje segregáciu údajov a export alebo odstránenie správnych údajov.
* Pre každú udalosť označte iba jednu vlastnosť, ktorá obsahuje osobné údaje. Ideálne takú, ktorá obsahuje iba jedinečný identifikátor.
* Neoznačujte vlastnosti obsahujúce podrobné hodnoty (napríklad celý text žiadosti). Schopnosť prehľadu zapojenia používa pri rozhodovaní, ktoré udalosti na odstránenie alebo export, presnú zhodu reťazcov.

[!INCLUDE[footer-include](includes/footer-banner.md)]