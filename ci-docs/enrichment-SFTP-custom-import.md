---
title: Obohatenie pomocou vlastného importu protokolu SFTP
description: Všeobecné informácie o obohatení pomocou vlastného importu protokolu SFTP.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: f52d24cbe793bee7948ad2af31059cd3edf40f94
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 04/27/2022
ms.locfileid: "8643024"
---
# <a name="enrich-customer-profiles-with-custom-data-preview"></a>Obohatenie profilov zákazníkov o vlastné údaje (ukážka)

Vlastný import protokolu SFTP (Secure File Transfer Protocol) vám umožňuje importovať údaje, ktoré nemusia prechádzať procesom zjednotenia údajov. Ide o flexibilný, bezpečný a ľahký spôsob, ako prenášať vaše údaje. Vlastný import SFTP je možné použiť v kombinácii s [exportom protokolu SFTP](export-sftp.md), ktorý vám umožňuje exportovať údaje profilu zákazníka, ktoré sú potrebné na obohatenie. Údaje sa potom môžu spracovať a obohatiť a pomocou vlastného importu SFTP sa obohatené údaje vrátia späť do Dynamics 365 Customer Insights.

## <a name="prerequisites"></a>Požiadavky

Ak chcete nakonfigurovať vlastný import protokolu SFTP, musíte splniť nasledujúce predpoklady:

- Máte názov súboru a umiestnenie (postup k) súboru, ktorý sa má importovať do hostiteľa SFTP.
- Existuje súbor *model.json*, ktorý špecifikuje [schému spoločného dátového modelu](/common-data-model/) na import údajov. Tento súbor musí byť v rovnakom adresári ako súbor, ktorý sa má importovať.
- Pripojenie SFTP už nakonfiguroval správca *alebo* máte povolenia [správcu](permissions.md#admin). Budete potrebovať prihlasovacie údaje používateľa, adresu URL a číslo portu pre umiestnenie SFTP, z ktorého chcete importovať údaje.


## <a name="configure-the-import"></a>Konfigurácia importu

1. Prejdite na **Údaje** > **Obohatenie** a vyberte kartu **Objavovať**.

1. V **dlaždici vlastného importu SFTP** stlačte možnosť **Obohatiť moje údaje** a potom stlačte možnosť **Začíname**.

   :::image type="content" source="media/SFTP_Custom_Import_tile.png" alt-text="Dlaždica vlastného importu.":::

1. Vyberte si z rozbaľovacieho zoznamu [pripojenie](connections.md). Ak nie je k dispozícii pripojenie, kontaktujte správcu. Ak ste správca, pripojenie môžete vytvoriť výberom možnosti **Pridať pripojenie** a následne položky **Vlastný import SFTP** z rozbaľovacieho zoznamu.

1. Vyberte **Pripojiť sa k vlastnému importu** na potvrdenie zvoleného spojenia.

1.  Vyberte možnosť **Ďalej** a zadajte **Postup** a **Názov súboru** s údajmi, ktorý chcete importovať.

    :::image type="content" source="media/enrichment-SFTP-path-and-filename.png" alt-text="Snímka obrazovky pri zadávaní umiestnenia údajov.":::

1. Vyberte **Ďalšie** a vyberte množinu údajov o zákazníkovi. Môžu to byť všetky profily zákazníkov alebo segment.

1. Stlačte možnosť **Ďalej** a uveďte názov obohatenia a názov výstupnej entity. 

1. Stlačte možnosť **Uložiť obohatenie** po preskúmaní vašich možností.

## <a name="configure-the-connection-for-sftp-custom-import"></a>Nakonfigurujte pripojenie pre vlastný import SFTP 

Na konfiguráciu pripojení musíte byť administrátor. Stlačte možnosť **Pridať pripojenie** pri konfigurácii obohatenia *alebo* prejdite na **Správca** > **Pripojenia** a vyberte **Nastaviť** na dlaždici Vlastný import.

1. Zadajte názov pripojenia do boxu **Zobrazovaný názov**.

1. Zadajte platné používateľské meno, heslo a adresu URL hostiteľa servera SFTP, na ktorom sa nachádzajú údaje, ktoré sa majú importovať.

1. Skontrolujte a poskytnite svoj súhlas pre **Ochranu osobných údajov a dodržiavanie súladu s nariadeniami** výberom začiarkavacieho políčka **Súhlasím**.

1. Stlačte **Overiť** na overenie konfigurácie.

1. Po dokončení overenia je možné pripojenie uložiť výberom možnosti **Uložiť**.

   > [!div class="mx-imgBorder"]
   > ![Stránka konfigurácie pripojenia Experian.](media/enrichment-SFTP-connection.png "Stránka konfigurácie pripojenia Experian")


## <a name="defining-field-mappings"></a>Definovanie mapovania polí 

Adresár, ktorý obsahuje súbor, ktorý sa má importovať na server SFTP, musí obsahovať aj súbor *model.json*. Tento súbor definuje schému, ktorá sa má použiť na importovanie údajov. Schéma musí využívať [Common Data Model](/common-data-model/) na určenie mapovania poľa. Jednoduchá ukážka súboru model.json vyzerá takto:

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

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
