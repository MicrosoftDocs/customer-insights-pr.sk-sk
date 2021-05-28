---
title: Obohaťte profily zákazníkov o údaje od spoločnosti Microsoft
description: Na obohatenie svojich zákazníckych údajov o záujmy značiek a záujmov použite patentované údaje spoločnosti Microsoft.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: be042dd139607849b795c903fa58da2edb9ff589
ms.sourcegitcommit: 72603fb39c4d5dbca71128815a2e1692542ea4dc
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 05/19/2021
ms.locfileid: "6064910"
---
# <a name="enrich-customer-profiles-with-brand-and-interest-affinities-preview"></a>Obohaťte profily zákazníkov o značky a záujmy (ukážka)

Na obohatenie svojich zákazníckych údajov o záujmy značiek a záujmov použite patentované údaje spoločnosti Microsoft. Tieto afinity sa určujú na základe údajov od ľudí s podobnou demografiou ako vaši zákazníci. Tieto informácie vám pomôžu lepšie porozumieť a segmentovať vašich zákazníkov na základe ich príslušnosti k určitým značkám a záujmom.

V prehľadoch cieľových skupín prejdite na **Údaje** > **Obohatenie** na [konfiguráciu a zobrazenie obohatení](enrichment-hub.md).

Ak chcete nakonfigurovať obohatenie o afinity značiek, prejdite na stránku **Objavovať** a vyberte **Obohatiť moje údaje** na dlaždici **Značky**.

Ak chcete nakonfigurovať obohatenie o afinity záujmov, prejdite na stránku **Objavovať** a vyberte **Obohatiť moje údaje** na dlaždici **Záujmy**.

   > [!div class="mx-imgBorder"]
   > ![Dlaždice Značky a záujmy](media/BrandsInterest-tile-Hub.png "Dlaždice Značky a záujmy")

## <a name="how-we-determine-affinities"></a>Ako určujeme príbuznosti

Údaje o vyhľadávaní online spoločnosti Microsoft používame na to, aby sme zistili príbuznosť značiek a záujmov v rôznych demografických segmentoch (definované podľa veku, pohlavia alebo umiestnenia). Objem online vyhľadávania pre určitú značku alebo záujem určuje, akú príbuznosť má demografický segment v porovnaní s inými segmentmi k tejto značke alebo záujmu.

## <a name="affinity-level-and-score"></a>Úroveň afinity a skóre

V každom obohatenom profile zákazníka poskytujeme dve súvisiace hodnoty – úroveň afinity a skóre afinity. Tieto hodnoty vám pomôžu určiť, aká silná je afinita k demografickému segmentu daného profilu, k značke alebo záujmu v porovnaní s ostatnými demografickými segmentmi.

*Úroveň afinity* pozostáva zo štyroch úrovní a *skóre afinity* sa počíta na 100-bodovej stupnici, ktorá sa mapuje na úrovne afinity.


|Úroveň afinity |Skóre afinity  |
|---------|---------|
|Veľmi vysoká     | 85 – 100       |
|Vysoký     | 70 – 84        |
|Stredný     | 35 – 69        |
|Nízky     | 1 – 34        |

V závislosti od podrobností, ktoré chcete pri meraní afinity, môžete použiť buď úroveň afinity alebo skóre. Skóre afinity vám dáva presnejšiu kontrolu.

## <a name="supported-countriesregions"></a>Podporované krajiny/regióny

V súčasnosti podporujeme možnosti nasledujúcich krajín/regiónov: Austrália, Kanada (angličtina), Francúzsko, Nemecko, Spojené kráľovstvo alebo Spojené štáty (angličtina).

Ak chcete vybrať krajinu, otvorte **Obohatenie značiek** alebo **Obohatenie záujmov** a vyberte **Zmeniť** vedľa **Krajiny/regiónu**. Na table **Nastavenia krajiny/regiónu** vyberte možnosť a následne položku **Použiť**.

### <a name="implications-related-to-country-selection"></a>Dôsledky týkajúce sa výberu krajiny

