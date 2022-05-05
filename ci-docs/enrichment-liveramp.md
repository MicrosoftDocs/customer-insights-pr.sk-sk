---
title: Obohatenie údajov identity LiveRamp
description: Obohaťte profily zákazníkov o údaje LiveRamp.
ms.date: 03/02/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 0727818f6df565d9a031966a68d521ae7167e484
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 04/27/2022
ms.locfileid: "8643193"
---
# <a name="enrich-customer-profiles-with-identity-data-from-liveramp-preview"></a>Obohaťte profily zákazníkov o údaje o identite z LiveRamp (ukážka) 

LiveRamp poskytuje deterministické offline rozlíšenie identity a konsolidáciu údajov o zákazníkoch. Môžete namapovať osobné identifikátory vo svojich zákazníckych údajoch do grafu identity AbiliTec a získať AbiliTec ID. Tieto ID potom môžete použiť na lepšie zjednotenie údajov o vašich zákazníkoch. 

## <a name="prerequisites"></a>Požiadavky 

Ak chcete nakonfigurovať obohatenie, musia byť splnené nasledujúce predpoklady: 

- Máte aktívne predplatné LiveRamp. Ak chcete získať predplatné, kontaktujte tím svojho účtu LiveRamp alebo na [dynamics@liveramp.com](mailto:dynamics@liveramp.com) Pre viac informácií.   

- Aktívne predplatné AbiliTec s ID klienta a tajným kódom na prístup k API. Ďalšie informácie nájdete v časti [AbiliTec API Developer Hub](https://developers.liveramp.com/abilitec-api/). 

## <a name="supported-countriesregions"></a>Podporované krajiny/regióny 

V súčasnosti podporujeme obohatenie zákazníckych profilov o údaje LiveRamp iba v Spojených štátoch. 

## <a name="configure-the-enrichment"></a>Konfigurácia obohatenia 

1. Prejdite na **Údaje** > **Obohatenie** a vyberte kartu **Objavovať**. 

1. Vyberte **Obohaťte moje údaje** na **identita** dlaždica. 

   :::image type="content" source="media/liveramp-tile.png" alt-text="Dlaždice identity na stránke prehľadu obohatenia.":::

1. Vyberte si z rozbaľovacieho zoznamu [pripojenie](connections.md). Ak nie je k dispozícii pripojenie, kontaktujte správcu. Ak ste správca, môžete vytvoriť pripojenie výberom **Pridať pripojenie**. Vyberte si **LiveRamp** z rozbaľovacieho zoznamu. 

1. Vyberte **Ďalšie** a vyberte si **Súbor zákazníckych údajov** chcete obohatiť o údaje o identite z LiveRamp. Môžete si vybrať *Zákazník* subjekt na obohatenie všetkých vašich zákazníckych profilov alebo vyberte a *segment* obohatiť iba profily zákazníkov obsiahnuté v tomto segmente. 

1. Vyberte **Ďalšie** a definujte, ktorý typ polí z vašich zjednotených profilov by sa mal použiť na hľadanie zodpovedajúcich údajov o identite z LiveRamp. Aspoň jedno z polí **Meno a adresa**, **·**, alebo **E-mail** sa vyžaduje. 

   > [!TIP]
   > Čím viac kľúčových identifikátorov a polí namapujete, tým väčšia je pravdepodobnosť vyššej miery zhody 

1. Mapujte polia z vášho zjednoteného *Zákazník* entita, ktorá sa použije na porovnávanie s grafom AbiliTec ID LiveRamp. 

   :::image type="content" source="media/liveramp-data-mapping.png" alt-text="Možnosti mapovania údajov pre obohatenie LiveRamp.":::

1. Stlačte možnosť **Ďalej** na vyplnenie mapovania poľa. 

1. Poskytnúť **názov** za obohatenie a **Výstupná entita**. 

1. Stlačte možnosť **Uložiť obohatenie** po preskúmaní vašich možností. 

## <a name="configure-the-connection-for-liveramp"></a>Nakonfigurujte pripojenie pre LiveRamp 

Na to musíte byť správcom [konfigurovať pripojenia](connections.md). Vyberte **Pridať pripojenie** pri konfigurácii obohatenia alebo prejdite na **Admin** > **Spojenia** a vyberte **Nastaviť** na **LiveRamp** dlaždica. 

:::image type="content" source="media/liveramp-connection.png" alt-text="Konfiguračný panel na nastavenie pripojenia k službe LiveRamp AbiliTec.":::

1. Pre **Zobraziť meno**, zadajte názov pripojenia. 

1. Poskytnite platné ID klienta LiveRamp a tajomstvo. 

1. Skontrolujte a poskytnite svoj súhlas pre **Ochranu osobných údajov a dodržiavanie súladu s nariadeniami** výberom začiarkavacieho políčka **Súhlasím**. 

1. Stlačte **Overiť** na overenie konfigurácie. 

1. Ak chcete dokončiť pripojenie, vyberte **Uložiť**. 

## <a name="enrichment-results"></a>Výsledky obohatenia 

Ak chcete spustiť proces obohatenia, vyberte položku Spustiť na paneli príkazov. Môžete tiež nechať systém spustiť obohatenie automaticky ako súčasť a [plánované obnovenie](system.md#schedule-tab). Čas spracovania závisí od veľkosti vašich zákazníckych údajov. 

Po dokončení procesu obohatenia si môžete prezrieť novo obohatené údaje zákazníckych profilov pod **Moje obohatenia**. Ďalej nájdete čas poslednej aktualizácie a počet obohatených profilov. 

Výberom získate prístup k podrobnému zobrazeniu každého obohateného profilu **Pohľad obohatený** údajov. 

## <a name="next-steps"></a>Ďalšie kroky

Stavajte na svojich obohatených údajoch o zákazníkoch. Použite AbiliTec ID na konsolidáciu zákazníckych profilov do osobného zobrazenia. 
[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

## <a name="data-privacy-and-compliance"></a>Ochrana osobných údajov a dodržiavanie súladu s nariadeniami 

Keď povolíte Dynamics 365 Customer Insights na prenos údajov do LiveRamp povolíte prenos údajov mimo hraníc súladu pre Dynamics 365 Customer Insights, vrátane potenciálne citlivých údajov, ako sú Osobné údaje. Spoločnosť Microsoft prenesie takéto údaje na váš pokyn, ale zodpovedáte za to, že LiveRamp spĺňa všetky vaše prípadné povinnosti týkajúce sa ochrany osobných údajov alebo zabezpečenia. Ďalšie informácie nájdete na stránke [Vyhlásenie o ochrane osobných údajov spoločnosti Microsoft](https://go.microsoft.com/fwlink/?linkid=396732). Váš správca služby Dynamics 365 Customer Insights môžete kedykoľvek prestať používať odstránením tohto obohatenia. 


[!INCLUDE [footer-include](includes/footer-banner.md)]
