---
title: Pripojte sa k entitám v spravovanom jazere služby Common Data Service
description: Import údajov zo spravovaného data lake Common Data Service.
ms.date: 09/29/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.reviewer: adkuppa
ms.openlocfilehash: 18b6cd3fdaf5b738877a73b520b91dbc6ded40de
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267833"
---
# <a name="connect-to-data-in-a-common-data-service-managed-data-lake"></a>Pripojenie k údajom v dátovom jazere spravovanom cez Common Data Service

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Tento článok poskytuje informácie o tom, ako sa súčasní zákazníci Dynamics 365 môžu rýchlo pripojiť k svojim analytickým entitám v spravovanom jazere Common Data Service. Musíte byť správcom organizácie Common Data Service, aby ste mohli pokračovať a pozrieť si zoznam entít dostupných v spravovanom jazere.

## <a name="important-considerations"></a>Dôležité aspekty

Údaje uložené v online službách, ako napríklad Azure Data Lake Storage, môžu byť uložené na inom mieste, ako je miesto, kde sa údaje spracúvajú alebo ukladajú v rámci Dynamics 365 Customer Insights.Importovaním alebo pripojením sa k údajom uloženým v online službách súhlasíte s tým, že údaje je možné prenášať a ukladať pomocou Dynamics 365 Customer Insights.  [Ďalšie informácie nájdete v Centre dôveryhodnosti spoločnosti Microsoft.](https://www.microsoft.com/trust-center)

## <a name="connect-to-a-common-data-service-managed-lake"></a>Pripojte sa k spravovanému fondu Common Data Service

1. V prehľadoch cieľových skupín prejdite na **Údaje** > **Zdroje údajov**.

2. Vyberte položku **Pridať zdroj údajov**.

3. Stlačte možnosť **Pripojiť k Common Data Service** a stlačte **Ďalej**.

4. Zadajte **Názov** zdroja údajov a následne vyberte položku **Ďalej**. Pokyny týkajúce sa pomenovania: 
   - Začnite písmenom.
   - Používajte iba písmená a číslice. Nie je povolené zadávanie špeciálnych znakov a medzier.
   - Použite 3 až 64 znakov.

5. Zadajte **Adresa servera** pre svoju organizáciu Common Data Service a potom stlačte možnosť **Prihlásiť sa**.

   > [!div class="mx-imgBorder"]
   > ![Dialógové okno zadávania serverovej adresy Common Data Service](media/enter-CDS-org-details.png)

6. Z dostupného zoznamu vyberte entity, ktoré chcete prijať.    

   > [!NOTE]
   > Ak sú niektoré entity už vybrané, môžu ich používať iné aplikácie Dynamics 365 (napríklad Dynamics 365 Sales Insights alebo Customer Service Insights). Výber nemožno meniť. Tieto entity budú k dispozícii po vytvorení zdroja údajov.

   > [!div class="mx-imgBorder"]
   > ![Dialógové okno so zoznamom entít v organizácii Common Data Service](media/select-analytical-entities.png)

7. Uložte výber a začnite synchronizovať vybrané entity so spravovaným fondom Common Data Service. Novo pridané pripojenie nájdete na stránke **Zdroje údajov**. Bude zaradená do frontu na obnovenie a zobrazí počet entít ako 0, kým sa všetky entity nesynchronizujú.

Iba jeden zdroj údajov z prostredia môže súčasne používať to isté spravované jazero služby Common Data Service.

## <a name="edit-a-common-data-service-managed-lake-data-source"></a>Upravte zdroj údajov spravovaného fondu Common Data Service

Výber entity môžete upraviť až po vytvorení zdroju údajov. Napríklad ak boli do entity pridané ďalšie entity Common Data Service a chcete ich tiež importovať.    
Ak sa chcete pripojiť k inému Common Data Service, [vytvorte nový zdroj údajov](#connect-to-a-common-data-service-managed-lake).

1. V prehľadoch cieľových skupín prejdite na **Údaje** > **Zdroje údajov**.

2. Vedľa zdroja údajov, ktorý chcete aktualizovať, vyberte tri bodky.

3. Zo zoznamu vyberte možnosť **Upraviť**.

4. Vyberte ďalšie entity z dostupného zoznamu entít a vyberte položku **Uložiť**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]