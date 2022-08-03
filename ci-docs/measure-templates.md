---
title: Vytvorte miery zo šablón
description: Definujte miery pomocou šablón pre bežné prípady použitia.
ms.date: 03/25/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: v-wendysmith
ms.author: wameng
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-measure-template
- customerInsights
ms.openlocfilehash: 6dc7fce78d10ba91de4b2abf54c6c6ab1c919d3a
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 07/18/2022
ms.locfileid: "9170792"
---
# <a name="create-measures-from-templates"></a>Vytvorte miery zo šablón

Použite preddefinované šablóny bežne používaných [Opatrenia](measures.md) aby ste ich vytvorili. Šablóny vychádzajú z mapovaných údajov z entity *Zjednotená aktivita*. Uistite sa teda, že ste nakonfigurovali [aktivity zákazníkov](activities.md) pred vytvorením merania zo šablóny.

Šablóny meraní sú podporované iba v prostrediach pre **individuálnych zákazníkov**. Ak chcete vytvoriť vlastné miery alebo vytvoriť miery pre B-to-B, pozri [Použite nástroj na tvorbu opatrení](measure-builder.md).

Dostupné šablóny merania:
- Priemerná hodnota transakcie (ATV)
- Celková hodnota transakcií
- Priemerný denný výnos
- Priemerný mesačný výnos
- Priemerný ročný výnos
- Počet transakcií
- Získané vernostné body
- Uplatnené vernostné body
- Zostatok vernostných bodov
- Životnosť aktívneho zákazníka
- Trvanie členstva vo vernostnom programe
- Čas od posledného nákupu

## <a name="build-a-new-measure-using-a-template"></a>Vytvorte nové opatrenie pomocou šablóny

1. Ísť do **Opatrenia**.

1. Stlačte **Nový** a stlačte **Výber šablóny**.

   :::image type="content" source="media/measure-use-template.png" alt-text="Snímka obrazovky s rozbaľovacou ponukou pri vytváraní nového opatrenia so zvýraznením šablóny.":::

1. Nájdite šablónu, ktorá vyhovuje vašim potrebám, a stlačte možnosť **Vybrať šablónu**.

1. Skontrolujte požadované údaje a vyberte **Začíname**, ak máte všetky údaje uvedené.

1. Vyberte **Upraviť podrobnosti** vedľa názvu miery. Zadajte názov opatrenia. Prípadne pridajte [značky](work-with-tags-columns.md#manage-tags) na mieru.

   :::image type="content" source="media/measures_edit_details.png" alt-text="Dialógové okno Upraviť podrobnosti.":::

1. Vyberte položku **Hotovo**.

1. V **Nastavte časové obdobie** definujte časový rámec údajov. Vyberte, či chcete, aby nové opatrenie pokrylo celú množinu údajov tak, že vyberiete možnosť **Celkovo**, alebo či chcete, aby sa opatrenie zameralo na **Konkrétne časové obdobie**.

   :::image type="content" source="media/measure-set-time-period.png" alt-text="Snímka obrazovky zobrazujúca sekciu časového obdobia pri konfigurácii merania zo šablóny.":::

1. V ďalšej časti vyberte možnosť **Pridať údaje** a vyberte si činnosti a namapujte príslušné údaje z vašej entity *Zjednotenej aktivity*.

    1. Krok 1 z 2: V časti **Typ činnosti**, vyberte typ entity, ktorú chcete použiť. Pre **Aktivity**, vyberte entity, ktoré chcete mapovať, a potom vyberte **Ďalšie**.
    1. Krok 2 z 2: Vyberte atribút z entity *Zjednotená činnosť* pre komponent požadovaný vzorcom. Napríklad pre Priemernú hodnotu transakcie je to atribút predstavujúci hodnotu Transakcie. Pre **Časová pečiatka aktivity**, vyberte atribút z *Jednotná aktivita* subjekt, ktorý predstavuje dátum a čas činnosti.
    1. Vyberte **Uložiť**.

    Keď je mapovanie údajov úspešné, zobrazí sa stav **Dokončiť** a zobrazí sa názov mapovaných aktivít a atribútov.

1. Vyberte **Bežať** na výpočet výsledkov merania. Vyberte **Uložiť koncept** ak chcete zachovať aktuálnu konfiguráciu a spustiť meranie neskôr. The **Opatrenia** zobrazí stránka.

## <a name="next-step"></a>Ďalší krok

Na vytvorenie použite existujúce opatrenia [zákaznícky segment](segments.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
