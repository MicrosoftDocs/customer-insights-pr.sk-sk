---
title: Prineste si vlastný trezor kľúčov Azure na správu tajomstiev
description: Zistite, ako nakonfigurovať Customer Insights na používanie vlastného trezora kľúčov Azure.
ms.date: 10/06/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: brndkfr
ms.author: bkief
manager: shellyha
searchScope:
- ci-system-security
- customerInsights
ms.openlocfilehash: 418575f724090628da8bd01e2569a4cb9e646337
ms.sourcegitcommit: 50d32a4cab01421a5c3689af789e20857ab009c4
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 03/03/2022
ms.locfileid: "8376527"
---
# <a name="bring-your-own-azure-key-vault-preview"></a>Prineste si vlastný trezor kľúčov Azure (verzia Preview)

Prepojenie vyhradeného [trezora kľúčov Azure](/azure/key-vault/general/basic-concepts) s prostredím s prehľadmi cieľovej skupiny pomáha organizáciám splniť požiadavky súladu.
Vyhradený trezor kľúčov je možné použiť na fázovanie a používanie tajomstiev v hraniciach dodržiavania predpisov organizácie. Prehľady publika môžu použiť tajomstvá v Azure Key Vault na [konfiguráciu pripojení](connections.md) do systémov tretích strán.

## <a name="link-the-key-vault-to-the-audience-insights-environment"></a>Prepojte trezor kľúčov s prostredím prehľadov cieľovej skupiny

### <a name="prerequisites"></a>Predpoklady

Ak chcete nakonfigurovať trezor kľúčov v prehľadoch cieľovej skupiny, musia byť splnené nasledujúce predpoklady:

- Musíte mať aktívne predplatné Azure.

