---
title: Predikcia odchodov založená na transakciách – vzorový sprievodca
description: V tomto vzorovom sprievodcovi môžete vyskúšať vopred pripravený model predikcie odchodov založený na transakciách.
ms.date: 09/19/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 0ccc32b6e5e96adf6f2fa8c6d52960a07d1513f3
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 09/30/2022
ms.locfileid: "9609704"
---
# <a name="transactional-churn-prediction-sample-guide"></a>Predikcia odchodov založená na transakciách – vzorový sprievodca

Táto príručka vám vysvetlí úplný príklad prechodu transakcií predikcia pomocou vzorových údajov. Odporúčame vám vyskúšať tento predikcia [v novom prostredí](manage-environments.md).

## <a name="scenario"></a>Scenár

Contoso je spoločnosť, ktorá vyrába vysokokvalitnú kávu a kávovary. Produkty predávajú prostredníctvom svojej webovej stránky Contoso Coffee. Ich cieľom je zistiť, ktorí zákazníci, ktorí si zvyčajne nakupujú svoje produkty pravidelne, prestanú byť aktívnymi zákazníkmi v nasledujúcich 60 dňoch. Poznatok, ktorý z ich zákazníkov **pravdepodobne odíde**, im môže im pomôcť ušetriť marketingové úsilie zameraním na ich udržanie.

## <a name="prerequisites"></a>Požiadavky

- Minimálne [povolenia prispievateľa](permissions.md).

## <a name="task-1---ingest-data"></a>Úloha 1 – Príjem údajov

Prečítajte si články [o prijímaní údajov](data-sources.md) a [pripojenie k a Power Query zdroj údajov](connect-power-query.md). Nasledujúce informácie predpokladajú, že ste oboznámení s prijímaním údajov vo všeobecnosti.

### <a name="ingest-customer-data-from-ecommerce-platform"></a>Príjem údajov o zákazníkoch z platformy eCommerce

1. Vytvorte zdroj údajov s názvom **eCommerce** a vyberte **Text/CSV** konektor.

1. Zadajte adresu URL kontaktov pre eCommerce https://aka.ms/ciadclasscontacts.

1. Počas upravovania údajov vyberte **Transformovať** a potom **Použite prvý riadok ako hlavičky**.

1. Aktualizujte typ údajov pre stĺpce uvedené nižšie:

   - **DateOfBirth**: Dátum
   - **CreatedOn**: Dátum/Čas/Pásmo

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Transformovať dátum narodenia na dátum.":::

1. V **názov** pole na pravej table premenujte zdroj údajov na **kontakty elektronického obchodu**

1. Uložte zdroj údajov.

### <a name="ingest-online-purchase-data"></a>Prijmite údaje o online nákupe

1. K tomu istému zdroju údajov **eCommerce** pridajte ďalšiu množinu údajov. Znova vyberte konektor **Text/CSV**.

1. Zadajte webovú adresu pre údaje o online nákupoch https://aka.ms/ciadclassonline.

1. Počas upravovania údajov vyberte **Transformovať** a potom **Použite prvý riadok ako hlavičky**.

1. Aktualizujte typ údajov pre stĺpce uvedené nižšie:

   - **PurchasedOn**: Dátum/Čas
   - **TotalPrice**: Mena

1. V **názov** pole na pravej table premenujte zdroj údajov na **eCommerceNákupy**.

1. Uložte zdroj údajov.

### <a name="ingest-customer-data-from-loyalty-schema"></a>Príjem údaje o zákazníkoch z vernostnej schémy

1. Vytvorte zdroj údajov s názvom **LoyaltyScheme** a vyberte **Text/CSV** konektor.

1. Zadajte adresu URL kontaktov pre eCommerce https://aka.ms/ciadclasscustomerloyalty.

1. Počas upravovania údajov vyberte **Transformovať** a potom **Použite prvý riadok ako hlavičky**.

1. Aktualizujte typ údajov pre stĺpce uvedené nižšie:

   - **DateOfBirth**: Dátum
   - **RewardsPoints**: Celé číslo
   - **CreatedOn**: Dátum/Čas

1. V **názov** pole na pravej table premenujte zdroj údajov na **loyZákazníci**.

1. Uložte zdroj údajov.

## <a name="task-2---data-unification"></a>Úloha 2 – Zjednotenie údajov

Prečítajte si článok [o zjednotení údajov](data-unification.md). Nasledujúce informácie predpokladajú, že ste oboznámení so zjednocovaním údajov vo všeobecnosti.

[!INCLUDE [sample-guide-unification](includes/sample-guide-unification.md)]

