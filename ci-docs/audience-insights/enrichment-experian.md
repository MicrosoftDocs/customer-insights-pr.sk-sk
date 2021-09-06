---
title: Obohatenie pomocou tretej strany Experian
description: Všeobecné informácie o obohatení pomocou tretej strany Experian.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: c54f6a00cb28b0ab11716c02aa8761dfa382f07e3360183b5d38b9720e890c21
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 08/10/2021
ms.locfileid: "7032639"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a>Obohaťte profily zákazníkov o demografické údaje od spoločnosti Experian (verzia Preview)

Experian je svetovým lídrom v oblasti vykazovania spotrebiteľských a obchodných úverov a marketingových služieb. So službami obohatenia údajov spoločnosti Experian môžete lepšie porozumieť svojim zákazníkom tým, že obohatíte ich zákaznícke profily o demografické údaje, ako je veľkosť domácnosti, príjem a podobne.

## <a name="prerequisites"></a>Predpoklady

Ak chcete nakonfigurovať Experian, musia byť splnené nasledujúce podmienky:

- Mať aktívne predplatné služby Experian. Ak chcete získať predplatné, [kontaktujte priamo spoločnosť Experian](https://www.experian.com/marketing-services/contact). [Získajte ďalšie informácie obohatení údajov Experian](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).

- Pripojenie Experian už nakonfiguroval správca *alebo* máte povolenia [správcu](permissions.md#administrator). Potrebujete tiež ID používateľa, ID strany a číslo modelu pre svoj účet Secure Transport (ST) s povoleným SSH, ktoré vám Experian vytvorí.

## <a name="supported-countriesregions"></a>Podporované krajiny/regióny

V súčasnosti podporujeme obohacovanie profilov zákazníkov iba v Spojených štátoch.

## <a name="configure-the-enrichment"></a>Konfigurácia obohatenia

1. Prejdite na **Údaje** > **Obohatenie** a vyberte kartu **Objavovať**.

1. Vyberte možnosť **Obohatiť moje údaje** na dlaždici Experian.

   > [!div class="mx-imgBorder"]
   > ![Experian dlaždica.](media/experian-tile.png "Experian tile")
   > 

1. Vyberte si z rozbaľovacieho zoznamu [pripojenie](connections.md). Ak nie je k dispozícii pripojenie, kontaktujte správcu. Ak ste správca, pripojenie môžete vytvoriť výberom možnosti **Pridať pripojenie** a následne položky Experian z rozbaľovacieho zoznamu. 

1. Výberom možnosti **Pripojiť k Experian** potvrdíte výber pripojenia.

1.  Vyberte možnosť **Ďalej** a vyberte si **množinu údajov zákazníkov**, ktorú chcete obohatiť o demografické údaje od spoločnosti Experian. Môžete zvoliť entitu **Zákazník**, aby ste obohatili všetky svoje zákaznícke profily, alebo vyberte entitu segmentu, aby ste obohatili iba profily zákazníkov obsiahnuté v danom segmente.

    :::image type="content" source="media/enrichment-Experian-configuration-customer-data-set.png" alt-text="Snímka obrazovky pri výbere množiny údajov o zákazníkoch.":::

1. Vyberte možnosť **Ďalej** a definujte, ktorý typ polí z vašich zjednotených profilov sa má použiť na vyhľadanie zodpovedajúcich demografických údajov od spoločnosti Experian. Aspoň jedno z polí **Meno a adresa**, **Telefón** alebo **Email** je požadované. Pre vyššiu presnosť zhody je možné pridať až dve ďalšie polia. Tento výber ovplyvní mapovacie polia, ku ktorým máte prístup v ďalšom kroku.

    > [!TIP]
    > Viac kľúčových atribútov identifikátora odoslaných spoločnosti Experian pravdepodobne prinesie vyššiu mieru zhody.

1. Stlačte možnosť **Ďalej** na spustenie mapovania poľa.

1. Definujte, ktorý typ polí z vašich zjednotených profilov sa má použiť na vyhľadanie zodpovedajúcich demografických údajov od spoločnosti Experian. Požadované polia sú označené.

1. Uveďte názov obohatenia a názov výstupnej entity.

1. Stlačte možnosť **Uložiť obohatenie** po preskúmaní vašich možností.

## <a name="configure-the-connection-for-experian"></a>Konfigurácia pripojenia pre Experian 

Na konfiguráciu pripojení musíte byť administrátor. Vyberte možnosť **Pridať pripojenie** pri konfigurácii obohatenia *alebo* prejdite na položku **Správca** > **Pripojenia** a vyberte možnosť **Nastaviť** na dlaždici Experian.

1. Vyberte položku **Začíname**.

1. Zadajte názov pripojenia do boxu **Zobrazovaný názov**.

1. Zadajte platné ID používateľa, ID strany a číslo modelu pre svoj účet Experian Secure Transport.

1. Skontrolujte a poskytnite svoj súhlas pre **Ochranu osobných údajov a dodržiavanie súladu s nariadeniami** výberom možnosti **Súhlasím**.

1. Stlačte **Overiť** na overenie konfigurácie.

1. Po dokončení overenia stlačte možnosť **Uložiť**.
   
   :::image type="content" source="media/enrichment-Experian-connection.png" alt-text="Tabla konfigurácie pripojenia Experian.":::

## <a name="enrichment-results"></a>Výsledky obohatenia

Proces obohatenia spustíte výberom položky **Spustiť** z panela príkazov. Môžete tiež nechať systém, aby obohatenie spustil automaticky ako súčasť a [plánovaného obnovenia](system.md#schedule-tab). Čas spracovania bude závisieť od rozsahu vašich zákazníckych údajov a procesov obohacovania nastavených pre váš účet spoločnosťou Experian.

Po dokončení procesu obohacovania môžete skontrolovať údaje o nových obohatených zákazníckych profiloch v časti **Moje obohatenia**. Ďalej nájdete čas poslednej aktualizácie a počet obohatených profilov.

Môžete získať podrobné zobrazenie každého obohateného profilu výberom **Zobraziť obohatené údaje**.

## <a name="next-steps"></a>Ďalšie kroky

Stavajte na svojich obohatených údajoch o zákazníkoch. Vytvárajte [segmenty](segments.md) a [opatrenia](measures.md), a dokonca [exportujte údaje](export-destinations.md), aby ste mohli poskytovať svojim zákazníkom zážitky šité na mieru.

## <a name="data-privacy-and-compliance"></a>Ochrana osobných údajov a dodržiavanie súladu s nariadeniami

Keď povolíte službe Dynamics 365 Customer Insights, aby prenášala údaje spoločnosti Experian, povoľujete tým aj prenos údajov mimo hranice súladu so službou Dynamics 365 Customer Insights vrátane potenciálne citlivých údajov, ako sú napríklad osobné údaje. Microsoft prenesie tieto údaje na váš pokyn, ale vy ste zodpovední za zabezpečenie toho, aby Experian spĺňal všetky záväzky týkajúce sa ochrany vášho súkromia alebo bezpečnosti. Ďalšie informácie nájdete vo [vyhlásení o ochrane súkromia spoločnosti Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Váš správca služby Dynamics 365 Customer Insights môžete kedykoľvek prestať používať odstránením tohto obohatenia.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
