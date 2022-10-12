---
title: Predikcia odporúčania produktov – vzorový sprievodca
description: V tomto vzorovom sprievodcovi môžete vyskúšať vopred pripravený model predikcie odporúčaní produktov.
ms.date: 09/19/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: wameng
manager: shellyha
searchScope:
- ci-predictions
- ci-create-prediction
- customerInsights
ms.openlocfilehash: 2b42a89e3f4ec8cf4f0769128b8536973365f1cb
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610163"
---
# <a name="product-recommendation-prediction-sample-guide"></a>Predikcia odporúčania produktov – vzorový sprievodca

Táto príručka vás prevedie úplným príkladom odporúčania produktu predikcia pomocou vzorových údajov. Odporúčame vám vyskúšať tento predikcia [v novom prostredí](manage-environments.md).

## <a name="scenario"></a>Scenár

Contoso je spoločnosť, ktorá vyrába vysokokvalitnú kávu a kávovary. Produkty predávajú prostredníctvom svojej webovej stránky Contoso Coffee. Ich cieľom je pochopiť, ktoré produkty by mali odporúčať svojim opakujúcim sa zákazníkom. Vedieť, čo sú zákazníci viac **pravdepodobne kúpi** im môže pomôcť ušetriť marketingové úsilie zameraním sa na konkrétne položky.

## <a name="prerequisites"></a>Požiadavky

- Minimálne [povolenia prispievateľa](permissions.md) v Customer Insights.

## <a name="task-1---ingest-data"></a>Úloha 1 – Príjem údajov

Prečítajte si články [o prijímaní údajov](data-sources.md) a [pripojenie k a Power Query zdroj údajov](connect-power-query.md). Nasledujúce informácie predpokladajú, že ste oboznámení s prijímaním údajov vo všeobecnosti.

### <a name="ingest-customer-data-from-ecommerce-platform"></a>Príjem údajov o zákazníkoch z platformy eCommerce

1. Vytvorte Power Query zdroj údajov s názvom **eCommerce** a vyberte **Text/CSV** konektor.

1. Zadajte adresu URL kontaktov elektronického obchodu:https://aka.ms/ciadclasscontacts.

1. Počas upravovania údajov vyberte **Transformovať** a potom **Použite prvý riadok ako hlavičky**.

1. Aktualizujte typ údajov pre stĺpce uvedené nižšie:
   - **DateOfBirth**: Dátum
   - **CreatedOn**: Dátum/Čas/Pásmo

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Transformácia dátumu narodenia na dátum.":::

1. V **názov** pole na pravej table premenujte zdroj údajov na **kontakty elektronického obchodu**.

1. **Uložte** zdroj údajov.

### <a name="ingest-online-purchase-data"></a>Prijmite údaje o online nákupe

1. K tomu istému zdroju údajov **eCommerce** pridajte ďalšiu množinu údajov. Znova vyberte konektor **Text/CSV**.

1. Zadajte webovú adresu pre údaje o online nákupoch https://aka.ms/ciadclassonline.

1. Počas upravovania údajov vyberte **Transformovať** a potom **Použite prvý riadok ako hlavičky**.

1. Aktualizujte typ údajov pre stĺpce uvedené nižšie:
   - **PurchasedOn**: Dátum/Čas
   - **TotalPrice**: Mena

1. V **názov** pole na bočnom paneli premenujte zdroj údajov na **eCommerceNákupy**.

1. **Uložte** zdroj údajov.

### <a name="ingest-customer-data-from-loyalty-schema"></a>Príjem údaje o zákazníkoch z vernostnej schémy

1. Vytvorte zdroj údajov s názvom **LoyaltyScheme** a vyberte **Text/CSV** konektor.

1. Zadajte adresu URL pre verných zákazníkov https://aka.ms/ciadclasscustomerloyalty.

1. Počas upravovania údajov vyberte **Transformovať** a potom **Použite prvý riadok ako hlavičky**.

