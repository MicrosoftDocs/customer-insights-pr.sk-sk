---
title: Začíname so súpravou iOS SDK
description: Zistite, ako prispôsobiť a spustiť iOS SDK
author: britl
ms.reviewer: mhart
ms.custom: intro-internal
ms.author: britl
ms.date: 09/15/2021
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 68e4d0555d2fc377fae62ff5db64c032fcebcb04
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 02/16/2022
ms.locfileid: "8226234"
---
# <a name="get-started-with-the-ios-sdk"></a>Začíname používať iOS SDK

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Tento kurz vás prevedie procesom inštrumentácie vašej aplikácie iOS pomocou prehľadov interakcií Dynamics 365 Customer Insights. Udalosti na svojom portáli uvidíte až o päť minút alebo skôr.

## <a name="configuration-options"></a>Možnosti konfigurácie

Nasledujúce možnosti konfigurácie je možné odovzdať súprave SDK prostredníctvom poskytnutého súboru `EIConfig.plist`:

- **ingestionKey**: Kľúč prijatia, ktorý sa používa na odosielanie udalostí do vášho projektu.
- **autocollectAction**: Booleovská hodnota na povolenie alebo zakázanie automatickej inštrumentácie udalosti akcie.
- **autocollectView**: Booleovská hodnota na povolenie alebo zakázanie automatickej inštrumentácie udalosti zobrazenia.
- **endpointUrl**: Adresa URL koncového bodu, do ktorého budú udalosti smerovať.

## <a name="prerequisites"></a>Predpoklady

- Verzia Xcode 9+
- Verzia iOS 8.2+
- Kľúč prijatia (získate ho podľa pokynov uvedených nižšie)

## <a name="integrate-the-sdk-into-your-application"></a>Integrácia súpravy SDK do vašej aplikácie

Proces začnite výberom pracovného priestoru, v ktorom chcete pracovať, výberom mobilnej platformy iOS a stiahnutím súpravy SDK.

- Pomocou prepínača pracovného priestoru na ľavej navigačnej table vyberte svoj pracovný priestor.

- Ak nemáte existujúci pracovný priestor, vyberte možnosť **Nový pracovný priestor** a postupujte podľa pokynov na vytvorenie [nového pracovného priestoru](create-workspace.md).

- Po vytvorení pracovného priestoru prejdite na položku **Správca** > **Pracovný priestor** a potom vyberte možnosť **Návod na inštaláciu**.

## <a name="configure-the-sdk"></a>Konfigurácia súpravy SDK

Po stiahnutí súpravy SDK s ňou môžete pracovať v Xcode, kde môžete povoliť a definovať udalosti. Existujú dva spôsoby, ako na to

### <a name="option-1-using-cocoapods-recommended"></a>Možnosť 1: Použite CocoaPods (odporúča sa)
CocoaPods je správca závislostí projektov Swift a Objective-C Cocoa. Ak ho použijete, uľahčíte si integrovanie súpravy SDK pre prehľady interakcií pre iOS. CocoaPods vám taktiež umožní inovovať na najnovšiu verziu súpravy SDK pre prehľady interakcií. Tu uvádzame postup, ako použiť CocoaPods  na integrovanie súpravy SDK na prehľad interakcií do vášho projektu Xcode. 

1. Inštalácia CocoaPods. 

1. V koreňovom adresári projektu vytvorte nový súbor s názvom Podfile a pridajte doň tieto príkazy.Názov nahraďte YOUR_TARGET_PROJECT_NAME názvom vášho projektu Xcode. 
```objectivec
platform :ios, '9.0'  

 target '${YOUR_TARGET_PROJECT_NAME}' do 

     use_frameworks!   

     pod 'EIObjC.framework.debug' 

     pod 'EIObjC.framework.release' 

 end 
```
Hore uvedená konfigurácia pod obsahuje tak verzie ladenia ako aj cieľového vydania SDK. Vyberte si tú, ktorá sa najviac hodí pre váš projekt.

