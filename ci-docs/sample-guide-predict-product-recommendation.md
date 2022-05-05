---
title: Predikcia odporúčania produktov – vzorový sprievodca
description: V tomto vzorovom sprievodcovi môžete vyskúšať vopred pripravený model predikcie odporúčaní produktov.
ms.date: 02/10/2021
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
ms.openlocfilehash: 1115bab13bdca4a308a8d9eb5a1dc270801d16be
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 04/27/2022
ms.locfileid: "8643583"
---
# <a name="product-recommendation-prediction-sample-guide"></a>Predikcia odporúčania produktov – vzorový sprievodca

Prejdeme si podrobný príklad predikcie odporúčaní produktov pomocou nižšie uvedených ukážkových údajov.

## <a name="scenario"></a>Scenár

Contoso je spoločnosť, ktorá vyrába vysokokvalitnú kávu a kávovary, ktoré predávajú prostredníctvom svojich webových stránok Contoso Coffee. Ich cieľom je pochopiť, ktoré produkty by mali odporúčať svojim opakujúcim sa zákazníkom. Ak budete vedieť, čo si zákazníci s **väčšou pravdepodobnosťou kúpia**, môže vám to pomôcť ušetriť marketingové úsilie zameraním na konkrétne položky.

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

5. V poli „Názov“ na pravej table premenujte svoj zdroj údajov z **Dotaz** na **eCommerceContacts**

6. **Uložte** zdroj údajov.

### <a name="ingest-online-purchase-data"></a>Prijmite údaje o online nákupe

1. K tomu istému zdroju údajov **eCommerce** pridajte ďalšiu množinu údajov. Znova vyberte konektor **Text/CSV**.

1. Zadajte adresu URL pre údaje **Online nákupy** https://aka.ms/ciadclassonline.

1. Počas úpravy údajov vyberte **Transformovať** a potom **Použiť prvý riadok ako hlavičky**.

1. Aktualizujte typ údajov pre stĺpce uvedené nižšie:
   - **PurchasedOn**: Dátum/Čas
   - **TotalPrice**: Mena

1. V poli **Názov** na bočnej table premenujte svoj zdroj údajov z **Dotaz** na **eCommercePurchases**.

1. **Uložte** zdroj údajov.


### <a name="ingest-customer-data-from-loyalty-schema"></a>Príjem údaje o zákazníkoch z vernostnej schémy

1. Vytvorte zdroj údajov s názvom **LoyaltyScheme**, vyberte možnosť importu a vyberte konektor **Text/CSV**.

1. Zadajte adresu URL kontaktov pre eCommerce https://aka.ms/ciadclasscustomerloyalty.

1. Počas úpravy údajov vyberte **Transformovať** a potom **Použiť prvý riadok ako hlavičky**.

1. Aktualizujte typ údajov pre stĺpce uvedené nižšie:
   - **DateOfBirth**: Dátum
   - **RewardsPoints**: Celé číslo
   - **CreatedOn**: Dátum/Čas

1. V poli **Názov** na pravej table premenujte svoj zdroj údajov z **Dotaz** na **loyCustomers**.

1. **Uložte** zdroj údajov.

## <a name="task-2---data-unification"></a>Úloha 2 – Zjednotenie údajov

Po prijatí údajov teraz začneme proces zjednocovania údajov, aby sme vytvorili jednotný profil zákazníka. Ďalšie informácie nájdete v téme [Zjednotenie údajov](data-unification.md).

### <a name="map"></a>Priradenie

1. Po prijatí údajov namapujte kontakty z údajov eCommerce a Loyalty na bežné typy údajov. Prejdite na **Údaje** > **Zjednotenie** > **Mapovanie**.

2. Vyberte entity, ktoré zastupujú profil zákazníka – **eCommerceContacts** a **loyCustomers**.

   ![Zjednotenie zdrojov údajov elektronického obchodu a vernostných údajov.](media/unify-ecommerce-loyalty.png)

3. Vyberte **ContactId** ako primárny kľúč pre **eCommerceContacts** a **LoyaltyID** ako primárny kľúč pre **loyCustomers**.

   ![Zjednotenie LoyaltyId ako primárny kľúč.](media/unify-loyaltyid.png)

### <a name="match"></a>Spárovanie

1. Prejdite na kartu **Spárovanie** a vyberte **Nastaviť poradie**.

2. V **primárnom** rozbaľovacom zozname si vyberte možnosť **eCommerceContacts: eCommerce** ako primárny zdroj a zahrňte do nej všetky záznamy.

3. V rozbaľovacom zozname **Entita 2** vyberte možnosť **loyCustomers: LoyaltyScheme** a zahrňte do nej všetky záznamy.

   ![Zjednotenie zosúladenia eCommerce a Loyalty.](media/unify-match-order.png)

4. Vyberte **Vytvoriť nové pravidlo**

5. Pridajte svoju prvú podmienku pomocou FullName.

   - V prípade eCommerceContacts vyberte z rozbaľovacieho zoznamu položku **FullName**.
   - V prípade loyCustomers vyberte z rozbaľovacieho zoznamu položku **FullName**.
   - Vyberte rozbaľovací zoznam **Normalizovať** a vyberte **Typ (Telefón, Meno, Adresa, ...)**.
   - Nastavte **Úroveň presnosti**: **Základná** a **Hodnota**: **Vysoká**.

