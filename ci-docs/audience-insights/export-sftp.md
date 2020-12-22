---
title: Export údajov služby Customer Insights do hostiteľov protokolu SFTP
description: Prečítajte si, ako nakonfigurovať pripojenie k hostiteľovi SFTP.
ms.date: 06/05/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: c2529744d7a26a06324b79cad6a8001d75903545
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643522"
---
# <a name="connector-for-sftp-preview"></a>Konektor pre SFTP (ukážka)

Používajte svoje zákaznícke údaje v aplikáciách tretích strán tak, že ich bezpečne exportujete do hostiteľa protokolu SFTP (Secure File Transfer Protocol).

## <a name="prerequisites"></a>Predpoklady

- Dostupnosť hostiteľa SFTP a zodpovedajúce poverenia.

## <a name="connect-to-sftp"></a>Pripojenie k SFTP

1. Prejdite do ponuky **Správca** > **Ciele exportu**.

1. Pod **SFTP** vyberte **Nastavenie**.

1. Do poľa **Zobrazovaný názov** zadajte rozpoznateľný názov cieľa.

1. Uveďte **Používateľské meno**, **Heslo** a **Meno hostiteľa** pre váš účet SFTP. Príklad: Ak je koreňovým priečinkom vášho servera SFTP /root/folder a chcete exportovať údaje do /root/folder/ci_export_destination_folder, hostiteľom by mal byť sftp://<server_address>/ci_export_destination_folder".

1. Na otestovanie pripojenia vyberte **Overiť**.

1. Po úspešnom overení vyberte, či chcete exportovať údaje **skomprimované** alebo **dekomprimované** a vyberte **oddeľovač poľa** pre exportované súbory.

1. Vyberte **Súhlasím** na potvrdenie **Ochrany osobných údajov a dodržiavanie súladu s nariadeniami**.

1. Vyberte **Ďalej** a začnite konfigurovať export.

## <a name="configure-the-connection"></a>Konfigurácia pripojenia

1. Vyberte **atribúty zákazníka**, ktoré chcete exportovať. Môžete exportovať jeden alebo viac atribútov.

1. Vyberte **Ďalej**.

1. Vyberte segmenty, ktoré chcete exportovať.

1. Vyberte položku **Uložiť**.

## <a name="export-the-data"></a>Export údajov

Môžete [exportovať údaje na vyžiadanie](export-destinations.md). Export sa spustí aj pri každej [plánovanej obnove](system.md#schedule-tab).

## <a name="data-privacy-and-compliance"></a>Ochrana osobných údajov a dodržiavanie súladu s nariadeniami

Keď povolíte prenos údajov spoločnosti SFTP v službe Dynamics 365 Customer Insights, povoľujete tým prenos údajov mimo hranice súladu so službou Dynamics 365 Customer Insights vrátane potenciálne citlivých údajov, ako sú napríklad osobné údaje. Spoločnosť Microsoft prenesie tieto údaje na váš pokyn, ale vy ste zodpovední za zabezpečenie toho, aby cieľ exportu plnil všetky prípadné povinnosti týkajúce sa ochrany vašich osobných údajov alebo zabezpečenia. Ďalšie informácie nájdete vo [vyhlásení o ochrane súkromia spoločnosti Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Váš správca služby Dynamics 365 Customer Insights môže túto funkciu kedykoľvek prestať používať odstránením tohto cieľového umiestnenia exportu.
