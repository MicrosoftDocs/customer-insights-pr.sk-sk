---
title: Obohatenie pomocou obohatenia tretej strany HERE Technologies
description: Všeobecné informácie o obohatení pomocou obohatenia tretej stranou HERE Technologies.
ms.date: 10/27/2020
ms.reviewer: jodahl
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 7082fcfec099c3c9436b233c193be23625f6691a
ms.sourcegitcommit: a9b2cf598f256d07a48bba8617347ee90024a1dd
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 12/03/2020
ms.locfileid: "4668697"
---
# <a name="enrichment-of-customer-profiles-with-here-technologies-preview"></a>Obohatenie profilov zákazníkov s pomocou HERE Technologies (ukážka)

HERE Technologies je spoločnosť s lokalizačnou platformou, ktorá poskytuje údaje a služby zamerané na lokalizáciu. So službami obohatenia údajov HERE Technologies môžete dosiahnuť presnejšie pochopenie polohy vašich zákazníkov pomocou normalizácie adresy, extrakcie zemepisnej šírky a dĺžky a ďalších údajov.

## <a name="prerequisites"></a>Predpoklady

Ak chcete nakonfigurovať obohatenia od HERE Technologies, musíte splniť nasledujúce predpoklady:

- Musíte mať aktívne predplatné HERE Technologies. Predplatné môžete získať tak, že [sa zaregistrujete tu](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) alebo že priamo [kontaktujete HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you). [Ďalšie informácie o obohacovaní lokalizačných údajov od HERE Technologies.](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- Máte kľúč rozhrania API pre HERE Technologies.

- Máte povolenia roly [Správca](permissions.md#administrator).

## <a name="configuration"></a>Konfigurácia

1. Prejdite na položku **Údaje** > **Obohatenie**.

1. Vyberte položku **Obohatiť moje údaje** na dlaždici HERE Technologies.

   > [!div class="mx-imgBorder"]
   > ![Dlaždica HERE Technologies](media/HERE-tile.png "Dlaždica HERE Technologies")

1. Zadajte aktívny **kľúč rozhrania API pre HERE Technologies**. Skontrolujte a poskytnite svoj súhlas pre **Ochranu osobných údajov a dodržiavanie súladu s nariadeniami** výberom začiarkavacieho políčka **Súhlasím**. 

1. Potvrďte obidva vstupy výberom položky **Pripojiť k HERE**.

1. Vyberte položku **Pridať údaje** a vyberte, či chcete namapovať polia na primárnu a/alebo sekundárnu adresu. Môžete určiť mapovanie polí pre obe adresy (napríklad adresu bydliska a firmy) a profily pre obe adresy obohatiť osobitne. Vyberte **Ďalej**.

1. Definujte, ktoré polia z vašich zjednotených profilov sa majú použiť na vyhľadanie zodpovedajúcich údajov o polohe od spoločnosti HERE Technologies. Polia **Ulica 1** a **PSČ** sú povinné pre vybranú primárnu a/alebo sekundárnu adresu. Pre vyššiu presnosť zhody je možné pridať viac polí.

   > [!div class="mx-imgBorder"]
   > ![Stránka konfigurácie obohatenia od HERE Technologies](media/enrichment-HERE-configuration.png "Stránka konfigurácie obohatenia od HERE Technologies")

1. Výberom položky **Použiť** dokončíte mapovanie polí.

## <a name="enrichment-results"></a>Výsledky obohatenia

Proces obohatenia spustíte výberom položky **Spustiť** z panela príkazov. Môžete tiež nechať systém, aby obohatenie spustil automaticky ako súčasť a [plánovaného obnovenia](system.md#schedule-tab). Čas spracovania bude závisieť od veľkosti vašich zákazníckych údajov a časov odozvy rozhraní API od HERE Technologies.

Po dokončení procesu obohacovania môžete skontrolovať údaje o nových obohatených zákazníckych profiloch v časti **Moje obohatenia**. Ďalej nájdete čas poslednej aktualizácie a počet obohatených profilov.

Môžete získať podrobné zobrazenie každého obohateného profilu výberom **Zobraziť obohatené údaje**.

## <a name="next-steps"></a>Ďalšie kroky

Stavajte na svojich obohatených údajoch o zákazníkoch. Vytvárajte [segmenty](segments.md), [miery](measures.md) a dokonca [exportujte údaje](export-destinations.md) na poskytovanie prispôsobenej používateľskej skúsenosti svojim zákazníkom.

## <a name="data-privacy-and-compliance"></a>Ochrana osobných údajov a dodržiavanie súladu s nariadeniami

Keď povolíte prenos údajov spoločnosti HERE Technologies v službe Dynamics 365 Customer Insights, povoľujete tým prenos údajov mimo hranice súladu so službou Dynamics 365 Customer Insights vrátane potenciálne citlivých údajov, ako sú napríklad osobné údaje. Spoločnosť Microsoft prenesie tieto údaje na váš pokyn, ale vy ste zodpovední za zabezpečenie toho, aby spoločnosť HERE Technologies plnila všetky prípadné povinnosti týkajúce sa ochrany vašich osobných údajov alebo zabezpečenia. Ďalšie informácie nájdete vo [vyhlásení o ochrane súkromia spoločnosti Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Váš správca služby Dynamics 365 Customer Insights môžete kedykoľvek prestať používať odstránením tohto obohatenia.
