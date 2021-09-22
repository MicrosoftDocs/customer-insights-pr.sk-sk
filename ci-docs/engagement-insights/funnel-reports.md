---
title: Lievikové zostavy
description: Ako pomocou lievikových zostáv porozumieť tomu, ako sa cieľová skupina rozhoduje.
ms.reviewer: mhart
ms.author: kamacdon
author: kamacdon
ms.date: 06/23/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 7c6b7b7285556f8a531ce9e29f0d1de162562be6fb43dd826a65fd9e00d87b30
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 08/10/2021
ms.locfileid: "7032274"
---
# <a name="create-and-manage-funnel-reports"></a>Vytváranie a správa lievikových zostáv

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Lieviková zostava zhromažďuje informácie o krokoch, ktoré sa uskutočnia v rámci činnosti zákazníka prostredníctvom vašej webovej lokality alebo mobilnej aplikácie. Pomáha vám pochopiť, ako cieľová skupina postupuje v procese, a identifikuje miesta odchodu. Môžete napríklad použiť lievikovú zostavu na identifikáciu ciest, ktorými sa zákazníci uberajú, skôr ako uskutočnia nákup. Lieviková zostava poskytuje údaje, ktoré slúžia na informovanie rozhodnutí a identifikáciu oblastí optimalizácie a zlepšenia procesov.

## <a name="create-a-funnel-report"></a>Vytvorenie lievikovej zostavy

Ak chcete vytvoriť lievikovú zostavu, zadajte kroky, ktoré chcete zahrnúť, a aktivitu pre jednotlivé kroky. Činnosť je [udalosť](glossary.md), ktorá predstavuje správanie používateľa. V lievikovej zostave sa zobrazuje počet používateľov, ktorí dokončili každý definovaný krok. 

1. Prejdite na možnosť **Lieviky** a stlačte možnosť **+ Nový lievik** na spustenie lievikovej zostavy.

1. V časti **Editor lievika** v ponuke **Kroky** stlačte možnosť **+ Pridať krok.** 

1. Zadajte názov do poľa **Názov kroku**.

   :::image type="content" source="media/new-funnel-report.png" alt-text="Nová lieviková zostava.":::

1. Stlačte možnosť **Aktivita**. Aktivita sa zaznamená, keď používateľ zobrazí stránku (aktivita **Zobrazenie**) alebo interaguje s obsahom (aktivita **Akcia**).

1. Použite možnosť **Kritériá kroku** na určenie dimenzie aktivity. [Dimenzie](dimensions.md) sú atribúty, ktoré môžu popisovať, filtrovať alebo zoskupovať údaje.

1. Voliteľne môžete nakonfigurovať kroky lievika s viacerými podmienkami. Vyberte **Pridať podmienku** a zadajte viac dimenzií v kroku. Ďalšie kritériá musia používať rovnaký typ aktivity. Môžete si vybrať, či je s operátorom AND alebo OR spojených viac podmienok.

   :::image type="content" source="media/funnel-add-condition.png" alt-text="Editor lievika zobrazujúci konfiguráciu krokov s krokmi s viacerými podmienkami.":::

1. Stláčajte možnosť **Pridať krok**, kým nevykonáte všetky požadované kroky v prehľade.

1. Stlačte možnosť **Uložiť**, pomenujte zostavu a znova stlačte možnosť **Uložiť**. 

### <a name="example-fourth-coffee-company-funnel-report"></a>Príklad: Lieviková zostava spoločnosti Fourth Coffee

Nasledujúci scenár demonštruje jeden spôsob použitia lievikovej zostavy. Analytik spoločnosti Fourth Coffee chce pochopiť vplyv nedávnej propagácie na ceny predplatného. Analytik vytvorí lievikovú zostavu na identifikáciu aktivity zákazníka. Začína sa to, keď zákazníci prídu na domovskú stránku spoločnosti, kým nevyužijú propagačný kód predplatného. Analytik vytvorí lievikovú zostavu s nasledujúcimi krokmi:

Krok 1: Zákazníci, ktorí sa dostanú na domovskú stránku   
Krok 2: Zákazníci, ktorí uskutočnia nákup   
Krok 3: Zákazníci, ktorí používajú propagačný kód na získanie zľavy z predplatného   
Krok 4: Registrácia predplatného   

:::image type="content" source="media/funnel-report-example.png" alt-text="príklad lievikovej zostavy.":::
  
Tento lievik vám umožňuje zistiť počet používateľov, ktorí použili propagačný kód po jednorazovom nákupe na zaregistrovanie sa do predplatného.

### <a name="configure-advanced-settings"></a>Konfigurácia rozšírených nastavení 

Lievikové zostavy vám umožňujú definovať obmedzenie času potrebného na dokončenie lievika. Môžete napríklad nastaviť čas na dokončenie lievika na štyri dni. Toto nastavenie bude počítať iba úspešné registrácie predplatného, ku ktorým došlo do štyroch dní po tom, čo používateľ navštívil domovskú stránku.

1. Prejdite do ponuky **Lieviky** a otvorte **Knižnica lievikov**.

