---
title: Export údajov Customer Insights do hostiteľov SFTP (video)
description: Zistite ako nakonfigurovať pripojenie a realizovať exportovanie do umiestnenia SFTP.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 568e5826175417175bd09435d697031f0ab64223
ms.sourcegitcommit: e141a6a34a985cca68f03082a700ed27f2f3c0c1
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 12/17/2021
ms.locfileid: "7927622"
---
# <a name="export-segments-and-other-data-to-sftp-preview"></a>Export segmentov a ďalších údajov do SFTP (verzia Preview)

Použite svoje údaje o zákazníkoch v aplikáciách tretích strán tak, že ich exportujete do umiestnenia Secure File Transfer Protocol (SFTP).

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWO94X]

## <a name="prerequisites-for-connection"></a>Predpoklad na pripojenie

- Dostupnosť hostiteľa SFTP a zodpovedajúcich poverení.

## <a name="known-limitations"></a>Známe obmedzenia

- Ciele SFTP za bránami firewall momentálne nie sú podporované. 
- Čas spustenia exportu závisí od výkonu vášho systému. Ako minimálna konfigurácia vášho servera odporúčame dve jadrá CPU a 1 GB pamäte. 
- Export entít s až 100 miliónmi zákazníckych profilov môže trvať 90 minút pri použití odporúčanej minimálnej konfigurácie dvoch jadier CPU a 1 GB pamäte. 

## <a name="set-up-connection-to-sftp"></a>Nastavenie pripojenia k SFTP

1. Prejdite do časti **Správca** > **Pripojenia**.

1. Stlačte možnosť **Pridať pripojenie** a stlačením možnosti **SFTP** nakonfigurujte pripojenie.

1. Do poľa **Zobrazovaný názov** zadajte rozpoznateľný názov pripojenia. Zobrazovaný názov a typ spojenia, ktoré popisuje toto spojenie. Odporúčame zvoliť názov, ktorý vysvetľuje účel a cieľ tohto spojenia.

1. Vyberte používateľov, ktorí môžu používať toto pripojenie. Ak neurobíte nič, predvolená hodnota bude Správcovia. Viac informácií nájdete v časti [Umožnite prispievateľom použiť pripojenie na export](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Uveďte **Používateľské meno**, **Heslo**, **Meno hostiteľa** a **Priečinok na export** pre váš účet SFTP.

1. Na otestovanie pripojenia vyberte **Overiť**.

1. Vyberte, či chcete exportovať svoje údaje **Zbalené** alebo **Rozbalené** a **oddeľovač polí** pre exportované súbory.

1. Vyberte **Súhlasím** na potvrdenie **Ochrany osobných údajov a dodržiavanie súladu s nariadeniami**.

1. Stlačte možnosť **Uložiť** a dokončite pripojenie.

## <a name="configure-an-export"></a>Nakonfigurujte export

Tento export môžete nakonfigurovať, ak máte prístup k pripojeniu tohto typu. Viac informácií nájdete na stránke [Na konfiguráciu exportu sú potrebné povolenia](export-destinations.md#set-up-a-new-export).

1. Prejdite na **Údaje** > **Exporty**.

1. Na vytvorenie nového exportu stlačte možnosť **Pridať cieľ**.

1. V poli **Pripojenie na export** vyberte pripojenie v časti SFTP. Ak nevidíte názov tejto sekcie, nemáte k dispozícii žiadne spojenia tohto typu.

1. Vyberte entity, napríklad segmenty, ktoré chcete exportovať.

   > [!NOTE]
   > Každá vybraná entita sa pri exportovaní rozdelí až na päť výstupných súborov. 

1. Vyberte položku **Uložiť**.

Uloženie exportu nespustí export okamžite.

Export prebieha s každým [plánovaným obnovením](system.md#schedule-tab). Môžete tiež [exportovať údaje na požiadanie](export-destinations.md#run-exports-on-demand). 

## <a name="data-privacy-and-compliance"></a>Ochrana osobných údajov a dodržiavanie súladu s nariadeniami

Keď povolíte prenos údajov spoločnosti SFTP v službe Dynamics 365 Customer Insights, povoľujete tým prenos údajov mimo hranice súladu so službou Dynamics 365 Customer Insights vrátane potenciálne citlivých údajov, ako sú napríklad osobné údaje. Spoločnosť Microsoft prenesie tieto údaje na váš pokyn, ale vy ste zodpovední za zabezpečenie toho, aby cieľ exportu plnil všetky prípadné povinnosti týkajúce sa ochrany vašich osobných údajov alebo zabezpečenia. Ďalšie informácie nájdete vo [vyhlásení o ochrane súkromia spoločnosti Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Váš správca služby Dynamics 365 Customer Insights môže túto funkciu kedykoľvek prestať používať odstránením tohto cieľového umiestnenia exportu.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
