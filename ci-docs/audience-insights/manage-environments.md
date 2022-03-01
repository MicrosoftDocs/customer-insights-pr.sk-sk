---
title: Slúži na vytvorenie a spravovanie prostredí
description: Zistite, ako sa môžete zaregistrovať do služby a spravovať prostredia.
ms.date: 06/15/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: 904ce68336cba4b7a4d5a37692b72d091400559d
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 06/24/2021
ms.locfileid: "6304899"
---
# <a name="manage-environments"></a>Správa prostredí

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Tento článok vysvetľuje, ako môžete vytvoriť novú organizáciu a ako zriadiť prostredie.

## <a name="sign-up-and-create-an-organization"></a>Zaregistrujte sa a vytvorte organizáciu

1. Prejsť na webovú lokalitu [Dynamics 365 Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/).

2. Vyberte položku **Začíname**.

3. Vyberte preferovaný scenár registrácie a zodpovedajúci odkaz.

4. Prijmite zmluvné podmienky a výberom možnosti **Pokračovať** začnite vytvárať organizáciu.

5. Po vytvorení prostredia budete presmerovaní do [Customer Insights](https://home.ci.ai.dynamics.com).

6. Pomocou demonštračného prostredia preskúmajte aplikáciu alebo vytvorte nové prostredie podľa krokov v nasledujúcej sekcii.

7. Po špecifikácii nastavení prostredia vyberte položku **vytvoriť**.

8. Po úspešnom vytvorení prostredia budete prihlásení.

## <a name="create-an-environment-in-an-existing-organization"></a>Vytvorenie prostredia v existujúcej organizácii

Existujú dva spôsoby vytvorenia nového prostredia. Môžete buď špecifikovať úplne novú konfiguráciu alebo môžete skopírovať niektoré nastavenia konfigurácie z existujúceho prostredia.

> [!NOTE]
> Organizácie môžu vytvárať *dva* prostredia pre každú licenciu Customer Insights. Ak vaša organizácia zakúpi viac ako jednu licenciu, [kontaktujte náš tím podpory](https://go.microsoft.com/fwlink/?linkid=2079641) a zvýšte si počet dostupných prostredí. Ďalšie informácie o kapacite a prídavnej kapacite nájdete v stiahnutom materiáli [Sprievodca licenciami pre Dynamics 365](https://go.microsoft.com/fwlink/?LinkId=866544).

Vytvorenie prostredia:

1. Vyberte nástroj na výber **Prostredia** v hlavičke aplikácie.

1. Vyberte **Nové**.

   > [!div class="mx-imgBorder"]
   > ![Nastavenia prostredia.](media/environment-settings-dialog.png)

1. V dialógovom okne **Vytvorenie prostredia** vyberte možnosť **Nové prostredie**.

   Ak chcete [kopírovať údaje z aktuálneho prostredia](#considerations-for-copy-configuration-preview), vyberte **Kopírovať z existujúceho prostredia**. Zobrazí sa zoznam všetkých dostupných prostredí vo vašej organizácii, z ktorých môžete kopírovať údaje.

1. Uveďte nasledujúce podrobnosti:
   - **Názov**: Názov tohto prostredia. Toto pole je už vyplnené, ak ste skopírovali existujúce prostredie, ale môžete ho zmeniť.
   - **Typ**: Vyberte, či chcete vytvoriť výrobné alebo izolované prostredie.
   - **Región**: Región, v ktorom je služba nasadená a hosťovaná.
   
1. Voliteľne môžete vybrať **Rozšírené nastavenia**:

   - **Uložiť všetky údaje do**: Určuje, kam sa majú ukladať výstupné údaje vygenerované z Customer Insights. Budete mať dve možnosti: **Úložisko Customer Insights** (Azure Data Lake spravované tímom Customer Insights) a **Azure Data Lake Storage** (vaše vlastné úložisko Azure Data Lake Storage). V predvolenom nastavení je vybraná možnosť úložiska Customer Insights.

     > [!NOTE]
     > Uložením údajov do Azure Data Lake Storage súhlasíte s tým, že údaje budú prenesené a uložené v príslušnom geografickom umiestnení pre dané konto ukladacieho priestoru v službe Azure, ktoré sa môže líšiť od umiestnenia, v ktorom sú údaje uložené v aplikácii Dynamics 365 Customer Insights. [Ďalšie informácie nájdete v centre dôveryhodnosti spoločnosti Microsoft.](https://www.microsoft.com/trust-center)
     >
     > V súčasnosti sú prijaté entity vždy uložené v objekte Data Lake spravovanom službou Customer Insights. 
     > 
     > Podporujeme iba účty Azure Data Lake Storage z rovnakej oblasti Azure ako z tej, ktorú ste vybrali pri vytváraní prostredia. 
     > 
     > Podporujeme iba účty Azure Data Lake Storage, ktoré majú povolený hierarchický priestor názvov.


   - V prípade možnosti Azure Data Lake Storage si môžete vybrať medzi voľbou založenou na zdrojoch a voľbou autentifikácie založenou na predplatnom. Ďalšie informácie sa dozviete v článku [Pripojenie prehľadov cieľových skupín k účtu Azure Data Lake Storage Gen2 pomocou objektu služby Azure](connect-service-principal.md). Názov **kontajnera** sa nedá zmeniť a bude `customerinsights`.
   
   - Ak chcete použiť [predikcie](predictions.md), nakonfigurovať zdieľanie údajov s Microsoft Dataverse, alebo povoliť príjem údajov z lokálnych zdrojov údajov, uveďte adresu URL prostredia Microsoft Dataverse v časti **Konfigurácia zdieľania údajov s Microsoft Dataverse a aktivujte ďalšie funkcie**. Vyberte **Povoliť zdieľanie údajov** na zdieľanie výstupných údajov Customer Insights s so spravovaným Microsoft Dataverse Data Lake.

     > [!NOTE]
     > - Zdieľanie údajov so spravovaným Microsoft Dataverse Data Lake nie je momentálne podporované, keď ukladáte všetky údaje do svojho Azure Data Lake Storage.
     > - [Predikcia chýbajúcich hodnôt v entite](predictions.md) nie je momentálne podporovaná, keď v súčasnosti povolíte zdieľanie údajov so spravovaným Microsoft Dataverse Data Lake.

     > [!div class="mx-imgBorder"]
     > ![Možnosti konfigurácie, ktoré umožnia zdieľanie údajov s Microsoft Dataverse.](media/datasharing-with-DataverseMDL.png)

   Keď spustíte procesy, ako je napríklad príjem údajov alebo vytváranie segmentov, vo vyššie uvedenom účte úložiska sa vytvoria zodpovedajúce priečinky. Dátové súbory a súbory model.json sa vytvoria a pridajú do priečinkov na základe názvu procesu.

   Ak vytvoríte viac prostredí služby Customer Insights a rozhodnete sa uložiť výstupné entity z týchto prostredí do svojho účtu úložiska, pre každé prostredie sa vytvoria samostatné priečinky s výrazom ci_<environmentid> v kontajneri.

### <a name="considerations-for-copy-configuration-preview"></a>Dôležité informácie o konfigurácii kopírovania (ukážka)

Skopírujú sa nasledujúce konfiguračné nastavenia:

- Konfigurácie funkcií
- Prijaté/importované zdroje údajov
- Zjednotenie údajov (Mapovanie, Zosúladenie, Zlúčenie)
- Segmenty
- Miery
- Vzťahy
- Aktivity
- Index vyhľadávania a filtrovania
- Ciele exportu
- Plánovaná obnova
- Obohatenia
- Spravovanie modelov
- Priradenia roly

Nasledujúce nastavenia sa *neskopírujú*:

- Profily zákazníkov.
- Poverenia zdroja údajov. Budete musieť poskytnúť poverenia pre každý zdroj údajov a ručne obnoviť zdroje údajov.
- Zdroje údajov z priečinka Common Data Model a objektu Data Lake spravovaného službou Dataverse. Tieto zdroje údajov budete musieť vytvoriť ručne s rovnakým názvom ako v zdrojovom prostredí.

Po skopírovaní prostredia sa zobrazí potvrdzovacia správa o vytvorení nového prostredia. Stlačte možnosť **Prejsť na zdroje údajov**, čím si zobrazíte zoznam zdrojov údajov.

Všetky zdroje údajov sa zobrazia so stavom **Vyžadované poverenia**. Upravte zdroje údajov a zadaním poverení ich obnovte.

> [!div class="mx-imgBorder"]
> ![Zdroje údajov skopírované.](media/data-sources-copied.png)

Po obnovení zdrojov údajov prejdite na stránku **Údaje** > **Zjednotiť**. Tu nájdete nastavenia zo zdrojového prostredia. Upravte ich podľa potreby alebo stlačte možnosť **Spustiť**, čím začnete proces zjednotenia údajov a vytvoríte jednotnú entitu zákazníka.

Po dokončení zjednotenia údajov prejdite na stránku **Opatrenia** a **Segmenty**, čím ich tiež obnovíte.

## <a name="edit-an-existing-environment"></a>Úprava existujúceho prostredia

Môžete upraviť niektoré podrobnosti o existujúcich prostrediach.

1.  Vyberte nástroj na výber **Prostredia** v hlavičke aplikácie.

2.  Vyberte ikonu **Upraviť**.

3. V poli **Upraviť prostredie** môžete aktualizovať **Zobrazovaný názov** prostredia, ale nemôžete zmeniť **Región** alebo **Typ**.

4. Ak je prostredie nakonfigurované na ukladanie údajov do Azure Data Lake Storage, môžete aktualizovať **Kľúč účtu**. Nemôžete však zmeniť **Názov účtu** ani názov **Kontajnera**.

5. Prípadne môžete aktualizáciu vykonať cez pripojenie založené na kľúči účtu na pripojenie založené na zdrojoch alebo predplatnom. Po inovácii sa po aktualizácii už nebudete môcť vrátiť ku kľúču účtu. Ďalšie informácie sa dozviete v článku [Pripojenie prehľadov cieľových skupín k účtu Azure Data Lake Storage Gen2 pomocou objektu služby Azure](connect-service-principal.md). Pri aktualizácii pripojenia nemôžete zmeniť informácie o **kontajneri**.

6. Voliteľne môžete poskytnúť adresu URL prostredia Microsoft Dataverse v časti **Konfigurácia zdieľania údajov s Microsoft Dataverse a aktivujte ďalšie funkcie**. Tieto schopnosti zahŕňajú zdieľanie údajov s aplikáciami a riešeniami založenými na Microsoft Dataverse, príjem dát z lokálnych zdrojov údajov alebo použitie [predikcií](predictions.md). Vyberte **Povoliť zdieľanie údajov** na zdieľanie výstupných údajov Customer Insights s so spravovaným Microsoft Dataverse Data Lake.

   > [!NOTE]
   > - Zdieľanie údajov so spravovaným Microsoft Dataverse Data Lake nie je momentálne podporované, keď ukladáte všetky údaje do svojho Azure Data Lake Storage.
   > - [Predikcia chýbajúcich hodnôt v entite](predictions.md), keď v súčasnosti povolíte zdieľanie údajov s Data Lake pod správou Microsoft Dataverse.

   Po povolení zdieľania údajov cez Microsoft Dataverse dôjde k spusteniu úplného obnovenia vašich zdrojov údajov a ďalších procesov. Ak sú procesy momentálne spustené, neuvidíte možnosť povoliť zdieľanie údajov s Microsoft Dataverse. Počkajte, kým sa tieto procesy nedokončia, alebo ich zrušte, aby ste povolili zdieľanie údajov. 
   
   :::image type="content" source="media/datasharing-with-DataverseMDL.png" alt-text="Možnosti konfigurácie, ktoré umožnia zdieľanie údajov s Microsoft Dataverse.":::
   
   Keď spustíte procesy, ako je napríklad príjem údajov alebo vytváranie segmentov, vo vyššie uvedenom účte úložiska sa vytvoria zodpovedajúce priečinky. Dátové súbory a súbory model.json sa vytvoria a pridajú do príslušných podpriečinkov v závislosti od spusteného procesu.

## <a name="reset-an-existing-environment"></a>Reset existujúceho prostredia

Ako správca môžete prostredie resetovať do prázdneho stavu, ak chcete odstrániť všetky konfigurácie a odobrať prijaté údaje.

1.  Vyberte nástroj na výber **Prostredia** v hlavičke aplikácie. 

2.  Vyberte prostredie, ktoré chcete resetovať, a vyberte tri bodky (**...**). 

3. Vyberte možnosť **Resetovať**. 

4.  Ak chcete potvrdiť odstránenie, zadajte názov prostredia a vyberte položku **Resetovať**.

## <a name="delete-an-existing-environment"></a>Odstránenie existujúceho prostredia

Ako správca môžete odstrániť prostredie, ktoré spravujete.

1.  Vyberte nástroj na výber **Prostredia** v hlavičke aplikácie.

2.  Vyberte prostredie, ktoré chcete resetovať, a vyberte tri bodky (**...**). 

3. Vyberte možnosť **Odstrániť**. 

4.  Odstránenie potvrdíte zadaním názvu prostredia a výberom položky **Odstrániť**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
