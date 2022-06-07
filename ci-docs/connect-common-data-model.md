---
title: Pripojte údaje z Common Data Model k účtu Azure Data Lake
description: Pracujte s údajmi z Common Data Model cez Azure Data Lake Storage.
ms.date: 05/24/2022
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-data-sources
- ci-create-data-source
- ci-attach-cdm
- customerInsights
ms.openlocfilehash: 2e8564950a3269180a85f80fb736d2dcbd1b03b6
ms.sourcegitcommit: f5af5613afd9c3f2f0695e2d62d225f0b504f033
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 06/01/2022
ms.locfileid: "8833404"
---
# <a name="connect-to-a-common-data-model-folder-using-an-azure-data-lake-account"></a>Pripojte priečinok Common Data Model použitím účtu Azure Data Lake

Tento článok poskytuje informácie o tom, ako doň prijímať údaje Dynamics 365 Customer Insights z priečinka Common Data Model pomocou vášho Azure Data Lake Storage Účet Gen2.

## <a name="important-considerations"></a>Dôležité aspekty

- Údaje vo vašom úložisku Azure Data Lake musia zodpovedať štandardu Common Data Model. Iné formáty momentálne nie sú podporované.

- Príjem údajov podporuje výhradne účty ukladacieho priestoru Azure Data Lake *Gen2*. Na príjem údajov nemôžete použiť účty ukladacieho priestoru Azure Data Lake Gen1.

- Účet úložiska Azure Data Lake musí mať [hierarchický menný priestor povolený](/azure/storage/blobs/data-lake-storage-namespace).

- Ak chcete vykonať overenie pomocou objektu služby Azure, uistite sa, že je nakonfigurovaný vo vašom nájomníkovi. Ďalšie informácie nájdete v časti [Pripojte sa k Azure Data Lake Storage Účet Gen2 s principálom služby Azure](connect-service-principal.md).

- Azure Data Lake, ku ktorému sa chcete pripojiť a z ktorého prijímať údaje, musí byť v rovnakej oblasti Azure ako prostredie Dynamics 365 Customer Insights. Pripojenia k priečinku Common Data Model z dátového jazera v inej oblasti Azure nie sú podporované. Ak chcete poznať oblasť prostredia Azure, prejdite na **Admin** > **systém** > **O** v Customer Insights.

