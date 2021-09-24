---
title: Začíname s možnosťou prehľadov interakcií
description: Prehľad zdrojov pomoci, ktoré vám pomôžu rýchlo začať.
ms.reviewer: mhart
ms.author: jefhar
author: mochimochi016
ms.date: 08/31/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: 644b125f5d140627d357630ded88dd6838d6edb7
ms.sourcegitcommit: fecdee73e26816c42d39d160d4d5cfb6c8a91596
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 09/15/2021
ms.locfileid: "7494613"
---
# <a name="get-started-with-dynamics-365-customer-insights-engagement-insights-capability-public-preview"></a>Začíname s možnosťou prehľadov interakcií Dynamics 365 Customer Insights (verejná verzia Preview)

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Prehľady interakcie je možnosť, ktorá vám umožňuje zhromažďovať a merať správanie zákazníkov na vašom webe. Integruje sa s možnosťami prehľadu cieľovej skupiny, takže vedľa prehľadov profilov zákazníkov môžete vidieť bohatú analýzu správania v reálnom čase. Odkazy v tomto článku vám pomôžu rýchlo nakonfigurovať a nastaviť vaše prostredie.

## <a name="step-1-review-prerequisites"></a>Krok 1: Pozrite si predpoklady

Najprv musíte mať aktívny používateľský účet Microsoft Azure Active Directory (AAD). Potom si prečítajte nasledujúce články pred vytvorením pracovného priestoru prehľadov interakcií.

- Prečítajte a odsúhlaste [Podmienky používania](terms-of-service.md) spoločnosti Microsoft.  
- Prečítajte si článok [Správa súborov cookie a súhlas používateľa](user-consent-storage.md). Potom uvážte, či je treba aktualizovať upozornenie na súhlas používateľa. Ak ste predtým nemali „nepodstatné“ súbory cookie, pravdepodobne budete musieť aktualizovať svoje pravidlá pre webové stránky.
- Prečítajte si [slovník](glossary.md) na rýchly úvod do kľúčových pojmov a konceptov.

## <a name="step-2-explore-engagement-insights"></a>Krok 2: Preskúmajte prehľady interakcií

Pri prvej návšteve prehľadov interakcií je možné nakonfigurovať nastavenia, skontrolovať zásady a preskúmať funkcie.

1. Prihláste sa do [portálu schopností pre prehľad interakcií](https://home.ci.ai.dynamics.com/app/engagement-insights) s použitím vášho používateľského (školského či pracovného) účtu Microsoft AAD.

1. Ak chcete dostávať e-mailové aktualizácie a ponuky, vyberte svoj región a označte začiarkavacie políčko.

1. Pozrite si súbor **prehľady interakcie (ukážka) – podmienky používania** a **Vyhlásenie o ochrane osobných údajov** a potom vyberte položku **Preskúmať ukážku**, čím prijmete tieto nastavenia.

1. Preskúmajte produkt pomocou sady vzorových údajov.

##  <a name="step-3-set-up-a-workspace-and-add-code-to-your-website"></a>Krok 3: Vytvorte si pracovný priestor a pridajte kód na svoj web

Pracovný priestor je miesto, kde môžete v reálnom čase sledovať aktivitu používateľov a ukladať a spravovať zostavy. Pridajte kód na svoj web a začnite zhromažďovať *udalosti*, údaje o činnosti, ktoré prichádzajú od používateľov.

1. [Vytvorenie pracovného priestoru](create-workspace.md) a pridanie členov.

1. [Pridajte kód do svojej webovej lokality](instrument-website.md) alebo [mobilnej aplikácie](developer-resources.md#capture-events-from-mobile-apps) a uvidíte aktivitu používateľov prichádzajúcich do vášho pracovného priestoru.

1. Zobrazte [správu v reálnom čase](view-reports.md), ktorá zobrazí aktívnych používateľov podľa prehliadača, zariadenia, operačného používaného systému, polohy a jazyka. Môžete tiež vytvárať [vlastné zostavy](custom-reports.md) na vytvorenie vlastných vizualizácií.
    
## <a name="step-4-export-data-to-other-channels"></a>Krok 4: Exportujte údaje do iných kanálov

Môžete vytvárať *spresnené udalosti* (virtuálne zobrazenie) vašich webových analytických údajov. Potom údaje filtrujte a exportujte do Azure Data Lake Storage. Exportované údaje môžete prijať ako zdroj údajov. Ďalšie informácie nájdete v časti [Vytvorte prepojenie medzi prehľadmi cieľových skupín a prehľadmi interakcií](integrate-audience-insights-engagement-insights.md).

1. [Vytvorte spresnené udalosti](refined-events.md) pre export.

1. [Exportujte údaje](export-events.md) do Data Lake Storage.

1. [Vytvorte prepojenie medzi štatistikami cieľovej skupiny a štatistikami interakcií](integrate-audience-insights-engagement-insights.md), a zdieľajte údaje medzi týmito dvomi funkciami.

1. Zistite, ako [odstrániť a exportovať údaje udalostí s obsahom osobných informácií](delete-export-personal-data.md).
 
## <a name="step-5-stay-connected"></a>Krok 5: Zostaňte v kontakte

Ceníme si vašu aktívnu účasť a pri vývoji všetkých vydaní v budúcnosti berieme do úvahy všetku príslušnú spätnú väzbu. Podeľte sa o svoju spätnú väzbu a nahláste problémy jedným z týchto kanálov:
- [Komunita](https://go.microsoft.com/fwlink/?linkid=2141648)
- [Poskytnúť pripomienky](https://go.microsoft.com/fwlink/?linkid=2143222)
- [Požiadať o podporu](https://go.microsoft.com/fwlink/?linkid=2145734) 


[!INCLUDE[footer-include](../includes/footer-banner.md)]
