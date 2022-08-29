---
title: Použite svoj vlastný Azure Data Lake Storage Účet Gen2
author: mukeshpo
description: Prečítajte si o požiadavkách na používanie vlastných Azure Data Lake Storage účet na ukladanie údajov Customer Insights.
ms.author: mukeshpo
ms.date: 08/15/2022
ms.topic: conceptual
ms.manager: shellyha
ms.custom: intro-internal
ms.reviewer: mhart
ms.openlocfilehash: 5e4b9348f06d4e5e10b4499ad86b38c9d52da1f5
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304400"
---
# <a name="use-your-own-azure-data-lake-storage-gen2-account"></a>Použite svoj vlastný Azure Data Lake Storage Účet Gen2

Dynamics 365 Customer Insights vám dáva možnosť uložiť všetky svoje údaje [Azure Data Lake Storage Gen2](/azure/storage/blobs/data-lake-storage-introduction). Uložením údajov do Data Lake Storage súhlasíte s tým, že údaje budú prenesené a uložené v príslušnom geografickom umiestnení pre daný účet Azure Storage. Viac informácií nájdete v časti [Centrum dôveryhodnosti spoločnosti Microsoft](https://www.microsoft.com/trust-center).

Správcovia v Customer Insights môžu [vytvárať prostredia](create-environment.md) a [zadajte možnosť ukladania údajov](create-environment.md#step-2-configure-data-storage) v procese.

## <a name="prerequisites"></a>Požiadavky

- Azure Data Lake Storage účty musia byť v rovnakej oblasti Azure, ktorú ste vybrali pri vytváraní prostredia Customer Insights. Ak chcete poznať oblasť životného prostredia, prejdite na **Admin** > **Systém** > **O** v Customer Insights.
- Účet Data Lake Storage musí byť Gen2. Účty úložiska Azure Data Lake Gen1 nie sú podporované.
- Účet Data Lake Storage musí mať [hierarchický menný priestor povolený](/azure/storage/blobs/data-lake-storage-namespace).
- Kontajner s názvom`customerinsights` musí existovať na účte úložiska. Vytvorte si ho skôr, ako použijete svoj vlastný Data Lake Storage v Customer Insights.
- Správca, ktorý nastavuje prostredie Customer Insights, potrebuje rolu prispievateľa údajov objektu Storage Blob alebo vlastníka údajov objektu úložiska v účte úložiska alebo`customerinsights` kontajner. Ďalšie informácie o prideľovaní povolení v účte úložiska nájdete v časti [Vytvorte si účet úložiska](/azure/storage/common/storage-account-create?toc=%2Fazure%2Fstorage%2Fblobs%2Ftoc.json&tabs=azure-portal).

## <a name="connect-customer-insights-with-your-storage-account"></a>Prepojte Customer Insights s vaším účtom úložiska

Keď vytvoríte nové prostredie, skontrolujte, či existuje účet Data Lake Storage a či sú splnené všetky predpoklady.

1. V **Úložisko dát** krok pri vytváraní prostredia, nastav **Uložte výstupné dáta** do **Azure Data Lake Storage Gen2**.
1. Vyberte si, ako na to **Pripojte úložisko**. Na autentifikáciu si môžete vybrať medzi možnosťou založenou na zdrojoch a možnosťou založenou na predplatnom. Viac informácií nájdete v časti [Pripojte sa k Azure Data Lake Storage účtu pomocou Azure Service Principal](connect-service-principal.md).
   - Pre **Predplatné Azure**, vyber **Predplatné**, **zdrojov**, a **Účet úložiska** ktorý obsahuje`customerinsights` kontajner.
   - Pre **Kľúč účtu**, poskytnúť **Názov účtu** a **Kľúč účtu** pre účet Data Lake Storage. Použitie tejto metódy overenia znamená, že ste informovaní, ak vaša organizácia otáča kľúče. Ty musíš [aktualizovať konfiguráciu prostredia](manage-environments.md#edit-an-existing-environment) s novým kľúčom, keď je otočený.
1. Vyberte, či chcete použiť Azure Private Link na pripojenie k účtu úložiska a [vytvorte pripojenie k súkromnému odkazu](security-overview.md#set-up-an-azure-private-link).

Po dokončení systémových procesov, ako je príjem údajov, systém vytvorí zodpovedajúce priečinky v účte úložiska. Vytvoria sa dátové súbory a súbory model.json, ktoré sa pridajú do priečinkov podľa názvu procesu.

Ak vytvoríte viacero prostredí Customer Insights a rozhodnete sa uložiť výstupné entity z týchto prostredí do svojho účtu úložiska, Customer Insights vytvorí samostatné priečinky pre každé prostredie s `ci_environmentID` v kontajneri.
