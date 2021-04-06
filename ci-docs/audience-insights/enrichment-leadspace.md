---
title: Obohatenie profilov spoločností pomocou obohatenia tretej strany Leadspace
description: Všeobecné informácie o obohatení pomocou obohatenia tretej stranou Leadspace.
ms.date: 11/24/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 41c56aece043c2d7658fd2655713e1e98775edec
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597668"
---
# <a name="enrichment-of-company-profiles-with-leadspace-preview"></a>Obohatenie profilov spoločnosti pomocou Leadspace (náhľad)

Leadspace je spoločnosť zaoberajúca dátovou vedou, ktorá poskytuje platformu B2B Customer Data. Umožňuje zákazníkom so zjednotenými zákazníckymi profilmi pre spoločnosti obohacovať svoje údaje. Obohatenia zahŕňajú ďalšie atribúty, ako napríklad veľkosť, umiestnenie, odvetvie spoločnosti a ďalšie.

## <a name="prerequisites"></a>Predpoklady

Na konfiguráciu Leadspace musia byť splnené nasledujúce predpoklady:

- Máte aktívnu licenciu pre Leadspace a „večný kľúč“ (označovaný ako **token pre Leadspace**). Kontaktujte priamo [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) pre podrobnosti o ich produkte.
- Máte povolenia roly [Správca](permissions.md#administrator).
- Máte [zjednotené profily zákazníkov](customer-profiles.md) pre spoločnosti.

## <a name="configuration"></a>Konfigurácia

1. V prehľadoch cieľových skupín prejdite na **Údaje** > **Obohatenie**.

1. Vyberte **Obohatiť moje údaje** na dlaždici Leadspace.

   :::image type="content" source="media/leadspace-tile.png" alt-text="Snímka obrazovky dlaždice Leadspace.":::

1. Vyberte položku **Začíname** a potom zadajte aktívny **token pre Leadspace** (večný kľúč). Skontrolujte a poskytnite svoj súhlas pre **Ochranu osobných údajov a dodržiavanie súladu s nariadeniami** výberom začiarkavacieho políčka **Súhlasím**. Potvrďte obidva vstupy výberom položky **Pripojiť k Leadspace**.

1. Vyberte **Mapovanie údajov** a vyberte množinu údajov, ktorú chcete obohatiť o údaje spoločnosti z programu Leadspace. Môžete zvoliť entitu *Zákazník*, aby ste obohatili všetky svoje zákaznícke profily, alebo vyberte entitu segmentu, aby ste obohatili iba profily zákazníkov obsiahnuté v danom segmente.

   :::image type="content" source="media/enrichment-leadspace-select-segment.png" alt-text="Vyberte si medzi profilom zákazníka a obohatením segmentu.":::

1. Kliknite na **Ďalej** a definujte, ktoré polia z vašich zjednotených profilov sa majú použiť na vyhľadanie zodpovedajúcich údajov spoločnosti z Leadspace. Pole **Názov spoločnosti** je povinné. Pre vyššiu presnosť zhody možno pridať až dve ďalšie polia, **Webová lokalita spoločnosti** a **Sídlo spoločnosti**.

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="Tabla mapovania polí Leadspace.":::
   
1. Výberom položky **Použiť** dokončíte mapovanie polí.

1. Vyberte **Spustiť** na obohatenie profilov spoločnosti. Dĺžka trvania obohacovania závisí od počtu zjednotených profilov zákazníkov.

## <a name="enrichment-results"></a>Výsledky obohatenia

Po aktualizácii obohatenia si môžete prezrieť novo obohatené údaje spoločnosti v časti [Moje obohatenia](enrichment-hub.md). Nájdete čas poslednej aktualizácie a počet obohatených profilov.

Môžete získať podrobné zobrazenie každého obohateného profilu výberom **Zobraziť obohatené údaje**.

Ďalšie informácie sa dozviete v časti [API Leadspace](https://support.leadspace.com/hc/en-us/sections/201997649-API).

## <a name="next-steps"></a>Ďalšie kroky

Stavajte na svojich obohatených údajoch o zákazníkoch. Vytvárajte [segmenty](segments.md), [miery](measures.md) a dokonca [exportujte údaje](export-destinations.md) na poskytovanie prispôsobenej používateľskej skúsenosti svojim zákazníkom.

## <a name="data-privacy-and-compliance"></a>Ochrana osobných údajov a dodržiavanie súladu s nariadeniami

Keď povolíte prenos údajov spoločnosti Leadspace v službe Dynamics 365 Customer Insights, povoľujete tým prenos údajov mimo hranice súladu so službou Dynamics 365 Customer Insights vrátane potenciálne citlivých údajov, ako sú napríklad osobné údaje. Spoločnosť Microsoft prenesie tieto údaje na váš pokyn, ale vy ste zodpovední za zabezpečenie toho, aby spoločnosť Leadspace plnila všetky prípadné povinnosti týkajúce sa ochrany vašich osobných údajov alebo zabezpečenia. Ďalšie informácie nájdete vo [vyhlásení o ochrane súkromia spoločnosti Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Váš správca služby Dynamics 365 Customer Insights môžete kedykoľvek prestať používať odstránením tohto obohatenia.


[!INCLUDE[footer-include](../includes/footer-banner.md)]