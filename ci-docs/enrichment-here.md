---
title: Obohaťte zákaznícke profily pomocou HERE Technologies (ukážka)
description: Všeobecné informácie o obohatení pomocou obohatenia tretej stranou HERE Technologies.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: d88085b6be156dd1c895e9e5b38cc9d77acbdb95
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 06/29/2022
ms.locfileid: "9052070"
---
# <a name="enrich-customer-profiles-with-here-technologies-preview"></a>Obohaťte zákaznícke profily pomocou HERE Technologies (ukážka)

HERE Technologies je spoločnosť s lokalizačnou platformou, ktorá poskytuje údaje a služby zamerané na lokalizáciu. Služby obohacovania údajov spoločnosti HERE Technologies zlepšujú presnosť informácií o polohe vašich zákazníkov. Poskytuje normalizáciu adries, extrakciu zemepisnej šírky a dĺžky a ďalšie.

## <a name="prerequisites"></a>Požiadavky

- Aktívne predplatné HERE Technologies. Ak chcete získať predplatné, [zaregistrujte sa tu](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) alebo [kontaktujte spoločnosť HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) priamo. [Ďalšie informácie o obohacovaní lokalizačných údajov od HERE Technologies.](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- A TU [spojenie](connections.md) je [nakonfigurovaný](#configure-the-connection-for-here-technologies) správcom.

## <a name="configure-the-connection-for-here-technologies"></a>Nakonfigurujte pripojenie pre HERE Technologies

Musíte byť [správca](permissions.md#admin) v Customer Insights a mať aktívny kľúč API technológie HERE.

1. Vyberte **Pridať pripojenie** pri konfigurácii obohatenia alebo prejdite na **Admin** > **Spojenia** a vyberte **Nastaviť** na dlaždici HERE Technologies.

1. Zadajte názov pripojenia a platný kľúč rozhrania HERE Technologies API.

1. Skontrolujte a poskytnite svoj súhlas pre [Ochranu osobných údajov a dodržiavanie súladu s nariadeniami](#data-privacy-and-compliance) výberom možnosti **Súhlasím**.

1. Vyberte **Overiť** potvrďte konfiguráciu a potom vyberte **Uložiť**.

   :::image type="content" source="media/enrichment-HERE-connection.png" alt-text="Konfiguračná stránka pripojenia HERE Technologies.":::

### <a name="data-privacy-and-compliance"></a>Ochrana osobných údajov a dodržiavanie súladu s nariadeniami

Keď povolíte prenos údajov spoločnosti HERE Technologies v službe Dynamics 365 Customer Insights, povoľujete tým prenos údajov mimo hranice súladu so službou Dynamics 365 Customer Insights vrátane potenciálne citlivých údajov, ako sú napríklad osobné údaje. Spoločnosť Microsoft prenesie tieto údaje na váš pokyn, ale vy ste zodpovední za zabezpečenie toho, aby spoločnosť HERE Technologies plnila všetky prípadné povinnosti týkajúce sa ochrany vašich osobných údajov alebo zabezpečenia. Ďalšie informácie nájdete vo [vyhlásení o ochrane súkromia spoločnosti Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Váš správca služby Dynamics 365 Customer Insights môžete kedykoľvek prestať používať odstránením tohto obohatenia.

## <a name="configure-the-enrichment"></a>Konfigurácia obohatenia

1. Prejdite na **Údaje** > **Obohatenie** a vyberte kartu **Objavovať**.

1. Vyberte **Obohaťte moje údaje** na **Poloha** z dlaždice HERE Technologies.

   :::image type="content" source="media/HERE-tile.png" alt-text="Dlaždica HERE Technologies.":::

1. Skontrolujte prehľad a potom vyberte **Ďalšie**.

1. Vyberte pripojenie. Ak nie je dostupný, kontaktujte správcu.

1. Vyberte **Ďalej**.

1. Vyberte **Súbor zákazníckych údajov** a vyberte si profil alebo segment, ktorý chcete obohatiť o dáta od HERE Technologies. The *Zákazník* subjekt obohacuje všetky vaše profily zákazníkov, zatiaľ čo segment obohacuje iba profily zákazníkov obsiahnuté v tomto segmente.

1. Definujte, ktorý typ polí z vašich zjednotených profilov sa má použiť na porovnávanie: primárna a/alebo sekundárna adresa. Môžete určiť mapovanie poľa pre obe adresy a profily pre obe adresy na samostatné obohatenie. Napríklad pre adresu bydliska a adresu firmy. Vyberte **Ďalej**.

1. Namapujte svoje polia na údaje z HERE Technologies. Polia **Ulica 1** a **PSČ** sú povinné pre vybranú primárnu a/alebo sekundárnu adresu. Pre vyššiu presnosť zhody pridajte viac polí.

1. Stlačte možnosť **Ďalej** na vyplnenie mapovania poľa.

1. Poskytnúť **názov** za obohatenie a **Názov výstupnej entity**.

1. Stlačte možnosť **Uložiť obohatenie** po preskúmaní vašich možností.

1. Vyberte **Bežať** začať proces obohacovania alebo zavrieť návrat do **Obohatenia** stránku.

## <a name="view-enrichment-results"></a>Pozrite si výsledky obohatenia

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

The **Počet zákazníkov obohatený o odbor** poskytuje hĺbkovú analýzu pokrytia každého obohateného poľa.

## <a name="next-steps"></a>Ďalšie kroky

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
