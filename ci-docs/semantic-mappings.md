---
title: Sémantické mapovanie (Preview)
description: Prehľad sémantických mapovaní a ich použitie.
ms.date: 08/12/2022
ms.subservice: audience-insights
ms.reviewer: v-wendysmith
ms.topic: conceptual
author: CadeSanthaMSFT
ms.author: cadesantha
manager: shellyha
searchScope:
- ci-semantic-mapping
- customerInsights
ms.openlocfilehash: 8780c11c8b091717349f0fd75a36b99c3a63ab49
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 08/16/2022
ms.locfileid: "9303895"
---
# <a name="semantic-mappings-preview"></a>Sémantické mapovanie (Preview)

> [!NOTE]
> The **Sémantické zobrazenia** je dostupná len pre obchodné prostredia (B-to-B), kde už boli vytvorené profily kontaktov pomocou tejto stránky. Môžete pokračovať vo vytváraní a spravovaní jednotlivých profilov kontaktov pomocou **Sémantické zobrazenia** stránku. alebo [zjednotiť svoje kontaktné údaje](data-unification-contacts.md) na odstránenie duplikátov, identifikáciu zhôd medzi entitami a vytvorenie jedného jednotného profilu kontaktu. Potom môžete použiť jednotný profil kontaktu na vytváranie aktivít na úrovni kontaktu.

Sémantické mapovania vám umožňujú mapovať údaje o vašej neaktivite do vopred definovaných schém. Tieto schémy pomáhajú Customer Insights lepšie pochopiť atribúty vašich údajov. Sémantické mapovanie a poskytnuté údaje umožňujú nové poznatky a funkcie v Customer Insights. Ak chcete mapovať údaje o svojej aktivite na schémy, prečítajte si dokumentáciu k [aktivitám](activities.md).

## <a name="define-a-contactprofile-semantic-entity-mapping"></a>Definícia sémantického mapovania entity ContactProfile

1. Ísť do **Údaje** > **Sémantické zobrazenia (ukážka)**.

1. Vyberte **Pridať sémantické mapovanie** a postupujte podľa pokynov.

1. V kroku **Údaje entity** nastavte hodnoty pre nasledujúce polia:

   - **Názov mapovania sémantickej entity** : Názov vášho mapovania sémantickej entity.
   - **Zdrojová entita** : Entita, ktorá obsahuje kontaktné údaje.
   - **Primárny kľúč** : Pole, ktoré jednoznačne identifikuje záznam kontaktu. Nemalo by obsahovať duplicitné hodnoty, prázdne ani chýbajúce hodnoty.

   :::image type="content" source="media/Semantic_Mapping_Wizard1.png" alt-text="Nastavte mapovanie sémantickej entity s názvom, zdrojovou entitou a primárnym kľúčom.":::

1. Vyberte **Ďalej**.

1. V kroku **Vzťahy** nakonfigurujte podrobnosti tak, aby boli vaše kontaktné údaje prepojené s príslušnými údajmi obchodného vzťahu. Tento krok vizualizuje spojenie medzi entitami.  

   Je možné implementovať dva typy ciest vzťahov: **Priame vzťahy** a **Nepriame vzťahy**. Ak chcete získať ďalšie informácie, navštívte stránku [cesty priamych a nepriamych vzťahov](relationships.md#relationship-paths).

   1. Vyberte **Pridať vzťah** konfigurovať vzťah.
   1. Vyberte atribút zo svojej zdrojovej entity, ktorý spája vašu kontaktnú entitu s inou entitou.
   1. Vyberte entitu, ku ktorej chcete pripojiť kontaktnú entitu. Vyberte entitu z **Účtovné subjekty** alebo **Sprostredkujúca entita** oddiele. Ak vyberiete sprostredkovateľskú entitu, definujte druhý vzťah na pripojenie k vašej cieľovej entite účtu.

      :::image type="content" source="media/Semantic_Mapping_Wizard2.png" alt-text="Vyberte buď entitu obchodného vzťahu alebo sprostredkovateľskú entitu.":::

   1. Zadajte **Názov vzťahu**. Ak vzťah medzi vašimi entitami už existuje, názov vzťahu je len na čítanie. Ak žiadny vzťah neexistuje, vytvorí sa nový vzťah so zadaným menom.
   1. Vyberte **Použiť** na dokončenie konfigurácie vzťahu.

   > [!NOTE]
   > Môžete nakonfigurovať viac vzťahov medzi entitou kontaktu a inými entitami obchodných vzťahov so sprostredkovateľskými entitami.
   
     :::image type="content" source="media/Semantic_Mapping_Wizard4.png" alt-text="Vizualizácia rôznych vzťahov spája kontaktné entity s entitami obchodných vzťahov.":::

1. Vyberte **Ďalej**.

1. V kroku **Nastavenie sémantického typu** zvoľte **Sémantický typ**. V súčasnosti tam existuje jeden **Sémantický typ** s názvom *ContactProfile*.

1. Namapujte svoje ID kontaktu na *Kontaktný profil* sémantický typ **ID kontaktu**. Voliteľne namapujte ďalšie polia, ako napríklad krstné meno, priezvisko, pohlavie alebo e-mail.

   :::image type="content" source="media/Semantic_Mapping_Wizard5.png" alt-text="Mapujte svoje atribúty kontaktných údajov do poskytnutých povinných a voliteľných polí.":::

1. Vyberte **Ďalej**.

1. V **Preskúmanie** krok, skontrolujte konfiguráciu sémantického mapovania. Ak chcete vykonať zmeny, vyberte **Upraviť** pre príslušnú sekciu.

1. Vyberte **Uložiť**.

1. Ak chcete spracovať sémantické mapovanie, vyberte **Bežať**. Alebo vyberte **Zavrieť** na uloženie sémantického mapovania bez jeho spracovania. Ak ho chcete spustiť neskôr, vyberte sémantické mapovanie a vyberte **Obnoviť**.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="manage-existing-semantic-mappings"></a>Spravujte existujúce sémantické mapovania

Ísť do **Údaje** > **Sémantické mapovania (ukážka)** na zobrazenie vašich uložených sémantických mapovaní, ich zdrojovej entity, sémantického typu, typu mapovania a stavu.

:::image type="content" source="media/semantic-mapping-options.png" alt-text="Možnosti správy sémantického mapovania.":::

Ak chcete zobraziť dostupné akcie, vyberte sémantické mapovanie.
- **Upraviť** aktuálnu konfiguráciu. Stlačte možnosť **Uložiť** a **Spustiť** na spracovanie zmien.
- **Obnoviť** sémantické mapovanie tak, aby zahŕňalo najnovšie údaje. Obnovením daného sémantického mapovania sa obnovia všetky sémantické mapovania rovnakého typu.
- **Premenovať** sémantické mapovanie. Vyberte **Uložiť**.
- **Odstrániť** sémantické mapovanie. Ak chcete odstrániť viac ako jedno sémantické mapovanie naraz, vyberte sémantické mapovania a ikonu odstránenia. Vyberte možnosť **Odstrániť** a potvrďte odstránenie.

[!INCLUDE [footer-include](includes/footer-banner.md)]
