---
title: Vytvoriť a nakonfigurovať skúšúbnú licenciu služby Customer Insights
description: Postup získania skúšobnej licencie predplatného služby Dynamics 365 Customer Insights a jej konfigurácie.
ms.date: 07/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: f038dedd369ac9e623146b66528efa87c47a8c23769037d8709fa9b804a0b723
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 08/10/2021
ms.locfileid: "7035434"
---
# <a name="set-up-a-trial-environment"></a>Nastavenie testovacieho prostredia 

Testovacia verzia služby Dynamics 365 Customer Insights vám umožní kontrolovať hlavné možnosti a zistiť viac o rôznych funkciách. Testovacie predplatné bude po skončení platnosti odstránené. Testovacie prostredia vytvárajú samostatní používatelia, ktorí sa súčasne stanú správcom tohto prostredia. Majú oprávnenie pozývať ďalších používateľov do svojho testovacieho prostredia a konfigurovať rozličné funkcie.

## <a name="create-a-trial-environment"></a>Vytvorenie skúšobného prostredia

Môžete sa zaregistrovať na skúšku na [skúšobnej registračnej stránke](https://dynamics.microsoft.com/get-started/free-trial/?appname=customerinsights). 

1. Vyberte možnosť **Zaregistrujte sa a získajte bezplatnú skúšobnú verziu** a vyberte **Zaregistrovať sa**.

1. Zadajte svoju pracovnú alebo školskú e-mailovú adresu, povedzte nám viac o sebe a označte položku **Začíname**.

   :::image type="content" source="media/trial-signup-dialog.png" alt-text="Dialógové okno na registráciu skúšobnej inštancie":::

1. Skontrolujte zmluvné podmienky a potom ich potvrďte označením položky **Pokračovať**.

1. Zadajte **Názov** pre vaše nové prostredie. 

1. Nastavte **typ** prostredia ako **testovacie**.

1. V poli **Vyberte demoverziu odvetvia** môžete vybrať množinu údajov špecifickú pre dané odvetvie. [Demoverziu odvetvia môžete zmeniť aj](#use-industry-specific-demo-data-sets-in-audience-insights) neskôr a začať s predvoleným súborom údajov.

1. Vyberte **Oblasť** pre svoje prostredie.

1. Ak ste správcom organizácie Dynamics 365, môžete vybrať možnosť **Pokročilé nastavenia** a zadať adresu URL svojej organizácie, aby ste tak mohli používať funkcie predikcie, ako napríklad predpovedanie odchodu zákazníkov. 

1. Vyberte položku **Vytvoriť**. 

Dokončenie nastavenia prostredia trvá chvíľu. Po dokončení budete presmerovaní na demoverziu prostredia alebo odvetvia, ktoré ste si vybrali v predchádzajúcom kroku. Teraz môžete aplikáciu preskúmať pomocou ukážkových údajov určených iba na čítanie. Ak chcete do prostredia pridať svoje vlastné údaje, pozrite si časť [Vytvárajte ukážkové údaje špecifické pre scenár vo svojom vlastnom prostredí](#create-scenario-specific-demo-data-in-your-own-environment).

:::image type="content" source="media/trial-environment.png" alt-text="Snímka obrazovky novovytvoreného testovacieho prostredia.":::

## <a name="use-industry-specific-demo-data-sets-in-audience-insights"></a>V prehľadoch o cieľovej skupine použite ukážkové údaje špecifické pre dané odvetvie

Pripojenie skutočných zdrojov údajov je jedným z dôležitých krokov pri využívaní schopností produktu Customer Insights. Ak chcete vyskúšať funkcie bez zasahovania do vlastných údajov, môžete voliteľne použiť ukážkové údaje špecifické pre dané odvetvie. K dispozícii máte niekoľko súborov ukážkových údajov pre tieto odvetvia: 

-   Automobily
-   Bankovníctvo
-   Spotrebný tovar
-   Vládna organizácia
-   Zdravotníctvo
-   Pohostinnosť
-   Poistenie
-   Výroba
-   Profesionálne služby
-   Maloobchod

### <a name="see-industry-specific-demo-data-in-trials"></a>Pozrite ukážkové údaje špecifické pre dané odvetvie v skúšobných verziách

Čo sa týka verzie Customer Insights určenej iba na čítanie prispôsobenej konkrétnemu odvetviu alebo scenáru, začnite v testovacom prostredí. 
 
1.  V prehľadoch cieľovej skupiny si v nástroji na výber prostredia vyberte **Testovacie** prostredie.

2.  Pri položke **Domov** si zvoľte možnosť z rozbaľovacej ponuky Vybrať demoverziu odvetvia.

:::image type="content" source="media/trial-select-industry-demo.png" alt-text="Vyberte si odvetvie pre testovacie prostredie.":::

### <a name="create-scenario-specific-demo-data-in-your-own-environment"></a>Vytvárajte ukážkové údaje špecifické pre scenár vo svojom vlastnom prostredí

Ako správca vytvorte nové prostredie výberom prostredia v hlavičke aplikácie. V novom prostredí môžete nakonfigurovať svoje vlastné zdroje údajov a nastaviť aplikáciu podľa svojich požiadaviek. 

1.  V prehľadoch cieľových skupín prejdite na **Údaje** > **Zdroje údajov**.

2.  Ak chcete importovať svoje vlastné zdroje údajov, prejdite do časti [sprievodca prijatím údajov](data-sources.md).     
   Ak dávate prednosť práci so vzorovými údajmi, ktoré vám umožňujú vyskúšať si prijímanie údajov, môžete vo svojom prostredí prijať ukážkové údaje z tohto odvetvia. Vyberte možnosť **Import z služby Datahub** a postupujte podľa dole uvedeného postupu.

3.  Vyberte kartu odvetvia, ktoré spĺňa váš scenár. 

4.  Skontrolujte a v prípade potreby aktualizujte navrhovaný názov zdroja údajov. 

5.  Vzorové údaje prijmete výberom položky **Ďalšie**. 

Teraz môžete použiť prijaté údaje a prispôsobiť službu Customer Insights tak, aby vyhovovala vášmu scenáru. Ak chcete vidieť prostredie špecifické pre požité ukážkové údaje, v nástroji na výber prostredia zvoľte možnosť **<Industry>Ukážka**.

## <a name="limitations-in-trials"></a>Obmedzenia v skúšobných verziách

- Skúšobné verzie sú štandardne aktívne 30 dní. Môžete ich však predĺžiť po 23. dni, ak sa prihlásite do skúšobnej verzie.
- Počas skúšobného obdobia nie je možné používať vlastné konto úložiska Azure Data Lake a ukladať tam výstupné údaje. Údaje však môžete prijímať z konta úložiska Data Lake.
- V prostredí Dataverse môžete do pamäte ukladať až 3 GB údajov. Prostredie sa automaticky zriadi pri spustení skúšobnej verzie služby Customer Insights.

## <a name="copy-data-from-a-trial-to-a-paid-subscription"></a>Skopírujte údaje zo skúšobnej verzie do plateného predplatného

Vo všeobecnosti odporúčame pri inovácii na platenú verziu služby Customer Insights začať s novými údajmi. 

Voliteľne môžete svoje údaje skopírovať zo skúšobného prostredia, pokiaľ si zakúpite službu Customer Insights. Ak chcete migrovať nastavenia zo skúšobného prostredia do plateného prostredia, je potrebné, aby ste boli správcom skúšobnej verzie služby Customer Insights a taktiež globálnym správcom vášho nájomníka služby Microsoft 365 alebo správcom služby Dynamics 365 vo vašej organizácii. 

Po prvom prihlásení do platenej inštancie služby Customer Insights sa zobrazí výzva na vytvorenie nového prostredia. Pri tomto procese máte možnosť sa rozhodnúť, či chcete skopírovať konfiguráciu z už existujúceho prostredia a migrovať z neho väčšinu nastavení. Ak máte hore uvedené povolenia, v tomto zozname sa zobrazí dané skúšobné prostredie. Ďalšie údaje nájdete v časti [Skopírujte konfiguráciu prostredia](manage-environments.md#copy-the-environment-configuration).

## <a name="next-steps"></a>Ďalšie kroky

Prečítajte si nasledujúce články, v ktorých nájdete informácie, ktoré vám môžu pomôcť začať konfigurovať službu Customer Insights. 

- [Pridajte ďalších používateľov a priraďte povolenia](permissions.md).
- [Prijmite zdroje údajov](data-sources.md) a spusťte ich prostredníctvom [procesu zjednocovania údajov](data-unification.md), aby ste získali [jednotné zákaznícke profily](customer-profiles.md).
- [Obohaťte zjednotené zákaznícke profily](enrichment-hub.md) alebo [spusťte prediktívne modely](predictions-overview.md).
- Vytvorte [segmenty](segments.md) skupinovým zákazníkom a KPI recenzie [opatrení](measures.md).
- Nastavte [spojenia](connections.md) a [exporty](export-destinations.md) na spracovanie podmnožín vašich údajov v iných aplikáciách.