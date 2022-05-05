---
title: Nastavenia zabezpečenia v Dynamics 365 Customer Insights
description: Prečítajte si o nastaveniach zabezpečenia v Dynamics 365 Customer Insights.
ms.date: 04/28/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 5d73bacccadc9193d76d8dfafd0365dabc911e00
ms.sourcegitcommit: cf74b8c20d88eb96e1ac86e18cd44fe27aad5ab9
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 04/28/2022
ms.locfileid: "8653810"
---
# <a name="security-overview-page"></a>Stránka s prehľadom zabezpečenia

The **Bezpečnosť** stránka obsahuje zoznam možností na konfiguráciu používateľských povolení a funkcií, ktoré pomáhajú pri vytváraní Dynamics 365 Customer Insights bezpečnejšie. Na túto stránku majú prístup iba správcovia. 

Ísť do **Admin** > **Bezpečnosť** na konfiguráciu nastavení.

The **Bezpečnosť** stránka obsahuje nasledujúce karty:
- [Používatelia](#users-tab)
- [Rozhrania API](#apis-tab)
- [Key Vault](#key-vault-tab)

## <a name="users-tab"></a>Karta Používatelia

Prístup k Customer Insights je obmedzený na používateľov vo vašej organizácii, ktorých do aplikácie pridal správca. The **Používatelia** vám umožňuje spravovať prístup používateľov a ich povolenia. Ďalšie informácie nájdete v časti [Používateľské oprávnenia](permissions.md).

## <a name="apis-tab"></a>Karta API

Zobrazte a spravujte kľúče na použitie [Rozhrania API Customer Insights](apis.md) s údajmi vášho prostredia.

Výberom môžete vytvoriť nový primárny a sekundárny kľúč **Primárne regenerovať** alebo **Regenerovať sekundárne**. 

Ak chcete zablokovať prístup API k prostrediu, vyberte **Zakázať**. Ak sú rozhrania API zakázané, môžete si vybrať **Povoliť** znovu udeliť prístup.

## <a name="key-vault-tab"></a>Záložka Key Vault

The **Trezor na kľúče** karta vám umožňuje prepojiť a spravovať svoje vlastné [Azúrový trezor kľúčov](/azure/key-vault/general/basic-concepts) k životnému prostrediu.
Vyhradený trezor kľúčov je možné použiť na fázovanie a používanie tajomstiev v hraniciach dodržiavania predpisov organizácie. Customer Insights môže použiť tajomstvá v Azure Key Vault na [nastaviť pripojenia](connections.md) na systémy tretích strán.

Viac informácií nájdete v časti [Prineste si vlastný trezor kľúčov Azure](use-azure-key-vault.md).


[!INCLUDE [footer-include](includes/footer-banner.md)]
