---
title: Predikcie hodnoty životnosti zákazníka (CLV) – vzorový sprievodca
description: V tomto vzorovom sprievodcovi si môžete vyskúšať model predikcie hodnoty životnosti zákazníka.
ms.date: 09/15/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: tutorial
author: yashlundia
ms.author: yalundia
manager: shellyha
ms.openlocfilehash: fec43b279326daa17fb179181f5e310c99d48bb7
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 09/30/2022
ms.locfileid: "9609657"
---
# <a name="customer-lifetime-value-clv-prediction-sample-guide"></a>Predikcie hodnoty životnosti zákazníka (CLV) – vzorový sprievodca

Táto príručka vás prevedie úplným príkladom celoživotnej hodnoty zákazníka (CLV) predikcia v Customer Insights pomocou vzorových údajov. Odporúčame vám vyskúšať tento predikcia [v novom prostredí](manage-environments.md).

## <a name="scenario"></a>Scenár

Contoso je spoločnosť, ktorá vyrába vysokokvalitnú kávu a kávovary. Produkty predávajú prostredníctvom svojej webovej stránky Contoso Coffee. Spoločnosť chce porozumieť hodnote (výnosom), ktorú môžu jej zákazníci vygenerovať počas nasledujúcich 12 mesiacov. Znalosť očakávanej hodnoty ich zákazníkov počas nasledujúcich 12 mesiacoch im pomôže nasmerovať ich marketingové úsilie na vysoko hodnotných zákazníkov.

## <a name="prerequisites"></a>Požiadavky

- Minimálne [povolenia prispievateľa](permissions.md).

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

1. **Uložte** zdroj údajov.

### <a name="ingest-online-purchase-data"></a>Prijmite údaje o online nákupe

1. K tomu istému zdroju údajov **eCommerce** pridajte ďalšiu množinu údajov. Znova vyberte konektor **Text/CSV**.

1. Zadajte adresu URL pre údaje **Online nákupy** https://aka.ms/ciadclassonline.

1. Počas upravovania údajov vyberte **Transformovať** a potom **Použite prvý riadok ako hlavičky**.

1. Aktualizujte typ údajov pre stĺpce uvedené nižšie:
   - **PurchasedOn**: Dátum/Čas
   - **TotalPrice**: Mena

1. V **názov** pole na bočnom paneli premenujte zdroj údajov na **eCommerceNákupy**.

1. **Uložte** zdroj údajov.

### <a name="ingest-customer-data-from-loyalty-schema"></a>Príjem údaje o zákazníkoch z vernostnej schémy

1. Vytvorte zdroj údajov s názvom **LoyaltyScheme** a vyberte **Text/CSV** konektor.

1. Zadajte adresu URL pre vernostných zákazníkov https://aka.ms/ciadclasscustomerloyalty.

1. Počas upravovania údajov vyberte **Transformovať** a potom **Použite prvý riadok ako hlavičky**.

1. Aktualizujte typ údajov pre stĺpce uvedené nižšie:
   - **DateOfBirth**: Dátum
   - **RewardsPoints**: Celé číslo
   - **CreatedOn**: Dátum/Čas

1. V **názov** pole na pravej table premenujte zdroj údajov na **loyZákazníci**.

1. **Uložte** zdroj údajov.

### <a name="ingest-customer-data-from-website-reviews"></a>Príjem údajov o zákazníkoch z recenzií na webe

1. Vytvorte zdroj údajov s názvom **webové stránky** a vyberte **Text/CSV** konektor.

1. Zadajte adresu URL pre recenzie webových stránok https://aka.ms/CI-ILT/WebReviews.

1. Počas upravovania údajov vyberte **Transformovať** a potom **Použite prvý riadok ako hlavičky**.

1. Aktualizujte typ údajov pre stĺpce uvedené nižšie:
   - **ReviewRating**: Desatinné číslo
   - **ReviewDate**: Dátum

1. V **názov** pole na pravej table premenujte zdroj údajov na **Recenzie**.

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

1. Pridajte ďalšiu aktivitu a priraďte názvy jej polí k zodpovedajúcim poliam:
   - **Subjekt činnosti** : Recenzie:Webová stránka
   - **Primárny kľúč** : ReviewId
   - **Časová značka** : Dátum revízie
   - **Aktivita udalosti** : Zobrazenie typu aktivity
   - **Ďalšie podrobnosti** : Hodnotenie recenzií
   - **Typ aktivity** : Preskúmanie

