---
title: Obohaťte firemné profily o vylepšené firemné údaje
description: Obohaťte a normalizujte firemné údaje pomocou modelov spoločnosti Microsoft.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 131ef3d1e123628779609ddec368cfef8f4d607e
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 06/29/2022
ms.locfileid: "9054267"
---
# <a name="enrich-company-profiles-with-enhanced-company-data"></a>Obohaťte firemné profily o vylepšené firemné údaje

Na opravu, doplnenie a štandardizáciu profilov vašej spoločnosti použite modely a skompilované údaje spoločnosti Microsoft. Použijeme [Formát Common Data Model](/common-data-model/schema/core/applicationcommon/account) pre lepšiu presnosť a prehľad.

Môžete tiež [zlepšiť firemné údaje o zdrojoch údajov](data-sources-enrichment.md) zlepšiť presnosť zhody v procese zjednotenia údajov.

Pre verejné spoločnosti v Spojených štátoch sú k dispozícii informácie, ako sú výnosy, burzový index, priemysel a ďalšie.  

## <a name="how-we-enhance-company-data"></a>Ako zlepšujeme firemné údaje

Náš model prechádza dvojkrokovým procesom na zlepšenie profilu spoločnosti. Po prvé, normalizuje názov spoločnosti. Napríklad, *Spoločnosť Microsoft Corp* budú opravené a štandardizované na *Microsoft Corporation*. Snaží sa nájsť zhodu v kompilovaných firemných dátach Microsoftu. Ak sa nájde zhoda, obohatíme firemný profil o informácie z našich zostavených firemných údajov vrátane názvu firmy.

### <a name="example"></a>Príklad

Informácie o vašej spoločnosti nemusia mať štandardizovaný formát a môžu obsahovať pravopisné chyby. Model sa snaží tieto problémy opraviť a vytvoriť konzistentné informácie.

```Input
Microsft
```

```Output
- AccountName: Microsoft Corporation
- MainPhoneNumber: 8006427676
- Website: https://www.microsoft.com/
- Street1: One Microsoft Way
- City: Redmond
- StateOrProvince: Washington
- County: King
- ZipOrPostalCode: 98052
- CountryOrRegion: United States
```

## <a name="limitations"></a>Obmedzenia

Čo model nerobí:

- Potvrďte identitu spoločnosti. Neoverujeme, či je vstupom existujúca organizácia alebo či spoločnosť používa výstup ako svoj štandardný názov.
- Komplexne pokrývať spoločnosti po celom svete. Kompilované firemné údaje spoločnosti Microsoft majú globálne pokrytie, ale väčšinu pokrytia ponúkajú v Austrálii, Kanade, Spojenom kráľovstve a Spojených štátoch.
- Globálne štandardizujte adresy spoločností. V súčasnosti podporujeme štandardizáciu adries v týchto krajinách alebo regiónoch: Austrália, Kanada, Francúzsko, Nemecko, Taliansko, Japonsko, Spojené kráľovstvo a Spojené štáty americké.
- Zaručiť presnosť alebo aktuálnosť údajov. Keďže obchodné informácie sa často menia, nemôžeme zaručiť, že poskytnuté vylepšené firemné údaje sú vždy presné alebo aktuálne.

## <a name="configure-the-enrichment"></a>Konfigurácia obohatenia

1. Prejdite na **Údaje** > **Obohatenie** a vyberte kartu **Objavovať**.

1. Vyberte **Obohaťte moje údaje** na **Vylepšené firemné údaje** dlaždica.

   :::image type="content" source="media/enhanced-company-data-tile.png" alt-text="Dlaždica obohatenia v centre obohatenia pre firemné údaje.":::

1. Skontrolujte prehľad a potom vyberte **Ďalšie**.

1. Vyberte **Súbor zákazníckych údajov** a vyberte si profil alebo segment, ktorý chcete obohatiť. The *Zákazník* subjekt obohacuje všetky vaše profily zákazníkov, zatiaľ čo segment obohacuje iba profily zákazníkov obsiahnuté v tomto segmente.

1. Vyberte typ polí z profilov vašej spoločnosti, ktoré sa majú použiť na porovnávanie s kompilovanými firemnými údajmi spoločnosti Microsoft. Tento výber ovplyvní mapovacie polia, ku ktorým máte prístup v ďalšom kroku.

1. Vyberte **Ďalej**.

1. Mapujte polia vašej spoločnosti na firemné údaje od spoločnosti Microsoft. Pre vyššiu presnosť zhody pridajte viac polí.

    :::image type="content" source="media/enhanced-company-data-mapping.png" alt-text="Krok mapovania údajov pri konfigurácii obohatenia spoločnosti.":::

1. Stlačte možnosť **Ďalej** na vyplnenie mapovania poľa.

1. Poskytnúť **názov** za obohatenie a **Výstupná entita**.

1. Stlačte možnosť **Uložiť obohatenie** po preskúmaní vašich možností.

1. Vyberte **Bežať** začať proces obohacovania alebo zavrieť návrat do **Obohatenia** stránku.

## <a name="view-enrichment-results"></a>Pozrite si výsledky obohatenia

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

### <a name="overview-card"></a>Prehľadová karta

The **Prehľad zmien zákazníkov** dlaždica zobrazuje podrobnosti o pokrytí obohatenia

- **Spoločnosti spracované a zmenené** : Počet zákazníckych firemných profilov, ktoré boli úspešne obohatené.
- **Spoločnosti spracované a nezmenené** : Počet zákazníckych firemných profilov, ktoré boli rozpoznané, ale neboli zmenené. Zvyčajne sa to stane, keď sú vstupné údaje platné a nemožno ich zlepšiť obohatením.
- **Spoločnosti nespracované a nezmenené** : Počet zákazníckych firemných profilov, ktoré neboli rozpoznané. To sa zvyčajne stáva pre vstupné údaje, ktoré sú neplatné alebo nie sú podporované obohatením.

## <a name="next-steps"></a>Ďalšie kroky

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
