---
title: Predikcia odchodu predplatiteľov – vzorový sprievodca
description: V tomto vzorovom sprievodcovi môžete vyskúšať vopred pripravený model predikcie odchodu predplatiteľov.
ms.date: 09/19/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: wameng
manager: shellyha
searchScope:
- ci-create-prediction
- customerInsights
ms.openlocfilehash: 7e754be9a2cb9450949c6b3667bbd37aa39cf0bf
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610025"
---
# <a name="subscription-churn-prediction-sample-guide"></a>Predikcia odchodu predplatiteľov – vzorový sprievodca

Táto príručka vám vysvetlí úplný príklad zrušenia predplatného predikcia pomocou vzorových údajov. Odporúčame vám vyskúšať tento predikcia [v novom prostredí](manage-environments.md).

## <a name="scenario"></a>Scenár

Contoso je spoločnosť, ktorá vyrába vysokokvalitnú kávu a kávovary. Produkty predávajú prostredníctvom svojej webovej stránky Contoso Coffee. Nedávno začali ponúkať pre svojich zákazníkov možnosť predplatného, aby mohli pravidelne dostávať kávu. Ich cieľom je pochopiť, ktorí odberatelia môžu zrušiť svoje predplatné v najbližších mesiacoch. Vedieť, ktorý z ich zákazníkov je **pravdepodobné, že sa bude krútiť** im môže pomôcť ušetriť marketingové úsilie tým, že sa zameria na ich udržanie.

## <a name="prerequisites"></a>Požiadavky

- Minimálne [povolenia prispievateľa](permissions.md) v Customer Insights.

## <a name="task-1---ingest-data"></a>Úloha 1 – Príjem údajov

Prečítajte si články [o prijímaní údajov](data-sources.md) a [pripojenie k a Power Query zdroj údajov](connect-power-query.md). Nasledujúce informácie predpokladajú, že ste oboznámení s prijímaním údajov vo všeobecnosti.

### <a name="ingest-customer-data-from-ecommerce-platform"></a>Príjem údajov o zákazníkoch z platformy eCommerce

1. Vytvorte Power Query zdroj údajov s názvom **eCommerce** a vyberte **Text/CSV** konektor.

1. Zadajte adresu URL kontaktov pre eCommerce https://aka.ms/ciadclasscontacts.

1. Počas upravovania údajov vyberte **Transformovať** a potom **Použite prvý riadok ako hlavičky**.

1. Aktualizujte typ údajov pre stĺpce uvedené nižšie:
   - **DateOfBirth**: Dátum
   - **CreatedOn**: Dátum/Čas/Pásmo

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Transformácia dátumu narodenia na dátum.":::

1. V **názov** pole na pravej table premenujte zdroj údajov na **kontakty elektronického obchodu**

1. Uložte zdroj údajov.

### <a name="ingest-customer-data-from-loyalty-schema"></a>Príjem údaje o zákazníkoch z vernostnej schémy

1. Vytvorte zdroj údajov s názvom **LoyaltyScheme** a vyberte **Text/CSV** konektor.

1. Zadajte adresu URL pre vernostných zákazníkov https://aka.ms/ciadclasscustomerloyalty.

1. Počas upravovania údajov vyberte **Transformovať** a potom **Použite prvý riadok ako hlavičky**.

1. Aktualizujte typ údajov pre stĺpce uvedené nižšie:
   - **DateOfBirth**: Dátum
   - **RewardsPoints**: Celé číslo
   - **CreatedOn**: Dátum/Čas

1. V **názov** pole na pravej table premenujte zdroj údajov na **loyZákazníci**.

1. Uložte zdroj údajov.

### <a name="ingest-subscription-information"></a>Príjem informácií o predplatnom

1. Vytvorte zdroj údajov s názvom **História predplatného** a vyberte **Text/CSV** konektor.

1. Zadajte adresu URL pre odbery https://aka.ms/ciadchurnsubscriptionhistory.

1. Počas upravovania údajov vyberte **Transformovať** a potom **Použite prvý riadok ako hlavičky**.

1. Aktualizujte typ údajov pre stĺpce uvedené nižšie:
   - **SubscriptioID**: Celé číslo
   - **SubscriptionAmount**: Mena
   - **SubscriptionEndDate**: Dátum/Čas
   - **SubscriptionStartDate**: Dátum/Čas
   - **TransactionDate**: Dátum/Čas
   - **IsRecurring**: Pravda/Nepravda
   - **Is_auto_renew**: Pravda/Nepravda
   - **RecurringFrequencyInMonths**: Celé číslo

1. V **názov** pole na pravej table premenujte zdroj údajov na **História predplatného**.

1. Uložte zdroj údajov.

### <a name="ingest-customer-data-from-website-reviews"></a>Príjem údajov o zákazníkoch z recenzií na webe

1. Vytvorte zdroj údajov s názvom **webové stránky** a vyberte **Text/CSV** konektor.

1. Zadajte adresu URL pre recenzie webových stránok https://aka.ms/ciadclasswebsite.

1. Počas upravovania údajov vyberte **Transformovať** a potom **Použite prvý riadok ako hlavičky**.

1. Aktualizujte typ údajov pre stĺpce uvedené nižšie:
   - **ReviewRating**: Celé číslo
   - **ReviewDate**: Dátum

1. V **názov** pole na pravej table premenujte zdroj údajov na **webReviews**.

## <a name="task-2---data-unification"></a>Úloha 2 – Zjednotenie údajov