1. Spustite aktivitu.

## <a name="task-4---configure-customer-lifetime-value-prediction"></a>Úloha 4 – Konfigurácia predikcie hodnoty životnosti zákazníka

So zjednotenými profilmi zákazníkov a vytvorenou aktivitou spustite celoživotnú hodnotu zákazníka (CLV) predikcia. Podrobné kroky nájdete v časti [Celoživotná hodnota zákazníka predikcia](predict-customer-lifetime-value.md).

1. Ísť do **Inteligencia** > **Predpovede**.

1. Na **Vytvorte** kartu, vyberte **Použite model** na **Celoživotná hodnota zákazníka** dlaždica.

1. Vyberte **Začíname**.

1. Pomenujte model **Predikcia OOB eCommerce CLV** a výstupnú entitu **OOBeCommerceCLVPrediction**.

1. Definujte preferencie modelu:
   - **predikcia časové obdobie** :**12 mesiacov alebo 1 rok** definovať, ako ďaleko do budúcnosti predpovedať CLV.
   - **Aktívni zákazníci** :**Nechajte model vypočítať nákupný interval** čo je časový rámec, v ktorom musí mať zákazník za sebou aspoň jednu transakciu, aby bol považovaný za aktívny.
   - **Zákazník s vysokou hodnotou** : manuálne definujte zákazníkov s vysokou hodnotou ako **najlepších 30 % aktívnych zákazníkov**.

    :::image type="content" source="media/clv-model-preferences.png" alt-text="Krok predvolieb v prostredí so sprievodcom pre model CLV.":::

1. Vyberte **Ďalej**.

1. V kroku **Požadované údaje** vyberte **Pridať údaje** na poskytnutie údajov o histórii transakcií.

    :::image type="content" source="media/clv-model-required.png" alt-text="Pridajte požadované údaje do sprievodcu pre model CLV.":::

1. Vyberte **SalesOrderLine** a entitu eCommercePurchases a vyberte **Ďalšie**. Požadované údaje sa automaticky vyplnia z aktivity. Vyberte **Uložiť** a potom **Ďalšie**.

1. The **Ďalšie údaje (voliteľné)** krok vám umožňuje pridať ďalšie údaje o aktivite zákazníkov, aby ste získali viac informácií o interakciách so zákazníkmi. Pre tento príklad vyberte **Pridajte údaje** a pridajte aktivitu kontroly webu.

1. Vyberte **Ďalej**.

1. V **Aktualizácie údajov** krok, vyberte **Mesačne** pre modelový harmonogram.

1. Vyberte **Ďalej**.

1. Po skontrolovaní všetkých podrobností vyberte možnosť **Uložiť a spustiť**.

## <a name="task-5---review-model-results-and-explanations"></a>Úloha 5 – Skontrolujte výsledky modelu a vysvetlenia

Nechajte model absolvovať školenie a skórovanie údajov. Skontrolujte [Výsledky a vysvetlenia modelu CLV](predict-customer-lifetime-value.md#view-prediction-results).

## <a name="task-6---create-a-segment-of-high-value-customers"></a>Úloha 6 – Vytvorte segment zákazníkov s vysokou hodnotou

Spustením modelu sa vytvorí nová entita, ktorá je uvedená na zozname **Údaje** > **Entity**. Nový segment zákazníkov môžete vytvoriť na základe entity vytvorenej modelom.

1. Na stránke s výsledkami vyberte možnosť **Vytvoriť segment**.

1. Vytvorte pravidlo pomocou **Predpoved OOBeCommerceCLVP** entity a definujte segment:
   - **Lúka** : CLVScore
   - **Operátor** : väčší než
   - **Hodnota** : 1500

1. Vyberte **Uložiť** a **Bežať** segmente.

Teraz máte segment, ktorý identifikuje zákazníkov, u ktorých sa predpokladá, že v nasledujúcich 12 mesiacoch vygenerujú viac ako 1500 $ výnosov. Ak sa prijme viac údajov, tento segment sa dynamicky aktualizuje. Ďalšie informácie nájdete v téme [Tvorba a správa segmentov](segments.md).

> [!TIP]
> Môžete tiež vytvoriť segment pre model predikcia z **Segmenty** stránku výberom **Nový** a výberom **Vytvoriť z** > **Inteligencia**. Ďalšie informácie nájdete v časti [Vytvorte nový segment s rýchlymi segmentmi](segment-quick.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