6. Zadajte meno **FullName, E-mail** pre nové pravidlo.

   - Vyberte druhú podmienku pre e-mailovú adresu výberom možnosti **Pridať podmienku**
   - Pri entite eCommerceContacts vyberte z rozbaľovacieho zoznamu položku **EMail**.
   - Pri entite loyCustomers vyberte z rozbaľovacieho zoznamu položku **EMail**.
   - Pole Normalizovať nechajte prázdne.
   - Nastavte **Úroveň presnosti**: **Základná** a **Hodnota**: **Vysoká**.

   ![Pravidlo zjednotenia zhody pre meno a e-mail.](media/unify-match-rule.png)

7. Vyberte položku **Uložiť** a **Spustiť**.

### <a name="merge"></a>Zlúčenie

1. Prejdite na kartu **Zlúčiť**.

1. V entite **ContactId** pre **loyCustomers** zmeňte zobrazovaný názov na **ContactIdLOYALTY** na odlíšenie od ostatných prijatých ID.

   ![premenovanie contactid z loyaltyid.](media/unify-merge-contactid.png)

1. Vyberte **Uložiť** a **Spustiť** na začatie procesu zlúčenia.

## <a name="task-3---configure-product-recommendation-prediction"></a>Úloha 3 – Konfigurácia predikcie odporúčania produktu

Po zavedení zjednotených profilov zákazníkov môžeme teraz spustiť predikciu odchodu predplatiteľov.

1. Prejdite na **Analýza** > **Predikcia** vyberte **Odporúčanie produktu**.

1. Vyberte **Začíname**.

1. Pomenujte model **Predikcia modelu odporúčania produktu OOB** a výstupnú entitu **OOBProductRecommendationModelPrediction**.

1. Definujte tri podmienky pre model:

   - **Počet produktov**: Nastavte túto hodnotu na **5**. Toto nastavenie definuje, koľko produktov chcete odporučiť zákazníkom.

   - **Očakávané opakované nákupy**: Vyberte **Áno** na označenie, že chcete zahrnúť produkty do odporúčania, ktoré si vaši zákazníci predtým kúpili.

   - **Dĺžka spätného zobrazenia:** Vyberte minimálne **365 dní**. Toto nastavenie definuje, ako ďaleko do minulosti bude model pozerať na aktivitu zákazníka, aby ju použil ako vstup jeho odporúčania.
   
   :::image type="content" source="media/product-recommendation-model-preferences.png" alt-text="Predvoľby modelu odporúčaní produktov.":::

1. Vyberte **Požadované údaje** a **Pridať údaje** pre históriu nákupov.

1. Pridajte entitu **eCommercePurchases: eCommerce** a mapujte polia z eCommerce na zodpovedajúce polia požadované modelom.

1. Spojte entitu **eCommercePurchases: eCommerce** s **eCommerceContacts: eCommerce**.

   ![Spojenie entít eCommerce.](media/model-purchase-join.png)

1. Vyberte **Ďalej** na nastavenie plánu modelu.

   Model sa musí pravidelne trénovať, aby sa naučil nové vzorce, keď dôjde k prijatiu nových údajov. Pre tento príklad vyberte **Mesačne**.

1. Po skontrolovaní všetkých podrobností vyberte možnosť **Uložiť a spustiť**.


## <a name="task-4---review-model-results-and-explanations"></a>Úloha 4 – Skontrolujte výsledky modelu a vysvetlenia

Nechajte model absolvovať školenie a skórovanie údajov. Teraz si môžete skontrolovať vysvetlenie modelu odporúčaní produktov. Viac informácií nájdete v článku [Kontrola stavu predikcie a výsledkov](predict-subscription-churn.md#review-a-prediction-status-and-results).

## <a name="task-5---create-a-segment-of-high-purchased-products"></a>Úloha 5 – Vytvorte segment najčastejšie kupovaných produktov

Spustením produkčného modelu sa vytvorí nová entita, ktorú môžete vidieť v ponuke **Údaje** > **Entity**.

Nový segment môžete vytvoriť na základe entity vytvorenej modelom.

1. Prejdite na **Segmenty**. Vyberte **Nový** následne **Vytvoriť z** > **Analýza**.

   ![Vytvorenie segmentu s výstupom modelu.](media/segment-intelligence.png)

1. Vyberte koncový bod **OOBProductRecommendationModelPrediction** a definujte segment:

   - Pole: ProductID
   - Operátor: Hodnota
   - Hodnota: Vyberte prvé tri ID produktov

   :::image type="content" source="media/product-recommendation-quick-segment.png" alt-text="Vytvorte segment z výsledkov modelu.":::

Teraz máte segment, ktorý sa dynamicky aktualizuje a ktorý identifikuje zákazníkov, ktorí sú ochotnejší kúpiť si tri najviac odporúčané produkty 

Ďalšie informácie nájdete v téme [Tvorba a správa segmentov](segments.md).


[!INCLUDE [footer-include](includes/footer-banner.md)]
