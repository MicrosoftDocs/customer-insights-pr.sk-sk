---
title: Obohatenie vylepšenia adresy
description: Obohaťte a normalizujte informácie o adrese profilov zákazníkov pomocou modelov spoločnosti Microsoft.
ms.date: 07/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: f56be1f4ecdac124ed76a0fb0eb1e313099248bf
ms.sourcegitcommit: 1565f4f7b4e131ede6ae089c5d21a79b02bba645
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 10/14/2021
ms.locfileid: "7643415"
---
# <a name="enrichment-of-customer-profiles-with-enhanced-addresses"></a>Obohatenie zákazníckych profilov vylepšenými adresami

Adresy vo vašich údajoch môžu byť neštruktúrované, neúplné alebo nesprávne. Použite modely spoločnosti Microsoft na normalizáciu a obohatenie vašich adries do [formátu Common Data Model](/common-data-model/schema/core/applicationcommon/address), aby bola zaistená lepšia presnosť a prehľad.

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

Vylepšené adresy fungujú iba s hodnotami, ktoré už existujú v údajoch o prijatej adrese. Čo model nerobí: 

1. Skontrolujte, či je adresa platná.
2. Overte si platnosť niektorej z hodnôt, ako sú PSČ alebo názvy ulíc.
3. Zmeňte hodnoty, ktoré nerozpozná.

Model používa na vylepšenie adries techniky založené na strojovom učení. Aj keď pri zmene vstupnej hodnoty modelu použijeme vysoký prah spoľahlivosti, rovnako ako u iných modelov založených na strojovom učení nie je možné zaručiť 100-percentnú presnosť.

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

Adresy musia obsahovať hodnotu krajiny alebo regiónu. Nespracovávame adresy pre krajiny alebo regióny, ktoré nie sú podporované, a adresy, pre ktoré nie je uvedená žiadna krajina alebo región.

## <a name="configure-the-enrichment"></a>Konfigurácia obohatenia

1. Prejdite na položku **Údaje** > **Obohatenie**.

1. Stlačte možnosť **Obohatiť moje údaje** na dlaždici **Vylepšené adresy**.

   :::image type="content" source="media/enhanced-addresses-tile.png" alt-text="Snímka obrazovky z dlaždice Vylepšené adresy.":::

1. Stlačte možnosť **Množina zákazníckych údajov** a vyberte entitu obsahujúcu adresy, ktoré chcete obohatiť. Môžete zvoliť entitu *Zákazník* na obohatenie adries vo všetkých vašich zákazníckych profiloch alebo vyberte entitu segmentu na obohatenie adries iba v profiloch zákazníkov obsiahnutých v danom segmente.

1. Vyberte spôsob formátovania adries vo svojich množinách údajov. Stlačte možnosť **Adresa s jedným atribútom** ak adresy vo vašich údajoch používajú jedno pole. Stlačte možnosť **Adresa s viacerými atribútmi** ak adresy vo vašich údajoch používajú viac než jedno údajové pole.

   > [!NOTE]
   > Štát/oblasť je povinný údaj v adresách s jedným atribútom aj s viacerými atribútmi. Adresy, ktoré neobsahujú platné alebo podporované hodnoty krajín alebo oblastí, nebudú obohatené.

1.  Mapujte polia adresy od svojej zjednotenej zákazníckej entity.

    :::image type="content" source="media/enhanced-address-mapping.png" alt-text="Vylepšená stránka na mapovanie polí adries.":::

1. Stlačte možnosť **Ďalej** na vyplnenie mapovania poľa.

1. Uveďte názov obohatenia a názov výstupnej entity.

1. Stlačte možnosť **Uložiť obohatenie** po preskúmaní vašich možností.

## <a name="enrichment-results"></a>Výsledky obohatenia

Proces obohatenia spustíte výberom položky **Spustiť** z panela príkazov. Môžete tiež nechať systém, aby obohatenie spustil automaticky ako súčasť a [plánovaného obnovenia](system.md#schedule-tab). Čas spracovania závisí od veľkosti vašich zákazníckych údajov.

Po dokončení procesu obohacovania môžete skontrolovať údaje o nových obohatených zákazníckych profiloch v časti **Moje obohatenia**. Ďalej nájdete čas poslednej aktualizácie a počet obohatených profilov.

Môžete získať podrobné zobrazenie každého obohateného profilu výberom **Zobraziť obohatené údaje**.

## <a name="next-steps"></a>Ďalšie kroky

[!INCLUDE [next-steps-enrichment](../includes/next-steps-enrichment.md)]

[!INCLUDE[footer-include](../includes/footer-banner.md)]
