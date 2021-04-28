---
title: Obohatenie pomocou obohatenia tretej strany Experian
description: Všeobecné informácie o obohatení pomocou obohatenia tretej stranou Experian.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 9cf2a7fa18ecc022ea67f6829f52381ad59f3172
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896392"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a>Obohatenie profilov zákazníkov o demografické údaje od spoločnosti Experian (ukážka)

Experian je svetový líder v oblasti marketingových služieb a zisťovania kreditu spotrebiteľov a firiem. So službami obohacovania údajov od spoločnosti Experian môžete hlbšie porozumieť svojim zákazníkom obohatením profilov svojich zákazníkov o demografické údaje, ako sú veľkosť domácnosti, príjem a ďalšie.

## <a name="prerequisites"></a>Predpoklady

Ak chcete nakonfigurovať Experian, musia byť splnené nasledujúce predpoklady:

- Máte aktívne predplatné Experian. Ak chcete získať predplatné, [kontaktujte Experian](https://www.experian.com/marketing-services/contact) priamo. [Ďalšie informácie o obohacovaní údajov Experian](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).

- Pripojenie Experian už nakonfiguroval správca *alebo* máte povolenia [správcu](permissions.md#administrator). Pre svoj účet Secure Transport (ST) s povoleným SSH, ktorý pre vás spoločnosť Experian vytvorila, potrebujete tiež ID používateľa, ID strany a Číslo modelu.

## <a name="configure-the-enrichment"></a>Konfigurácia obohatenia

1. Prejdite na **Údaje** > **Obohatenie** a vyberte kartu **Objavovať**.

1. Vyberte **Obohatiť moje údaje** na dlaždici Experian.

   > [!div class="mx-imgBorder"]
   > ![Dlaždica Experian](media/experian-tile.png "Dlaždica Experian")
   > 

1. V rozbaľovacej ponuke stlačte možnosť [pripojenie](connections.md). Ak nie je k dispozícii pripojenie, kontaktujte správcu. Ak ste správca, pripojenie môžete vytvoriť výberom možnosti **Pridať pripojenie** a v rozbaľovacej ponuke Experian stlačte možnosť Vlastný import SFTP. 

1. Vyberte **Pripojiť sa k Experian** na potvrdenie zvoleného spojenia.

1.  Stlačte možnosť **Ďalej** a vyberte **Množina údajov o zákazníkoch** na obohatenie o demografické údaje z Experian. Môžete zvoliť entitu **Zákazník**, aby ste obohatili všetky svoje zákaznícke profily, alebo vyberte entitu segmentu, aby ste obohatili iba profily zákazníkov obsiahnuté v danom segmente.

    :::image type="content" source="media/enrichment-Experian-configuration-customer-data-set.png" alt-text="Snímka obrazovky pri výbere množiny údajov o zákazníkoch.":::

1. Stlačte možnosť **Ďalej** a definujte, ktorý typ polí z vašich zjednotených profilov sa má použiť na vyhľadanie zodpovedajúcich demografických údajov z Experian. Aspoň jedno z polí **Meno a adresa**, **Telefón** alebo **Email** je požadované. Pre vyššiu presnosť zhody je možné pridať až dve ďalšie polia. Tento výber ovplyvní mapovacie polia, ku ktorým máte prístup v ďalšom kroku.

    > [!TIP]
    > Viac kľúčových identifikačných atribútov zaslaných spoločnosti Experian pravdepodobne prinesie vyššiu mieru zhody.

1. Stlačte možnosť **Ďalej** na spustenie mapovania poľa.

1. Definujte, ktorý typ polí z vašich zjednotených profilov sa má použiť na vyhľadanie zodpovedajúcich demografických údajov z Experian. Požadované polia sú označené.

1. Uveďte názov obohatenia a názov výstupnej entity.

1. Stlačte možnosť **Uložiť obohatenie** po preskúmaní vašich možností.

## <a name="configure-the-connection-for-experian"></a>Nakonfigurujte pripojenie pre Experian 

Na konfiguráciu pripojení musíte byť administrátor. Stlačte možnosť **Pridať pripojenie** pri konfigurácii obohatenia *alebo* prejdite na **Správca** > **Pripojenia** a vyberte **Nastaviť** na dlaždici Experian.

1. Vyberte položku **Začíname**.

1. Zadajte názov pripojenia do boxu **Zobrazovaný názov**.

1. Zadajte platné ID používateľa, ID strany a číslo modelu pre váš účet Experian Secure Transport.

1. Skontrolujte a poskytnite svoj súhlas pre **Ochrana osobných údajov a dodržiavanie súladu s nariadeniami** označením začiarkavacieho políčka **Súhlasím**.

1. Stlačte **Overiť** na overenie konfigurácie.

1. Po dokončení overenia stlačte možnosť **Uložiť**.
   
   :::image type="content" source="media/enrichment-Experian-connection.png" alt-text="Konfiguračná tabla pripojenia Experian":::

## <a name="enrichment-results"></a>Výsledky obohatenia

Proces obohatenia spustíte výberom položky **Spustiť** z panela príkazov. Môžete tiež nechať systém, aby obohatenie spustil automaticky ako súčasť a [plánovaného obnovenia](system.md#schedule-tab). Doba spracovania bude závisieť od veľkosti vašich zákazníckych údajov a procesov obohacovania nastavených pre váš účet spoločnosťou Experian.

Po dokončení procesu obohacovania môžete skontrolovať údaje o nových obohatených zákazníckych profiloch v časti **Moje obohatenia**. Ďalej nájdete čas poslednej aktualizácie a počet obohatených profilov.

Môžete získať podrobné zobrazenie každého obohateného profilu výberom **Zobraziť obohatené údaje**.

## <a name="next-steps"></a>Ďalšie kroky

Stavajte na svojich obohatených údajoch o zákazníkoch. Vytvárajte [segmenty](segments.md), [miery](measures.md) a dokonca [exportujte údaje](export-destinations.md) na poskytovanie prispôsobenej používateľskej skúsenosti svojim zákazníkom.

## <a name="data-privacy-and-compliance"></a>Ochrana osobných údajov a dodržiavanie súladu s nariadeniami

Keď povolíte prenos údajov spoločnosti Experian v službe Dynamics 365 Customer Insights, povoľujete tým prenos údajov mimo hranice súladu so službou Dynamics 365 Customer Insights vrátane potenciálne citlivých údajov, ako sú napríklad osobné údaje. Spoločnosť Microsoft prenesie tieto údaje na váš pokyn, ale vy ste zodpovední za zabezpečenie toho, aby spoločnosť Experian plnila všetky prípadné povinnosti týkajúce sa ochrany vašich osobných údajov alebo zabezpečenia. Ďalšie informácie nájdete vo [vyhlásení o ochrane súkromia spoločnosti Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Váš správca služby Dynamics 365 Customer Insights môžete kedykoľvek prestať používať odstránením tohto obohatenia.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
