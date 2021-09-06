---
title: Predikcia odchodu predplatiteľov – vzorový sprievodca
description: V tomto vzorovom sprievodcovi môžete vyskúšať vopred pripravený model predikcie odchodu predplatiteľov.
ms.date: 11/19/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: diegogranados117
ms.author: digranad
manager: shellyha
ms.openlocfilehash: e2360c707bcbdfa64482f06f0a0cd0783a377b4fd79620ffd3cc1c9c6cad9ed3
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 08/10/2021
ms.locfileid: "7029602"
---
# <a name="subscription-churn-prediction-preview-sample-guide"></a>Predikcia odchodu predplatiteľov (ukážka) – vzorový sprievodca

Prejdeme si podrobný príklad predikcie odchodov predplatiteľov pomocou nižšie uvedených údajov. 

## <a name="scenario"></a>Scenár

Contoso je spoločnosť, ktorá vyrába vysoko kvalitnú kávu a kávovary, ktoré predávajú prostredníctvom svojej webovej stránky Contoso Coffee. Nedávno začali ponúkať pre svojich zákazníkov možnosť predplatného, aby mohli pravidelne dostávať kávu. Ich cieľom je pochopiť, ktorí zákazníci s predplatným môžu predplatné v najbližších mesiacoch zrušiť. Poznatok, ktorý z ich zákazníkov **pravdepodobne odíde**, im môže im pomôcť ušetriť marketingové úsilie zameraním na ich udržanie.

## <a name="prerequisites"></a>Predpoklady

- Minimálne [povolenia prispievateľa](permissions.md) v Customer Insights.
- Odporúčame vám vykonať nasledujúce kroky [v novom prostredí](manage-environments.md).

## <a name="task-1---ingest-data"></a>Úloha 1 – Príjem údajov

Prečítajte si články [o príjme údajov](data-sources.md) a konkrétne o [importe zdrojov údajov pomocou konektorov Power Query](connect-power-query.md). Nasledujúce informácie predpokladajú, že ste sa oboznámili s prijímaním údajov vo všeobecnosti. 

### <a name="ingest-customer-data-from-ecommerce-platform"></a>Príjem údajov o zákazníkoch z platformy eCommerce

1. Vytvorte zdroj údajov s názvom **eCommerce**, vyberte možnosť importu a vyberte konektor **Text/CSV**.

1. Zadajte adresu URL kontaktov pre eCommerce https://aka.ms/ciadclasscontacts.

1. Počas úpravy údajov vyberte **Transformovať** a potom **Použiť prvý riadok ako hlavičky**.

1. Aktualizujte typ údajov pre stĺpce uvedené nižšie:

   - **DateOfBirth**: Dátum
   - **CreatedOn**: Dátum/Čas/Pásmo

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Transformácia dátumu narodenia na dátum.":::

1. V poli **Názov** na pravej table premenujte svoj zdroj údajov z **Dotaz** na **eCommerceContacts**

1. Uložte zdroj údajov.

### <a name="ingest-customer-data-from-loyalty-schema"></a>Príjem údaje o zákazníkoch z vernostnej schémy

1. Vytvorte zdroj údajov s názvom **LoyaltyScheme**, vyberte možnosť importu a vyberte konektor **Text/CSV**.

1. Zadajte adresu URL kontaktov pre eCommerce https://aka.ms/ciadclasscustomerloyalty.

1. Počas úpravy údajov vyberte **Transformovať** a potom **Použiť prvý riadok ako hlavičky**.

1. Aktualizujte typ údajov pre stĺpce uvedené nižšie:

   - **DateOfBirth**: Dátum
   - **RewardsPoints**: Celé číslo
   - **CreatedOn**: Dátum/Čas

1. V poli **Názov** na pravej table premenujte svoj zdroj údajov z **Dotaz** na **loyCustomers**.

1. Uložte zdroj údajov.

### <a name="ingest-subscription-information"></a>Príjem informácií o predplatnom

1. Vytvorte zdroj údajov s názvom **SubscriptionHistory**, vyberte možnosť importu a vyberte konektor **Text/CSV**.

1. Zadajte adresu URL kontaktov pre eCommerce https://aka.ms/ciadchurnsubscriptionhistory.

1. Počas úpravy údajov vyberte **Transformovať** a potom **Použiť prvý riadok ako hlavičky**.

1. Aktualizujte typ údajov pre stĺpce uvedené nižšie:

   - **SubscriptioID**: Celé číslo
   - **SubscriptionAmount**: Mena
   - **SubscriptionEndDate**: Dátum/Čas
   - **SubscriptionStartDate**: Dátum/Čas
   - **TransactionDate**: Dátum/Čas
   - **IsRecurring**: Pravda/Nepravda
   - **Is_auto_renew**: Pravda/Nepravda
   - **RecurringFrequencyInMonths**: Celé číslo

