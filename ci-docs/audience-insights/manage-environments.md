---
title: Slúži na vytvorenie a spravovanie prostredí
description: Zistite, ako sa môžete zaregistrovať do služby a spravovať prostredia.
ms.date: 02/09/2022
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: NimrodMagen
ms.author: nimagen
manager: shellyha
searchScope:
- ci-system-about
- customerInsights
ms.openlocfilehash: 4f4e5a8415f6c2128b0480edf67f317124eeeba9
ms.sourcegitcommit: 50d32a4cab01421a5c3689af789e20857ab009c4
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 03/03/2022
ms.locfileid: "8376895"
---
# <a name="manage-environments"></a>Správa prostredí

## <a name="switch-environments"></a>Prepnutie prostredí

Ak chcete zmeniť prostredie, vyberte ovládací prvok **prostredia** v pravom hornom rohu stránky.

:::image type="content" source="media/home-page-environment-switcher.png" alt-text="Snímka obrazovky ovládacieho prvku na prepínanie prostredí.":::

Správcovia môžu [vytvárať](create-environment.md) a spravovať prostredia.

## <a name="edit-an-existing-environment"></a>Úprava existujúceho prostredia

Môžete upraviť niektoré podrobnosti o existujúcich prostrediach.

1.  Vyberte nástroj na výber **Prostredia** v hlavičke aplikácie.

2.  Vyberte ikonu **Upraviť**.

3. V poli **Upraviť prostredie** môžete aktualizovať nastavenia prostredia.

Ďalšie informácie o nastaveniach prostredia nájdete v článku [Vytvorenie nového prostredia](create-environment.md).

## <a name="connect-to-microsoft-dataverse"></a>Pripojiť k systému Microsoft Dataverse
   
Krok **Microsoft Dataverse** vám umožní prepojiť Customer Insights s vašim prostredím Dataverse.

Ak chcete použiť [pripravené modely predikcie](predictions-overview.md#out-of-box-models), nakonfigurujte zdieľanie údajov s Dataverse. Alebo môžete povoliť príjem údajov z lokálnych zdrojov údajov poskytnutím adresy URL prostredia Microsoft Dataverse, ktoré spravuje vaša organizácia.

> [!IMPORTANT]
> Štatistiky zákazníkov a Dataverse musia byť v rovnakej oblasti, aby bolo možné zdieľať údaje.

:::image type="content" source="media/dataverse-provisioning.png" alt-text="Možnosti konfigurácie, ktoré umožnia zdieľanie údajov s Microsoft Dataverse.":::

> [!NOTE]
> Customer Insights nepodporuje nasledujúce scenáre zdieľania údajov:
> - Ak uložíte všetky údaje do vlastného Azure Data Lake Storage, nebudete môcť povoliť zdieľanie údajov pomocou dátového jazera spravovaného prostredníctvom Dataverse.
> - Ak povolíte zdieľanie údajov pomocou Dataverse, nebudete môcť [vytvárať predikované ani chýbajúce hodnoty v entite](predictions.md).

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

- Zdroje údajov z priečinka Common Data Model a dátového jazera spravovaného v Dataverse. Tieto zdroje údajov budete musieť vytvoriť ručne s rovnakým názvom ako v zdrojovom prostredí.

Po skopírovaní prostredia sa zobrazí potvrdzovacia správa o vytvorení nového prostredia. Stlačte možnosť **Prejsť na zdroje údajov**, čím si zobrazíte zoznam zdrojov údajov.

Všetky zdroje údajov sa zobrazia so stavom **Vyžadované poverenia**. Upravte zdroje údajov a zadaním poverení ich obnovte.

:::image type="content" source="media/data-sources-copied.png" alt-text="Zoznam zdrojov údajov, ktoré boli skopírované a vyžadujú autentifikáciu.":::

Po obnovení zdrojov údajov prejdite na stránku **Údaje** > **Zjednotiť**. Tu nájdete nastavenia zo zdrojového prostredia. Upravte ich podľa potreby alebo stlačte možnosť **Spustiť**, čím začnete proces zjednotenia údajov a vytvoríte jednotnú entitu zákazníka.

Po dokončení zjednotenia údajov prejdite na stránku **Opatrenia** a **Segmenty**, čím ich tiež obnovíte.

## <a name="change-the-owner-of-an-environment"></a>Zmeňte vlastníka prostredia

Aj keď v Customer Insights môže mať niekoľko používateľov povolenia správcu, vlastníkom prostredia je iba jeden používateľ. V predvolenom nastavení je to správca, ktorý na začiatku vytvára prostredie. Ako správca prostredia môžete prideliť vlastníctvo inému používateľovi s oprávneniami správcu.

1. Vyberte nástroj na výber **Prostredia** v hlavičke aplikácie.

1. Vyberte ikonu **Upraviť**.

1. V **Upraviť prostredie** box, prejdite na **Základné informácie** krok.

1. V **Zmeniť vlastníka prostredia** poľa, vybrať nového vlastníka prostredia.  

1. Vyberte **Skontrolujte a dokončite**, potom **Aktualizovať** aplikujte zmeny. 

## <a name="claim-ownership-of-an-environment"></a>Nárokovať si vlastníctvo prostredia

Ak vlastník prostredia opustí organizáciu alebo sa odstráni jeho používateľský účet, prostredie nebude mať vlastníka. Používateľ s oprávneniami správcu si môže nárokovať vlastníctvo a stať sa novým vlastníkom. Môžu naďalej vlastniť životné prostredie resp [zmeniť vlastníctvo na iného správcu](#change-the-owner-of-an-environment). 

Ak si chcete nárokovať vlastníctvo, vyberte **Prevziať vlastníctvo** tlačidlo, ktoré sa zobrazuje v hornej časti každej stránky v Customer Insights, keď pôvodný vlastník opustil organizáciu.

## <a name="reset-an-existing-environment"></a>Reset existujúceho prostredia

Ako vlastník prostredia môžete resetovať prostredie do prázdneho stavu, ak chcete vymazať všetky konfigurácie a odstrániť prijaté údaje.

1.  Vyberte nástroj na výber **Prostredia** v hlavičke aplikácie. 

2.  Vyberte prostredie, ktoré chcete resetovať, a vyberte tri bodky (**...**). 

3. Vyberte možnosť **Resetovať**. 

4.  Ak chcete potvrdiť odstránenie, zadajte názov prostredia a vyberte položku **Resetovať**.

## <a name="delete-an-existing-environment"></a>Odstránenie existujúceho prostredia

Ako vlastník prostredia môžete odstrániť prostredie, ktoré spravujete.

1.  Vyberte nástroj na výber **Prostredia** v hlavičke aplikácie.

2.  Vyberte prostredie, ktoré chcete resetovať, a vyberte tri bodky (**...**). 

3. Vyberte možnosť **Odstrániť**. 

4.  Odstránenie potvrdíte zadaním názvu prostredia a výberom položky **Odstrániť**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
