---
title: Slúži na vytvorenie a spravovanie prostredí
description: Zistite, ako sa môžete zaregistrovať do služby a spravovať prostredia.
ms.date: 11/10/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
ms.reviewer: nimagen
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 010336445d0825a7ff82d1b7a65702fc12245788
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 11/25/2020
ms.locfileid: "4644152"
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

1. Vyberte symbol **Nastavenia** v záhlaví aplikácie.

1. Vyberte **Nové prostredie**.

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
   
   - Ak chcete použiť [predikcie](predictions.md), navštívte adresu URL inštancie služby Common Data Service v poli **Adresa servera** v sekcii **Používanie predikcií**.

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

1. Prejdite do **Správca** > **Systém** > **Informácie**.

2. Vyberte **Upraviť**.

3. Môžete aktualizovať **Zobrazovaný názov** prostredia, ale nemôžete zmeniť **Región** ani **Typ**.

4. Ak je prostredie nakonfigurované na ukladanie údajov do Azure Data Lake Storage Gen2, môžete aktualizovať **Kľúč účtu**. Nemôžete však zmeniť **Názov účtu** ani názov **Kontajnera**.

5. Prípadne môžete aktualizáciu vykonať cez pripojenie založené na kľúči účtu na pripojenie založené na zdrojoch alebo predplatnom. Po inovácii sa po aktualizácii už nebudete môcť vrátiť ku kľúču účtu. Ďalšie informácie sa dozviete v článku [Pripojenie prehľadov cieľových skupín k účtu Azure Data Lake Storage Gen2 pomocou objektu služby Azure](connect-service-principal.md). Pri aktualizácii pripojenia nemôžete zmeniť informácie o **kontajneri**.

## <a name="reset-an-existing-environment"></a>Reset existujúceho prostredia

Ak chcete odstrániť všetky konfigurácie a odobrať prijaté údaje, môžete prostredie resetovať do prázdneho stavu.

1.  Prejdite do **Správca** > **Systém** > **Informácie**.

2.  Vyberte položku **Resetovať**. 

3.  Ak chcete potvrdiť odstránenie, zadajte názov prostredia a vyberte položku **Resetovať**.


## <a name="delete-an-existing-environment"></a>Odstránenie existujúceho prostredia

1. Prejdite do **Správca** > **Systém** > **Informácie**.

1. Vyberte **Odstrániť**.

1. Odstránenie potvrdíte zadaním názvu prostredia a výberom položky **Odstrániť**.
