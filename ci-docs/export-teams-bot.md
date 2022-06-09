---
title: Bot pre Microsoft Teams
description: Vyhľadajte jednotné profily zákazníkov v službe Microsoft Teams pomocou bota.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 89a293d5b6f9f5452b2ccba495d2475002806019
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 04/27/2022
ms.locfileid: "8643903"
---
# <a name="teams-bot-for-dynamics-365-customer-insights-preview"></a>Bot služby Teams pre Dynamics 365 Customer Insights (ukážka)

Pripojte sa k Microsoft Teams, aby mohol bot vyhľadať jednotné profily zákazníkov v kanáloch služby Teams.

> [!div class="mx-imgBorder"]
> ![Bot Teams, ktorý zobrazuje záznam zákazníka.](media/teams-bot.png "Bot Teams, ktorý zobrazuje záznam zákazníka")

## <a name="prerequisites"></a>Predpoklady

Na nastavenie a konfiguráciu bota musia byť splnené nasledujúce predpoklady:

- Existuje aspoň jeden [pridaný zdroj údajov](data-sources.md).
- [Proces zjednocovania](data-unification.md) je dokončený.
- Polia sa pridávajú do [indexu vyhľadávania a filtrovania](search-filter-index.md).
- Customer Insights a Teams sú v rovnakej organizácii.
- Vaše prostredie má primárne cieľové publikum nastavené na individuálnych zákazníkov. Firemné obchodné vzťahy nie sú podporované.


> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWRElj]

## <a name="configure-the-bot"></a>Konfigurácia bota

1. Ísť do **Admin** > **Exportné destinácie**.
1. Na dlaždici Microsoft Teams vyberte **Nastaviť**.
1. Ste presmerovaný do oblasti **Aplikácie** v Teams. Môžete tiež otvoriť Teams a vybrať **Aplikácie** v ľavom dolnom rohu alebo [ho stiahnuť z AppSource](https://go.microsoft.com/fwlink/?linkid=2124104) priamo.
1. Vyhľadajte **Customer Insights** a vyberte aplikáciu.
1. Stlačte možnosť **Pridať**.
1. Po prihlásení sa do Customer Insights v Teams sa zobrazí uvítacia správa a môžete začať.

## <a name="things-you-can-do-with-the-bot"></a>Veci, ktoré môžete robiť s botom

Bot poskytuje možnosti vyhľadávania pre zjednotené profily zákazníkov.

- Zadajte **vyhľadávať** a následne meno, e-mailovú adresu alebo akékoľvek iné pole v zjednotenom profile zákazníka, ktorý sa pridá do indexu vyhľadávania a filtra.

  Z výsledného profilu zákazníka dostanete kartu s až 15 poľami. Viaceré zhody vrátia zoznam výsledkov, kde si môžete vybrať profil. Ak chcete vyhľadať presnú zhodu, môžete hľadaný výraz pridať do dvojitých úvodzoviek.

- Ak vaša organizácia udržiava viac prostredí služby Customer Insights v tej istej organizácii, môžete otvoriť **switchinstance** a vybrať, ku ktorému prostrediu chcete bota pripojiť.

- Zadajte **pomoc**, aby ste videli zoznam dostupných príkazov pre bota.  


[!INCLUDE [footer-include](includes/footer-banner.md)]