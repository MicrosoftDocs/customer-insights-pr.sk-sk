---
title: Pripojenie k údajom v dátovom jazere spravovanom cez Microsoft Dataverse
description: Import údajov zo spravovaného data lake Microsoft Dataverse.
ms.date: 07/26/2022
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.reviewer: v-wendysmith
searchScope:
- ci-dataverse
- customerInsights
ms.openlocfilehash: b21150a1c51bdad35250cae7fde7f38a014ec876
ms.sourcegitcommit: 5807b7d8c822925b727b099713a74ce2cb7897ba
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 07/28/2022
ms.locfileid: "9206972"
---
# <a name="connect-to-data-in-a-microsoft-dataverse-managed-data-lake"></a>Pripojenie k údajom v dátovom jazere spravovanom cez Microsoft Dataverse

Microsoft Dataverse používatelia sa môžu rýchlo pripojiť k analytickým entitám v a Microsoft Dataverse spravované jazero. Iba jeden zdroj údajov z prostredia môže súčasne používať to isté spravované jazero služby Dataverse.

> [!NOTE]
> Musíte byť správcom na Dataverse organizáciu pokračovať a zobraziť zoznam subjektov dostupných v spravovanom jazere.

## <a name="prerequisites"></a>Požiadavky

- Údaje uložené v online službách, ako napríklad Azure Data Lake Storage, môžu byť uložené na inom mieste, ako je miesto, kde sa údaje spracúvajú alebo ukladajú v rámci Dynamics 365 Customer Insights.Importovaním alebo pripojením k údajom uloženým v online službách súhlasíte s tým, že údaje môžu byť prenesené a uložené s Dynamics 365 Customer Insights . [Ďalšie informácie nájdete v Centre dôveryhodnosti spoločnosti Microsoft](https://www.microsoft.com/trust-center).

- Iba Dataverse subjekty s [sledovanie zmien](/power-platform/admin/enable-change-tracking-control-data-synchronization) povolené sú viditeľné. Tieto entity je možné exportovať do Dataverse -spravované dátové jazero a používané v Customer Insights. Po vybalení Dataverse tabuľky majú predvolene povolené sledovanie zmien. Pre vlastné tabuľky musíte zapnúť sledovanie zmien. Ak chcete skontrolovať, či a Dataverse v tabuľke je povolené sledovanie zmien, prejdite na [Power Apps](https://make.powerapps.com) > **Údaje** > **Tabuľky**. Nájdite tabuľku, ktorá vás zaujíma, a vyberte ju. Ísť do **nastavenie** > **Pokročilé nastavenia** a preskúmať **Sledovanie zmien** nastavenie.

## <a name="connect-to-a-dataverse-managed-lake"></a>Pripojte sa k spravovanému fondu Dataverse

1. Prejdite do **Údaje** > **Zdroje údajov**.

1. Vyberte položku **Pridať zdroj údajov**.

1. Vyberte položku **Microsoft Dataverse**.

1. Zadajte a **názov** pre zdroj údajov a voliteľné **Popis**.

1. Poskytnite údaj **Adresa servera** pre organizáciu Dataverse a označte položku **Prihlásiť sa**.

1. Z dostupného zoznamu vyberte tabuľky, ktoré chcete prijať ako entity do Customer Insights.

   > [!NOTE]
   > Ak sú niektoré tabuľky už označené, možno ich používajú iné aplikácie Dynamics 365 (napríklad Dynamics 365 Sales Insights alebo služba Customer Service Insights). Výber nemožno meniť. Tieto tabuľky budú dostupné ako entity po vytvorení zdroja údajov.

    :::image type="content" source="media/select-dataverse-entities.png" alt-text="Dialógové okno, so zoznamom entít v prostredí Dataverse.":::

1. Uložte svoj výber a spusťte synchronizáciu vybratých tabuliek z nástroja Dataverse. Novo pridané pripojenie nájdete na stránke **Zdroje údajov**. Bude zaradený do frontu na obnovenie a počet entít sa zobrazí ako 0, kým nebudú synchronizované všetky vybraté tabuľky.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

Načítanie údajov môže chvíľu trvať. Po úspešnom obnovení môžu byť prijaté údaje skontrolované z [**entity**](entities.md) stránku.

## <a name="edit-a-dataverse-managed-lake-data-source"></a>Upravte zdroj údajov spravovaného fondu Dataverse

Výber entity môžete upraviť až po vytvorení zdroju údajov. Napríklad ak boli do entity pridané ďalšie entity Dataverse a chcete ich tiež importovať.
Ak sa chcete pripojiť k inému dátovému jazeru Dataverse,[ vytvorte nový zdroj údajov ](#connect-to-a-dataverse-managed-lake).

1. Prejdite do **Údaje** > **Zdroje údajov**.

1. Vedľa zdroj údajov, ktorý chcete aktualizovať, vyberte **Upraviť**.

1. Vyberte ďalšie entity z dostupného zoznamu entít.

1. Kliknite **Uložiť** aplikujte zmeny a vráťte sa na stránku **Zdroje dát** stránku.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
