---
title: 'Ako na to: Vytvorte nové prostredie'
description: Kroky na vytvorenie prostredia v Dynamics 365 Customer Insights.
ms.date: 05/31/2022
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
ms.openlocfilehash: 875cbbd095dfd239ab83c1c80db28ea7c0a04ed0
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 08/10/2022
ms.locfileid: "9245576"
---
# <a name="how-to-create-a-new-environment"></a>Ako na to: Vytvorte nové prostredie

Po [zakúpenie predplatiteľskej licencie pre Dynamics 365 Customer Insights](paid-license.md), globálny správca spoločnosti Microsoft 365 nájomník dostane e-mail, ktorý ho pozýva na vytvorenie prostredia. Ak chcete začať, pozrite si časť [https://home.ci.ai.dynamics.com/start](https://home.ci.ai.dynamics.com/start). V tomto scenári môžete prejsť priamo na [Krok 1: Poskytnite základné informácie](#step-1-provide-basic-information).

Po vytvorení prvého prostredia globálny správca Microsoft 365 nájomca môže [pridať používateľov zo svojej organizácie ako správcov](permissions.md). V budúcnosti môžu títo správcovia spravovať používateľov a prostredia. Ak si vaša organizácia zakúpi viac ako jednu licenciu pre Customer Insights, [kontaktujte náš tím podpory](https://go.microsoft.com/fwlink/?linkid=2079641) zvýšiť počet dostupných prostredí. Ďalšie informácie o kapacite a prídavnej kapacite nájdete na stránke [Licenčná príručka Dynamics 365](https://go.microsoft.com/fwlink/?LinkId=866544).

> [!TIP]
> Ak chcete službu vyskúšať, pozrite si [Nastavenie skúšobného prostredia](trial-signup.md).

## <a name="prerequisites"></a>Požiadavky

Potrebuješ [oprávnenia správcu](permissions.md) v Customer Insights na vytváranie alebo správu prostredí.

## <a name="start-the-environment-creation-process"></a>Spustite proces vytvárania prostredia

1. Otvorte výber prostredia a vyberte **+ Nové**.
  
   :::image type="content" source="media/environment-picker.png" alt-text="Vyberte nástroj na výber prostredia.":::

1. Ak chcete poskytnúť všetky požadované informácie pre nové prostredie, postupujte podľa sprievodcu popísaných v nasledujúcich častiach. Ak ste predtým nakonfigurovali prostredie, môžete tiež [skopírujte konfiguráciu](#copy-the-environment-configuration).

## <a name="step-1-provide-basic-information"></a>Krok 1: Poskytnite základné informácie

V kroku **Základné informácie** zvoľte, či chcete vytvoriť prostredie od začiatku alebo [kopírovať údaje z iného prostredia](#copy-the-environment-configuration).

   :::image type="content" source="media/environment-settings-dialog.png" alt-text="Dialógové okno na vytvorenie nového prostredia služby Customer Insights.":::

Uveďte nasledujúce podrobnosti:

- **Názov**: Názov tohto prostredia. Toto pole je už vyplnené, ak ste skopírovali existujúce prostredie, ale môžete ho zmeniť. Ak máte viac ako jedno pracovné prostredie, dajte každému ľahko identifikovateľný názov.
- **Vyberte si svoje podnikanie**: Vyberte primárnu cieľovú skupinu pre nové prostredie. Môžete pracovať s jednotlivými spotrebiteľmi (firma a spotrebiteľ) resp. s [podnikateľskými obchodnými vzťahmi](work-with-business-accounts.md) (firma a firma). Ak vaša organizácia obchoduje najmä s jednotlivcami, ako je maloobchod alebo kaviareň, vyberte si individuálnych spotrebiteľov. Ak sú vaším hlavným publikom iné spoločnosti, ako napríklad výrobca automobilov alebo papierenská spoločnosť, vyberte si podnikateľské účty.
- **Typ**: Vyberte, či chcete vytvoriť výrobné alebo testovacie prostredie. Testovacie prostredia neumožňujú plánované obnovenie údajov a sú určené na predbežnú implementáciu a testovanie. Izolované prostredia používajú rovnaké primárne publikum ako produkčné prostredie, ktoré je aktuálne vybraté.
- **Región**: Región, v ktorom je služba nasadená a hosťovaná. Komu [použiť svoj vlastný Azure Data Lake Storage účtu](own-data-lake-storage.md) alebo [pripojiť k existujúcemu Microsoft Dataverse Organizácia](customer-insights-dataverse.md), prostredie Customer Insights musí byť v rovnakej oblasti.

## <a name="step-2-configure-data-storage"></a>Krok 2: Konfigurácia ukladania údajov

V **Úložisko dát** vyberte, kam sa majú uložiť údaje Customer Insights.

Môžete si vybrať z dvoch možností:

- **Úložisko Customer Insights** : Ukladanie údajov spravuje tím Customer Insights. Je to predvolená možnosť a pokiaľ neexistujú špecifické požiadavky na ukladanie údajov vo vašom vlastnom účte úložiska, odporúčame použiť túto možnosť.
- **Azure Data Lake Storage**: Zadajte svoje vlastné Azure Data Lake Storage na ukladanie údajov, aby ste mali plnú kontrolu nad tým, kde sú údaje uložené. Viac informácií nájdete v časti [Použite svoj vlastný Azure Data Lake Storage účtu](own-data-lake-storage.md).

:::image type="content" source="media/data-storage-environment.png" alt-text="Vyberte preferovanú možnosť na uloženie údajov.":::

## <a name="step-3-connect-to-microsoft-dataverse"></a>Krok 3: Pripojte sa k Microsoft Dataverse

Krok **Microsoft Dataverse** vám umožní prepojiť Customer Insights s vašim prostredím Dataverse. Zdieľať údaje s Dataverse používať s obchodnými aplikáciami založenými na Dataverse, ako je Dynamics 365 Marketing alebo modelom riadené aplikácie Power Apps.

Nechajte toto pole prázdne, ak nemáte vlastné Dataverse prostredie a my vám ho vytvoríme.

Viac informácií nájdete v časti [Pracujte s údajmi Customer Insights v Microsoft Dataverse](customer-insights-dataverse.md).

:::image type="content" source="media/dataverse-provisioning.png" alt-text="zdieľanie údajov s Microsoft Dataverse automaticky povolené pre nové sieťové prostredia.":::

### <a name="step-4-finalize-the-settings"></a>Krok č. 4: Dokončenie nastavení

V **Preskúmanie** krok, prejdite všetkými zadanými nastaveniami. Keď všetko vyzerá byť úplné, vyberte **Vytvoriť** na nastavenie prostredia.

Niektoré nastavenia môžete neskôr zmeniť. Ďalšie informácie nájdete v článku [Správa prostredí](manage-environments.md).

## <a name="work-with-your-new-environment"></a>Pracujte vo svojom novom prostredí

Prečítajte si nasledujúce články, ktoré vám pomôžu začať s konfiguráciou Customer Insights:

- [Pridajte ďalších používateľov a priraďte povolenia](permissions.md).
- [Prijmite zdroje údajov](data-sources.md) a spusťte ich prostredníctvom [procesu zjednocovania údajov](data-unification.md), aby ste získali [jednotné zákaznícke profily](customer-profiles.md).
- [Obohaťte zjednotené zákaznícke profily](enrichment-hub.md) alebo [spusťte prediktívne modely](predictions-overview.md).
- [Vytvorte segmenty](segments.md) skupinovým zákazníkom a [miery](measures.md) na kontrolu KPI.
- [Nastavte spojenia](connections.md) a [exporty](export-destinations.md) na spracovanie podmnožín vašich údajov v iných aplikáciách.

## <a name="copy-the-environment-configuration"></a>Skopírovať konfiguráciu prostredia

Ako správca môžete pri vytváraní nového prostredia skopírovať konfiguráciu z existujúceho prostredia.

:::image type="content" source="media/environment-settings-dialog.png" alt-text="Snímka obrazovky s možnosťami nastavení v nastaveniach prostredia.":::

Zobrazí sa zoznam všetkých dostupných prostredí vo vašej organizácii, z ktorých môžete kopírovať údaje.

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

## <a name="set-up-a-copied-environment"></a>Nastavte skopírované prostredie

Pri kopírovaní konfigurácie prostredia musíte na potvrdenie poverení prejsť niekoľkými ďalšími krokmi:

- Profily zákazníkov. Najprv overte a vykonajte svoje zdroje údajov a spustite zjednotenie údajov, aby ste znova vytvorili profily zákazníkov.
- Poverenia zdroja údajov. Musíte poskytnúť poverenia pre každý zdroj údajov na manuálne overenie a obnovenie zdrojov údajov.
- Zdroje údajov z priečinka Common Data Model a Dataverse. Tieto zdroje údajov musíte vytvoriť manuálne s rovnakým názvom ako v zdrojovom prostredí.
- Tajomstvá pripojenia, ktoré sa používajú na exporty a obohatenia. Musíte znova overiť pripojenia a potom znova aktivovať obohatenia a exporty.

Po vytvorení skopírovaného prostredia sa zobrazí potvrdzujúca správa. Stlačte možnosť **Prejsť na zdroje údajov**, čím si zobrazíte zoznam zdrojov údajov.

Všetky zdroje údajov sa zobrazia so stavom **Vyžadované poverenia**. Upravte zdroje údajov a zadaním poverení ich obnovte.

:::image type="content" source="media/data-sources-copied.png" alt-text="Zoznam zdrojov údajov, ktoré boli skopírované a vyžadujú autentifikáciu.":::

Po obnovení zdrojov údajov prejdite na stránku **Údaje** > **Zjednotiť**. Tu nájdete nastavenia zo zdrojového prostredia. Upravte ich podľa potreby alebo stlačte možnosť **Spustiť**, čím začnete proces zjednotenia údajov a vytvoríte jednotnú entitu zákazníka.

Po dokončení zjednotenia údajov prejdite na stránku **Opatrenia** a **Segmenty**, čím ich tiež obnovíte.

Pred opätovnou aktiváciou exportov a obohatení prejdite na stránku **Admin** > **Spojenia** na opätovné overenie pripojení vo vašom novom prostredí.

[!INCLUDE [footer-include](includes/footer-banner.md)]
