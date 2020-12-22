---
title: Obohatenie pomocou vlastného importu protokolu SFTP
description: Všeobecné informácie o obohatení pomocou vlastného importu protokolu SFTP.
ms.date: 11/18/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: jdahl
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 59f7f05ca0825ba147e9e93f10fa3508ec3a16dd
ms.sourcegitcommit: ff824bbbd31fd666ab0da682bf48ea31580d242c
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 11/18/2020
ms.locfileid: "4568501"
---
# <a name="enrich-customer-profiles-with-custom-data-preview"></a>Obohatenie profilov zákazníkov o vlastné údaje (ukážka)

Vlastný import protokolu SFTP (Secure File Transfer Protocol) vám umožňuje importovať údaje, ktoré nemusia prechádzať procesom zjednotenia údajov. Ide o flexibilný, bezpečný a ľahký spôsob, ako prenášať vaše údaje. Vlastný import SFTP je možné použiť v kombinácii s [exportom protokolu SFTP](export-sftp.md), ktorý vám umožňuje exportovať údaje profilu zákazníka, ktoré sú potrebné na obohatenie. Údaje potom môžu byť spracované, obohatené a vlastný import protokolu SFTP je možné použiť na prenos obohatených údajov späť do funkcie prehľadov cieľových skupín v službe Dynamics 365 Customer Insights.

## <a name="prerequisites"></a>Predpoklady

Ak chcete nakonfigurovať vlastný import protokolu SFTP, musíte splniť nasledujúce predpoklady:

- Máte používateľské poverenia (používateľské meno a heslo) pre umiestnenie protokolu SFTP, odkiaľ sa budú importovať údaje.
- Máte adresu URL a číslo portu (zvyčajne 22) hostiteľa protokolu STFP.
- Máte názov súboru a umiestnenie súboru, ktorý sa má importovať, na hostiteľovi protokolu SFTP.
- Existuje súbor *model.json*, ktorý určuje schému pre údaje, ktoré sa majú importovať. Tento súbor musí byť v rovnakom adresári ako súbor, ktorý sa má importovať.
- Máte povolenie roly [Správca](permissions.md#administrator).

## <a name="configuration"></a>Konfigurácia

1. Prejdite na **Údaje** > **Obohatenie** a vyberte kartu **Objavovať**.

1. Na **dlažici vlastného importu protokolu SFTP** vyberte položku **Obohatiť moje údaje**.

   > [!div class="mx-imgBorder"]
   > ![Dlaždica vlastného importu protokolu SFTP](media/SFTP_Custom_Import_tile.png "Dlaždica vlastného importu protokolu SFTP")

1. Vyberte položku **Začíname** a zadajte poverenia a adresu servera SFTP. Napríklad zadajte sftp://mysftpserver.com:22.

1. Zadajte názov súboru, ktorý obsahuje údaje, a postup k súboru na serveri SFTP, ak sa nenachádza v koreňovom priečinku.

1. Všetky vstupy potvrďte výberom položky **Pripojiť k vlastnému importu**.

   > [!div class="mx-imgBorder"]
   > ![Rozbaľovacia ponuka konfigurácie vlastného importu protokolu SFTP](media/SFTP_Custom_Import_Configuration_flyout.png "Rozbaľovacia ponuka konfigurácie vlastného importu protokolu SFTP")

## <a name="defining-field-mappings"></a>Definovanie mapovania polí 

Adresár, ktorý obsahuje súbor, ktorý sa má importovať na server SFTP, musí obsahovať aj súbor *model.json*. Tento súbor definuje schému, ktorá sa má použiť na importovanie údajov. Schéma musí používať [Common Data Model](https://docs.microsoft.com/common-data-model/) na určenie mapovania polí. Jednoduchá ukážka súboru model.json vyzerá takto:

```
{
    "name": "EnrichmentFromMicrosoft",
    "description": "Model containing data enrichment",
    "entities": [
        {
            "name": "CustomImport",
            "attributes": [
                {
                    "name": "CustomerId",
                    "friendlyName": "Client id",
                    "dataType": "string"
                },
                {
                    "name": "PreferredCity",
                    "friendlyName": "Preferred City for vacation",
                    "dataType": "string"
                },
                {
                    "name": "PreferredTransportation",
                    "friendlyName": "Preferred transportation",
                    "dataType": "string"
                }
            ],
            "annotations": [
                {
                    "name": "c360:PrimaryKey",
                    "value": "CustomerId"
                }
            ]
        }
    ],
    "modifiedTime": "2020-01-02T12:00:00+08:00",
    "annotations": [
        {
            "name": "testAnnotation",
            "value": "testValue"
        }
    ]
}
```

## <a name="enrichment-results"></a>Výsledky obohatenia

Proces obohatenia spustíte výberom položky **Spustiť** z panela príkazov. Môžete tiež nechať systém, aby obohatenie spustil automaticky ako súčasť a [plánovaného obnovenia](system.md#schedule-tab). Čas spracovania bude závisieť od množstva údajov, ktoré sa majú importovať, a od pripojenia k serveru SFTP.

Po dokončení procesu obohacovania môžete svoje novo importované údaje o vlastnom obohacovaní skontrolovať v sekcii **Moje obohatenia**. Ďalej nájdete čas poslednej aktualizácie a počet obohatených profilov.

Môžete získať podrobné zobrazenie každého obohateného profilu výberom **Zobraziť obohatené údaje**.

## <a name="next-steps"></a>Ďalšie kroky

Stavajte na svojich obohatených údajoch o zákazníkoch. Vytváraním [segmentov](segments.md), [mier](measures.md) a [exportovaním údajov](export-destinations.md) môžete zákazníkom pripravovať prispôsobené prostredia.


