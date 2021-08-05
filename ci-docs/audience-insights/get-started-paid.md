---
title: Vytvoriť a nakonfigurovať platenú licenciu služby Customer Insights
description: Postup získania licencovaného predplatného služby Dynamics 365 Customer Insights a jej konfigurácie.
ms.date: 07/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: f8cf1be97ee8af46145a450009fd278b1821f8fe
ms.sourcegitcommit: 5c9c54ffe045017c19f0042437ada2c101dcaa0f
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 07/22/2021
ms.locfileid: "6650510"
---
# <a name="get-started-with-a-paid-subscription"></a>Začíname pracovať s predplatným

Tento článok popisuje spôsob, ako vytvoriť nové prostredie po tom, čo si vaša organizácia kúpila predplatné služby Dynamics 365 Customer Insights. Ak si chcete kúpiť službu Customer Insights, naše kontaktné informácie sú uvedené na webovej lokalite [Dynamics 365 Customer Insights ](https://dynamics.microsoft.com/ai/customer-insights/). 

Ak by ste chceli službu a funkcie vyskúšať, pozrite sa na časť [Nastaviť skúšobné prostredie](get-started-trial.md).

## <a name="create-an-environment-in-an-existing-organization"></a>Vytvorenie prostredia v existujúcej organizácii

Po zakúpení licencie na predplatné služby Customer Insights dostane globálny správca nájomníka Microsoft 365 e-mail s pozvánkou na vytvorenie prostredia. Ak chcete začať, pozrite si časť [https://home.ci.dynamics.com/start](https://home.ci.dynamics.com/start). 

Služba Customer Insights nie je licencovaná na jedného používateľa, takže sa nezobrazí v oblasti licencií. Ak hľadáte licenciu v centre spravovania služby Microsoft 365, prejdite do časti **Vaše produkty**. 

> [!NOTE]
> Organizácie môžu vytvárať *dva* prostredia pre každú licenciu Customer Insights. Ak vaša organizácia zakúpi viac ako jednu licenciu, [kontaktujte náš tím podpory](https://go.microsoft.com/fwlink/?linkid=2079641) a zvýšte si počet dostupných prostredí. Ďalšie údaje o kapacite a kapacite doplnku nájdete [Sprievodcovi licencovaním systému Dynamics 365](https://go.microsoft.com/fwlink/?LinkId=866544).

Vytvorenie prostredia:

1. V dialógovom okne **Vytvorenie prostredia** vyberte možnosť **Nové prostredie**.

   :::image type="content" source="media/environment-settings-dialog.png" alt-text="Dialógové okno na vytvorenie nového prostredia služby Customer Insights.":::

   Odporúčame začať s nastavením prostredia úplne od začiatku. Ak ste však správcom alebo členom skúšobného prostredia, môžete [skopírovať údaje z iného prostredia](manage-environments.md#copy-the-environment-configuration) tak, že vyberiete možnosť **Kopírovať z existujúceho prostredia**. Zobrazí sa zoznam všetkých dostupných prostredí vo vašej organizácii, z ktorých môžete kopírovať údaje.

1. Uveďte nasledujúce podrobnosti:
   - **Názov**: Názov tohto prostredia. Toto pole je už vyplnené, ak ste skopírovali existujúce prostredie, ale môžete ho zmeniť.
   - **Región**: Región, v ktorom je služba nasadená a hosťovaná.
   - **Typ**: Vyberte, či chcete vytvoriť výrobné alebo testovacie prostredie. Testovacie prostredia neumožňujú plánované obnovenie údajov a sú určené na predbežnú implementáciu a testovanie.
   
1. Voliteľne môžete vybrať **Rozšírené nastavenia**:

   - **Uložiť všetky údaje do**: Určuje, kam sa majú ukladať výstupné údaje vygenerované z Customer Insights. Budete mať dve možnosti: **Úložisko Customer Insights** (Azure Data Lake spravované tímom Customer Insights) a **Azure Data Lake Storage** (vaše vlastné úložisko Azure Data Lake Storage). V predvolenom nastavení je vybraná možnosť úložiska Customer Insights.

     > [!NOTE]
     > Uložením údajov do Azure Data Lake Storage súhlasíte s tým, že údaje budú prenesené a uložené v príslušnom geografickom umiestnení pre dané konto ukladacieho priestoru v službe Azure, ktoré sa môže líšiť od umiestnenia, v ktorom sú údaje uložené v aplikácii Dynamics 365 Customer Insights. [Ďalšie informácie nájdete v centre dôveryhodnosti spoločnosti Microsoft.](https://www.microsoft.com/trust-center)
     >
     > V súčasnosti sú entity prijaté z dátových tokov Power BI vždy uložené v spravovanej službe Data Lake Microsoft Dataverse. 
     > 
     > Podporujeme iba účty Azure Data Lake Storage z rovnakej oblasti Azure ako z tej, ktorú ste vybrali pri vytváraní prostredia. 
     > 
     > Podporujeme iba účty Azure Data Lake Storage, ktoré majú povolený hierarchický priestor názvov.


   - V prípade možnosti Azure Data Lake Storage si môžete vybrať medzi voľbou založenou na zdrojoch a voľbou autentifikácie založenou na predplatnom. Ďalšie informácie sa dozviete v článku [Pripojenie prehľadov cieľových skupín k účtu Azure Data Lake Storage Gen2 pomocou objektu služby Azure](connect-service-principal.md). Názov **kontajnera** sa nedá zmeniť a bude `customerinsights`.
   
   - Ak chcete použiť [pripravené modely](predictions-overview.md#out-of-box-models), nakonfigurujte zdieľanie údajov so službou Microsoft Dataverse, alebo povoľte príjem údajov z lokálnych zdrojov, poskytnite adresu URL prostredia Microsoft Dataverse v časti **Konfigurácia zdieľania údajov pomocou služby Microsoft Dataverse a povoľte ďalšie možnosti**. Vyberte **Povoliť zdieľanie údajov** na zdieľanie výstupných údajov Customer Insights s so spravovaným Microsoft Dataverse Data Lake.

     > [!NOTE]
     > - Zdieľanie údajov so spravovaným Microsoft Dataverse Data Lake nie je momentálne podporované, keď ukladáte všetky údaje do svojho Azure Data Lake Storage.
     > - [Predikcia chýbajúcich hodnôt v entite](predictions.md), keď v súčasnosti povolíte zdieľanie údajov s Data Lake pod správou Microsoft Dataverse.

     :::image type="content" source="media/Datasharing-with-DataverseMDL.png" alt-text="Možnosti konfigurácie, ktoré umožnia zdieľanie údajov s Microsoft Dataverse.":::

   Keď sa systémové procesy, ako je príjem údajov, dokončia, systém vytvorí príslušné priečinky vo vami zadanom konte úložiska. Vytvoria sa dátové súbory a súbory model.json, ktoré sa pridajú do priečinkov podľa názvu procesu.

   Ak vytvoríte viac prostredí služby Customer Insights a rozhodnete sa uložiť výstupné entity z týchto prostredí do svojho účtu úložiska, pre každé prostredie sa vytvoria samostatné priečinky s výrazom ci_<environmentid> v kontajneri.

1. Ak chcete nastaviť prostredie, označte položku **Vytvoriť**. 

## <a name="configure-an-environment"></a>Konfigurácia prostredia

Prečítajte si nasledujúce články, v ktorých nájdete informácie, ktoré vám môžu pomôcť začať konfigurovať službu Customer Insights. 

- [Pridajte ďalších používateľov a priraďte povolenia](permissions.md).
- [Prijmite zdroje údajov](data-sources.md) a spusťte ich prostredníctvom [procesu zjednocovania údajov](data-unification.md), aby ste získali [jednotné zákaznícke profily](customer-profiles.md).
- [Obohaťte zjednotené zákaznícke profily](enrichment-hub.md) alebo [spusťte prediktívne modely](predictions-overview.md).
- Vytvorte [segmenty](segments.md) skupinovým zákazníkom a KPI recenzie [opatrení](measures.md).
- Nastavte [spojenia](connections.md) a [exporty](export-destinations.md) na spracovanie podmnožín vašich údajov v iných aplikáciách.
