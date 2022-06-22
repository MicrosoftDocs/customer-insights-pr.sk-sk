---
title: Obohaťte profily zákazníkov o údaje o značkách a záujmoch od spoločnosti Microsoft
description: Použite proprietárne údaje od spoločnosti Microsoft na obohatenie údajov o zákazníkoch o príbuznosti a zdieľanie hlasu.
ms.date: 03/02/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
searchScope:
- ci-enrichments
- ci-enrichment-wizard
- customerInsights
ms.openlocfilehash: 61262980cafdcd130430e200e466ce7da6cc4d07
ms.sourcegitcommit: 27c5473eecd851263e60b2b6c96f6c0a99d68acb
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 06/13/2022
ms.locfileid: "8953784"
---
# <a name="enrich-customer-profiles-with-affinities-and-share-of-voice-preview"></a>Obohaťte zákaznícke profily o afinity a zdieľanie hlasu (ukážka)

Použite vlastné údaje spoločnosti Microsoft na obohatenie svojich zákazníckych údajov o príbuznosť so značkou, záujmovú príbuznosť a podiel hlasu (SoV). Tieto afinity a SoV sú založené na údajoch od ľudí s podobnými demografickými údajmi ako vaši zákazníci. Tieto informácie vám pomôžu lepšie pochopiť a segmentovať vašich zákazníkov na základe ich afinity alebo SoV ku konkrétnym značkám a záujmom.

## <a name="how-we-determine-affinities-and-sov"></a>Ako určujeme afinity a SoV

Údaje z online vyhľadávania od spoločnosti Microsoft používame na nájdenie afinity a SoV pre značky a záujmy v rôznych demografických segmentoch (definovaných podľa veku, pohlavia alebo polohy). Online objem vyhľadávania pre značku alebo záujem tvorí základ pre určenie afinity alebo SoV. Každý z nich však poskytuje iný pohľad na pochopenie vašich zákazníkov.

- Afinita je porovnateľný údaj naprieč demografickými segmentmi. Tieto informácie môžete použiť na identifikáciu demografických segmentov, ktoré majú najvyššiu afinitu k danej značke alebo záujmu v porovnaní s inými segmentmi.

- Podiel hlasu predstavuje porovnanie medzi vami vybranými značkami alebo záujmami. Tieto informácie môžete použiť na zistenie, ktorá značka alebo záujem má najvyšší podiel hlasu pre daný demografický segment v porovnaní s inými značkami alebo záujmami, ktoré ste vybrali.

## <a name="affinity-level-and-score"></a>Úroveň afinity a skóre

V každom obohatenom profile zákazníka poskytujeme dve súvisiace hodnoty: úroveň afinity a skóre afinity. Tieto hodnoty vám pomôžu určiť, aká silná je afinita k demografickému segmentu daného profilu, k značke alebo záujmu v porovnaní s ostatnými demografickými segmentmi.

*Úroveň afinity* pozostáva zo štyroch úrovní a *skóre afinity* sa počíta na 100-bodovej stupnici, ktorá sa mapuje na úrovne afinity.

|Úroveň afinity |Skóre afinity  |
|---------|---------|
|Veľmi vysoká     | 85 – 100       |
|Vysoký     | 70 – 84        |
|Stredný     | 35 – 69        |
|Nízky     | 1 – 34        |

V závislosti od podrobností, ktoré chcete pri meraní afinity, môžete použiť buď úroveň afinity alebo skóre. Skóre afinity vám dáva presnejšiu kontrolu.

## <a name="share-of-voice-sov"></a>Podiel hlasu (SoV)

SoV počítame na 100-bodovej škále. Celková hodnota SoV naprieč všetkými značkami alebo záujmami pre každý rozšírený zákaznícky profil je 100. Na rozdiel od afinity je SoV relatívna k značkám a záujmom, ktoré si vyberiete. Napríklad hodnoty SoV pre 'Microsoft' sa môžu líšiť, ak sú vybraté značky ('Microsoft', 'GitHub') oproti ('Microsoft', 'LinkedIn').

## <a name="supported-countriesregions"></a>Podporované krajiny/regióny

V súčasnosti podporujeme možnosti nasledujúcich krajín/regiónov: Austrália, Kanada (angličtina), Francúzsko, Nemecko, Spojené kráľovstvo alebo Spojené štáty (angličtina).

## <a name="configure-the-enrichment"></a>Konfigurácia obohatenia

1. Prejdite na **Údaje** > **Obohatenie** a vyberte kartu **Objavovať**.

   - Ak chcete nakonfigurovať afinity k značke a obohatenie SoV, vyberte **Obohaťte moje údaje** na **Značky** dlaždica.

   - Ak chcete nakonfigurovať záujmové afinity a obohatenie SoV, vyberte **Obohaťte moje údaje** na **Záujmy** dlaždica.

   > [!div class="mx-imgBorder"]
   > ![Dlaždice značiek a záujmov.](media/BrandsInterest-tile-Hub.png "Dlaždice značiek a záujmov")

