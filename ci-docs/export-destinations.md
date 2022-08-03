---
title: Prehľad exportov (verzia Preview)
description: Spravujte exporty do zdieľania údajov.
ms.date: 07/25/2022
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
ms.openlocfilehash: a70aadda4fc0eff3ddb4c89665506762613c291a
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 07/27/2022
ms.locfileid: "9194987"
---
# <a name="exports-preview-overview"></a>Prehľad exportov (verzia Preview)

 Exporty vám umožňujú zdieľať špecifické údaje s rôznymi aplikáciami. Môžu zahŕňať profily zákazníkov, entity, schémy a podrobnosti o mapovaní. Každý export vyžaduje [pripojenie, nastavenie zo strany správcu na správu autentifikácie a prístupu](connections.md). Stránka **Exporty** zobrazuje všetky nakonfigurované exporty.

## <a name="export-types"></a>Typy exportu

Existujú dva hlavné typy exportov:  

- **Export dát** : exportovať akýkoľvek typ entity dostupnej v Customer Insights. Entity, ktoré vyberiete na export, sa exportujú so všetkými údajovými poľami, metadátami, schémami a podrobnosťami mapovania.
- **Segmentové exporty** : export entít segmentu z Customer Insights. Segmenty predstavujú zoznam profilov zákazníkov. Pri konfigurácii exportu vyberáte zahrnuté dátové polia v závislosti od cieľového systému, do ktorého exportujete dáta.

### <a name="export-segments"></a>Segmenty exportu

**Export segmentov v prostrediach pre firemné obchodné vzťahy (firma a firma) alebo individuálnych spotrebiteľov (firma a spotrebiteľ)**  
Väčšina možností exportu podporuje oba typy prostredí. Export segmentov do rôznych cieľových systémov má špecifické požiadavky. 

**Exporty segmentov v prostrediach pre jednotlivých spotrebiteľov (firma a spotrebiteľ)**  
- Segmenty v kontexte prostredí pre jednotlivých zákazníkov sú založené na entite *zjednotený profil zákazníka*. Exportovať je možné každý segment, ktorý spĺňa požiadavky cieľových systémov (napríklad e -mailová adresa).

**Prostredia exportu segmentov pre firemné obchodné vzťahy (firma a firma)**  
- Segmenty v kontexte prostredí pre firemné obchodné vzťahy sú založené na entite *obchodný vzťah*. Na export segmentov obchodného vzťahu tak, ako sú, musí cieľový systém podporovať čisté segmenty obchodných vzťahov. To je prípad [LinkedIn](export-linkedin-ads.md), keď si vyberiete možnosť **spoločnosť** pri definovaní exportu.
- Všetky ostatné cieľové systémy vyžadujú polia od entity kontaktu. Aby ste zaistili, že segmenty obchodného vzťahu môžu získavať údaje zo súvisiacich kontaktov, definícia vášho segmentu musí premietať atribúty entity kontaktu. Prečítajte si viac o tom, ako [konfigurovať segmenty a atribúty projektu](segment-builder.md).

**Limity exportu segmentov**  
- Cieľové systémy tretích strán môžu obmedziť počet zákazníckych profilov, ktoré môžete exportovať. 
- Pri individuálnych zákazníkoch uvidíte skutočný počet členov segmentu, keď vyberiete segment na export. Ak je segment príliš veľký, zobrazí sa upozornenie. 
- Pri firemných obchodných vzťahoch uvidíte počet obchodných vzťahov v segmente; počet kontaktov, ktoré je možné projektovať, sa však nezobrazí. V niektorých prípadoch to môže viesť k tomu, že exportovaný segment skutočne obsahuje viac profilov zákazníkov, ako cieľový systém akceptuje. Ak sú prekročené limity cieľového systému, export sa preskočí.

## <a name="set-up-a-new-export"></a>Nastavenie nového exportu

