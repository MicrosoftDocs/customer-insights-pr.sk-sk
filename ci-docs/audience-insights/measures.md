---
title: Vytváranie a spravovanie mier
description: Definujte miery na analýzu a zobrazovanie výkonnosti vášho podnikania.
ms.date: 09/30/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wameng
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 39acca78c022bc15ebc15dc80f21fe175da04d4d
ms.sourcegitcommit: 5d82e5b808517e0e99fdfdd7e4a4422a5b8ebd5c
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 10/11/2021
ms.locfileid: "7623051"
---
# <a name="define-and-manage-measures"></a>Definovanie a spravovanie mier

Opatrenia vám pomôžu lepšie pochopiť správanie zákazníkov a výkonnosť podniku. Pozerajú sa na príslušné hodnoty zo [zjednotených profilov](data-unification.md). Firma chce napríklad vidieť *celkové výdavky na zákazníka*, aby pochopila históriu nákupov tohto zákazníka alebo zistila *celkové predaje spoločnosti* s cieľom porozumieť agregovaným výnosom v celej firme.  

Miery sa vytvárajú pomocou nástroja na tvorbu mier, platformy na dotazovanie údajov s rôznymi operátormi a jednoduchými možnosťami mapovania. Umožňujú vám filtrovať údaje, zoskupovať výsledky, zisťovať [cesty vzťahov medzi entitami](relationships.md) a zobrazovať ukážku výstupu.

Použite nástroj na tvorbu mier na plánovanie obchodných aktivít dotazovaním na údaje o zákazníkoch a získavaním prehľadov. Napríklad vytvorenie miery *celkové výdavky na zákazníka* a *celková návratnosť na zákazníka* pomáha identifikovať skupinu zákazníkov s vysokými výdavkami, ale s vysokou návratnosťou. Môžete [vytvoriť segment](segments.md) na podporu ďalších najvhodnejších akcií. 

## <a name="build-your-own-measure-from-scratch"></a>Vytvorte si vlastné meranie úplne od začiatku

Táto sekcia vás prevedie vytvorením novej miery od nuly. Mieru môžete vytvoriť pomocou atribútov údajov z údajových entít, ktoré majú nastavený vzťah na prepojenie s entitou zjednoteného profilu zákazníka.

# <a name="individual-customers-b2c"></a>[Individuálni zákazníci (B2C)](#tab/b2c)

1. V prehľadoch cieľových skupín prejdite na **Miery**.

1. Vyberte **Nový** a stlačte **Vytvorte si vlastnú**.

1. Vyberte **Upraviť názov** a zadajte **Názov** miery. 

1. V konfiguračnej oblasti vyberte agregačnú funkciu z rozbaľovacej ponuky **Vybrať funkciu**. Medzi agregačné funkcie patria: 
   - **Sum**
   - **Priemer**
   - **Obchodný vzťah**
   - **Počet jedinečných**
   - **Max**
   - **Minimum**
   - **Prvé**: berie prvú hodnotu dátového záznamu
   - **Posledné**: berie poslednú hodnotu, ktorá bola pridaná do dátového záznamu

   :::image type="content" source="media/measure-operators.png" alt-text="Operátory výpočtov miery.":::

1. Vyberte **Pridať atribút** a vyberte údaje, ktoré potrebujete na vytvorenie tejto miery.
   
   1. Vyberte karty **Atribúty**. 
   1. Dátová entita: Vyberte entitu, ktorá obsahuje atribút, ktorý chcete merať. 
   1. Atribút údajov: Vyberte atribút, ktorý chcete použiť vo funkcii agregácie na výpočet miery. Môžete vybrať iba jeden atribút naraz.
   1. Atribút údajov môžete vybrať aj z existujúcej miery výberom karty **Miery**. Alebo môžete vyhľadať názov entity alebo miery. 
   1. Vyberte **Pridať** na pridanie vybraného atribútu k miere.

   :::image type="content" source="media/measure-attribute-selection.png" alt-text="Vyberte atribút, ktorý sa má použiť pri výpočtoch.":::

1. Ak chcete vytvoriť zložitejšie miery, môžete pridať ďalšie atribúty alebo použiť matematické operátory svojej funkcie miery.

   :::image type="content" source="media/measure-math-operators.png" alt-text="Vytvorte komplexné miery s matematickými operátormi.":::

1. Ak chcete pridať filtre, vyberte **Filtrovať** v konfiguračnej oblasti. 
  
   1. V sekcii **Pridať atribút** na table **Filtre** vyberte atribút, ktorý chcete použiť na vytvorenie filtrov.
   1. Nastavte operátory filtra tak, aby definovali filter pre každý vybraný atribút.
   1. Vyberte **Použiť** na pridanie filtrov k miere.