1. Výberom názvu zostavy ju otvorte. 

1. Na table **Editor lievika** vyberte **Pokročilé nastavenia**. 

1. Nastavte obmedzenie času na dokončenia lievika na **Zap.**

   :::image type="content" source="media/funnel-limit-time.png" alt-text="Editor lievika zobrazujúci pokročilé nastavenie a možnosti na obmedzenie času na dokončenie lievika.":::

1. Čas, v ktorom musí byť lievik dokončený, si vyberiete z rozbaľovacieho zoznamu **Nastaviť limit na**.

1. Zmeny vykonajte výberom položky **Uložiť**.


## <a name="cross-channel-funnel-reports"></a>Lievikové zostavy naprieč kanálmi 

Prehľady interakcií môžu tiež zhromažďovať údaje o správaní zákazníkov vo vašej mobilnej aplikácii. Po vybavení vašej mobilnej aplikácie prehľadmi interakcií [Android SDK](get-started-android.md) alebo [iOS SDK](get-started-ios.md) môžete vytvárať lievikové zostavy naprieč kanálmi. 

### <a name="create-a-cross-channel-funnel-report"></a>Vytvorenie lievikovej zostavy naprieč kanálmi 

1. Postupujte podľa pokynov na [vytvorenie lievikovej zostavy](#create-a-funnel-report).    

1. Ak chcete sledovať, ako zákazníci interagujú s vašou značkou na vašej webovej lokalite a v mobilnej aplikácii alebo na viacerých webových lokalitách, pomocou prepínača pracovného priestoru vytvorte kroky lievika s údajmi z iných pracovných priestorov. V sekcii **Editor lievika** po položkou **Kroky** vyberte, z ktorého pracovného priestoru majú pochádzať údaje pre váš krok lievika.

## <a name="manage-funnel-reports"></a>Správa lievikových zostáv

Môžete skontrolovať prehľady zúžení a analyzovať údaje, sledovať výkon a zhromažďovať štatistiky.

> [!NOTE]
> - Správy zúženia prehľadu Štatistiky zapojenia v súčasnosti podporujú scenáre, v ktorých sú všetci používatelia v zúžení anonymní alebo sú všetci používatelia autentifikovaní. 
> - Historické údaje v lievikových zostavách sú k dispozícii za posledných 30 dní.

### <a name="view-funnel-reports"></a>Zobrazenie lievikových zostáv

1. Prejdite do ponuky **Lieviky** a otvorte **Knižnica lievikov**.
1. Výberom názvu zostavy ju otvorte.    

### <a name="see-the-data-collected-for-a-report"></a>Pozrite si údaje zhromaždené pre zostavu   

Zobrazenie informácií o fáze

- Ukážte na krok v zostave.

:::image type="content" source="media/funnel-step-data.png" alt-text="údaje o lieviku.":::

### <a name="change-the-date-range-for-the-funnel-report"></a>Zmeňte rozsah dátumov pre lievikovú zostavu

1. Prejdite do ponuky **Lieviky** a otvorte **Knižnica lievikov**.

1. Výberom názvu zostavy ju otvorte.

1. Otvorte **časový rozsah** a vyberte nové časové obdobie zo zoznamu alebo **Pevný rozsah dátumov** na určenie rozsahu dátumov.

## <a name="edit-or-delete-funnel-reports"></a>Úpravy alebo odstránenie lievikových zostáv

Môžete zmeniť názov lievikovej zostavy, odstrániť ju alebo upraviť kroky v prehľade.

### <a name="rename-or-delete-a-funnel-report"></a>Premenujte alebo odstráňte lievikovú zostavu

1. Prejdite do ponuky **Lieviky** a otvorte **Knižnica lievikov**. 

1. Vyberte **Viac** vedľa prehľadu, ktorý chcete zmeniť, a stlačte možnosť **Upraviť názov** alebo **Odstrániť**.

### <a name="edit-a-funnel-step"></a>Úprava kroku lievika  

1. Prejdite do ponuky **Lieviky** a otvorte **Knižnica lievikov**. 

1. Výberom názvu zostavy ju otvorte.

1. Vyberie krok, ktorý chcete upravovať.

1. Vyberte **Upraviť**.

1. V **Editor lievika** aktualizujte informácie, ktoré chcete zmeniť.  

1. Vyberte položku **Uložiť**.

### <a name="reorder-a-funnel-step"></a>Zmena poradia lievikových krokov

1. Prejdite do ponuky **Lieviky** a otvorte **Knižnica lievikov**. 

1. Výberom názvu zostavy ju otvorte.

1. Vyberie krok, ktorý chcete preskupiť.

1. Stlačte možnosť **Presunúť** a potom možnosťami **Hore**, **Dole**, **Na vrch** alebo **Na spodok** presuňte krok.

### <a name="delete-a-funnel-step"></a>Odstránenie lievikového kroku

1. Prejdite do ponuky **Lieviky** a otvorte **Knižnica lievikov**. 

1. Výberom názvu zostavy ju otvorte.

1. Zvoľte krok, ktorý si želáte odstrániť, a potom stlačte možnosť **Odstrániť**.

