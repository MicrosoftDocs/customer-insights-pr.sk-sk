---
title: Mapovanie entít na účely zjednotenia údajov
description: Namapujte údaje na účely vytvorenia jednotných profilov zákazníkov.
ms.date: 09/25/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 36b7f7b2fac9497245cf6759506c53753972f173
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596012"
---
# <a name="map-entities-and-attributes"></a>Mapovanie entít a atribútov

**Mapovanie** je prvou fázou procesu zjednotenia údajov o prehľadoch cieľových skupín. Mapovanie pozostáva z troch fáz:

- *Výber entity*: Identifikujte kombinovateľné entity, ktoré vedú k množine údajov s úplnejšími informáciami o vašich zákazníkoch.
- *Výber atribútov*: Pre každú entitu identifikujte stĺpce, ktoré chcete kombinovať a zrovnať vo fázach *zosúladenia* a *zlúčenia*. Tieto stĺpce sa nazývajú *Atribúty*.
- *Výber primárneho kľúča a sémantického typu*: Pre každú entitu identifikujte atribút, ktorý chcete definovať ako primárny kľúč pre túto entitu. Pre každý atribút identifikujte sémantický typ, ktorý tento atribút najlepšie charakterizuje.

Ďalšie informácie o všeobecnom toku zjednotenia údajov nájdete v téme [Zjednotenie](data-unification.md).

## <a name="select-the-first-entities"></a>Vyberte prvé entity

1. V prehľadoch cieľových skupín prejdite na **Údaje** > **Zjednotiť** > **Namapovať**.

2. Ak chcete spustiť fázu mapovania, vyberte položku **Vybrať entity**.

3. Vyberte entity a atribúty, ktoré chcete použiť vo fázach *mapovania* a *zlúčenia*. Požadované atribúty môžete vybrať jednotlivo z entity alebo zahrnúť všetky atribúty z entity výberom začiarkavacieho políčka **Zahrnúť všetky polia** na úrovni entity. Odporúčame vybrať aspoň dve entity, ktoré majú ťažiť z procesu zjednotenia údajov.

   > [!div class="mx-imgBorder"]
   > ![Príklad pridania entít](media/data-manager-configure-map-add-entities-example.png "Príklad pridania entít")

   V tomto príklade pridávame entity **eCommerceContacts** a **loyCustomers**. Výberom týchto entít môžete získať informácie o tom, ktorí z online zákazníkov obchodu sú členmi vernostného programu.
   
   Môžete vyhľadávať kľúčové slová vo všetkých atribútoch a entitách a vybrať požadované atribúty, ktoré chcete mapovať.
   
     > [!div class="mx-imgBorder"]
   > ![Príklad vyhľadávacích polí](media/data-manager-configure-map-search-fields-example.png "Príklad vyhľadávacích polí")

4. Svoje výbery potvrďte výberom položky **Použiť**.

## <a name="select-primary-key-and-semantic-type-for-attributes"></a>Pre atribúty vyberte primárny kľúč a sémantický typ

Po výbere entít zobrazí stránka **Mapovať** vybrané entity na kontrolu. Definujte primárny kľúč pre entitu a identifikujte sémantický typ pre atribút v entite.

- **Primárny kľúč**: Vyberte jeden atribút ako primárny kľúč pre každú z vašich entít. Ak má byť atribút platným primárnym kľúčom, nemal by obsahovať duplicitné hodnoty, chýbajúce hodnoty ani nulové hodnoty. Atribúty reťazcov, celého čísla a údajových typov GUID sú podporované ako primárne kľúče a budú sa zobrazovať v poli, z ktorého si môžete vybrať.

- **Atribút sémantického typu**: Kategórie atribútov, napríklad e-mailová adresa alebo názov. Ak chcete používať modely umelej inteligencie pre inteligentnú predikciu sémantiky, ušetriť čas a zlepšiť presnosť, nastavte **Inteligentné mapovanie** na **ZAP.** Inteligentné mapovanie zdôrazňuje odporúčanie sémantiky založené na AI v poli **Typ**. Ak nastavíte na **VYP.**, uvidíte naše pravidelné odporúčania týkajúce sa mapovania. Z dostupného zoznamu možností môžete vybrať ľubovoľný sémantický typ a navrhovaný výber prepísať.

