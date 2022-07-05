---
title: Export segmentov do Marketo (ukážka)
description: Zistite ako nakonfigurovať pripojenie a realizovať exportovanie do Marketo.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 8cd24cf436bd5fdfd4ec3834d35baa1495e37ca4
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 06/29/2022
ms.locfileid: "9053224"
---
# <a name="export-segments-to-marketo-preview"></a>Export segmentov do Marketo (ukážka)

Marketo umožňuje export zjednotených profilov zákazníkov s cieľom vytvárať kampane, poskytovať e-mailový marketing a využívať konkrétne skupiny zákazníkov.

## <a name="prerequisites-for-connection"></a>Predpoklad na pripojenie

-   Máte [účet Marketo](https://login.marketo.com/) a zodpovedajúce poverenia správcu.
-   V službe Marketo a zodpovedajúcich ID existujú zoznamy. Ďalšie informácie nájdete v téme [Zoznamy služby Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).
-   Máte [nakonfigurované segmenty](segments.md).
-   Zjednotené profily zákazníkov v exportovaných segmentoch obsahujú pole predstavujúce e-mailovú adresu.

## <a name="known-limitations"></a>Známe obmedzenia

- Až 1 milión profilov zákazníkov na export do služby Marketo.
- Export do Marketo je obmedzený na segmenty.
- Export segmentov s celkovo 1 miliónom profilov zákazníkov môže trvať až 3 hodiny. 
- Počet profilov zákazníkov, ktoré môžete exportovať do služby Marketo, závisí od vašej zmluvy so spoločnosťou Marketo a je obmedzený.

## <a name="set-up-connection-to-marketo"></a>Nastavenie pripojenia k Marketo

1. Prejdite do časti **Správca** > **Pripojenia**.

1. Stlačte možnosť **Pridať pripojenie** a stlačením možnosti **Marketo** nakonfigurujte pripojenie.

1. Do poľa **Zobrazovaný názov** zadajte rozpoznateľný názov pripojenia. Zobrazovaný názov a typ spojenia, ktoré popisuje toto spojenie. Odporúčame zvoliť názov, ktorý vysvetľuje účel a cieľ tohto spojenia.

1. Vyberte používateľov, ktorí môžu používať toto pripojenie. Ak neurobíte nič, predvolená hodnota bude Správcovia. Viac informácií nájdete v časti [Umožnite prispievateľom použiť pripojenie na export](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Zadajte svoje **[ID klienta Marketo, tajný kľúč klienta a názov hostiteľa koncového bodu REST](https://developers.marketo.com/rest-api/authentication/)**. Názov hostiteľa koncového bodu REST je iba názov hostiteľa bez `https://`. Príklad: `xyz-abc-123.mktorest.com`. 

1. Výberom položky **Súhlasím** potvrďte **Ochranu osobných údajov a dodržiavanie súladu s nariadeniami** a vyberte položku **Pripojiť** na inicializáciu pripojenia k službe Marketo.

1. Vyberte položku **Pridať samého seba ako používateľa exportu** a uveďte svoje poverenia pre Customer Insights.

1. Stlačte možnosť **Uložiť** a dokončite pripojenie.

## <a name="configure-an-export"></a>Nakonfigurujte export

Tento export môžete nakonfigurovať, ak máte prístup k pripojeniu tohto typu. Viac informácií nájdete na stránke [Na konfiguráciu exportu sú potrebné povolenia](export-destinations.md#set-up-a-new-export).

1. Prejdite na **Údaje** > **Exporty**.

1. Na vytvorenie nového exportu stlačte možnosť **Pridať cieľ**.

1. V poli **Pripojenie na export** vyberte pripojenie v časti Marketo. Ak nevidíte názov tejto sekcie, nemáte k dispozícii žiadne spojenia tohto typu.

1. Zadajte svoje **[ID zoznamu Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)**. ID zoznamu je čisto číselná hodnota. Napríklad, ak je vaše ID v zozname Marketo ST12345A7, odstráňte znak pred a za číslicami a zadajte `12345`. 

1. V **Zhoda údajov** vyberte aspoň jedno pole, ktoré predstavuje e-mailovú adresu zákazníka alebo Marketo ID zákazníka. 

1. Voliteľné možno exportovať **Meno**, **Priezvisko**, **Mesto**, **Štát** a **Krajina/oblasť** a vytvorte si viac prispôsobené e-maily. Výberom položky **Pridať atribút** namapujete tieto polia.

1. Vyberte segmenty, ktoré chcete exportovať. Do služby Marketo môžete exportovať spolu až 1 milión zákazníckych profilov.

1. Vyberte položku **Uložiť**.

Uloženie exportu nespustí export okamžite.

Export prebieha s každým [plánovaným obnovením](system.md#schedule-tab). Môžete tiež [exportovať údaje na požiadanie](export-destinations.md#run-exports-on-demand). V službe Marketo teraz nájdete svoje segmenty v sekcii [Zoznamy Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).


## <a name="data-privacy-and-compliance"></a>Ochrana osobných údajov a dodržiavanie súladu s nariadeniami

Keď povolíte prenos údajov spoločnosti Marketo v službe Dynamics 365 Customer Insights, povoľujete tým prenos údajov mimo hranice súladu so službou Dynamics 365 Customer Insights vrátane potenciálne citlivých údajov, ako sú napríklad osobné údaje. Spoločnosť Microsoft prenesie tieto údaje na váš pokyn, ale vy ste zodpovední za zabezpečenie toho, aby spoločnosť Marketo plnila všetky prípadné povinnosti týkajúce sa ochrany vašich osobných údajov alebo zabezpečenia. Ďalšie informácie nájdete vo [vyhlásení o ochrane súkromia spoločnosti Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Váš správca služby Dynamics 365 Customer Insights môže túto funkciu kedykoľvek prestať používať odstránením tohto cieľového umiestnenia exportu.


[!INCLUDE [footer-include](includes/footer-banner.md)]
