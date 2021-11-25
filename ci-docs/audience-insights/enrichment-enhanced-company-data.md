---
title: Vylepšenie firemných údajov
description: Obohaťte a normalizujte firemné údaje pomocou modelov spoločnosti Microsoft.
ms.date: 11/15/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: d11700c87f31cedc40d32b201251d8a9e2e2c312
ms.sourcegitcommit: dfc4843cc78857f1e3ca49d7b938e3ba77969169
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 11/15/2021
ms.locfileid: "7813936"
---
# <a name="enrichment-of-company-profiles-with-enhanced-company-data"></a>Obohatenie firemných profilov o vylepšené firemné dáta

Na opravu, doplnenie a štandardizáciu profilov vašej spoločnosti použite modely a skompilované údaje spoločnosti Microsoft. Použijeme [Formát Common Data Model](/common-data-model/schema/core/applicationcommon/account) pre lepšiu presnosť a prehľad.

## <a name="how-we-enhance-company-data"></a>Ako zlepšujeme firemné údaje

Náš model prechádza dvojkrokovým procesom na zlepšenie profilu spoločnosti. Po prvé, normalizuje názov spoločnosti. Napríklad, *Microsoft Corp* budú opravené a štandardizované na *Microsoft Corporation*. Snaží sa nájsť zhodu v kompilovaných firemných dátach Microsoftu. Ak sa nájde zhoda, obohatíme firemný profil o informácie z našich zostavených firemných údajov vrátane názvu firmy.


### <a name="example"></a>Príklad

Informácie o vašej spoločnosti nemusia mať štandardizovaný formát a môžu obsahovať pravopisné chyby. Model sa snaží opraviť tieto problémy a vytvoriť konzistentné informácie.

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

Rozšírené údaje majú niekoľko obmedzení. Položky v zozname nižšie nie sú modelom podporované.

1.  Potvrďte identitu spoločnosti. Neoverujeme, či je vstupom existujúca organizácia alebo či spoločnosť používa výstup ako svoj štandardný názov.
2.  Komplexne pokrývať spoločnosti po celom svete. Kompilované údaje spoločnosti Microsoft majú globálne pokrytie, ale väčšinu pokrytia ponúkajú v Austrálii, Kanade, Spojenom kráľovstve a Spojených štátoch.
3.  Globálne štandardizujte adresy spoločností. V súčasnosti podporujeme štandardizáciu adries v týchto krajinách alebo regiónoch: Austrália, Kanada, Francúzsko, Nemecko, Taliansko, Japonsko, Spojené kráľovstvo a Spojené štáty americké.
4.  Zaručiť presnosť alebo aktuálnosť údajov. Keďže obchodné informácie sa často menia, nemôžeme zaručiť, že poskytnuté vylepšené firemné údaje sú vždy presné alebo aktuálne.

## <a name="configure-the-enrichment"></a>Konfigurácia obohatenia

1. Prejdite na položku **Údaje** > **Obohatenie**.

1. Vyberte **Obohaťte moje údaje** na **Vylepšené firemné údaje** dlaždica.

   :::image type="content" source="media/enhanced-company-data-tile.png" alt-text="Dlaždica obohatenia v centre obohatenia pre firemné údaje.":::

1. Stlačte možnosť **Množina zákazníckych údajov** a vyberte entitu obsahujúcu adresy, ktoré chcete obohatiť. Môžete zvoliť entitu *Zákazník* na obohatenie adries vo všetkých vašich zákazníckych profiloch alebo vyberte entitu segmentu na obohatenie adries iba v profiloch zákazníkov obsiahnutých v danom segmente.

1. Vyberte, ktorý typ polí z vašich firemných profilov sa má použiť na porovnávanie s kompilovanými firemnými údajmi spoločnosti Microsoft. Tento výber ovplyvní mapovacie polia, ku ktorým máte prístup v ďalšom kroku.

1.  Namapujte polia spoločnosti z vašej jednotnej zákazníckej entity. Čím viac kľúčových identifikátorov a polí namapujete, tým väčšia je pravdepodobnosť vyššej miery zhody.

    :::image type="content" source="media/enhanced-company-data-mapping.png" alt-text="Krok mapovania údajov pri konfigurácii obohatenia spoločnosti.":::

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
