---
title: Vytváranie prostredí v Customer Insights
description: Kroky na vytvorenie prostredí s licencovaným predplatným pre Dynamics 365 Customer Insights.
ms.date: 04/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.custom: intro-internal
searchScope:
- ci-home
- customerInsights
ms.openlocfilehash: 0efda9d2997bcfd069b6d2445b69d159d7d3e59b
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 04/27/2022
ms.locfileid: "8643103"
---
# <a name="create-an-environment-in-customer-insights"></a>Vytvorte prostredie v Customer Insights

Tento článok popisuje spôsob, ako vytvoriť nové prostredie po tom, čo si vaša organizácia kúpila predplatné služby Dynamics 365 Customer Insights. 

Organizácie môžu vytvoriť viacero prostredí pre každú licenciu Customer Insights. Ak si vaša organizácia kúpi viac ako jednu licenciu, [kontaktujte náš tím podpory](https://go.microsoft.com/fwlink/?linkid=2079641), aby zvýšil počet dostupných prostredí. Ďalšie informácie o kapacite a prídavnej kapacite nájdete na stránke [Licenčná príručka Dynamics 365](https://go.microsoft.com/fwlink/?LinkId=866544).

> [!NOTE]
> Ak chcete službu vyskúšať, pozrite si [Nastavenie skúšobného prostredia](trial-signup.md).

## <a name="create-a-new-environment"></a>Vytvoriť nové prostredie

Po zakúpení predplatiteľskej licencie pre Customer Insights, globálny správca Microsoft 365 nájomník dostane e-mail, ktorý ho pozýva na vytvorenie prostredia. Ak chcete začať, pozrite si časť [https://home.ci.ai.dynamics.com/start](https://home.ci.ai.dynamics.com/start). 

Prostredie so sprievodcom vám pomôže krok za krokom zhromaždiť všetky požadované informácie pre nové prostredie. Potrebuješ [oprávnenia správcu](permissions.md) v Customer Insights na vytváranie alebo správu prostredí.

1. Otvorte výber prostredia a vyberte **+ Nové**.
  
   :::image type="content" source="media/environment-picker.png" alt-text="Vyberte nástroj na výber prostredia.":::

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

V **Úložisko dát** vyberte, kam sa majú uložiť údaje Customer Insights.

Budete mať dve možnosti: **Úložisko Customer Insights** (Azure Data Lake spravované tímom Customer Insights) a **Azure Data Lake Storage** (vaše vlastné úložisko Azure Data Lake Storage). V predvolenom nastavení je vybraná možnosť úložiska Customer Insights.

:::image type="content" source="media/data-storage-environment.png" alt-text="Vyber Azure Data Lake Storage na uloženie vašich údajov.":::

Uložením údajov do Azure Data Lake Storage súhlasíte s tým, že údaje budú prenesené a uložené v príslušnom geografickom umiestnení pre daný účet úložiska Azure. Toto umiestnenie sa môže líšiť od miesta, kde sú uložené údaje Dynamics 365 Customer Insights. Ďalšie informácie nájdete v [centre dôveryhodnosti spoločnosti Microsoft](https://www.microsoft.com/trust-center).

> [!NOTE]
> Customer Insights v súčasnosti podporuje nasledujúce:
> - Prijaté entity z tokov údajov Power BI, ktoré sú uložené v Data Lake spravovanom prostredníctvom Microsoft Dataverse.  
> - Účty Azure Data Lake Storage z rovnakej oblasti Azure, ktorú ste vybrali pri vytváraní prostredia.
> - Azure Data Lake Storage účty, ktoré sú Gen2 a majú *hierarchický menný priestor* povolené. Účty úložiska Azure Data Lake Gen1 nie sú podporované.

V prípade možnosti Azure Data Lake Storage si môžete vybrať medzi voľbou založenou na zdrojoch a voľbou autentifikácie založenou na predplatnom. Viac informácií nájdete v časti [Pripojte sa účtu Azure Data Lake Storage pomocou objektu služby Azure](connect-service-principal.md). Kontajner s názvom`customerinsights` musí existovať na účte úložiska.

Keď sú systémové procesy, ako napríklad príjem údajov, dokončené, systém vytvorí zodpovedajúce priečinky vo vami zadanom účte úložiska. Vytvoria sa dátové súbory a súbory *model.json*, ktoré sa pridajú do priečinkov podľa názvu procesu.

Ak vytvoríte viacero prostredí Customer Insights a rozhodnete sa uložiť výstupné entity z týchto prostredí do svojho účtu úložiska, Customer Insights vytvorí samostatné priečinky pre každé prostredie s `ci_environmentID` v kontajneri.

### <a name="step-3-connect-to-microsoft-dataverse"></a>Krok 3: Pripojte sa k Microsoft Dataverse
   
Krok **Microsoft Dataverse** vám umožní prepojiť Customer Insights s vašim prostredím Dataverse.

Poskytnite svoje vlastné Microsoft Dataverse prostredie na zdieľanie údajov (profilov a prehľadov) s obchodnými aplikáciami založenými na Dataverse, ako je Dynamics 365 Marketing alebo modelom riadené aplikácie v Power Apps. Ak nemáte vlastné, nechajte toto pole prázdne Dataverse prostredie a my vám jeden zabezpečíme.

Pripája sa k vášmu Dataverse prostredie vám to tiež umožňuje [prijímať údaje zo zdrojov údajov lokálny pomocou Power Platform dátové toky a brány](data-sources.md#add-data-from-on-premises-data-sources). Môžete tiež použiť [out-of-box predikcia modely](predictions-overview.md?tabs=b2c#out-of-box-models) pripojením k a Dataverse životné prostredie.

> [!IMPORTANT]
> 1. Štatistiky zákazníkov a Dataverse musia byť v rovnakej oblasti, aby bolo možné zdieľať údaje.
> 1. Musíte mať rolu globálneho správcu v Dataverse životné prostredie. Overte si, či toto [Dataverse prostredie je spojené](/power-platform/admin/control-user-access#associate-a-security-group-with-a-dataverse-environment) do určitých bezpečnostných skupín a uistite sa, že ste boli pridaní do týchto bezpečnostných skupín.
> 1. Nie je s tým už spojené žiadne existujúce prostredie Customer Insights Dataverse životné prostredie. Naučiť sa ako [odstrániť existujúce pripojenie k a Dataverse životné prostredie](manage-environments.md#remove-an-existing-connection-to-a-dataverse-environment).

:::image type="content" source="media/dataverse-provisioning.png" alt-text="zdieľanie údajov s Microsoft Dataverse automatické povolené pre nové inštancie siete.":::

Ďalšie informácie o povolení zdieľania údajov s Microsoft Dataverse z vlastného Azure Data Lake Storage pozri [Pripojte sa k Microsoft Dataverse](manage-environments.md#connect-to-microsoft-dataverse).

Customer Insights nepodporuje nasledujúce scenáre zdieľania údajov:
- Ak povolíte zdieľanie údajov pomocou Dataverse, nebudete môcť [vytvárať predikované ani chýbajúce hodnoty v entite](predictions.md).

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