- Údaje uložené v online službách môžu byť uložené na inom mieste, než kde sa údaje spracúvajú alebo ukladajú Dynamics 365 Customer Insights.Importovaním alebo pripojením k údajom uloženým v online službách súhlasíte s tým, že údaje môžu byť prenesené a uložené s Dynamics 365 Customer Insights . [Ďalšie informácie nájdete v Centre dôveryhodnosti spoločnosti Microsoft](https://www.microsoft.com/trust-center).

## <a name="connect-to-a-common-data-model-folder"></a>Pripojiť k priečinku Common Data Model

1. Prejdite do **Údaje** > **Zdroje údajov**.

1. Vyberte položku **Pridať zdroj údajov**.

1. Vyberte **Úložisko dátového jazera Azure**, zadajte a **názov** pre zdroj údajov, potom vyberte **Ďalšie**.

   - Ak sa zobrazí výzva, vyberte jednu zo vzorových množín údajov, ktoré sa týkajú vášho odvetvia, a potom vyberte **Ďalšie**.

1. Na overenie si môžete vybrať medzi použitím možnosti založenej na zdrojoch a možnosti založenej na predplatnom. Ďalšie informácie nájdete v časti [Pripojte sa k Azure Data Lake Storage Účet Gen2 s principálom služby Azure](connect-service-principal.md). Zadajte **Adresa servera**, vyberte **Prihlásiť sa** a potom vyberte **Ďalšie**.
   > [!div class="mx-imgBorder"]
   > ![Dialógové okno na zadanie nových podrobností pripojenia pre Azure Data Lake.](media/enter-new-storage-details.png)
   > [!NOTE]
   > Pre kontajner na účte úložiska potrebujete jednu z nasledujúcich rolí a vytvorte zdroj údajov:
   >
   >  - Storage Blob Data Reader postačuje na čítanie z účtu úložiska a prijímanie údajov do Customer Insights. 
   >  - Ak chcete upravovať súbory manifestu priamo v Customer Insights, vyžaduje sa prispievateľ alebo vlastník dátového objektu úložiska.

1. V dialógovom okne **Vybrať priečinok Common Data Model** vyberte súbor model.json alebo manifest.json, z ktorého chcete importovať údaje, a vyberte položku **Ďalej**.
   > [!NOTE]
   > Žiadny súbor model.json ani manifest.json spojený s iným zdrojom údajov v prostredí sa v zozname nezobrazí.

1. Vo vybratom súbore model.json alebo manifest.json sa zobrazí zoznam dostupných entít. Skontrolujte a vyberte zo zoznamu dostupných entít, potom vyberte **Uložiť**. Všetky vybraté entity sa prijmú z nového zdroja údajov.
   > [!div class="mx-imgBorder"]
   > ![Dialógové okno so zoznamom entít zo súboru model.json.](media/review-entities.png)

1. Označte, ktoré údajové entity chcete povoliť profilovanie údajov, a potom vyberte **Uložiť**. Profilovanie údajov umožňuje analýzy a ďalšie funkcie. Môžete vybrať celú entitu, ktorá vyberie všetky atribúty z entity, alebo môžete vybrať určité atribúty podľa vlastného výberu. V predvolenom nastavení nie je pre profilovanie údajov povolená žiadna entita.
   > [!div class="mx-imgBorder"]
   > ![Dialógové okno zobrazujúce profilovanie údajov.](media/dataprofiling-entities.png)

1. Po uložení vašich výberov sa otvorí stránka **Zdroje údajov**. Teraz by ste mali vidieť pripojenie priečinka Common Data Model ako zdroja údajov.

> [!NOTE]
> Súbor model.json alebo manifest.json sa môže v rovnakom prostredí spojiť iba s jedným zdrojom údajov. Rovnaký súbor model.json alebo manifest.json je však možné použiť pre zdroje údajov vo viacerých prostrediach.

## <a name="edit-a-common-data-model-folder-data-source"></a>Úprava zdroja údajov pre Common Data Model

Môžete aktualizovať prístupový kľúč pre účet úložiska, ktoré obsahuje priečinok Common Data Model. Môžete tiež zmeniť súbor model.json alebo manifest.json. Ak sa chcete pripojiť k inému kontajneru z účtu úložiska alebo zmeniť názov účtu, musíte [vytvoriť nové pripojenie k zdroju údajov](#connect-to-a-common-data-model-folder).

1. Prejdite do **Údaje** > **Zdroje údajov**.

2. Vedľa zdroj údajov, ktorý chcete aktualizovať, vyberte zvislú elipsu (&vellip;).

3. Zo zoznamu vyberte možnosť **Upraviť**.

4. Prípadne aktualizujte **Prístupový kľúč** a vyberte položku **Ďalej**.

   ![Dialógové okno na úpravu a aktualizáciu prístupového kľúča k existujúcemu zdroju údajov.](media/edit-access-key.png)

5. Prípadne môžete aktualizáciu vykonať cez pripojenie kľúča účtu na pripojenie založené na zdrojoch alebo predplatnom. Ďalšie informácie nájdete v časti [Pripojte sa k Azure Data Lake Storage Účet Gen2 s principálom služby Azure](connect-service-principal.md). Pri aktualizácii pripojenia nemôžete zmeniť informácie o **kontajneri**.
   > [!div class="mx-imgBorder"]

   > ![Dialógové okno na zadanie podrobností pripojenia pre Azure Data Lake k existujúcemu účtu úložiska.](media/enter-existing-storage-details.png)

6. Voliteľne môžete z kontajnera zvoliť iný súbor model.json alebo manifest.json s inou množinou entít.

7. Prípadne môžete vybrať ďalšie entity na príjem. Ak už neexistujú žiadne závislosti, môžete odstrániť aj všetky už vybrané entity.

   > [!IMPORTANT]
   > Ak existujú závislosti na existujúcom súbore model.json alebo manifest.json a množine entít, zobrazí sa chybové hlásenie a nemôžete vybrať iný súbor model.json alebo manifest.json. Pred zmenou súboru model.json alebo manifest.json tieto závislosti odstráňte alebo vytvorte nový zdroj údajov so súborom model.json alebo manifest.json, ktorý chcete použiť, aby ste sa vyhli odstráneniu závislostí.

8. Prípadne môžete vybrať ďalšie atribúty alebo entity, ktoré povolia profilovanie údajov alebo zakážu tie už vybrané.

[!INCLUDE [footer-include](includes/footer-banner.md)]
