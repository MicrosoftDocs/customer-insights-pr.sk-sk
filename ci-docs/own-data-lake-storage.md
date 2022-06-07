---
title: Použite svoj vlastný Azure Data Lake Storage Účet Gen2
author: mukeshpo
description: Prečítajte si o požiadavkách na používanie vlastných Azure Data Lake Storage účet na ukladanie údajov Customer Insights.
ms.author: mukeshpo
ms.date: 05/30/2022
ms.topic: conceptual
ms.manager: shellyha
ms.custom: intro-internal
ms.reviewer: mhart
ms.openlocfilehash: 9fcd7645e34bf310ac3a1b98a0dd9a60598b19dc
ms.sourcegitcommit: f5af5613afd9c3f2f0695e2d62d225f0b504f033
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 06/01/2022
ms.locfileid: "8833955"
---
# <a name="use-your-own-azure-data-lake-storage-gen2-account"></a>Použite svoj vlastný Azure Data Lake Storage Účet Gen2

Dynamics 365 Customer Insights vám dáva možnosť uložiť všetky svoje údaje [Azure Data Lake Storage Gen2](/azure/storage/blobs/data-lake-storage-introduction).

Uložením údajov do Data Lake Storage súhlasíte s tým, že údaje budú prenesené a uložené v príslušnom geografickom umiestnení pre daný účet Azure Storage. Ďalšie informácie nájdete v časti [Centrum dôveryhodnosti spoločnosti Microsoft](https://www.microsoft.com/trust-center).

Správcovia v Customer Insights môžu [vytvárať prostredia](create-environment.md) a [zadajte možnosť ukladania údajov](create-environment.md#step-2-configure-data-storage) v procese.

## <a name="prerequisites-to-use-your-storage-account"></a>Predpoklady na používanie účtu úložiska

- Azure Data Lake Storage účty musia byť v rovnakej oblasti Azure, ktorú ste vybrali pri vytváraní prostredia Customer Insights. Región prostredia Customer Insights môžete skontrolovať pod **Admin** > **systém** > **O**.
- Data Lake Storage musí byť Gen2 a musí mať [hierarchický menný priestor povolený](/azure/storage/blobs/create-data-lake-storage-account). Účty úložiska Gen1 nie sú podporované.
- Kontajner s názvom`customerinsights` musí existovať na účte úložiska. Musíte ho vytvoriť skôr, ako použijete svoj vlastný Data Lake Storage v Customer Insights. Správca, ktorý nastavuje prostredie Customer Insights, potrebuje rolu prispievateľa údajov objektu Storage Blob alebo vlastníka údajov objektu úložiska v účte úložiska alebo`customerinsights` kontajner. Ďalšie informácie o prideľovaní povolení v účte úložiska nájdete v časti [Vytvorte si účet úložiska](/azure/storage/common/storage-account-create?toc=%2Fazure%2Fstorage%2Fblobs%2Ftoc.json&tabs=azure-portal).

## <a name="connect-customer-insights-with-your-storage-account"></a>Prepojte Customer Insights s vaším účtom úložiska

Keď vytvoríte nové prostredie, skontrolujte, či existuje účet Data Lake Storage a či sú splnené všetky predpoklady.

1. V **Úložisko dát** krok pri vytváraní prostredia, nastav **Uložiť výstupné dáta** do **Azure Data Lake Storage Gen2**.
1. Vyberte si, ako na to **Pripojte úložisko**. Na autentifikáciu si môžete vybrať medzi možnosťou založenou na zdrojoch a možnosťou založenou na predplatnom. Ďalšie informácie nájdete v časti [Pripojte sa k Azure Data Lake Storage účtu pomocou Azure Service Principal](connect-service-principal.md).
   - Pre **Predplatné Azure**, vyber **Predplatné**, **zdrojov** a **Účet úložiska** ktorý obsahuje`customerinsights` kontajner.
   - Pre **Kľúč účtu**, poskytnúť **Názov účtu** a **Kľúč účtu** pre účet Data Lake Storage. Použitie tejto metódy overenia znamená, že ste informovaní, ak vaša organizácia strieda kľúče. Ty musíš [aktualizovať konfiguráciu prostredia](manage-environments.md#edit-an-existing-environment) s novým kľúčom, keď je otočený.

Po dokončení systémových procesov, ako je príjem údajov, systém vytvorí zodpovedajúce priečinky v účte úložiska. Vytvoria sa dátové súbory a súbory *model.json*, ktoré sa pridajú do priečinkov podľa názvu procesu.

Ak vytvoríte viacero prostredí Customer Insights a rozhodnete sa uložiť výstupné entity z týchto prostredí do svojho účtu úložiska, Customer Insights vytvorí samostatné priečinky pre každé prostredie s `ci_environmentID` v kontajneri.