- Pri [výbere vlastných značiek](#define-your-brands-or-interests) systém poskytuje návrhy na základe vybranej krajiny alebo regiónu.

- Pri [výbere odvetvia](#define-your-brands-or-interests) získate najrelevantnejšie značky alebo záujmy na základe vybranej krajiny alebo regiónu.

- Pri [obohacovaní profilov](#refresh-enrichment) obohatíme všetky profily zákazníkov, pre ktoré získame údaje o vybraných značkách a záujmoch. Zahrnutie profilov, ktoré sa nenachádzajú vo vybranej krajine alebo oblasti. Napríklad ak ste vybrali Nemecko, obohatíme profily nachádzajúce sa v USA, ak máme k dispozícii údaje o vybraných značkách a záujmoch v USA.

## <a name="configure-enrichment"></a>Konfigurácia obohatenia

Prehliadka so sprievodcom vám pomôže pri konfigurácii obohatení. 

### <a name="define-your-brands-or-interests"></a>Definujte svoje značky alebo záujmy

Vyberte jednu z nasledujúcich možností:

- **Odvetvie**: Systém identifikuje top značky alebo záujmy relevantné pre vaše odvetvie a obohacuje o nich vaše zákaznícke údaje.
- **Vyberte svoje vlastné**: Vyberte až päť položiek zo zoznamu značiek alebo záujmov, ktoré sú pre vašu organizáciu najrelevantnejšie.

Ak chcete pridať značku alebo záujem, zadajte ich do vstupnej oblasti a získajte návrhy na základe zhodných výrazov. Ak neuvedieme hľadanú značku alebo záujem, pošlite nám svoje pripomienky pomocou odkazu **Navrhnúť**.

### <a name="review-enrichment-preferences"></a>Kontrola predvolieb obohacovania

Skontrolujte svoje predvolené predvoľby obohatenia a podľa potreby ich aktualizujte.

:::image type="content" source="media/affinity-enrichment-preferences.png" alt-text="Snímka obrazovky okna s predvoľbami obohacovania.":::

### <a name="select-entity-to-enrich"></a>Vyberte entitu na obohatenie

Stlačte možnosť **Obohatená entita** a vyberte množinu údajov, ktorú chcete obohatiť o údaje spoločnosti od spoločnosti Microsoft. Môžete zvoliť entitu Zákazník, aby ste obohatili všetky svoje zákaznícke profily, alebo vyberte entitu segmentu, aby ste obohatili iba profily zákazníkov obsiahnuté v danom segmente.

### <a name="map-your-fields"></a>Priraďte svoje polia

Mapujte polia z vašej zjednotenej entity zákazníka a definujte demografický segment, ktorý má systém používať na obohatenie vašich údajov o zákazníkoch. Mapujte krajinu/región a minimálne atribúty Dátum narodenia alebo Pohlavie. Okrem toho musíte namapovať aspoň jedno mesto (a štát/kraj) alebo PSČ. Zvoľte možnosť **Upraviť** na definovanie mapovania polí a keď to dokončíte, stlačte možnosť **Použiť**. Vyberte **Uložiť** na dokončenie mapovania polí.

Podporované sú nasledujúce formáty a hodnoty, hodnoty nerozlišujú veľké a malé písmená:

- **Dátum narodenia**: Počas prijímania údajov vám odporúčame previesť dátum narodenia na typ DateTime. Alternatívne to môže byť reťazec vo formáte [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) „rrrr-MM-dd“ alebo „rrrr-MM-ddTHH: mm: ssZ“.
- **Pohlavie**: muž, žena, neznáme
- **Poštové smerovacie číslo**: Päťmiestne PSČ pre USA, štandardné poštové smerovacie číslo všade inde
- **Mesto**: Názov mesta v angličtine
- **Štát/provincia**: Dvojpísmenová skratka pre USA a Kanadu. Dvoj- alebo trojpísmenná skratka pre Austráliu. Nevzťahuje sa na Francúzsko, Nemecko ani Spojené kráľovstvo.
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

> [!TIP]
> Existuje [šesť druhov stavov](system.md#status-types) pre úlohy/procesy. Okrem toho väčšina procesov [závisí na ďalších nadväzujúcich procesoch](system.md#refresh-policies). Môžete si vybrať stav procesu a zobraziť podrobnosti o priebehu celej úlohy. Po výbere **Pozrieť detaily** pre jednu z úloh úlohy nájdete ďalšie informácie: čas spracovania, posledný dátum spracovania a všetky chyby a varovania spojené s úlohou.

## <a name="enrichment-results"></a>Výsledky obohatenia

Po dokončení procesu obohacovania prejdite na **Moje obohatenia** a skontrolujte celkový počet obohatených zákazníkov a prehľad značiek a záujmov v obohatených profiloch zákazníkov.

:::image type="content" source="media/my-enrichments.png" alt-text="Ukážka výsledkov po spustení procesu obohacovania":::

Vyberte obohatené údaje výberom **Zobraziť obohatené údaje** v tabuľke. Obohatené údaje o značkách prejdú do entity **BrandAffinityFromMicrosoft**. Údaje o záujmoch sú v entite **InterestAffinityFromMicrosoft**. Tieto entity nájdete uvedené aj v skupine **Obohatenie** v časti **Údaje** > **Entity**.

## <a name="see-enrichment-data-on-the-customer-card"></a>Pozrite si údaje o obohatení na karte zákazníka

Značky a záujmy môžu byť zobrazené aj na jednotlivých zákazníckych kartách. Prejdite na možnosť **Zákazníci** a zvoľte si profil zákazníka. Na zákazníckej karte nájdete grafy značiek alebo záujmov, ku ktorým majú ľudia v demografickom profile daného zákazníka afinitu.

:::image type="content" source="media/enrichment-customer-card.png" alt-text="Karta zákazníka s obohatenými údajmi":::

## <a name="next-steps"></a>Ďalšie kroky

Stavajte na svojich obohatených údajoch o zákazníkoch. Vytvárajte [segmenty](segments.md), [merania](measures.md) a dokonca [exportujte údaje](export-destinations.md) na poskytovanie prispôsobenej používateľskej skúsenosti svojim zákazníkom.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
