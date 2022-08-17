---
title: Nakonfigurujte nastavenia zabezpečenia
description: Prečítajte si o nastaveniach zabezpečenia v Dynamics 365 Customer Insights.
ms.date: 08/02/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: ea21163d7dd05370de28ca8340ae9583846adb26
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 08/10/2022
ms.locfileid: "9246081"
---
# <a name="configure-security-settings"></a>Nakonfigurujte nastavenia zabezpečenia

Spravujte kľúče API, pristupujte k údajom zákazníkov a nastavte súkromné prepojenie Azure.

## <a name="manage-api-keys"></a>Spravujte kľúče API

Zobrazte a spravujte kľúče na použitie [Rozhrania API Customer Insights](apis.md) s údajmi vo vašom prostredí.

1. Ísť do **Systém** > **Bezpečnosť** a vyberte **API** tab.

1. Ak nebol nastavený prístup API k prostrediu, vyberte **Povoliť**. Alebo ak chcete zablokovať prístup API k prostrediu, vyberte **Zakázať** a potvrďte.

1. Spravujte primárne a sekundárne kľúče API:

   1. Ak chcete zobraziť primárny alebo sekundárny kľúč API, vyberte **Šou** symbol.

   1. Ak chcete skopírovať primárny alebo sekundárny kľúč API, vyberte **Kopírovať** symbol.

   1. Ak chcete vytvoriť nové primárne alebo sekundárne kľúče API, vyberte **Primárne regenerovať** alebo **Regenerovať sekundárne**.

## <a name="securely-access-customer-data-with-customer-lockbox-preview"></a>Bezpečný prístup k zákazníckym údajom pomocou Customer Lockbox (ukážka)

Customer Insights používa Power Platform Možnosť zákazníckeho uzamykacieho boxu. Customer Lockbox poskytuje rozhranie na kontrolu a schválenie (alebo odmietnutie) žiadostí o prístup k údajom. Tieto požiadavky sa vyskytujú, keď je potrebný prístup k údajom o zákazníckych údajoch na vyriešenie prípadu podpory. Ak chcete použiť túto funkciu, Customer Insights musí mať existujúce pripojenie k a Microsoft Dataverse prostredia vo vašom nájomcovi.

Ďalšie informácie o Customer Lockbox nájdete na [zhrnutie](/power-platform/admin/about-lockbox#summary) z Power Platform Zákaznícka skrinka. Článok tiež popisuje [pracovný tok](/power-platform/admin/about-lockbox#workflow) a požadované [nastaviť](/power-platform/admin/about-lockbox#enable-the-lockbox-policy) aby ste povolili Customer Lockbox.

> [!IMPORTANT]
> Globálni správcovia pre Power Platform alebo Power Platform správcovia môžu schvaľovať požiadavky zákazníckej schránky vydané pre Customer Insights.

## <a name="set-up-an-azure-private-link"></a>Nastavte súkromné prepojenie Azure

[Súkromný odkaz Azure](/azure/private-link/private-link-overview) prepojme Customer Insights s vašou Azure Data Lake Storage účtu cez súkromný koncový bod vo vašej virtuálnej sieti. Pre údaje v účte úložiska, ktorý nie je vystavený verejnému internetu, umožňuje Súkromné prepojenie pripojenie k tejto obmedzenej sieti.

> [!IMPORTANT]
> Minimálna požiadavka na rolu na nastavenie pripojenia Private Link:
>
> - Customer Insights: Administrátor
> - Vstavaná rola Azure: [Prispievateľ účtu úložiska](/azure/role-based-access-control/built-in-roles#storage-account-contributor)
> - Povolenia pre vlastnú rolu Azure: [Microsoft.Storage/storageAccounts/read a Microsoft.Storage/storageAccounts/PrivateEndpointConnectionsApproval/action](/azure/role-based-access-control/resource-provider-operations#microsoftstorage)

1. V Customer Insights prejdite na **Admin** > **Bezpečnosť** a vyberte **Súkromné odkazy** tab.

1. Vyberte **Pridať súkromný odkaz**.

   The **Pridať súkromný odkaz** panel zobrazuje účty úložiska od vášho nájomníka, na zobrazenie ktorých máte povolenia.

1. Vyberte predplatné, skupinu prostriedkov a konto úložiska.

1. Skontrolujte [ochrana osobných údajov a dodržiavanie predpisov](connections.md#data-privacy-and-compliance) a vyberte **Súhlasím**.

1. Vyberte **Uložiť**.

1. Prejdite do svojho účtu Data Lake Storage a otvorte odkaz zobrazený na obrazovke.

1. Schváľte súkromný odkaz.


[!INCLUDE [footer-include](includes/footer-banner.md)]