Prečítajte si článok [o zjednotení údajov](data-unification.md). Nasledujúce informácie predpokladajú, že ste oboznámení so zjednocovaním údajov vo všeobecnosti.

[!INCLUDE [sample-guide-unification](includes/sample-guide-unification.md)]

## <a name="task-3---create-transaction-history-activity"></a>Úloha 3 - Vytvorte aktivitu histórie transakcií

Prečítajte si článok [o zákazníckych aktivitách](activities.md). Nasledujúce informácie predpokladajú, že ste oboznámení s vytváraním aktivít vo všeobecnosti.

1. Vytvorte aktivitu tzv **História predplatného** s *Predplatné* entita a jej primárny kľúč, **CustomerId**.

1. Vytvorte vzťah medzi *História predplatného: Predplatné* a *eCommerceContacts:eCommerce* s **CustomerID** ako cudzí kľúč na prepojenie dvoch entít.

1. Vyberte **Typ predplatného** pre **EventActivity** a **Dátum konca predplatného** pre **Časová značka**.

1. Vyberte **Predplatné** pre **Typ aktivity** a sémanticky mapovať údaje o činnosti.

1. Spustite aktivitu.

1. Pridajte ďalšiu aktivitu a priraďte názvy jej polí k zodpovedajúcim poliam:
   - Entita aktivity zákazníka: Recenzie: Webová lokalita
   - Primárny kľúč: Website.Reviews.ReviewId
   - Časová pečiatka: Website.Reviews.ReviewDate
   - Udalosť (názov aktivity): Website.Reviews.ActivityTypeDisplay
   - Podrobnosti (suma alebo hodnota): Website.Reviews.ReviewRating

1. Spustite aktivitu.

## <a name="task-4---configure-the-subscription-churn-prediction"></a>Úloha 4 – Konfigurácia predikcie odchodov predplatiteľov

So zjednotenými zákazníckymi profilmi a vytvorenými aktivitami spustite predplatné churn predikcia. Podrobné kroky nájdete v časti [Zrušenie predplatného predikcia](predict-subscription-churn.md).

1. Ísť do **Inteligencia** > **Predpovede**.

1. Na **Vytvorte** kartu, vyberte **Použite model** na **Model odchodu zákazníkov** dlaždica.

1. Vyberte **Predplatné** pre typ churn a potom **Začať**.

1. Pomenujte model **Predikcia odchodov predplatiteľov OOB** a výstupnú entitu **OOBSubscriptionChurnPrediction**.

1. Definujte preferencie modelu:
   - **Dni od ukončenia predplatného** :**60** dní na označenie, že zákazník sa považuje za zrušeného, ak neobnoví predplatné v tomto období po skončení predplatného.
   - **Dni na skúmanie budúcnosti, aby sa predpovedalo miznutie** :**93** dní, čo je trvanie, počas ktorého model predpovedá, ktorí zákazníci môžu míňať. Čím ďalej do budúcnosti budete pozerať, tým budú výsledky menej presné.

   :::image type="content" source="media/model-subs-levers.PNG" alt-text="Vyberte preferencie modelu a definíciu odchodu.":::

1. Vyberte **Ďalej**.

1. V **Požadované údaje** krok, vyberte **Pridajte údaje** poskytnúť históriu predplatného.

1. Vyberte **Predplatné** a entitu SubscriptionHistory a vyberte **Ďalšie**. Požadované údaje sa automaticky vyplnia z aktivity. Vyberte **Uložiť**.

1. V časti Zákaznícke aktivity vyberte **Pridajte údaje**.

1. V tomto príklade pridajte aktivitu kontroly webu.

1. Vyberte **Ďalej**.

1. V **Aktualizácie údajov** krok, vyberte **Mesačne** pre modelový harmonogram.

1. Po skontrolovaní všetkých podrobností vyberte možnosť **Uložiť a spustiť**.

## <a name="task-5---review-model-results-and-explanations"></a>Úloha 5 – Skontrolujte výsledky modelu a vysvetlenia

Nechajte model absolvovať školenie a skórovanie údajov. Prezrite si vysvetlenia modelu ukončenia odberu. Ďalšie informácie nájdete v časti [Zobraziť výsledky predikcia](predict-subscription-churn.md#view-prediction-results).

## <a name="task-6---create-a-segment-of-high-churn-risk-customers"></a>Úloha 6 – Vytvorenie segmentu zákazníkov s vysokým rizikom odchodu

Spustením modelu sa vytvorí nová entita, ktorá je uvedená na zozname **Údaje** > **Entity**. Nový segment môžete vytvoriť na základe entity vytvorenej modelom.

1. Na stránke s výsledkami vyberte možnosť **Vytvoriť segment**.

1. Vytvorte pravidlo pomocou **OOBSubscriptionChurnPrediction** entity a definujte segment:
   - **Lúka** : ChurnScore
   - **Operátor** : väčší než
   - **Hodnota** : 0,6

1. Vyberte **Uložiť** a **Bežať** segmente.

Teraz máte segment, ktorý sa dynamicky aktualizuje a ktorý identifikuje vysoko rizikových zákazníkov pre toto predplatné. Ďalšie informácie nájdete v téme [Tvorba a správa segmentov](segments.md).

> [!TIP]
> Môžete tiež vytvoriť segment pre model predikcia z **Segmenty** stránku výberom **Nový** a výberom **Vytvoriť z** > **Inteligencia**. Ďalšie informácie nájdete v časti [Vytvorte nový segment s rýchlymi segmentmi](segment-quick.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