1. Ak chcete pridať dimenzie, vyberte **Dimenzie** v konfiguračnej oblasti. Dimenzie sa zobrazia ako stĺpce v entite výstupu miery.
 
   1. Vyberte **Upraviť dimenzie**, ak chcete pridať atribúty údajov, podľa ktorých chcete zoskupiť namerané hodnoty. Napríklad mesto alebo pohlavie. V predvolenom nastavení je vybraná dimenzia *CustomerID* na vytvorenie *mier na úrovni zákazníka*. Ak chcete vytvoriť *miery na úrovni podniku*, môžete odstrániť predvolenú dimenziu.
   1. Vyberte **Hotovo** na pridanie dimenzie k miere.

1. Ak vo vašich údajoch existujú hodnoty, ktoré je potrebné nahradiť celým číslom, vyberte položku **Pravidlá**. Nakonfigurujte pravidlo a uistite sa, že ste ako náhradu vybrali iba celé čísla. Napríklad nahraďte *null* s *0*.

1. Ak existuje viac postupov medzi dátovou entitou, ktorú ste mapovali, a entitou *zákazníka*, musíte zvoliť jednu z identifikovaných [postupov vzťahov medzi entitami](relationships.md). Výsledky mier sa môžu líšiť v závislosti od zvoleného postupu. 
   
   1. Vyberte **Cesta vyjadrujúca vzťah** a vyberte cestu entity, ktorá by mala byť použitá na identifikáciu vašej miery. Ak existuje iba jedna cesta k entite *Zákazník*, tento ovládací prvok sa nezobrazí.
   1. Výberom možnosti **Hotovo** použite svoj výber. 

   :::image type="content" source="media/measures-data-preferences.png" alt-text="Vyberte postup entity pre mieru.":::

1. Ak chcete pridať ďalšie výpočty miery, vyberte položku **Nový výpočet**. Na nové výpočty môžete použiť iba entity v tom istom postupe entity. Ďalšie výpočty sa zobrazia ako nové stĺpce v entite výstupu miery.

1. Vyberte **...** vo výpočte na **Duplikovanie**, **Premenovanie** alebo **Odstránenie** výpočtu z miery.

1. V oblasti **Ukážka** uvidíte dátovú schému entity výstupu miery vrátane filtrov a dimenzií. Ukážka dynamicky reaguje na zmeny v konfigurácii.

1. Vyberte **Spustiť** na výpočet výsledkov pre nakonfigurovanú mieru. Vyberte **Uložiť a zavrieť**, ak si chcete ponechať aktuálnu konfiguráciu a mieru spustiť neskôr.

1. Prechodom na možnosť **Miery** zobrazíte novovytvorenú mieru v zozname.

# <a name="business-accounts-b2b"></a>[Firemné obchodné vzťahy (B2B)](#tab/b2b)

1. V prehľadoch cieľových skupín prejdite na **Miery**.

1. Vyberte **Nový** a stlačte **Vytvorte si vlastnú**.

1. Vyberte **Upraviť názov** a zadajte **Názov** miery. 

1. V konfiguračnej oblasti vyberte agregačnú funkciu z rozbaľovacej ponuky **Vybrať funkciu**. Medzi agregačné funkcie patria: 
   - **Sum**
   - **Priemer**
   - **Obchodný vzťah**
   - **Počet jedinečných**
   - **Max**
   - **Minimum**
   - **Prvé**: berie prvú hodnotu dátového záznamu
   - **Posledné**: berie poslednú hodnotu, ktorá bola pridaná do dátového záznamu

   :::image type="content" source="media/measure-operators.png" alt-text="Operátory výpočtov miery.":::

1. Vyberte **Pridať atribút** a vyberte údaje, ktoré potrebujete na vytvorenie tejto miery.
   
   1. Vyberte karty **Atribúty**. 
   1. Dátová entita: Vyberte entitu, ktorá obsahuje atribút, ktorý chcete merať. 
   1. Atribút údajov: Vyberte atribút, ktorý chcete použiť vo funkcii agregácie na výpočet miery. Môžete vybrať iba jeden atribút naraz.
   1. Atribút údajov môžete vybrať aj z existujúcej miery výberom karty **Miery**. Alebo môžete vyhľadať názov entity alebo miery. 
   1. Vyberte **Pridať** na pridanie vybraného atribútu k miere.

   :::image type="content" source="media/measure-attribute-selection.png" alt-text="Vyberte atribút, ktorý sa má použiť pri výpočtoch.":::

1. Ak chcete vytvoriť zložitejšie miery, môžete pridať ďalšie atribúty alebo použiť matematické operátory svojej funkcie miery.

   :::image type="content" source="media/measure-math-operators.png" alt-text="Vytvorte komplexné miery s matematickými operátormi.":::

