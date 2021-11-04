---
title: Export údajov služby Customer Insights do Správcu reklám Facebook
description: Zistite ako nakonfigurovať pripojenie a realizovať exportovanie do Facebook Ads Manager.
ms.date: 04/15/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: bb74e35799410b92b64e48e065b45efda82490ca
ms.sourcegitcommit: 31985755c7c973fb1eb540c52fd1451731d2bed2
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 10/22/2021
ms.locfileid: "7672972"
---
# <a name="export-segments-list-to-facebook-ads-manager-preview"></a>Export zoznamu segmentov do Facebook Ads Manager (verzia Preview)

Export segmentov zjednotených zákazníckych profilov do Správcu reklám Facebook, na ktorom chcete vytvárať kampane na Facebook a Instagram.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWO1aN]

## <a name="prerequisites-for-connection"></a>Predpoklad na pripojenie

- Musíte mať [**reklamné konto Facebook**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account), ktoré zahŕňa [**obchodné konto Facebook**](https://business.facebook.com/).
- Musíte byť správca [**reklamného konta Facebook**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).

## <a name="known-limitations"></a>Známe obmedzenia

- Až 10 miliónov profilov zákazníkov na jeden export do Správcu reklám Facebook.
- Export do Facebook Ads Manager je obmedzený na segmenty.
- Vytvárajte alebo aktualizujte iba vlastné cieľové skupiny v službe Facebook typu *zoznam zákazníkov*.
- Export segmentov s celkovo 10 miliónmi profilov zákazníkov môže trvať až 90 minút.

## <a name="set-up-connection-to-facebook-ads-manager"></a>Nastavenie pripojenia do Facebook Ads Manager

Predtým, ako budú môcť používatelia vytvoriť export, musí správca nakonfigurovať pripojenie k službe a umožniť prispievateľom používať pripojenie.

1. Prejdite do časti **Správca** > **Pripojenia**.

1. Stlačte možnosť **Pridať pripojenie** a stlačením možnosti **Facebook Google Ads** nakonfigurujte pripojenie.

1. Do poľa **Zobrazovaný názov** zadajte rozpoznateľný názov pripojenia. Zobrazovaný názov a typ spojenia, ktoré popisuje toto spojenie. Odporúčame zvoliť názov, ktorý vysvetľuje účel a cieľ tohto spojenia.

1. Vyberte používateľov, ktorí môžu používať toto pripojenie. Ak neurobíte nič, predvolená hodnota bude Správcovia. Viac informácií nájdete v časti [Umožnite prispievateľom použiť pripojenie na export](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Overenie pomocou služby Facebook Ads: 

   1. Výberom možnosti **Pokračovať cez Facebook** sa prihlásite do svojho reklamného konta Facebook.

   1. Povoľte povolenie **ads_management** po vykonaní overenia cez Facebook.

   1. Zvoľte **Reklamný účet Facebook**, s ktorým chcete pracovať.

   1. Vyberte si z rozbaľovacieho zoznamu možnosť **Existujúca vlastná cieľová skupina** alebo si vytvorte **novú vlastnú cieľovú skupinu**. Viac informácií nájdete v časti [**Publiká v Správcovi reklám Facebook**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).
      > [!NOTE]
      > Vlastné publiká môžete vytvárať alebo aktualizovať iba v službe Facebook typu *zoznam zákazníkov* s týmto exportom. V niektorých prípadoch sa v rozbaľovacom zozname zobrazia vlastné cieľové skupiny rôznych typov. Výber iného typu *zoznamu zákazníkov* bude mať za následok zlyhanie exportu. 

1. Prečítajte si časť **Ochrana osobných údajov a ich dodržiavanie** a stlačte možnosť **Súhlasím**.

1. Stlačte možnosť **Uložiť** a dokončite pripojenie.

## <a name="configure-an-export"></a>Nakonfigurujte export

Tento export môžete nakonfigurovať, ak máte prístup k pripojeniu tohto typu. Viac informácií nájdete na stránke [Na konfiguráciu exportu sú potrebné povolenia](export-destinations.md#set-up-a-new-export).

1. Prejdite na **Údaje** > **Exporty**.

1. Na vytvorenie nového exportu stlačte možnosť **Pridať cieľ**. 

1. V poli **Pripojenie na export** vyberte pripojenie v časti **Facebook Ads Manager**. Ak nevidíte názov tejto sekcie, nemáte k dispozícii žiadne pripojenia tohto typu.

1. V časti **Vyberte pole identifikátora kľúča** vyberte **E-mail**, **Meno a adresa** alebo **Telefón** na odoslanie so Správcu reklám Facebook. 

1. Do poľa **Zobrazovaný názov** zadajte rozpoznateľný názov pripojenia.

1. Priraďte zodpovedajúce atribúty z vašej zjednotenej entity zákazníka na vybratý identifikátor kľúča.
   > [!TIP]
   > Najlepšie šance na zabezpečenie súladu nastanú, ak vyberiete ako kľúčový identifikátor **E-mail**. Pridanie ďalších identifikátorov môže zlepšiť zosúladenie.

1. Vyberte **Pridať atribút** na mapovanie ďalších atribútov na odoslanie do Facebook Ads Manager. Atribúty z Facebook Ads Manager sú mapované pomocou nasledovných používateľských názvov: **FN** = **Krstné meno**, **LN** = **Priezvisko**, **FI** = **Prvé písmeno**, **PHONE** = **Telefón**, **GEN** = **Pohlavie**, **DOB** = **Dátum narodenia**, **ST** = **Stav**, **CT** = **Mesto**, **ZIP** = **PSČ**, **COUNTRY** = **Štát/oblasť**

1. Vyberte segmenty, ktoré chcete exportovať.

1. Vyberte položku **Uložiť**.

Uloženie exportu nespustí export okamžite.

Export prebieha s každým [plánovaným obnovením](system.md#schedule-tab). 

Môžete tiež [exportovať údaje na požiadanie](export-destinations.md#run-exports-on-demand). 

## <a name="data-privacy-and-compliance"></a>Ochrana osobných údajov a dodržiavanie súladu s nariadeniami

Keď povolíte prenos údajov do Správcu reklám Facebook v službe Dynamics 365 Customer Insights, povoľujete tým prenos údajov mimo hranice súladu so službou Dynamics 365 Customer Insights vrátane potenciálne citlivých údajov, ako sú napríklad osobné údaje. Spoločnosť Microsoft prenesie tieto údaje na váš pokyn, ale vy ste zodpovední za zabezpečenie toho, aby Reklamy Facebook plnili všetky prípadné povinnosti týkajúce sa ochrany vašich osobných údajov alebo zabezpečenia. Ďalšie informácie nájdete vo [vyhlásení o ochrane súkromia spoločnosti Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Váš správca služby Dynamics 365 Customer Insights môže túto funkciu kedykoľvek prestať používať odstránením tohto cieľového umiestnenia exportu.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
