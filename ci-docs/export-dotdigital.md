---
title: Export segmentov do DotDigital (verzia Preview)
description: Zistite ako nakonfigurovať pripojenie a realizovať exportovanie do DotDigital.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: cabaea84e31f8fe97bc558a8dca8d93bc40f43b7
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196091"
---
# <a name="export-segments-to-dotdigital-preview"></a>Export segmentov do DotDigital (verzia Preview)

Exportujte segmenty zjednotených profilov zákazníkov do adresárov DotDigital a použite ich na kampane, e-mailový marketing a na vytváranie segmentov zákazníkov cez DotDigital.

## <a name="prerequisites"></a>Požiadavky

- A [Účet DotDigital](https://dotdigital.com/) a [Používateľ API](https://support.dotdigital.com/hc/articles/115001718730-How-do-I-create-an-API-user).
- ID DotDigital od a [Nový](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book) alebo existujúci adresár v DotDigital. ID nájdete v adrese URL, keď vyberiete a otvoríte adresár.
- [Konfigurované segmenty](segments.md) v Customer Insights.
- Zjednotené profily zákazníkov v exportovaných segmentoch obsahujú pole predstavujúce e-mailovú adresu.

## <a name="known-limitations"></a>Známe obmedzenia

- Až 1 milión zákazníckych profilov na export do DotDigital, ktorého dokončenie môže trvať až tri hodiny z dôvodu obmedzení na strane poskytovateľa. Počet zákazníckych profilov, ktoré môžete exportovať do DotDigital, závisí od vašej zmluvy s DotDigital.
- Iba segmenty.

## <a name="set-up-connection-to-dotdigital"></a>Nastavenie pripojenia k DotDigital

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Prejdite do časti **Správca** > **Pripojenia**.

1. Vyberte **Pridať pripojenie** a vyberte si **DotDigital**.

1. Do poľa **Zobrazovaný názov** zadajte rozpoznateľný názov pripojenia. Zobrazovaný názov a typ spojenia, ktoré popisuje toto spojenie. Odporúčame zvoliť názov, ktorý vysvetľuje účel a cieľ tohto spojenia.

1. Vyberte používateľov, ktorí môžu používať toto pripojenie. Predvolene sú to iba správcovia. Viac informácií nájdete v časti [Umožnite prispievateľom použiť pripojenie na export](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Zadajte **používateľské meno a heslo pre API DotDigital**.

1. Zadajte svoje **ID adresára DotDigital**.

1. Skontrolujte [ochrana osobných údajov a dodržiavanie predpisov](connections.md#data-privacy-and-compliance) a vyberte **Súhlasím**.

1. Vyberte **Pripojte sa** na inicializáciu pripojenia.

1. Vyberte položku **Pridať samého seba ako používateľa exportu** a uveďte svoje poverenia pre Customer Insights.

1. Stlačte možnosť **Uložiť** a dokončite pripojenie.

## <a name="configure-an-export"></a>Nakonfigurujte export

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Prejdite na **Údaje** > **Exporty**.

1. Vyberte **Pridať export**.

1. V poli **Pripojenie na export** vyberte pripojenie v časti DotDigital. Ak nie je k dispozícii pripojenie, kontaktujte správcu.

1. Zadajte názov exportu.

1. V sekcii **Párovanie údajov** v poli **E-mail** vyberte pole, ktoré predstavuje e-mailovú adresu zákazníka.

1. Voliteľne exportujte **krstné meno**, **·**, **meno**, **·**, a **PSČ**.

1. Vyberte segmenty, ktoré chcete exportovať.

1. Vyberte **Uložiť**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

V DotDigital nájdite svoje segmenty v [DotDigital adresáre](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).

[!INCLUDE [footer-include](includes/footer-banner.md)]
