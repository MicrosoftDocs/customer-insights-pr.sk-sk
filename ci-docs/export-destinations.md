---
title: Prehľad exportov (verzia Preview)
description: Spravujte exporty do zdieľania údajov.
ms.date: 08/12/2022
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
ms.openlocfilehash: 44f58d694b9bd35a8d8c04d487d40743291e0566
ms.sourcegitcommit: ef3e17134d44d2731605381ea0385dbc5aef6120
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 09/09/2022
ms.locfileid: "9460209"
---
# <a name="exports-preview-overview"></a>Prehľad exportov (verzia Preview)

 Exporty vám umožňujú zdieľať špecifické údaje s rôznymi aplikáciami. Môžu zahŕňať profily zákazníkov, entity, schémy a podrobnosti o mapovaní. Každý export vyžaduje [pripojenie, nastavenie zo strany správcu na správu autentifikácie a prístupu](connections.md). Stránka **Exporty** zobrazuje všetky nakonfigurované exporty.

## <a name="export-types"></a>Typy exportu

Existujú dva hlavné typy exportov:  

- **Export dát** vám umožní exportovať akýkoľvek typ entity dostupnej v Customer Insights. Entity, ktoré vyberiete na export, sa exportujú so všetkými údajovými poľami, metadátami, schémami a podrobnosťami mapovania.
- **Segmentové exporty** vám umožní exportovať entity segmentov z Customer Insights. Pre individuálnych spotrebiteľov (B-to-C) predstavujú segmenty zoznam zákazníckych profilov. Pre firmy (B-to-B), [segmenty môžu predstavovať zoznam účtov alebo kontaktov](segment-builder.md#create-a-new-segment-with-segment-builder). Pri konfigurácii exportu vyberáte zahrnuté dátové polia v závislosti od cieľového systému, do ktorého exportujete dáta.

### <a name="export-segments"></a>Segmenty exportu

**Export segmentov v prostrediach pre firemné obchodné vzťahy (firma a firma) alebo individuálnych spotrebiteľov (firma a spotrebiteľ)**  
Väčšina možností exportu podporuje oba typy prostredí. Export segmentov do rôznych cieľových systémov má špecifické požiadavky. 

**Exporty segmentov v prostrediach pre jednotlivých spotrebiteľov (firma a spotrebiteľ)**  
- Segmenty v kontexte prostredí pre jednotlivých zákazníkov sú založené na entite *zjednotený profil zákazníka*. Exportovať je možné každý segment, ktorý spĺňa požiadavky cieľových systémov (napríklad e -mailová adresa).

**Segmentovať exporty v prostrediach pre obchodné účty (B-to-B)**  
- Segmenty v kontexte prostredí pre obchodné účty sú postavené na *účtu* subjekt alebo *kontakt* subjekt. Na export segmentov obchodného vzťahu tak, ako sú, musí cieľový systém podporovať čisté segmenty obchodných vzťahov. To je prípad [LinkedIn](export-linkedin-ads.md), keď si vyberiete možnosť **spoločnosť** pri definovaní exportu.
- Všetky ostatné cieľové systémy vyžadujú polia od entity kontaktu.
- S dvomi typmi segmentov (kontakty a účty) Customer Insights automaticky identifikuje, ktorý typ segmentov je vhodný na export na základe cieľového systému. Napríklad pre cieľový systém zameraný na kontakt, ako je Mailchimp, vám Customer Insights umožňuje vybrať segmenty kontaktov na export.

**Limity exportu segmentov**  
- Cieľové systémy tretích strán môžu obmedziť počet zákazníckych profilov, ktoré môžete exportovať. 
- Pri individuálnych zákazníkoch uvidíte skutočný počet členov segmentu, keď vyberiete segment na export. Ak je segment príliš veľký, dostanete varovanie. 
- V prípade firemných účtov uvidíte počet účtov alebo kontaktov v závislosti od segmentu. Ak je segment príliš veľký, dostanete varovanie. Prekročenie limitov výsledkov cieľových systémov preskočí export.

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

Každý export, ktorý nakonfigurujete, má plán obnovenia. Počas obnovenia systém vyhľadá nové alebo aktualizované údaje, ktoré by zahrnul do exportu. Export sa štandardne spúšťa ako súčasť každého [plánovaného obnovenia systému](schedule-refresh.md). Môžete prispôsobiť plán obnovenia alebo ho vypnúť, aby sa exporty spúšťali manuálne.

> [!TIP]
> Minimalizujte čas spracovania exportov segmentov pomocou nasledujúcich osvedčených postupov:
> - Rozdeľte entity segmentov v rámci viacerých exportov.
> - Vyhnite sa plánovaniu všetkých exportov naraz. Ponechajte 30 minút alebo jednu hodinu medzi naplánovaným časom každého exportu.

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

## <a name="troubleshooting"></a>Riešenie problémov

### <a name="segment-not-eligible-for-export"></a>Segment nie je vhodný na export

**Problém** V prostredí obchodných účtov vaše exporty zlyhávajú s chybovým hlásením: „Nasledujúci segment nie je vhodný pre tento exportný cieľ:“{ názov segmentu} '. Vyberte len segmenty typu ContactProfile a skúste to znova."

**Rozhodnutie** Prostredia Customer Insights pre firemné účty boli aktualizované, aby okrem segmentov účtov podporovali aj segmenty kontaktov. V dôsledku tejto zmeny exporty vyžadujúce kontaktné údaje fungujú iba so segmentmi založenými na kontaktoch.

1. [Vytvorte segment založený na kontaktoch](segment-builder.md) ktorý sa zhoduje s predtým použitým segmentom.

1. Po spustení segmentu kontaktu upravte príslušný export a vyberte nový segment.

1. Vyberte **Uložiť** pre uloženie konfigurácie resp **Uložiť a spustiť** tento export ihneď otestovať.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]


[!INCLUDE [footer-include](includes/footer-banner.md)]
