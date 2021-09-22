---
title: Ukážka súpravy Android SDK
description: Ukážkový projekt, kde sa dozviete viac o súprave Android SDK
author: britl
ms.reviewer: m-hartmann
ms.author: britl
ms.date: 06/23/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: ba51961bc7f9555d7dba5b6a21c8636011438d75cba87bc132b896841c467a33
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 08/10/2021
ms.locfileid: "7035845"
---
# <a name="run-the-android-sdk-sample"></a>Spustenie ukážky súpravy Android SDK

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Tento ukážkový projekt pre Android vám pomôže pochopiť, ako SDK funguje v aplikácii. Nemusíte si zapisovať žiadne kódy. Stačí pridať kľúč prijatia a okamžite môžete vo vašom pracovnom priestore vidieť udalosti.

## <a name="prerequisites"></a>Predpoklady

- [Android Studio](https://developer.android.com/studio)
- [Kľúč prijatia](get-started-android.md)

## <a name="download-the-android-sdk-sample"></a>Stiahnutie ukážky súpravy Android SDK

1. [Stiahnite si ukážku prehľadov interakcií súpravy Android SDK](https://download.pi.dynamics.com/sdk/EI-SDKs/ei-android-sample.zip).
1. Rozbaľte skomprimovaný súbor `ei-android-sample.zip`.
1. Otvorte rozbalený priečinok v Android Studio.
1. V súbore `AndroidManifest.xml` nahraďte reťazec `"Your-Ingestion-Key"` kľúčom prijatia vášho pracovného priestoru z prehľadov interakcií v sekcii **Správca** > **Pracovný priestor** > **Návod na inštaláciu**. 

   > [!NOTE]
   > Nemusíte vymeniť sekciu `${applicationId}`. Vyplní sa automaticky.

   ```xml
   <application>
   ...
       <provider
           android:authorities="${applicationId}.com.microsoft.engagementinsights.eiandroidsdk.AnalyticsContentProvider"
           android:name="microsoft.dynamics.engagementinsights.eiandroidsdk.AnalyticsContentProvider" />
       <meta-data
           android:name="com.microsoft.engagementinsights.ingestionKey"
           android:value="Your-Ingestion-Key" />
       <meta-data
           android:name="com.microsoft.engagementinsights.autoCapture"
           android:value="true" />
   ...
   </application>
   ```

1. Ak chcete spustiť ukážkový projekt, vyberte tlačidlo **Spustiť**.
1. Zobrazte si udalosti vo svojom pracovnom priestore.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
