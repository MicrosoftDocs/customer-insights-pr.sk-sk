---
title: Export údajov do hostiteľov SFTP (ukážka) (obsahuje video)
description: Zistite ako nakonfigurovať pripojenie a realizovať exportovanie do umiestnenia SFTP.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: b12d25ecbd2e5fb31d7d5a6bb775dc3e7c1bf007
ms.sourcegitcommit: 5807b7d8c822925b727b099713a74ce2cb7897ba
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 07/28/2022
ms.locfileid: "9207248"
---
# <a name="export-data-to-sftp-hosts-preview"></a>Export údajov do hostiteľov SFTP (ukážka)

Použite svoje údaje o zákazníkoch v aplikáciách tretích strán tak, že ich exportujete do umiestnenia Secure File Transfer Protocol (SFTP).

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWO94X]

## <a name="prerequisites"></a>Požiadavky

- Dostupnosť hostiteľa SFTP a zodpovedajúcich poverení.

## <a name="known-limitations"></a>Známe obmedzenia

- Ciele SFTP za bránami firewall momentálne nie sú podporované.
- Čas spustenia exportu závisí od výkonu vášho systému. Ako minimálna konfigurácia vášho servera odporúčame dve jadrá CPU a 1 GB pamäte.
- Až 100 miliónov zákazníckych profilov, čo môže trvať 90 minút pri použití odporúčanej minimálnej konfigurácie dvoch jadier CPU a 1 Gb pamäte.
- Ak na autentifikáciu používate kľúč SSH, uistite sa, že ste [vytvorte si svoj súkromný kľúč](/azure/virtual-machines/linux/create-ssh-keys-detailed#basic-example) ako formát PEM alebo SSH.COM. Ak používate Putty, konvertujte svoj súkromný kľúč exportovaním ako Open SSH. Podporované sú nasledujúce formáty súkromných kľúčov:
  - RSA vo formáte OpenSSL PEM a ssh.com
  - DSA vo formáte OpenSSL PEM a ssh.com
  - ECDSA 256/384/521 vo formáte OpenSSL PEM
  - ED25519 a RSA vo formáte kľúča OpenSSH

## <a name="set-up-connection-to-sftp"></a>Nastavenie pripojenia k SFTP

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Prejdite do časti **Správca** > **Pripojenia**.

1. Vyberte **Pridať pripojenie** a vyberte si **SFTP**.

1. Do poľa **Zobrazovaný názov** zadajte rozpoznateľný názov pripojenia. Zobrazovaný názov a typ spojenia, ktoré popisuje toto spojenie. Odporúčame zvoliť názov, ktorý vysvetľuje účel a cieľ tohto spojenia.

1. Vyberte používateľov, ktorí môžu používať toto pripojenie. Predvolene sú to iba správcovia. Viac informácií nájdete v časti [Umožnite prispievateľom použiť pripojenie na export](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Vyberte, či sa chcete overiť prostredníctvom SSH alebo používateľského mena/hesla pre vaše pripojenie a uveďte potrebné podrobnosti. Ak na autentifikáciu používate kľúč SSH, uistite sa, že ste [vytvorte si svoj súkromný kľúč](/azure/virtual-machines/linux/create-ssh-keys-detailed#basic-example) ako formát PEM alebo SSH.COM. Ak používate Putty, konvertujte svoj súkromný kľúč exportovaním ako Open SSH. Podporované sú nasledujúce formáty súkromných kľúčov:
   - RSA vo formáte OpenSSL PEM a ssh.com
   - DSA vo formáte OpenSSL PEM a ssh.com
   - ECDSA 256/384/521 vo formáte OpenSSL PEM
   - ED25519 a RSA vo formáte kľúča OpenSSH

1. Na otestovanie pripojenia vyberte **Overiť**.

1. Skontrolujte [ochrana osobných údajov a dodržiavanie predpisov](connections.md#data-privacy-and-compliance) a vyberte **Súhlasím**.

1. Stlačte možnosť **Uložiť** a dokončite pripojenie.

## <a name="configure-an-export"></a>Nakonfigurujte export

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Prejdite na **Údaje** > **Exporty**.

1. Vyberte **Pridať export**.

1. V poli **Pripojenie na export** vyberte pripojenie v časti SFTP. Ak nie je k dispozícii pripojenie, kontaktujte správcu.

1. Zadajte názov exportu.

1. Vyberte, či chcete exportovať svoje údaje **Zbalené** alebo **Rozbalené** a **oddeľovač polí** pre exportované súbory.

1. Vyberte entity, napríklad segmenty, ktoré chcete exportovať.

   > [!NOTE]
   > Každá vybraná entita bude pri exporte rozdelená do maximálne piatich výstupných súborov.

1. Vyberte **Uložiť**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

> [!TIP]
> Export entít, ktoré obsahujú veľké množstvo údajov, môže viesť k viacerým súborom CSV v rovnakom priečinku pre každý export. K rozdeleniu exportov dochádza z dôvodov výkonu, aby sa minimalizoval čas potrebný na dokončenie exportu.

[!INCLUDE [footer-include](includes/footer-banner.md)]