1. Ak chcete pridať filtre, vyberte **Filtrovať** v konfiguračnej oblasti. 
  
   1. V sekcii **Pridať atribút** na table **Filtre** vyberte atribút, ktorý chcete použiť na vytvorenie filtrov.
   1. Nastavte operátory filtra tak, aby definovali filter pre každý vybraný atribút.
   1. Vyberte **Použiť** na pridanie filtrov k miere.

1. Ak chcete pridať dimenzie, vyberte **Dimenzie** v konfiguračnej oblasti. Dimenzie sa zobrazia ako stĺpce v entite výstupu miery.
 
   1. Vyberte **Upraviť dimenzie**, ak chcete pridať atribúty údajov, podľa ktorých chcete zoskupiť namerané hodnoty. Napríklad mesto alebo pohlavie. V predvolenom nastavení je vybraná dimenzia *CustomerID* na vytvorenie *mier na úrovni zákazníka*. Ak chcete vytvoriť *miery na úrovni podniku*, môžete odstrániť predvolenú dimenziu.
   1. Vyberte **Hotovo** na pridanie dimenzie k miere.

1. Ak vo vašich údajoch existujú hodnoty, ktoré je potrebné nahradiť celým číslom, vyberte položku **Pravidlá**. Nakonfigurujte pravidlo a uistite sa, že ste ako náhradu vybrali iba celé čísla. Napríklad nahraďte *null* s *0*.

