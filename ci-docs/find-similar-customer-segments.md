---
title: Nájdite podobných zákazníkov pomocou AI (obsahuje video)
description: Nájdite podobné zákaznícke segmenty pomocou umelej inteligencie.
ms.date: 03/25/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-segment-builder
- ci-segment-insights
- customerInsights
ms.openlocfilehash: 7877349817829f7486a63a1355a81361e1cb2c13
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 04/27/2022
ms.locfileid: "8643391"
---
# <a name="similar-customers-preview"></a>Podobní zákazníci (ukážka)

Táto funkcia vám umožní nájsť podobných zákazníkov vo vašej zákazníckej základni pomocou umelej inteligencie. Aby ste mohli používať túto funkciu, musíte mať aspoň jeden segment. Rozšírenie kritérií existujúceho segmentu pomôže nájsť zákazníkov, ktorí sú podobní tomuto segmentu.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWOFou]

> [!NOTE]
> *Nájdite podobných zákazníkov* využíva automatizované prostriedky na vyhodnotenie údajov a vypracovanie predpovedí na základe týchto údajov, a preto má schopnosť použitia ako metódy profilovania, pretože tento pojem je vymedzený vo všeobecnom nariadení o ochrane údajov („GDPR“). Použitie tejto funkcie zákazníkom na spracovanie údajov môže podliehať GDPR alebo iným zákonom alebo predpisom. Ste zodpovední za zabezpečenie toho, že vaše používanie služby Dynamics 365 Customer Insights vrátane predikcií bude v súlade so všetkými platnými zákonmi a nariadeniami vrátane zákonov týkajúcich sa ochrany súkromia, osobných údajov, biometrických údajov, ochrany údajov a dôvernosti komunikácií.

## <a name="finding-similar-customers"></a>Hľadanie podobných zákazníkov

1. Ísť do **Segmenty** a vyberte segment, na ktorom chcete založiť nový segment. Toto je váš *zdrojový segment*.

1. Na paneli akcií vyberte položku **Vyhľadanie podobných zákazníkov**.

1. Skontrolujte navrhovaný názov nového segmentu a v prípade potreby ho zmeňte.

1. Prípadne pridajte [značky](work-with-tags-columns.md#manage-tags) do nového segmentu.

1. Skontrolujte polia, ktoré definujú váš nový segment. Tieto polia definujú základ, na ktorom sa systém pokúsi nájsť podobných zákazníkov ako váš zdrojový segment. Systém predvolene vyberie odporúčané polia.
  Polia, ktoré môžu výrazne znížiť výkon modelu, sú automaticky vylúčené:
  
   - Polia s nasledujúcimi typmi údajov: StringType, BooleanType, CharType, LongType, IntType, DoubleType, FloatType, ShortType
   - Polia s mohutnosťou (počet prvkov v poli) menšie ako 2 alebo viac ako 30

1. Vyberte, či chcete zahrnúť **Všetkých zákazníkov** alebo iba zákazníci v **Špecifickom existujúcom segmente** vo vašom novom segmente.

1. Systém predvolene navrhuje zahrnúť do výstupu iba 20 % cieľovej veľkosti publika. Upravte tento prah podľa potreby. Zvýšenie prahu zníži presnosť.

1. Zahrňte zákazníkov do zdrojového segmentu výberom možnosti **Okrem zákazníkov s podobnými atribútmi zahrňte aj členov zo zdrojového segmentu** začiarkavacie políčko.

1. Vyberte **Spustiť** v dolnej časti stránky na spustenie úlohy binárnej klasifikácie (metóda strojového učenia), ktorá analyzuje množinu údajov.

## <a name="view-the-similar-segment"></a>Zobraziť podobný segment

Po spracovaní podobného segmentu nájdete nový segment uvedený na stránke **Segmenty**.

> [!div class="mx-imgBorder"]
> ![Segment podobných zákazníkov.](media/expanded-segment.png "Segment podobných zákazníkov")

Vyberte **Zobraziť** na paneli akcií na otvorenie podrobností o segmente. Toto zobrazenie obsahuje informácie o distribúcii výsledkov naprieč [skóre podobnosti](#about-similarity-scores). Hodnoty skóre podobnosti nájdete aj v **Ukážke členov segmentu**.

## <a name="use-the-output-of-a-similar-segment"></a>Použite výstup podobného segmentu

Môžete [pracovať s výstupom podobného segmentu](segments.md) rovnako ako v prípade iných segmentov. Napríklad exportujte segment alebo vytvorte mieru.

## <a name="refresh-and-edit-a-similar-segment"></a>Obnovte a upravte podobný segment

Ak chcete obnoviť podobný segment, vyberte ho na stránke **Segmenty** a vyberte **Obnoviť** na paneli akcií.

Úpravou podobného segmentu sa znova spracujú vaše údaje. Predtým vytvorený segment sa aktualizuje aktualizovanými údajmi.
Ak chcete upraviť podobný segment, vyberte ho na stránke **Segmenty** a vyberte **Upraviť** na paneli akcií. Vykonajte zmeny a vyberte položku **Spustiť** na spustenie spracovania.

## <a name="delete-a-similar-segment"></a>Odstráňte podobný segment

Vyberte segment na stránke **Segmenty** a vyberte **Odstrániť** na paneli akcií. Potom potvrďte odstránenie.

## <a name="about-similarity-scores"></a>O skóre podobnosti

Model binárnej klasifikácie strojového učenia priraďuje skóre zákazníkom v podobnom segmente. Skóre je založené na podobnosti so zákazníkmi v segmente zdrojov.

- Skóre podobnosti pod 0,55 sú zákazníci klasifikovaní systémom ako *nie podobní* zákazníkom v zdrojovom segmente
- Skóre podobnosti medzi 0,55 – 0,7 sa klasifikuje ako *trochu podobní*
- Skóre podobnosti medzi 0,7 – 0,85 sa klasifikuje ako *podobní*
- Skóre podobnosti medzi 0,85 – 1 sú zákazníci klasifikovaní ako *veľmi podobní*

Zákazníci so skóre podobnosti pod 0,4 nie sú zahrnutí do výstupu modelu. Systém ich nepovažuje za dosť podobných zdrojovému segmentu.

[!INCLUDE [footer-include](includes/footer-banner.md)]
