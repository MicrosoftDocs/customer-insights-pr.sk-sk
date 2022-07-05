---
title: Export segmentov do Sendinblue (verzia Preview)
description: Zistite, ako nakonfigurovať pripojenie a exportovať do Sendinblue.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 9f6550b5c57866702631b4c294bb059279461bd6
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 06/29/2022
ms.locfileid: "9083088"
---
# <a name="export-segments-to-sendinblue-preview"></a>Export segmentov do Sendinblue (verzia Preview)

Sendinblue umožňuje export segmentov zjednotených zákazníkov na tvorbu kampaní, poskytovanie e-mailového marketingu a využívanie konkrétny skupín zákazníkov.

## <a name="prerequisites-for-connection"></a>Predpoklad na pripojenie

-   Máte [účet Sendinblue](https://www.sendinblue.com/) a zodpovedajúce poverenia správcu.
-   V rámci Sendinblue existujú zoznamy a zodpovedajúce ID.
-   Máte [nakonfigurované segmenty](segments.md).
-   Zjednotené profily zákazníkov v exportovaných segmentoch obsahujú pole predstavujúce e-mailovú adresu.

## <a name="known-limitations"></a>Známe obmedzenia

- Až 1 milión profilov zákazníkov na export do služby Sendinblue.
- Export do Sendinblue je obmedzený na segmenty.
- Export segmentov s celkovo 1 miliónom profilov zákazníkov môže trvať až 90 minút. 
- Počet profilov zákazníkov, ktoré môžete exportovať do služby Sendinblue, závisí od vašej zmluvy so spoločnosťou Sendinblue a je obmedzený.

## <a name="set-up-connection-to-sendinblue"></a>Nastavenie pripojenia k Sendinblue

1. Prejdite do časti **Správca** > **Pripojenia**.

1. Vyberte možnosť **Pridať pripojenie** a výberom položky **Sendinblue** nakonfigurujte pripojenie.

1. Do poľa **Zobrazovaný názov** zadajte rozpoznateľný názov pripojenia. Zobrazovaný názov a typ spojenia, ktoré popisuje toto spojenie. Odporúčame zvoliť názov, ktorý vysvetľuje účel a cieľ tohto spojenia.

1. Vyberte používateľov, ktorí môžu používať toto pripojenie. Predvolene sú to iba správcovia. Viac informácií nájdete v časti [Umožnite prispievateľom použiť pripojenie na export](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Zadajte svoj **[kľúč rozhrania API pre SendinBlue](https://developers.sendinblue.com/docs/getting-started#:~:text=Get%20your%20API%20key&text=You%20can%20create%20one%20from,your%20settings%20This%20API%20key)**.

1. Výberom možnosti **Súhlasím** potvrďte položku **Ochrana osobných údajov a dodržiavanie súladu s nariadeniami** a výberom možnosti **Pripojiť** inicializujte pripojenie k Sendinblue.

1. Vyberte položku **Pridať samého seba ako používateľa exportu** a uveďte svoje poverenia pre Customer Insights.

1. Stlačte možnosť **Uložiť** a dokončite pripojenie.

## <a name="configure-an-export"></a>Nakonfigurujte export

Tento export môžete nakonfigurovať, ak máte prístup k pripojeniu tohto typu. Viac informácií nájdete na stránke [Na konfiguráciu exportu sú potrebné povolenia](export-destinations.md#set-up-a-new-export).

1. Prejdite na **Údaje** > **Exporty**.

1. Na vytvorenie nového exportu stlačte možnosť **Pridať cieľ**.

1. V poli **Pripojenie na export** vyberte pripojenie zo sekcie Sendinblue. Ak nevidíte názov tejto sekcie, nemáte k dispozícii žiadne spojenia tohto typu.

1. Zadajte svoje **ID zoznamu aplikácie Sendinblue** 

1. V sekcii **Párovanie údajov** v poli **E-mail** vyberte pole, ktoré predstavuje e-mailovú adresu zákazníka. 

1. Prípadne môžete aj exportovať **krstné meno**, **priezvisko** a **telefón**, a vytvoriť tak prispôsobenejšie e-maily. Výberom položky **Pridať atribút** namapujete tieto polia.

1. Vyberte segmenty, ktoré chcete exportovať. 

1. Vyberte položku **Uložiť**.

Uloženie exportu nespustí export okamžite.

Export prebieha s každým [plánovaným obnovením](system.md#schedule-tab). Môžete tiež [exportovať údaje na požiadanie](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Ochrana osobných údajov a dodržiavanie súladu s nariadeniami

Keď povolíte službe Dynamics 365 Customer Insights, aby prenášala údaje do Sendinblue, povoľujete tým aj prenos údajov mimo hranice súladu so službou Dynamics 365 Customer Insights vrátane potenciálne citlivých údajov, ako sú napríklad osobné údaje. Microsoft prenesie tieto údaje na váš pokyn, ale vy ste zodpovední za zabezpečenie toho, aby Sendinblue spĺňal všetky záväzky týkajúce sa ochrany vášho súkromia alebo bezpečnosti. Ďalšie informácie nájdete vo [vyhlásení o ochrane súkromia spoločnosti Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Váš správca služby Dynamics 365 Customer Insights môže túto funkciu kedykoľvek prestať používať odstránením tohto cieľového umiestnenia exportu.


[!INCLUDE [footer-include](includes/footer-banner.md)]
