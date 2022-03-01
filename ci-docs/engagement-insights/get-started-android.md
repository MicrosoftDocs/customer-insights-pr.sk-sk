---
title: Začnite s Android SDK
description: Zistite, ako prispôsobiť a spustiť Android SDK
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 10/19/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: c678c2dafbb77926269b5602bca363c678ec6b3f
ms.sourcegitcommit: ef823f3d7fa28d3a90cfde9409be9465ffa2cf09
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 10/19/2021
ms.locfileid: "7655361"
---
# <a name="get-started-with-the-android-sdk"></a>Začnite s Android SDK

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Tento návod vás prevedie procesom inštrumentovania vašej Android aplikácie pomocou Dynamics 365 Customer Insights súpravy SDK na analýzu interakcií. Udalosti na svojom portáli uvidíte až o päť minút alebo skôr.

## <a name="configuration-options"></a>Možnosti konfigurácie
Nasledujúce možnosti konfigurácie je možné odovzdať súprave SDK:

- **ingestionKey**: Kľúč prijatia, ktorý sa používa na odosielanie udalostí do vášho pracovného priestoru.

## <a name="prerequisites"></a>Predpoklady

- Android Studio

- Minimálna Android úroveň API: 16 (Jelly Bean)

- Kľúč prijatia (získate ho podľa pokynov uvedených nižšie)

## <a name="integrate-the-sdk-into-your-application"></a>Integrácia súpravy SDK do vašej aplikácie
Začnite proces výberom pracovného priestoru, výberom Android mobilnej platformy a stiahnutím Android SDK.

- Pomocou prepínača pracovného priestoru na ľavej navigačnej table vyberte svoj pracovný priestor.

- Ak nemáte existujúci pracovný priestor, vyberte možnosť **Nový pracovný priestor** a postupujte podľa pokynov na vytvorenie [nového pracovného priestoru](create-workspace.md).

- Po vytvorení pracovného priestoru prejdite na položku **Správca** > **Pracovný priestor** a potom vyberte možnosť **Návod na inštaláciu**.

## <a name="configure-the-sdk"></a>Konfigurácia súpravy SDK

Po stiahnutí súpravy SDK s ňou môžete pracovať v Android Studio a povoliť a definovať udalosti. Existujú dva spôsoby, ako na to:
### <a name="option-1-use-jitpack-recommended"></a>Možnosť 1: Použite JitPack (odporúča sa)
1. Do koreňového adresára `build.gradle` pridajte odkladací priestor JitPack:
    ```gradle
    allprojects {
        repositories {
            ...
            maven { url 'https://jitpack.io' }
        }
    }
    ```

1. Pridať závislosť:
    ```gradle
    dependencies {
        implementation 'com.github.microsoft:engagementinsights-sdk-android:v1.0.0'
        api 'com.google.code.gson:gson:2.8.1'
    }
    ```

