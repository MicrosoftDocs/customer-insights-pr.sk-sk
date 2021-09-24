---
title: Obohaťte profily zákazníkov údajmi o polohe z Azure Maps
description: Všeobecné informácie o obohatení pomocou služby prvej strany Azure Maps.
ms.date: 08/31/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 63f241c27ec86f357c83a301d6797f9ff87c2241
ms.sourcegitcommit: 2acda3c5adf40bc3f5bbb4b2b4b6c22f84371da7
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 09/01/2021
ms.locfileid: "7466781"
---
# <a name="enrichment-of-customer-profiles-with-azure-maps-preview"></a>Obohatenie zákazníckych profilov o Azure Maps (ukážka)

Služba Azure Maps poskytuje údaje a služby týkajúce sa polohy. Poskytuje zážitky založené na geopriestorových údajoch so zabudovanou analýzou polohy. Služby obohacovania údajov Azure Maps zlepšujú presnosť informácií o polohe vašich zákazníkov. Prináša možnosti, ako je normalizácia adries a výber zemepisnej šírky a dĺžky Dynamics 365 Customer Insights.

## <a name="prerequisites"></a>Predpoklady

Ak chcete nakonfigurovať obohatenie údajov služby Azure Maps, je potrebné splniť tieto predpoklady:

- Je potrebné mať aktívne predplatnú službu Azure Maps. Predplatné získate [zaregistrovaním sa alebo získaním bezplatnej skúšobnej verzie](https://azure.microsoft.com/services/azure-maps/).

- Je dostupné [pripojenie](connections.md) k službe Azure Maps, *alebo* máte povolenie [správcu](permissions.md#administrator) a aktívny kľúč API služby Azure Maps.

## <a name="configure-the-enrichment"></a>Konfigurácia obohatenia

1. Prejdite na položku **Údaje** > **Obohatenie**. 

1. Na dlaždici **Poloha** označte položku **Obohatiť moje údaje**.

   :::image type="content" source="media/azure-maps-tile.png" alt-text="Dlaždica služby Azure Maps.":::

1. Vyberte si z rozbaľovacieho zoznamu [pripojenie](connections.md). Ak nie je dostupné pripojenie k službe Azure Maps, obráťte sa na správcu. Ak ste správca, môžete[ nakonfigurovať pripojenie pre službu Azure Maps ](#configure-the-connection-for-azure-maps). 

1. Označenim položky **Ďalej** potvrďte výber.

1. Označte **dátový súbor zákazníka**, ktorý chcete obohatiť o údaje polohy zo služby Azure Maps. Vybraním položky **Zákazník** môžete obohatiť všetky svoje zjednotené profily zákazníkov, alebo vybraním entity segmentu obohatíte iba profily zákazníkov obsiahnuté v tomto segmente.

    :::image type="content" source="media/enrichment-azure-maps-configuration-customer-data-set.png" alt-text="Snímka obrazovky pre výber množiny údajov zákazníkov.":::

1. Zvoľte, či chcete polia mapovať na primárnu a/alebo sekundárnu adresu. Môžete určiť mapovanie polí pre obidve adresy a obohatiť profily pre obidve adresy zvlášť&mdash; napríklad pre domovskú a firemnú adresu. Vyberte **Ďalej**.

1. Definujte, ktorý typ polí z vašich zjednotených profilov sa má použiť na vyhľadanie príslušných údajov o polohe zo spoločnosti Azure Maps. Polia **Ulica 1** a **PSČ** sú povinné pre zvolenú primárnu alebo sekundárnu adresu. Pre väčšiu presnosť zhody môžete pridať ďalšie polia.

   :::image type="content" source="media/enrichment-azure-maps-configuration.png" alt-text="Stránka konfigurácie obohatenia od Azure Maps.":::

1. Stlačte možnosť **Ďalej** na vyplnenie mapovania poľa.

1. Rozhodnite sa, či chcete upraviť **Pokročilé nastavenia**. Tieto slúžia na poskytnutie maximálnej flexibility pri riešení pokročilých prípadov použitia, no predvolené hodnoty sú postačujúce pre väčšinu prípadov:
   - **Typ adries**: Predvolené správanie je, že obohatenie vráti tú najlepšiu zhodu adries, aj keď je neúplná. Ak chcete získať iba úplné adresy&mdash; napríklad adresy, ktoré obsahujú popisné číslo&mdash; zrušte začiarknutie všetkých políčok okrem **Adresy bodov**. 
   - **Jazyk** : Adresy sa štandardne vracajú v jazyku oblasti, pre ktorú bola určená adresa. Ak chcete použiť štandardizovaný jazyk adries, vyberte jazyk z rozbaľovacej ponuky. Napríklad výberom možnosti **Angličtina** sa zobrazí text **Kodaň, Dánsko** namiesto **København, Danmark**.

1. Zadajte názov pre obohatenie.

1. Prezrite si svoje voľby a potom vyberte možnosť **Uložiť obohatenie**.

## <a name="configure-the-connection-for-azure-maps"></a>Nakonfigurujte pripojenie pre službu Azure Maps

Aby ste mohli konfigurovať pripojenia, je potrebné byť správcom prehľadov cieľovej skupiny. Pri konfigurácii obohatenia zvoľte možnosť **Pridať pripojenie**, alebo prejdite na položku **Správca** > **Pripojenia** a vyberte možnosť **Nastaviť** na dlaždici služby Azure Maps..

1. V poli **Zobraziť názov** napíšte názov pripojenia.

1. Zadajte platný kľúč API služby Azure Maps.

1. Skontrolujte a poskytnite svoj súhlas pre **Ochrana osobných údajov a dodržiavanie súladu s nariadeniami** označením začiarkavacieho políčka **Súhlasím**.

1. Stlačte **Overiť** na overenie konfigurácie.

1. Po dokončení overenia stlačte možnosť **Uložiť**.

:::image type="content" source="media/enrichment-azure-maps-connection.png" alt-text="Stránka konfigurácie pripojenia služby Azure Maps.":::

## <a name="enrichment-results"></a>Výsledky obohatenia

Proces obohatenia spustíte výberom položky **Spustiť** z panela príkazov. Môžete tiež nechať systém, aby obohatenie spustil automaticky ako súčasť a [plánovaného obnovenia](system.md#schedule-tab). Čas spracovania bude závisieť od množstva vašich údajov o zákazníkoch a časov odozvy rozhrania API.

Po dokončení obohacovania si môžete pozrieť údaje novo obohatených profilov zákazníkov v časti **Moje obohatenia**. Ďalej nájdete čas poslednej aktualizácie a počet obohatených profilov.

Môžete získať podrobné zobrazenie každého obohateného profilu výberom **Zobraziť obohatené údaje**.

## <a name="next-steps"></a>Ďalšie kroky

Stavajte na svojich obohatených údajoch o zákazníkoch. Vytvárajte [segmenty](segments.md), [miery](measures.md) a dokonca [exportujte údaje](export-destinations.md) na poskytovanie prispôsobenej používateľskej skúsenosti svojim zákazníkom.

## <a name="data-privacy-and-compliance"></a>Ochrana osobných údajov a dodržiavanie súladu s nariadeniami

Keď povolíte službe Dynamics 365 Customer Insights, aby prenášala údaje do Azure Maps, povoľujete tým aj prenos údajov mimo hranice súladu so službou Dynamics 365 Customer Insights vrátane potenciálne citlivých údajov, ako sú napríklad osobné údaje. Microsoft prenesie tieto údaje na váš pokyn, ale vy ste zodpovední za zabezpečenie toho, aby služba Azure Maps spĺňala všetky záväzky týkajúce sa ochrany vášho súkromia alebo bezpečnosti. Ďalšie informácie nájdete na stránke [Vyhlásenie o ochrane osobných údajov spoločnosti Microsoft ](https://go.microsoft.com/fwlink/?linkid=396732).
Váš správca služby Dynamics 365 Customer Insights môžete kedykoľvek prestať používať odstránením tohto obohatenia.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
