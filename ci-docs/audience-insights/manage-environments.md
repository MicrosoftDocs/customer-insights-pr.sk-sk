---
title: Slúži na vytvorenie a spravovanie prostredí
description: Zistite, ako sa môžete zaregistrovať do služby a spravovať prostredia.
ms.date: 07/22/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: e3f99f8f151aea5f120084382babd5e46e109545a4f63aafc51c3ecb1400cc33
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 08/10/2021
ms.locfileid: "7034196"
---
# <a name="manage-environments"></a>Správa prostredí

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

## <a name="switch-environments"></a>Prepnutie prostredí

Ak chcete zmeniť prostredie, vyberte ovládací prvok **prostredia** v pravom hornom rohu stránky.

:::image type="content" source="media/home-page-environment-switcher.png" alt-text="Snímka obrazovky ovládacieho prvku na prepínanie prostredí.":::

Správcovia môžu [vytvárať](get-started-paid.md) a spravovať prostredia.

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
   > - [Predikcia chýbajúcich hodnôt v entite](predictions.md) a správy PowerBI Embedded v prehľadoch cieľovej skupiny (ak sú vo vašom prostredí povolené) nie sú v súčasnosti podporované, ak máte povolené zdieľanie údajov so spravovaným dátovým jazerom Microsoft Dataverse.

   Po povolení zdieľania údajov cez Microsoft Dataverse dôjde k spusteniu úplného obnovenia vašich zdrojov údajov a ďalších procesov. Ak sú procesy momentálne spustené, neuvidíte možnosť povoliť zdieľanie údajov s Microsoft Dataverse. Počkajte, kým sa tieto procesy nedokončia, alebo ich zrušte, aby ste povolili zdieľanie údajov. 
   
   :::image type="content" source="media/datasharing-with-DataverseMDL.png" alt-text="Možnosti konfigurácie, ktoré umožnia zdieľanie údajov s Microsoft Dataverse.":::
   
   Keď spustíte procesy, ako je napríklad príjem údajov alebo vytváranie segmentov, vo vyššie uvedenom účte úložiska sa vytvoria zodpovedajúce priečinky. Dátové súbory a súbory model.json sa vytvoria a pridajú do príslušných podpriečinkov v závislosti od spusteného procesu.

## <a name="copy-the-environment-configuration"></a>Skopírovať konfiguráciu prostredia

Keď vytvárate nové prostredie, môžete sa rozhodnúť, či chcete skopírovať konfiguráciu z už existujúceho prostredia. 

:::image type="content" source="media/environment-settings-dialog.png" alt-text="Snímka obrazovky s možnosťami nastavení v nastaveniach prostredia.":::

Zobrazí sa zoznam všetkých dostupných prostredí vo vašej organizácii, z ktorých môžete kopírovať údaje.

Skopírujú sa nasledujúce konfiguračné nastavenia:

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

Tieto údaje *nebudú* skopírované:

- Profily zákazníkov.
- Poverenia zdroja údajov. Budete musieť poskytnúť poverenia pre každý zdroj údajov a ručne obnoviť zdroje údajov.
- Zdroje údajov z priečinka Common Data Model a objektu Data Lake spravovaného službou Dataverse. Tieto zdroje údajov budete musieť vytvoriť ručne s rovnakým názvom ako v zdrojovom prostredí.

Po skopírovaní prostredia sa zobrazí potvrdzovacia správa o vytvorení nového prostredia. Stlačte možnosť **Prejsť na zdroje údajov**, čím si zobrazíte zoznam zdrojov údajov.

Všetky zdroje údajov sa zobrazia so stavom **Vyžadované poverenia**. Upravte zdroje údajov a zadaním poverení ich obnovte.

:::image type="content" source="media/data-sources-copied.png" alt-text="Zoznam zdrojov údajov, ktoré boli skopírované a vyžadujú autentifikáciu.":::

Po obnovení zdrojov údajov prejdite na stránku **Údaje** > **Zjednotiť**. Tu nájdete nastavenia zo zdrojového prostredia. Upravte ich podľa potreby alebo stlačte možnosť **Spustiť**, čím začnete proces zjednotenia údajov a vytvoríte jednotnú entitu zákazníka.

Po dokončení zjednotenia údajov prejdite na stránku **Opatrenia** a **Segmenty**, čím ich tiež obnovíte.

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
