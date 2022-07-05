---
title: Prehľad exportov (verzia Preview)
description: Spravujte exporty do zdieľania údajov.
ms.date: 11/01/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: overview
author: pkieffer
ms.author: philk
manager: shellyha
searchScope:
- ci-export
- ci-connections
- customerInsights
ms.openlocfilehash: d983e84e713003610eb27dc9b3f911b62b01d522
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 06/29/2022
ms.locfileid: "9082920"
---
# <a name="exports-preview-overview"></a>Prehľad exportov (verzia Preview)

Stránka **Exporty** zobrazuje všetky nakonfigurované exporty. Exporty zdieľajú konkrétne údaje s rôznymi aplikáciami. Môžu zahŕňať profily zákazníkov, entity, schémy a podrobnosti o mapovaní. Každý export vyžaduje [pripojenie, nastavenie zo strany správcu na správu autentifikácie a prístupu](connections.md).

Prejdite do ponuky **Údaje** > **Exporty** a zobrazte si stránku s exportmi. Všetky roly používateľov môžu zobrazovať nakonfigurované exporty. Pomocou vyhľadávacieho poľa na paneli príkazov vyhľadajte exporty podľa názvu, názvu pripojenia alebo typu pripojenia.

## <a name="export-types"></a>Typy exportu

Existujú dva hlavné typy exportov:  

- **Export dát** vám umožní exportovať akýkoľvek typ entity dostupnej v Customer Insights. Entity, ktoré vyberiete na export, sa exportujú so všetkými údajovými poľami, metadátami, schémami a podrobnosťami mapovania. 
- **Segmentové exporty** vám umožní exportovať entity segmentov z Customer Insights. Segmenty predstavujú zoznam profilov zákazníkov. Pri konfigurácii exportu vyberiete zahrnuté údajové polia v závislosti od cieľového systému, do ktorého exportujete údaje. 

### <a name="export-segments"></a>Segmenty exportu

**Export segmentov v prostrediach pre firemné obchodné vzťahy (firma a firma) alebo individuálnych spotrebiteľov (firma a spotrebiteľ)**  
Väčšina možností exportu podporuje oba typy prostredí. Export segmentov do rôznych cieľových systémov má špecifické požiadavky. Člen segmentu, profil zákazníka spravidla obsahuje kontaktné informácie. Aj keď to zvyčajne platí pre segmenty postavené na individuálnych spotrebiteľoch (firma a spotrebiteľ), nemusí to nevyhnutne platiť pre segmenty založené na firemných obchodných vzťahoch (firma a firma). 

**Prostredia exportu segmentov pre firemné obchodné vzťahy (firma a firma)**  
- Segmenty v kontexte prostredí pre firemné obchodné vzťahy sú založené na entite *obchodný vzťah*. Na export segmentov obchodného vzťahu tak, ako sú, musí cieľový systém podporovať čisté segmenty obchodných vzťahov. To je prípad [LinkedIn](export-linkedin-ads.md), keď si vyberiete možnosť **spoločnosť** pri definovaní exportu.
- Všetky ostatné cieľové systémy vyžadujú polia od entity kontaktu. Aby ste zaistili, že segmenty obchodného vzťahu môžu získavať údaje zo súvisiacich kontaktov, definícia vášho segmentu musí premietať atribúty entity kontaktu. Prečítajte si viac o tom, ako [konfigurovať segmenty a atribúty projektu](segment-builder.md).

**Exporty segmentov v prostrediach pre jednotlivých spotrebiteľov (firma a spotrebiteľ)**  
- Segmenty v kontexte prostredí pre jednotlivých zákazníkov sú založené na entite *zjednotený profil zákazníka*. Exportovať je možné každý segment, ktorý spĺňa požiadavky cieľových systémov (napríklad e -mailová adresa).

**Limity exportu segmentov**  
- Cieľové systémy tretích strán môžu obmedziť počet zákazníckych profilov, ktoré môžete exportovať. 
- Pri individuálnych zákazníkoch uvidíte skutočný počet členov segmentu, keď vyberiete segment na export. Ak je segment príliš veľký, zobrazí sa upozornenie. 
- Pri firemných obchodných vzťahoch uvidíte počet obchodných vzťahov v segmente; počet kontaktov, ktoré je možné projektovať, sa však nezobrazí. V niektorých prípadoch to môže viesť k tomu, že exportovaný segment skutočne obsahuje viac profilov zákazníkov, ako cieľový systém akceptuje. Prekročenie limitov výsledkov cieľových systémov preskočí export. 

## <a name="set-up-a-new-export"></a>Nastavenie nového exportu  
Ak chcete nastaviť alebo upraviť export, musíte mať k dispozícii pripojenia. Pripojenia závisia od vašej [roly používateľa](permissions.md):
- **Správcovia** majú prístup ku všetkým pripojeniam. Môžu tiež vytvárať nové pripojenia pri nastavovaní exportu.
- **Prispievatelia** môžu mať prístup ku konkrétnym pripojeniam. Závisia od správcov, ktorí konfigurujú a zdieľajú pripojenia. Zoznam exportov zobrazuje prispievateľov, či môžu upravovať alebo len zobraziť export v stĺpci **Vaše povolenia**. Ak chcete získať ďalšie informácie, navštívte stránku [Povoliť prispievateľom používať pripojenie na export](connections.md#allow-contributors-to-use-a-connection-for-exports).
- **Diváci** môžu zobrazovať iba existujúce exporty – nie ich vytvárať.

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

1. Používatelia bez povolení na úpravy vyberú možnosť **Zobraziť** namiesto možnosti **Upraviť** na zobrazenie podrobností o exporte.

1. Bočná tabla zobrazuje konfiguráciu exportu. Bez povolení na úpravy nemôžete hodnoty meniť. Stlačte možnosť **Zavrieť** pre návrat na stránku exportu.

## <a name="schedule-and-run-exports"></a>Plánovanie a spustenie exportov

Každý export, ktorý nakonfigurujete, má plán obnovenia. Počas obnovenia systém vyhľadá nové alebo aktualizované údaje, ktoré by zahrnul do exportu. Export sa štandardne spúšťa ako súčasť každého [plánovaného obnovenia systému](system.md#schedule-tab). Môžete prispôsobiť plán obnovenia alebo ho vypnúť, aby sa exporty spúšťali manuálne.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

Plány exportu závisia od stavu vášho prostredia. Ak prebiehajú aktualizácie v rámci [závislostí](system.md#refresh-processes), keď sa má spustiť plánovaný export, systém najskôr dokončí aktualizácie a potom spustí export. V stĺpci môžete vidieť, kedy sa export naposledy obnovil v stĺpci **Obnovené**.

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


[!INCLUDE [footer-include](includes/footer-banner.md)]
