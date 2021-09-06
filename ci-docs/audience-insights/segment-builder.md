---
title: Slúži na vytvorenie a spravovanie segmentov
description: Vytvorenie segmentov zákazníkov na ich zoskupenie na základe rôznych atribútov.
ms.date: 07/18/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: e759872643cc7387cf732d73c7a320ae8901e5a9
ms.sourcegitcommit: 42692a815695b9fdc93b9358eae09f2c3e97293c
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 08/13/2021
ms.locfileid: "7377807"
---
# <a name="create-and-manage-segments"></a>Slúži na vytvorenie a spravovanie segmentov

> [!IMPORTANT]
> V septembri 2021 bude v prostredí vytvárania segmentov zavedených niekoľko zmien: 
> - Zostavovač segmentov sa bude mierne líšiť vďaka novonavrhnutým prvkov a vylepšenému používateľskému postupu.
> - V zostavovači segmentov sú zapnuté nové operátory dátumu a času a vylepšený nástroj na výber dátumu.
> - Budete môcť pridať alebo odstrániť podmienky a pravidlá zo segmentov. 
> - K dispozícii budú vnorené pravidlá, ktoré sa začínajú podmienkou OR. Na vonkajšej vrstve už nie je potrebná podmienka AND.
> - Bočná tabla na výber atribútov bude neustále k dispozícii.
> - Možnosť výberu ciest vyjadrujúcich vzťahy entít.
> Pokiaľ chcete vyskúšať nový nástroj na tvorbu segmentov, odošlite e-mail s predmetom „Žiadosť o povolenie nového nástroja na tvorbu segmentov“ na adresu cihelp [at] microsoft.com. Uveďte názov svojej organizácie a ID vášho testovacieho prostredia.
> :::image type="content" source="media/segment-builder-overview.png" alt-text="Prvky zostavovača segmentov." lightbox="media/segment-builder-overview.png":::
>
> 1 – Organizujte svoj segment pomocou pravidiel a podskupín. Každé pravidlo alebo čiastkové pravidlo pozostáva z podmienok. Skombinujte podmienky s logickými operátormi
>
> 2 – Vyberte položku [postup vzťahu](relationships.md) medzi entitami, ktoré sa vzťahujú na pravidlo. Postup vzťahu určuje, ktoré atribúty je možné použiť v podmienke.
>
> 3 – Spravujte pravidlá a čiastkové pravidlá. Zmeňte pozíciu pravidla alebo ho odstráňte.
>
> 4 – Pridajte podmienky a vytvorte správnu úroveň vnorenia pomocou podradených pravidiel.
>
> 5 – Aplikujte nastavené operácie na prepojené pravidlá.
>
> 6 – Pomocou tably atribútov pridajte dostupné atribúty entity alebo vytvorte podmienky na základe atribútov. Tabla zobrazuje zoznam entít a atribútov na základe vybraného postupu vzťahu, ktoré sú k dispozícii pre vybraté pravidlo.
>
> 7 – Pridajte podmienky na základe atribútov k existujúcim pravidlám a čiastkovým pravidlám alebo ich pridajte do nového pravidla.
>
> 8 – Pri vytváraní segmentu sa zmeny vrátia a znova vykonajú.

Definujte komplexné filtre okolo zjednotenej entity zákazníka a jej súvisiacich entít. Každý segment po spracovaní vytvorí skupinu zákazníckych záznamov, ktoré môžete exportovať a podniknúť kroky. Segmenty sú spravované na stránke **Segmenty**. 

Nasledujúci príklad ilustruje možnosti segmentácie. Definovali sme segment pre zákazníkov, ktorí za posledných 90 dní objednali tovar aspoň za 500 USD *a* ktorí boli zapojení do hovoru služieb pre zákazníkov, ktorý bol eskalovaný.

:::image type="content" source="media/segmentation-group1-2.png" alt-text="Snímka obrazovky používateľského rozhrania nástroja na tvorbu segmentov s dvoma skupinami, ktoré určujú segment zákazníka.":::

## <a name="create-a-new-segment"></a>Vytvorenie nového segmentu

