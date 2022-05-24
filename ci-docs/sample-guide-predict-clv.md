---
title: Predikcie hodnoty životnosti zákazníka – vzorový sprievodca
description: V tomto vzorovom sprievodcovi si môžete vyskúšať model predikcie hodnoty životnosti zákazníka.
ms.date: 03/31/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: tutorial
author: yashlundia
ms.author: yalundia
manager: shellyha
ms.openlocfilehash: 351946c734f5a1054eb3769b2d9cced3bed48e15
ms.sourcegitcommit: 6a5f4312a2bb808c40830863f26620daf65b921d
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 05/11/2022
ms.locfileid: "8740830"
---
# <a name="customer-lifetime-value-clv-prediction-sample-guide"></a>Predikcie hodnoty životnosti zákazníka (CLV) – vzorový sprievodca

Táto príručka vám podrobne vysvetlí príklad predikcie hodnoty životnosti zákazníka (CLV) v nástroji Customer Insights pomocou vzorových údajov.

## <a name="scenario"></a>Scenár

Contoso je spoločnosť, ktorá vyrába vysokokvalitnú kávu a kávovary. Produkty predávajú prostredníctvom svojej webovej stránky Contoso Coffee. Spoločnosť chce porozumieť hodnote (výnosom), ktorú môžu jej zákazníci vygenerovať počas nasledujúcich 12 mesiacov. Znalosť očakávanej hodnoty ich zákazníkov počas nasledujúcich 12 mesiacoch im pomôže nasmerovať ich marketingové úsilie na vysoko hodnotných zákazníkov.

## <a name="prerequisites"></a>Požiadavky

- Minimálne [povolenia prispievateľa](permissions.md) v Customer Insights.
- Odporúčame vám vykonať nasledujúce kroky [v novom prostredí](manage-environments.md).

## <a name="task-1---ingest-data"></a>Úloha 1 – Príjem údajov

Prečítajte si články [o prijímaní údajov](data-sources.md) a [importovanie zdrojov údajov pomocou Power Query konektory](connect-power-query.md). Nasledujúce informácie predpokladajú, že ste sa oboznámili s prijímaním údajov vo všeobecnosti.

### <a name="ingest-customer-data-from-ecommerce-platform"></a>Príjem údajov o zákazníkoch z platformy eCommerce

1. Vytvorte zdroj údajov s názvom **eCommerce**, vyberte možnosť importu a vyberte konektor **Text/CSV**.

