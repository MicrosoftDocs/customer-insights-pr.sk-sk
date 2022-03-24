---
title: Obohaťte zákaznícke profily o údaje z Microsoft Office 365
description: Použiť proprietárne údaje z Microsoft Office obohatiť svoje profily zákazníkov o údaje o interakciách.
ms.date: 12/03/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahl
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 47239bd7f0c89742cf9c673bb2ebe4c41d853233
ms.sourcegitcommit: 50d32a4cab01421a5c3689af789e20857ab009c4
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 03/03/2022
ms.locfileid: "8376849"
---
# <a name="enrich-customer-profiles-with-engagement-data-preview"></a>Obohaťte profily zákazníkov o údaje o interakciách (ukážka)

Použiť údaje z Microsoft Office 365 obohatiť profily svojich zákazníckych účtov o informácie o interakciách prostredníctvom Office 365 aplikácie. Údaje o interakciách pozostávajú z e-mailov a aktivít na stretnutiach, ktoré sú agregované na úrovni účtu. Napríklad počet e-mailov z obchodného účtu alebo počet stretnutí s účtom. Nie sú k dispozícii žiadne údaje o jednotlivých používateľoch. 

Toto obohatenie je dostupné v nasledujúcich regiónoch: Spojené kráľovstvo, Európa, Severná Amerika.

## <a name="prerequisites"></a>Požiadavky

Ak chcete nakonfigurovať obohatenie, musia byť splnené nasledujúce predpoklady:

