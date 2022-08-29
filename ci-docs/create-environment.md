---
title: Vytvoriť nové prostredie
description: Kroky na vytvorenie prostredia v Dynamics 365 Customer Insights.
ms.date: 08/15/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.custom: intro-internal
searchScope:
- ci-home
- customerInsights
ms.openlocfilehash: 0a45e2fd2bdb7b85883a536f8b42ee650e54db7e
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304263"
---
# <a name="create-a-new-environment"></a>Vytvoriť nové prostredie

Po [zakúpenie predplatiteľskej licencie pre Dynamics 365 Customer Insights](paid-license.md), globálny správca spoločnosti Microsoft 365 nájomník dostane e-mail, ktorý ho pozýva na vytvorenie prostredia. Ak chcete začať, pozrite si časť [https://home.ci.ai.dynamics.com/start](https://home.ci.ai.dynamics.com/start). V tomto scenári začnite s [Krok 1: Poskytnite základné informácie](#step-1-provide-basic-information).

Po vytvorení prvého prostredia globálny správca Microsoft 365 nájomca môže [pridať používateľov z ich organizácie ako správcov](permissions.md). Títo správcovia potom môžu spravovať používateľov a prostredia. Ak si vaša organizácia zakúpi viac ako jednu licenciu na Customer Insights, [kontaktujte náš tím podpory](https://go.microsoft.com/fwlink/?linkid=2079641) zvýšiť počet dostupných prostredí. Ďalšie informácie o kapacite a prídavnej kapacite nájdete na stránke [Licenčná príručka Dynamics 365](https://go.microsoft.com/fwlink/?LinkId=866544). Keď budete mať možnosť vytvárať ďalšie prostredia, prejdite na [Spustite proces vytvárania prostredia](#start-the-environment-creation-process).

> [!TIP]
> Ak chcete službu vyskúšať, pozrite si [Nastavenie skúšobného prostredia](trial-signup.md).

## <a name="prerequisites"></a>Požiadavky

[Povolenia správcu](permissions.md) v Customer Insights

## <a name="start-the-environment-creation-process"></a>Spustite proces vytvárania prostredia

1. Otvorte výber prostredia a vyberte **+ Nové**.
  
   :::image type="content" source="media/environment-picker.png" alt-text="Vyberte nástroj na výber prostredia.":::

1. Ak chcete poskytnúť všetky požadované informácie pre nové prostredie, postupujte podľa sprievodcu popísaných v nasledujúcich častiach.

## <a name="step-1-provide-basic-information"></a>Krok 1: Poskytnite základné informácie

1. Vyberte, či chcete vytvoriť prostredie od začiatku alebo kopírovať údaje z iného prostredia. [Kopírovanie údajov z iného prostredia](#copy-the-environment-configuration) vyžaduje ďalšie kroky.

   :::image type="content" source="media/environment-settings-dialog.png" alt-text="Dialógové okno na vytvorenie nového prostredia služby Customer Insights.":::

1. Uveďte nasledujúce podrobnosti:

   - **názov** : Názov pre toto prostredie. Toto pole je už vyplnené, ak ste skopírovali existujúce prostredie, ale môžete ho zmeniť.
   - **Vyberte si svoju firmu** : Primárne publikum pre nové prostredie: individuálni spotrebitelia (B-to-C) resp [podnikateľské účty](work-with-business-accounts.md) (B-to-B). Ak vaša organizácia obchoduje najmä s jednotlivcami, ako je maloobchod alebo kaviareň, vyberte si individuálnych spotrebiteľov. Ak sú vaším hlavným publikom iné spoločnosti, ako napríklad výrobca automobilov alebo papierenská spoločnosť, vyberte si podnikateľské účty.
   - **Typ** : Typ prostredia: výrobné alebo pieskovisko. Testovacie prostredia neumožňujú plánované obnovenie údajov a sú určené na predbežnú implementáciu a testovanie. Izolované prostredia používajú rovnaké primárne publikum ako produkčné prostredie, ktoré je aktuálne vybraté.
   - **región** : Oblasť, v ktorej je služba nasadená a hosťovaná. Komu [použiť svoj vlastný Azure Data Lake Storage účtu](own-data-lake-storage.md) alebo [pripojiť k existujúcemu Microsoft Dataverse Organizácia](customer-insights-dataverse.md), prostredie Customer Insights musí byť v rovnakej oblasti.

1. Vyberte **Ďalej**.

## <a name="step-2-configure-data-storage"></a>Krok 2: Konfigurácia ukladania údajov

1. Vyberte, kam sa majú ukladať údaje Customer Insights:

   - **Úložisko Customer Insights** : Ukladanie údajov je spravované automaticky. Je to predvolená možnosť a pokiaľ neexistujú špecifické požiadavky na ukladanie údajov vo vašom vlastnom účte úložiska, odporúčame použiť túto možnosť.
   - **Azure Data Lake Storage**: Tvoj vlastný Azure Data Lake Storage na ukladanie údajov, aby ste mali plnú kontrolu nad tým, kde sú údaje uložené. Postupujte podľa krokov v [Použite svoj vlastný Azure Data Lake Storage účtu](own-data-lake-storage.md).

   :::image type="content" source="media/data-storage-environment.png" alt-text="Vyberte preferovanú možnosť na uloženie údajov.":::

1. Vyberte **Ďalej**.

## <a name="step-3-connect-to-microsoft-dataverse"></a>Krok 3: Pripojte sa k Microsoft Dataverse

Ak máte a Dataverse prostredia, pripojte Customer Insights. Zdieľať údaje s Dataverse používať s obchodnými aplikáciami založenými na Dataverse, ako je Dynamics 365 Marketing alebo modelom riadené aplikácie Power Apps.

1. Postupujte podľa krokov v [Pracujte s údajmi Customer Insights v Microsoft Dataverse](customer-insights-dataverse.md).

   :::image type="content" source="media/dataverse-provisioning.png" alt-text="zdieľanie údajov s Microsoft Dataverse automaticky povolené pre nové sieťové prostredia.":::

1. Vyberte **Ďalej**.

## <a name="step-4-finalize-the-settings"></a>Krok č. 4: Dokončenie nastavení

Skontrolujte zadané nastavenia. Keď všetko vyzerá byť úplné, vyberte **Vytvoriť** na nastavenie prostredia.

Ak chcete neskôr zmeniť niektoré nastavenia, pozrite si časť [Spravujte prostredia](manage-environments.md).

## <a name="work-with-your-new-environment"></a>Pracujte vo svojom novom prostredí

Prečítajte si nasledujúce články, ktoré vám pomôžu začať s konfiguráciou Customer Insights:

- [Pridajte ďalších používateľov a priraďte povolenia](permissions.md).
- [Prijmite zdroje údajov](data-sources.md) a spusťte ich prostredníctvom [procesu zjednocovania údajov](data-unification.md), aby ste získali [jednotné zákaznícke profily](customer-profiles.md).
- [Obohaťte zjednotené zákaznícke profily](enrichment-hub.md) alebo [spusťte prediktívne modely](predictions-overview.md).
- [Vytvorte segmenty](segments.md) skupinovým zákazníkom a [miery](measures.md) na kontrolu KPI.
- [Nastavte spojenia](connections.md) a [exporty](export-destinations.md) na spracovanie podmnožín vašich údajov v iných aplikáciách.

## <a name="copy-the-environment-configuration"></a>Skopírovať konfiguráciu prostredia

Ak ste sa ako správca rozhodli skopírovať konfiguráciu z existujúceho prostredia, vyberte si zo zoznamu všetkých dostupných prostredí vo vašej organizácii.

:::image type="content" source="media/environment-settings-dialog.png" alt-text="Snímka obrazovky s možnosťami nastavení v nastaveniach prostredia.":::

Skopírujú sa nasledujúce konfiguračné nastavenia:

- Zdroje údajov importované cez Power Query
- Konfigurácia zjednotenia údajov
- Segmenty
- Miery
- Vzťahy 
- Aktivity
- Index vyhľadávania a filtrovania
- Exporty
- Plán obnovenia
- Obohatenia
- Predikcia modely
- Priradenia roly

### <a name="set-up-a-copied-environment"></a>Nastavte skopírované prostredie

Keď kopírujete konfiguráciu prostredia, po vytvorení skopírovaného prostredia sa zobrazí potvrdzujúca správa. Vykonajte nasledujúce kroky na potvrdenie poverení.

1. Stlačte možnosť **Prejsť na zdroje údajov**, čím si zobrazíte zoznam zdrojov údajov. Všetky zdroje údajov zobrazujú **Vyžadujú sa poverenia** postavenie.

   :::image type="content" source="media/data-sources-copied.png" alt-text="Zoznam zdrojov údajov, ktoré boli skopírované a vyžadujú autentifikáciu.":::

1. Upravte zdroje údajov a zadaním poverení ich obnovte. Zdroje údajov z priečinka Common Data Model a Dataverse musí byť vytvorený manuálne s rovnakým názvom ako v zdrojovom prostredí.

1. Po obnovení zdrojov údajov prejdite na stránku **Údaje** > **Zjednotiť**. Tu nájdete nastavenia zo zdrojového prostredia. Upravte ich podľa potreby alebo vyberte **Zjednotiť** > **Zjednotiť profily a závislosti zákazníkov** spustiť proces zjednotenia údajov a vytvoriť jednotnú entitu zákazníka.

   > [!TIP]
   > Pre účty a kontakty vyberte **Zjednotiť účty** > **Zjednotiť profily a závislosti**.

1. Po dokončení zjednotenia údajov prejdite na **Opatrenia** a **Segmenty** osviežiť ich.

1. Ísť do **Admin** > **Spojenia** na opätovné overenie pripojení vo vašom novom prostredí.

1. Ísť do **Údaje** > **Obohacovanie** a **Údaje** > **Vývoz** aby ste ich znova aktivovali.

[!INCLUDE [footer-include](includes/footer-banner.md)]
