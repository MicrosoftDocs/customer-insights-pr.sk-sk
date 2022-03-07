---
title: Správa pracovných priestorov a prostredí
description: Ako vytvárať, premenovávať a mazať pracovné priestory a prostredia.
author: jusali
ms.reviewer: mhart
ms.author: jusali
ms.date: 10/01/2021
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: ded9e98f06109b7cdc27f449455b7f58d633722f
ms.sourcegitcommit: 1946d7af0bd2ca216885bec3c5c95009996d9a28
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 02/25/2022
ms.locfileid: "8350656"
---
# <a name="manage-environments-and-workspaces"></a>Spravovanie prostrední a pracovných priestorov

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

## <a name="overview"></a>Prehľad

Táto téma sa zaoberá správou pracovných priestorov a prostredí, keď už boli vytvorené. 

- *Pracovný priestor* je priestor na ukladanie a správu udalostí a zostáv. Na tomto mieste môžete sledovať aktivitu používateľov v reálnom čase. Pri vytváraní pracovného priestoru vyberiete typ údajov, ktoré sa majú odoslať do pracovného priestoru. V súčasnosti sú podporované webové dáta a mobilné aplikácie. Ďalšie informácie nájdete v časti [Vytvorte nový pracovný priestor a pridajte členov](create-workspace.md).

- *Prostredie* je priestor, v ktorom spravujete svoje pracovné priestory a pripojenia. Ďalšie informácie nájdete v téme [Vytvorenie nového prostredia](create-new-environment.md).

## <a name="manage-an-existing-workspace"></a>Spravovanie existujúceho pracovného priestoru

V prostredí môžete súčasne udržiavať viac pracovných priestorov. Vaša [rola](user-roles.md) určuje, ako v nich môžete pracovať. 

 - Ak chcete spravovať pracovný priestor, musíte byť správcom prostredia alebo správcom pracovného priestoru.
 - Ako správca pracovného priestoru môžete existujúce pracovné priestory premenovať alebo ich odstrániť. 

:::image type="content" source="media/workspace-edit.png" alt-text="Centrum správcu pracovného priestoru.":::

### <a name="edit-a-workspace-name"></a>Úprava názvu pracovného priestoru

1. Prejdite na ponuku **Správca** > **Pracovný priestor** a stlačte možnosť **Nastavenia**.

1. Do poľa **Názov pracovného priestoru** zadajte nový názov.

1. Zmeny vykonajte výberom položky **Uložiť**.

### <a name="delete-a-workspace"></a>Odstránenie pracovného priestoru

Odstránením pracovného priestoru natrvalo odstránite všetok jeho obsah, údaje, nastavenia a povolenia. Táto akcia sa nedá vrátiť späť.

1. Prejdite na ponuku **Správca** > **Pracovný priestor** a stlačte možnosť **Nastavenia**.

1. Stlačte možnosť **Odstrániť pracovný priestor**. 

1. V dialógovom okne **Odstrániť pracovný priestor** zadajte **POTVRDIŤ VYMAZANIE** veľkými písmenami. 

1. Ak chcete natrvalo odstrániť pracovný priestor, stlačte možnosť **Odstrániť**.

### <a name="manage-workspace-members"></a>Správa členov pracovného priestoru

1. Prejdite na ponuku **Správca** > **Pracovný priestor** a stlačte možnosť **Členovia**.

1. Stlačte možnosť **Pridať členov**, udeľte prístup a [priraďte roly](user-roles.md). Momentálne je dostupná len **Správca pracovného priestoru**.

1. Stlačte možnosť **Pridať členov** a pridajte ich do svojho pracovného priestoru.

## <a name="manage-an-existing-environment"></a>Spravovanie existujúceho prostredia

Ako správca prostredia máte prístup do prostredia z ľavej navigačnej tably. Je možné nakonfigurovať nastavenia prostredia, iných správcov prostredia a pracovné priestory. Vyberte karty, aby ste sa pohybovali medzi rôznymi oblasťami v centre správcu.

:::image type="content" source="media/environment-edit.png" alt-text="Centrum spravovania prostredia.":::

### <a name="edit-an-environment-name"></a>Upravte názov prostredia

1. Prejdite na ponuku **Správca** > **Prostredie** a stlačte možnosť **Nastavenia**.

1. Aktualizujte **Názov prostredia** a stačte možnosť **Uložiť**, čím použijete svoje zmeny.

### <a name="delete-an-environment"></a>Odstrániť prostredie

Správcovia prostredí môžu prostredia odstraňovať. Než odstránite prostredie, je potrebné vymazať všetky pracovné priestory pod ním.

1. Prejdite na ponuku **Správca** > **Prostredie** a stlačte možnosť **Nastavenia**.

1. Označte položku  **Odstrániť prostredie**. 

1. V dialógovom okne **Odstrániť pracovný priestor** zadajte **POTVRDIŤ VYMAZANIE** veľkými písmenami. 

1. Ak chcete natrvalo odstrániť prostredie, označte položku **Odstrániť**.

### <a name="manage-environment-members"></a>Správa členov prostredia

1. Prejdite na ponuku **Správca** > **Prostredie** a stlačte možnosť **Členovia**.

1. Stlačte možnosť **Pridať členov** na aktualizáciu členov a [priradenie rol](user-roles.md). Momentálne je dostupná len **Správca prostredia**.

1. Stlačte možnosť **Pridať členov** a pridajte ich do svojho prostredia.

## <a name="manage-connections"></a>Spravovanie pripojení

Nadviazanie kontaktov so audience insights vám umožní vidieť prehľady v prehľadoch interakcií na základe zjednotených profilov zákazníkov. 

Ďalšie informácie nájdete v časti [Vytvorte prepojenie medzi prehľadmi cieľových skupín a prehľadmi interakcií](integrate-audience-insights-engagement-insights.md).

## <a name="manage-personal-data"></a>Správa osobných údajov

V záujme ochrany osobných údajov zákazníka môžete vymazať alebo exportovať identifikovateľné údaje koncového používateľa.

Viac informácií nájdete v časti [Odstránenie a export údajov udalosti s obsahom osobných údajov](../dsr-rights-requests.md).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
