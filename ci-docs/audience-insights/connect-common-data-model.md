---
title: Pripojte údaje z Common Data Model k účtu Azure Data Lake
description: Pracujte s údajmi z Common Data Model cez Azure Data Lake Storage.
ms.date: 05/29/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: 25de23e615704a72f6b41d98ae9418beb338e77e
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643477"
---
# <a name="connect-to-a-common-data-model-folder-using-an-azure-data-lake-account"></a>Pripojte priečinok Common Data Model použitím účtu Azure Data Lake

Tento článok poskytuje informácie o tom, ako prijímať údaje z Common Data Model pomocou vášho účtu Azure Data Lake Storage Gen2.

## <a name="important-considerations"></a>Dôležité aspekty

- Údaje vo vašom úložisku Azure Data Lake musia zodpovedať štandardu Common Data Model. Iné formáty momentálne nie sú podporované.

- Príjem údajov podporuje výhradne účty ukladacieho priestoru Azure Data Lake *Gen2*. Na príjem údajov nemôžete použiť účty ukladacieho priestoru Azure Data Lake Gen1.

- Ak chcete vykonať overenie pomocou objektu služby Azure, uistite sa, že je nakonfigurovaný vo vašom nájomníkovi. Ďalšie informácie sa dozviete v článku [Pripojenie prehľadov cieľových skupín k účtu Azure Data Lake Storage Gen2 pomocou objektu služby Azure](connect-service-principal.md).

- Azure Data Lake, ku ktorému sa chcete pripojiť a z ktorého prijímať údaje, musí byť v rovnakej oblasti Azure ako prostredie Dynamics 365 Customer Insights. Pripojenia k priečinku Common Data Model z dátového jazera v inej oblasti Azure nie sú podporované. Ak chcete spoznať oblasť Azure v prostredí, prejdite na časť **Správca** > **Systém** > **Informácie** v prehľadoch o cieľových skupinách.

- Údaje uložené v online službách sa môžu ukladať na inom mieste ako tam, kde sa údaje spracúvajú alebo ukladajú v rámci služby Dynamics 365 Customer Insights.Importovaním alebo pripojením sa k údajom uloženým v online službách súhlasíte s tým, že údaje je možné prenášať a ukladať pomocou Dynamics 365 Customer Insights.  [Ďalšie informácie nájdete v Centre dôveryhodnosti spoločnosti Microsoft.](https://www.microsoft.com/trust-center)

## <a name="connect-to-a-common-data-model-folder"></a>Pripojiť k priečinku Common Data Model

1. V prehľadoch cieľových skupín prejdite na **Údaje** > **Zdroje údajov**.

1. Vyberte položku **Pridať zdroj údajov**.

1. Vyberte položku **Pripojiť k priečinku Common Data Model**, zadajte **Názov** zdroja údajov a vyberte položku **Ďalej**.

1. Na overenie si môžete vybrať medzi použitím možnosti založenej na zdrojoch a možnosti založenej na predplatnom. Ďalšie informácie sa dozviete v článku [Pripojenie prehľadov cieľových skupín k účtu Azure Data Lake Storage Gen2 pomocou objektu služby Azure](connect-service-principal.md). Zadajte informáciu **Kontajner** a vyberte položku **Ďalej**.
   > [!div class="mx-imgBorder"]
   > ![Dialógové okno na zadávanie podrobností o pripojení k Azure Data Lake](media/enter-new-storage-details.png)

1. V dialógovom okne **Vybrať priečinok Common Data Model** vyberte súbor model.json, z ktorého chcete importovať údaje, a vyberte položku **Ďalej**.
   > [!NOTE]
   > Žiadny súbor model.json spojený s iným zdrojom údajov v prostredí sa v zozname nezobrazí.

1. Vo vybranom súbore model.json získate zoznam dostupných entít. Môžete skontrolovať a vybrať zo zoznamu dostupných entít a vybrať položku **Uložiť**. Všetky vybraté entity sa prijmú z nového zdroja údajov.
   > [!div class="mx-imgBorder"]
   > ![Dialógové okno so zoznamom entít zo súboru model.json](media/review-entities.png)

8. Uveďte, pre ktoré údajové entity chcete povoliť profilovanie údajov, a vyberte položku **Uložiť**. Profilovanie údajov umožňuje analýzy a ďalšie funkcie. Môžete vybrať celú entitu, ktorá vyberie všetky atribúty z entity, alebo môžete vybrať určité atribúty podľa vlastného výberu. V predvolenom nastavení nie je pre profilovanie údajov povolená žiadna entita.
   > [!div class="mx-imgBorder"]
   > ![Dialógové okno zobrazujúce profilovanie údajov](media/dataprofiling-entities.png)

9. Po uložení vašich výberov sa otvorí stránka **Zdroje údajov**. Teraz by ste mali vidieť pripojenie priečinka Common Data Model ako zdroja údajov.

> [!NOTE]
> Súbor model.json sa môže v rovnakom prostredí spojiť iba s jedným zdrojom údajov. Rovnaký súbor model.json je však možné použiť pre zdroje údajov vo viacerých prostrediach.

## <a name="edit-a-common-data-model-folder-data-source"></a>Úprava zdroja údajov pre Common Data Model

Môžete aktualizovať prístupový kľúč pre účet úložiska, ktoré obsahuje priečinok Common Data Model. Môžete tiež zmeniť súbor model.json. Ak sa chcete pripojiť k inému kontajneru z účtu úložiska alebo zmeniť názov účtu, musíte [vytvoriť nové pripojenie k zdroju údajov](#connect-to-a-common-data-model-folder).

1. V prehľadoch cieľových skupín prejdite na **Údaje** > **Zdroje údajov**.

2. Vedľa zdroja údajov, ktorý chcete aktualizovať, vyberte tri bodky.

3. Zo zoznamu vyberte možnosť **Upraviť**.

4. Prípadne aktualizujte **Prístupový kľúč** a vyberte položku **Ďalej**.

   ![Dialógové okno na úpravu a aktualizáciu prístupového kľúča k existujúcemu zdroju údajov](media/edit-access-key.png)

5. Prípadne môžete aktualizáciu vykonať cez pripojenie kľúča účtu na pripojenie založené na zdrojoch alebo predplatnom. Ďalšie informácie sa dozviete v článku [Pripojenie prehľadov cieľových skupín k účtu Azure Data Lake Storage Gen2 pomocou objektu služby Azure](connect-service-principal.md). Pri aktualizácii pripojenia nemôžete zmeniť informácie o **kontajneri**.
   > [!div class="mx-imgBorder"]
   > ![Dialógové okno na zadávanie podrobností o pripojení k Azure Data Lake](media/enter-existing-storage-details.png)

6. Prípadne vyberte iný súbor model.json s inou množinou entít z kontajnera.

7. Prípadne môžete vybrať ďalšie entity na príjem. Ak už neexistujú žiadne závislosti, môžete odstrániť aj všetky už vybrané entity.

   > [!IMPORTANT]
   > Ak existujú závislosti na existujúcom súbore model.json a množine entít, zobrazí sa chybová správa a vy nebudete môcť vybrať iný súbor model.json. Pred zmenou súboru model.json odstráňte tieto závislosti alebo vytvorte nový zdroj údajov so súborom model.json, ktorý chcete použiť na to, aby ste zabránili odstráneniu závislostí.

8. Prípadne môžete vybrať ďalšie atribúty alebo entity, ktoré povolia profilovanie údajov alebo zakážu tie už vybrané.   
