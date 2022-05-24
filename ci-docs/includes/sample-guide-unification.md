---
ms.openlocfilehash: 1d79987893986148421c316193b27d268cfe0a0b
ms.sourcegitcommit: 4ae316c856b8de0f08a4605f73e75a8c2cf51c4e
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 05/13/2022
ms.locfileid: "8755563"
---
Po prijatí údajov začnite proces zjednocovania údajov na vytvorenie jednotného profilu zákazníka. Ďalšie informácie nájdete v téme [Zjednotenie údajov](../data-unification.md).

### <a name="select-source-fields"></a>Vyberte zdrojové polia

1. Po prijatí údajov namapujte kontakty z údajov eCommerce a Loyalty na bežné typy údajov. Ísť do **Údaje** > **Zjednotiť**.

1. Vyberte entity, ktoré zastupujú profil zákazníka – **eCommerceContacts** a **loyCustomers**.

   ![Zjednotenie zdrojov údajov elektronického obchodu a vernostných údajov.](../media/unify-ecommerce-loyalty.png)

1. Vyberte **ContactId** ako primárny kľúč pre **eCommerceContacts** a **LoyaltyID** ako primárny kľúč pre **loyCustomers**.

1. Vyberte **Ďalej**. Preskočte duplicitné záznamy a vyberte **Ďalšie**.

### <a name="match-conditions"></a>Podmienky zápasu

1. Vyberte si **eCommerceContacts: eCommerce** ako primárny subjekt a zahŕňajú všetky záznamy.

1. Vyberte si **loyCustomers: LoyaltyScheme** a zahrnúť všetky záznamy.

1. Pridajte pravidlo:
   - Vyberte **Celé meno** pre eCommerceContacts a loyCustomers.
   - Vyberte **Typ (telefón, meno, adresa, ...)** pre **Normalizovať**.
   - Nastavte **Úroveň presnosti**: **Základná** a **Hodnota**: **Vysoká**.
   - Zadajte **Celé meno, e-mail** pre meno.

1. Pridajte druhú podmienku pre e-mailovú adresu:
   - Vyberte **Email** pre eCommerceContacts a loyCustomers.
   - Pole Normalizovať nechajte prázdne.
   - Nastavte **Úroveň presnosti**: **Základná** a **Hodnota**: **Vysoká**.

   ![Pravidlo zjednotenia zhody pre meno a e-mail.](../media/unify-match-rule.png)

1. Vyberte položku **Hotovo**.

1. Vyberte **Ďalej**.

### <a name="unify-fields"></a>Zjednotiť polia

1. Premenujte **ContactId** pre **loyZákazníci** subjekt do **ContactIdLOYALTY** na odlíšenie od ostatných prijatých ID.

1. Vyberte **Ďalšie** skontrolovať a potom vybrať **Vytvorte profily zákazníkov**.
