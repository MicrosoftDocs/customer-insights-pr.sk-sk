---
title: Práca s údajmi Customer Insights v Microsoft Dataverse
description: Zistite, ako prepojiť Customer Insights a Microsoft Dataverse a pochopiť výstupné entity, ktoré sa exportujú do Dataverse.
ms.date: 08/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: dfa63110fc5291f2b63aebf588d6fdd20ed4ab67
ms.sourcegitcommit: 134aac66e3e0b77b2e96a595d6acbb91bf9afda2
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 09/07/2022
ms.locfileid: "9424328"
---
# <a name="work-with-customer-insights-data-in-microsoft-dataverse"></a>Práca s údajmi Customer Insights v Microsoft Dataverse

Customer Insights poskytuje možnosť sprístupniť výstupné entity dostupné v [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro). Táto integrácia umožňuje jednoduché zdieľanie údajov a vlastný vývoj prostredníctvom prístupu s nízkym kódom/bez kódu. The [výstupné entity](#output-entities) sú dostupné ako tabuľky v a Dataverse životné prostredie. Údaje môžete použiť pre akúkoľvek inú aplikáciu založenú na Dataverse tabuľky. Tieto tabuľky umožňujú scenáre, ako sú automatizované pracovné postupy Power Automate alebo vytváranie aplikácií pomocou Power Apps.

Pripája sa k vášmu Dataverse prostredie vám to tiež umožňuje [prijímať údaje zo zdrojov údajov lokálny pomocou Power Platform dátové toky a brány](connect-power-query.md#add-data-from-on-premises-data-sources).

## <a name="prerequisites"></a>Požiadavky

- Štatistiky zákazníkov a Dataverse prostredia musia byť hosťované v rovnakej oblasti.
- Rola globálneho správcu nastavená v Dataverse životné prostredie. Overte si, či toto [Dataverse prostredie je spojené](/power-platform/admin/control-user-access#associate-a-security-group-with-a-dataverse-environment) do určitých skupín zabezpečenia a uistite sa, že ste do týchto skupín zabezpečenia pridaný.
- Žiadne iné prostredie Customer Insights už nie je spojené s Dataverse prostredie, ktoré chcete pripojiť. Naučiť sa ako [odstrániť existujúce pripojenie k a Dataverse životné prostredie](#remove-an-existing-connection-to-a-dataverse-environment).
- A Microsoft Dataverse prostredie pripojené k jednému úložnému kontu, ak toto prostredie nakonfigurujete [použi svoj Azure Data Lake Storage](own-data-lake-storage.md).

## <a name="dataverse-storage-capacity-entitlement"></a>Dataverse nárok na skladovaciu kapacitu

Predplatné Customer Insights vás oprávňuje na dodatočnú kapacitu pre existujúcu organizáciu [Dataverse úložná kapacita](/power-platform/admin/capacity-storage). Pridaná kapacita závisí od počtu profilov, ktoré vaše predplatné používa.

**Príklad:**

Za predpokladu, že získate 15 GB úložného priestoru pre databázu a 20 GB úložného priestoru pre súbory na 100 000 zákazníckych profilov. Ak vaše predplatné zahŕňa 300 000 zákazníckych profilov, vaša celková kapacita úložiska je 45 GB (3 x 15 GB) úložiska databázy a 60 GB úložiska súborov (3 x 20 GB). Podobne, ak máte predplatné B-to-B s 30 000 účtami, vaša celková úložná kapacita je 45 GB (3 x 15 GB) úložisko databázy a 60 GB úložisko súborov (3 x 20 GB).

Kapacita denníka nie je pre vašu organizáciu prírastková a pevná.

Ďalšie informácie o podrobných kapacitných nárokoch nájdete v časti [Licenčná príručka Dynamics 365](https://go.microsoft.com/fwlink/?LinkId=866544).

## <a name="connect-a-dataverse-environment-to-customer-insights"></a>Pripojte a Dataverse prostredia na Customer Insights

The **Microsoft Dataverse** krok vám umožní prepojiť Customer Insights s vaším Dataverse prostredia kým [vytvorenie prostredia Customer Insights](create-environment.md).

:::image type="content" source="media/dataverse-provisioning.png" alt-text="zdieľanie údajov s Microsoft Dataverse automaticky povolené pre nové prostredia.":::

1. Poskytnite webovú adresu svojho Dataverse prostredie alebo ponechajte pole prázdne, ak chcete, aby bolo vytvorené pre vás.

   > [!NOTE]
   > Po nadviazaní spojenia medzi Customer Insights a Dataverse, nemeňte názov organizácie pre Dataverse životné prostredie. Názov organizácie sa používa v Dataverse URL a zmenený názov prerušia spojenie s Customer Insights.

   [Power Platform správcovia môžu kontrolovať, kto môže vytvoriť nový Dataverse prostredia](/power-platform/admin/control-environment-creation). Ak sa pokúšate nastaviť nové prostredie Customer Insights a nedarí sa vám to, správca možno zakázal vytváranie Dataverse prostredia pre všetkých okrem správcov.

1. Ak používate svoj vlastný účet Data Lake Storage:
   1. Vyberte **Povoliť zdieľanie údajov** s Dataverse.
   1. Zadajte **Identifikátor povolení**. Ak chcete získať identifikátor povolenia, [povoliť zdieľanie údajov s Dataverse zo svojho vlastného Azure Data Lake Storage](#enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview).

## <a name="enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview"></a>Povoliť zdieľanie údajov s Dataverse z vlastného Azure Data Lake Storage (Náhľad)

In [tvoj vlastný Azure Data Lake Storage účtu](own-data-lake-storage.md), overte, či používateľ, ktorý nastavuje prostredie Customer Insights, má min **Storage Blob Data Reader** povolenia na`customerinsights` kontajnera v účte úložiska.

### <a name="limitations"></a>Obmedzenia

- Iba mapovanie jedna ku jednej medzi a Dataverse organizácia a an Azure Data Lake Storage účtu. Raz Dataverse organizácia je pripojená k účtu úložiska, nemôže sa pripojiť k inému účtu úložiska. Toto obmedzenie zabraňuje Dataverse z naplnenia viacerých účtov úložiska.
- Zdieľanie údajov nebude fungovať, ak je na prístup k vášmu účtu potrebné nastavenie Azure Private Link Azure Data Lake Storage účet, pretože je za firewallom. Dataverse momentálne nepodporuje pripojenie k súkromným koncovým bodom cez Private Link.

### <a name="set-up-security-groups-on-your-own-azure-data-lake-storage"></a>Nastavte si skupiny zabezpečenia sami Azure Data Lake Storage

1. Vytvorte dve skupiny zabezpečenia vo svojom predplatnom Azure – jednu **Čitateľ** bezpečnostná skupina a jedna **Prispievateľ** bezpečnostnú skupinu a nastavte Microsoft Dataverse ako vlastník pre obe bezpečnostné skupiny.

1. Spravujte zoznam riadenia prístupu (ACL) na`customerinsights` kontajnera vo vašom účte úložiska prostredníctvom týchto skupín zabezpečenia.
   1. Pridajte Microsoft Dataverse servis a akékoľvek Dataverse podnikových aplikácií, ako je Dynamics 365 Marketing **Čitateľ** bezpečnostná skupina s **iba na čítanie** povolenia.
   1. Pridať *iba* aplikáciu Customers Insights na **Prispievateľ** bezpečnostná skupina udeliť oboje **čítaj a píš** povolenia na písanie profilov a prehľadov.

### <a name="set-up-powershell"></a>Nastavte PowerShell

Nastavte PowerShell na spúšťanie skriptov PowerShell.

1. Nainštalujte najnovšiu verziu [Azure Active Directory PowerShell pre Graph](/powershell/azure/active-directory/install-adv2).
   1. Na počítači stlačte kláves Windows a nájdite **Windows PowerShell** a vyberte **Spustiť ako správca**.
   1. Do okna PowerShell, ktoré sa otvorí, zadajte výraz `Install-Module AzureAD`.

1. Importujte tri moduly.
   1. V okne PowerShell zadajte`Install-Module -Name Az.Accounts` a postupujte podľa krokov.
   1. Opakujte pre`Install-Module -Name Az.Resources` a `Install-Module -Name Az.Storage`.

### <a name="execute-powershell-scripts-and-obtain-the-permission-identifier"></a>Spustite skripty PowerShell a získajte identifikátor povolenia

1. Stiahnite si dva skripty PowerShell, ktoré potrebujete na spustenie, z nášho inžiniera [Úložisko GitHub](https://github.com/trin-msft/byol).
   - `CreateSecurityGroups.ps1`: Vyžaduje oprávnenia správcu nájomníka.
   - `ByolSetup.ps1`: Vyžaduje povolenia vlastníka údajov objektu Storage Blob na úrovni účtu úložiska/kontajnera. Tento skript vytvorí povolenie za vás. Po úspešnom spustení skriptu je možné priradenie vašej role manuálne odstrániť.

1. Vykonať`CreateSecurityGroups.ps1` v prostredí Windows PowerShell poskytnutím ID predplatného Azure, ktoré obsahuje vaše Azure Data Lake Storage. Otvorte skript PowerShell v editore a pozrite si ďalšie informácie a implementovanú logiku.

   Tento skript vytvorí dve skupiny zabezpečenia vo vašom predplatnom Azure: jednu pre skupinu Reader a druhú pre skupinu prispievateľov. Microsoft Dataverse služba je vlastníkom oboch týchto bezpečnostných skupín.

1. Uložte obe hodnoty ID bezpečnostnej skupiny vygenerované týmto skriptom na použitie v`ByolSetup.ps1` skript.

   > [!NOTE]
   > Vytvorenie skupiny zabezpečenia je možné vo vašom nájomníkovi zakázať. V takom prípade by bolo potrebné manuálne nastavenie a vaše Azure AD admin by musel [povoliť vytvorenie bezpečnostnej skupiny](/azure/active-directory/enterprise-users/groups-self-service-management).

1. Vykonať`ByolSetup.ps1` v prostredí Windows PowerShell poskytnutím ID predplatného Azure, ktoré obsahuje vaše Azure Data Lake Storage, názov účtu úložiska, názov skupiny prostriedkov a hodnoty ID bezpečnostnej skupiny Reader a Contributor. Otvorte skript PowerShell v editore a pozrite si ďalšie informácie a implementovanú logiku.

   Tento skript pridáva požadované riadenie prístupu na základe rolí pre Microsoft Dataverse servis a akékoľvek Dataverse podnikové aplikácie. Aktualizuje tiež zoznam riadenia prístupu (ACL) na`customerinsights` kontajner pre bezpečnostné skupiny vytvorené pomocou`CreateSecurityGroups.ps1` skript. Skupina prispievateľov je uvedená *rwx* je udelené povolenie a skupina čitateľov *rx* iba povolenie.

1. Skopírujte výstupný reťazec, ktorý vyzerá takto:`https://DVBYODLDemo/customerinsights?rg=285f5727-a2ae-4afd-9549-64343a0gbabc&cg=720d2dae-4ac8-59f8-9e96-2fa675dbdabc`

1. Zadajte skopírovaný výstupný reťazec do **Identifikátor povolení** poľa kroku konfigurácie prostredia pre Microsoft Dataverse.

   :::image type="content" source="media/dataverse-enable-datasharing-BYODL.png" alt-text="Možnosti konfigurácie umožňujúce zdieľanie údajov z vašich vlastných Azure Data Lake Storage s Microsoft Dataverse .":::

## <a name="remove-an-existing-connection-to-a-dataverse-environment"></a>Odstráňte existujúce pripojenie k a Dataverse životné prostredie

Pri pripájaní k a Dataverse prostredia, chybové hlásenie **Táto organizácia CDS je už pripojená k inej inštancii Customer Insights** znamená, že Dataverse sa už používa v prostredí Customer Insights. Existujúce pripojenie môžete odstrániť ako globálny správca na Dataverse životné prostredie. Vyplnenie zmien môže trvať niekoľko hodín.

1. Prejdite do systému [Power Apps](https://make.powerapps.com).
1. Vyberte prostredie z výberu prostredia.
1. Ísť do **Riešenia**.
1. Odinštalujte alebo odstráňte pomenované riešenie **Dynamics 365 Customer Insights Doplnok zákazníckej karty (ukážka)**.

OR

1. Otvor tvoj Dataverse životné prostredie.
1. Ísť do **Pokročilé nastavenia** > **Riešenia**.
1. Odinštalujte **CustomerInsightsCustomerCard** Riešenie.

Ak odstránenie pripojenia zlyhá kvôli závislostiam, musíte odstrániť aj závislosti. Viac informácií nájdete v časti [Odstránenie závislostí](/power-platform/alm/removing-dependencies).

## <a name="output-entities"></a>Výstupné entity

Niektoré výstupné entity z Customer Insights sú dostupné ako tabuľky v Dataverse. Nasledujúce časti popisujú očakávanú schému týchto tabuliek.

- [CustomerProfile](#customerprofile)
- [ContactProfile](#contactprofile)
- [AlternateKey](#alternatekey)
- [UnifiedActivity](#unifiedactivity)
- [CustomerMeasure](#customermeasure)
- [Obohatenie](#enrichment)
- [Predikcia](#prediction)
- [Členstvo v segmente](#segment-membership)

### <a name="customerprofile"></a>CustomerProfile

Táto tabuľka obsahuje zjednotený profil zákazníka z nástroja Customer Insights. Schéma pre zjednotený zákaznícky profil závisí od entít a atribútov použitých v procese zjednotenia údajov. Schéma profilu zákazníka zvyčajne obsahuje podmnožinu atribútov z [Definícia Common Data Model pre CustomerProfile ](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customerprofile). Pre scenár B-to-B obsahuje zákaznícky profil zjednotené účty a schéma zvyčajne obsahuje podmnožinu atribútov z [Definícia spoločného dátového modelu účtu](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/account).

### <a name="contactprofile"></a>ContactProfile

Kontaktný profil obsahuje jednotné informácie o kontakte. Kontakty sú [jednotlivcov, ktorí sú priradení k účtu](data-unification-contacts.md) v scenári B-to-B.

| Column                       | Type                | Description     |
| ---------------------------- | ------------------- | --------------- |
|  Dátum narodenia            | Dátum a čas       |  Dátum narodenia kontaktu               |
|  City                 | SMS správa |  Mesto kontaktnej adresy               |
|  ContactId            | SMS správa |  ID profilu kontaktu               |
|  ContactProfileId     | Jednoznačný identifikátor   |  GUID pre kontakt               |
|  Krajina alebo Región      | SMS správa |  Krajina/región kontaktnej adresy               |
|  ID zákazníka           | SMS správa |  ID účtu, ku ktorému je kontakt priradený               |
|  EntityName           | SMS správa |  Entita, z ktorej pochádzajú údaje                |
|  FirstName            | SMS správa |  Krstné meno kontaktu               |
|  Pohlavie               | SMS správa |  Pohlavie kontaktu               |
|  Id                   | SMS správa |  Deterministický GUID založený na`Identifier`               |
|  Identifikátor           | SMS správa |  Interné ID profilu kontaktu:`ContactProfile|CustomerId|ContactId`               |
|  JobTitle             | SMS správa |  Pracovná pozícia kontaktu               |
|  LastName             | SMS správa |  Priezvisko kontaktu               |
|  PostalCode           | SMS správa |  PSČ kontaktnej adresy               |
|  Primárny e-mail         | SMS správa |  Emailová adresa kontaktu               |
|  Hlavný telefón         | SMS správa |  Telefónne číslo kontaktu               |
|  Kraj      | SMS správa |  Štát alebo provincia kontaktnej adresy               |
|  StreetAddress        | SMS správa |  Ulica kontaktnej adresy               |

### <a name="alternatekey"></a>AlternateKey

Tabuľka AlternateKey obsahuje kľúče entít, ktoré sa zúčastnili procesu zjednotenia.

|Column  |Type  |Description  |
|---------|---------|---------|
|DataSourceName    |SMS správa         | Názov zdroja údajov. Napríklad: `datasource5`        |
|EntityName        | SMS správa        | Názov entity v Customer Insights. Napríklad: `contact1`        |
|AlternateValue    |SMS správa         |Alternatívne ID, ktoré je namapované na ID zákazníka. Príklad: `cntid_1078`         |
|KeyRing           | SMS správa        | Hodnota JSON  </br> Ukážka: [{"dataSourceName":" datasource5 ",</br>"entityName":" contact1",</br>"preferredKey":" cntid_1078",</br>"keys":[" cntid_1078"]}]       |
|ID zákazníka         | SMS správa        | ID zjednoteného profilu zákazníka.         |
|AlternateKeyId     | Jednoznačný identifikátor        |  AlternateKey deterministický GUID založený na`Identifier`      |
|Identifikátor |   SMS správa      |   `DataSourceName|EntityName|AlternateValue`  </br> Ukážka: `testdatasource|contact1|cntid_1078`    |

### <a name="unifiedactivity"></a>UnifiedActivity

Táto tabuľka obsahuje aktivity používateľov, ktoré sú k dispozícii v Customer Insights.

| Column            | Type        | Description                                                                              |
|-------------------|-------------|------------------------------------------------------------------------------------------|
| ID zákazníka        | SMS správa      | ID profilu zákazníka                                                                      |
| ActivityId        | SMS správa      | Interné ID aktivity zákazníka (primárny kľúč)                                       |
| SourceEntityName  | SMS správa      | Názov zdrojovej entity                                                                |
| SourceActivityId  | SMS správa      | Primárny kľúč zo zdrojovej entity                                                       |
| ActivityType      | SMS správa      | Typ sémantickej aktivity alebo názov vlastnej aktivity                                        |
| ActivityTimeStamp | Dátum a čas    | Časová známka aktivity                                                                      |
| Title             | SMS správa      | Titul alebo názov aktivity                                                               |
| Description       | SMS správa      | Opis aktivity                                                                     |
| URL               | SMS správa      | Odkaz na externú adresu URL špecifickú pre danú aktivitu                                         |
| SemanticData      | SMS správa | Zahŕňa zoznam párov kľúč/hodnota pre polia sémantického mapovania špecifické pre typ aktivity |
| RangeIndex        | SMS správa      | Unixová časová pečiatka používaná na triedenie časovej osi aktivity a dotazov na efektívny rozsah |
| UnifiedActivityId   | Jednoznačný identifikátor | Interné ID aktivity zákazníka (ActivityId) |

### <a name="customermeasure"></a>CustomerMeasure

Táto tabuľka obsahuje výstupné údaje mier založených na atribútoch zákazníka.

| Column             | Type             | Description                 |
|--------------------|------------------|-----------------------------|
| ID zákazníka         | SMS správa           | ID profilu zákazníka        |
| Miery           | SMS správa      | Zahŕňa zoznam párov kľúčových hodnôt pre názov miery a hodnoty pre daného zákazníka |
| Identifikátor | SMS správa           | `Customer_Measure|CustomerId` |
| CustomerMeasureId | Jednoznačný identifikátor     | ID profilu zákazníka |

### <a name="enrichment"></a>Obohatenie

Táto tabuľka obsahuje výstup z procesu obohacovania.

| Column               | Type             |  Description                                          |
|----------------------|------------------|------------------------------------------------------|
| ID zákazníka           | SMS správa           | ID profilu zákazníka                                 |
| EnrichmentProvider   | SMS správa           | Názov poskytovateľa pre obohatenie                                  |
| EnrichmentType       | SMS správa           | Typ obohatenia                                      |
| Hodnoty               | SMS správa      | Zoznam atribútov získaných procesom obohacovania |
| EnrichmentId | Jednoznačný identifikátor            | Deterministické GUID generované z`Identifier` |
| Identifikátor   | SMS správa           | `EnrichmentProvider|EnrichmentType|CustomerId`         |

### <a name="prediction"></a>Predpoveď

Táto tabuľka obsahuje výstup predikcií modelu.

| Column               | Type        | Description                                          |
|----------------------|-------------|------------------------------------------------------|
| ID zákazníka           | SMS správa      | ID profilu zákazníka                                  |
| ModelProvider        | SMS správa      | Názov poskytovateľa modelu                                      |
| Model                | SMS správa      | Názov modelu                                                |
| Hodnoty               | SMS správa | Zoznam atribútov získaných modelom |
| PredpoveďId | Jednoznačný identifikátor       | Deterministické GUID generované z`Identifier` |
| Identifikátor   | SMS správa      |  `Model|ModelProvider|CustomerId`                      |

### <a name="segment-membership"></a>Členstvo v segmente

Táto tabuľka obsahuje informácie o členstve v segmentoch profilov zákazníkov.

| Column        | Type | Description                        |
|--------------------|--------------|-----------------------------|
| ID zákazníka        | SMS správa       | ID profilu zákazníka        |
| SegmentProvider      | SMS správa       | Aplikácia, ktorá zverejňuje segmenty.      |
| Typ členstva v segmente | SMS správa       | Typ zákazníka pre tento záznam členstva v segmente. Podporuje viacero typov, ako napríklad Zákazník, Kontakt alebo Účet. Predvolené: Zákazník  |
| Segmenty       | SMS správa  | Zoznam jedinečných segmentov, ktorých členom je profil zákazníka      |
| Identifikátor  | SMS správa   | Jedinečný identifikátor záznamu členstva v segmente. `CustomerId|SegmentProvider|SegmentMembershipType|Name`  |
| SegmentMembershipId | Jednoznačný identifikátor      | Deterministické GUID generované z`Identifier`          |

[!INCLUDE [footer-include](includes/footer-banner.md)]
