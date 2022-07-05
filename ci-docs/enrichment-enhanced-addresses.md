---
title: Obohaťte profily zákazníkov o vylepšené adresy (obsahuje video)
description: Obohaťte a normalizujte informácie o adrese profilov zákazníkov pomocou modelov spoločnosti Microsoft.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
searchScope:
- ci-data-sources-enrichment
- ci-data-sources-enrichment-details
- ci-enrichments
- ci-enrichment-wizard
- customerInsights
ms.openlocfilehash: 01f1c917c75e932cc69f4c7251e57524fc859dce
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 06/29/2022
ms.locfileid: "9082080"
---
# <a name="enrich-customer-profiles-with-enhanced-addresses"></a>Obohaťte zákaznícke profily o vylepšené adresy

Adresy vo vašich údajoch môžu byť neštruktúrované, neúplné alebo nesprávne. Použite modely spoločnosti Microsoft na normalizáciu a obohatenie vašich adries do [formátu Common Data Model](/common-data-model/schema/core/applicationcommon/address), aby bola zaistená lepšia presnosť a prehľad.

Môžete tiež [obohatiť adresy o zdroje údajov](data-sources-enrichment.md) zlepšiť presnosť zhody v procese zjednotenia údajov. 

## <a name="how-we-enhance-addresses"></a>Ako vylepšujeme adresy

Náš model prechádza vylepšením adresy v dvoch krokoch. Najskôr analyzuje adresu, aby identifikovala jej súčasti, a umiestni ich do štruktúrovaného formátu. Potom pomocou AI opravíme, doplníme a štandardizujeme hodnoty v adrese.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWNewo]

### <a name="example"></a>Príklad

Informácie o adrese môžu byť uvedené v neštandardnom formáte a môžu obsahovať pravopisné chyby. Model dokáže tieto problémy vyriešiť a vytvoriť jednotné adresy v zjednotených profiloch zákazníkov.

```Input
4567 w main stret californa missouri 54321 us
```

```Output
- Street1: 4567 W Main St
- City: California
- StateOrProvince: MO
- ZipOrPostalCode: 54321
- CountryOrRegion: United States of America

- Address: 4567 W Main St, California, MO, 54321, United States of America
```

### <a name="limitations"></a>Obmedzenia

Rozšírené adresy fungujú iba s hodnotami, ktoré už existujú vo vašich prijatých adresových údajoch. Čo model nerobí:

1. Skontrolujte, či je adresa platná.
2. Overte si platnosť niektorej z hodnôt, ako sú PSČ alebo názvy ulíc.
3. Zmeňte hodnoty, ktoré nerozpozná.

Model používa na vylepšenie adries techniky založené na strojovom učení. Rovnako ako pri každom modeli založenom na strojovom učení nie je zaručená 100-percentná presnosť.

## <a name="supported-countries-or-regions"></a>Podporované krajiny alebo regióny

V súčasnosti podporujeme obohatenie adries v týchto krajinách alebo regiónoch:

- Austrália
- Kanada
- Francúzsko
- Nemecko
- Taliansko
- Japonsko
- Spojené kráľovstvo
- Spojené štáty americké

## <a name="configure-the-enrichment"></a>Konfigurácia obohatenia

1. Prejdite na **Údaje** > **Obohatenie** a vyberte kartu **Objavovať**.

1. Stlačte možnosť **Obohatiť moje údaje** na dlaždici **Vylepšené adresy**.

   :::image type="content" source="media/enhanced-addresses-tile.png" alt-text="Snímka obrazovky z dlaždice Vylepšené adresy.":::

1. Skontrolujte prehľad a potom vyberte **Ďalšie**.

1. Vyberte **Súbor zákazníckych údajov** a vyberte si profil alebo segment, ktorý chcete obohatiť. The *Zákazník* subjekt obohacuje všetky vaše profily zákazníkov, zatiaľ čo segment obohacuje iba profily zákazníkov obsiahnuté v tomto segmente.

1. Vyberte spôsob formátovania adries vo svojich množinách údajov. Stlačte možnosť **Adresa s jedným atribútom** ak adresy vo vašich údajoch používajú jedno pole. Stlačte možnosť **Adresa s viacerými atribútmi** ak adresy vo vašich údajoch používajú viac než jedno údajové pole.

1. Vyberte **Ďalšie** a namapujte polia adresy z vašej jednotnej zákazníckej entity.

    :::image type="content" source="media/enhanced-address-mapping.png" alt-text="Vylepšená stránka na mapovanie polí adries.":::

   > [!NOTE]
   > Štát/oblasť je povinný údaj v adresách s jedným atribútom aj s viacerými atribútmi. Adresy, ktoré neobsahujú platné alebo podporované hodnoty krajín alebo oblastí, nebudú obohatené.

1. Stlačte možnosť **Ďalej** na vyplnenie mapovania poľa.

1. Poskytnúť **názov** za obohatenie a **Výstupná entita**.

1. Stlačte možnosť **Uložiť obohatenie** po preskúmaní vašich možností.

## <a name="view-enrichment-results"></a>Pozrite si výsledky obohatenia

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

The **Počet zákazníkov obohatený o odbor** poskytuje hĺbkovú analýzu pokrytia každého obohateného poľa.

### <a name="overview-card"></a>Prehľadová karta

The **Prehľad zmien zákazníkov** karta zobrazuje podrobnosti o pokrytí obohatenia:

- **Adresy spracované a zmenené** : Počet zákazníckych profilov s adresami, ktoré boli úspešne obohatené.
- **Adresy spracované a nezmenené** : Počet zákazníckych profilov s adresami, ktoré boli rozpoznané, ale neboli zmenené. Zvyčajne sa to stane, keď sú vstupné údaje platné a nemožno ich zlepšiť obohatením.
- **Adresy neboli spracované a nezmenené** : Počet profilov s adresami, ktoré neboli rozpoznané. Zvyčajne pre vstupné údaje, ktoré sú neplatné alebo nie sú podporované obohatením.

## <a name="next-steps"></a>Ďalšie kroky

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
