---
title: Správa prostredí
description: Zistite, ako spravovať existujúce prostredia Customer Insights ako správca.“
ms.date: 08/15/2022
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-system-about
- customerInsights
ms.openlocfilehash: 8b4a88bdb75c6e638a76c39d18647681ad4556d7
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304308"
---
# <a name="manage-environments"></a>Správa prostredí

Administrátori [vytvoriť](create-environment.md) a spravovať prostredia. Môžu zmeniť niektoré nastavenia v existujúcich prostrediach. Firma, typ, región, možnosť uloženia a Dataverse nastavenia sú opravené po vytvorení prostredia. Ak chcete zmeniť tieto nastavenia, [resetovať prostredie](#reset-an-existing-environment-preview) alebo [vytvoriť nové prostredie](create-environment.md).

## <a name="edit-an-existing-environment"></a>Úprava existujúceho prostredia

Upravte podrobnosti existujúceho prostredia, ako je názov alebo nastavenie predvoleného prostredia.

1. Vyberte nástroj na výber **Prostredia** v hlavičke aplikácie.

1. Vyberte ikonu **Upraviť**.

   :::image type="content" source="media/edit-environment.png" alt-text="Ikona na úpravu nastavení prostredia.":::

1. V **Upraviť prostredie** panel, aktualizujte nastavenia prostredia.

1. Vyberte **Skontrolujte a dokončite**, potom **Aktualizovať** aplikujte zmeny.

## <a name="change-the-owner-of-an-environment"></a>Zmeňte vlastníka prostredia

Niekoľko používateľov môže mať oprávnenia správcu, ale iba jeden používateľ je vlastníkom prostredia. V predvolenom nastavení je to správca, ktorý na začiatku vytvára prostredie. Ako správca prostredia môžete prideliť vlastníctvo inému používateľovi s oprávneniami správcu.

1. Vyberte nástroj na výber **Prostredia** v hlavičke aplikácie.

1. Vyberte ikonu **Upraviť**.

1. V **Upraviť prostredie** panel, prejdite na **Základné informácie** krok.

1. V **Zmeniť vlastníka prostredia** poľa, vybrať nového vlastníka prostredia.  

1. Vyberte **Skontrolujte a dokončite**, potom **Aktualizovať** aplikujte zmeny.

## <a name="claim-ownership-of-an-environment"></a>Nárokovať si vlastníctvo prostredia

Ak je používateľský účet vlastníka odstránený alebo pozastavený, prostredie nebude mať vlastníka. Každý administrátor si môže nárokovať vlastníctvo a stať sa novým vlastníkom. Vlastník admin môže naďalej vlastniť prostredie resp [zmeniť vlastníctvo na iného správcu](#change-the-owner-of-an-environment).

Ak si chcete nárokovať vlastníctvo, vyberte **Prevziať vlastníctvo** tlačidlo, ktoré sa zobrazuje v hornej časti každej stránky v Customer Insights, keď pôvodný vlastník opustil organizáciu.

## <a name="reset-an-existing-environment-preview"></a>Obnoviť existujúce prostredie (ukážka)

Ako vlastník prostredia resetujte prostredie do prázdneho stavu, ak chcete vymazať všetky konfigurácie a odstrániť prijaté údaje.

1. Vyberte nástroj na výber **Prostredia** v hlavičke aplikácie.

1. Vyberte prostredie, ktoré chcete resetovať, a vyberte zvislú elipsu (&vellip;).

1. Vyberte si **Resetovať (ukážka)**.

   :::image type="content" source="media/reset-environment.png" alt-text="Ovládanie na resetovanie prostredia.":::

1. Vyberte, či chcete resetovať celé prostredie, všetko okrem zdrojov údajov alebo čokoľvek, čo je nakonfigurované nad zjednoteným zákazníckym profilom.

1. Pre potvrdenie zadajte názov prostredia a vyberte **Resetovať**.

## <a name="delete-an-existing-environment"></a>Odstránenie existujúceho prostredia

Ako vlastník prostredia ho môžete odstrániť.

> [!IMPORTANT]
> Vymazaním prostredia sa neodstráni pripojenie k a Dataverse životné prostredie. Ak plánujete pripojiť to isté Dataverse prostredia do nového prostredia Customer Insights v budúcnosti, musíte [odstráňte toto spojenie s Dataverse životné prostredie](customer-insights-dataverse.md#remove-an-existing-connection-to-a-dataverse-environment).

1. Vyberte nástroj na výber **Prostredia** v hlavičke aplikácie.

1. Vyberte prostredie, ktoré chcete odstrániť, a vyberte zvislú elipsu (&vellip;). 

1. Vyberte si **Odstrániť**.

   :::image type="content" source="media/delete-environment.png" alt-text="Ovládaním vymažete prostredie.":::

1. Odstránenie potvrdíte zadaním názvu prostredia a výberom položky **Odstrániť**.

[!INCLUDE [footer-include](includes/footer-banner.md)]
