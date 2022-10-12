---
ms.openlocfilehash: a67714de5aae80a0080c0e631ae6f8986eb2a003
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 09/30/2022
ms.locfileid: "9611136"
---
- **Výkon tréningového modelu** : Stupne A, B alebo C označujú výkon predikcia a môžu vám pomôcť pri rozhodovaní o použití výsledkov uložených vo výstupnej entite.

  Klasifikácie sa určujú na základe nasledujúcich pravidiel:
  - **A** keď model presne predikoval najmenej 50 % celkových predikcií a keď percento presných predikcií pre zákazníkov, ktorí odišli, je väčšie ako základná miera najmenej o 10 %.
  - **B** keď model presne predikoval najmenej 50 % celkových predikcií a keď percento presných predikcií pre zákazníkov, ktorí odišli, je väčšie ako základná miera o hodnotu do 10 %.
  - **C** keď model presne predpovedal menej ako 50 % z celkových predpovedí, alebo keď je percento presných predpovedí pre zákazníkov, ktorí chŕli, menšie ako základná hodnota.
  - **Základná línia** berie predikcia vstup časového okna pre model (napríklad jeden rok) a vytvára rôzne časti času delením dvomi, kým nedosiahne jeden mesiac alebo menej. Pomocou týchto zlomkov vytvára obchodné pravidlo pre zákazníkov, ktorí si v tomto časovom rámci nenakúpili. Títo zákazníci sa považujú za odídených. Ako základný model sa zvolilo obchodné pravidlo založené na čase s najvyššou schopnosťou predpovedať, kto bude pravdepodobne plytvať.

- **Pravdepodobnosť odchodu (počet zákazníkov)**: Skupiny zákazníkov na základe ich predpokladaného rizika odchodu. voliteľne [vytvárať segmenty zákazníkov](../prediction-based-segment.md) s vysokým rizikom odchodu. Takéto segmenty pomáhajú pochopiť, kde by malo byť vaše obmedzenie pre členstvo v segmente.

- **Najvýznamnejšie faktory**: Pri vytváraní vašej predikcie sa zohľadňuje veľa faktorov. Každý z faktorov má svoju dôležitosť vypočítanú pre agregované predpovede, ktoré model vytvára. Použite tieto faktory na overenie vašich výsledkov predikcia. Alebo použite tieto informácie neskôr [vytvárať segmenty](../prediction-based-segment.md) ktoré by mohli pomôcť ovplyvniť riziko odchodu zákazníkov.