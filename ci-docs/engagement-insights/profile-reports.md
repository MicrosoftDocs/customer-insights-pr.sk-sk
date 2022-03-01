---
title: Aktivácia pripravených profilových zostáv
description: Ako vytvárať predvolené profilové zostavy zoskupené podľa pohlavia, veku a kraja alebo regiónu pôvodu.
author: darrinw-docs
ms.reviewer: mhart
ms.author: darrinw
ms.date: 05/03/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 3aa9599fc780098a2f7f31f0210d76ed2ef27ece774dd6212b5cb2a599ad537e
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 08/10/2021
ms.locfileid: "7033971"
---
# <a name="out-of-box-profile-reports"></a>Pripravené profilové zostavy

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Správa je súborom vizualizácie údajov, ktoré vám pomôžu pochopiť, ako sa správajú používatelia. Po pripojení k Customer Insights audience insights môžu prehľady interakcií zobraziť prehľad s informáciami o zjednotených profiloch zákazníkov. Tento prehľad obsahuje počet profilov, ktoré máte, zoskupené podľa pohlavia, veku a geografického umiestnenia.

## <a name="prerequisites"></a>Predpoklady

Prostredie prehľadu cieľových skupín musí uchovávať údaje spravované zákazníkom v účte Azure Data Lake Storage.

Ak používate skúšobnú verziu funkcie prehľadov o cieľovej skupine alebo prostredia v spravovanom Data LakeCustomer Insights, [kontaktujte nás](https://go.microsoft.com/fwlink/?linkid=2145734) so žiadosťou o asistenciu.  


## <a name="enable-the-customer-profile-report"></a>Povoliť prehľad profilu zákazníka

Správca prostredia musí [vytvoriť spojenie s prehľadmi o cieľovej skupine](configure-connections.md).

Po zadaní podrobností o pripojení môže správca udeliť prístup ďalším ľuďom v organizácii, aby si mohli prehľad pozrieť. Správca prostredia, ktorý nastavuje pripojenie, má automaticky prístup k zostave. 

Po dokončení pripojenia funkcia **Profily** bude k dispozícii na ľavej navigačnej table. 

- Prejdite do ponuky **Objavovať** > **Profily** a pozrite si zostavu.

Zostava **Profily** obsahuje vizualizácie o pohlaví, veku a geografickom umiestnení prepojených profilov zákazníkov.

:::image type="content" source="media/customer-profiles.png" alt-text="Zostava profilu zákazníka.":::

[!INCLUDE[footer-include](../includes/footer-banner.md)]