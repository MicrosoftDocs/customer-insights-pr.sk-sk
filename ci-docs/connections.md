---
title: Prehľad pripojení (ukážka)
description: Prepojenia s inými službami zo služby Customer Insights.
ms.date: 08/04/2022
ms.reviewer: nikeller
ms.subservice: audience-insights
ms.topic: overview
author: m-hartmann
ms.author: mhart
manager: shellyha
searchScope:
- ci-connections
- customerInsights
ms.openlocfilehash: 8580dc7d90c75f66f73efc15f8e38f5e10fbb8a7
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 08/10/2022
ms.locfileid: "9245530"
---
# <a name="connections-preview-overview"></a>Prehľad pripojení (ukážka)

Pripojenia sú kľúčom na umožnenie zdieľania údajov smerom do a z Customer Insights. Každé pripojenie ustanovuje zdieľanie údajov s konkrétnou službou. Použite pripojenia na [konfigurovať obohatenia tretích strán](enrichment-hub.md) a [konfigurovať exporty](export-destinations.md). Rovnaké pripojenie je možné použiť viackrát. Napríklad jedno pripojenie k Dynamics 365 Marketing funguje pre viac exportov a jedno pripojenie Leadspace je možné použiť pre niekoľko obohatení.

## <a name="export-connections"></a>Exportujte pripojenia

