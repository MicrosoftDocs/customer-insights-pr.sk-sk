---
title: Predikcia odchodov založená na transakciách – vzorový sprievodca
description: V tomto vzorovom sprievodcovi môžete vyskúšať vopred pripravený model predikcie odchodov založený na transakciách.
ms.date: 11/19/2020
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: d3465b7eaa17a24e2926b8ea432b33e705931b88
ms.sourcegitcommit: 696ad9ab6e10046c00f1ac86a7e8fc37386e6fe7
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 04/08/2022
ms.locfileid: "8555378"
---
# <a name="transactional-churn-prediction-sample-guide"></a>Predikcia odchodov založená na transakciách – vzorový sprievodca

Táto príručka vám vysvetlí podrobný príklad predikcie odchodov založených na transakciách v nástroji Customer Insights pomocou nižšie uvedených údajov. Všetky údaje použité v tejto príručke nie sú skutočnými údajmi o zákazníkoch. Sú súčasťou súboru údajov Contoso, ktorý sa nachádza v *ukážkovom* prostredí v rámci vášho predplatného Customer Insights.

## <a name="scenario"></a>Scenár

Contoso je spoločnosť, ktorá vyrába vysokokvalitnú kávu a kávovary, ktoré predávajú prostredníctvom svojich webových stránok Contoso Coffee. Ich cieľom je zistiť, ktorí zákazníci, ktorí si zvyčajne nakupujú svoje produkty pravidelne, prestanú byť aktívnymi zákazníkmi v nasledujúcich 60 dňoch. Poznatok, ktorý z ich zákazníkov **pravdepodobne odíde**, im môže im pomôcť ušetriť marketingové úsilie zameraním na ich udržanie.

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

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Transformovať dátum narodenia na dátum.":::

1. V poli **Názov** na pravej table premenujte svoj zdroj údajov z **Dotaz** na **eCommerceContacts**

1. Uložte zdroj údajov.

### <a name="ingest-online-purchase-data"></a>Prijmite údaje o online nákupe

1. K tomu istému zdroju údajov **eCommerce** pridajte ďalšiu množinu údajov. Znova vyberte konektor **Text/CSV**.

1. Zadajte adresu URL pre údaje **Online nákupy** https://aka.ms/ciadclassonline.

1. Počas úpravy údajov vyberte **Transformovať** a potom **Použiť prvý riadok ako hlavičky**.

1. Aktualizujte typ údajov pre stĺpce uvedené nižšie:

   - **PurchasedOn**: Dátum/Čas
   - **TotalPrice**: Mena
   
1. V poli **Názov** na pravej table premenujte svoj zdroj údajov z **Dotaz** na **eCommercePurchases**.

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



## <a name="task-3---configure-transaction-churn-prediction"></a>Úloha 3 - Konfigurácia predikcie odchodov založených na transakciách

Po zavedení zjednotených profilov zákazníkov môžeme teraz spustiť predikciu odchodu predplatiteľov. Podrobné kroky nájdete na [Zrušenie predplatného predikcia](predict-subscription-churn.md) článok. 

1. Prejdite na **Analýza** > **Objavovať** a vyberte použitie **Model odchodu zákazníkov**.

1. Vyberte možnosť **Transakčné** a vyberte **Začíname**.

1. Pomenujte model **Predikcia odchodov založených na transakciách OOB** a výstupnú entitu **OOBeCommerceChurnPrediction**.

1. Definujte dve podmienky pre model odchodu:

   * **Okno predikcie**: **najmenej 60** dní. Toto nastavenie definuje, ako ďaleko do budúcnosti chceme predpovedať odchod zákazníkov.

   * **Definícia odchodu**: **najmenej 60** dní. Doba bez nákupu, po ktorej sa zákazník považuje za odídeného.

     :::image type="content" source="media/model-levers.PNG" alt-text="Vyberte úrovne modelov Okno predikcie a Definícia odchodu.":::

1. Vyberte **História nákupov (povinné)** a **Pridať údaje** pre históriu nákupov.

1. Pridajte entitu **eCommercePurchases: eCommerce** a mapujte polia z eCommerce na zodpovedajúce polia požadované modelom.

1. Spojte entitu **eCommercePurchases: eCommerce** s **eCommerceContacts: eCommerce**.

   :::image type="content" source="media/model-purchase-join.PNG" alt-text="Spojenie entít eCommerce.":::

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
