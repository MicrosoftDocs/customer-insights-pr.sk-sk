---
title: Vyberte zdrojové polia na zjednotenie údajov
description: Prvým krokom v procese zjednotenia je výber entít, atribútov, primárnych kľúčov a sémantických typov na mapovanie údajov do jednotného profilu zákazníka.
recommendations: false
ms.date: 04/22/2022
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
ms.openlocfilehash: a75218c996b277e00924f2b7b38ea686a1f4dc38
ms.sourcegitcommit: 3c5b0b40b2b45e420015bbdd228ce0e610245e6f
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 07/12/2022
ms.locfileid: "9139801"
---
# <a name="select-source-fields-for-data-unification"></a>Vyberte zdrojové polia na zjednotenie údajov

Prvým krokom pri zjednotení je výber entít a polí vo vašich množinách údajov, ktoré chcete zjednotiť. Vyberte entity, ktoré obsahujú podrobnosti týkajúce sa zákazníka, ako je meno, adresa, telefónne číslo a e-mail. Môžete vybrať jednu alebo viac entít.

## <a name="select-entities-and-fields"></a>Výber entít a polí

1. Ísť do **Údaje** > **Zjednotiť**.

   :::image type="content" source="media/m3_unify_land.png" alt-text="Snímka obrazovky zjednotenia vstupnej stránky pre prvé spustenie so zvýraznenou možnosťou Začať.":::

1. Vyberte **Začíname**.

1. Na **Zdrojové polia** stránku, vyberte **Vyberte entity a polia**. The **Vyberte entity a polia** panel zobrazí.

1. Vyberte aspoň jednu entitu.

1. Pre každú vybratú entitu identifikujte polia, ktoré chcete použiť na priradenie záznamov zákazníkov a polia, ktoré sa majú zahrnúť do zjednoteného profilu. Tieto polia sú tzv *Atribúty*. Môžete vybrať požadované atribúty jednotlivo z entity alebo zahrnúť všetky atribúty z entity začiarknutím políčka na úrovni entity. Môžete vyhľadávať kľúčové slová vo všetkých atribútoch a entitách a vybrať požadované atribúty, ktoré chcete mapovať.

   :::image type="content" source="media/m3_select_entities.png" alt-text="Snímka obrazovky vybraných entít a atribútov.":::

   V tomto príklade pridávame **Kontakty** a **Zákaznícka lojalita** subjektov. Výberom týchto entít môžete získať informácie o tom, ktorí z online zákazníkov obchodu sú členmi vernostného programu.

1. Svoje výbery potvrďte výberom položky **Použiť**. Zobrazia sa vybrané entity a atribúty.

## <a name="select-primary-key-and-semantic-type-for-attributes"></a>Pre atribúty vyberte primárny kľúč a sémantický typ

   :::image type="content" source="media/m3_select_primary.png" alt-text="Snímka obrazovky vybratých entít s nevybratým primárnym kľúčom." lightbox="media/m3_select_primary.png":::

Pre každú entitu vykonajte nasledujúce kroky.

1. Vyber **Primárny kľúč**. Primárny kľúč je atribút jedinečný pre entitu. Ak má byť atribút platným primárnym kľúčom, nemal by obsahovať duplicitné hodnoty, chýbajúce hodnoty ani nulové hodnoty. Ako primárne kľúče sú podporované atribúty typu reťazec, celé číslo a GUID.

1. Ak chcete používať modely AI pre inteligentnú predikcia sémantiky, ušetrite čas a zvýšte presnosť, zaistite **Inteligentné mapovanie** je zapnutá. Inteligentné mapovanie zdôrazňuje odporúčanie sémantiky založené na AI v poli **Typ**. Navrhovaný výber môžete prepísať výberom ľubovoľného sémantického typu z dostupného zoznamu možností.

1. Pre každý atribút vyberte sémantiku **Typ** ktorý najlepšie vystihuje daný atribút, napríklad meno, mesto alebo e-mailová adresa.

   > [!NOTE]
   > Jedno pole by sa malo namapovať na sémantický typ *Osoba.Celé meno* na vyplnenie mena zákazníka v zákazníckej karte. V opačnom prípade sa zákaznícke karty zobrazia bez mena.

   1. Ak chcete zmeniť typ atribútu identifikovaný systémom, vyberte iný typ. Ak typ neexistuje, vytvorte vlastný sémantický typ výberom **Typ** pole pre atribút a zadanie názvu vlastného sémantického typu.

   1. Ak chcete pridať atribút, ktorý obsahuje adresu URL, k verejne dostupným profilovým obrázkom alebo logám, vyberte entitu a pole, ktoré obsahuje adresu URL. V **Typ** do poľa zadajte nasledovné:
      - Pre osobu: Person.ProfileImage
      - Pre organizáciu: Organization.LogoImage

   1. Pre atribút názvu účtu zadajte do poľa „Organization.Name“.**Typ** lúka.

1. Skontrolujte atribúty, v ktorých sa automaticky identifikuje sémantický typ. Tieto atribúty sú uvedené pod **Skontrolujte namapované polia**. V súbore je možné kombinovať iba atribúty rovnakého typu **Zjednotené zákaznícke polia** krok. Sémantické typy sa používajú na automatické navrhovanie prehľadov. Uistite sa, že typy, ktoré ste vybrali, sú konzistentné vo všetkých vybratých entitách.

1. V prípade atribútov, ktoré nie sú automaticky namapované na sémantický typ, vyberte pole sémantického typu, zadajte názov vlastného typu atribútu alebo ich nechajte nenamapované. Tieto atribúty sú uvedené pod **Definujte údaje v nezmapovaných poliach**.

1. Po dokončení krokov pre každú entitu vyberte **Uložiť zdrojové polia**.

1. Vyberte **Ďalej**.

> [!div class="nextstepaction"]
> [Ďalší krok: Odstráňte duplikáty](remove-duplicates.md)

[!INCLUDE [footer-include](includes/footer-banner.md)]
