---
title: Prineste si vlastný trezor kľúčov Azure (verzia Preview)
description: Zistite, ako nakonfigurovať Customer Insights na používanie vlastného trezoru kľúčov Azure na správu tajných informácií.
ms.date: 08/02/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: brndkfr
ms.author: bkief
manager: shellyha
searchScope:
- ci-system-security
- customerInsights
ms.openlocfilehash: 229fb5698a02d1d73c30442f61c7b1b5fce918bf
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 08/10/2022
ms.locfileid: "9246174"
---
# <a name="bring-your-own-azure-key-vault-preview"></a>Prineste si vlastný trezor kľúčov Azure (verzia Preview)

Prepojenie špecializovaného [Azúrový trezor kľúčov](/azure/key-vault/general/basic-concepts) do prostredia Customer Insights pomáha organizáciám splniť požiadavky na dodržiavanie predpisov.

## <a name="link-the-key-vault-to-the-customer-insights-environment"></a>Prepojte trezor kľúčov s prostredím Customer Insights

Nastavte vyhradený trezor kľúčov na vytváranie a používanie tajných kľúčov v hraniciach dodržiavania pravidiel organizácie.

### <a name="prerequisites"></a>Požiadavky

- Aktívne predplatné služieb Azure.

- An [správca](permissions.md#admin) úlohu [pridelených](permissions.md#add-users) v Customer Insights.

- [Prispievateľ](/azure/role-based-access-control/built-in-roles#contributor) a [Administrátor prístupu používateľov](/azure/role-based-access-control/built-in-roles#user-access-administrator) roly v trezore kľúčov alebo skupine prostriedkov, do ktorej trezor kľúčov patrí. Ak chcete získať ďalšie informácie, navštívte stránku [Pridajte alebo odstráňte priradenia rolí Azure pomocou portálu Azure](/azure/role-based-access-control/role-assignments-portal). Ak nemáte rolu správcu prístupu používateľov v trezore kľúčov, nastavte povolenia riadenia prístupu na základe rolí pre principál služby Azure pre Dynamics 365 Customer Insights oddelene. Postupujte podľa pokynov [na použitie objektu služby Azure](connect-service-principal.md) pre trezor kľúčov, ktorý by mal byť prepojený.

- Key Vault musí mať bránu firewall Key Vault **zdravotne postihnutých**.

- Trezor kľúčov je v tom istom [Azúrová poloha](https://azure.microsoft.com/global-infrastructure/geographies/#overview) ako prostredie Customer Insights. V Customer Insights prejdite na **Admin** > **Systém** a **O** kartu na zobrazenie oblasti prostredia.

### <a name="recommendations"></a>Odporúčania

- [Použite samostatný alebo vyhradený trezor kľúčov](/azure/key-vault/general/best-practices#why-we-recommend-separate-key-vaults) ktorý obsahuje iba tajomstvá požadované pre Customer Insights.

- Postupujte podľa [osvedčených postupov, ako používať Key Vault](/azure/key-vault/general/best-practices#turn-on-logging) pre možnosti riadenia prístupu, zálohovania, auditu a obnovy.

### <a name="link-a-key-vault-to-the-environment"></a>Prepojenie trezora kľúčov s prostredím

1. Ísť do **Admin** > **Bezpečnosť** a potom vyberte položku **Trezor na kľúče** tab.
1. Na dlaždici **Trezor kľúčov** vyberte **Nastaviť**.
1. Vyberte **Predplatné**.
1. Vyberte trezor kľúčov z rozbaľovacie zoznamu **Key Vault**. Ak je k dispozícii príliš veľa trezorov kľúčov, výberom skupiny prostriedkov obmedzte výsledky vyhľadávania.
1. Prečítajte si časť [Ochrana osobných údajov a ich dodržiavanie](connections.md#data-privacy-and-compliance) a stlačte možnosť **Súhlasím**.
1. Vyberte **Uložiť**.

The **Trezor na kľúče** dlaždica zobrazuje prepojený názov trezoru kľúčov, predplatné a skupinu prostriedkov. Je pripravený na použitie v nastavení pripojenia.
Podrobnosti o tom, ktoré povolenia v trezore kľúčov sú udelené pre Customer Insights, nájdete na [Povolenia udelené v trezore kľúčov](#permissions-granted-on-the-key-vault).

## <a name="use-the-key-vault-in-the-connection-setup"></a>Použitie trezora kľúčov v nastavení pripojenia

Kedy [nastavenie pripojení](connections.md) do [podporovaná tretia strana](#supported-connection-types) systémy, použite na konfiguráciu pripojení tajomstvá z prepojeného Key Vault.

1. Prejdite do časti **Správca** > **Pripojenia**.
1. Vyberte **Pridať pripojenie**.
1. Pokiaľ ide o podporované typy pripojení, prepínač **Použiť Key Vault** je k dispozícii, ak ste prepojili trezor kľúčov.
1. Namiesto manuálneho zadávania tajného kľúča vyberte tajný názov, ktorý ukazuje na tajnú hodnotu v trezore kľúčov.

   :::image type="content" source="media/use-key-vault-secret.png" alt-text="Tabla pripojenia s pripojením SFTP, ktoré používa tajomstvo Key Vault.":::

1. Vyberte **Uložiť** na vytvorenie spojenia.

## <a name="supported-connection-types"></a>Podporované typy pripojení

Sú podporované nasledujúce pripojenia [exportu](export-destinations.md):

* [ActiveCampaign](export-active-campaign.md)
* [Autopilot](export-autopilot.md)
* [DotDigital](export-dotdigital.md)
* [Reklamy Google](export-google-ads.md)
* [Klaviyo](export-klaviyo.md)
* [LiveRamp](export-liveramp.md)
* [Marketo](export-marketo.md)
* [Omnisend](export-omnisend.md)
* [Salesforce Marketing Cloud](export-salesforce.md)
* [Sendgrid](export-sendgrid.md)
* [Sendinblue](export-sendinblue.md)
* [SFTP](export-sftp.md)

## <a name="permissions-granted-on-the-key-vault"></a>Povolenia udelené v trezore kľúčov

Nasledujúce povolenia sú udelené pre Customer Insights v prepojenom trezore kľúčov, ak sú k dispozícii [Zásady prístupu k trezoru kľúčov](/azure/key-vault/general/assign-access-policy?tabs=azure-portal) alebo [Riadenie prístupu na základe rolí v Azure](/azure/key-vault/general/rbac-guide?tabs=azure-cli) je umožnené.

### <a name="key-vault-access-policy"></a>Zásady prístupu ku Key Vault

| Zadať        | Povolenia          |
| ----------- | -------------------- |
| Kláves         | [Získajte kľúče](/rest/api/keyvault/keys/get-keys/get-keys), [Získajte kľúč](/rest/api/keyvault/keys/get-key/get-key)                                 |
| Tajný kód      | [Získajte tajomstvá](/rest/api/keyvault/secrets/get-secrets/get-secrets), [Získajte tajomstvo](/rest/api/keyvault/secrets/get-secret/get-secret)                     |
| Certifikát | [Získajte certifikáty](/rest/api/keyvault/certificates/get-certificates/get-certificates), [Získajte certifikát](/rest/api/keyvault/certificates/get-certificate/get-certificate) |

Predchádzajúce hodnoty sú minimum na zobrazenie a čítanie počas vykonávania.

### <a name="azure-role-based-access-control"></a>Riadenie prístupu na základe rolí Azure

The [Používateľské roly aplikácie Key Vault Reader a Key Vault Secrets](/azure/key-vault/general/rbac-guide?tabs=azure-cli) budú pridané pre Customer Insights.

## <a name="frequently-asked-questions"></a>Najčastejšie otázky

### <a name="can-customer-insights-write-secrets-or-overwrite-secrets-into-the-key-vault"></a>Môže Customer Insights zapisovať tajné informácie alebo prepisovať tajné informácie do trezoru kľúčov?

Nie. Iba povolenia na čítanie a zoznamy uvedené v [udelené povolenia](#permissions-granted-on-the-key-vault) sú poskytnuté Customer Insights. Systém nemôže pridávať, odstraňovať ani prepisovať tajomstvá v trezore kľúčov. To je tiež dôvod, prečo nemôžete zadať poverenia, keď pripojenie používa Key Vault.

### <a name="can-i-change-a-connection-from-using-key-vault-secrets-to-default-authentication"></a>Môžem zmeniť pripojenie z použitia tajomstiev Key Vault na predvolené overenie?

Nie. Po nakonfigurovaní pomocou tajomstva z prepojeného trezora kľúčov sa nemôžete vrátiť späť na predvolené pripojenie. Vytvorte samostatné pripojenie a pôvodné odstráňte, ak ho už nepotrebujete.

### <a name="how-can-i-revoke-access-to-a-key-vault-for-customer-insights"></a>Ako môžem zrušiť prístup k trezoru kľúčov pre Customer Insights?

Ak [Zásady prístupu k trezoru kľúčov](/azure/key-vault/general/assign-access-policy?tabs=azure-portal) alebo [Riadenie prístupu na základe rolí v Azure](/azure/key-vault/general/rbac-guide?tabs=azure-cli) je povolené, odstráňte povolenia pre principál služby`0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` s menom `Dynamics 365 AI for Customer Insights`. Všetky pripojenia, ktoré používajú trezor kľúčov, prestanú fungovať.

### <a name="a-secret-thats-used-in-a-connection-got-removed-from-the-key-vault-what-can-i-do"></a>Tajomstvo, ktoré sa používa v spojení, bolo odstránené z trezora kľúčov. Čo mám robiť?

Keď už nie je prístupný nakonfigurovaný tajný kľúč z trezoru kľúčov, v Customer Insights sa zobrazí upozornenie. Povoľte [mäkké odstránenie](/azure/key-vault/general/soft-delete-overview) v trezore kľúčov na obnovenie tajomstiev, ak boli omylom odstránené.

### <a name="a-connection-doesnt-work-but-my-secret-is-in-the-key-vault-what-might-be-the-cause"></a>Pripojenie nefunguje, ale moje tajomstvo je v trezore kľúčov. Čo môže byť príčinou?

Keď nemá prístup k trezoru kľúčov, v Customer Insights sa zobrazí upozornenie. Príčinou môže byť:

- Povolenia pre principál služby Customer Insights boli odstránené. Je potrebné ich obnoviť ručne.

- Brána firewall v trezore kľúčov je povolená. Aby bol trezor kľúčov opäť prístupný pre Customer Insights, musí byť firewall vypnutý.
