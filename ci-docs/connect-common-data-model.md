---
title: Pripojte priečinok Common Data Model použitím účtu Azure Data Lake
description: Pracujte s údajmi z Common Data Model cez Azure Data Lake Storage.
ms.date: 05/30/2022
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-data-sources
- ci-create-data-source
- ci-attach-cdm
- customerInsights
ms.openlocfilehash: b1cdcb46df17d722ad49d361ae4c7ab34c83eeb1
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 06/29/2022
ms.locfileid: "9082269"
---
# <a name="connect-to-data-in-azure-data-lake-storage"></a>Pripojiť sa k údajom v doplnku Azure Data Lake Storage

Vkladať údaje do Dynamics 365 Customer Insights pomocou vášho Azure Data Lake Storage Účet Gen2. Príjem údajov môže byť úplný alebo prírastkový.

## <a name="prerequisites"></a>Požiadavky

- Podporuje príjem údajov Azure Data Lake Storage *Gen2* účty. Účty Data Lake Storage Gen1 nemôžete používať na prijímanie údajov.

- The Azure Data Lake Storage účet musí mať [hierarchický menný priestor povolený](/azure/storage/blobs/data-lake-storage-namespace). Údaje musia byť uložené vo formáte hierarchického priečinka, ktorý definuje koreňový priečinok a má podpriečinky pre každú entitu. Podpriečinky môžu mať priečinky s úplnými údajmi alebo s prírastkovými údajmi.

- Ak chcete vykonať overenie pomocou objektu služby Azure, uistite sa, že je nakonfigurovaný vo vašom nájomníkovi. Viac informácií nájdete v časti [Pripojte sa k Azure Data Lake Storage Účet Gen2 s principálom služby Azure](connect-service-principal.md).

- The Azure Data Lake Storage z ktorého sa chcete pripojiť a prijímať údaje, musí byť v rovnakej oblasti Azure ako Dynamics 365 Customer Insights životné prostredie. Pripojenia k priečinku Common Data Model z dátového jazera v inej oblasti Azure nie sú podporované. Ak chcete poznať oblasť prostredia Azure, prejdite na **Admin** > **Systém** > **O** v Customer Insights.

