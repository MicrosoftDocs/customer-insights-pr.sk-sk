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
ms.openlocfilehash: eeabd889f7b694f8d809894169a3cdc068acc340
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 04/27/2022
ms.locfileid: "8643139"
---
# <a name="use-a-template-to-build-a-measure"></a>Na vytvorenie miery použite šablónu

Môžete použiť preddefinované šablóny bežne používaných [Opatrenia](measures.md) na ich vytvorenie. Podrobné popisy šablón a sprievodca vám pomôže s efektívnym vytváraním opatrení. Šablóny vychádzajú z mapovaných údajov z entity *Zjednotená aktivita*. Uistite sa teda, že ste nakonfigurovali [aktivity zákazníkov](activities.md) pred vytvorením merania zo šablóny.

Ak chcete vytvoriť vlastné miery, pozrite si [Použite nástroj na tvorbu opatrení na vytvorenie mier od začiatku](measure-builder.md).

# <a name="individual-consumers-b-to-c"></a>[Jednotliví spotrebitelia (firma a spotrebiteľ)](#tab/b2c)

Dostupné šablóny merania: 
- Priemerná hodnota transakcie (ATV)
- Celková hodnota transakcií
- Priemerný denný výnos
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

1. V časti **Nastaviť časové obdobie** definujte časový rámec údajov, ktoré sa majú použiť. Vyberte, či chcete, aby nové opatrenie pokrylo celú množinu údajov tak, že vyberiete možnosť **Celkovo**, alebo či chcete, aby sa opatrenie zameralo na **Konkrétne časové obdobie**.

   :::image type="content" source="media/measure-set-time-period.png" alt-text="Snímka obrazovky zobrazujúca sekciu časového obdobia pri konfigurácii merania zo šablóny.":::

1. V ďalšej časti vyberte možnosť **Pridať údaje** a vyberte si činnosti a namapujte príslušné údaje z vašej entity *Zjednotenej aktivity*.

    1. Krok 1 z 2: V časti **Typ činnosti**, vyberte typ entity, ktorú chcete použiť. Pre **Činnosti**, vyberte entity, ktoré chcete mapovať.
    1. Krok 2 z 2: Vyberte atribút z entity *Zjednotená činnosť* pre komponent požadovaný vzorcom. Napríklad pre Priemernú hodnotu transakcie je to atribút predstavujúci hodnotu Transakcie. Pre **Časová pečiatka aktivity** vyberte atribút z entity Unified Activity, ktorá predstavuje dátum a čas aktivity.
   
1. Po úspešnom mapovaní údajov môžete vidieť stav ako **Dokončené** a názov mapovaných aktivít a atribútov.

1. Teraz môžete stlačiť možnosť **Spustiť** na výpočet výsledkov opatrenia. Ak ju chcete neskôr spresniť, stlačte možnosť **Uložiť koncept**.

# <a name="business-accounts-b-to-b"></a>[Firemné obchodné vzťahy (firma a firma)](#tab/b2b)

Táto funkcia je k dispozícii iba pre miery vytvorené v prostrediach s individuálnymi zákazníkmi ako primárnym cieľovým publikom.

---