1. Zadajte adresu URL kontaktov pre eCommerce [https://aka.ms/ciadclasscontacts](https://aka.ms/ciadclasscontacts).

1. Počas úpravy údajov vyberte **Transformovať** a potom **Použiť prvý riadok ako hlavičky**.

1. Aktualizujte typ údajov pre stĺpce uvedené nižšie:
   - **DateOfBirth**: Dátum
   - **CreatedOn**: Dátum/Čas/Pásmo

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Transformácia dátumu narodenia na dátum.":::

1. V poli „Názov“ na pravej table premenujte svoj zdroj údajov z **Dotaz** na **eCommerceContacts**

1. **Uložte** zdroj údajov.

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

### <a name="ingest-customer-data-from-website-reviews"></a>Príjem údajov o zákazníkoch z recenzií na webe

1. Vytvorte zdroj údajov s názvom **Website**, vyberte možnosť importu a vyberte konektor **Text/CSV**.

1. Zadajte adresu URL kontaktov pre eCommerce https://aka.ms/CI-ILT/WebReviews.

1. Počas úpravy údajov vyberte **Transformovať** a potom **Použiť prvý riadok ako hlavičky**.

1. Aktualizujte typ údajov pre stĺpce uvedené nižšie:

   - **ReviewRating**: Desatinné číslo
   - **ReviewDate**: Dátum

1. V poli „Názov“ na pravej table premenujte svoj zdroj údajov z **Dotaz** na **Recenzie**.

1. **Uložte** zdroj údajov.

## <a name="task-2---data-unification"></a>Úloha 2 – Zjednotenie údajov

[!INCLUDE [sample-guide-unification](includes/sample-guide-unification.md)]

## <a name="task-3---configure-customer-lifetime-value-prediction"></a>Úloha 3 – Konfigurácia predikcie hodnoty životnosti zákazníka

Po zavedených zjednotených profiloch zákazníkov môžeme teraz spustiť predikciu hodnoty životnosti zákazníka. Podrobné kroky nájdete v časti [Celoživotná hodnota zákazníka predikcia](predict-customer-lifetime-value.md).

1. Prejdite na **Analýza**  > **Predikcie** a vyberte **Model hodnoty životnosti zákazníka**.

1. Prejdite si informácie na bočnom paneli a vyberte **Začíname**.

1. Pomenujte model **Predikcia OOB eCommerce CLV** a výstupnú entitu **OOBeCommerceCLVPrediction**.

1. Definujte predvoľby modelu pre model CLV:
   - **Časové obdobie predikcie**: **12 mesiacov alebo 1 rok**. Toto nastavenie definuje, ako ďaleko do budúcnosti sa má predikovať hodnota životnosti zákazníka.
   - **Aktívni zákazníci**: Zadajte, čo pre vašu firmu znamenajú aktívni zákazníci. Nastavte historický časový rámec, v ktorom zákazník musel mať minimálne jednu transakciu, aby mohol byť považovaný za aktívneho. Model bude predpovedať CLV iba pre aktívnych zákazníkov. Vyberte si medzi tým, či chcete nechať model vypočítať časové obdobie na základe historických údajov o transakciách, alebo poskytnúť konkrétny časový rámec. V tomto vzorovom sprievodcovi **necháme model vypočítať interval nákupu**, čo je predvolená možnosť.
   - **Zákazníci s vysokou hodnotou**: Definujte zákazníkov s vysokou hodnotou ako percentil najlepšie platiacich zákazníkov. Model používa tento vstup na poskytnutie výsledkov, ktoré zodpovedajú vašej obchodnej definícii zákazníkov s vysokou hodnotou. Môžete sa rozhodnúť nechať model definovať zákazníkov s vysokou hodnotou. Používa heuristické pravidlo, ktoré odvodzuje percentil. Môžete tiež definovať zákazníkov s vysokou hodnotou ako percentil najlepšie platiacich budúcich zákazníkov. V tomto vzorovom sprievodcovi manuálne definujeme zákazníkov s vysokou hodnotou ako **najlepších 30 % aktívne platiacich zákazníkov** a vyberieme **Ďalej**.

    :::image type="content" source="media/clv-model-preferences.png" alt-text="Krok predvolieb v prostredí so sprievodcom pre model CLV.":::

1. V kroku **Požadované údaje** vyberte **Pridať údaje** na poskytnutie údajov o histórii transakcií.

1. Pridajte entitu **eCommercePurchases: eCommerce** a vykonajte mapovanie atribútov požadovaných modelom:
   - ID transakcie: eCommerce.eCommercePurchases.PurchaseId
   - Dátum transakcie: eCommerce.eCommercePurchases.PurchasedOn
   - Suma transakcie: eCommerce.eCommercePurchases.TotalPrice
   - ID produktu: eCommerce.eCommercePurchases.ProductId

1. Vyberte **Ďalej**.

1. Nastavte vzťah medzi entitou **eCommercePurchases : eCommerce** a **eCommerceContacts : eCommerce**.

1. Krok **Dodatočné údaje (voliteľné)** umožňuje pridať viac údajov o aktivite zákazníka. Tieto údaje môžu pomôcť získať viac prehľadov o interakciách zákazníkov s vašou firmou, čo môže prispieť k CLV. Pridaním kľúčových interakcií so zákazníkmi, ako sú webové denníky, denníky služieb pre zákazníkov alebo história programov odmien môžu zvýšiť presnosť predikcií. Vyberte **Pridať údaje** na zahrnutie ďalších údajov o činnosti zákazníkov.

1. Pridajte entitu aktivity zákazníka a vykonajte mapovanie jej názvov polí na príslušné polia požadované modelom:
   - Entita aktivity zákazníka: Recenzie: Webová lokalita
   - Primárny kľúč: Website.Reviews.ReviewId
   - Časová pečiatka: Website.Reviews.ReviewDate
   - Udalosť (názov aktivity): Website.Reviews.ActivityTypeDisplay
   - Podrobnosti (suma alebo hodnota): Website.Reviews.ReviewRating

1. Vyberte **Ďalej** a nakonfigurujte aktivitu a vzťah medzi údajmi o transakciách a údajmi o zákazníkoch:  
   - Typ aktivity: Vybrať existujúcu
   - Označenie aktivity: Recenzia
   - Zodpovedajúce označenie: Website.Reviews.UserId
   - Entita zákazníka: eCommerceKontakty:eCommerce
   - Vzťah: WebsiteReviews

1. Vyberte **Ďalej** na nastavenie plánu modelu.

   Keď sú prijaté nové údaje, musí model pravidelne trénovať, aby sa naučil nové vzorce. Pre tento príklad vyberte **Mesačne**.

1. Po skontrolovaní všetkých podrobností vyberte možnosť **Uložiť a spustiť**.

## <a name="task-4---review-model-results-and-explanations"></a>Úloha 4 – Skontrolujte výsledky modelu a vysvetlenia

Nechajte model absolvovať školenie a skórovanie údajov. Ďalej si môžete pozrieť výsledky modelu CLV a vysvetlenia. Viac informácií nájdete v článku [Kontrola stavu predikcie a výsledkov](predict-customer-lifetime-value.md#review-prediction-status-and-results).

## <a name="task-5---create-a-segment-of-high-value-customers"></a>Úloha 5 – Vytvorte segment zákazníkov s vysokou hodnotou

Spustením modelu sa vytvorí nová entita, ktorá je uvedená na zozname **Údaje** > **Entity**. Nový segment zákazníkov môžete vytvoriť na základe entity vytvorenej modelom.

1. Prejdite na **Segmenty**. 

1. Vyberte **Nový** následne **Vytvoriť z** > **Analýza**.

   ![Vytvorenie segmentu s výstupom modelu.](media/segment-intelligence.png)

1. Vyberte entitu **OOBeCommerceCLVPrediction** a definujte segment:
  - Pole: CLVScore
  - Operátor: je väčšie ako
  - Hodnota: 1500

1. Vyberte **Recenzia** a **Uložte** segment.

Teraz máte segment, ktorý identifikuje zákazníkov, u ktorých sa predpokladá, že v nasledujúcich 12 mesiacoch vygenerujú viac ako 1500 $ výnosov. Ak sa prijme viac údajov, tento segment sa dynamicky aktualizuje.

Ďalšie informácie nájdete v téme [Tvorba a správa segmentov](segments.md).