- Údaje uložené v online službách môžu byť uložené na inom mieste, než kde sa údaje spracúvajú alebo ukladajú Dynamics 365 Customer Insights.Importovaním alebo pripojením k údajom uloženým v online službách súhlasíte s tým, že údaje môžu byť prenesené a uložené s Dynamics 365 Customer Insights . [Ďalšie informácie nájdete v Centre dôveryhodnosti spoločnosti Microsoft](https://www.microsoft.com/trust-center).

- Principál služby Customer Insights musí mať jednu z nasledujúcich rolí, aby mohol pristupovať k účtu úložiska. Viac informácií nájdete v časti [Udeľte správcovi služby povolenia na prístup k účtu úložiska](connect-service-principal.md#grant-permissions-to-the-service-principal-to-access-the-storage-account).
  - Čítačka údajov objektu Blob
  - Majiteľ údajov objektu Blob
  - Prispievateľ údajov do objektu BLOB úložiska

- Údaje vo vašom úložisku Data Lake by sa mali riadiť štandardom Common Data Model pre ukladanie vašich údajov a mali by mať manifest spoločného údajového modelu, ktorý bude reprezentovať schému dátových súborov (*.csv alebo *.parquet). Manifest musí obsahovať podrobnosti o entitách, ako sú stĺpce entít a typy údajov a umiestnenie a typ súboru s údajmi. Viac informácií nájdete v časti [Manifest spoločného dátového modelu](/common-data-model/sdk/manifest). Ak manifest neexistuje, správcovia s prístupom vlastníka údajov objektu Storage Blob alebo prispievateľa údajov objektu úložiska môžu definovať schému pri prijímaní údajov.

## <a name="connect-to-azure-data-lake-storage"></a>Pripojenie k sieti Azure Data Lake Storage

1. Prejdite do **Údaje** > **Zdroje údajov**.

1. Vyberte položku **Pridať zdroj údajov**.

1. Vyberte **Úložisko dátového jazera Azure**.

   :::image type="content" source="media/data_sources_ADLS.png" alt-text="Dialógové okno na zadanie podrobností o pripojení pre Azure Data Lake." lightbox="media/data_sources_ADLS.png":::

1. Zadajte a **názov** pre zdroj údajov a voliteľné **Popis**. Názov jedinečne identifikuje zdroj údajov a odkazuje sa naň v následných procesoch a nemožno ho zmeniť.

1. Vyberte jednu z nasledujúcich možností pre **Pripojte svoje úložisko pomocou**. Viac informácií nájdete v časti [Pripojte Customer Insights k a Azure Data Lake Storage Účet Gen2 s principálom služby Azure](connect-service-principal.md).

   - **Prostriedok Azure** : Zadajte **ID zdroja** . Voliteľne, ak chcete prijímať údaje z účtu úložiska prostredníctvom súkromného prepojenia Azure, vyberte **Povoliť súkromný odkaz**. Viac informácií nájdete v časti [Súkromné odkazy](security-overview.md#private-links-tab).
   - **Predplatné Azure** : Vyberte **Predplatné** a potom **Skupina zdrojov** a **Účet úložiska**. Voliteľne, ak chcete prijímať údaje z účtu úložiska prostredníctvom súkromného prepojenia Azure, vyberte **Povoliť súkromný odkaz**. Viac informácií nájdete v časti [Súkromné odkazy](security-overview.md#private-links-tab).
  
   > [!NOTE]
   > Na vytvorenie zdroj údajov potrebujete jednu z nasledujúcich rolí pre kontajner alebo účet úložiska:
   >
   >  - Aplikácia Storage Blob Data Reader postačuje na čítanie z účtu úložiska a prijímanie údajov do Customer Insights. 
   >  - Ak chcete upravovať súbory manifestu priamo v Customer Insights, vyžaduje sa prispievateľ alebo vlastník dátového objektu úložiska.  
  
1. Vyberte názov **Kontajner** ktorý obsahuje údaje a schému (súbor model.json alebo manifest.json), z ktorého chcete importovať údaje, a vyberte **Ďalšie**.
   > [!NOTE]
   > Žiadny súbor model.json ani manifest.json spojený s iným zdrojom údajov v prostredí sa v zozname nezobrazí. Rovnaký súbor model.json alebo manifest.json je však možné použiť pre zdroje údajov vo viacerých prostrediach.

1. Ak chcete vytvoriť novú schému, prejdite na [Vytvorte nový súbor schémy](#create-a-new-schema-file).

1. Ak chcete použiť existujúcu schému, prejdite do priečinka so súborom model.json alebo manifest.cdm.json. Súbor môžete vyhľadať v adresári.

1. Vyberte súbor json a vyberte **Ďalšie**. Zobrazí sa zoznam dostupných entít.

   :::image type="content" source="media/review-entities.png" alt-text="Dialógové okno so zoznamom entít na výber":::

1. Vyberte entity, ktoré chcete zahrnúť.

   :::image type="content" source="media/ADLS_required.png" alt-text="Dialógové okno so zobrazením Povinné pre primárny kľúč":::

   > [!TIP]
   > Ak chcete upraviť entity v rozhraní na úpravu JSON, vyberte **Zobraziť viac** > **Upravte súbor schémy**. Vykonajte zmeny a vyberte **Uložiť**.

1. Pre vybrané entity, ktoré vyžadujú postupné prijímanie, **Požadovaný** zobrazuje pod **Prírastkové obnovenie**. Pre každý z týchto subjektov viď [Nakonfigurujte prírastkové obnovenie pre zdroje údajov Azure Data Lake](incremental-refresh-data-sources.md).

1. Pre vybrané entity, kde primárny kľúč nebol definovaný, **Požadovaný** zobrazuje pod **Primárny kľúč**. Pre každý z týchto subjektov:
   1. Vyberte **Požadovaný**. The **Upraviť entitu** zobrazí panel.
   1. Vyber **Primárny kľúč**. Primárny kľúč je atribút jedinečný pre entitu. Ak má byť atribút platným primárnym kľúčom, nemal by obsahovať duplicitné hodnoty, chýbajúce hodnoty ani nulové hodnoty. Ako primárne kľúče sú podporované atribúty typu reťazec, celé číslo a GUID.
   1. Voliteľne zmeňte vzor oddielu.
   1. Vyberte **Zavrieť** uložte a zatvorte panel.

1. Vyberte počet **Atribúty** pre každú zahrnutú entitu. The **Spravujte atribúty** zobrazí stránka.

   :::image type="content" source="media/dataprofiling-entities.png" alt-text="Dialógové okno na výber profilovania údajov.":::

   1. Vytvorte nové atribúty, upravte alebo odstráňte existujúce atribúty. Môžete zmeniť názov, formát údajov alebo pridať sémantický typ.
   1. Ak chcete povoliť analýzu a ďalšie funkcie, vyberte **Profilovanie údajov** pre celú entitu alebo pre špecifické atribúty. V predvolenom nastavení nie je pre profilovanie údajov povolená žiadna entita.
   1. Vyberte položku **Hotovo**.

1. Vyberte **Uložiť**. The **Zdroje dát** otvorí sa stránka s novým zdroj údajov v **Osviežujúce** postavenie.

### <a name="create-a-new-schema-file"></a>Vytvorte nový súbor schémy

1. Vyberte **Nový súbor schémy**.

1. Zadajte názov súboru a vyberte **Uložiť**.

1. Vyberte **Nová entita**. The **Nová entita** zobrazí panel.

1. Zadajte názov entity a vyberte **Umiestnenie dátových súborov**.
   - **Viaceré súbory .csv alebo .parquet** : Prejdite do koreňového priečinka, vyberte typ vzoru a zadajte výraz.
   - **Jeden súbor .csv alebo .parquet** : Prejdite na súbor .csv alebo .parquet a vyberte ho.

   :::image type="content" source="media/ADLS_new_entity_location.png" alt-text="Dialógové okno na vytvorenie novej entity so zvýrazneným umiestnením dátových súborov.":::

1. Vyberte **Uložiť**.

   :::image type="content" source="media/ADLS_new_entity_define_attributes.png" alt-text="Dialógové okno na definovanie alebo automatické generovanie atribútov.":::

1. Vyberte **definovať atribúty** manuálne pridať atribúty, alebo vyberte **automaticky ich vygenerovať**. Ak chcete definovať atribúty, zadajte názov, vyberte formát údajov a voliteľný sémantický typ. Pre automaticky generované atribúty:

   1. Po automatickom vygenerovaní atribútov vyberte **Skontrolujte atribúty**. The **Spravujte atribúty** zobrazí stránka.

   1. Uistite sa, že formát údajov je správny pre každý atribút.

   1. Ak chcete povoliť analýzu a ďalšie funkcie, vyberte **Profilovanie údajov** pre celú entitu alebo pre špecifické atribúty. V predvolenom nastavení nie je pre profilovanie údajov povolená žiadna entita.

      :::image type="content" source="media/dataprofiling-entities.png" alt-text="Dialógové okno na výber profilovania údajov.":::

   1. Vyberte položku **Hotovo**. The **Vyberte entity** zobrazí stránka.

1. Pokračujte v pridávaní entít a atribútov, ak je to možné.

1. Po pridaní všetkých entít vyberte **Zahrnúť** na zahrnutie entít do zdroj údajov príjmu.

   :::image type="content" source="media/ADLS_required.png" alt-text="Dialógové okno so zobrazením Povinné pre primárny kľúč":::

1. Pre vybrané entity, ktoré vyžadujú postupné prijímanie, **Požadovaný** zobrazuje pod **Prírastkové obnovenie**. Pre každý z týchto subjektov viď [Nakonfigurujte prírastkové obnovenie pre zdroje údajov Azure Data Lake](incremental-refresh-data-sources.md).

1. Pre vybrané entity, kde primárny kľúč nebol definovaný, **Požadovaný** zobrazuje pod **Primárny kľúč**. Pre každý z týchto subjektov:
   1. Vyberte **Požadovaný**. The **Upraviť entitu** zobrazí panel.
   1. Vyber **Primárny kľúč**. Primárny kľúč je atribút jedinečný pre entitu. Ak má byť atribút platným primárnym kľúčom, nemal by obsahovať duplicitné hodnoty, chýbajúce hodnoty ani nulové hodnoty. Ako primárne kľúče sú podporované atribúty typu reťazec, celé číslo a GUID.
   1. Voliteľne zmeňte vzor oddielu.
   1. Vyberte **Zavrieť** uložte a zatvorte panel.

1. Vyberte **Uložiť**. The **Zdroje dát** otvorí sa stránka s novým zdroj údajov v **Osviežujúce** postavenie.


## <a name="edit-an-azure-data-lake-storage-data-source"></a>Upraviť Azure Data Lake Storage zdroj údajov

Môžete aktualizovať *Pripojte sa k účtu úložiska pomocou* možnosť. Viac informácií nájdete v časti [Pripojte Customer Insights k a Azure Data Lake Storage Účet Gen2 s principálom služby Azure](connect-service-principal.md). Ak sa chcete pripojiť k inému kontajneru z účtu úložiska alebo zmeniť názov účtu, musíte [vytvoriť nové pripojenie k zdroju údajov](#connect-to-azure-data-lake-storage).

1. Prejdite do **Údaje** > **Zdroje údajov**.

1. Vedľa zdroj údajov, ktorý chcete aktualizovať, vyberte **Upraviť**.

   :::image type="content" source="media/data_sources_edit_ADLS.png" alt-text="Dialógové okno na úpravu Azure Data Lake zdroj údajov.":::

1. Zmeňte ktorúkoľvek z nasledujúcich informácií:

   - **Opis**
   - **Pripojte svoje úložisko pomocou** a informácie o pripojení. Pri aktualizácii pripojenia nemôžete zmeniť informácie o **kontajneri**.
      > [!NOTE]
      > K účtu úložiska alebo kontajneru musí byť priradená jedna z nasledujúcich rolí:
        > - Čítačka údajov objektu Blob
        > - Majiteľ údajov objektu Blob
        > - Prispievateľ údajov do objektu BLOB úložiska

   - **Povoliť súkromný odkaz** ak chcete prijímať údaje z účtu úložiska prostredníctvom súkromného prepojenia Azure. Viac informácií nájdete v časti [Súkromné odkazy](security-overview.md#private-links-tab).

1. Vyberte **Ďalej**.
1. Zmeňte čokoľvek z nasledujúceho:
   - Prejdite do iného súboru model.json alebo manifest.json s inou množinou entít z kontajnera.
   - Ak chcete pridať ďalšie entity na príjem, vyberte **Nová entita**.
   - Ak chcete odstrániť už vybraté entity, ak neexistujú žiadne závislosti, vyberte entitu a **Odstrániť**.
      > [!IMPORTANT]
      > Ak existujú závislosti na existujúcom súbore model.json alebo manifest.json a množine entít, zobrazí sa chybové hlásenie a nemôžete vybrať iný súbor model.json alebo manifest.json. Pred zmenou súboru model.json alebo manifest.json tieto závislosti odstráňte alebo vytvorte nový zdroj údajov so súborom model.json alebo manifest.json, ktorý chcete použiť, aby ste sa vyhli odstráneniu závislostí.
   - Ak chcete zmeniť umiestnenie dátového súboru alebo primárny kľúč, vyberte **Upraviť**.
   - Ak chcete zmeniť údaje o prírastkovom príjme, pozrite si časť [Nakonfigurujte prírastkové obnovenie pre zdroje údajov Azure Data Lake](incremental-refresh-data-sources.md)

1. Vyberte **Atribúty** pridať alebo zmeniť atribúty alebo povoliť profilovanie údajov. Potom vyberte položku **Hotovo**.

1. Kliknite **Uložiť** aplikujte zmeny a vráťte sa do **Zdroje dát** stránku.