Nové pripojenia môžu konfigurovať iba správcovia, ale môžu [udeliť prístup prispievateľom](#allow-contributors-to-use-a-connection-for-exports) použiť existujúce spojenia. Správcovia kontrolujú, kam môžu údaje smerovať, prispievatelia definujú užitočné zaťaženie a frekvenciu zodpovedajúcu ich potrebám.

## <a name="enrichment-connections"></a>Spojenia obohatenia

Nové pripojenia môžu konfigurovať iba správcovia, ale vytvorené pripojenia sú vždy dostupné pre správcov aj prispievateľov. Správcovia spravujú poverenia a udeľujú súhlas s prenosmi údajov. Pripojenia možno použiť na obohatenie správcov aj prispievateľov.

## <a name="add-a-new-connection"></a>Pridať nové pripojenie

### <a name="prerequisites"></a>Požiadavky

- [Povolenia správcu](permissions.md)
- Ostatné služby spoločnosti Microsoft, ak existujú, sú v rovnakej organizácii

1. Prejdite do časti **Správca** > **Pripojenia**.

1. Vyberte **Pridať pripojenie** a vyberte typ pripojenia, ktoré chcete vytvoriť. Alebo prejdite na **Objavte** kartu a vyberte **Nastaviť** na spojovacej dlaždici.

1. Do poľa **Zobrazovaný názov** zadajte rozpoznateľný názov pripojenia. Zobrazovaný názov a typ spojenia, ktoré popisuje toto spojenie. Odporúčame zvoliť názov, ktorý vysvetľuje účel a cieľ tohto spojenia.

1. Zadajte požadované údaje. Presné polia závisia od služby, ku ktorej sa pripájate. Podrobnosti o konkrétnom type pripojenia nájdete v článku o cieľovej službe.

1. Ak [použijete svoj vlastný Key Vault](use-azure-key-vault.md) na uloženie tajomstiev, aktivujte **Použiť Key Vault** a vyberte tajomstvo zo zoznamu.

1. Skontrolujte súkromie údajov a súlad a vyberte **Súhlasím**.

1. Vyberte **Uložiť** na vytvorenie spojenia.

### <a name="data-privacy-and-compliance"></a>Ochrana osobných údajov a dodržiavanie súladu s nariadeniami

Keď povolíte Dynamics 365 Customer Insights na prenos údajov tretím stranám alebo iným produktom spoločnosti Microsoft povoľujete prenos údajov mimo rámca súladu Dynamics 365 Customer Insights, vrátane potenciálne citlivých údajov, ako sú Osobné údaje. Spoločnosť Microsoft prenesie takéto údaje na váš pokyn, ale vy ste zodpovední za to, že tretia strana splní všetky vaše povinnosti týkajúce sa ochrany osobných údajov alebo zabezpečenia. Ďalšie informácie nájdete vo [vyhlásení o ochrane súkromia spoločnosti Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).

Váš Dynamics 365 Customer Insights správca môže pripojenie kedykoľvek zrušiť a prestať tak funkciu používať.

## <a name="allow-contributors-to-use-a-connection-for-exports"></a>Umožnite prispievateľom použiť pripojenie na exportovania

Pri nastavovaní alebo úprave pripojenia exportu vyberte, ktorí používatelia môžu použiť toto konkrétne pripojenie na definovanie [exportov](export-destinations.md). Štandardne je pripojenie dostupné pre používateľov s rolou správcu. Zmeniť **Vyberte, kto môže toto pripojenie používať** nastavenie umožňujúce používateľom s rolou prispievateľa používať toto pripojenie.

- Prispievatelia nebudú môcť zobraziť ani upraviť pripojenie. Pri vytváraní exportu uvidia iba zobrazovaný názov a jeho typ.
- Zdieľaním pripojenia umožňujete prispievateľom používať pripojenie. Prispievateľom sa po nastavení exportu zobrazia zdieľané pripojenia. Môžu spravovať každý export, ktorý používa toto konkrétne pripojenie.
- Toto nastavenie môžete zmeniť pri zachovaní exportov, ktoré už boli definované prispievateľmi.

## <a name="manage-existing-connections"></a>Spravujte existujúce pripojenia

1. Prejdite do časti **Správca** > **Pripojenia**.

1. Vyberte **Obohacovanie** alebo **Vývoz** zobrazíte zoznam pripojení obohatenia alebo exportu, typ pripojenia, kedy bolo vytvorené a kto má prístup. Zoznam pripojení môžete zoradiť podľa ľubovoľného stĺpca.

1. Výberom pripojenia zobrazíte dostupné akcie.

   - **Upraviť** spojenie.
   - [**Odstrániť**](#remove-a-connection) spojenie.

### <a name="remove-a-connection"></a>Odstrániť pripojenie

Ak pripojenie, ktoré odstraňujete, používajú obohatenia alebo exporty, najskôr ich odpojte alebo odstráňte. Dialógové okno na odstránenie vás prevedie k príslušným obohateniam alebo exportom.

> [!TIP]
> Deaktivované obohatenia a oddelené exporty sa stanú neaktívnymi. Znova ich aktivujete pridaním ďalšieho spojenia na ne na stránke [Obohatenia](enrichment-hub.md) alebo [Exporty](export-destinations.md).

1. Prejdite do časti **Správca** > **Pripojenia**.

1. Vyberte **Obohacovanie** alebo **Vývoz** tab.

1. Vyberte pripojenie, ktoré chcete odstrániť.

1. Vyberte položku **Odstrániť** z rozbaľovacej ponuky. Zobrazí sa dialógové okno s potvrdením.

   1. Ak pomocou tohto pripojenia existujú obohatenia alebo exporty, kliknutím na toto tlačidlo zobrazíte informácie o tom, čo toto pripojenie využíva.
      - **Vývoz:** Vyberte si buď **Odstrániť** vývoz, resp **Odpojte spojenie**. Odpojením pripojenia sa zachová konfigurácia exportu, ale nespustí sa, kým sa k nemu nepridá ďalšie pripojenie.
      - **Obohatenia:** Vyberte si buď **Odstrániť** alebo **Deaktivovať** obohatenia.
   1. Keď už pripojenie nemá žiadne ďalšie závislosti, vráťte sa späť na časť **Správca** > **Pripojenia** a skúste pripojenie znova odstrániť.

1. Na potvrdenie odstránenia vyberte možnosť **Odstrániť**.

## <a name="set-up-connections-with-secrets-managed-by-your-own-key-vault"></a>Nastavte si pripojenia pomocou tajomstiev, ktoré spravuje váš vlastný Key Vault

Niektoré pripojenia vyžadujú tajomstvá, ako sú kľúče API alebo heslá. Niektoré pripojenia podporujú tajomstvá uložené vo vašom vlastnom Key Vault. Získajte viac informácií o podporovaných pripojeniach a o tom, ako ich nastaviť [svoj vlastný trezor kľúčov pre Customer Insights](use-azure-key-vault.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