1. Aktualizujte typ údajov pre stĺpce uvedené nižšie:
   - **DateOfBirth**: Dátum
   - **RewardsPoints**: Celé číslo
   - **CreatedOn**: Dátum/Čas

1. V **názov** pole na pravej table premenujte zdroj údajov na **loyZákazníci**.

1. **Uložte** zdroj údajov.

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

## <a name="task-4---configure-product-recommendation-prediction"></a>Úloha 4 – Konfigurácia predikcie odporúčania produktu

So zjednotenými profilmi zákazníkov a vytvorenou aktivitou spustite odporúčanie produktu predikcia.

1. Ísť do **Inteligencia** > **Predpovede**.

1. Na **Vytvorte** kartu, vyberte **Použite model** na **Odporúčania produktov (ukážka)** dlaždica.

1. Vyberte **Začíname**.

1. Pomenujte model **Predikcia modelu odporúčania produktu OOB** a výstupnú entitu **OOBProductRecommendationModelPrediction**.

1. Vyberte **Ďalej**.

1. Definujte preferencie modelu:
   - **Počet produktov** :**5** definovať, koľko produktov chcete odporučiť svojim zákazníkom.
   - **Očakávajú sa opakované nákupy** :**Áno** zahrnúť do odporúčania už zakúpené produkty.
   - **Pohľad dozadu:** **365 dní** na definovanie toho, ako ďaleko sa bude model obzerať pred ďalším odporúčaním produktu.

   :::image type="content" source="media/product-recommendation-model-preferences.png" alt-text="Predvoľby modelu odporúčaní produktov.":::

1. Vyberte **Ďalej**.

1. V **Pridajte históriu nákupov** krok, vyberte **Pridajte údaje**.

1. Vyberte **SalesOrderLine** a entitu eCommercePurchases a vyberte **Ďalšie**. Požadované údaje sa automaticky vyplnia z aktivity. Vyberte **Uložiť** a potom **Ďalšie**.

1. Preskočte **Pridajte informácie o produkte** a **Produktové filtre** kroky, pretože nemáme informácie o produkte.

1. V **Aktualizácie údajov** krok, vyberte **Mesačne** pre modelový harmonogram.

1. Vyberte **Ďalej**.

1. Po skontrolovaní všetkých podrobností vyberte možnosť **Uložiť a spustiť**.

## <a name="task-5---review-model-results-and-explanations"></a>Úloha 5 – Skontrolujte výsledky modelu a vysvetlenia

Nechajte model absolvovať školenie a skórovanie údajov. Skontrolujte [vysvetlenia modelov odporúčaní produktov](predict-transactional-churn.md#view-prediction-results).

## <a name="task-6---create-a-segment-of-high-purchased-products"></a>Úloha 6 – Vytvorte segment najčastejšie kupovaných produktov

Spustením modelu sa vytvorí nová entita, ktorá je uvedená na zozname **Údaje** > **Entity**. Nový segment môžete vytvoriť na základe entity vytvorenej modelom.

1. Na stránke s výsledkami vyberte možnosť **Vytvoriť segment**.

1. Vytvorte pravidlo pomocou **OOBProductRecommendationModelPrediction** entity a definujte segment:
   - **Lúka** : Identifikačné číslo produktu
   - **Hodnota** : Vyberte tri najlepšie ID produktov

1. Vyberte **Uložiť** a **Bežať** segmente.

Teraz máte segment, ktorý sa dynamicky aktualizuje a ktorý identifikuje zákazníkov, ktorí by mohli mať záujem o kúpu piatich najviac odporúčaných produktov. Ďalšie informácie nájdete v téme [Tvorba a správa segmentov](segments.md).

> [!TIP]
> Môžete tiež vytvoriť segment pre model predikcia z **Segmenty** stránku výberom **Nový** a výberom **Vytvoriť z** > **Inteligencia**. Ďalšie informácie nájdete v časti [Vytvorte nový segment s rýchlymi segmentmi](segment-quick.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
