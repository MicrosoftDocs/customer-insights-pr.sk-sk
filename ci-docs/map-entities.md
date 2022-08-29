---
title: Vyberte zdrojové polia na zjednotenie údajov
description: Prvým krokom v procese zjednotenia je výber entít, atribútov, primárnych kľúčov a sémantických typov na mapovanie údajov do jednotného profilu zákazníka.
recommendations: false
ms.date: 08/12/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: v-wendysmith
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-map
- ci-match
- customerInsights
ms.openlocfilehash: bc120aa7a3713e1184ff278edf0942925faafa12
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304584"
---
# <a name="select-source-fields-for-data-unification"></a>Vyberte zdrojové polia na zjednotenie údajov

Prvým krokom pri zjednotení je výber entít a polí vo vašich množinách údajov, ktoré chcete zjednotiť. Vyberte entity, ktoré obsahujú podrobnosti týkajúce sa zákazníka, ako je meno, adresa, telefónne číslo a e-mail. Môžete vybrať jednu alebo viac entít.

[!INCLUDE [m3-first-run-note](includes/m3-first-run-note.md)]

## <a name="select-entities-and-fields"></a>Výber entít a polí

1. Ísť do **Údaje** > **Zjednotiť**.

   Pre individuálnych zákazníkov (B-to-C) je **Zjednotiť** zobrazenie vstupnej stránky **Začať** na prvom kroku, **Zdrojové polia**.

   :::image type="content" source="media/m3_unify_land.png" alt-text="Snímka obrazovky zjednotenia vstupnej stránky na prvé spustenie pre jednotlivých zákazníkov.":::

   Pre podnikateľské účty (B-to-B) **Zjednotiť** zobrazí vstupnú stránku **Zjednotiť účty** zobrazujúci **Začať** na prvom kroku, **Zdrojové polia**. The **Zjednotiť kontakty (ukážka)** kroky sú voliteľné a čakajú na dokončenie zjednotenia účtu.

   :::image type="content" source="media/b2b_unify_land.png" alt-text="Snímka obrazovky zjednotenia vstupnej stránky pre prvé spustenie pre firemné účty.":::

1. Vyberte **Začíname**.

1. Na **Zdrojové polia** stránku, vyberte **Vyberte entity a polia**. The **Vyberte entity a polia** panel zobrazí.

1. Vyberte aspoň jednu entitu.

1. Pre každú vybratú entitu identifikujte polia, ktoré chcete použiť na priradenie záznamov zákazníkov a polia, ktoré sa majú zahrnúť do zjednoteného profilu. Tieto polia sú tzv *Atribúty*. Môžete vybrať požadované atribúty jednotlivo z entity alebo zahrnúť všetky atribúty z entity začiarknutím políčka na úrovni entity. Môžete vyhľadávať kľúčové slová vo všetkých atribútoch a entitách a vybrať požadované atribúty, ktoré chcete mapovať.

   :::image type="content" source="media/m3_select_entities.png" alt-text="Snímka obrazovky vybraných entít a atribútov.":::

   V tomto príklade pridávame **kontakty elektronického obchodu** a **loyZákazník** subjektov. Výberom týchto entít môžete získať informácie o tom, ktorí z online zákazníkov obchodu sú členmi vernostného programu.

1. Svoje výbery potvrďte výberom položky **Použiť**. Zobrazia sa vybrané entity a atribúty.

## <a name="select-primary-key-and-semantic-type-for-attributes"></a>Pre atribúty vyberte primárny kľúč a sémantický typ

   :::image type="content" source="media/m3_select_primary.png" alt-text="Snímka obrazovky vybratých entít, pričom primárny kľúč ešte nie je vybratý." lightbox="media/m3_select_primary.png":::

Pre každú entitu vykonajte nasledujúce kroky.

1. Vyber **Primárny kľúč**. Primárny kľúč je atribút jedinečný pre entitu. Ak má byť atribút platným primárnym kľúčom, nemal by obsahovať duplicitné hodnoty, chýbajúce hodnoty ani nulové hodnoty. Ako primárne kľúče sú podporované atribúty typu reťazec, celé číslo a GUID.

1. Ak chcete používať modely AI pre inteligentnú predikcia sémantiky, ktorá šetrí čas a zvyšuje presnosť, zaistite **Inteligentné mapovanie** je zapnutá. Inteligentné mapovanie poskytuje sémantické odporúčania založené na AI v **Typ** lúka.

1. Pre každý atribút vyberte sémantiku **Typ** ktorý najlepšie vystihuje daný atribút, napríklad meno, mesto alebo e-mailová adresa.

   > [!NOTE]
   > V B-to-C by sa jedno pole malo mapovať na sémantický typ *Osoba.Celé meno* na vyplnenie mena zákazníka v zákazníckej karte. V B-to-B by mal názov účtu mapovať na *Organization.Name*. V opačnom prípade sa zákaznícke karty zobrazia bez mena.

   1. Ak chcete prepísať typ atribútu identifikovaný systémom, vyberte inú možnosť. Ak typ neexistuje, vytvorte vlastný sémantický typ výberom položky **Typ** pole pre atribút a zadanie názvu vlastného sémantického typu.

   1. Ak chcete pridať atribút, ktorý obsahuje adresu URL, k verejne dostupným profilovým obrázkom alebo logám, vyberte entitu a pole, ktoré obsahuje adresu URL. V **Typ** do poľa zadajte nasledovné:
      - Pre osobu: Person.ProfileImage
      - Pre organizáciu: Organization.LogoImage

1. Skontrolujte atribúty, v ktorých sa automaticky identifikuje sémantický typ. Tieto atribúty sú uvedené pod **Skontrolujte namapované polia**. V súbore je možné kombinovať iba atribúty rovnakého typu **Zjednotiť zákaznícke polia** krok. Sémantické typy sa používajú na automatické navrhovanie prehľadov. Uistite sa, že typy, ktoré ste vybrali, sú konzistentné vo všetkých vybratých entitách.

1. V prípade atribútov, ktoré nie sú automaticky namapované na sémantický typ, vyberte pole sémantického typu, zadajte názov vlastného typu atribútu alebo ich nechajte nenamapované. Tieto atribúty sú uvedené pod **Definujte údaje v nezmapovaných poliach**.

1. Po dokončení krokov pre každú entitu vyberte **Uložiť zdrojové polia**.

1. Vyberte **Ďalej**.

> [!div class="nextstepaction"]
> [Ďalší krok: Odstráňte duplikáty](remove-duplicates.md)

[!INCLUDE [footer-include](includes/footer-banner.md)]
