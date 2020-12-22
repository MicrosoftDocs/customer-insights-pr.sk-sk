---
title: Domovská stránka v prehľadoch cieľových skupín
description: Začnite prezerať aplikáciu na stránke Domov.
ms.date: 09/30/2020
ms.reviewer: nimagen
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: bd16966eabb126d9c9945ededc53273df02c3369
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406920"
---
# <a name="create-a-new-environment"></a>Vytvoriť nové prostredie

## <a name="create-a-trial-environment"></a>Vytvorenie skúšobného prostredia

Môžete sa zaregistrovať na skúšku na [skúšobnej registračnej stránke](https://dynamics.microsoft.com/get-started/free-trial/?appname=customerinsights). 

> [!NOTE]
> Platnosť skúšky vyprší po 30 dňoch.

1. Vyberte možnosť **Zaregistrujte sa a získajte bezplatnú skúšobnú verziu** a vyberte **Zaregistrovať sa**.

1. Zadajte svoju pracovnú alebo školskú e-mailovú adresu, povedzte nám o sebe viac a vyberte **Ďalej**.

1. Zadajte **Názov** pre vaše nové prostredie. 

1. Vyberte typ skúšobnej verzie.

1. Vyberte **Oblasť** pre svoje prostredie.

1. Voliteľne pre správcov organizácie Dynamics 365: Vyberte **Pokročilé nastavenia** a uveďte adresu URL svojej organizácie na použitie funkcií predikcie, ako je odchod zákazníkov.

1. Stlačte možnosť **Vytvoriť**. 

Po vytvorení prostredia sa zobrazí **Ukážkové** prostredie, ktoré vám umožní preskúmať aplikáciu pomocou fiktívnych údajov. Vzorové údaje môžete zmeniť tak, aby zodpovedali vášmu odvetviu. Vyberte ikonu **Nastavenia** v hlavičke a vyberte **Nastavenia demoverzie**. Ďalej môžete zmeniť vizuálnu tému. 

[Prejdete do prostredia](#change-between-environments), ktoré ste vytvorili počas procesu registrácie na prácu s vašimi vlastnými údajmi.

## <a name="create-a-new-production-or-sandbox-environment"></a>Vytvorenie nového produkčného alebo testovacieho prostredia

Vo svojom prostredí vyberte ikonu **Nastavenia** v hlavičke a vyberte **Nové prostredie**.

Postupujte podľa pokynov, akoby ste [vytvárali testovacie prostredie](#create-a-trial-environment). Pri výbere **Pokročilé nastavenia** získate ďalšiu možnosť na uloženie údajov do vlastného Azure Data Lake. Zadajte názov svojho účtu a kľúč účtu na nadviazanie pripojenia k vášmu Azure Data Lake. Predvolene sa údaje ukladajú v spravovanom dátovom jazere Customer Insights.

> [!IMPORTANT]
> Uložením údajov do vašej služby Azure Data Lake Storage súhlasíte s tým, že údaje budú prenesené a uložené v príslušnej geografickej oblasti pre dané konto úložiska v Azure, ktoré sa môže líšiť od oblasti, v ktorej sú uložené údaje služby Dynamics 365 Customer Insights. [Ďalšie informácie nájdete v centre dôveryhodnosti spoločnosti Microsoft.](https://www.microsoft.com/trust-center)

## <a name="explore-the-home-page"></a>Preskúmanie domovskej stránky

Môžete [navštíviť vaše prostredie služby Customer Insights](https://home.ci.ai.dynamics.com/) na nasledujúcej adrese URL: [https://home.ci.ai.dynamics.com/](https://home.ci.ai.dynamics.com/).
Stránka **Domov** zobrazuje prehľad zákazníckej základne a kľúčové metriky na sledovanie stavu vašej firmy.

> [!div class="mx-imgBorder"] 
> ![Prehľady na domovskej stránke](media/home-page-insights.png "Prehľady na domovskej stránke")

Pod **Posledné segmenty** uvidíte skupiny zákazníkov na základe demografických, behaviorálnych alebo transakčných atribútov, ktoré ste definovali. [Vytváranie segmentov](segments.md) pomáha lepšie zacieliť vaše obchodné aktivity.

**Nedávne miery** ukazuje dlaždice s [mierami](measures.md). Miery sú kľúčové ukazovatele výkonu (KPI), ktoré ste definovali. Napríklad priemerná pravdepodobnosť odchodu zákazníkov alebo priemerné online výdavky na zákazníka.

Sekcia **Nedávne obohatenia** uvádza výsledky behov obohacovania, ktoré skončili nedávno. Obohatenia pridávajú informácie o vašej zákazníckej základni. Napríklad porozumením záujmov a značkám, ku ktorým majú vzťah. Tieto informácie je možné odomknúť pomocou funkcií [obohatenia](enrichment-microsoft-graph.md), po dokončení fáz [mapovania](map-entities.md), [zosúlaďovania](match-entities.md) a [zlúčenia](merge-entities.md).

## <a name="change-between-environments"></a>Zmena medzi prostrediami

Po nastavení a konfigurácii [zdrojov údajov](data-sources.md) budete chcieť prejsť z ukážkového prostredia na živé prostredie. Používanie produkčného prostredia vám umožňuje pracovať s vašimi vlastnými údajmi o zákazníkoch. Ak chcete zmeniť prostredie, vyberte ovládací prvok **prostredia** v pravom hornom rohu stránky.

> [!div class="mx-imgBorder"] 
> ![Prepnúť prostredie](media/home-page-environment-switcher.png "Prepnúť prostredie")

Správcovia môžu vytvárať a spravovať [viaceré prostredia](manage-environments.md). Udržiavanie viacerých prostredí môže byť užitočné, ak napríklad vaša organizácia pôsobí na medzinárodnej úrovni a potrebujete oddeliť údaje a informácie rôznymi spôsobmi.

## <a name="next-step"></a>Nasledujúci krok

Ak chcete na svojej domovskej stránke zobraziť svoje vlastné prehľady, musíte najskôr [pridať zdroje údajov](data-sources.md) a [zjednotiť](data-unification.md) vaše údaje na vytvorenie profilov zákazníkov.