1. Môžete použiť prepínač **Zahrnúť podradené obchodné vzťahy**, ak [používate obchodné vzťahy s hierarchiami](relationships.md#set-up-account-hierarchies).
   - Ak je nastavené na **Vyp.** miera sa vypočíta pre každý obchodný vzťah. Každý obchodný vzťah má svoj vlastný výsledok.
   - Ak je nastavený na **Zap.**, vyberte **Upraviť** a zvoľte hierarchiu účtov podľa prijatých hierarchií. Miera prinesie iba jeden výsledok, pretože je agregovaná s podradenými obchodnými vzťahmi.

1. Ak existuje viac postupov medzi dátovou entitou, ktorú ste mapovali, a entitou *zákazníka*, musíte zvoliť jednu z identifikovaných [postupov vzťahov medzi entitami](relationships.md). Výsledky mier sa môžu líšiť v závislosti od zvoleného postupu. 
   
   1. Vyberte **Cesta vyjadrujúca vzťah** a vyberte cestu entity, ktorá by mala byť použitá na identifikáciu vašej miery. Ak existuje iba jedna cesta k entite *Zákazník*, tento ovládací prvok sa nezobrazí.
   1. Výberom možnosti **Hotovo** použite svoj výber. 

   :::image type="content" source="media/measures-data-preferences.png" alt-text="Vyberte postup entity pre mieru.":::

1. Vyberte **...** vo výpočte na **Duplikovanie**, **Premenovanie** alebo **Odstránenie** výpočtu z miery.

1. V oblasti **Ukážka** uvidíte dátovú schému entity výstupu miery vrátane filtrov a dimenzií. Ukážka dynamicky reaguje na zmeny v konfigurácii.

1. Vyberte **Spustiť** na výpočet výsledkov pre nakonfigurovanú mieru. Vyberte **Uložiť a zavrieť**, ak si chcete ponechať aktuálnu konfiguráciu a mieru spustiť neskôr.

1. Prechodom na možnosť **Miery** zobrazíte novovytvorenú mieru v zozname.

---

## <a name="use-a-template-to-build-a-measure"></a>Na vytvorenie miery použite šablónu

Na ich vytvorenie môžete použiť preddefinované šablóny bežne používaných meraní. Podrobné popisy šablón a sprievodca vám pomôže s efektívnym vytváraním opatrení. Šablóny vychádzajú z mapovaných údajov z entity *Zjednotená aktivita*. Uistite sa teda, že ste nakonfigurovali [aktivity zákazníkov](activities.md) pred vytvorením merania zo šablóny.

# <a name="individual-customers-b2c"></a>[Individuálni zákazníci (B2C)](#tab/b2c)

Na ich vytvorenie môžete použiť preddefinované šablóny bežne používaných meraní. Podrobné popisy šablón a sprievodca vám pomôže s efektívnym vytváraním opatrení. Šablóny vychádzajú z mapovaných údajov z entity *Zjednotená aktivita*. Uistite sa teda, že ste nakonfigurovali [aktivity zákazníkov](activities.md) pred vytvorením merania zo šablóny.

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

Nasledujúci postup popisuje kroky na vytvorenie nového opatrenia pomocou šablóny.

1. V prehľadoch cieľových skupín prejdite na **Miery**.

1. Stlačte **Nový** a stlačte **Výber šablóny**.

   :::image type="content" source="media/measure-use-template.png" alt-text="Snímka obrazovky s rozbaľovacou ponukou pri vytváraní nového opatrenia so zvýraznením šablóny.":::

1. Nájdite šablónu, ktorá vyhovuje vašim potrebám, a stlačte možnosť **Vybrať šablónu**.

1. Skontrolujte požadované údaje a vyberte **Začíname**, ak máte všetky údaje uvedené.

1. Na table **Upraviť názov** nastavte názov svojej miery a výstupnú entitu. 

1. Vyberte položku **Hotovo**.

1. V časti **Nastaviť časové obdobie** definujte časový rámec údajov, ktoré sa majú použiť. Vyberte, či chcete, aby nové opatrenie pokrylo celú množinu údajov tak, že vyberiete možnosť **Celkovo**, alebo či chcete, aby sa opatrenie zameralo na **Konkrétne časové obdobie**.

   :::image type="content" source="media/measure-set-time-period.png" alt-text="Snímka obrazovky zobrazujúca sekciu časového obdobia pri konfigurácii merania zo šablóny.":::

1. V ďalšej časti vyberte možnosť **Pridať údaje** a vyberte si činnosti a namapujte príslušné údaje z vašej entity *Zjednotenej aktivity*.

    1. Krok 1 z 2: V časti **Typ činnosti**, vyberte typ entity, ktorú chcete použiť. Pre **Činnosti**, vyberte entity, ktoré chcete mapovať.
    1. Krok 2 z 2: Vyberte atribút z entity *Zjednotená činnosť* pre komponent požadovaný vzorcom. Napríklad pre Priemernú hodnotu transakcie je to atribút predstavujúci hodnotu Transakcie. Pre **Časová pečiatka aktivity** vyberte atribút z entity Unified Activity, ktorá predstavuje dátum a čas aktivity.
   
1. Po úspešnom mapovaní údajov môžete vidieť stav ako **Dokončené** a názov mapovaných aktivít a atribútov.

   :::image type="content" source="media/measure-template-configured.png" alt-text="Snímka obrazovky z dokončenej konfigurácie šablóny mierky.":::

1. Teraz môžete stlačiť možnosť **Spustiť** na výpočet výsledkov opatrenia. Ak ju chcete neskôr spresniť, stlačte možnosť **Uložiť koncept**.

# <a name="business-accounts-b2b"></a>[Firemné obchodné vzťahy (B2B)](#tab/b2b)

Táto funkcia je k dispozícii iba pre miery vytvorené v prostrediach s individuálnymi zákazníkmi ako primárnym cieľovým publikom.

---

## <a name="manage-your-measures"></a>Spravovanie mier

Zoznam opatrení nájdete na stránke **Miery**.

Nájdete informácie o type miery, jej tvorcovi, dátume vytvorenia, statuse a stave. Keď vyberiete opatrenie zo zoznamu, môžete si pozrieť verziu Preview výstupu a stiahnuť súbor vo formáte CSV.

Ak chcete obnoviť všetky svoje miery naraz, vyberte položku **Obnoviť všetko** bez výberu konkrétnej miery.

> [!div class="mx-imgBorder"]
> ![Akcie na spravovanie jednotlivých opatrení.](media/measure-actions.png "Akcie na spravovanie jednotlivých opatrení.")

Vyberte mieru zo zoznamu a zobrazte nasledujúce možnosti:

- Kliknutím na názov miery zobrazíte podrobnosti.
- **Upravte** konfiguráciu miery.
- **Obnovte** mieru na základe najnovších údajov.
- **Premenujte** mieru.
- **Odstráňte** mieru.
- **Aktivujte** alebo **Deaktivujte**. Neaktívne miery sa počas [plánovaného obnovenia](system.md#schedule-tab) neobnovujú.

> [!TIP]
> Existuje [šesť druhov stavov](system.md#status-types) pre úlohy/procesy. Okrem toho väčšina procesov [závisí na ďalších nadväzujúcich procesoch](system.md#refresh-policies). Môžete si vybrať stav procesu a zobraziť podrobnosti o priebehu celej úlohy. Po výbere možnosti **Zobraziť podrobnosti** pre jednu z pracovných úloh nájdete ďalšie informácie: čas spracovania, posledný dátum spracovania a všetky chyby a varovania spojené s danou úlohou.

## <a name="next-step"></a>Nasledujúci krok

Existujúce opatrenia môžete použiť na vytvorenie [zákazníckeho segmentu](segments.md).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