- Máte aktívny Office 365 cloudová licencia.
- Máš [jednotné profily zákazníkov](customer-profiles.md) založené na [podnikateľské účty](work-with-business-accounts.md).
- Vaše prostredie Customer Insights musí mať a [Microsoft Dataverse pripojená organizácia](create-environment.md#step-3-connect-to-microsoft-dataverse).
- Máš [správca](permissions.md#admin) povolenia.
- Máte alebo môžete získať súhlas od svojho Office 365 správca nájomcu použiť Office 365 údaje poskytnúť **Prehľady pre organizáciu** v rámci aplikácií Dynamics 365.

## <a name="configure-the-enrichment"></a>Konfigurácia obohatenia

1. V prehľadoch cieľových skupín prejdite na **Údaje** > **Obohatenie**.

1. Choďte na **Objavte** kartu a vyberte **Obohaťte moje údaje** na **Zapojenie účtu** dlaždica.

   :::image type="content" source="media/enrichment-office-tile.png" alt-text="Dlaždica zapojenia účtu.":::
   
1. Vyberte **Ďalšie** v **Prehľad** krok a zadajte e-mailové adresy z vašej organizácie, pre ktoré sa budú agregovať údaje balíka Office. Pre relevantnú komunikáciu sa spracúvajú iba údaje z uvedených e-mailových adries. Osvedčeným postupom je použiť e-mailové skupiny, napr.*Predajný tím USA*, ktoré sa ľahko spravujú v Office 365. Počet e-mailových adries v skupinách je vyriešený a zobrazený. Celkový počet e-mailových adries musí byť aspoň 2 a nesmie presiahnuť 2 500.

   :::image type="content" source="media/enrichment-office-email-addresses.png" alt-text="E-mailové adresy na interakciu s účtom.":::

1. Skontrolujte vyhlásenie o súhlase, vyberte **Súhlasím** začiarknite políčko a vyberte **Ďalšie**.

1. Vyberte množinu údajov o zákazníkoch a vyberte **Ďalšie**.

1. Namapujte pole kontaktnej e-mailovej adresy a vyberte **Ďalšie**.

1. Skontrolujte konfiguráciu obohatenia, pomenujte obohatenie a vyberte **Ušetrite obohatenie** zachrániť obohatenie.

## <a name="office-365-tenant-administrator-consent"></a>Office 365 súhlas správcu nájomcu

Súhlas od an Office 365 nájomca správca je povinný aktivovať obohatenie. E-mail sa odošle na adresu Office 365 správcov nájomníkov, keď sa obohatenie uloží, čo ich požiada, aby skontrolovali a súhlasili s tým, aby aplikácie Dynamics 365 mohli používať Office 365 údaje poskytnúť **Prehľady pre organizáciu**. The Office 365 správca nájomcu môže súhlasiť aj priamo vo svojom Office 365 administrátorskej konzoly výberom **Prehľady pre organizáciu**.

## <a name="running-the-enrichment-for-the-first-time"></a>Spustenie obohatenia po prvýkrát

Keď sa obohacovanie začne po prvýkrát, po Office 365 správca nájomcu udelil súhlas, sťahovanie údajov z Office 365 začína. Tento proces trvá určitý čas. Prvý cyklus obohacovania bude naplánovaný so šesťhodinovým oneskorením. Počet dní, ktoré pokrývajú údaje, môžete vidieť na stránke prehľadu interakcií s účtom po dokončení rozšírenia. Pri veľkom objeme dát spustite obohatenie znova po niekoľkých dňoch. Zaisťuje kompletnosť údajov za celé časové okno, čo je jeden rok.

Ak chcete spustiť proces, vyberte **Bežať** na stránke konfigurácie interakcie s účtom. Okrem toho môžete nechať systém spustiť obohatenie automaticky ako súčasť a [plánované obnovenie](system.md#schedule-tab). Obohacovanie štandardne prebieha raz za týždeň.

V závislosti od veľkosti údajov balíka Office môže dokončenie procesu obohatenia trvať niekoľko hodín.

Keď spustíte obohatenie, spoločnosť Microsoft spracuje údaje v rámci Office 365 hranicu súladu na vytvorenie súhrnných štatistík, ktoré sa potom pridajú do vášho prostredia Customer Insights. Používateľom Customer Insights nebudú k dispozícii žiadne údaje na individuálnej úrovni (napríklad telo akéhokoľvek e-mailu alebo pozvánky v kalendári). 

[!INCLUDE [progress-details-pane](../includes/progress-details-pane.md)]

## <a name="enrichment-results"></a>Výsledky obohatenia

Po spustení procesu obohatenia prejdite na **Moje obohatenia** na preskúmanie výsledkov obohatenia. Nájdete tu celkový počet obohatených zákazníkov a prehľad výsledkov obohatenia. Zahŕňa počet spracovaných e-mailov a stretnutí, počet dní, za ktoré boli údaje agregované, a ďalšie.

Nájdete tu aj graf s počtom obohatených zákazníkov v priebehu času a náhľad údajov o obohatení.  

:::image type="content" source="media/enrichment-office-results-overview.png" alt-text="Ukážka výsledkov po spustení procesu obohacovania.":::

Všetky údaje sú agregované až po úroveň účtu. Systém vypočíta skóre zapojenia, ktoré sa pohybuje od 0 do 100, pre každý účet. Skóre zapojenia poskytuje zloženú mieru zapojenia účtu cez e-maily a stretnutia v porovnaní s vašimi ostatnými účtami. Nasledujúci zoznam obsahuje súhrnné údaje, ktoré poskytuje rozšírenie o interakciu s účtom:



| Údaje                                                                              | Názov stĺpca                              |
| :-------------------------------------------------------------------------------- |:---------------------------------------- |
| Skóre interakcie                                                                  |  EngagementScore                         |
| Počet e-mailov na účet                                                       |  NoOfEmails_ToAccount                    |
| Počet e-mailov z účtu                                                     |  NoOfEmails_FromAccount                  | 
| Počet stretnutí iniciovaných účtom                                           |  NoOfMeetings_FromAccount                | 
| Počet stretnutí iniciovaných vašou organizáciou                                 |  NoOfMeetings_ToAccount                  | 
| Počet ľudí z vašej organizácie na stretnutiach s účtom                  |  NoOfContactsInvolved_Meetings           | 
| Počet ľudí z vašej organizácie v e-mailových konverzáciách s účtom       |  NoOfContactsInvolved_Emails             | 
| Počet ľudí z účtu na stretnutiach s vašou organizáciou                  |  NoOfAccountContactsInvolved_Stretnutia    | 
| Počet ľudí z účtu v e-mailových konverzáciách s vašou organizáciou       |  NoOfAccountContactsInvolved_Emails      | 
| Dátum začiatku zapojenia (prvý e-mail alebo stretnutie v údajoch)                        |  EngagementStartDate                     | 
| Počet dní od posledného e-mailu                                                             |  DaysSinceLastEmail                      | 
| Dni od posledného stretnutia                                                           |  Dni od posledného stretnutia                    | 
| Priemerná dĺžka trvania stretnutí                                                      |  AverageDuration_Of_Meetings             | 
| Priemerné trvanie e-mailových odpovedí z účtu                                    |  AverageDuration_Of_AccountEmailReplies  | 
| Dátum začiatku agregácie                                                            |  AgregationStartDate                    | 
| Úroveň agregácie (rok, mesiac alebo týždeň)                                          |  AgregationLevel                        | 


Výberom skontrolujte obohatené údaje **Pozrieť viac** v sekcii ukážky. Otvára sa *Kancelária* subjekt. Môžete tiež nájsť subjekt uvedený v **Obohacovanie** skupina v **Údaje** > **entity**. Nájdete tu aj *Office_UserEntity*, ktorý obsahuje ID služby Active Directory pre e-mailové adresy, ktoré boli zvolené počas konfigurácie obohatenia 

## <a name="see-enrichment-data-on-the-customer-card"></a>Pozrite si údaje o obohatení na karte zákazníka

Zapojenie účtu je možné zobraziť aj na kartách jednotlivých zákazníkov. Prejdite na možnosť **Zákazníci** a zvoľte si profil zákazníka. Na karte zákazníka nájdete skóre zapojenia účtu, celkový počet e-mailov a celkový počet stretnutí za posledný rok. Nájdete tu aj grafy, ktoré zobrazujú históriu e-mailov a stretnutí.

:::image type="content" source="media/enrichment-office-customer-card.png" alt-text="Karta zákazníka s obohatenými údajmi.":::

## <a name="create-segments-and-measures-based-on-the-enriched-data"></a>Vytvárajte segmenty a miery na základe obohatených údajov

Obohatené údaje možno použiť na vytvorenie segmentov a meraní, ako je podrobne uvedené nižšie. Napríklad segment, ktorý obsahuje všetkých zákazníkov s hodnotou nad 60 pre *dní od posledného e-mailu* a *dní od posledného stretnutia*. Tento segment obsahuje zastarané účty, ktoré môžete skúsiť znova aktivovať. 

## <a name="next-steps"></a>Ďalšie kroky

[!INCLUDE [next-steps-enrichment](../includes/next-steps-enrichment.md)]


[!INCLUDE[footer-include](../includes/footer-banner.md)]
