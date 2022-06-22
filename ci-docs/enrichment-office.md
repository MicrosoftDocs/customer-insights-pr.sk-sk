---
title: Obohaťte zákaznícke profily o údaje z Microsoft Office 365
description: Použiť proprietárne údaje z Microsoft Office obohatiť svoje profily zákazníkov o údaje o interakciách.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahl
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 7192b7680e73a581dd603de174c57b20bec996dd
ms.sourcegitcommit: 27c5473eecd851263e60b2b6c96f6c0a99d68acb
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 06/13/2022
ms.locfileid: "8954152"
---
# <a name="enrich-customer-profiles-with-engagement-data-preview"></a>Obohaťte profily zákazníkov o údaje o interakciách (ukážka)

Použiť údaje z Microsoft Office 365 obohatiť profily svojich zákazníckych účtov o informácie o interakciách prostredníctvom Office 365 aplikácie. Údaje o interakciách pozostávajú z e-mailov a aktivít na stretnutiach, ktoré sú agregované na úrovni účtu. Napríklad počet e-mailov z obchodného účtu alebo počet stretnutí s účtom. Nie sú k dispozícii žiadne údaje o jednotlivých používateľoch.

## <a name="supported-countries-or-regions"></a>Podporované krajiny alebo regióny

V súčasnosti podporujeme tieto regióny: Veľká Británia, Európa, Severná Amerika.

## <a name="prerequisites"></a>Požiadavky

- Aktívny Office 365 cloudová licencia.
- [Zjednotené profily zákazníkov](customer-profiles.md) založené na [podnikateľské účty](work-with-business-accounts.md).
- A [Microsoft Dataverse pripojená organizácia](create-environment.md#step-3-connect-to-microsoft-dataverse) vo vašom prostredí Customer Insights.
- [správca](permissions.md#admin) povolenia.
- Súhlas od vášho Office 365 správca nájomcu použiť Office 365 údaje poskytnúť **Prehľady pre organizáciu** v rámci aplikácií Dynamics 365.

## <a name="configure-the-enrichment"></a>Konfigurácia obohatenia

1. Prejdite na **Údaje** > **Obohatenie** a vyberte kartu **Objavovať**.

1. Vyberte **Obohaťte moje údaje** na **Zapojenie účtu** dlaždica.

   :::image type="content" source="media/enrichment-office-tile.png" alt-text="Dlaždica zapojenia účtu.":::

1. Skontrolujte prehľad a potom vyberte **Ďalšie**.

1. Zadajte e-mailové adresy z vašej organizácie, pre ktoré sa budú agregovať údaje balíka Office. Pre relevantnú komunikáciu sa spracúvajú iba údaje z uvedených e-mailových adries. Osvedčeným postupom je použiť e-mailové skupiny, napr.*Predajný tím USA*, v ktorom môžete spravovať Office 365. Počet e-mailových adries v skupinách je vyriešený a zobrazený. Celkový počet e-mailových adries musí byť aspoň 2 a nesmie presiahnuť 2 500.

   :::image type="content" source="media/enrichment-office-email-addresses.png" alt-text="E-mailové adresy na interakciu s účtom.":::

1. Skontrolujte a poskytnite svoj súhlas [Office 365 súhlas správcu nájomcu](#office-365-tenant-administrator-consent) výberom **Súhlasím**.

1. Vyberte **Ďalej**.

1. Vyberte **Súbor kontaktných údajov** a vyberte si profil, ktorý chcete obohatiť. Vyberte **Ďalej**.

1. Namapujte pole kontaktnej e-mailovej adresy a vyberte **Ďalšie**.

1. Poskytnúť **názov** za obohatenie a **Výstupná entita**.

1. Stlačte možnosť **Uložiť obohatenie** po preskúmaní vašich možností.

1. Vyberte **Zavrieť** vrátiť sa do **Obohatenia** stránku.

### <a name="office-365-tenant-administrator-consent"></a>Office 365 súhlas správcu nájomcu

Súhlas od an Office 365 nájomca správca je povinný aktivovať obohatenie. E-mail sa odošle na adresu Office 365 správcov nájomníkov, keď sa obohatenie uloží, čo ich požiada, aby skontrolovali a súhlasili s tým, aby aplikácie Dynamics 365 mohli používať Office 365 údaje poskytnúť **Prehľady pre organizáciu**. The Office 365 správca nájomcu môže súhlasiť aj priamo vo svojom Office 365 administrátorskej konzoly výberom **Prehľady pre organizáciu**.

## <a name="running-the-enrichment-for-the-first-time"></a>Spustenie obohatenia po prvýkrát

Keď sa obohacovanie začne po prvýkrát, po Office 365 správca nájomcu udelil súhlas, sťahovanie údajov z Office 365 začína. Tento proces trvá určitý čas. Prvý cyklus obohacovania bude naplánovaný so šesťhodinovým oneskorením. Počet dní, ktoré údaje pokrývajú, môžete vidieť na stránke prehľadu interakcií s účtom po dokončení rozšírenia. Pri veľkom objeme dát spustite obohatenie znova po niekoľkých dňoch. Zabezpečuje kompletnosť údajov za celé časové okno, čo je jeden rok.

V závislosti od veľkosti údajov balíka Office môže dokončenie procesu obohatenia trvať niekoľko hodín.

Keď spustíte obohatenie, spoločnosť Microsoft spracuje údaje v rámci Office 365 hranicu súladu, aby ste vytvorili súhrnné štatistiky, ktoré sa potom pridajú do vášho prostredia Customer Insights. Používateľom Customer Insights nebudú k dispozícii žiadne údaje na individuálnej úrovni (napríklad telo akéhokoľvek e-mailu alebo pozvánky v kalendári).

Vyberte **Bežať** začať proces obohacovania.

[!INCLUDE [progress-details-pane](includes/progress-details-pane.md)]

## <a name="enrichment-results"></a>Výsledky obohatenia

[!INCLUDE [enrichment-results](includes/enrichment-results.md)] To je *Kancelária* subjekt. The *Office_UserEntity* obsahuje ID služby Active Directory pre e-mailové adresy, ktoré boli zvolené počas konfigurácie obohatenia.

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

## <a name="see-enrichment-data-on-the-customer-card"></a>Pozrite si údaje o obohatení na karte zákazníka

Zapojenie účtu je možné zobraziť aj na kartách jednotlivých zákazníkov. Prejdite na možnosť **Zákazníci** a zvoľte si profil zákazníka. Na karte zákazníka nájdete skóre zapojenia účtu, celkový počet e-mailov a celkový počet stretnutí za posledný rok. Nájdete tu aj grafy, ktoré zobrazujú históriu e-mailov a stretnutí.

:::image type="content" source="media/enrichment-office-customer-card.png" alt-text="Karta zákazníka s obohatenými údajmi.":::

## <a name="next-steps"></a>Ďalšie kroky

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]
Napríklad segment, ktorý obsahuje všetkých zákazníkov s hodnotou nad 60 pre *dní od posledného e-mailu* a *dní od posledného stretnutia*. Tento segment obsahuje zastarané účty, ktoré môžete skúsiť znova aktivovať.

[!INCLUDE [footer-include](includes/footer-banner.md)]