Existuje niekoľko spôsobov, ako vytvoriť nový segment. Táto časť popisuje, ako vytvoriť *prázdny segment* od začiatku. Môžete tiež vytvoriť *rýchly segment* na základe existujúcich entít alebo využite modely strojového učenia na získanie *navrhovaných segmentov*. Ďalšie informácie: [Prehľad segmentov](segments.md).

Pri vytváraní segmentu môžete uložiť koncept. Bude uložený ako neaktívny segment a nemožno ho aktivovať, pretože je dokončený s platnou konfiguráciou.

1. Prejdite na stránku **Segmenty**.

1. Vyberte **Nový** > **Prázdny segment**.

1. Na table **Nový segment** vyberte typ segmentu:

   - **Dynamické segmenty** [sa obnovujú](segments.md#refresh-segments) podľa opakujúceho sa harmonogramu.
   - **Statické segmenty** sa spustia raz po vytvorení.

1. Uveďte **Názov výstupnej entity** pre daný segment. Voliteľne uveďte zobrazovaný názov a popis, ktorý pomôže identifikovať segment.

1. Vyberte **Ďalšie** a prejdite na stránku **Tvorca segmentov**, kde definujete skupinu. Skupina je množina zákazníkov.

1. Vyberte entity, ktorá obsahuje atribút, podľa ktorého chcete segmentovať.

1. Vyberte atribút pre segment podľa. Tento atribút môže mať jeden zo štyroch typov hodnôt: číselný, reťazec, dátum alebo logický.

1. Vyberte operátora a hodnotu pre vybraného atribútu.

   > [!div class="mx-imgBorder"]
   > ![Filter vlastnej skupiny.](media/customer-group-numbers.png "Filter skupiny zákazníkov")

   |Číslo |Definícia  |
   |---------|---------|
   |1     |Entity          |
   |2     |Atribút          |
   |3    |Operátor         |
   |4    |Hodnota         |

   1. Na pridanie ďalších podmienok do skupiny môžete použiť dva logické operátory:

      - Operátor **A**: Obe podmienky musia byť splnené ako súčasť procesu segmentácie. Táto voľba je najužitočnejšia, keď definujete podmienky pre rôzne entity.

      - Operátor **ALEBO**: V rámci procesu segmentácie musí byť splnená jedna z podmienok. Táto voľba je najužitočnejšia, keď definujete viac podmienok pre jednu entitu.

      > [!div class="mx-imgBorder"]
      > ![Operátor ALEBO, ktorý musí splniť ktorúkoľvek z podmienok.](media/segmentation-either-condition.png "Operátor ALEBO, ktorý musí splniť ktorúkoľvek z podmienok")

      V súčasnosti je možné vnoriť operátor **ALEBO** pod operátor **A**, ale nie naopak.

   1. Každá skupina zodpovedá skupine zákazníkov. Skupiny môžete skombinovať tak, aby zahŕňali zákazníkov požadovaných pre váš obchodný prípad.    
   Vyberte **Pridať skupinu**.

      > [!div class="mx-imgBorder"]
      > ![Skupina zákazníkov – pridanie skupiny.](media/customer-group-add-group.png "Skupina zákazníkov – pridanie skupiny")

   1. Vyberte jedného z nastavených operátorov: **Zjednotiť**, **Prienik** alebo **Okrem**.

   > [!div class="mx-imgBorder"]
   > ![Skupina zákazníkov – pridanie zjednotenia.](media/customer-group-union.png "Skupina zákazníkov – pridanie zjednotenia")

   - **Zjednotenie** zjednocuje obe skupiny.

   - **Prienik** prekrýva obe skupiny. Iba údaje, ktoré *sú spoločné* pre obe skupiny, sa zachovávajú v zjednotenej skupine.

   - Možnosť **Okrem** kombinuje dve skupiny. Zachovajú sa iba údaje v skupine A, ktoré *nie sú spoločné* s údajmi v skupine B.

1. Ak je entita prepojená so zjednotenou entitou zákazníka prostredníctvom [vzťahov](relationships.md), musíte definovať cestu vzťahov, aby ste vytvorili platný segment. Pridajte entity z cesty vzťahov, kým si nevyberiete entitu **Zákazník: CustomerInsights** z rozbaľovacej ponuky. Potom stlačte možnosť **Všetky záznamy** pre každý krok.

   > [!div class="mx-imgBorder"]
   > ![Cesta vzťahov pri vytváraní segmentov.](media/segments-multiple-relationships.png "Cesta vzťahov pri vytváraní segmentov")

1. V predvolenom nastavení segmenty generujú výstupnú entitu, ktorá obsahuje všetky atribúty profilov zákazníkov, ktoré zodpovedajú definovaným filtrom. Ak je segment založený na iných entitách ako entita *Zákazník*, môžete do výstupnej entity pridať ďalšie atribúty z týchto entít. Stlačte možnosť **Atribúty projektu** na výber atribútov, ktoré sa pripoja k výstupnej entite.  
  
   Príklad: Segment je založený na entite, ktorá obsahuje údaje o činnosti zákazníkov súvisiace s entitou *Zákazník*. Segment vyhľadáva všetkých zákazníkov, ktorí zavolali na technickú podporu za posledných 60 dní. Môžete sa rozhodnúť pridať trvanie hovoru a počet hovorov ku všetkým zodpovedajúcim záznamom zákazníka vo výstupnej entite. Tieto informácie môžu byť užitočné pri zasielaní e-mailov s užitočnými odkazmi na články online pomoci a časté otázky zákazníkom, ktorí často volali.

   > [!NOTE]
   > - Projektované atribúty fungujú iba pre entity, ktoré majú vzťah typu jedna k mnohým so entitou zákazníka. Napríklad jeden zákazník môže mať viac predplatných.
   > - Atribúty môžete projektovať iba z entity, ktorá sa používa v každej skupine segmentových dotazov, ktoré zostavujete.
   > - Pri použití množinových operátorov sa zohľadňujú projektované atribúty.

1. Segment uložte výberom položky **Uložiť**. Váš segment bude uložený a spracovaný, ak budú splnené všetky požiadavky. V opačnom prípade sa uloží ako koncept.

1. Ak sa chcete vrátiť späť na stránku **Segmenty**, vyberte **Späť na segmenty**.



## <a name="quick-segments"></a>Rýchle segmenty

Rýchle segmenty vám umožňujú rýchlo vytvárať jednoduché segmenty pomocou jedného operátora a získať tak rýchlejší prehľad.

1. Na stránke **Segmenty** stlačte možnosť **Nový** > **Vytvoriť z**.

   - Vyberte možnosť **Profily** na vytvorenie segmentu, ktorý je založený na *zjednotenej entite zákazníka*.
   - Stlačte možnosť **Opatrenia** a vytvorte segment okolo opatrení, ktoré ste predtým vytvorili.
   - Vyberte možnosť **Analýza** na zostavenie segmentu okolo jednej z výstupných entít, ktoré ste vygenerovali pomocou funkcií **Predpovede** alebo **Vlastné modely**.

2. V dialógovom okne **Nový rýchly segment** vyberte atribút z rozbaľovacej ponuky **Pole**.

3. Systém poskytne niektoré ďalšie informácie, ktoré vám pomôžu vytvoriť lepšie segmenty vašich zákazníkov.
   - Pre kategorické polia zobrazíme 10 najvyšších počtov zákazníkov. Vyberte **Hodnota** a potom **Skontrolovať**.

   - Pokiaľ ide o číselný atribút, systém ukáže, ktorá hodnota atribútu spadá pod percentil každého zákazníka. Vyberte **Operátor** a **Hodnota**, potom vyberte **Skontrolovať**.

4. Systém vám poskytne **Odhadovanú veľkosť segmentu**. Môžete si vybrať, či chcete vygenerovať segment, ktorý ste definovali, alebo ho znova opraviť, aby ste získali inú veľkosť segmentu.

    > [!div class="mx-imgBorder"]
    > ![Názov a odhad rýchleho segmentu.](media/quick-segment-name.png "Názov a odhad rýchleho segmentu")

5. Zadajte **Názov** pre svoj segment. Voliteľne zadajte **Zobrazovaný názov**.

6. Výberom položky **Uložiť** vytvorte segment.

7. Po dokončení spracovania môžete segment zobraziť ako akýkoľvek iný segment, ktorý ste vytvorili.

## <a name="next-steps"></a>Ďalšie kroky

[Exportujte segment](export-destinations.md) a preskúmajte časť [Integrácia karty zákazníka](customer-card-add-in.md) na používanie segmentov v iných aplikáciách.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
