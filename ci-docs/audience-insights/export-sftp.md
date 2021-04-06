---
title: Export údajov služby Customer Insights do hostiteľov protokolu SFTP
description: Prečítajte si, ako nakonfigurovať pripojenie k hostiteľovi SFTP.
ms.date: 01/27/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 9ec14fafa8f99e34b95349371298082e166535d0
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598404"
---
# <a name="connector-for-sftp-preview"></a>Konektor pre SFTP (ukážka)

Používajte svoje zákaznícke údaje v aplikáciách tretích strán tak, že ich bezpečne exportujete do hostiteľa protokolu SFTP (Secure File Transfer Protocol).

## <a name="prerequisites"></a>Predpoklady

- Dostupnosť hostiteľa SFTP a zodpovedajúcich poverení.

## <a name="connect-to-sftp"></a>Pripojenie k SFTP

1. Prejdite do ponuky **Správca** > **Ciele exportu**.

1. Pod **SFTP** vyberte **Nastavenie**.

1. Do poľa **Zobrazovaný názov** zadajte rozpoznateľný názov cieľa.

1. Uveďte **Používateľské meno**, **Heslo**, **Meno hostiteľa** a **Priečinok na export** pre váš účet SFTP.

1. Na otestovanie pripojenia vyberte **Overiť**.

1. Po úspešnom overení vyberte, či chcete exportovať svoje údaje **Komprimované ako gzip** alebo **Dekomprimované** a vyberte **oddeľovač polí** pre exportované súbory.

1. Vyberte **Súhlasím** na potvrdenie **Ochrany osobných údajov a dodržiavanie súladu s nariadeniami**.

1. Vyberte **Ďalej** a začnite konfigurovať export.

## <a name="configure-the-export"></a>Konfigurácia exportu

1. Vyberte entity, napríklad segmenty, ktoré chcete exportovať.

   > [!NOTE]
   > Každá vybraná entita bude mať pri exporte až päť výstupných súborov. 

1. Vyberte položku **Uložiť**.

## <a name="export-the-data"></a>Export údajov

Môžete [exportovať údaje na vyžiadanie](export-destinations.md). Export sa spustí aj pri každej [plánovanej obnove](system.md#schedule-tab).

## <a name="known-limitations"></a>Známe obmedzenia

- Čas spustenia exportu závisí od výkonu vášho systému. Ako minimálna konfigurácia vášho servera odporúčame dve jadrá CPU a 1 GB pamäte. 
- Export entít s až 100 miliónmi zákazníckych profilov môže trvať 90 minút pri použití odporúčanej minimálnej konfigurácie dvoch jadier CPU a 1 GB pamäte. 

## <a name="data-privacy-and-compliance"></a>Ochrana osobných údajov a dodržiavanie súladu s nariadeniami

Keď povolíte prenos údajov spoločnosti SFTP v službe Dynamics 365 Customer Insights, povoľujete tým prenos údajov mimo hranice súladu so službou Dynamics 365 Customer Insights vrátane potenciálne citlivých údajov, ako sú napríklad osobné údaje. Spoločnosť Microsoft prenesie tieto údaje na váš pokyn, ale vy ste zodpovední za zabezpečenie toho, aby cieľ exportu plnil všetky prípadné povinnosti týkajúce sa ochrany vašich osobných údajov alebo zabezpečenia. Ďalšie informácie nájdete vo [vyhlásení o ochrane súkromia spoločnosti Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Váš správca služby Dynamics 365 Customer Insights môže túto funkciu kedykoľvek prestať používať odstránením tohto cieľového umiestnenia exportu.


[!INCLUDE[footer-include](../includes/footer-banner.md)]