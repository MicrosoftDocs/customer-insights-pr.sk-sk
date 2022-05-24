---
title: Predikcia odporúčania produktov – vzorový sprievodca
description: V tomto vzorovom sprievodcovi môžete vyskúšať vopred pripravený model predikcie odporúčaní produktov.
ms.date: 05/16/2022
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
ms.openlocfilehash: cc72cce15fa0c9e92dbf202c803e99514c9ce2b1
ms.sourcegitcommit: 82f417cfb0a16600e9f552d7a21d598cc8f5a267
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 05/16/2022
ms.locfileid: "8762705"
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

1. Zadajte adresu URL kontaktov elektronického obchodu: [https://aka.ms/ciadclasscontacts](https://aka.ms/ciadclasscontacts).

1. Počas úpravy údajov vyberte **Transformovať** a potom **Použiť prvý riadok ako hlavičky**.

1. Aktualizujte typ údajov pre stĺpce uvedené nižšie:
   - **DateOfBirth**: Dátum
   - **CreatedOn**: Dátum/Čas/Pásmo

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Transformácia dátumu narodenia na dátum.":::

1. V poli „Názov“ na pravej table premenujte svoj zdroj údajov z **Dotaz** na **eCommerceContacts**

1. **Uložte** zdroj údajov.

### <a name="ingest-online-purchase-data"></a>Prijmite údaje o online nákupe

1. K tomu istému zdroju údajov **eCommerce** pridajte ďalšiu množinu údajov. Znova vyberte konektor **Text/CSV**.

1. Zadajte adresu URL pre **Online nákupy** údaje [https://aka.ms/ciadclassonline](https://aka.ms/ciadclassonline).

1. Počas úpravy údajov vyberte **Transformovať** a potom **Použiť prvý riadok ako hlavičky**.

1. Aktualizujte typ údajov pre stĺpce uvedené nižšie:
   - **PurchasedOn**: Dátum/Čas
   - **TotalPrice**: Mena

1. V poli **Názov** na bočnej table premenujte svoj zdroj údajov z **Dotaz** na **eCommercePurchases**.

1. **Uložte** zdroj údajov.

### <a name="ingest-customer-data-from-loyalty-schema"></a>Príjem údaje o zákazníkoch z vernostnej schémy

1. Vytvorte zdroj údajov s názvom **LoyaltyScheme**, vyberte možnosť importu a vyberte konektor **Text/CSV**.

1. Zadajte adresu URL kontaktov elektronického obchodu [https://aka.ms/ciadclasscustomerloyalty](https://aka.ms/ciadclasscustomerloyalty).

1. Počas úpravy údajov vyberte **Transformovať** a potom **Použiť prvý riadok ako hlavičky**.

1. Aktualizujte typ údajov pre stĺpce uvedené nižšie:
   - **DateOfBirth**: Dátum
   - **RewardsPoints**: Celé číslo
   - **CreatedOn**: Dátum/Čas

1. V poli **Názov** na pravej table premenujte svoj zdroj údajov z **Dotaz** na **loyCustomers**.

1. **Uložte** zdroj údajov.

## <a name="task-2---data-unification"></a>Úloha 2 – Zjednotenie údajov

[!INCLUDE [sample-guide-unification](includes/sample-guide-unification.md)]

## <a name="task-3---configure-product-recommendation-prediction"></a>Úloha 3 – Konfigurácia predikcie odporúčania produktu

So zjednotenými profilmi zákazníkov teraz môžeme spustiť odporúčanie produktu predikcia.

1. Prejdite na **Analýza** > **Predikcia** vyberte **Odporúčanie produktu**.

1. Vyberte **Začíname**.

1. Pomenujte model **Predikcia modelu odporúčania produktu OOB** a výstupnú entitu **OOBProductRecommendationModelPrediction**.

1. Definujte tri podmienky pre model:

   - **Počet produktov**: Nastavte túto hodnotu na **5**. Toto nastavenie definuje, koľko produktov chcete odporučiť zákazníkom.

   - **Očakávané opakované nákupy**: Vyberte **Áno** na označenie, že chcete zahrnúť produkty do odporúčania, ktoré si vaši zákazníci predtým kúpili.

   - **Dĺžka spätného zobrazenia:** Vyberte minimálne **365 dní**. Toto nastavenie definuje, ako ďaleko do minulosti bude model pozerať na aktivitu zákazníka, aby ju použil ako vstup jeho odporúčania.

   :::image type="content" source="media/product-recommendation-model-preferences.png" alt-text="Predvoľby modelu odporúčaní produktov.":::

1. V **Pridajte požadované údaje** krok, vyberte **Pridajte údaje**.

1. V **Pridajte údaje** panel, vyberte **SalesOrderLine** ako subjekt histórie nákupov. V tomto bode pravdepodobne ešte nie je nakonfigurovaný. Otvorte odkaz na table a vytvorte aktivitu podľa nasledujúcich krokov:
   1. Zadajte **Názov aktivity** a vyberte si *Elektronický obchod: Elektronický obchod* ako **Subjekt činnosti**. The **Primárny kľúč** je *Id nákupu*.
   1. Definujte a pomenujte vzťah k *eCommerceContacts:Entita elektronického obchodu* a vyberte si **ContactId** ako cudzí kľúč.
   1. Pre zjednotenie aktivity nastavte **Aktivita udalosti** ako *Celková cena* a Časová pečiatka do *ZakúpenéOn*. Môžete zadať viac polí, ako je uvedené v [Zákaznícke aktivity](activities.md).
   1. Pre **Typ aktivity**, vyberte si *SalesOrderLine*. Mapujte nasledujúce polia aktivít:
      - ID riadku objednávky: PurchaseId
      - ID objednávky: PurchaseId
      - Údaje o objednávke: ZakúpenéOn
      - ID produktu: ProductId
      - Suma: Celková cena
   1. Pred návratom ku konfigurácii modelu skontrolujte a dokončite aktivitu.

1. Späť v **Vyberte aktivity** krok, vyberte novovytvorenú aktivitu v **Aktivity** oddiele. Vyberte **Ďalšie** a mapovanie atribútov je už vyplnené. Vyberte **Uložiť**.

1. V tejto vzorovej príručke preskočíme **Pridajte informácie o produkte** a **Produktové filtre** nastaviť, pretože nemáme informácie o produkte.

1. V **Aktualizácie údajov** krok, nastavte plán modelu.

   Model sa musí pravidelne trénovať, aby sa naučil nové vzorce, keď dôjde k prijatiu nových údajov. Pre tento príklad vyberte **Mesačne**.

1. Po skontrolovaní všetkých podrobností vyberte možnosť **Uložiť a spustiť**. Prvé spustenie modelu bude trvať niekoľko minút.

## <a name="task-4---review-model-results-and-explanations"></a>Úloha 4 – Skontrolujte výsledky modelu a vysvetlenia

Nechajte model absolvovať školenie a skórovanie údajov. Teraz si môžete skontrolovať vysvetlenie modelu odporúčaní produktov. Viac informácií nájdete v článku [Kontrola stavu predikcie a výsledkov](predict-transactional-churn.md#review-a-prediction-status-and-results).

## <a name="task-5---create-a-segment-of-high-purchased-products"></a>Úloha 5 – Vytvorte segment najčastejšie kupovaných produktov

Spustením produkčného modelu sa vytvorí nová entita, ktorú môžete vidieť v ponuke **Údaje** > **Entity**.

Nový segment môžete vytvoriť na základe entity vytvorenej modelom.

1. Prejdite na **Segmenty**. Vyberte **Nový** a vyberte si **Tvorte z inteligencie**.

   ![Vytvorenie segmentu s výstupom modelu.](media/segment-intelligence.png)

1. Vyberte koncový bod **OOBProductRecommendationModelPrediction** a definujte segment:

   - Pole: ProductID
   - Hodnota: Vyberte prvé tri ID produktov

   :::image type="content" source="media/product-recommendation-quick-segment.png" alt-text="Vytvorte segment z výsledkov modelu.":::

Teraz máte segment, ktorý sa dynamicky aktualizuje a ktorý identifikuje zákazníkov, ktorí by mohli mať záujem o kúpu troch najviac odporúčaných produktov.

Ďalšie informácie nájdete v téme [Tvorba a správa segmentov](segments.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
