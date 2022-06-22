---
title: Obohaťte profily zákazníkov údajmi o polohe z Azure Maps
description: Všeobecné informácie o obohatení pomocou služby prvej strany Azure Maps.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: a806b2d0c791972c967c90694527608b4def9f3f
ms.sourcegitcommit: 27c5473eecd851263e60b2b6c96f6c0a99d68acb
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 06/13/2022
ms.locfileid: "8953647"
---
# <a name="enrichment-of-customer-profiles-with-azure-maps-preview"></a>Obohatenie zákazníckych profilov o Azure Maps (ukážka)

Azure Maps poskytujú údaje a služby orientované na polohu, aby poskytovali skúsenosti založené na geopriestorových údajoch so vstavanou inteligenciou polohy. Služby obohacovania údajov Azure Maps zlepšujú presnosť informácií o polohe vašich zákazníkov. Prináša možnosti, ako je normalizácia adries a výber zemepisnej šírky a dĺžky Dynamics 365 Customer Insights.

## <a name="prerequisites"></a>Požiadavky

- Aktívne predplatné služby Azure Maps. Ak chcete získať predplatné, [zaregistrujte sa alebo získajte bezplatnú skúšobnú verziu](https://azure.microsoft.com/services/azure-maps/).

- Azúrové mapy [spojenie](connections.md) je [nakonfigurovaný](#configure-the-connection-for-azure-maps) správcom.

## <a name="configure-the-connection-for-azure-maps"></a>Nakonfigurujte pripojenie pre službu Azure Maps

Musíte byť [správca](permissions.md#admin) v Customer Insights a máte aktívny kľúč API pre Azure Maps.

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

1. Vyberte **Obohaťte moje údaje** na **Miesto** od Microsoft Azure Dlaždice mapy.

   :::image type="content" source="media/azure-maps-tile.png" alt-text="Dlaždica služby Azure Maps.":::

1. Skontrolujte prehľad a potom vyberte **Ďalšie**.

1. Vyberte pripojenie. Ak nie je k dispozícii pripojenie, kontaktujte správcu.

1. Vyberte **Ďalej**.

1. Vyberte **Súbor zákazníckych údajov** a vyberte si profil alebo segment, ktorý chcete obohatiť o údaje od spoločnosti Microsoft. The *Zákazník* entita obohacuje všetky vaše profily zákazníkov, zatiaľ čo segment obohacuje iba profily zákazníkov obsiahnuté v tomto segmente.

1. Definujte, ktorý typ polí z vašich zjednotených profilov sa má použiť na porovnávanie: primárna a/alebo sekundárna adresa. Môžete určiť mapovanie poľa pre obe adresy a profily pre obe adresy na samostatné obohatenie. Napríklad pre adresu bydliska a adresu firmy. Vyberte **Ďalej**.

1. Namapujte svoje polia na údaje o polohe z Azure Maps. Polia **Ulica 1** a **PSČ** sú povinné pre vybranú primárnu a/alebo sekundárnu adresu. Pre vyššiu presnosť zhody pridajte viac polí.

   :::image type="content" source="media/enrichment-azure-maps-attributes.png" alt-text="Mapovanie atribútov Azure Maps.":::

1. Stlačte možnosť **Ďalej** na vyplnenie mapovania poľa.

1. Preskúmanie **Pokročilé nastavenia** ktoré ponúkajú maximálnu flexibilitu pri riešení pokročilých prípadov použitia. Nasledujúce predvolené hodnoty však zvyčajne nie je potrebné meniť.

   - **Typ adries** : Najlepšia zhoda adresy sa vráti, aj keď je neúplná. Ak chcete získať iba úplné adresy&mdash; napríklad adresy, ktoré obsahujú popisné číslo&mdash; zrušte začiarknutie všetkých políčok okrem **Adresy bodov**.
   - **Jazyk** : Adresy sa vrátia v jazyku podľa regiónu adresy. Ak chcete použiť štandardizovaný jazyk adries, vyberte jazyk z rozbaľovacej ponuky. Napríklad výber **Angličtina** sa vracia **Kodaň, Dánsko** namiesto **København, Dánsko**.
   - **Maximálny počet výsledkov** : Počet výsledkov na adresu.

1. Vyberte **Ďalej**.

1. Poskytnúť **názov** za obohatenie a **Názov výstupnej entity**.

1. Stlačte možnosť **Uložiť obohatenie** po preskúmaní vašich možností.

1. Vyberte **Bežať** na spustenie procesu obohacovania alebo zatvorenie návratu do **Obohatenia** stránku.

## <a name="enrichment-results"></a>Výsledky obohatenia

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

The **Počet zákazníkov obohatený o odbor** poskytuje hĺbkovú analýzu pokrytia každého obohateného poľa.

## <a name="next-steps"></a>Ďalšie kroky

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