### <a name="option-2-use-download-link"></a>Možnosť 2: Použite odkaz na stiahnutie
1. Stiahnite si [štatistiky interakcie Android SDK](https://download.pi.dynamics.com/sdk/EI-SDKs/ei-android-sdk.zip) a umiestnite`eiandroidsdk-debug.aar` súbor v`libs` priečinok.

1. Otvorte súbor `build.gradle` na úrovni projektu a pridajte nasledujúce úryvky:
    ```gradle
    dependencies {
        implementation(name: 'eiandroidsdk-debug', ext: 'aar')
        api 'com.google.code.gson:gson:2.8.1'
    }

    repositories {
        flatDir {
            dirs 'libs'
        }
    }
    ```

## <a name="enable-auto-instrumentation"></a>Povolenie automatickej inštrumentácie

1. Pridajte povolenie pre sieť a internet do súboru `AndroidManifest.xml`, ktorý sa nachádza v priečinku `manifests` .
    ```xml
    <manifest>
        ...
        <uses-permission android:name="android.permission.INTERNET" />
        <uses-permission android:name="android.permission.ACCESS_NETWORK_STATE" />
    ```

1. Nastavte konfiguráciu prehľadov interakcií súpravy SDK prostredníctvom súboru `AndroidManifest.xml`

1. Skopírujte úryvok XML z **Návodu na inštaláciu**. `Your-Ingestion-Key` by sa mal vyplniť automaticky.

   > [!NOTE]
   > Nemusíte vymeniť sekciu `${applicationId}`. Vyplní sa automaticky.


   ```xml
   <application>
   ...
       <provider
           android:authorities="${applicationId}.com.microsoft.engagementinsights.AnalyticsContentProvider"
           android:name="com.microsoft.engagementinsights.AnalyticsContentProvider" />
       <meta-data
           android:name="com.microsoft.engagementinsights.ingestionKey"
           android:value="Your-Ingestion-Key" />
       <meta-data
           android:name="com.microsoft.engagementinsights.autoCapture"
           android:value="true" />
   ...
   </application>
   ```

1. Povoľte alebo zakážte automatický zber údajov udalostí `View` nastavením vyššie uvedeného poľa `autoCapture` na hodnotu `true` alebo `false`. 

   >[!NOTE]
   >`Action` udalosti je potrebné pridať ručne.

1. (Voliteľné) Medzi ďalšie konfigurácie patrí nastavenie adresy URL zberača koncových bodov. Môžu byť pridané pod metaúdaje kľúča príjmu v `AndroidManifest.xml`.

   ```xml
        <meta-data
            android:name="com.microsoft.engagementinsights.endpointUrl"
            android:value="https://some-endpoint-url.com" />
   ```

## <a name="implement-custom-events"></a>Implementácia vlastných udalostí

Po inicializácii súpravy SDK môžete pracovať s udalosťami a ich vlastnosťami v prostredí `MainActivity`.


Java:
```java
Analytics analytics = new Analytics();
```

Kotlin:
```kotlin
var analytics = Analytics()
```

### <a name="set-property-for-all-events-optional"></a>Nastaviť vlastnosť pre všetky udalosti (voliteľné)

Java:
```java
analytics.setProperty("year", 2021);
```

Kotlin:
```kotlin
analytics.setProperty("year", 2021)
```

Pre vlastnosti kontextovej udalosti sú podporované nasledujúce typy:
- String
- Dátum
- Dvojité
- Long
- Boolean
- UUID

### <a name="track-an-event"></a>Sledovanie udalosti

Java:
```java
Event event = new Event("video");
event.setProperty("duration", 320);
event.setProperty("ad_shown", true);
analytics.trackEvent(event);
```

Kotlin:
```kotlin
var event = Event("video")
event.setProperty("duration", 320)
event.setProperty("ad_shown", true)
analytics.trackEvent(event)
```

## <a name="set-user-details-for-your-event-optional"></a>Nastavenie podrobností používateľa pre udalosť (voliteľné)

Súprava SDK umožňuje definovať informácie o používateľovi, ktoré je možné odoslať pri každej udalosti. Informácie o používateľovi môžete špecifikovať tým, že vyvoláte API `setUser(user: User)` na úrovni `Analytics`.

Java:
```java
User user = new User();
user.setName("testuser");
user.setEmail("abc@xyz.com");
analytics.setUser(user);
```

Kotlin:
```kotlin
var user = User()
user.name = "testuser"
user.email = "abc@xyz.com"
analytics.setUser(user)
```

Trieda údajov `User` obsahuje nasledujúce vlastnosti reťazca:

- **localId**: Miestne ID používateľa.
- **authId**: ID autentifikovaného užívateľa.
- **authType**: Typ autentifikácie, ktorý sa používa na získanie ID autentifikovaného používateľa.
- **meno**: Meno používateľa.
- **e-mail**: Používateľská e-mailová adresa.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
