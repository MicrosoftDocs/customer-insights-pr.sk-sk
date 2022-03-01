---
title: Konektor LiveRamp
description: Naučte sa, ako exportovať údaje do riešenia LiveRamp.
ms.date: 12/02/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 86aa8c66a47ee61741082c95f05d2e5ce3f06f35
ms.sourcegitcommit: 334633cbd58f5659d20b4f87252c1a10cc7130db
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 12/03/2020
ms.locfileid: "4667203"
---
# <a name="liverampreg-connector-preview"></a>Konektor LiveRamp&reg; (ukážka)

Aktivujte svoje údaje v riešení LiveRamp a spojte sa s viac ako 500 platformami naprieč digitálnymi, sociálnymi a televíznymi ekosystémami. Spolupracujte s vašimi údajmi v riešení LiveRamp na zacielení, potlačení a prispôsobení reklamných kampaní.

## <a name="prerequisites"></a>Predpoklady

- Na používanie tohto konektora potrebujete predplatné LiveRamp.
- Ak chcete získať predplatné, [kontaktujte LiveRamp](https://liveramp.com/contact/) priamo. [Získajte viac informácií o zaradení riešenia LiveRamp](https://liveramp.com/our-platform/data-onboarding/).

## <a name="connect-to-liveramp"></a>Pripojenie k riešeniu LiveRamp

1. V prehľadoch cieľových skupín prejdite na **Správca** > **Ciele exportu**.

1. Na dlaždici **LiveRamp** vyberte položku **Nastaviť**.

1. Do poľa **Zobrazovaný názov** zadajte rozpoznateľný názov cieľa.

1. Zadajte **používateľské meno** a **heslo** pre vaše konto LiveRamp Secure FTP (SFTP).
Tieto poverenia sa môžu líšiť od vašich poverení pre LiveRamp Onboarding.

1. Vyberte **Overiť** na testovanie pripojenia k riešeniu LiveRamp.

1. Po úspešnom overení poskytnite svoj súhlas pre **Ochranu osobných údajov a dodržiavanie súladu s nariadeniami** výberom začiarkavacieho políčka **Súhlasím**.

1. Vyberte **Ďalej** na nastavenie konektora LiveRamp.

## <a name="configure-the-connector"></a>Nakonfigurujte konektor

1. V poli **Vyberte identifikátor kľúča** vyberte **E-mail**, **Meno a adresu** alebo **Telefón** na odoslanie do riešenia LiveRamp na rozlíšenie identity.

1. Priraďte zodpovedajúce atribúty z vašej zjednotenej entity zákazníka na vybratý identifikátor kľúča.

1. Vyberte **Pridať atribút** na priradenie ďalších atribútov na odoslanie do LiveRamp.

   > [!TIP]
   > Poslaním ďalších atribútov kľúčového identifikátora do riešenia LiveRamp pravdepodobne získate vyššiu mieru zhody.

1. Vyberte segmenty, ktoré chcete exportovať do LiveRamp.

1. Vyberte položku **Uložiť**.

> [!div class="mx-imgBorder"]
> ![Konektor LiveRamp s priradením atribútov](media/export-liveramp-segments.png "Konektor LiveRamp s priradením atribútov")

## <a name="export-the-data"></a>Export údajov

Export sa začne čoskoro, ak budú splnené všetky predpoklady na export. Export sa spustí aj pri každej [plánovanej obnove](system.md#schedule-tab).
Po úspešnom dokončení exportu sa môžete prihlásiť do riešenia LiveRamp Onboarding a aktivovať a distribuovať svoje údaje.

## <a name="data-privacy-and-compliance"></a>Ochrana osobných údajov a dodržiavanie súladu s nariadeniami

Keď povolíte prenos údajov spoločnosti Liveramp v službe Dynamics 365 Customer Insights, povoľujete tým prenos údajov mimo hranice súladu so službou Dynamics 365 Customer Insights vrátane potenciálne citlivých údajov, ako sú napríklad osobné údaje. Spoločnosť Microsoft prenesie tieto údaje na váš pokyn, ale vy ste zodpovední za zabezpečenie toho, aby spoločnosť Liveramp plnila všetky prípadné povinnosti týkajúce sa ochrany vašich osobných údajov alebo zabezpečenia. Ďalšie informácie nájdete vo [vyhlásení o ochrane súkromia spoločnosti Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Váš správca služby Dynamics 365 Customer Insights môže túto funkciu kedykoľvek prestať používať odstránením tohto cieľového umiestnenia exportu.