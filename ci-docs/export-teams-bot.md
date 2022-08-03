---
title: Bot služby Teams pre Dynamics 365 Customer Insights (ukážka)
description: Vyhľadajte jednotné profily zákazníkov v službe Microsoft Teams pomocou bota.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: d140ae72578b48091a41005c4acafe03bac540da
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195861"
---
# <a name="teams-bot-for-dynamics-365-customer-insights-preview"></a>Bot služby Teams pre Dynamics 365 Customer Insights (ukážka)

Pripojte sa k Microsoft Teams, aby mohol bot vyhľadať jednotné profily zákazníkov v kanáloch služby Teams.

:::image type="content" source="media/teams-bot.png" alt-text="Bot Teams, ktorý zobrazuje záznam zákazníka":::

## <a name="prerequisites"></a>Požiadavky

- Aspoň jeden [zdroj údajov pridané](data-sources.md).
- [Proces zjednocovania](data-unification.md) je dokončený.
- Polia sa pridajú do [index vyhľadávania a filtrovania](search-filter-index.md).
- Customer Insights a Teams sú v rovnakej organizácii.
- Vaše prostredie má primárne cieľové publikum nastavené na individuálnych zákazníkov. Firemné obchodné vzťahy nie sú podporované.


> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWRElj]

## <a name="configure-the-bot"></a>Konfigurácia bota

1. Prejdite do časti **Správca** > **Pripojenia**.
1. Na dlaždici Microsoft Teams vyberte **Nastaviť**.
1. Ste presmerovaný do oblasti **Aplikácie** v Teams. Môžete tiež otvoriť Teams a vybrať **Aplikácie** v ľavom dolnom rohu alebo [ho stiahnuť z AppSource](https://go.microsoft.com/fwlink/?linkid=2124104) priamo.
1. Vyhľadajte **Customer Insights** a vyberte aplikáciu.
1. Stlačte možnosť **Pridať**.
1. Prihláste sa do Customer Insights v Teams. Zobrazí sa uvítacia správa.

## <a name="things-you-can-do-with-the-bot"></a>Veci, ktoré môžete robiť s botom

Bot poskytuje možnosti vyhľadávania pre zjednotené profily zákazníkov.

- Zadajte **Vyhľadávanie** nasleduje meno, e-mailová adresa alebo akékoľvek iné pole v zjednotenom zákazníckom profile, ktoré sa pridá do indexu vyhľadávania a filtrovania.

  Z výsledného profilu zákazníka dostanete kartu s až 15 poľami. Viaceré zhody vrátia zoznam výsledkov, kde si môžete vybrať profil. Ak chcete vyhľadať presnú zhodu, pridajte hľadaný výraz do dvojitých úvodzoviek.

- Ak vaša organizácia spravuje viacero prostredí Customer Insights v tej istej organizácii, zadajte **spínacia inštancia** vyberte prostredie, ku ktorému chcete robota pripojiť.

- Zadajte **pomoc**, aby ste videli zoznam dostupných príkazov pre bota.  

[!INCLUDE [footer-include](includes/footer-banner.md)]