1. V poli **Názov** na pravej table premenujte svoj zdroj údajov z **Dotaz** na **SubscriptionHistory**.

1. Uložte zdroj údajov.

### <a name="ingest-customer-data-from-website-reviews"></a>Príjem údajov o zákazníkoch z recenzií na webe

1. Vytvorte zdroj údajov s názvom **Website**, vyberte možnosť importu a vyberte konektor **Text/CSV**.

1. Zadajte adresu URL kontaktov pre eCommerce https://aka.ms/ciadclasswebsite.

1. Počas úpravy údajov vyberte **Transformovať** a potom **Použiť prvý riadok ako hlavičky**.

1. Aktualizujte typ údajov pre stĺpce uvedené nižšie:

   - **ReviewRating**: Celé číslo
   - **ReviewDate**: Dátum

1. V poli „Názov“ na pravej table premenujte svoj zdroj údajov z **Query** na **webReviews**.

## <a name="task-2---data-unification"></a>Úloha 2 – Zjednotenie údajov

Po prijatí údajov teraz začíname proces **Mapovanie, párovanie, zlúčenie** na vytvorenie zjednoteného profilu zákazníka. Ďalšie informácie nájdete v téme [Zjednotenie údajov](data-unification.md).

### <a name="map"></a>Priradenie

1. Po prijatí údajov namapujte kontakty z údajov eCommerce a Loyalty na bežné typy údajov. Prejdite na **Údaje** > **Zjednotenie** > **Mapovanie**.

1. Vyberte entity, ktoré zastupujú profil zákazníka – **eCommerceContacts** a **loyCustomers**. 

   :::image type="content" source="media/unify-ecommerce-loyalty.PNG" alt-text="Zjednotenie zdrojov údajov elektronického obchodu a vernostných údajov.":::

1. Vyberte **ContactId** ako primárny kľúč pre **eCommerceContacts** a **LoyaltyID** ako primárny kľúč pre **loyCustomers**.

   :::image type="content" source="media/unify-loyaltyid.PNG" alt-text="Zjednotenie LoyaltyId ako primárny kľúč.":::

### <a name="match"></a>Spárovanie

1. Prejdite na kartu **Spárovanie** a vyberte **Nastaviť poradie**.

1. V **primárnom** rozbaľovacom zozname si vyberte možnosť **eCommerceContacts: eCommerce** ako primárny zdroj a zahrňte do nej všetky záznamy.

1. V rozbaľovacom zozname **Entita 2** vyberte možnosť **loyCustomers: LoyaltyScheme** a zahrňte do nej všetky záznamy.

   :::image type="content" source="media/unify-match-order.PNG" alt-text="Zjednotenie zosúladenia eCommerce a Loyalty.":::

1. Vyberte **Vytvoriť nové pravidlo**

1. Pridajte svoju prvú podmienku pomocou FullName.

   * V prípade eCommerceContacts vyberte z rozbaľovacieho zoznamu položku **FullName**.
   * V prípade loyCustomers vyberte z rozbaľovacieho zoznamu položku **FullName**.
   * Vyberte rozbaľovací zoznam **Normalizovať** a vyberte **Typ (Telefón, Meno, Adresa, ...)**.
   * Nastavte **Úroveň presnosti**: **Základná** a **Hodnota**: **Vysoká**.

1. Zadajte meno **FullName, E-mail** pre nové pravidlo.

   * Vyberte druhú podmienku pre e-mailovú adresu výberom možnosti **Pridať podmienku**
   * Pri entite eCommerceContacts vyberte z rozbaľovacieho zoznamu položku **EMail**.
   * Pri entite loyCustomers vyberte z rozbaľovacieho zoznamu položku **EMail**. 
   * Pole Normalizovať nechajte prázdne. 
   * Nastavte **Úroveň presnosti**: **Základná** a **Hodnota**: **Vysoká**.

   :::image type="content" source="media/unify-match-rule.PNG" alt-text="Pravidlo zjednotenia zhody pre meno a e-mail.":::

7. Vyberte položku **Uložiť** a **Spustiť**.

### <a name="merge"></a>Zlúčenie

1. Prejdite na kartu **Zlúčiť**.

1. V entite **ContactId** pre **loyCustomers** zmeňte zobrazovaný názov na **ContactIdLOYALTY** na odlíšenie od ostatných prijatých ID.

   :::image type="content" source="media/unify-merge-contactid.PNG" alt-text="premenovanie contactid z loyaltyid.":::

