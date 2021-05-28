---
title: Exportujte údaje z Customer Insights
description: Spravujte exporty do zdieľania údajov.
ms.date: 03/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: c1078ed0ba259a6e9cde3c7ede3570890ae48e67
ms.sourcegitcommit: 33a8e21b3bf6521bdb8346f81f79fce88091ddfd
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 05/10/2021
ms.locfileid: "6016655"
---
# <a name="exports-preview-overview"></a>Prehľad exportov (verzia Preview)

Stránka **Exporty** zobrazuje všetky nakonfigurované exporty. Exporty zdieľajú konkrétne údaje s rôznymi aplikáciami. Môžu obsahovať zákaznícke profily alebo entity, schémy a podrobnosti mapovania. Každý export vyžaduje [pripojenie, nastavenie zo strany správcu na správu autentifikácie a prístupu](connections.md).

Prejdite do ponuky **Údaje** > **Exporty** a zobrazte si stránku s exportmi. Všetky používateľské roly majú prístup na zobrazenie nakonfigurovaných exportov. Pomocou vyhľadávacieho poľa na paneli príkazov môžete vyhľadať exporty podľa ich názvu, názvu pripojenia alebo typu pripojenia.

## <a name="set-up-a-new-export"></a>Nastavenie nového exportu

Ak chcete nastaviť alebo upraviť export, musíte mať k dispozícii pripojenia. Pripojenia závisia od vašej [roly používateľa](permissions.md):
- Správcovia majú prístup ku všetkým pripojeniam. Môžu tiež vytvárať nové pripojenia pri nastavovaní exportu.
- Prispievatelia môžu mať prístup ku konkrétnym pripojeniam. Závisia od správcov, ktorí konfigurujú a zdieľajú pripojenia. Viac informácií nájdete v časti [Umožnite prispievateľom použiť pripojenie na export](connections.md#allow-contributors-to-use-a-connection-for-exports).
- Diváci môžu iba prezerať existujúce exporty, ale nemôžu ich vytvárať.

1. Prejdite na **Údaje** > **Exporty**.

1. Stlačte možnosť **Pridať export** na vytvorenie nového cieľového umiestnenia exportu.

1. V table **Nastaviť export** zvoľte, ktoré pripojenie sa má použiť. [Pripojenia](connections.md) sú spravované správcami. 

1. Zadajte požadované podrobnosti a stlačte možnosť **Uložiť**, čím si vytvoríte export.

### <a name="edit-an-export"></a>Upraviť export

1. Vyberte zvislé tri bodky pri cieli exportu, ktorý chcete upraviť.

1. V rozbaľovacej ponuke stlačte možnosť **Upraviť**.

1. Zmeňte hodnoty, ktoré chcete aktualizovať, a stlačte možnosť **Uložiť**.

## <a name="view-exports-and-export-details"></a>Zobraziť exporty a podrobnosti exportu

Po vytvorení exportných cieľov sa uvedú v časti **Údaje** > **Exporty**. Všetci používatelia môžu vidieť, ktoré údaje sú zdieľané, a ich najnovší stav.

1. Prejdite na **Údaje** > **Exporty**.

1. Používatelia bez oprávnení na úpravy zvoľte možnosť **Zobraziť** namiesto **Upraviť** a zobrazte si podrobnosti exportu.

1. Táto bočná tabla zobrazuje nastavenie tohto exportu. Bez povolení na úpravy nemôžete hodnoty meniť. Stlačte možnosť **Zavrieť** pre návrat na stránku exportu.

## <a name="run-exports-on-demand"></a>Spúšťanie exportov na požiadanie

Po nakonfigurovaní exportu bude prebiehať s každým [plánované obnovenie](system.md#schedule-tab) pokiaľ má funkčné spojenie.

Ak chcete exportovať údaje bez čakania na plánované obnovenie, prejdite na **Údaje** > **Exporty**. Máte dve možnosti:

- Ak chcete spustiť všetky exporty, stlačte možnosť **Spustiť všetko** na paneli príkazov. 
- Ak chcete spustiť jeden export, stlačte tri bodky (...) v položke zoznamu a potom stlačte možnosť **Spustiť**.

## <a name="remove-an-export"></a>Odstránenie exportu

1. Prejdite na **Údaje** > **Exporty**.

1. Vyberte zvislé tri bodky pri exporte, ktorý chcete odstrániť.

1. Vyberte položku **Odstrániť** z rozbaľovacej ponuky.

1. Odstránenie potvrďte výberom položky **Odstrániť** na obrazovke s potvrdením.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
