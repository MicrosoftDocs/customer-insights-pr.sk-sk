---
title: Obohaťte profily zákazníkov pomocou vlastného importu SFTP (ukážka)
description: Všeobecné informácie o obohatení pomocou vlastného importu protokolu SFTP.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 88fc366ab9478c3b67034af794e237ff4573da7c
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 06/29/2022
ms.locfileid: "9082332"
---
# <a name="enrich-customer-profiles-with-sftp-custom-import-preview"></a>Obohaťte profily zákazníkov pomocou vlastného importu SFTP (ukážka)

Vlastný import protokolu SFTP (Secure File Transfer Protocol) vám umožňuje importovať údaje, ktoré nemusia prechádzať procesom zjednotenia údajov. Ide o flexibilný, bezpečný a ľahký spôsob, ako prenášať vaše údaje. Vlastný import SFTP je možné použiť v kombinácii s [exportom protokolu SFTP](export-sftp.md), ktorý vám umožňuje exportovať údaje profilu zákazníka, ktoré sú potrebné na obohatenie. Údaje sa potom môžu spracovať a obohatiť a pomocou vlastného importu SFTP sa obohatené údaje vrátia späť do Dynamics 365 Customer Insights.

## <a name="prerequisites"></a>Požiadavky

- Je známy názov súboru a umiestnenie (cesta) súboru, ktorý sa má importovať na hostiteľa SFTP.

- A *model.json* je k dispozícii súbor, ktorý špecifikuje schému Common Data Model pre údaje, ktoré sa majú importovať. Tento súbor musí byť v rovnakom adresári ako súbor, ktorý sa má importovať.

- SFTP [spojenie](connections.md) je [nakonfigurovaný](#configure-the-connection-for-sftp-custom-import).

## <a name="file-schema-example"></a>Príklad schémy súboru

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
                    "friendlyName": "Client ID",
                    "dataType": "string"
                },
                {
                    "name": "PreferredCity",
                    "friendlyName": "Preferred city for vacation",
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

## <a name="configure-the-connection-for-sftp-custom-import"></a>Nakonfigurujte pripojenie pre vlastný import SFTP

Musíte byť [správca](permissions.md#admin) v Customer Insights a majte používateľské poverenia, adresu URL a číslo portu pre umiestnenie SFTP, z ktorého chcete importovať údaje.

1. Vyberte **Pridať pripojenie** pri konfigurácii obohatenia alebo prejdite na **Admin** > **Spojenia** a vyberte **Nastaviť** na dlaždici Vlastný import.

   :::image type="content" source="media/enrichment-SFTP-connection.png" alt-text="Vlastná stránka konfigurácie pripojenia importu.":::

1. Zadajte názov pripojenia.

1. Zadajte platné používateľské meno, heslo a adresu URL hostiteľa servera SFTP, na ktorom sa nachádzajú údaje, ktoré sa majú importovať.

1. Skontrolujte a poskytnite svoj súhlas pre [Ochranu osobných údajov a dodržiavanie súladu s nariadeniami](#data-privacy-and-compliance) výberom možnosti **Súhlasím**.

1. Vyberte **Overiť** potvrďte konfiguráciu a potom vyberte **Uložiť**.

### <a name="data-privacy-and-compliance"></a>Ochrana osobných údajov a dodržiavanie súladu s nariadeniami

Keď povolíte Dynamics 365 Customer Insights na prenos údajov pomocou vlastného importu povolíte prenos údajov mimo hranice súladu pre Dynamics 365 Customer Insights, vrátane potenciálne citlivých údajov, ako sú Osobné údaje. Spoločnosť Microsoft prenesie takéto údaje na váš pokyn, ale vy ste zodpovední za zabezpečenie toho, aby údaje spĺňali všetky vaše povinnosti týkajúce sa ochrany osobných údajov alebo zabezpečenia. Ďalšie informácie nájdete vo [vyhlásení o ochrane súkromia spoločnosti Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Váš správca služby Dynamics 365 Customer Insights môžete kedykoľvek prestať používať odstránením tohto obohatenia.

## <a name="configure-the-import"></a>Konfigurácia importu

1. Prejdite na **Údaje** > **Obohatenie** a vyberte kartu **Objavovať**.

1. Vyberte **Obohaťte moje údaje** na **Vlastný import SFTP** dlaždica.

   :::image type="content" source="media/SFTP_Custom_Import_tile.png" alt-text="Dlaždica vlastného importu.":::

1. Skontrolujte prehľad a potom vyberte **Ďalšie**.

1. Vyberte pripojenie. Ak nie je dostupný, kontaktujte správcu.

1. Vyberte **Súbor zákazníckych údajov** a vyberte si profil alebo segment, ktorý chcete obohatiť. The *Zákazník* subjekt obohacuje všetky vaše profily zákazníkov, zatiaľ čo segment obohacuje iba profily zákazníkov obsiahnuté v tomto segmente.

1. Vyberte **Ďalej**.

1. Zadajte **Cesta** a **Názov súboru** dátového súboru, ktorý chcete importovať.

1. Vyberte **Ďalej**.

1. Poskytnúť **názov** za obohatenie a **Názov výstupnej entity**.

1. Stlačte možnosť **Uložiť obohatenie** po preskúmaní vašich možností.

1. Vyberte **Bežať** začať proces obohacovania alebo zavrieť návrat do **Obohatenia** stránku.

## <a name="view-enrichment-results"></a>Pozrite si výsledky obohatenia

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

## <a name="next-steps"></a>Ďalšie kroky

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
