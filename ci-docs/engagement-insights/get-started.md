---
title: Začíname s možnosťou prehľadov interakcií
description: Prehľad zdrojov pomoci, ktoré vám pomôžu rýchlo začať.
ms.reviewer: mhart
ms.author: jefhar
author: mochimochi016
ms.date: 12/21/2020
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: 5ee1567cea834670a16aaa3253912b7957ce26b3
ms.sourcegitcommit: 86739a3f238162fc96837270b5d184e648fab15c
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 08/20/2021
ms.locfileid: "7405377"
---
# <a name="get-started-with-dynamics-365-customer-insights-engagement-insights-capability-public-preview"></a>Začíname s možnosťou prehľadov interakcií Dynamics 365 Customer Insights (verejná verzia Preview)

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Prehľady interakcie je možnosť, ktorá vám umožňuje zhromažďovať a merať správanie zákazníkov na vašom webe. Integruje sa s možnosťami prehľadu cieľovej skupiny, takže vedľa prehľadov profilov zákazníkov môžete vidieť bohatú analýzu správania v reálnom čase. Odkazy v tomto článku vám pomôžu rýchlo nakonfigurovať a nastaviť vaše prostredie.

## <a name="step-1-review-prerequisites"></a>Krok 1: Pozrite si predpoklady

Najprv musíte mať aktívny používateľský účet Microsoft Azure Active Directory. Potom si prečítajte nasledujúce články pred vytvorením pracovného priestoru prehľadov interakcií.

- Prečítajte a odsúhlaste [Podmienky používania](terms-of-service.md) spoločnosti Microsoft.  
- Prečítajte si článok [Správa súborov cookie a súhlas používateľa](user-consent-storage.md). Po prečítaní tohto článku zvážte, či je potrebné aktualizovať upozornenie na súhlas používateľa. Ak ste predtým nemali „nepodstatné“ súbory cookie, pravdepodobne budete musieť aktualizovať svoje pravidlá pre webové stránky.
- Prečítajte si [slovník](glossary.md) na rýchly úvod do kľúčových pojmov a konceptov.

## <a name="step-2-explore-engagement-insights"></a>Krok 2: Preskúmajte prehľady interakcií

Pri prvej návšteve prehľadov interakcií môžete nakonfigurovať nastavenia, skontrolovať pravidlá a preskúmať produkt.

1. Prihláste sa do [portálu možností prehľadu interakcií](https://pi.dynamics.com) pomocou svojho používateľského účtu Microsoft Azure Active Directory. (Môže to byť váš školský alebo pracovný účet.)

1. Vyberte svoj región a pomocou začiarkavacieho políčka označte, či sa chcete prihlásiť na prijímanie aktualizácií a ponúk e-mailom.

1. Prečítajte si **podmienky používania (verzia Preview) prehľadov interakcie** a **Vyhlásenie o ochrane súkromia**. Odsúhlaste ich stlačením možnosti **Pozrieť ukážku**.

1. Preskúmajte produkt pomocou sady vzorových údajov.

##  <a name="step-3-set-up-a-workspace-and-add-code-to-your-website"></a>Krok 3: Vytvorte si pracovný priestor a pridajte kód na svoj web

Pracovný priestor je miestom, kde môžete zobraziť aktivitu používateľov v reálnom čase a ukladať a spravovať správy. Pridajte kód na svoj web a začnite zhromažďovať *udalosti*, údaje o činnosti, ktoré prichádzajú od používateľov.

1. [Vytvorenie pracovného priestoru](create-workspace.md) a pridanie členov.

1. [Pridajte kód do svojej webovej lokality](instrument-website.md) alebo [mobilnej aplikácie](developer-resources.md#capture-events-from-mobile-apps) a uvidíte aktivitu používateľov prichádzajúcich do vášho pracovného priestoru.

1. Zobrazte si [zostavu v reálnom čase](view-reports.md) s údajmi o aktívnych používateľov podľa prehľadávača, zariadenia, operačného systému, umiestnenia a jazyka. Môžete tiež vytvárať [vlastné zostavy](custom-reports.md) na vytvorenie vlastných vizualizácií.
    
## <a name="step-4-export-data-to-other-channels"></a>Krok 4: Exportujte údaje do iných kanálov

Môžete vytvárať *spresnené udalosti* (virtuálne zobrazenie) vašich webových analytických údajov. Potom údaje filtrujte a exportujte do Azure Data Lake Storage. Exportované údaje môžete prijať ako zdroj údajov. Ďalšie informácie nájdete v časti [Vytvorte prepojenie medzi prehľadmi cieľových skupín a prehľadmi interakcií](integrate-audience-insights-engagement-insights.md).

1. [Vytvorte spresnené udalosti](refined-events.md) pre export.

1. [Exportujte údaje](export-events.md) do Data Lake Storage.

1. Zistite, ako [odstrániť a exportovať údaje udalostí s obsahom osobných informácií](delete-export-personal-data.md).
 
## <a name="step-5-stay-connected"></a>Krok 5: Zostaňte v kontakte

Vážime si vašu aktívnu účasť a plánujeme vziať do úvahy všetku relevantnú spätnú väzbu pri vývoji budúcich vydaní. Podeľte sa o svoju spätnú väzbu a nahláste problémy jedným z týchto kanálov:
- [Komunita](https://go.microsoft.com/fwlink/?linkid=2141648)
- [Poskytnúť pripomienky](https://go.microsoft.com/fwlink/?linkid=2143222)
- [Požiadať o podporu](https://go.microsoft.com/fwlink/?linkid=2145734) 


[!INCLUDE[footer-include](../includes/footer-banner.md)]