Na nastavenie alebo úpravu exportu potrebujete správne pripojenia, ktoré máte k dispozícii. Pripojenia závisia od vašej [roly používateľa](permissions.md):
- **Správcovia** majú prístup ku všetkým pripojeniam. Môžu tiež vytvárať nové pripojenia pri nastavovaní exportu.
- **Prispievatelia** môžu mať prístup ku konkrétnym pripojeniam. Závisia od správcov, ktorí konfigurujú a zdieľajú pripojenia. Zoznam exportov zobrazuje prispievateľov, či môžu upravovať alebo len zobraziť export v stĺpci **Vaše povolenia**. Ak chcete získať ďalšie informácie, navštívte stránku [Povoliť prispievateľom používať pripojenie na export](connections.md#allow-contributors-to-use-a-connection-for-exports).
- **Diváci** môžu zobrazovať iba existujúce exporty – nie ich vytvárať.

1. Prejdite na **Údaje** > **Exporty**.

1. Vyberte **Pridať export** na vytvorenie nového exportu.

1. V **Nastavte export** panel, vyberte ktorý [spojenie](connections.md) použit.

1. Zadajte požadované podrobnosti a stlačte možnosť **Uložiť**, čím si vytvoríte export. Požadované podrobnosti nájdete v dokumentácii Customer Insights pre konkrétny export.

## <a name="manage-existing-exports"></a>Spravujte existujúce exporty

Ísť do **Údaje** > **Vývoz** zobrazíte exporty, ich názov pripojenia, typ pripojenia a stav. Všetky roly používateľov môžu zobrazovať nakonfigurované exporty. Zoznam exportov môžete zoradiť podľa ľubovoľného stĺpca alebo pomocou vyhľadávacieho poľa nájsť export, ktorý chcete spravovať.

Ak chcete zobraziť dostupné akcie, vyberte export.

:::image type="content" source="media/exports_showmore.png" alt-text="Stránka exportov.":::

- **vyhliadka** alebo **Upraviť** export. Používatelia bez povolení na úpravy vyberú možnosť **Zobraziť** namiesto možnosti **Upraviť** na zobrazenie podrobností o exporte.
- **Bežať** export na export najnovších údajov.
- **Vytvorte duplikát** vývozu.
- **[Rozvrh](#schedule-and-run-exports)** export.
- **Odpojte pripojenie** na odstránenie pripojenia pre tento export. Detach neodstráni pripojenie, ale deaktivuje export. The **Použité pripojenie** stĺpec zobrazuje No Connection.
- **Odstrániť** export.

## <a name="schedule-and-run-exports"></a>Plánovanie a spustenie exportov

Každý export, ktorý nakonfigurujete, má plán obnovenia. Počas obnovenia systém vyhľadá nové alebo aktualizované údaje, ktoré by zahrnul do exportu. Export sa štandardne spúšťa ako súčasť každého [plánovaného obnovenia systému](system.md#schedule-tab). Môžete prispôsobiť plán obnovenia alebo ho vypnúť, aby sa exporty spúšťali manuálne.

Plány exportu závisia od stavu vášho prostredia. Ak prebiehajú aktualizácie v rámci [závislostí](system.md#refresh-processes), keď sa má spustiť plánovaný export, systém najskôr dokončí aktualizácie a potom spustí export. The **Osviežené** zobrazuje, kedy bol export naposledy obnovený.

### <a name="schedule-exports"></a>Plánovanie exportov

Definujte vlastné plány obnovy pre jednotlivé exporty alebo niekoľko exportov naraz. Aktuálne definovaný plán je uvedený v stĺpci **Plán** exportného zoznamu. Povolenie na zmenu rozvrhu je rovnaké ako [editovanie a definovanie exportov](export-destinations.md#set-up-a-new-export).

1. Prejdite na **Údaje** > **Exporty**.

1. Vyberte export, ktorý chcete naplánovať.

1. Stlačte možnosť **Naplánovať**.

1. Na table **Plán exportu** nastavte **Naplánovať spustenie** na **Zap** na spustenie exportu automaticky. Nastavte ho na **Vyp**, ak ho chcete obnovovať ručne.

1. Pre automaticky obnovované exporty zvoľte hodnotu **Opakovanie** a uveďte jej podrobnosti. Definovaný čas platí pre všetky prípady opakovania. Je to čas, kedy by sa mal export začať obnovovať.

1. Vyberte **Uložiť**.

Pri úprave plánu pre niekoľko exportov vykonajte výber pod **Ponechajte alebo prepíšte plány**:

- **Dodržiavajte individuálne rozvrhy** : Ponechajte predtým definovaný plán pre vybrané exporty a iba ich zakážte alebo povoľte.
- **Definovať nový plán pre všetky vybraté exporty**: Prepísanie existujúcich plánov vybratých exportov.

### <a name="run-exports-on-demand"></a>Spúšťanie exportov na požiadanie

Ak chcete exportovať údaje bez čakania na plánované obnovenie, prejdite na **Údaje** > **Exporty**.

- Ak chcete spustiť všetky exporty, stlačte možnosť **Spustiť všetko** na paneli príkazov. Spustia sa iba exporty, ktoré majú aktívny plán. Ak chcete spustiť export, ktorý nie je aktívny, spustite jeden export.
- Ak chcete spustiť jeden export, vyberte ho v zozname a vyberte **Spustiť** na paneli príkazov.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]


[!INCLUDE [footer-include](includes/footer-banner.md)]
