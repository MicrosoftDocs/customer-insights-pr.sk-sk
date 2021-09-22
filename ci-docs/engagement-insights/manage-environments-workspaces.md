---
title: Správa pracovných priestorov a prostredí
description: Ako vytvárať, premenovávať a mazať pracovné priestory a prostredia.
author: jusali
ms.reviewer: mhart
ms.author: jusali
ms.date: 07/01/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: bf310b1a50ba7baac5d11d5f22ff42003fbba516efd7d165c00b59adc958da2e
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 08/10/2021
ms.locfileid: "7034061"
---
# <a name="manage-environments-and-workspaces"></a>Spravovanie prostrední a pracovných priestorov

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

## <a name="overview"></a>Prehľad

Pracovný priestor je priestor na ukladanie a správu udalostí a správ. Na tomto mieste môžete sledovať aktivitu používateľov v reálnom čase. Pri vytváraní pracovného priestoru vyberiete typ údajov, ktoré sa majú odoslať do pracovného priestoru. V súčasnosti sú podporované webové dáta a mobilné aplikácie.

Prostredie je priestor, v ktorom spravujete svoje pracovné priestory a pripojenia. To, ako používate prostredia, závisí od vašej organizácie a prípadu použitia. Môžete napríklad vytvárať:

-   Jedno prostredie.
-   Samostatné prostredia pre testovanie a výrobu.
-   Samostatné prostredia pre konkrétne tímy alebo oddelenia vo vašej organizácii, ktoré obsahujú relevantné udalosti pre každé publikum.
-   Samostatné prostredia pre rôzne globálne pobočky vašej spoločnosti.
-   Možnosť pripojenia k Customer Insights audience insights

## <a name="choose-an-environment-and-create-a-workspace"></a>Vyberte si prostredie a vytvorte pracovný priestor 

Každý pracovný priestor musí byť v prostredí. Pri vytváraní pracovného priestoru môžete vybrať už existujúce prostredie alebo vytvoriť nové. Potom sa môžete rozhodnúť pridať členov pracovného priestoru a začať zhromažďovať údaje.

**Vytvorenie prvého pracovného priestoru**

1. V prehľadoch interakcie stlačte možnosť **Nový** v prepínači pracovného priestoru. 

   :::image type="content" source="media/New-workspace.png" alt-text="Výber pracovného priestoru stránky Customer Insights.":::

1. Vyberte prostredie zo zoznamu alebo stlačte možnosť **Vytvoriť nové prostredie**.

1. Zadajte názov do položky **Názov pracovného priestoru**. 

1. Vyberte typ prostredia, ktoré chcete vytvoriť, podľa toho, či chcete zisťovať, čo sa deje na webovej lokalite alebo v mobilnej aplikácii. 

1. Môžete pridať členov a priradiť úroveň ich povolení zo zoznamu **Rola**. Potom stlačte možnosť **Dokončiť** na vytvorenie pracovného priestoru alebo **Ďalej** na inštaláciu kódu. 

1. Nainštalujte si úryvok kódu, aby ste začali prijímať údaje, a potom stlačte možnosť **Hotovo**. 

## <a name="manage-a-workspace"></a>Správa pracovného priestoru

V prostredí môžete súčasne udržiavať viac pracovných priestorov. Vaša [rola](user-roles.md) určuje, ako v nich môžete pracovať. 

 - Ak chcete spravovať pracovný priestor, musíte byť správcom prostredia alebo správcom pracovného priestoru.
 - Ako správca pracovného priestoru môžete existujúce pracovné priestory premenovať alebo ich odstrániť. 

### <a name="edit-a-workspace-name"></a>Úprava názvu pracovného priestoru

1. Prejdite na ponuku **Správca** > **Pracovný priestor** a stlačte možnosť **Nastavenia**.

1. Do poľa **Názov pracovného priestoru** zadajte nový názov.

1. Zmeny vykonajte výberom položky **Uložiť**.

### <a name="delete-a-workspace"></a>Odstránenie pracovného priestoru

Odstránením pracovného priestoru sa natrvalo odstráni všetok jeho obsah, údaje, nastavenia a povolenia. Táto akcia sa nedá vrátiť späť.

1. Prejdite na ponuku **Správca** > **Pracovný priestor** a stlačte možnosť **Nastavenia**.

1. Stlačte možnosť **Odstrániť pracovný priestor**. 

