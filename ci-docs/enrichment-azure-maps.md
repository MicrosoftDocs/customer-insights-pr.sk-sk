---
title: Obohaťte profily zákazníkov o údaje o polohe z Azure Maps (ukážka)
description: Všeobecné informácie o obohatení pomocou služby prvej strany Azure Maps.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: dfadc08f67beac3fded1a97e557ee9e1880664e0
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 06/29/2022
ms.locfileid: "9052626"
---
# <a name="enrich-customer-profiles-with-location-data-from-azure-maps-preview"></a>Obohaťte profily zákazníkov o údaje o polohe z Azure Maps (ukážka)

Azure Maps poskytujú údaje a služby orientované na polohu, aby poskytovali skúsenosti založené na geopriestorových údajoch so vstavanou inteligenciou polohy. Služby obohacovania údajov Azure Maps zlepšujú presnosť informácií o polohe vašich zákazníkov. Prináša možnosti, ako je normalizácia adries a výber zemepisnej šírky a dĺžky Dynamics 365 Customer Insights.

## <a name="prerequisites"></a>Požiadavky

- Aktívne predplatné služby Azure Maps. Ak chcete získať predplatné, [zaregistrujte sa alebo získajte bezplatnú skúšobnú verziu](https://azure.microsoft.com/services/azure-maps/).

- Azúrové mapy [spojenie](connections.md) je [nakonfigurovaný](#configure-the-connection-for-azure-maps) správcom.

## <a name="configure-the-connection-for-azure-maps"></a>Nakonfigurujte pripojenie pre službu Azure Maps

Musíte byť [správca](permissions.md#admin) v Customer Insights a mať aktívny kľúč API pre Azure Maps.

1. Pri konfigurácii obohatenia zvoľte možnosť **Pridať pripojenie**, alebo prejdite na položku **Správca** > **Pripojenia** a vyberte možnosť **Nastaviť** na dlaždici služby Azure Maps..

   :::image type="content" source="media/enrichment-azure-maps-connection.png" alt-text="Stránka konfigurácie pripojenia služby Azure Maps.":::

1. Zadajte názov pripojenia a platný kľúč API pre Azure Maps.

1. Skontrolujte a poskytnite svoj súhlas pre [Ochranu osobných údajov a dodržiavanie súladu s nariadeniami](#data-privacy-and-compliance) výberom možnosti **Súhlasím**.

1. Vyberte **Overiť** potvrďte konfiguráciu a potom vyberte **Uložiť**.

### <a name="data-privacy-and-compliance"></a>Ochrana osobných údajov a dodržiavanie súladu s nariadeniami

Keď povolíte službe Dynamics 365 Customer Insights, aby prenášala údaje do Azure Maps, povoľujete tým aj prenos údajov mimo hranice súladu so službou Dynamics 365 Customer Insights vrátane potenciálne citlivých údajov, ako sú napríklad osobné údaje. Spoločnosť Microsoft prenesie takéto údaje na váš pokyn, ale vy ste zodpovední za to, že Azure Maps spĺňa všetky vaše povinnosti týkajúce sa ochrany osobných údajov alebo zabezpečenia. Ďalšie informácie nájdete na stránke [Vyhlásenie o ochrane osobných údajov spoločnosti Microsoft ](https://go.microsoft.com/fwlink/?linkid=396732).
Váš správca služby Dynamics 365 Customer Insights môžete kedykoľvek prestať používať odstránením tohto obohatenia.

## <a name="configure-the-enrichment"></a>Konfigurácia obohatenia

1. Prejdite na **Údaje** > **Obohatenie** a vyberte kartu **Objavovať**.

1. Vyberte **Obohaťte moje údaje** na **Poloha** od Microsoft Azure Dlaždice mapy.

   :::image type="content" source="media/azure-maps-tile.png" alt-text="Dlaždica služby Azure Maps.":::

1. Skontrolujte prehľad a potom vyberte **Ďalšie**.

1. Vyberte pripojenie. Ak nie je k dispozícii pripojenie, kontaktujte správcu.

1. Vyberte **Ďalej**.

1. Vyberte **Súbor zákazníckych údajov** a vyberte si profil alebo segment, ktorý chcete obohatiť o údaje od spoločnosti Microsoft. The *Zákazník* subjekt obohacuje všetky vaše profily zákazníkov, zatiaľ čo segment obohacuje iba profily zákazníkov obsiahnuté v tomto segmente.

1. Definujte, ktorý typ polí z vašich zjednotených profilov sa má použiť na porovnávanie: primárna a/alebo sekundárna adresa. Môžete určiť mapovanie poľa pre obe adresy a profily pre obe adresy na samostatné obohatenie. Napríklad pre adresu bydliska a adresu firmy. Vyberte **Ďalej**.

1. Namapujte svoje polia na údaje o polohe z Azure Maps. Polia **Ulica 1** a **PSČ** sú povinné pre vybranú primárnu a/alebo sekundárnu adresu. Pre vyššiu presnosť zhody pridajte viac polí.

   :::image type="content" source="media/enrichment-azure-maps-attributes.png" alt-text="Mapovanie atribútov Azure Maps.":::

1. Stlačte možnosť **Ďalej** na vyplnenie mapovania poľa.

1. Preskúmanie **Pokročilé nastavenia** ktoré ponúkajú maximálnu flexibilitu pri riešení pokročilých prípadov použitia. Nasledujúce predvolené hodnoty však zvyčajne nie je potrebné meniť.

   - **Typ adries** : Najlepšia zhoda adresy sa vráti, aj keď je neúplná. Ak chcete získať iba úplné adresy&mdash; napríklad adresy, ktoré obsahujú popisné číslo&mdash; zrušte začiarknutie všetkých políčok okrem **Adresy bodov**.
   - **Jazyk** : Adresy sa vrátia v jazyku podľa oblasti adresy. Ak chcete použiť štandardizovaný jazyk adries, vyberte jazyk z rozbaľovacej ponuky. Napríklad výber **Angličtina** sa vracia **Kodaň, Dánsko** namiesto **København, Dánsko**.
   - **Maximálny počet výsledkov** : Počet výsledkov na adresu.

1. Vyberte **Ďalej**.

1. Poskytnúť **názov** za obohatenie a **Názov výstupnej entity**.

1. Stlačte možnosť **Uložiť obohatenie** po preskúmaní vašich možností.

1. Vyberte **Bežať** začať proces obohacovania alebo zavrieť návrat do **Obohatenia** stránku.

## <a name="view-enrichment-results"></a>Pozrite si výsledky obohatenia

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

The **Počet zákazníkov obohatený o odbor** poskytuje hĺbkovú analýzu pokrytia každého obohateného poľa.

## <a name="next-steps"></a>Ďalšie kroky

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
