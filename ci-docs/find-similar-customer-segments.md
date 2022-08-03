---
title: Nájdite podobných zákazníkov pomocou AI (ukážka) (obsahuje video)
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
ms.openlocfilehash: 09fe36a4da45d114cbfccf8dad1e7b80b4b7e320
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 07/18/2022
ms.locfileid: "9170746"
---
# <a name="find-similar-customers-with-ai-preview"></a>Nájdite podobných zákazníkov pomocou AI (ukážka)

Nájdite podobných zákazníkov vo svojej zákazníckej základni pomocou umelej inteligencie. Ak chcete použiť túto funkciu, musíte vytvoriť aspoň jeden segment. Rozšírenie kritérií existujúceho segmentu pomáha nájsť zákazníkov, ktorí sú podobní tomuto segmentu.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWOFou]

> [!NOTE]
> *Nájdite podobných zákazníkov* používa automatizované prostriedky na vyhodnocovanie údajov a vytváranie predpovedí na základe týchto údajov. Preto je možné ho použiť ako metódu profilovania, keďže tento pojem je definovaný všeobecným nariadením o ochrane údajov (ďalej len „GDPR“). Použitie tejto funkcie zákazníkom na spracovanie údajov môže podliehať GDPR alebo iným zákonom alebo predpisom. Ste zodpovední za zabezpečenie toho, že vaše používanie služby Dynamics 365 Customer Insights vrátane predikcií bude v súlade so všetkými platnými zákonmi a nariadeniami vrátane zákonov týkajúcich sa ochrany súkromia, osobných údajov, biometrických údajov, ochrany údajov a dôvernosti komunikácií.

## <a name="find-similar-customers"></a>Nájsť podobných zákazníkov

1. Ísť do **Segmenty** a vyberte segment, na ktorom chcete založiť nový segment. Toto je váš *zdrojový segment*.

1. Vyberte **Nájdite podobných zákazníkov**.

1. Skontrolujte navrhovaný názov nového segmentu a v prípade potreby ho zmeňte.

1. Prípadne pridajte [značky](work-with-tags-columns.md#manage-tags) do nového segmentu.

1. Skontrolujte polia, ktoré definujú váš nový segment. Tieto polia definujú základ, na ktorom sa systém pokúsi nájsť podobných zákazníkov ako váš zdrojový segment. Systém štandardne vyberá odporúčané polia. V prípade potreby pridajte ďalšie polia.
  Polia, ktoré môžu výrazne znížiť výkon modelu, sú automaticky vylúčené:
  
   - Polia s nasledujúcimi typmi údajov: StringType, BooleanType, CharType, LongType, IntType, DoubleType, FloatType, ShortType
   - Polia s mohutnosťou (počet prvkov v poli) menšie ako 2 alebo viac ako 30

1. Vyberte, či chcete zahrnúť **Všetci zákazníci** okrem zdrojového segmentu alebo iba zákazníkov v a **iný segment** vo svojom novom segmente.

1. Systém predvolene navrhuje zahrnúť do výstupu iba 20 % cieľovej veľkosti publika. Upravte tento prah podľa potreby. Zvýšenie prahu zníži presnosť.

1. Zahrňte zákazníkov do zdrojového segmentu výberom možnosti **Okrem zákazníkov s podobnými atribútmi zahrňte aj členov zo zdrojového segmentu** začiarkavacie políčko.

1. Vyberte **Bežať** v dolnej časti stránky začnite a [binárna klasifikačná úloha](#about-similarity-scores) (metóda strojové učenie), ktorá analyzuje súbor údajov.

## <a name="view-the-similar-segment"></a>Zobraziť podobný segment

Po spracovaní podobného segmentu nájdete nový segment uvedený na stránke **Segmenty** strana s typom **Rozšírenie**.

Vyberte **vyhliadka** aby ste videli rozloženie výsledkov [skóre podobnosti](#about-similarity-scores) a hodnoty skóre podobnosti pod **Ukážka členov segmentu**.

:::image type="content" source="media/expanded-segment.png" alt-text="Segment podobných zákazníkov.":::

## <a name="manage-a-similar-segment"></a>Spravujte podobný segment

[Pracujte a spravujte podobný segment](segments.md#manage-existing-segments) ako to robíte s inými segmentmi. Napríklad exportujte segment alebo vytvorte mieru.

Upravte, obnovte, premenujte, stiahnite a odstráňte podobný segment. Úpravou podobného segmentu sa znova spracujú vaše údaje. Predtým vytvorený segment sa aktualizuje aktualizovanými údajmi.

## <a name="about-similarity-scores"></a>O skóre podobnosti

Model binárnej klasifikácie strojového učenia priraďuje skóre zákazníkom v podobnom segmente. Skóre je založené na podobnosti so zákazníkmi v segmente zdrojov.

- Skóre podobnosti pod 0,55 sú zákazníci klasifikovaní systémom ako *nie podobní* zákazníkom v zdrojovom segmente
- Skóre podobnosti medzi 0,55 – 0,7 sa klasifikuje ako *trochu podobní*
- Skóre podobnosti medzi 0,7 – 0,85 sa klasifikuje ako *podobní*
- Skóre podobnosti medzi 0,85 – 1 sú zákazníci klasifikovaní ako *veľmi podobní*

Zákazníci so skóre podobnosti pod 0,4 nie sú zahrnutí do výstupu modelu. Systém ich nepovažuje za dosť podobných zdrojovému segmentu.

[!INCLUDE [footer-include](includes/footer-banner.md)]