1. V dialógovom okne **Odstrániť pracovný priestor** zadajte **POTVRDIŤ ODSTRÁNENIE**. 

1. Ak chcete natrvalo odstrániť pracovný priestor, stlačte možnosť **Odstrániť**.

### <a name="manage-workspace-members"></a>Správa členov pracovného priestoru

1. Prejdite na ponuku **Správca** > **Pracovný priestor** a stlačte možnosť **Členovia**.

1. Stlačte možnosť **Pridať členov**, udeľte prístup a [priraďte roly](user-roles.md). Momentálne je dostupná len **Správca pracovného priestoru**.

1. Ak nastavíte a [pripojenie k Audience Insights](configure-connections.md), môžete stlačiť možnosť **Povoliť prístup k profilovým údajom** a umožniť členovi zobraziť správy založené na [používateľských profiloch](profile-reports.md).

1. Stlačte možnosť **Pridať členov** a pridajte ich do svojho pracovného priestoru.

## <a name="manage-an-environment"></a>Správa prostredia

Ako správca prostredia máte prístup do prostredia z ľavej navigačnej tably. Môžete konfigurovať nastavenia prostredia, ďalších správcov prostredia, pracovných priestorov a [prepojenie na audience insights](configure-connections.md). Vyberte karty, aby ste sa pohybovali medzi rôznymi oblasťami v centre správcu.

:::image type="content" source="media/New-environment.png" alt-text="Centrum spravovania prostredia.":::

### <a name="create-an-environment"></a>Vytvoriť prostredie

1. Vo výbere pracovného priestoru označte položku **+Nový**.

1. Systém vás prevedie k rozbaľovcej ponuke **Prostredie**, kde označte položku **Vytvoriť nové prostredie**. 

1. Poskytnite údaj **Názov prostredia**.

   :::image type="content" source="media/create-environment.png" alt-text="Vstúpte do sprievodcu a zadajte podrobnosti o prostredí.":::

1. Zvoľte položku **Región** a označte **Ďalšie**. 

1. Zadajte názov pracovného priestoru a zvoľte typ pracovného priestoru, ktorý chcete vytvoriť. 

1.  Môžete tiež pridať členov a skopírovať úryvok kódu a dokončiť tak proces vytvárania.

### <a name="rename-an-environment"></a>Premenovanie prostredia

1. Prejdite na ponuku **Správca** > **Prostredie** a stlačte možnosť **Nastavenia**.

1. Aktualizujte **Názov prostredia** a stačte možnosť **Uložiť**, čím použijete svoje zmeny.

### <a name="manage-environment-members"></a>Správa členov prostredia

1. Prejdite na ponuku **Správca** > **Prostredie** a stlačte možnosť **Členovia**.

1. Stlačte možnosť **Pridať členov** na aktualizáciu členov a [priradenie rol](user-roles.md). Momentálne je dostupná len **Správca prostredia**.

1. Ak nastavíte a [pripojenie k Audience Insights](configure-connections.md), môžete stlačiť možnosť **Povoliť prístup k profilovým údajom** a umožniť členovi zobraziť správy založené na [používateľských profiloch](profile-reports.md).

1. Stlačte možnosť **Pridať členov** a pridajte ich do svojho prostredia.

### <a name="delete-an-environment"></a>Odstrániť prostredie

Správcovia prostredí môžu prostredia odstraňovať. Než odstránite prostredie, je potrebné vymazať všetky pracovné priestory pod ním.

1. Prejdite na ponuku **Správca** > **Prostredie** a stlačte možnosť **Nastavenia**.

1. Označte položku  **Odstrániť prostredie**. 

1. V dialógovom okne **Odstrániť pracovný priestor** zadajte **POTVRDIŤ ODSTRÁNENIE**. 

1. Ak chcete natrvalo odstrániť prostredie, označte položku **Odstrániť**.

## <a name="manage-connections"></a>Spravovanie pripojení

Nadviazanie kontaktov so audience insights vám umožní vidieť prehľady v prehľadoch interakcií na základe zjednotených profilov zákazníkov. 

Ďalšie informácie nájdete v téme [Konfigurácia pripojení](configure-connections.md).

## <a name="manage-personal-data"></a>Správa osobných údajov

V záujme ochrany osobných údajov zákazníka môžete vymazať alebo exportovať identifikovateľné údaje koncového používateľa.

Viac informácií nájdete v časti [Odstránenie a export údajov udalosti s obsahom osobných údajov](delete-export-personal-data.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