1. Vyberte **Uložiť** a **Spustiť** na začatie procesu zlúčenia.


## <a name="task-3---configure-the-subscription-churn-prediction"></a>Úloha 3 – Konfigurácia predikcie odchodov predplatiteľov

Po zavedení zjednotených profilov zákazníkov môžeme teraz spustiť predikciu odchodu predplatiteľov. Podrobné kroky nájdete v článku [Predikcia odchodu predplatiteľov (ukážka)](predict-subscription-churn.md). 

1. Prejdite na **Analýza** > **Objavovať** a vyberte použitie **Model odchodu zákazníkov**.

1. Vyberte možnosť **Predplatné** a vyberte **Začíname**.

1. Pomenujte model **Predikcia odchodov predplatiteľov OOB** a výstupnú entitu **OOBSubscriptionChurnPrediction**.

1. Definujte dve podmienky pre model odchodu:

   * **Dni od ukončenia predplatného**: **najmenej 60** dní. Ak zákazník neobnoví svoje predplatné v tomto období po skončení predplatného, považuje sa za odídeného. 

   * **Definícia odchodu**: **najmenej 93** dní. Doba, počas ktorej model predikuje, ktorí zákazníci by mohli odísť. Čím ďalej do budúcnosti budete pozerať, tým budú výsledky menej presné.

     :::image type="content" source="media/model-subs-levers.PNG" alt-text="Vyberte úrovne modelov Okno predikcie a Definícia odchodu.":::

1. Vyberte **Pridať požadované údaje** a **Pridať údaje** pre históriu predplatného.

1. Pridajte entitu **Subscription : SubscriptionHistory** a mapujte polia z eCommerce na zodpovedajúce polia požadované modelom.

1. Spojte entitu **Subscription : SubscriptionHistory** s **eCommerceContacts : eCommerce**, pomenujte vzťah **eCommerceSubscription**.

   :::image type="content" source="media/model-subscription-join.PNG" alt-text="Spojenie entít eCommerce.":::

1. V časti Aktivity zákazníkov pridajte entitu **webReviews : Website** a mapujte polia z webReviews na zodpovedajúce polia požadované modelom. 
   - Primárny kľúč: ReviewId
   - Časová pečiatka: ReviewDate
   - Udalosť: ReviewRating

1. Nakonfigurujte aktivitu pre recenzie na webových stránkach. Vyberte aktivitu **Recenzia** a spojte entitu **webReviews : Website** s **eCommerceContacts : eCommerce**.

1. Vyberte **Ďalej** na nastavenie plánu modelu.

   Model sa musí pravidelne trénovať, aby sa naučil nové vzorce, keď dôjde k prijatiu nových údajov. Pre tento príklad vyberte **Mesačne**.

1. Po skontrolovaní všetkých podrobností vyberte možnosť **Uložiť a spustiť**.

## <a name="task-4---review-model-results-and-explanations"></a>Úloha 4 – Skontrolujte výsledky modelu a vysvetlenia

Nechajte model absolvovať školenie a skórovanie údajov. Teraz si môžete vysvetlenie modelu odchodu predplatiteľov. Viac informácií nájdete v článku [Kontrola stavu predikcie a výsledkov](predict-subscription-churn.md#review-a-prediction-status-and-results).

## <a name="task-5---create-a-segment-of-high-churn-risk-customers"></a>Úloha 5 – Vytvorenie segmentu zákazníkov s vysokým rizikom odchodu

Spustením produkčného modelu sa vytvorí nová entita, ktorú môžete vidieť v ponuke **Údaje** > **Entity**.   

Nový segment môžete vytvoriť na základe entity vytvorenej modelom.

1.  Prejdite na **Segmenty**. Vyberte **Nový** následne **Vytvoriť z** > **Analýza**. 

   :::image type="content" source="media/segment-intelligence.PNG" alt-text="Vytvorenie segmentu s výstupom modelu.":::

1. Vyberte koncový bod **OOBSubscriptionChurnPrediction** a definujte segment: 
   - Pole: ChurnScore
   - Operátor: je väčšie ako
   - Hodnota: 0,6
   
   :::image type="content" source="media/segment-setup-subs.PNG" alt-text="Nastavenie segmentu odchodu predplatiteľov.":::

Teraz máte segment, ktorý sa dynamicky aktualizuje a ktorý identifikuje vysoko rizikových zákazníkov pre toto predplatné.

Ďalšie informácie nájdete v téme [Tvorba a správa segmentov](segments.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]