## <a name="task-3---create-transaction-history-activity"></a>Úloha 3 - Vytvorte aktivitu histórie transakcií

Prečítajte si článok [o zákazníckych aktivitách](activities.md). Nasledujúce informácie predpokladajú, že ste oboznámení s vytváraním aktivít vo všeobecnosti.

1. Vytvorte aktivitu tzv **eCommerceNákupy** s *eCommerceNákupy:eCommerce* entita a jej primárny kľúč, **Id nákupu**.

1. Vytvorte vzťah medzi *eCommerceNákupy:eCommerce* a *eCommerceContacts:eCommerce* s **ContactID** ako cudzí kľúč na prepojenie dvoch entít.

1. Vyberte **Celková cena** pre **EventActivity** a **ZakúpenéOn** pre **Časová značka**.

1. Vyberte **SalesOrderLine** pre **Typ aktivity** a sémanticky mapovať údaje o činnosti.

1. Spustite aktivitu.

## <a name="task-4---configure-transaction-churn-prediction"></a>Úloha 4 - Konfigurácia predikcie odchodov založených na transakciách

So zjednotenými zákazníckymi profilmi a aktivitami spustite transakciu predikcia.

1. Ísť do **Inteligencia** > **Predpovede**.

1. Na **Vytvorte** kartu, vyberte **Použite model** na **Model odchodu zákazníkov**.

1. Vyberte **Transakčný** pre typ churn a potom **Začať**.

1. Pomenujte model **Predikcia odchodov založených na transakciách OOB** a výstupnú entitu **OOBeCommerceChurnPrediction**.

1. Vyberte **Ďalej**.

1. Definujte preferencie modelu:

   - **predikcia okno** :**60** dní, aby sme definovali, ako ďaleko do budúcnosti chceme predpovedať odchod zákazníkov.

   - **Definícia odchodu** :**60** dní na uvedenie trvania bez nákupu, po uplynutí ktorého sa zákazník považuje za zrušeného.

     :::image type="content" source="media/model-levers.PNG" alt-text="Vyberte predvoľby modelu predikcia Window and Churn Definition.":::

1. Vyberte **Ďalej**.

1. Vyberte **História nákupov (povinné)** a **Pridať údaje** pre históriu nákupov.

1. Vyberte **SalesOrderLine** a entitu eCommercePurchases a vyberte **Ďalšie**. Požadované údaje sa automaticky vyplnia z aktivity. Vyberte **Uložiť** a potom **Ďalšie**.

   :::image type="content" source="media/model-purchase-join.PNG" alt-text="Spojenie entít eCommerce.":::

1. Preskočte **Ďalšie údaje (voliteľné)** krok.

1. V **Aktualizácie údajov** krok, vyberte **Mesačne** pre modelový harmonogram.

1. Po skontrolovaní všetkých podrobností vyberte možnosť **Uložiť a spustiť**.

## <a name="task-5---review-model-results-and-explanations"></a>Úloha 5 – Skontrolujte výsledky modelu a vysvetlenia

Nechajte model absolvovať školenie a skórovanie údajov. Prezrite si vysvetlenia k modelu vracania. Ďalšie informácie nájdete v časti [Zobraziť výsledky predikcia](predict-transactional-churn.md#view-prediction-results).

## <a name="task-6---create-a-segment-of-high-churn-risk-customers"></a>Úloha 6 – Vytvorenie segmentu zákazníkov s vysokým rizikom odchodu

Spustením produkčného modelu sa vytvorí nová entita, ktorá je uvedená na **Údaje** > **entity**. Nový segment môžete vytvoriť na základe entity vytvorenej modelom.

1. Na stránke s výsledkami vyberte možnosť **Vytvoriť segment**.

1. Vytvorte pravidlo pomocou **OOBeCommerceChurnPrediction** entity a definujte segment:
   - **Lúka** : ChurnScore
   - **Operátor** : väčší než
   - **Hodnota** : 0,6

1. Vyberte **Uložiť** a **Bežať** segmente.

Teraz máte segment, ktorý sa dynamicky aktualizuje a ktorý identifikuje zákazníkov s vysokým rizikom odchodu. Ďalšie informácie nájdete v téme [Tvorba a správa segmentov](segments.md).

> [!TIP]
> Môžete tiež vytvoriť segment pre model predikcia z **Segmenty** stránku výberom **Nový** a výberom **Vytvoriť z** > **Inteligencia**. Ďalšie informácie nájdete v časti [Vytvorte nový segment s rýchlymi segmentmi](segment-quick.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