1. Skontrolujte prehľad a potom vyberte **Ďalšie**.

1. Ak chcete zmeniť krajinu alebo región, vyberte **Zmeniť** vedľa **Krajina/región**. V **Nastavenia krajiny/regiónu** panel, vyberte a [podporovaná krajina/región](#supported-countriesregions) a vyberte **Použiť**.

   > [!NOTE]
   > Pri výbere vlastných značiek systém poskytuje návrhy na základe vybranej krajiny alebo regiónu. Pri výbere odvetvia získate najrelevantnejšie značky alebo záujmy na základe vybranej krajiny alebo regiónu.

1. Vyberte si až päť značiek alebo záujmov pomocou jednej alebo oboch z týchto možností:

   - **Odvetvie**: Z rozbaľovacieho zoznamu vyberte svoje odvetvie a potom si vyberte z top značiek alebo záujmov pre dané odvetvie.
   - **Vyberte svoje vlastné**: Zadajte značku alebo záujem, ktorý je relevantný pre vašu organizáciu, a potom si vyberte zodpovedajúce návrhy. Ak neuvedieme hľadanú značku alebo záujem, pošlite nám svoje pripomienky pomocou odkazu **Navrhnúť**.

1. Vyberte **Ďalšie** a skontrolujte svoje predvolené preferencie obohatenia a podľa potreby ich aktualizujte.

   :::image type="content" source="media/affinity-enrichment-preferences.png" alt-text="Snímka obrazovky okna s predvoľbami obohacovania.":::

1. Vyberte **Ďalej**.

1. Vyberte **Súbor zákazníckych údajov** a vyberte si profil alebo segment, ktorý chcete obohatiť o údaje od spoločnosti Microsoft. The *Zákazník* entita obohacuje všetky vaše profily zákazníkov, zatiaľ čo segment obohacuje iba profily zákazníkov obsiahnuté v tomto segmente.

1. Vyberte **Ďalej**.

1. Namapujte svoje polia z vašej jednotnej entity zákazníka na údaje spoločnosti Microsoft.

   > [!NOTE]
   > Vyžadujú sa aspoň atribúty Dátum narodenia alebo Pohlavie. Vyžaduje sa krajina/región a aspoň mesto (a štát/provincia) alebo PSČ. Odporúčame, aby sa dátum narodenia počas prijímania údajov skonvertoval na typ DateTime. Prípadne to môže byť reťazec vo formáte [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) „rrrr-MM-dd“ alebo „rrrr-MM-ddTHH:mm:ss“.

1. Stlačte možnosť **Ďalej** na vyplnenie mapovania poľa.

1. Zadajte názov pre obohatenie. The **Názov výstupnej entity** sa vyberie automaticky.

   :::image type="content" source="media/enrichment-interests-summary.png" alt-text="Stránka kontroly záujmov a pomenovania.":::

1. Stlačte možnosť **Uložiť obohatenie** po preskúmaní vašich možností.

1. Vyberte **Bežať** na spustenie procesu obohacovania alebo zatvorenie návratu do **Obohatenia** stránku.

   Pri obohacovaní profilov obohatíme všetky profily zákazníkov, pre ktoré získame údaje o vybraných značkách a záujmoch, vrátane profilov, ktoré sa nenachádzajú vo vybranej krajine alebo regióne. Napríklad ak ste vybrali Nemecko, obohatíme profily nachádzajúce sa v USA, ak máme k dispozícii údaje o vybraných značkách a záujmoch v USA.

## <a name="enrichment-results"></a>Výsledky obohatenia

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

:::image type="content" source="media/my-enrichments.png" alt-text="Ukážka výsledkov po spustení procesu obohacovania.":::

Výsledky zahŕňajú **Úroveň afinity** alebo **Podiel hlasu** grafy.

Subjekty vytvorené z obohatenia sú uvedené pod **Obohacovanie** skupina v **Údaje** > **entity**. Obohatené údaje o značkách idú do **BrandAffinity od Microsoftu** a **BrandShareOfVoiceFromMicrosoft** subjektov. Údaje pre záujmy sú v **InterestAffinityFromMicrosoft** a **InterestShareOfVoiceFromMicrosoft** subjektov.

## <a name="see-enrichment-data-on-the-customer-card"></a>Pozrite si údaje o obohatení na karte zákazníka

Značku a záujem SoV je možné zobraziť aj na individuálnych zákazníckych kartách. Prejdite na možnosť **Zákazníci** a zvoľte si profil zákazníka. V zákazníckej karte nájdete grafy pre značku alebo záujmovú SoV na základe ľudí v demografickom profile daného zákazníka.

:::image type="content" source="media/enrichment-customer-card.png" alt-text="Karta zákazníka s obohatenými údajmi.":::

## <a name="next-steps"></a>Ďalšie kroky

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]


[!INCLUDE [footer-include](includes/footer-banner.md)]