> [!div class="mx-imgBorder"]
> ![Typ atribútu a sémantické predikcia](media/data-manager-configure-map-add-attributes-semantic-prediction.png "Typ atribútu a sémantická predikcia")

Pridanie vlastného sémantického typu je tiež možné. Vyberte pole Typ pre atribút a zadajte názov vlastného sémantického typu. Takýmto spôsobom môžete tiež zmeniť typy atribútov, ktoré identifikoval systém.

Všetky atribúty, pre ktoré sa sémantický typ identifikoval automaticky, sú zoskupené v sekcii **Kontrola mapovaných polí**. Skontrolujte tieto atribúty a ich sémantické typy, pretože sa budú používať na kombináciu vašich entít v kroku zlúčenia zjednotenia údajov.

Atribúty, ktoré nie sú automaticky mapované na sémantický typ, sú zoskupené v sekcii **Definícia údajov v nemapovaných poliach**. Vyberte pole sémantického typu pre nemapované atribúty alebo zadajte vlastný názov typu atribútu.

> [!div class="mx-imgBorder"]
> ![Primárny kľúč a typ atribútu](media/data-manager-configure-map-add-attributes.png "Primárny kľúč a typ atribútu")

> [!NOTE]
> Jedno pole by sa malo namapovať na sémantický typ Person.FullName, aby sa vyplnilo meno zákazníka na karte zákazníka. V opačnom prípade sa zákaznícke karty zobrazia bez mena. 

## <a name="add-and-remove-attributes-and-entities"></a>Pridanie a odstránenie atribútov a entít

1. V ponuke **Zjednotiť** > **Mapovať** vyberte **Upraviť polia**.

2. Na table **Upraviť polia** môžete pridať alebo odstrániť atribúty a entity. Pomocou vyhľadávania alebo posúvania nájdite a vyberte atribúty a entity, ktoré vás zaujímajú. Atribút alebo entitu nemôžete odstrániť, ak už boli spárované.

   > [!div class="mx-imgBorder"]
   > ![Pridanie alebo odstránenie atribútov](media/configure-data-map-edit.png "Pridanie alebo odstránenie atribútov")

3. Vyberte **Použiť**.

## <a name="add-images-to-profiles"></a>Pridajte obrázky do profilov

Ak entita obsahuje adresy URL na verejne dostupné profilové obrázky alebo logá, môžete ich pridať do zjednoteného profilu zákazníka.

Vyberte entitu a vyhľadajte pole, ktoré obsahuje webovú adresu URL pre obrázok profilu. Vo vstupnom poli **Typ** zadajte manuálne niektorú z nasledujúcich hodnôt: 
- Pre osobu: Person.ProfileImage
- Pre organizáciu: Organization.LogoImage

Pokračujte v krokoch zjednotenia a zaistite, aby bol atribút, ktorý obsahuje adresu URL obrázka, tiež pridaný v kroku [Zlúčiť](merge-entities.md).

## <a name="set-attributes-for-organizations"></a>Nastavenie atribútov pre organizácie

Pre organizácie (ukážka) by mal byť typ atribútu mapovaný k položke „Organization.Name“.
> [!div class="mx-imgBorder"]
> ![Primárny kľúč a typ atribútu B2B](media/configure-data-map-edit-b2b.png "Primárny kľúč a typ atribútu B2B")

## <a name="next-step"></a>Nasledujúci krok

Ako súčasť procesu zjednotenia údajov prejdite na stránku **Zosúladenie**. Navštívte [**Zosúladenie**](match-entities.md), ak sa chcete dozvedieť o tejto fáze.

> [!TIP]
> Pozrite si nasledujúce video: [Začíname: Vytvorenie zjednoteného profilu zákazníka](https://youtu.be/oBfGEhucAxs).


[!INCLUDE[footer-include](../includes/footer-banner.md)]