---
title: Vytváranie prostredí v Customer Insights
description: Kroky na vytvorenie prostredí s licencovaným predplatným pre Dynamics 365 Customer Insights.
ms.date: 10/14/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: 914af46d2d82f3556d149f2836680c902f826d50
ms.sourcegitcommit: 31985755c7c973fb1eb540c52fd1451731d2bed2
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 10/22/2021
ms.locfileid: "7673410"
---
# <a name="create-an-environment-in-audience-insights"></a>Vytvorenie prostredia v prehľadoch cieľových skupín

Tento článok popisuje spôsob, ako vytvoriť nové prostredie po tom, čo si vaša organizácia kúpila predplatné služby Dynamics 365 Customer Insights. 

Organizácie môžu vytvárať *dva* prostredia pre každú licenciu Customer Insights. Ak si vaša organizácia kúpi viac ako jednu licenciu, [kontaktujte náš tím podpory](https://go.microsoft.com/fwlink/?linkid=2079641), aby zvýšil počet dostupných prostredí. Ďalšie údaje o kapacite a kapacite doplnku nájdete [Sprievodcovi licencovaním systému Dynamics 365](https://go.microsoft.com/fwlink/?LinkId=866544).

> [!NOTE]
> Ak chcete službu vyskúšať, pozrite si [Nastavenie skúšobného prostredia](../trial-signup.md).

## <a name="create-a-new-environment"></a>Vytvoriť nové prostredie

Po zakúpení licencie na predplatné služby Customer Insights dostane globálny správca nájomníka Microsoft 365 e-mail s pozvánkou na vytvorenie prostredia. Ak chcete začať, pozrite si časť [https://home.ci.ai.dynamics.com/start](https://home.ci.ai.dynamics.com/start). 

Prostredie so sprievodcom vám pomôže krok za krokom zhromaždiť všetky požadované informácie pre nové prostredie. Potrebujete [oprávnenia správcu](permissions.md) v prehľadoch cieľových skupín na vytváranie alebo správu prostredí.

1. V prehľadoch cieľových skupín otvorte výber prostredia a vyberte **+ Nové**.
  
   :::image type="content" source="../engagement-insights/media/environment-picker.png" alt-text="Vyberte nástroj na výber prostredia.":::

1. Postupujte podľa pokynov uvedených v nasledujúcich častiach.

### <a name="step-1-provide-environment-information"></a>Krok 1: Poskytnite informácie o prostredí

V kroku **Základné informácie** zvoľte, či chcete vytvoriť prostredie od začiatku alebo [kopírovať údaje z iného prostredia](manage-environments.md#copy-the-environment-configuration).

   :::image type="content" source="media/environment-settings-dialog.png" alt-text="Dialógové okno na vytvorenie nového prostredia služby Customer Insights.":::

Uveďte nasledujúce podrobnosti:
   - **Názov**: Názov tohto prostredia. Toto pole je už vyplnené, ak ste skopírovali existujúce prostredie, ale môžete ho zmeniť.
   - **Vyberte si svoje podnikanie**: Vyberte primárnu cieľovú skupinu pre nové prostredie. Môžete pracovať s jednotlivými spotrebiteľmi (firma a spotrebiteľ) resp. s [podnikateľskými obchodnými vzťahmi](work-with-business-accounts.md) (firma a firma).
   - **Typ**: Vyberte, či chcete vytvoriť výrobné alebo testovacie prostredie. Testovacie prostredia neumožňujú plánované obnovenie údajov a sú určené na predbežnú implementáciu a testovanie. Izolované prostredia používajú rovnaké primárne publikum ako produkčné prostredie, ktoré je aktuálne vybraté.
   - **Región**: Región, v ktorom je služba nasadená a hosťovaná.

### <a name="step-2-configure-data-storage"></a>Krok 2: Konfigurácia ukladania údajov

V kroku **Úložisko údajov** zvoľte, kam sa majú údaje z prehľadov cieľových skupín uložiť.

Budete mať dve možnosti: **Úložisko Customer Insights** (Azure Data Lake spravované tímom Customer Insights) a **Azure Data Lake Storage** (vaše vlastné úložisko Azure Data Lake Storage). V predvolenom nastavení je vybraná možnosť úložiska Customer Insights.

:::image type="content" source="media/data-storage-environment.png" alt-text="Vyberte Azure Data Lake Storage na uloženie údajov prehľadov vašich cieľových skupín.":::

Uložením údajov do Azure Data Lake Storage súhlasíte s tým, že údaje budú prenesené a uložené v príslušnom geografickom umiestnení pre daný účet úložiska Azure. Toto umiestnenie sa môže líšiť od miesta, kde sú uložené údaje Dynamics 365 Customer Insights. Ďalšie informácie nájdete v [centre dôveryhodnosti spoločnosti Microsoft](https://www.microsoft.com/trust-center).

> [!NOTE]
> Customer Insights v súčasnosti podporuje nasledujúce:
> - Prijaté entity z tokov údajov Power BI, ktoré sú uložené v Data Lake spravovanom prostredníctvom Microsoft Dataverse.  
> - Účty Azure Data Lake Storage z rovnakej oblasti Azure, ktorú ste vybrali pri vytváraní prostredia.
> - Účty Azure Data Lake Storage, ktoré majú povolený *hierarchický priestor mien*.

V prípade možnosti Azure Data Lake Storage si môžete vybrať medzi voľbou založenou na zdrojoch a voľbou autentifikácie založenou na predplatnom. Viac informácií nájdete v časti [Pripojte sa účtu Azure Data Lake Storage pomocou objektu služby Azure](connect-service-principal.md). Názov **kontajnera** bude `customerinsights` a nedá sa zmeniť.

Keď sú systémové procesy, ako napríklad príjem údajov, dokončené, systém vytvorí zodpovedajúce priečinky vo vami zadanom účte úložiska. Vytvoria sa dátové súbory a súbory *model.json*, ktoré sa pridajú do priečinkov podľa názvu procesu.

Ak vytvoríte viacero prostredí Customer Insights a rozhodnete sa uložiť výstupné entity z týchto prostredí do svojho účtu úložiska, Customer Insights vytvorí samostatné priečinky pre každé prostredie s `ci_environmentID` v kontajneri.

### <a name="step-3-connect-to-microsoft-dataverse"></a>Krok 3: Pripojte sa k Microsoft Dataverse
   
Krok **Microsoft Dataverse** vám umožní prepojiť Customer Insights s vašim prostredím Dataverse.

Ak chcete použiť [pripravené modely predikcie](predictions-overview.md#out-of-box-models), nakonfigurujte zdieľanie údajov s Dataverse. Alebo môžete povoliť príjem údajov z lokálnych zdrojov údajov poskytnutím adresy URL prostredia Microsoft Dataverse, ktoré spravuje vaša organizácia. Vyberte **Povoliť zdieľanie údajov** na zdieľanie výstupných údajov Customer Insights s dátovým jazerom spravovaným s Dataverse.

:::image type="content" source="media/dataverse-data-sharing.png" alt-text="Možnosti konfigurácie, ktoré umožnia zdieľanie údajov s Microsoft Dataverse.":::

> [!NOTE]
> Customer Insights nepodporuje nasledujúce scenáre zdieľania údajov:
> - Ak uložíte všetky údaje do vlastného Azure Data Lake Storage, nebudete môcť povoliť zdieľanie údajov pomocou dátového jazera spravovaného prostredníctvom Dataverse.
> - Ak povolíte zdieľanie údajov pomocou Dataverse, nebudete môcť [vytvárať predikované ani chýbajúce hodnoty v entite](predictions.md).

### <a name="step-4-finalize-the-settings"></a>Krok č. 4: Dokončenie nastavení

V kroku **Kontrola** prejdite všetkými zadanými nastaveniami. Keď všetko vyzerá byť úplné, vyberte **Vytvoriť** na nastavenie prostredia. 

Väčšinu nastavení môžete tiež zmeniť neskôr. Ďalšie informácie nájdete v článku [Správa prostredí](manage-environments.md).

## <a name="work-with-your-new-environment"></a>Pracujte vo svojom novom prostredí

Prečítajte si nasledujúce články, ktoré vám pomôžu začať s konfiguráciou Customer Insights: 

- [Pridajte ďalších používateľov a priraďte povolenia](permissions.md).
- [Prijmite zdroje údajov](data-sources.md) a spusťte ich prostredníctvom [procesu zjednocovania údajov](data-unification.md), aby ste získali [jednotné zákaznícke profily](customer-profiles.md).
- [Obohaťte zjednotené zákaznícke profily](enrichment-hub.md) alebo [spusťte prediktívne modely](predictions-overview.md).
- [Vytvorte segmenty](segments.md) skupinovým zákazníkom a [miery](measures.md) na kontrolu KPI.
- [Nastavte spojenia](connections.md) a [exporty](export-destinations.md) na spracovanie podmnožín vašich údajov v iných aplikáciách.