- Máte rolu [Správca](permissions.md#admin) v prehľadoch cieľovej skupiny. Prečítajte si viac o [povoleniach používateľov v prehľadoch cieľovej skupiny](permissions.md#assign-roles-and-permissions).

- Máte roly [Prispievateľ](/azure/role-based-access-control/built-in-roles#contributor) a [Správca prístupu používateľov](/azure/role-based-access-control/built-in-roles#user-access-administrator) v trezore kľúčov alebo v skupine zdrojov, do ktorej trezor kľúčov patrí. Ak chcete získať ďalšie informácie, navštívte stránku [Pridajte alebo odstráňte priradenia rolí Azure pomocou portálu Azure](/azure/role-based-access-control/role-assignments-portal). Ak v trezore kľúčov nemáte rolu Správca prístupu používateľov, musíte nastaviť oprávnenia riadenia prístupu na základe rolí pre objekt služby Azure pre Dynamics 365 Customer Insights oddelene. Postupujte podľa pokynov [na použitie objektu služby Azure](connect-service-principal.md) pre trezor kľúčov, ktorý by mal byť prepojený.

- Trezor kľúčov musí mať bránu firewall Key Vault **zakázanú**.

- Trezor kľúčov je v rovnakej [lokalite Azure](https://azure.microsoft.com/global-infrastructure/geographies/#overview) ako prostredie prehľadov cieľových skupín. Región prostredia v prehľadoch cieľových skupín je uvedený v časti **Správca** > **Systém** > **O** > **Región**.

### <a name="link-a-key-vault-to-the-environment"></a>Prepojenie trezora kľúčov s prostredím

1. Prejdite na **Správca** > **Systém** a potom vyberte kartu **Zabezpečenie**.
1. Na dlaždici **Trezor kľúčov** vyberte **Nastaviť**.
1. Vyberte **Predplatné**.
1. Vyberte trezor kľúčov z rozbaľovacie zoznamu **Key Vault**. Ak sa zobrazuje príliš veľa trezorov kľúčov, obmedzte výsledky vyhľadávania výberom skupiny zdrojov.
1. Prijmite vyhlásenie **Ochrana osobných údajov a súlad**.
1. Vyberte položku **Uložiť**.

:::image type="content" source="media/set-up-azure-key-vault.png" alt-text="Kroky na nastavenie prepojeného trezora kľúčov v prehľadoch publika.":::

Na dlaždici **Key Vault** sa teraz zobrazuje názov prepojeného trezora kľúčov, skupina zdrojov a predplatné. Je pripravený na použitie v nastavení pripojenia.
Podrobnosti o tom, ktoré povolenia v trezore kľúčov sú udeľované prehľadom cieľovej skupiny, nájdete na v časti [Povolenia udelené v trezore kľúčov pre prehľady cieľových skupín](#permissions-granted-on-the-key-vault-to-audience-insights), neskôr v tomto článku.

## <a name="use-the-key-vault-in-the-connection-setup"></a>Použitie trezora kľúčov v nastavení pripojenia

Pri [nastavovaní pripojení](connections.md) pre systémy tretích strán je možné na konfiguráciu pripojení použiť tajomstvá prepojeného trezora kľúčov.

1. Prejdite do časti **Správca** > **Pripojenia**.
1. Vyberte **Pridať pripojenie**.
1. Pokiaľ ide o podporované typy pripojení, prepínač **Použiť Key Vault** je k dispozícii, ak ste prepojili trezor kľúčov.
1. Namiesto manuálneho zadávania tajomstva môžete zvoliť názov tajomstva, ktorý ukazuje na hodnotu tajomstva v trezore kľúčov.

:::image type="content" source="media/use-key-vault-secret.png" alt-text="Tabla pripojenia s pripojením SFTP, ktoré používa tajomstvo Key Vault.":::

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

## <a name="permissions-granted-on-the-key-vault-to-audience-insights"></a>Povolenia udelené v trezore kľúčov pre prehľady cieľových skupín

Nasledujúce povolenia sú udelené prehľadom cieľových skupín v prepojenom trezore kľúčov, ak sú povolené [Zásady prístupu ku Key Vault](/azure/key-vault/general/assign-access-policy?tabs=azure-portal) alebo [Riadenie prístupu na základe rolí Azure](/azure/key-vault/general/rbac-guide?tabs=azure-cli).

### <a name="key-vault-access-policy"></a>Zásady prístupu ku Key Vault

| Zadať        | Povolenia          |
| ----------- | -------------------- |
| Kláves         | [Získajte kľúče](/rest/api/keyvault/get-keys), [Získajte kľúč](/rest/api/keyvault/get-key)                                 |
| Tajný kód      | [Získajte tajomstvá](/rest/api/keyvault/get-secrets), [Získajte tajomstvo](/rest/api/keyvault/get-secret)                     |
| Certifikát | [Získajte certifikáty](/rest/api/keyvault/get-certificates), [Získajte certifikát](/rest/api/keyvault/get-certificate) |

Predchádzajúce hodnoty sú minimum na zobrazenie a čítanie počas vykonávania.

### <a name="azure-role-based-access-control"></a>Riadenie prístupu na základe rolí Azure

Na základe prehľadov cieľových skupín budú pridané roly Key Vault Reader a Key Vault Secrets User. Podrobnosti o týchto rolách nájdete v článku [Vstavané roly Azure pre operácie s dátovými rovinami Key Vault](/azure/key-vault/general/rbac-guide?tabs=azure-cli).

## <a name="recommendations"></a>Odporúčania

- Použite samostatný alebo vyhradený trezor kľúčov, ktorý obsahuje iba tajomstvá požadované pre prehľady cieľových skupín. Prečítajte si viac o tom, prečo [sú odporúčané samostatné trezory kľúčov](/azure/key-vault/general/best-practices#why-we-recommend-separate-key-vaults).

- Postupujte podľa [osvedčených postupov, ako používať Key Vault](/azure/key-vault/general/best-practices#turn-on-logging) pre možnosti riadenia prístupu, zálohovania, auditu a obnovy.

## <a name="frequently-asked-questions"></a>Najčastejšie otázky

### <a name="can-audience-insights-write-secrets-or-overwrite-secrets-into-the-key-vault"></a>Môžu prehľady cieľových skupín zapísať tajomstvá alebo ich prepísať do trezora kľúčov?

Nie. Iba povolenia na čítanie a zobrazenie uvedené v sekcii [udelené povolenia](#permissions-granted-on-the-key-vault-to-audience-insights) skôr v tomto článku sú poskytnuté prehľadom cieľových skupín. Systém nemôže pridávať, odstraňovať ani prepisovať tajomstvá v trezore kľúčov. To je tiež dôvod, prečo nemôžete zadať poverenia, keď pripojenie používa Key Vault.

### <a name="can-i-change-a-connection-from-using-key-vault-secrets-to-default-authentication"></a>Môžem zmeniť pripojenie z použitia tajomstiev Key Vault na predvolené overenie?

Nie. Po nakonfigurovaní pomocou tajomstva z prepojeného trezora kľúčov sa nemôžete vrátiť späť na predvolené pripojenie. Vytvorte samostatné pripojenie a pôvodné odstráňte, ak ho už nepotrebujete.

### <a name="how-can-i-revoke-access-to-a-key-vault-for-audience-insights"></a>Ako môžem odvolať prístup k trezoru kľúčov pre prehľady o cieľových skupinách?

V závislosti od toho, či sú povolené [Zásady prístupu ku Key Vault](/azure/key-vault/general/assign-access-policy?tabs=azure-portal) alebo[Riadenie prístupu na základe rolí Azure](/azure/key-vault/general/rbac-guide?tabs=azure-cli), musíte odobrať povolenia pre správcu služby `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` s názvom `Dynamics 365 AI for Customer Insights`. Všetky pripojenia, ktoré používajú trezor kľúčov, prestanú fungovať.

### <a name="a-secret-thats-used-in-a-connection-got-removed-from-the-key-vault-what-can-i-do"></a>Tajomstvo, ktoré sa používa v spojení, bolo odstránené z trezora kľúčov. Čo mám robiť?

V prehľadoch cieľových skupín sa zobrazí upozornenie, keď konfigurované tajomstvo z trezora kľúčov už nie je prístupné. Povoľte [mäkké odstránenie](/azure/key-vault/general/soft-delete-overview) v trezore kľúčov na obnovenie tajomstiev, ak boli omylom odstránené.

### <a name="a-connection-doesnt-work-but-my-secret-is-in-the-key-vault-what-might-be-the-cause"></a>Pripojenie nefunguje, ale moje tajomstvo je v trezore kľúčov. Čo môže byť príčinou?

V prehľadoch cieľových skupín sa zobrazí oznámenie, keď nemôže získať prístup k trezoru kľúčov. Príčinou môže byť:

- Povolenia pre objekt služby prehľadov cieľových skupín boli odstránené. Je potrebné ich obnoviť ručne.

- Brána firewall v trezore kľúčov je povolená. Ak chcete znova sprístupniť trezor kľúčov pre prehľady cieľových skupín, je potrebné vypnúť bránu firewall.
