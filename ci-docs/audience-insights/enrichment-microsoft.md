---
title: Obohaťte profily zákazníkov o údaje od spoločnosti Microsoft
description: Použite vlastné údaje od spoločnosti Microsoft na obohatenie údajov o zákazníkoch o príbuznosť a zdieľanie hlasu.
ms.date: 11/11/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 346c79d0a4d5cd5c47e91c195a48d3a153db0dc0
ms.sourcegitcommit: 9d3c9e4eb2ce20996a4f4fb44c42e3fe020c5b48
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 11/11/2021
ms.locfileid: "7793722"
---
# <a name="enrich-customer-profiles-with-affinities-and-share-of-voice-preview"></a>Obohaťte zákaznícke profily o afinity a zdieľanie hlasu (ukážka)

Použite vlastné údaje spoločnosti Microsoft na obohatenie svojich zákazníckych údajov o príbuznosť so značkou, záujmovú príbuznosť a podiel hlasu (SoV). Tieto afinity a SoV sú založené na údajoch od ľudí s podobnými demografickými údajmi ako vaši zákazníci. Tieto informácie vám pomôžu lepšie pochopiť a segmentovať vašich zákazníkov na základe ich afinity alebo SoV ku konkrétnym značkám a záujmom.

V prehľadoch cieľových skupín prejdite na **Údaje** > **Obohatenie** na [konfiguráciu a zobrazenie obohatení](enrichment-hub.md).

Ak chcete nakonfigurovať afinity k značke a obohatenie SoV, prejdite na stránku **Objavte** kartu a vyberte **Obohaťte moje údaje** na **Značky** dlaždica.

Ak chcete nakonfigurovať záujmové afinity a obohatenie SoV, prejdite na stránku **Objavte** kartu a vyberte **Obohaťte moje údaje** na **Záujmy** dlaždica.

   > [!div class="mx-imgBorder"]
   > ![Dlaždice značiek a záujmov.](media/BrandsInterest-tile-Hub.png "Dlaždice značiek a záujmov")

## <a name="how-we-determine-affinities-and-sov"></a>Ako určujeme afinity a SoV

Údaje z online vyhľadávania od spoločnosti Microsoft používame na nájdenie afinity a SoV pre značky a záujmy v rôznych demografických segmentoch (definovaných podľa veku, pohlavia alebo polohy). Online objem vyhľadávania pre značku alebo záujem tvorí základ pre určenie afinity alebo SoV. Každý z nich však poskytuje iný pohľad na pochopenie vašich zákazníkov.

- Afinita predstavuje porovnanie naprieč demografickými segmentmi. Tieto informácie môžete použiť na identifikáciu demografických segmentov, ktoré majú najvyššiu afinitu k danej značke alebo záujmu v porovnaní s inými segmentmi.

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

Ak chcete zvoliť krajinu alebo región, otvorte stránku **Obohatenie značiek** alebo **Obohatenie záujmov** a vyberte položku **Zmeniť** vedľa položky **Krajina/región**. Na table **Nastavenia krajiny/regiónu** vyberte možnosť a následne položku **Použiť**.

### <a name="implications-related-to-country-selection"></a>Dôsledky týkajúce sa výberu krajiny

