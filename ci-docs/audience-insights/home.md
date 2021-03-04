---
title: Domovská stránka v prehľadoch cieľových skupín
description: Začnite prezerať aplikáciu na stránke Domov.
ms.date: 01/07/2021
ms.reviewer: nimagen
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 7cc767f5d80b213a4c1bb5b2e8062bd44c15279b
ms.sourcegitcommit: 0260ed244b97c2fd0be5e9a084c4c489358e8d4f
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 02/18/2021
ms.locfileid: "5477060"
---
# <a name="create-a-new-environment"></a>Vytvoriť nové prostredie

## <a name="create-a-trial-environment"></a>Vytvorenie skúšobného prostredia

Môžete sa zaregistrovať na skúšku na [skúšobnej registračnej stránke](https://dynamics.microsoft.com/get-started/free-trial/?appname=customerinsights). 

> [!NOTE]
> Platnosť skúšky vyprší po 30 dňoch.

1. Vyberte možnosť **Zaregistrujte sa a získajte bezplatnú skúšobnú verziu** a vyberte **Zaregistrovať sa**.

1. Zadajte svoju pracovnú alebo školskú e-mailovú adresu, povedzte nám o sebe viac a vyberte **Ďalej**.

   :::image type="content" source="media/trial-signup-dialog.png" alt-text="Dialógové okno na registráciu skúšobnej inštancie":::

1. Zadajte **Názov** pre vaše nové prostredie. 

1. Vyberte typ skúšobnej verzie.

1. Vyberte **Oblasť** pre svoje prostredie.

1. Voliteľne pre správcov organizácie Dynamics 365: Vyberte **Pokročilé nastavenia** a uveďte adresu URL svojej organizácie na použitie funkcií predikcie, ako je odchod zákazníkov.

1. Stlačte možnosť **Vytvoriť**. 

Po vytvorení prostredia sa zobrazí **Ukážkové** prostredie, ktoré vám umožní preskúmať aplikáciu pomocou fiktívnych údajov. Vzorové údaje môžete zmeniť tak, aby zodpovedali vášmu odvetviu. Vyberte ikonu **Nastavenia** v hlavičke a vyberte **Nastavenia demoverzie**. Ďalej môžete zmeniť vizuálnu tému. 

[Prejdete do prostredia](#switch-environments), ktoré ste vytvorili počas procesu registrácie na prácu s vašimi vlastnými údajmi.

## <a name="create-a-new-production-or-sandbox-environment"></a>Vytvorenie nového produkčného alebo testovacieho prostredia

Vo svojom prostredí vyberte nástroj na výber **Prostredia** v hlavičke aplikácie a vyberte **Nový**.

Postupujte podľa pokynov, akoby ste [vytvárali testovacie prostredie](#create-a-trial-environment). Predvolene sa údaje ukladajú v spravovanom dátovom jazere Customer Insights. Pri výbere **Pokročilé nastavenia** získate ďalšiu možnosť na uloženie údajov do vlastného Azure Data Lake. Zadajte názov svojho účtu a kľúč účtu na nadviazanie pripojenia k vášmu Azure Data Lake. 

> [!IMPORTANT]
> Uložením údajov do vašej služby Azure Data Lake Storage súhlasíte s tým, že údaje budú prenesené a uložené v príslušnej geografickej oblasti pre dané konto úložiska v Azure, ktoré sa môže líšiť od oblasti, v ktorej sú uložené údaje služby Dynamics 365 Customer Insights. [Ďalšie informácie nájdete v centre dôveryhodnosti spoločnosti Microsoft.](https://www.microsoft.com/trust-center)

## <a name="explore-the-home-page"></a>Preskúmanie domovskej stránky

Môžete [získať prístup k prehľadom o cieľových skupinách z Dynamics 365 Customer Insights](https://home.ci.ai.dynamics.com/) na nasledujúcej adrese URL: [https://home.ci.ai.dynamics.com/](https://home.ci.ai.dynamics.com/).
**Domovská** stránka zobrazuje prehľad segmentov, mier a údajov o obohatení (ak sú nakonfigurované) po dokončení [mapovania](map-entities.md), [párovania](match-entities.md) a [zlučovania](merge-entities.md).

> [!div class="mx-imgBorder"] 
> ![Prehľady na domovskej stránke](media/home-page-insights.png "Prehľady na domovskej stránke")

Pod **Posledné segmenty** uvidíte skupiny zákazníkov na základe demografických, behaviorálnych alebo transakčných atribútov, ktoré ste definovali. [Vytváranie segmentov](segments.md) vám pomôže zoskupiť zákaznícku základňu a lepšie zacieliť vaše obchodné aktivity.

**Nedávne miery** zobrazujú dlaždice s [kľúčovými ukazovateľmi výkonu (KPI)](measures.md) ktoré ste definovali. Napríklad priemerná pravdepodobnosť odchodu zákazníka alebo priemerné online výdavky na zákazníka.

Sekcia **Nedávne obohatenia** uvádza výsledky behov obohacovania, ktoré skončili nedávno. [Obohatenia](enrichment-hub.md) pridávajú informácie o vašej zákazníckej základni. Napríklad porozumením záujmov a značkám, ku ktorým majú vzťah.

## <a name="switch-environments"></a>Prepnutie prostredí

Ak chcete zmeniť prostredie, vyberte ovládací prvok **prostredia** v pravom hornom rohu stránky.

> [!div class="mx-imgBorder"] 
> ![Prepnúť prostredie](media/home-page-environment-switcher.png "Prepnúť prostredie")

Správcovia môžu vytvárať a spravovať [viaceré prostredia](manage-environments.md). Udržiavanie viacerých prostredí môže byť užitočné, ak napríklad vaša organizácia pôsobí na medzinárodnej úrovni a potrebujete oddeliť údaje a informácie rôznymi spôsobmi.

## <a name="next-step"></a>Nasledujúci krok

Ak chcete na svojej domovskej stránke zobraziť svoje vlastné prehľady, musíte najskôr [pridať zdroje údajov](data-sources.md) a [zjednotiť](data-unification.md) vaše údaje na vytvorenie profilov zákazníkov.


[!INCLUDE[footer-include](../includes/footer-banner.md)]