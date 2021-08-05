---
title: Pripojiť sa k tabuľkám v doplnku Microsoft Dataverse
description: Import údajov zo spravovaného data lake Microsoft Dataverse.
ms.date: 07/23/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.reviewer: mhart
ms.openlocfilehash: f92d64723e6a4d2fcebdbb3758519d4bfd4aeaf4
ms.sourcegitcommit: 8cc70f30baaae13dfb9c4c201a79691f311634f5
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 07/30/2021
ms.locfileid: "6692593"
---
# <a name="connect-to-data-in-a-microsoft-dataverse-managed-data-lake"></a>Pripojenie k údajom v dátovom jazere spravovanom cez Microsoft Dataverse

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Tento článok popisuje spôsob,, ako sa používatelia nástroja Dataverse môžu rýchlo pripojiť k svojim analytickým entitám v spravovanom jazere Dataverse. Musíte byť správcom organizácie Dataverse, aby ste mohli pokračovať a pozrieť si zoznam entít dostupných v spravovanom jazere.

## <a name="important-considerations"></a>Dôležité aspekty

Údaje uložené v online službách, ako napríklad Azure Data Lake Storage, môžu byť uložené na inom mieste, ako je miesto, kde sa údaje spracúvajú alebo ukladajú v rámci Dynamics 365 Customer Insights.Importovaním alebo pripojením sa k údajom uloženým v online službách súhlasíte s tým, že údaje je možné prenášať a ukladať pomocou Dynamics 365 Customer Insights.  [Ďalšie informácie nájdete v Centre dôveryhodnosti spoločnosti Microsoft.](https://www.microsoft.com/trust-center)

## <a name="connect-to-a-dataverse-managed-lake"></a>Pripojte sa k spravovanému fondu Dataverse

1. V prehľadoch cieľových skupín prejdite na **Údaje** > **Zdroje údajov**.

2. Vyberte položku **Pridať zdroj údajov**.

3. Označte položku **Pripojiť k spravovanému jazeru Microsoft Dataverse** a potom položku **Ďalšie**.

4. Zadajte **Názov** zdroja údajov a následne vyberte položku **Ďalej**. Pokyny týkajúce sa pomenovania: 
   - Začnite písmenom.
   - Používajte iba písmená a číslice. Nie je povolené zadávanie špeciálnych znakov a medzier.
   - Použite 3 až 64 znakov.

5. Poskytnite údaj **Adresa servera** pre organizáciu Dataverse a označte položku **Prihlásiť sa**.

   :::image type="content" source="media/ingest-dataverse-server-address.png" alt-text="Obrazovka v kroku prijímania údajov, kde používateľ zadáva adresu URL prostredia Dataverse.":::

6. Z dostupného zoznamu označte tabuľky, ktoré chcete použiť ako entity pre prehľady cieľovej skupiny.    

   > [!NOTE]
   > Ak sú niektoré tabuľky už označené, možno ich používajú iné aplikácie Dynamics 365 (napríklad Dynamics 365 Sales Insights alebo služba Customer Service Insights). Výber nemožno meniť. Tieto tabuľky budú dostupné ako entity po vytvorení zdroja údajov.

   :::image type="content" source="media/select-dataverse-entities.png" alt-text="Dialógové okno, so zoznamom entít v prostredí Dataverse.":::

7. Uložte svoj výber a spusťte synchronizáciu vybratých tabuliek z nástroja Dataverse. Novo pridané pripojenie nájdete na stránke **Zdroje údajov**. Bude zaradený do frontu na obnovenie a počet entít sa zobrazí ako 0, kým nebudú synchronizované všetky vybraté tabuľky.

Iba jeden zdroj údajov z prostredia môže súčasne používať to isté spravované jazero služby Dataverse.

## <a name="edit-a-dataverse-managed-lake-data-source"></a>Upravte zdroj údajov spravovaného fondu Dataverse

Výber entity môžete upraviť až po vytvorení zdroju údajov. Napríklad ak boli do entity pridané ďalšie entity Dataverse a chcete ich tiež importovať.    
Ak sa chcete pripojiť k inému dátovému jazeru Dataverse,[ vytvorte nový zdroj údajov ](#connect-to-a-dataverse-managed-lake).

1. V prehľadoch cieľových skupín prejdite na **Údaje** > **Zdroje údajov**.

2. Vedľa zdroja údajov, ktorý chcete aktualizovať, vyberte tri bodky.

3. Zo zoznamu vyberte možnosť **Upraviť**.

4. Vyberte ďalšie entity z dostupného zoznamu entít a vyberte položku **Uložiť**.

[!INCLUDE[footer-include](../includes/footer-banner.md)]