1. Nainštalujte pod spustením tohto príkazu: `pod install --repo-update `

### <a name="option-2-using-download-link"></a>Možnosť 2: Stiahnite si pomocou odkazu

1. Stiahnite si [prehľady interakcií súpravy iOS SDK](https://download.pi.dynamics.com/sdk/EI-SDKs/ei-ios-sdk.zip) a umiestnite súbor `EIObjC.xcframework` do priečinka `Frameworks`.

1. Ak priečinok `Frameworks` neexistuje, vytvorte ho v priečinku projektu.

## <a name="enable-auto-instrumentation"></a>Povolenie automatickej inštrumentácie
 
Môžete ľahko povoliť automatickú inštrumentáciu bez kódovania. Po spustení projektu sa budú automaticky sledovať udalosti `view` a `action` pomocou nakonfigurovaného kľúča prijatia. 

1. Aktualizujte a zahrňte poskytnutý súbor `EIConfig.plist` do vášho priečinku adresára projektu pre nasledujúce polia:
    - ingestionKey = `"Your-Ingestion-Key"`
    - autocollectView = ÁNO
    - autocollectAction = ÁNO

2. Potom pridajte súbor `EIConfig.plist` do vášho projektu v Xcode. 



Ak chcete zakázať automatickú inštrumentáciu, aktualizujte nasledujúce polia v zahrnutom súbore `EIConfig.plist` do vášho priečinku adresára projektu. 

```objectivec
'autocollectView' = NO (to disable)
'autocollectAction' = NO (to disable)
```


## <a name="implement-custom-events"></a>Implementácia vlastných udalostí

1. Otvorte svoj projekt v Xcode a prejdite na **Všeobecné** nastavenia. 
1. Pridajte súbor `EIObjC.xcframework` do projektu v sekcii „Rámce, knižnice a vložený obsah“.

1. Importujte súbor hlavičky architektúry v AppDelegate.m pomocou nasledujúceho úryvku:

    ```objectivec
    #import <EIObjC/EIObjC.h>
    ```

1. Inicializujte prehľady interakcie súpravy SDK z aplikácie: didFinishLaunchingWithOptions.
1. Skopírujte úryvok XML z **Návodu na inštaláciu**.

    ```objectivec
    NSError *error = [NSError new];
    id<EIIAnalytics> analytics = [EIAnalyticsProvider analyticsForIngestionKey:nil error:&error];
    ```

1. Sledovanie udalosti:

    ```objectivec
    EIEvent *event = [EIEvent new];
    event.name = @"video.log";
    [event setLongValue:320 forKey:@"duration"];
    [event setBoolValue:YES forKey:@"ad_shown"];
    [analytics trackEvent:event];
    ```

## <a name="set-user-details-for-your-event"></a>Nastavenie podrobností používateľa pre udalosť

Súprava SDK umožňuje definovať informácie o používateľovi, ktoré je možné odoslať pri každej udalosti. Informácie o používateľovi môžete špecifikovať tým, že vyvoláte API `setUser:(nonnull EIUser *)user` na SDK.

Uvedenie podrobností o používateľovi na úrovni `Analytics` znamená, že všetky telemetrie budú obsahovať tieto informácie. Ak ich však uvediete na úrovni udalosti tak, že vyvoláte API `setUser:(nonnull EIUser *)user` v objekte EIEvent, tieto informácie bude obsahovať iba konkrétna udalosť.

Trieda údajov `EIUser` obsahuje nasledujúce vlastnosti NSString:

- **localId**: Miestne ID používateľa.
- **authId**: ID autentifikovaného užívateľa.
- **authType**: Typ autentifikácie používaný na získanie autentifikovaného ID užívateľa.
- **meno**: Meno používateľa.
- **e-mail**: Používateľská e-mailová adresa.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
