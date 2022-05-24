---
title: Predikcia odchodu predplatiteľov – vzorový sprievodca
description: V tomto vzorovom sprievodcovi môžete vyskúšať vopred pripravený model predikcie odchodu predplatiteľov.
ms.date: 03/31/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: wameng
manager: shellyha
searchScope:
- ci-create-prediction
- customerInsights
ms.openlocfilehash: 5a8eeafecacef3d0bb4a798b698cf490423ca98d
ms.sourcegitcommit: 6a5f4312a2bb808c40830863f26620daf65b921d
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 05/11/2022
ms.locfileid: "8741430"
---
# <a name="subscription-churn-prediction-sample-guide"></a>Predikcia odchodu predplatiteľov – vzorový sprievodca

Prejdeme si podrobný príklad predikcie odchodov predplatiteľov pomocou nižšie uvedených údajov. 

## <a name="scenario"></a>Scenár

Contoso je spoločnosť, ktorá vyrába vysokokvalitnú kávu a kávovary, ktoré predávajú prostredníctvom svojich webových stránok Contoso Coffee. Nedávno začali ponúkať pre svojich zákazníkov možnosť predplatného, aby mohli pravidelne dostávať kávu. Ich cieľom je pochopiť, ktorí zákazníci s predplatným môžu predplatné v najbližších mesiacoch zrušiť. Poznatok, ktorý z ich zákazníkov **pravdepodobne odíde**, im môže im pomôcť ušetriť marketingové úsilie zameraním na ich udržanie.

## <a name="prerequisites"></a>Predpoklady

- Minimálne [povolenia prispievateľa](permissions.md) v Customer Insights.
- Odporúčame vám vykonať nasledujúce kroky [v novom prostredí](manage-environments.md).

## <a name="task-1---ingest-data"></a>Úloha 1 – Príjem údajov

Prečítajte si články [o prijímaní údajov](data-sources.md) a [importovanie zdrojov údajov pomocou Power Query konektory](connect-power-query.md) konkrétne. Nasledujúce informácie predpokladajú, že ste sa oboznámili s prijímaním údajov vo všeobecnosti. 

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

[!INCLUDE [sample-guide-unification](includes/sample-guide-unification.md)]

## <a name="task-3---configure-the-subscription-churn-prediction"></a>Úloha 3 – Konfigurácia predikcie odchodov predplatiteľov

Po zavedení zjednotených profilov zákazníkov môžeme teraz spustiť predikciu odchodu predplatiteľov. Podrobné kroky nájdete na [Zrušenie predplatného predikcia](predict-subscription-churn.md) článok. 

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


[!INCLUDE [footer-include](includes/footer-banner.md)]