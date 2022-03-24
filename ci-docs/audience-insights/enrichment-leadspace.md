---
title: Obohatenie profilov spoločností pomocou obohatenia tretej strany Leadspace
description: Všeobecné informácie o obohatení pomocou obohatenia tretej stranou Leadspace.
ms.date: 09/30/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 0db0c984f6bf9f7ded0704b6fa0caf39c7dace3a
ms.sourcegitcommit: 50d32a4cab01421a5c3689af789e20857ab009c4
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 03/03/2022
ms.locfileid: "8376803"
---
# <a name="enrichment-of-company-profiles-with-leadspace-preview"></a>Obohatenie profilov spoločnosti pomocou Leadspace (náhľad)

Leadspace je dátová vedecká spoločnosť, ktorá poskytuje platformu údajov zákazníkov pre scenáre „firma a firma“. Umožňuje prostrediam so zjednotenými profilmi zákazníkov na základe obchodných vzťahov obohatiť ich údaje. Obohaťte *Profily zákazníkov* s atribútmi, ako je veľkosť spoločnosti, umiestnenie alebo odvetvie. Obohaťte *Kontaktné profily* s atribútmi, ako sú titul, osoba alebo overenie e-mailom.

## <a name="prerequisites"></a>Predpoklady

Na konfiguráciu Leadspace musia byť splnené nasledujúce predpoklady:

- Máte aktívnu licenciu Leadspace.
- Máte [zjednotené profily zákazníkov](customer-profiles.md) založené na obchodných vzťahoch.
- Pripojenie Leadspace už nakonfiguroval správca alebo máte povolenia [správcu](permissions.md#admin) a „trvalý kľúč” (označovaný ako **Token vedúceho priestoru**). Kontakt [Leadspace](https://www.leadspace.com/leadspace-microsoft-dynamics-365/) priamo pre podrobnosti o ich produkte.

## <a name="configure-the-enrichment"></a>Konfigurácia obohatenia

1. V prehľadoch cieľových skupín prejdite na **Údaje** > **Obohatenie**.

1. Zvoľte možnosť **Obohatiť moje údaje** na dlaždici Leadspace a stlačte možnosť **Začíname**.

   :::image type="content" source="media/leadspace-tile.png" alt-text="Snímka obrazovky dlaždice Leadspace.":::

1. Vyberte si z rozbaľovacieho zoznamu [pripojenie](connections.md). Ak nie je k dispozícii pripojenie, kontaktujte správcu. Ak ste správca, pripojenie môžete vytvoriť výberom možnosti **Pridať pripojenie** a zvoľte možnosť **Leadspace**. 

1. Vyberte **Pripojiť sa k Leadspace** na potvrdenie zvoleného spojenia.

1. Stlačte možnosť **Ďalej** a vyberte **Množina údajov o zákazníkoch** na obohatenie o demografické údaje spoločnosti z Leadspace. Môžete zvoliť entitu **Zákazník**, aby ste obohatili všetky svoje zákaznícke profily, alebo vyberte entitu segmentu, aby ste obohatili iba profily zákazníkov obsiahnuté v danom segmente.

    :::image type="content" source="media/enrichment-Leadspace-configuration-customer-data-set.png" alt-text="Snímka obrazovky pri výbere množiny údajov o zákazníkoch.":::

1. Stlačte možnosť **Ďalej** a definujte, ktorý typ polí z vašich zjednotených profilov sa má použiť na vyhľadanie zodpovedajúcich demografických údajov spoločnosti z Leadspace. Pole **Názov spoločnosti** je povinné. Pre vyššiu presnosť zhody možno pridať až dve ďalšie polia, **Webová lokalita spoločnosti** a **Sídlo spoločnosti**.

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="Tabla mapovania polí Leadspace.":::

1. Stlačte možnosť **Ďalej** na vyplnenie mapovania poľa.

1. Začiarknite políčko, ak máte *Kontaktné profily*, ktoré by ste chceli obohatiť. Prehľady cieľových skupín automaticky mapujú požadované polia.

   :::image type="content" source="media/enrichment-leadspace-contacts.png" alt-text="Obohatenie záznamov kontaktov Leadspace.":::
 
1. Zadajte názov obohatenia a vyberte **Uložiť obohatenie** po preskúmaní vašich možností.


## <a name="configure-the-connection-for-leadspace"></a>Nakonfigurujte pripojenie pre Leadspace 

Na konfiguráciu pripojení musíte byť administrátor. Stlačte možnosť **Pridať pripojenie** pri konfigurácii obohatenia *alebo* prejdite na **Správca** > **Pripojenia** a vyberte **Nastaviť** na dlaždici Leadspace.

1. Vyberte položku **Začíname**. 

1. Zadajte názov pripojenia do boxu **Zobrazovaný názov**.

1. Poskytnite platný token Leadspace.

1. Skontrolujte a poskytnite svoj súhlas pre **Ochranu osobných údajov a dodržiavanie súladu s nariadeniami** výberom možnosti **Súhlasím**.

1. Stlačte **Overiť** na overenie konfigurácie.

1. Po dokončení overenia stlačte možnosť **Uložiť**.
   
   :::image type="content" source="media/enrichment-Leadspace-connection.png" alt-text="Konfiguračná stránka pripojenia Leadspace.":::

## <a name="enrichment-results"></a>Výsledky obohatenia

Po aktualizácii obohatenia si môžete prezrieť novo obohatené údaje spoločnosti v časti [Moje obohatenia](enrichment-hub.md). Nájdete čas poslednej aktualizácie a počet obohatených profilov.

Môžete získať podrobné zobrazenie každého obohateného profilu výberom **Zobraziť obohatené údaje**.

Ďalšie informácie sa dozviete v časti [API Leadspace](https://support.leadspace.com/hc/en-us/sections/201997649-API).

## <a name="next-steps"></a>Ďalšie kroky


[!INCLUDE [next-steps-enrichment](../includes/next-steps-enrichment.md)]

## <a name="data-privacy-and-compliance"></a>Ochrana osobných údajov a dodržiavanie súladu s nariadeniami

Keď povolíte prenos údajov spoločnosti Leadspace v službe Dynamics 365 Customer Insights, povoľujete tým prenos údajov mimo hranice súladu so službou Dynamics 365 Customer Insights vrátane potenciálne citlivých údajov, ako sú napríklad osobné údaje. Spoločnosť Microsoft prenesie tieto údaje na váš pokyn, ale vy ste zodpovední za zabezpečenie toho, aby spoločnosť Leadspace plnila všetky prípadné povinnosti týkajúce sa ochrany vašich osobných údajov alebo zabezpečenia. Ďalšie informácie nájdete vo [vyhlásení o ochrane súkromia spoločnosti Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Váš správca služby Dynamics 365 Customer Insights môžete kedykoľvek prestať používať odstránením tohto obohatenia.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
