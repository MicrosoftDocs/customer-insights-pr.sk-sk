---
title: Slúži na vytvorenie a spravovanie prostredí
description: Zistite, ako sa môžete zaregistrovať do služby a spravovať prostredia.
ms.date: 02/01/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: nimagen
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 744f0bcbf5d2700363180f44e38d6dee9bf5df63
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 02/15/2021
ms.locfileid: "5270131"
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

Vytvorenie prostredia:

1. Vyberte nástroj na výber **Prostredia** v hlavičke aplikácie.

1. Vyberte **Nové**.

   > [!div class="mx-imgBorder"]
   > ![Nastavenia prostredia](media/environment-settings-dialog.png)

1. V dialógovom okne **Vytvoriť nové prostredie** vyberte **Nové prostredie**.

   Ak chcete [kopírovať údaje z aktuálneho prostredia](#additional-considerations-for-copy-configuration-preview), vyberte **Kopírovať z existujúceho prostredia**. Zobrazí sa zoznam všetkých dostupných prostredí vo vašej organizácii, z ktorých môžete kopírovať údaje.

1. Uveďte nasledujúce podrobnosti:
   - **Názov**: Názov tohto prostredia. Toto pole je už vyplnené, ak ste skopírovali existujúce prostredie, ale môžete ho zmeniť.
   - **Región**: Región, v ktorom je služba nasadená a hosťovaná.
   - **Typ**: Vyberte, či chcete vytvoriť výrobné alebo izolované prostredie.

2. Voliteľne môžete vybrať **Rozšírené nastavenia**:

   - **Uložiť všetky údaje do**: Určuje, kam sa majú ukladať výstupné údaje vygenerované z Customer Insights. Budete mať dve možnosti: **Úložisko Customer Insights** (Azure Data Lake spravované tímom Customer Insights) a **Azure Data Lake Storage** Gen2 (vaše vlastné úložisko Azure Data Lake Storage). V predvolenom nastavení je vybraná možnosť úložiska Customer Insights.

   > [!NOTE]
   > Uložením údajov do Azure Data Lake Storage súhlasíte s tým, že údaje budú prenesené a uložené v príslušnom geografickom umiestnení pre dané konto ukladacieho priestoru v službe Azure, ktoré sa môže líšiť od umiestnenia, v ktorom sú údaje uložené v aplikácii Dynamics 365 Customer Insights. [Ďalšie informácie nájdete v centre dôveryhodnosti spoločnosti Microsoft.](https://www.microsoft.com/trust-center)
   >
   > V súčasnosti sú prijaté entity vždy uložené v dátovom jazere spravovanom službou Customer Insights.
   > Podporujeme iba účty ukladacieho priestoru Azure Data Lake Gen2 z rovnakej oblasti Azure, ktorú ste vybrali pri vytváraní prostredia.
   > Podporujeme iba účty úložísk s povoleným hierarchickým názvom priestoru (HNS) Azure Data Lake Gen2.

   - V prípade možnosti Azure Data Lake Storage Gen2 si môžete vybrať medzi použitím možnosti založenej na zdrojoch a možnosti založenej na predplatnom. Ďalšie informácie sa dozviete v článku [Pripojenie prehľadov cieľových skupín k účtu Azure Data Lake Storage Gen2 pomocou objektu služby Azure](connect-service-principal.md). Názov **kontajnera** sa nedá zmeniť a bude znieť „customerinsights“.
   
   - Ak chcete použiť [predikcie](predictions.md) alebo nakonfigurovať zdieľanie údajov s aplikáciami a riešeniami založenými na Microsoft Dataverse, uveďte URL prostredia Microsoft Dataverse pod **Konfigurácia zdieľania údajov s Microsoft Dataverse a povolenie ďalších funkcií**. Vyberte **Povoliť zdieľanie údajov** na zdieľanie výstupných údajov Customer Insights s so spravovaným Microsoft Dataverse Data Lake.

     > [!NOTE]
     > - Zdieľanie údajov so spravovaným Microsoft Dataverse Data Lake nie je momentálne podporované, keď ukladáte všetky údaje do svojho Azure Data Lake Storage.
     > - [Predikcia chýbajúcich hodnôt v entite](predictions.md) nie je momentálne podporovaná, keď v súčasnosti povolíte zdieľanie údajov so spravovaným Microsoft Dataverse Data Lake.

     > [!div class="mx-imgBorder"]
     > ![Možnosti konfigurácie, ktoré umožnia zdieľanie údajov s Microsoft Dataverse](media/Datasharing-with-DataverseMDL.png)

   Keď spustíte procesy, ako je napríklad príjem údajov alebo vytváranie segmentov, vo vyššie uvedenom účte úložiska sa vytvoria zodpovedajúce priečinky. Dátové súbory a súbory model.json sa vytvoria a pridajú do príslušných podpriečinkov na základe spusteného procesu.

   Ak vytvoríte viac prostredí služby Customer Insights a rozhodnete sa uložiť výstupné entity z týchto prostredí do svojho účtu úložiska, pre každé prostredie sa vytvoria samostatné priečinky s výrazom ci_<environmentid> v kontajneri.

### <a name="additional-considerations-for-copy-configuration-preview"></a>Ďalšie informácie o konfigurácii kopírovania (ukážka)

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
- Zdroje údajov zo zložky Common Data Model a spravovaného fondu Common Data Service. Tieto zdroje údajov budete musieť vytvoriť ručne s rovnakým názvom ako v zdrojovom prostredí.

Po skopírovaní prostredia sa zobrazí potvrdzovacia správa o vytvorení nového prostredia. Stlačte možnosť **Prejsť na zdroje údajov**, čím si zobrazíte zoznam zdrojov údajov.

Všetky zdroje údajov sa zobrazia so stavom **Vyžadované poverenia**. Upravte zdroje údajov a zadaním poverení ich obnovte.

> [!div class="mx-imgBorder"]
> ![Zdroje údajov skopírované](media/data-sources-copied.png)

Po obnovení zdrojov údajov prejdite na stránku **Údaje** > **Zjednotiť**. Tu nájdete nastavenia zo zdrojového prostredia. Upravte ich podľa potreby alebo stlačte možnosť **Spustiť**, čím začnete proces zjednotenia údajov a vytvoríte jednotnú entitu zákazníka.

Po dokončení zjednotenia údajov prejdite na stránku **Opatrenia** a **Segmenty**, čím ich tiež obnovíte.

## <a name="edit-an-existing-environment"></a>Úprava existujúceho prostredia

Môžete upraviť niektoré podrobnosti o existujúcich prostrediach.

1.  Vyberte nástroj na výber **Prostredia** v hlavičke aplikácie.

2.  Vyberte ikonu **Upraviť**.

3. V poli **Upraviť prostredie** môžete aktualizovať **Zobrazovaný názov** prostredia, ale nemôžete zmeniť **Región** alebo **Typ**.

4. Ak je prostredie nakonfigurované na ukladanie údajov do Azure Data Lake Storage Gen2, môžete aktualizovať **Kľúč účtu**. Nemôžete však zmeniť **Názov účtu** ani názov **Kontajnera**.

5. Prípadne môžete aktualizáciu vykonať cez pripojenie založené na kľúči účtu na pripojenie založené na zdrojoch alebo predplatnom. Po inovácii sa po aktualizácii už nebudete môcť vrátiť ku kľúču účtu. Ďalšie informácie sa dozviete v článku [Pripojenie prehľadov cieľových skupín k účtu Azure Data Lake Storage Gen2 pomocou objektu služby Azure](connect-service-principal.md). Pri aktualizácii pripojenia nemôžete zmeniť informácie o **kontajneri**.

## <a name="reset-an-existing-environment"></a>Reset existujúceho prostredia

Ako správca môžete prostredie resetovať do prázdneho stavu, ak chcete odstrániť všetky konfigurácie a odobrať prijaté údaje.

1.  Vyberte nástroj na výber **Prostredia** v hlavičke aplikácie. 

2.  Vyberte prostredie, ktoré chcete resetovať, a vyberte tri bodky **...**. 

3. Vyberte možnosť **Resetovať**. 

4.  Ak chcete potvrdiť odstránenie, zadajte názov prostredia a vyberte položku **Resetovať**.

## <a name="delete-an-existing-environment-available-only-for-admins"></a>Odstránenie existujúceho prostredia (k dispozícii iba pre správcov)

Ako správca môžete odstrániť prostredie, ktoré spravujete.

1.  Vyberte nástroj na výber **Prostredia** v hlavičke aplikácie.

2.  Vyberte prostredie, ktoré chcete resetovať, a vyberte tri bodky **...**. 

3. Vyberte možnosť **Odstrániť**. 

4.  Odstránenie potvrdíte zadaním názvu prostredia a výberom položky **Odstrániť**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]