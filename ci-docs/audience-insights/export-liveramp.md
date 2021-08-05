---
title: Konektor LiveRamp
description: Zistite ako nakonfigurovať pripojenie a realizovať exportovanie do LiveRamp.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: b377a3500c5d91962e59d46fbc259db5cc8fa7d0
ms.sourcegitcommit: dab2cbf818fafc9436e685376df94c5e44e4b144
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 07/13/2021
ms.locfileid: "6555464"
---
# <a name="export-segments-to-liverampreg-preview"></a>Export segmentov do LiveRamp&reg; (ukážka)

Aktivujte svoje údaje v službe LiveRamp a spojte sa s viac ako 500 platformami v digitálnych, sociálnych a televíznych zariadeniach. Spolupracujte s vašimi údajmi v riešení LiveRamp na zacielení, potlačení a prispôsobení reklamných kampaní.

## <a name="prerequisites-for-a-connection"></a>Predpoklad na pripojenie

- Na používanie tohto konektora potrebujete predplatné LiveRamp.
- Ak chcete získať predplatné, [kontaktujte LiveRamp](https://liveramp.com/contact/) priamo. [Získajte viac informácií o zaradení riešenia LiveRamp](https://liveramp.com/our-platform/data-onboarding/).

## <a name="set-up-connection-to-liveramp"></a>Nastavenie pripojenia k LiveRamp

1. Prejdite do časti **Správca** > **Pripojenia**.

1. Stlačte možnosť **Pridať pripojenie** a stlačením možnosti **LiveRamp** nakonfigurujte pripojenie.

1. Do poľa **Zobrazovaný názov** zadajte rozpoznateľný názov pripojenia. Zobrazovaný názov a typ spojenia, ktoré popisuje toto spojenie. Odporúčame zvoliť názov, ktorý vysvetľuje účel a cieľ tohto spojenia.

1. Vyberte používateľov, ktorí môžu používať toto pripojenie. Ak neurobíte nič, predvolená hodnota bude Správcovia. Viac informácií nájdete v časti [Umožnite prispievateľom použiť pripojenie na export](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Zadajte **používateľské meno** a **heslo** pre vaše konto LiveRamp Secure FTP (SFTP).
Tieto poverenia sa môžu líšiť od vašich poverení pre LiveRamp Onboarding.

1. Vyberte **Overiť** na testovanie pripojenia k riešeniu LiveRamp.

1. Po úspešnom overení poskytnite svoj súhlas pre **Ochranu osobných údajov a dodržiavanie súladu s nariadeniami** výberom začiarkavacieho políčka **Súhlasím**.

1. Stlačte možnosť **Uložiť** a dokončite pripojenie.

## <a name="configure-an-export"></a>Nakonfigurujte export

Tento export môžete nakonfigurovať, ak máte prístup k pripojeniu tohto typu. Viac informácií nájdete na stránke [Na konfiguráciu exportu sú potrebné povolenia](export-destinations.md#set-up-a-new-export).

1. Prejdite na **Údaje** > **Exporty**.

1. Na vytvorenie nového exportu stlačte možnosť **Pridať cieľ**.

1. V poli **Pripojenie na export** vyberte pripojenie v časti LiveRamp. Ak nevidíte názov tejto sekcie, nemáte k dispozícii žiadne spojenia tohto typu.

1. V poli **Vyberte identifikátor kľúča** vyberte **E-mail**, **Meno a adresu** alebo **Telefón** na odoslanie do riešenia LiveRamp na rozlíšenie identity.
   > [!div class="mx-imgBorder"]
   > ![Konektor LiveRamp s priradením atribútov.](media/export-liveramp-segments.png "Konektor LiveRamp s priradením atribútov")

1. Priraďte zodpovedajúce atribúty z vašej zjednotenej entity zákazníka na vybratý identifikátor kľúča.

1. Vyberte **Pridať atribút** na mapovanie ďalších atribútov na odoslanie do LiveRamp.

   > [!TIP]
   > Poslaním ďalších atribútov kľúčového identifikátora do riešenia LiveRamp pravdepodobne získate vyššiu mieru zhody.

1. Vyberte segmenty, ktoré chcete exportovať do LiveRamp.

1. Vyberte položku **Uložiť**.

Uloženie exportu nespustí export okamžite.

Export prebieha s každým [plánovaným obnovením](system.md#schedule-tab). Môžete tiež [exportovať údaje na požiadanie](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Ochrana osobných údajov a dodržiavanie súladu s nariadeniami

Keď povolíte prenos údajov spoločnosti Liveramp v službe Dynamics 365 Customer Insights, povoľujete tým prenos údajov mimo hranice súladu so službou Dynamics 365 Customer Insights vrátane potenciálne citlivých údajov, ako sú napríklad osobné údaje. Spoločnosť Microsoft prenesie tieto údaje na váš pokyn, ale vy ste zodpovední za zabezpečenie toho, aby spoločnosť Liveramp plnila všetky prípadné povinnosti týkajúce sa ochrany vašich osobných údajov alebo zabezpečenia. Ďalšie informácie nájdete vo [vyhlásení o ochrane súkromia spoločnosti Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Váš správca služby Dynamics 365 Customer Insights môže túto funkciu kedykoľvek prestať používať odstránením tohto cieľového umiestnenia exportu.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
