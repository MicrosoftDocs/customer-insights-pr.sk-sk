---
title: Exportujte údaje z Customer Insights
description: Spravujte exporty do zdieľania údajov.
ms.date: 06/14/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6e7793fa99f8431d9d420529b39e0b5b5dbf6748
ms.sourcegitcommit: 0689e7ed4265855d1f76745d68af390f8f4af8a0
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 06/14/2021
ms.locfileid: "6253059"
---
# <a name="exports-preview-overview"></a>Prehľad exportov (verzia Preview)

Stránka **Exporty** zobrazuje všetky nakonfigurované exporty. Exporty zdieľajú konkrétne údaje s rôznymi aplikáciami. Môžu obsahovať zákaznícke profily alebo entity, schémy a podrobnosti mapovania. Každý export vyžaduje [pripojenie, nastavenie zo strany správcu na správu autentifikácie a prístupu](connections.md).

Prejdite do ponuky **Údaje** > **Exporty** a zobrazte si stránku s exportmi. Všetky používateľské roly majú prístup na zobrazenie nakonfigurovaných exportov. Pomocou vyhľadávacieho poľa na paneli príkazov môžete vyhľadať exporty podľa ich názvu, názvu pripojenia alebo typu pripojenia.

## <a name="set-up-a-new-export"></a>Nastavenie nového exportu

Ak chcete nastaviť alebo upraviť export, musíte mať k dispozícii pripojenia. Pripojenia závisia od vašej [roly používateľa](permissions.md):
- Správcovia majú prístup ku všetkým pripojeniam. Môžu tiež vytvárať nové pripojenia pri nastavovaní exportu.
- Prispievatelia môžu mať prístup ku konkrétnym pripojeniam. Závisia od správcov, ktorí konfigurujú a zdieľajú pripojenia. Zoznam exportov zobrazuje prispievateľov, či môžu upravovať alebo len zobraziť export v stĺpci **Vaše povolenia**. Viac informácií nájdete v časti [Umožnite prispievateľom použiť pripojenie na export](connections.md#allow-contributors-to-use-a-connection-for-exports).
- Diváci môžu iba prezerať existujúce exporty, ale nemôžu ich vytvárať.

### <a name="define-a-new-export"></a>Definovanie nového exportu

1. Prejdite na **Údaje** > **Exporty**.

1. Vyberte **Pridať export** na vytvorenie nového exportu.

1. V table **Nastaviť export** zvoľte, ktoré pripojenie sa má použiť. [Pripojenia](connections.md) sú spravované správcami. 

1. Zadajte požadované podrobnosti a stlačte možnosť **Uložiť**, čím si vytvoríte export.

### <a name="define-a-new-export-based-on-an-existing-export"></a>Definujte nový export na základe existujúceho exportu

1. Prejdite na **Údaje** > **Exporty**.

1. V zozname exportov vyberte export, ktorý chcete duplikovať.

1. Vyberte **Vytvoriť duplikát** na paneli príkazov na otvorenie tably **Nastaviť export** s podrobnosťami vybratého exportu.

1. Skontrolujte a prispôsobte export a vyberte **Uložiť** na vytvorenie nového exportu.

### <a name="edit-an-export"></a>Upraviť export

1. Prejdite na **Údaje** > **Exporty**.

1. V zozname exportov vyberte export, ktorý chcete upraviť.

1. Na paneli príkazov vyberte **Upraviť**.

1. Zmeňte hodnoty, ktoré chcete aktualizovať, a stlačte možnosť **Uložiť**.

## <a name="view-exports-and-export-details"></a>Zobrazenie exportov a podrobností exportu

Po vytvorení cieľov exportu sa tieto uvedú v časti **Údaje** > **Exporty**. Všetci používatelia môžu vidieť, ktoré údaje sú zdieľané, a ich najnovší stav.

1. Prejdite na **Údaje** > **Exporty**.

1. Používatelia bez oprávnení na úpravy zvoľte možnosť **Zobraziť** namiesto **Upraviť** a zobrazte si podrobnosti exportu.

1. Bočná tabla zobrazuje konfiguráciu exportu. Bez povolení na úpravy nemôžete hodnoty meniť. Stlačte možnosť **Zavrieť** pre návrat na stránku exportu.

## <a name="schedule-and-run-exports"></a>Plánovanie a spustenie exportov

Každý export, ktorý nakonfigurujete, má plán obnovenia. Počas obnovenia systém vyhľadá nové alebo aktualizované údaje, ktoré by zahrnul do exportu. Export sa štandardne spúšťa ako súčasť každého [plánovaného obnovenia systému](system.md#schedule-tab). Môžete prispôsobiť plán obnovenia alebo ho vypnúť, aby sa exporty spúšťali manuálne.

Plány exportu závisia od stavu vášho prostredia. Ak prebiehajú aktualizácie [závislostí](system.md#refresh-policies), keď by sa mal spustiť plánovaný export, systém najskôr dokončí závislosti a potom spustí export. V stĺpci môžete vidieť, kedy sa export naposledy obnovil v stĺpci **Obnovené**.

### <a name="schedule-exports"></a>Plánovanie exportov

Môžete definovať vlastné plány obnovenia pre jednotlivé exporty alebo niekoľko exportov naraz. Aktuálne definovaný plán je uvedený v stĺpci **Plán** exportného zoznamu. Povolenie na zmenu plánu je rovnaké ako pre [úpravy a definovanie exportov](export-destinations.md#set-up-a-new-export). 

1. Prejdite na **Údaje** > **Exporty**.

1. Vyberte export, ktorý chcete naplánovať.

1. Na paneli príkazov vyberte **Plán**.

1. Na table **Plán exportu** nastavte **Naplánovať spustenie** na **Zap** na spustenie exportu automaticky. Nastavte ho na **Vyp**, ak ho chcete obnovovať ručne.

1. Pre automaticky obnovované exporty zvoľte hodnotu **Opakovanie** a uveďte jej podrobnosti. Definovaný čas platí pre všetky prípady opakovania. Je to čas, kedy by sa mal export začať obnovovať.

1. Použite a aktivujte svoje zmeny výberom možnosti **Uložiť**.

Pri úprave plánu pre niekoľko exportov musíte urobiť výber pod **Ponechať alebo prepísať plány**:
- **Ponechať jednotlivé plány**: Zachovanie predtým definovaného plánu pre vybrané exporty a iba ich zakázanie alebo povolenie.
- **Definovať nový plán pre všetky vybraté exporty**: Prepísanie existujúcich plánov vybratých exportov.

### <a name="run-exports-on-demand"></a>Spúšťanie exportov na požiadanie

Ak chcete exportovať údaje bez čakania na plánované obnovenie, prejdite na **Údaje** > **Exporty**.

- Ak chcete spustiť všetky exporty, stlačte možnosť **Spustiť všetko** na paneli príkazov. Táto akcia spustí iba exporty, ktoré majú aktívny plán.
- Ak chcete spustiť jeden export, vyberte ho v zozname a vyberte **Spustiť** na paneli príkazov. Takto spustíte exporty bez aktívneho plánu. 

## <a name="remove-an-export"></a>Odstránenie exportu

1. Prejdite na **Údaje** > **Exporty**.

1. Vyberte export, ktorý chcete odstrániť.

1. Na paneli príkazov vyberte možnosť **Odstrániť**.

1. Odstránenie potvrďte výberom položky **Odstrániť** na obrazovke s potvrdením.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
