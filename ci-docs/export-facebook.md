---
title: Exportovať segmenty do Facebook Správca reklám (ukážka) (obsahuje video)
description: Zistite ako nakonfigurovať pripojenie a realizovať exportovanie do Facebook Ads Manager.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: c7a4b1be1c959d70fad929b56452169b40e5b592
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 10/27/2022
ms.locfileid: "9724635"
---
# <a name="export-segments-to-facebook-ads-manager-preview"></a>Exportovať segmenty do Facebook Správca reklám (ukážka)

Export segmentov zjednotených zákazníckych profilov do Správcu reklám Facebook, na ktorom chcete vytvárať kampane na Facebook a Instagram.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWO1aN]

## <a name="prerequisites"></a>Požiadavky

- A [Facebook Reklamy účet](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) ktorý zahŕňa a [Facebook Podnikateľský účet](https://business.facebook.com/).
- Oprávnenia správcu na [Facebook Reklamy účet](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).
- Používateľ, ktorý nastavuje pripojenie v Customer Insights, musí prijať vlastné podmienky publika.

## <a name="known-limitations"></a>Známe obmedzenia

- Až 10 miliónov zákazníckych profilov na export do Facebook Správca reklám, čo môže trvať až 90 minút.
- Iba segmenty.
- Facebook Integrácia reklám nepodporuje používateľov s viac ako 25 reklamnými účtami.
- Facebook *zoznam zákazníkov* zadajte [vlastné publiká](https://www.facebook.com/business/help/744354708981227?id=2469097953376494) iba.
  > [!NOTE]
  > V niektorých prípadoch môžete v rozbaľovacom zozname vidieť vlastné publiká rôznych typov. Ak vyberiete iný typ než *zoznam zákazníkov*, export zlyhá.

## <a name="set-up-connection-to-facebook-ads-manager"></a>Nastavenie pripojenia do Facebook Ads Manager

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Prejdite do časti **Správca** > **Pripojenia**.

1. Vyberte **Pridať pripojenie** a vyberte si **Facebook Správca reklám**.

1. Do poľa **Zobrazovaný názov** zadajte rozpoznateľný názov pripojenia. Zobrazovaný názov a typ spojenia, ktoré popisuje toto spojenie. Odporúčame zvoliť názov, ktorý vysvetľuje účel a cieľ tohto spojenia.

1. [Povoliť prispievateľom používať pripojenie na exporty](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Overenie pomocou služby Facebook Ads:

   1. Výberom možnosti **Pokračovať cez Facebook** sa prihlásite do svojho reklamného konta Facebook.

   1. Povoľte povolenie **ads_management** po vykonaní overenia cez Facebook.

   1. Zvoľte **Reklamný účet Facebook**, s ktorým chcete pracovať.

   1. Vyberte si z rozbaľovacieho zoznamu možnosť **Existujúca vlastná cieľová skupina** alebo si vytvorte **novú vlastnú cieľovú skupinu**.

1. Skontrolujte [ochrana osobných údajov a dodržiavanie predpisov](connections.md#data-privacy-and-compliance) a vyberte **Súhlasím**.

1. Stlačte možnosť **Uložiť** a dokončite pripojenie.

## <a name="configure-an-export"></a>Nakonfigurujte export

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Prejdite na **Údaje** > **Exporty**.

1. Vyberte **Pridať export**.

1. V **Pripojenie na export** vyberte spojenie z poľa Facebook Sekcia Správca reklám. Ak nie je k dispozícii pripojenie, kontaktujte správcu.

1. Zadajte názov exportu.

1. V **Pripojte dáta** pole, vyberte **Email**, **a adresa**, alebo **Telefón** poslať komu Facebook Správca reklám.

1. Priraďte zodpovedajúce atribúty z vašej zjednotenej entity zákazníka na vybratý identifikátor kľúča.
   > [!TIP]
   > Najlepšie šance na zabezpečenie súladu nastanú, ak vyberiete ako kľúčový identifikátor **E-mail**. Pridanie ďalších identifikátorov môže zlepšiť zosúladenie.

1. Vyberte **Pridať atribút** na mapovanie ďalších atribútov na odoslanie do Facebook Ads Manager. Atribúty z Facebook Ads Manager sú mapované pomocou nasledovných používateľských názvov: **FN** = **Krstné meno**, **LN** = **Priezvisko**, **FI** = **Prvé písmeno**, **PHONE** = **Telefón**, **GEN** = **Pohlavie**, **DOB** = **Dátum narodenia**, **ST** = **Stav**, **CT** = **Mesto**, **ZIP** = **PSČ**, **COUNTRY** = **Štát/oblasť**

1. Vyberte segmenty, ktoré chcete exportovať.

1. Vyberte **Uložiť**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