- Pri [výbere vlastných značiek](#define-your-brands-or-interests) systém poskytuje návrhy na základe vybranej krajiny alebo regiónu.

- Pri [výbere odvetvia](#define-your-brands-or-interests) získate najrelevantnejšie značky alebo záujmy na základe vybranej krajiny alebo regiónu.

- Pri [obohacovaní profilov](#refresh-enrichment) obohatíme všetky profily zákazníkov, pre ktoré získame údaje o vybraných značkách a záujmoch, vrátane profilov, ktoré sa nenachádzajú vo vybranej krajine alebo regióne. Napríklad ak ste vybrali Nemecko, obohatíme profily nachádzajúce sa v USA, ak máme k dispozícii údaje o vybraných značkách a záujmoch v USA.

## <a name="configure-enrichment"></a>Konfigurácia obohatenia

Prehliadka so sprievodcom vám pomôže pri konfigurácii obohatení. 

### <a name="define-your-brands-or-interests"></a>Definujte svoje značky alebo záujmy

Vyberte si až päť značiek alebo záujmov pomocou jednej alebo oboch z týchto možností:

- **Odvetvie**: Z rozbaľovacieho zoznamu vyberte svoje odvetvie a potom si vyberte z top značiek alebo záujmov pre dané odvetvie.
- **Vyberte svoje vlastné**: Zadajte značku alebo záujem, ktorý je relevantný pre vašu organizáciu, a potom si vyberte zodpovedajúce návrhy. Ak neuvedieme hľadanú značku alebo záujem, pošlite nám svoje pripomienky pomocou odkazu **Navrhnúť**.

### <a name="review-enrichment-preferences"></a>Kontrola predvolieb obohacovania

Skontrolujte svoje predvolené predvoľby obohatenia a podľa potreby ich aktualizujte.

:::image type="content" source="media/affinity-enrichment-preferences.png" alt-text="Snímka obrazovky okna s predvoľbami obohacovania.":::

### <a name="select-entity-to-enrich"></a>Vyberte entitu na obohatenie

Vyberte **Obohatená entita** a vyberte súbor údajov, ktorý chcete obohatiť o údaje od spoločnosti Microsoft. Môžete zvoliť entitu Zákazník, aby ste obohatili všetky svoje zákaznícke profily, alebo vyberte entitu segmentu, aby ste obohatili iba profily zákazníkov obsiahnuté v danom segmente.

### <a name="map-your-fields"></a>Priraďte svoje polia

Mapujte polia z vašej zjednotenej entity zákazníka a definujte demografický segment, ktorý má systém používať na obohatenie vašich údajov o zákazníkoch. Mapujte krajinu/región a minimálne atribúty Dátum narodenia alebo Pohlavie. Okrem toho musíte namapovať aspoň jedno mesto (a štát/kraj) alebo PSČ. Zvoľte možnosť **Upraviť** na definovanie mapovania polí a keď to dokončíte, stlačte možnosť **Použiť**. Vyberte **Uložiť** na dokončenie mapovania polí.

Podporované sú nasledujúce formáty a hodnoty (hodnoty nerozlišujú veľké a malé písmená):

- **Dátum narodenia**: Počas prijímania údajov vám odporúčame previesť dátum narodenia na typ DateTime. Prípadne to môže byť reťazec vo formáte [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) „rrrr-MM-dd“ alebo „rrrr-MM-ddTHH:mm:ss“.
- **Pohlavie**: muž, žena, neznáme.
- **Poštové smerovacie číslo**: Päťmiestne PSČ pre Spojené štáty, štandardné poštové smerovacie číslo v ostatných štátoch.
- **Mesto**: názov mesta v angličtine.
- **Štát/provincia**: Dvojpísmenová skratka pre USA a Kanadu. Dvoj- alebo trojpísmenková skratka pre Austráliu. Nevzťahuje sa na Francúzsko, Nemecko ani Spojené kráľovstvo.
- **Krajina/oblasť**:

  - USA: Spojené štáty americké, Spojené štáty, USA, US, Amerika
  - CA: Kanada, CA
  - GB: Spojené kráľovstvo, UK, Veľká Británia, GB, Spojené kráľovstvo Veľkej Británie a Severného Írska, Spojené kráľovstvo Veľkej Británie
  - AU: Austrália, AU, Austrálske spoločenstvo
  - FR: Francúzsko, FR, Francúzska republika
  - DE: Nemecko, Deutschland, Allemagne, DE, Spolková republika Nemecko, Nemecká republika

## <a name="review-and-name-the-enrichment"></a>Skontrolujte a pomenujte obohatenie

Nakoniec si prečítate informácie a uvediete názov obohatenia.

:::image type="content" source="media/enrichment-interests-summary.png" alt-text="Stránka kontroly záujmov a pomenovania.":::

## <a name="refresh-enrichment"></a>Obnovenie obohatenia

Spustite obohatenie po nakonfigurovaní značiek, záujmov a mapovania terénu pre demografické údaje. Ak chcete proces spustiť, vyberte položku **Spustiť** na stránke konfigurácie značky alebo záujmu. Okrem toho môžete nechať systém, aby obohatenie spustil automaticky ako súčasť plánovanej obnovy.

V závislosti od veľkosti vašich zákazníckych údajov môže dokončenie procesu obohatenia trvať niekoľko minút.

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

## <a name="enrichment-results"></a>Výsledky obohatenia

Po dokončení procesu obohacovania prejdite na **Moje obohatenia** a skontrolujte celkový počet obohatených zákazníkov a prehľad značiek a záujmov v obohatených profiloch zákazníkov.

:::image type="content" source="media/my-enrichments.png" alt-text="Ukážka výsledkov po spustení procesu obohacovania.":::

Nájdete tu graf s počtom obohatených zákazníckych profilov v priebehu času a náhľadmi obohatených entít. Výberom skontrolujte obohatené údaje **Pozrieť viac** v **Úroveň afinity** alebo **Podiel hlasu** grafy. Obohatené údaje o značkách idú do **BrandAffinity od Microsoftu** a **BrandShareOfVoiceFromMicrosoft** subjektov. Údaje pre záujmy sú v **InterestAffinityFromMicrosoft** a **InterestShareOfVoiceFromMicrosoft** subjektov. Tieto entity nájdete uvedené aj v skupine **Obohatenie** v časti **Údaje** > **Entity**.

## <a name="see-enrichment-data-on-the-customer-card"></a>Pozrite si údaje o obohatení na karte zákazníka

Značku a záujem SoV je možné zobraziť aj na individuálnych zákazníckych kartách. Prejdite na možnosť **Zákazníci** a zvoľte si profil zákazníka. V zákazníckej karte nájdete grafy pre značku alebo záujmovú SoV na základe ľudí v demografickom profile daného zákazníka.

:::image type="content" source="media/enrichment-customer-card.png" alt-text="Karta zákazníka s obohatenými údajmi.":::

## <a name="next-steps"></a>Ďalšie kroky

[!INCLUDE [next-steps-enrichment](../includes/next-steps-enrichment.md)]


[!INCLUDE[footer-include](../includes/footer-banner.md)]
