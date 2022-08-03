---
title: Export segmentov do LiveRamp (ukážka)
description: Zistite ako nakonfigurovať pripojenie a realizovať exportovanie do LiveRamp.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 55eacea3af83f46583a3a43797d625479f56586b
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196735"
---
# <a name="export-segments-to-liverampreg-preview"></a>Export segmentov do LiveRamp&reg; (ukážka)

Aktivujte svoje údaje v službe LiveRamp a spojte sa s viac ako 500 platformami v digitálnych, sociálnych a televíznych zariadeniach. Spolupracujte s vašimi údajmi v riešení LiveRamp na zacielení, potlačení a prispôsobení reklamných kampaní.

## <a name="prerequisites"></a>Požiadavky

- Predplatné LiveRamp na používanie tohto konektora. Ak chcete získať predplatné, [kontaktujte LiveRamp](https://liveramp.com/contact/) priamo. [Získajte viac informácií o zaradení riešenia LiveRamp](https://liveramp.com/our-platform/data-onboarding/).

## <a name="known-limitations"></a>Známe obmedzenia

- Export LiveRamp používa export SFTP. Ciele SFTP za bránami firewall momentálne nie sú podporované.
- Ak na autentifikáciu používate kľúč SSH, uistite sa, že ste [vytvorte si svoj súkromný kľúč](/azure/virtual-machines/linux/create-ssh-keys-detailed#basic-example) ako formát PEM alebo SSH.COM. Ak používate Putty, konvertujte svoj súkromný kľúč exportovaním ako Open SSH. Podporované sú nasledujúce formáty súkromných kľúčov:
  - RSA vo formáte OpenSSL PEM a ssh.com
  - DSA vo formáte OpenSSL PEM a ssh.com
  - ECDSA 256/384/521 vo formáte OpenSSL PEM
  - ED25519 a RSA vo formáte kľúča OpenSSH
- Čas spustenia exportu závisí od výkonu vášho systému. Ako minimálna konfigurácia vášho servera odporúčame dve jadrá CPU a 1 GB pamäte.
- Export entít s až 100 miliónmi zákazníckych profilov môže trvať 90 minút pri použití odporúčanej minimálnej konfigurácie dvoch jadier CPU a 1 GB pamäte.
- Skutočný počet profilov (alebo údajov), ktoré môžete exportovať do LiveRamp, závisí od vášho predplatného s LiveRamp.

## <a name="set-up-connection-to-liveramp"></a>Nastavenie pripojenia k LiveRamp

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Prejdite do časti **Správca** > **Pripojenia**.

1. Vyberte **Pridať pripojenie** a vyberte si **LiveRamp**.

1. Do poľa **Zobrazovaný názov** zadajte rozpoznateľný názov pripojenia. Zobrazovaný názov a typ spojenia, ktoré popisuje toto spojenie. Odporúčame zvoliť názov, ktorý vysvetľuje účel a cieľ tohto spojenia.

1. Vyberte používateľov, ktorí môžu používať toto pripojenie. Predvolene sú to iba správcovia. Viac informácií nájdete v časti [Umožnite prispievateľom použiť pripojenie na export](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Vyberte, či sa chcete overiť prostredníctvom SSH alebo používateľského mena/hesla pre vaše pripojenie a uveďte potrebné podrobnosti.

1. Vyberte **Overiť** na testovanie pripojenia k riešeniu LiveRamp.

1. Po úspešnom overení skontrolujte [ochrana osobných údajov a dodržiavanie predpisov](connections.md#data-privacy-and-compliance) a vyberte **Súhlasím**.

1. Stlačte možnosť **Uložiť** a dokončite pripojenie.

## <a name="configure-an-export"></a>Nakonfigurujte export

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Prejdite na **Údaje** > **Exporty**.

1. Vyberte **Pridať export**.

1. V poli **Pripojenie na export** vyberte pripojenie v časti LiveRamp. Ak nie je k dispozícii pripojenie, kontaktujte správcu.

1. Zadajte názov exportu.

1. V **Pripojte dáta** pole, vyberte **Email**, **a adresa**, alebo **Telefón** poslať na LiveRamp na vyriešenie identity.

   :::image type="content" source="media/export-liveramp-segments.png" alt-text="Konektor LiveRamp s priradením atribútov.":::

1. Mapujte zodpovedajúce atribúty zo svojej entity *Zákazník* pre vybratý identifikátor kľúča.

1. Vyberte **Pridať atribút** na mapovanie ďalších atribútov na odoslanie do LiveRamp.

   > [!TIP]
   > Poslaním ďalších atribútov kľúčového identifikátora do riešenia LiveRamp pravdepodobne získate vyššiu mieru zhody.

1. Vyberte segmenty, ktoré chcete exportovať.

1. Vyberte **Uložiť**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
