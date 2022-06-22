---
title: Nastavenia zabezpečenia v Customer Insights
description: Prečítajte si o nastaveniach zabezpečenia v Dynamics 365 Customer Insights.
ms.date: 06/08/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 163deb9bed4f82d742c46cace27dd128f0aca18b
ms.sourcegitcommit: 8e9f0a9693fd8d91ad0227735ff03688fef5406f
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 06/10/2022
ms.locfileid: "8947434"
---
# <a name="security-settings-in-customer-insights"></a>Nastavenia zabezpečenia v Customer Insights

The **Bezpečnosť** stránka obsahuje zoznam možností na konfiguráciu používateľských povolení a funkcií, ktoré pomáhajú pri vytváraní Dynamics 365 Customer Insights bezpečnejšie. Na túto stránku majú prístup iba správcovia.

Ísť do **Admin** > **Bezpečnosť** na konfiguráciu nastavení.

The **Bezpečnosť** stránka obsahuje nasledujúce karty:

- [Používatelia](#users-tab)
- [Rozhrania API](#apis-tab)
- [Súkromné prepojenia](#private-links-tab)
- [Key Vault](#key-vault-tab)
- [Bezpečný prístup k zákazníckym údajom pomocou Customer Lockbox (ukážka)](#securely-access-customer-data-with-customer-lockbox-preview)

## <a name="users-tab"></a>Karta Používatelia

Prístup k Customer Insights je obmedzený na používateľov vo vašej organizácii, ktorých do aplikácie pridal správca. The **Používatelia** vám umožňuje spravovať prístup používateľov a ich povolenia. Ďalšie informácie nájdete v časti [Používateľské oprávnenia](permissions.md).

## <a name="apis-tab"></a>Karta API

Zobrazte a spravujte kľúče na použitie [Rozhrania API Customer Insights](apis.md) s údajmi vášho prostredia.

Výberom môžete vytvoriť nový primárny a sekundárny kľúč **Primárne regenerovať** alebo **Regenerovať sekundárne**. 

Ak chcete zablokovať prístup API k prostrediu, vyberte **Zakázať**. Ak sú rozhrania API zakázané, môžete si vybrať **Povoliť** znovu udeliť prístup.

## <a name="private-links-tab"></a>Karta Súkromné odkazy

[Súkromné prepojenie Azure](/azure/private-link/private-link-overview) prepojme Customer Insights s vaším Azure Data Lake Storage účtu cez súkromný koncový bod vo vašej virtuálnej sieti. Pre údaje v účte úložiska, ktorý nie je vystavený verejnému internetu, umožňuje Súkromné prepojenie pripojenie k tejto obmedzenej sieti.

> [!IMPORTANT]
> Minimálna požiadavka na rolu na nastavenie pripojenia Private Link:
>
> - Customer Insights: Administrátor
> - Vstavaná rola Azure: [Prispievateľ účtu úložiska](/azure/role-based-access-control/built-in-roles#storage-account-contributor)
> - Povolenia pre vlastnú rolu Azure: [Microsoft.Storage/storageAccounts/read a Microsoft.Storage/storageAccounts/PrivateEndpointConnectionsApproval/action](/azure/role-based-access-control/resource-provider-operations#microsoftstorage)
>

Nastavenie Private Link v Customer Insights je dvojkrokový proces. Najprv spustíte vytvorenie súkromného odkazu z **Admin** > **Bezpečnosť** > **Súkromné odkazy** v Customer Insights. The **Pridať súkromný odkaz** panel zobrazuje účty úložiska od vášho nájomníka, na zobrazenie ktorých máte povolenia. Vyberte účet úložiska a poskytnite súhlas na vytvorenie súkromného prepojenia.

Ďalej musíte schváliť súkromné prepojenie na strane účtu Data Lake Storage. Otvorte odkaz zobrazený na obrazovke, aby ste schválili nový súkromný odkaz.

## <a name="key-vault-tab"></a>Záložka Key Vault

The **Trezor na kľúče** karta vám umožňuje prepojiť a spravovať svoje vlastné [Azúrový trezor kľúčov](/azure/key-vault/general/basic-concepts) k životnému prostrediu.
Vyhradený trezor kľúčov je možné použiť na fázovanie a používanie tajomstiev v hraniciach dodržiavania predpisov organizácie. Customer Insights môže použiť tajomstvá v Azure Key Vault na [nastaviť pripojenia](connections.md) na systémy tretích strán.

Viac informácií nájdete v časti [Prineste si vlastný trezor kľúčov Azure](use-azure-key-vault.md).

## <a name="securely-access-customer-data-with-customer-lockbox-preview"></a>Bezpečný prístup k zákazníckym údajom pomocou Customer Lockbox (ukážka)

Customer Insights používa Power Platform Možnosť zákazníckeho uzamykacieho boxu. Customer Lockbox poskytuje rozhranie na kontrolu a schválenie (alebo odmietnutie) žiadostí o prístup k údajom. Tieto požiadavky sa vyskytujú, keď je potrebný prístup k údajom o zákazníckych údajoch na vyriešenie prípadu podpory. Ak chcete použiť túto funkciu, Customer Insights musí mať existujúce pripojenie k a Microsoft Dataverse prostredia vo vašom nájomcovi.

Ďalšie informácie o Customer Lockbox nájdete na [zhrnutie](/power-platform/admin/about-lockbox#summary) z Power Platform Zákaznícka skrinka. Článok tiež popisuje [pracovný tok](/power-platform/admin/about-lockbox#workflow) a požadované [nastaviť](/power-platform/admin/about-lockbox#enable-the-lockbox-policy) aby ste povolili Customer Lockbox.

> [!IMPORTANT]
> Globálni správcovia pre Power Platform alebo Power Platform správcovia môžu schvaľovať požiadavky zákazníckej schránky vydané pre Customer Insights.

[!INCLUDE [footer-include](includes/footer-banner.md)]
