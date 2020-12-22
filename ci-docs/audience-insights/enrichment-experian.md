---
title: Obohatenie pomocou obohatenia tretej strany Experian
description: Všeobecné informácie o obohatení pomocou obohatenia tretej stranou Experian.
ms.date: 09/17/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 60fc49734e54740e83b47a7028be216a0eb81e49
ms.sourcegitcommit: a9b2cf598f256d07a48bba8617347ee90024a1dd
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 12/03/2020
ms.locfileid: "4668832"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a>Obohatenie profilov zákazníkov o demografické údaje od spoločnosti Experian (ukážka)

Experian je svetový líder v oblasti marketingových služieb a zisťovania kreditu spotrebiteľov a firiem. So službami obohacovania údajov od spoločnosti Experian môžete hlbšie porozumieť svojim zákazníkom obohatením profilov svojich zákazníkov o demografické údaje, ako sú veľkosť domácnosti, príjem a ďalšie.

## <a name="prerequisites"></a>Predpoklady

Ak chcete nakonfigurovať Experian, musia byť splnené nasledujúce predpoklady:

- Máte aktívne predplatné Experian. Ak chcete získať predplatné, [kontaktujte Experian](https://www.experian.com/marketing-services/contact) priamo. [Ďalšie informácie o obohacovaní údajov Experian](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).
- Máte ID používateľa, ID strany a číslo modely pre svoj účet Secure Transport (ST) s podporou SSH, ktoré pre vás vytvorila spoločnosť Experian.
- Máte povolenia roly [Správca](permissions.md#administrator) prehľadoch cieľových skupín.

## <a name="configuration"></a>Konfigurácia

1. Prejdite na **Údaje** > **Obohatenie** a vyberte kartu **Objavovať**.

1. Vyberte **Obohatiť moje údaje** na dlaždici Experian.

   > [!div class="mx-imgBorder"]
   > ![Dlaždica Experian](media/experian-tile.png "Dlaždica Experian")

1. Vyberte **Začíname** a zadajte ID používateľa, ID strany a Číslo modelu pre váš účet Secure Transport spoločnosti Experian. Skontrolujte a poskytnite svoj súhlas pre **Ochranu osobných údajov a dodržiavanie súladu s nariadeniami** výberom začiarkavacieho políčka **Súhlasím**. Všetky zadané údaje potvrďte výberom položky **Použiť**.

## <a name="map-your-fields"></a>Priraďte svoje polia

1. Vyberte **Pridať údaje** a svoje kľúčové identifikátory z položiek **Meno a adresa**, **E-mail** alebo **Telefón**, ktoré pošlete spoločnosti Experian na rozlíšenie identity.

   > [!TIP]
   > Viac kľúčových identifikačných atribútov zaslaných spoločnosti Experian pravdepodobne prinesie vyššiu mieru zhody.

1. Vyberte **Ďalej** a mapujte zodpovedajúce atribúty z vašej zjednotenej entity zákazníka pre vybrané polia kľúčového identifikátora.

1. Vyberte **Pridať atribút** na mapovanie akýchkoľvek ďalších atribútov, ktoré by ste chceli poslať spoločnosti Experian.

1.  Vyberte **Uložiť** na dokončenie mapovania polí.

   > [!div class="mx-imgBorder"]
   > ![Mapovanie polí Experian](media/experian-field-mapping.png "Mapovanie polí Experian")

## <a name="enrichment-results"></a>Výsledky obohatenia

Proces obohatenia spustíte výberom položky **Spustiť** z panela príkazov. Môžete tiež nechať systém, aby obohatenie spustil automaticky ako súčasť a [plánovaného obnovenia](system.md#schedule-tab). Doba spracovania bude závisieť od veľkosti vašich zákazníckych údajov a procesov obohacovania nastavených pre váš účet spoločnosťou Experian.

Po dokončení procesu obohacovania môžete skontrolovať údaje o nových obohatených zákazníckych profiloch v časti **Moje obohatenia**. Ďalej nájdete čas poslednej aktualizácie a počet obohatených profilov.

Môžete získať podrobné zobrazenie každého obohateného profilu výberom **Zobraziť obohatené údaje**.

## <a name="next-steps"></a>Ďalšie kroky

Stavajte na svojich obohatených údajoch o zákazníkoch. Vytvárajte [segmenty](segments.md), [miery](measures.md) a dokonca [exportujte údaje](export-destinations.md) na poskytovanie prispôsobenej používateľskej skúsenosti svojim zákazníkom.

## <a name="data-privacy-and-compliance"></a>Ochrana osobných údajov a dodržiavanie súladu s nariadeniami

Keď povolíte prenos údajov spoločnosti Experian v službe Dynamics 365 Customer Insights, povoľujete tým prenos údajov mimo hranice súladu so službou Dynamics 365 Customer Insights vrátane potenciálne citlivých údajov, ako sú napríklad osobné údaje. Spoločnosť Microsoft prenesie tieto údaje na váš pokyn, ale vy ste zodpovední za zabezpečenie toho, aby spoločnosť Experian plnila všetky prípadné povinnosti týkajúce sa ochrany vašich osobných údajov alebo zabezpečenia. Ďalšie informácie nájdete vo [vyhlásení o ochrane súkromia spoločnosti Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Váš správca služby Dynamics 365 Customer Insights môžete kedykoľvek prestať používať odstránením tohto obohatenia.
