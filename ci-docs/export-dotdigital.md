---
title: Export údajov služby Customer Insights do DotDigital
description: Zistite ako nakonfigurovať pripojenie a realizovať exportovanie do DotDigital.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: f63a0f5f5f93e96681a88fd758381c012a404f43
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 04/27/2022
ms.locfileid: "8642969"
---
# <a name="export-segments-to-dotdigital-preview"></a>Export segmentov do DotDigital (verzia Preview)

Exportujte segmenty zjednotených profilov zákazníkov do adresárov DotDigital a použite ich na kampane, e-mailový marketing a na vytváranie segmentov zákazníkov cez DotDigital. 

## <a name="prerequisites-for-a-connection"></a>Predpoklad na pripojenie

-   Máte [účet v rámci služby DotDigital](https://dotdigital.com/) a vytvorili ste [používateľa API](https://support.dotdigital.com/hc/articles/115001718730-How-do-I-create-an-API-user). Na vytvorenie pripojenia budete potrebovať používateľské poverenia pre API
-   V DotDigital a zodpovedajúcich ID existujú adresáre. ID nájdete v adrese URL, keď vyberiete a otvoríte adresár. Ďalšie informácie nájdete v [adresároch DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).
-   Máš [nakonfigurované segmenty](segments.md) v Customer Insights.
-   Zjednotené profily zákazníkov v exportovaných segmentoch obsahujú pole predstavujúce e-mailovú adresu.

## <a name="known-limitations"></a>Známe obmedzenia

- Až 1 milión profilov zákazníkov na export do služby DotDigital.
- Export do DotDigital je obmedzený na segmenty.
- Export segmentov s celkovo 1 miliónom profilov zákazníkov môže z dôvodu obmedzení na strane poskytovateľa trvať až 3 hodiny. 
- Počet profilov zákazníkov, ktoré môžete exportovať do služby DotDigital, závisí od vašej zmluvy so spoločnosťou DotDigital a je obmedzený.

## <a name="set-up-connection-to-dotdigital"></a>Nastavenie pripojenia k DotDigital

1. Prejdite do časti **Správca** > **Pripojenia**.

1. Stlačte možnosť **Pridať pripojenie** a stlačením možnosti **DotDigital** nakonfigurujte pripojenie.

1. Do poľa **Zobrazovaný názov** zadajte rozpoznateľný názov pripojenia. Zobrazovaný názov a typ spojenia, ktoré popisuje toto spojenie. Odporúčame zvoliť názov, ktorý vysvetľuje účel a cieľ tohto spojenia.

1. Vyberte používateľov, ktorí môžu používať toto pripojenie. Ak neurobíte nič, predvolená hodnota bude Správcovia. Viac informácií nájdete v časti [Umožnite prispievateľom použiť pripojenie na export](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Zadajte **používateľské meno a heslo pre API DotDigital**. 

1. Zadajte **[ID adresára DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**.

1. Vyberte **Súhlasím** na potvrdenie **Ochrany osobných údajov a dodržiavanie súladu s nariadeniami**.

1. Vyberte položku **Pripojiť** na inicializáciu pripojenia k DotDigital.

1. Vyberte položku **Pridať samého seba ako používateľa exportu** a uveďte svoje poverenia pre Customer Insights.

1. Stlačte možnosť **Uložiť** a dokončite pripojenie. 

## <a name="configure-an-export"></a>Nakonfigurujte export

Tento export môžete nakonfigurovať, ak máte prístup k pripojeniu tohto typu. Viac informácií nájdete na stránke [Na konfiguráciu exportu sú potrebné povolenia](export-destinations.md#set-up-a-new-export).

1. Prejdite na **Údaje** > **Exporty**.

1. Na vytvorenie nového exportu stlačte možnosť **Pridať cieľ**.

1. V poli **Pripojenie na export** vyberte pripojenie v časti DotDigital. Ak nevidíte názov tejto sekcie, nemáte k dispozícii žiadne spojenia tohto typu.


1. V sekcii **Párovanie údajov** v poli **E-mail** vyberte pole, ktoré predstavuje e-mailovú adresu zákazníka. Rovnaký postup zopakujte pri ďalších voliteľných poliach, ako je **Krstné meno**, **Priezvisko**, **Celé meno**, **Rod** a **PSČ**.

1. Vyberte segmenty, ktoré chcete exportovať. Do DotDigital môžete exportovať spolu až 1 milión zákazníckych profilov.

1. Vyberte položku **Uložiť**.

Uloženie exportu nespustí export okamžite.

Export prebieha s každým [plánovaným obnovením](system.md#schedule-tab). Môžete tiež [exportovať údaje na požiadanie](export-destinations.md#run-exports-on-demand). 
 
V DotDigital teraz nájdete svoje segmenty v [adresároch DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).


## <a name="data-privacy-and-compliance"></a>Ochrana osobných údajov a dodržiavanie súladu s nariadeniami

Keď povolíte prenos údajov spoločnosti DotDigital v službe Dynamics 365 Customer Insights, povoľujete tým prenos údajov mimo hranice súladu so službou Dynamics 365 Customer Insights vrátane potenciálne citlivých údajov, ako sú napríklad osobné údaje. Spoločnosť Microsoft prenesie tieto údaje na váš pokyn, ale vy ste zodpovední za zabezpečenie toho, aby spoločnosť DotDigital plnila všetky prípadné povinnosti týkajúce sa ochrany vašich osobných údajov alebo zabezpečenia. Ďalšie informácie nájdete vo [vyhlásení o ochrane súkromia spoločnosti Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Váš správca služby Dynamics 365 Customer Insights môže túto funkciu kedykoľvek prestať používať odstránením tohto cieľového umiestnenia exportu.


[!INCLUDE [footer-include](includes/footer-banner.md)]
