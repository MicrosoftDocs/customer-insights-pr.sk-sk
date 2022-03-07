---
title: Slúži na vytvorenie a spravovanie prostredí
description: Zistite, ako sa môžete zaregistrovať do služby a spravovať prostredia.
ms.date: 12/06/2021
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: NimrodMagen
ms.author: nimagen
manager: shellyha
searchScope:
- ci-system-about
- customerInsights
ms.openlocfilehash: d9e0ee726dbbfcf330022c4d95747551d3114e7e
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 02/25/2022
ms.locfileid: "8354298"
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
