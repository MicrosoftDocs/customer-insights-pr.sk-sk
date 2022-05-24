---
title: Obohatenie firemných profilov o Dun & Bradstreet
description: Všeobecné informácie o obohatení Dun & Bradstreet treťou stranou.
ms.date: 04/26/2022
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: c738c2657d4cda213342629156ddc8104366bd8a
ms.sourcegitcommit: 4ae316c856b8de0f08a4605f73e75a8c2cf51c4e
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 05/13/2022
ms.locfileid: "8755419"
---
# <a name="enrichment-of-company-profiles-with-dun--bradstreet-preview"></a>Obohatenie firemných profilov o Dun & Bradstreet (ukážka)

Dun & Bradstreet poskytuje firmám komerčné údaje, analýzy a prehľady. Umožňuje zákazníkom so zjednotenými zákazníckymi profilmi pre spoločnosti obohacovať svoje údaje. Obohatenia zahŕňajú atribúty, ako je číslo DUNS, veľkosť spoločnosti, lokalita, odvetvie a ďalšie.

## <a name="prerequisites"></a>Požiadavky

Ak chcete nakonfigurovať obohatenie Dun & Bradstreet, musia byť splnené nasledujúce predpoklady:

- Máte aktívny [Dun & Bradstreet](https://www.dnb.com/marketing/media/give-your-data-a-boost.html?source=microsoft_audience_insights) licenciu.
- Máte [zjednotené profily zákazníkov](customer-profiles.md) pre spoločnosti.
- Dun & Bradstreet [spojenie](connections.md) je nakonfigurovaný správcom. Môžete si ho vytvoriť, ak máte [správca](permissions.md#admin) povolenia a poverenia z Dun & Bradstreet Connect.

## <a name="setting-up-your-dun--bradstreet-project"></a>Nastavenie vášho projektu Dun & Bradstreet

Ako licencovaný používateľ Dun & Bradstreet môžete nastaviť projekt v [Dun & Bradstreet Connect](https://connect.dnb.com?lead_source=microsoft_audienceinsights).


1. Prihlásiť sa [Dun & Bradstreet Connect](https://connect.dnb.com?lead_source=microsoft_audienceinsights). Ak chcete získať poverenia, [obnovte svoje heslo](https://sso.dnb.com/signin/forgot-password?lead_source=microsoft_audienceinsights).

1. Stiahnuť ▼[náš súbor šablóny csv](https://c360devenrichment.blob.core.windows.net/mapping/DnBCIdatamapping.csv) ktoré sa použijú na mapovanie polí Customer Insights k zodpovedajúcim poliam Dun & Bradstreet.

1. Nahrajte súbor do **Nahrajte údaje** krok skúseností s tvorbou projektu Dun & Bradstreet.

1. Vyberte vodorovné bodky pod príslušným **zdroj** v novovytvorenom projekte Dun & Bradstreet, aby ste videli dostupné možnosti.

   :::image type="content" source="media/enrichment-dnb-dots.png" alt-text="Snímka obrazovky bodiek v projekte Dun & Bradstreet.":::

1. Vyberte si **Získajte podrobnosti o S3**. Uložte tieto informácie na bezpečnom mieste. Budete to potrebovať [vytvoriť spojenie na obohatenie](#configure-a-connection-for-dun--bradstreet) v Customer Insights.

   :::image type="content" source="media/enrichment-dnb-s3info.png" alt-text="Snímka obrazovky výberu informácií s3 v projekte Dun & Bradstreet.":::

## <a name="configure-the-enrichment"></a>Konfigurácia obohatenia

1. Prejdite na položku **Údaje** > **Obohatenie**.

1. Vyberte **Obohaťte moje údaje** na dlaždici Dun & Bradstreet a vyberte **Začať**.

   :::image type="content" source="media/enrichment-dnb-tile.png" alt-text="Snímka obrazovky dlaždice Dun & Bradstreet.":::

1. Vyberte si z rozbaľovacieho zoznamu [pripojenie](connections.md). Ak nie je k dispozícii pripojenie, kontaktujte správcu. Ak ste správca, môžete vytvoriť pripojenie. Vyberte **Pridať pripojenie** a vyberte si **Dun & Bradstreet**.

1. Vyberte **Pripojte sa k Dun & Bradstreet** na potvrdenie spojenia.

1. Vyberte **Ďalšie** a vyberte si **Súbor zákazníckych údajov** chcete obohatiť o firemné údaje z Dun & Bradstreet. Môžete si vybrať **Zákazník** entity na obohatenie všetkých vašich zákazníckych profilov alebo vyberte segmentovú entitu na obohatenie iba zjednotených zákazníckych profilov obsiahnutých v danom segmente.

1. Vyberte **Ďalšie** a definujte, ktoré polia z vašich zjednotených profilov sa použijú na hľadanie zodpovedajúcich údajov spoločnosti z Dun & Bradstreet. Buď **DUNS číslo** alebo **Názov spoločnosti** a **Krajina** polia sú povinné. Pole krajiny podporuje [dvoj- alebo trojpísmenové kódy krajín](https://www.iso.org/iso-3166-country-codes.html), názov krajiny v angličtine, názov krajiny v rodnom jazyku a predvoľba telefónu. Niektoré bežné varianty krajín zahŕňajú:

- USA: Spojené štáty americké, Spojené štáty americké, USA, Amerika.
- CA: Kanada.
- GB: Spojené kráľovstvo, Spojené kráľovstvo, Veľká Británia, GB, Spojené kráľovstvo Veľkej Británie a Severného Írska, Spojené kráľovstvo Veľkej Británie.
- AU: Austrália, Austrálske spoločenstvo.
- FR: Francúzsko, Francúzska republika.
- DE: Nemecko, Nemecko, Nemecko, Allemagne, Spolková republika Nemecko, Nemecká republika.

   :::image type="content" source="media/enrichment-dnb-mapping.png" alt-text="Panel mapovania poľa Dun & Bradstreet.":::

1. Stlačte možnosť **Ďalej** na vyplnenie mapovania poľa.

1. Zadajte názov obohatenia a vyberte **Uložiť obohatenie** po preskúmaní vašich možností.

## <a name="configure-a-connection-for-dun--bradstreet"></a>Nakonfigurujte pripojenie pre Dun & Bradstreet

Na konfiguráciu pripojení musíte byť administrátor. Vyberte **Pridať pripojenie** pri konfigurácii obohatenia *alebo* ísť do **Admin** > **Spojenia** a vyberte **Nastaviť** na dlaždici Dun & Bradstreet.

1. Vyberte položku **Začíname**.

1. Zadajte názov pripojenia do boxu **Zobrazovaný názov**.

1. Poskytnite platné poverenia Dun & Bradstreet a podrobnosti o projekte Dun & Bradstreet *Región, Drop folder path a Drop folder name*. vy [získať tieto informácie](#setting-up-your-dun--bradstreet-project) z projektu Dun & Bradstreet.

1. Skontrolujte a poskytnite svoj súhlas pre **Ochranu osobných údajov a dodržiavanie súladu s nariadeniami** výberom možnosti **Súhlasím**.

1. Stlačte **Overiť** na overenie konfigurácie.

1. Po dokončení overenia stlačte možnosť **Uložiť**.

   :::image type="content" source="media/enrichment-dnb-connection.png" alt-text="Konfiguračná stránka pripojenia Dun & Bradstreet.":::

## <a name="enrichment-results"></a>Výsledky obohatenia

Po aktualizácii obohatenia si môžete prezrieť novo obohatené údaje spoločnosti v časti [Moje obohatenia](enrichment-hub.md). Nájdete čas poslednej aktualizácie a počet obohatených profilov.

Môžete získať podrobné zobrazenie každého obohateného profilu výberom **Zobraziť obohatené údaje**.

## <a name="next-steps"></a>Ďalšie kroky

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

## <a name="data-privacy-and-compliance"></a>Ochrana osobných údajov a dodržiavanie súladu s nariadeniami

Keď povolíte Dynamics 365 Customer Insights na prenos údajov do spoločnosti Dun & Bradstreet povolíte prenos údajov mimo hraníc súladu pre Dynamics 365 Customer Insights, vrátane potenciálne citlivých údajov, ako sú Osobné údaje. Spoločnosť Microsoft prenesie takéto údaje na váš pokyn, ale vy ste zodpovední za to, že Dun & Bradstreet spĺňa všetky vaše prípadné povinnosti týkajúce sa ochrany súkromia alebo zabezpečenia. Ďalšie informácie nájdete vo [vyhlásení o ochrane súkromia spoločnosti Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Váš správca služby Dynamics 365 Customer Insights môžete kedykoľvek prestať používať odstránením tohto obohatenia.

[!INCLUDE[footer-include](includes/footer-banner.md)]
