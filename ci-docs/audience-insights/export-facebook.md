---
title: Export údajov služby Customer Insights do Správcu reklám Facebook
description: Prečítajte si, ako nakonfigurovať pripojenie s Správcovi reklám Facebook.
ms.date: 06/05/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 8260e3b5e529f3d54678d9d6e11aebb2795e27fd
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643702"
---
# <a name="connector-for-facebook-ads-manager-preview"></a>Konektor pre Správcu reklám Facebook (ukážka)

Export segmentov zjednotených zákazníckych profilov do Správcu reklám Facebook, na ktorom chcete vytvárať kampane na Facebook a Instagram.

## <a name="prerequisites"></a>Predpoklady

- Musíte mať [**Reklamný účet Facebook**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account), ktorý zahŕňa [**Firemný účet Facebook**](https://business.facebook.com/) .
- Na počítači musíte byť správcom [**Reklamného účtu Facebook**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).

## <a name="connect-to-facebook-ads-manager"></a>Pripojenie k Správcovi reklám Facebook

1. Prejdite do ponuky **Správca** > **Ciele exportu**.

1. Pod Správca reklám **Facebook** vyberte **Nastavenie**.

1. Do poľa **Zobrazovaný názov** zadajte rozpoznateľný názov cieľa exportu.

1. Vyberte **Pokračovať s Facebook** a prihláste sa do svojho reklamného účtu Facebook.

1. Povoľte povolenie **ads_management** po vykonaní overenia cez Facebook.

1. Zvoľte **Reklamný účet Facebook**, s ktorým chcete pracovať.

1. Vyberte ikonu **Existujúce vlastné publikum** z rozbaľovacieho zoznamu alebo vytvorte a **Nové vlastné publikum**. Viac informácií nájdete v časti [**Publiká v Správcovi reklám Facebook**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).

1. Vyberte **Súhlasím** na potvrdenie **Ochrany osobných údajov a dodržiavanie súladu s nariadeniami**.

1. Vyberte **Ďalej** a nakonfigurujte export.

## <a name="configure-the-connector"></a>Nakonfigurujte konektor

1. V časti **Vyberte pole identifikátora kľúča** vyberte **E-mail**, **Meno a adresa** alebo **Telefón** na odoslanie so Správcu reklám Facebook.

1. Priraďte zodpovedajúce atribúty z vašej zjednotenej entity zákazníka na vybratý identifikátor kľúča.
   > [TIP] Najlepšie šance na zabezpečenie súladu nastanú, ak vyberiete ako kľúčový identifikátor **E-mail**. Pridanie ďalších identifikátorov môže zlepšiť zosúladenie.

1. Vyberte **Pridať atribút** na mapovanie ďalších atribútov, ktoré sa majú odoslať do Správcu reklám Facebook. Atribúty zo Správcu reklám Facebook mapujú nasledujúce používateľsky prívetivé mená: **FN** = **Krstné meno**, **LN** = **Priezvisko**, **FI** = **Iniciála krstného mena**, **TELEFÓN** = **Telefón**, **GEN** = **Pohlavie**, **DOB** = **Dátum narodenia**, **ST** = **Štát**, **CT** = **Mesto**, **ZIP** = **PSČ**, **COUNTRY** = **Krajina/región**

1. Vyberte segmenty, ktoré chcete exportovať.

1. Vyberte položku **Uložiť**.

## <a name="export-the-data"></a>Export údajov

Môžete [exportovať údaje na vyžiadanie](export-destinations.md). Export sa spustí aj pri každej [plánovanej obnove](system.md#schedule-tab).

## <a name="data-privacy-and-compliance"></a>Ochrana osobných údajov a dodržiavanie súladu s nariadeniami

Keď povolíte prenos údajov do Správcu reklám Facebook v službe Dynamics 365 Customer Insights, povoľujete tým prenos údajov mimo hranice súladu so službou Dynamics 365 Customer Insights vrátane potenciálne citlivých údajov, ako sú napríklad osobné údaje. Spoločnosť Microsoft prenesie tieto údaje na váš pokyn, ale vy ste zodpovední za zabezpečenie toho, aby Reklamy Facebook plnili všetky prípadné povinnosti týkajúce sa ochrany vašich osobných údajov alebo zabezpečenia. Ďalšie informácie nájdete vo [vyhlásení o ochrane súkromia spoločnosti Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Váš správca služby Dynamics 365 Customer Insights môže túto funkciu kedykoľvek prestať používať odstránením tohto cieľového umiestnenia exportu.
