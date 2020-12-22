---
title: Bot pre Microsoft Teams
description: Vyhľadajte jednotné profily zákazníkov v službe Microsoft Teams pomocou bota.
ms.date: 04/21/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 45ea23fbefe5f1d44c3961183b76d2cc5c45355e
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406923"
---
# <a name="teams-bot-for-dynamics-365-customer-insights-preview"></a><span data-ttu-id="73754-103">Bot služby Teams pre Dynamics 365 Customer Insights (ukážka)</span><span class="sxs-lookup"><span data-stu-id="73754-103">Teams bot for Dynamics 365 Customer Insights (preview)</span></span>

<span data-ttu-id="73754-104">Pripojte sa k Microsoft Teams, aby mohol bot vyhľadať jednotné profily zákazníkov v kanáloch služby Teams.</span><span class="sxs-lookup"><span data-stu-id="73754-104">Connect with Microsoft Teams to let a bot look up unified customer profiles in Teams channels.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="73754-105">![Bot Teams, ktorý zobrazuje záznam zákazníka](media/teams-bot.png "Bot Teams, ktorý zobrazuje záznam zákazníka")</span><span class="sxs-lookup"><span data-stu-id="73754-105">![Teams bot showing a customer record](media/teams-bot.png "Teams bot showing a customer record")</span></span>

## <a name="prerequisites"></a><span data-ttu-id="73754-106">Predpoklady</span><span class="sxs-lookup"><span data-stu-id="73754-106">Prerequisites</span></span>

<span data-ttu-id="73754-107">Na nastavenie a konfiguráciu bota musia byť splnené nasledujúce predpoklady:</span><span class="sxs-lookup"><span data-stu-id="73754-107">To set up and configure the bot, the following prerequisites must be met:</span></span>

- <span data-ttu-id="73754-108">Existuje aspoň jeden [pridaný zdroj údajov](data-sources.md).</span><span class="sxs-lookup"><span data-stu-id="73754-108">There's at least one [data source added](data-sources.md).</span></span>
- <span data-ttu-id="73754-109">[Proces zjednocovania](data-unification.md) je dokončený.</span><span class="sxs-lookup"><span data-stu-id="73754-109">The [unification process](data-unification.md) is complete.</span></span>
- <span data-ttu-id="73754-110">Polia sa pridávajú do [indexu vyhľadávania a filtrovania](search-filter-index.md).</span><span class="sxs-lookup"><span data-stu-id="73754-110">Fields are added to the [search and filter index](search-filter-index.md).</span></span>
- <span data-ttu-id="73754-111">Customer Insights a Teams sú v rovnakej organizácii.</span><span class="sxs-lookup"><span data-stu-id="73754-111">Customer Insights and Teams are in the same organization.</span></span>

## <a name="configure-the-bot"></a><span data-ttu-id="73754-112">Konfigurácia bota</span><span class="sxs-lookup"><span data-stu-id="73754-112">Configure the bot</span></span>

1. <span data-ttu-id="73754-113">V prehľadoch cieľových skupín prejdite na **Správca** > **Ciele exportu**.</span><span class="sxs-lookup"><span data-stu-id="73754-113">In audience insights, go to **Admin** > **Export Destinations**.</span></span>
1. <span data-ttu-id="73754-114">Na dlaždici Microsoft Teams vyberte **Nastaviť**.</span><span class="sxs-lookup"><span data-stu-id="73754-114">On the Microsoft Teams tile, select **Set up**.</span></span>
1. <span data-ttu-id="73754-115">Ste presmerovaný do oblasti **Aplikácie** v Teams.</span><span class="sxs-lookup"><span data-stu-id="73754-115">You're redirected to the **Apps** area in Teams.</span></span> <span data-ttu-id="73754-116">Môžete tiež otvoriť Teams a vybrať **Aplikácie** v ľavom dolnom rohu alebo [ho stiahnuť z AppSource](https://go.microsoft.com/fwlink/?linkid=2124104) priamo.</span><span class="sxs-lookup"><span data-stu-id="73754-116">You can also open Teams and select **Apps** in the bottom-left corner or [get it from AppSource](https://go.microsoft.com/fwlink/?linkid=2124104) directly.</span></span>
1. <span data-ttu-id="73754-117">Vyhľadajte **Customer Insights** a vyberte aplikáciu.</span><span class="sxs-lookup"><span data-stu-id="73754-117">Search for **Customer Insights** and select the app.</span></span>
1. <span data-ttu-id="73754-118">Stlačte možnosť **Pridať**.</span><span class="sxs-lookup"><span data-stu-id="73754-118">Select **Add**.</span></span>
1. <span data-ttu-id="73754-119">Po prihlásení sa do Customer Insights v Teams sa zobrazí uvítacia správa a môžete začať.</span><span class="sxs-lookup"><span data-stu-id="73754-119">After signing in to Customer Insights in Teams, you'll see a welcome message and can get started.</span></span>

## <a name="things-you-can-do-with-the-bot"></a><span data-ttu-id="73754-120">Veci, ktoré môžete robiť s botom</span><span class="sxs-lookup"><span data-stu-id="73754-120">Things you can do with the bot</span></span>

<span data-ttu-id="73754-121">Bot poskytuje možnosti vyhľadávania pre zjednotené profily zákazníkov.</span><span class="sxs-lookup"><span data-stu-id="73754-121">The bot provides lookup capabilities for unified customer profiles.</span></span>

- <span data-ttu-id="73754-122">Zadajte **vyhľadávať** a následne meno, e-mailovú adresu alebo akékoľvek iné pole v zjednotenom profile zákazníka, ktorý sa pridá do indexu vyhľadávania a filtra.</span><span class="sxs-lookup"><span data-stu-id="73754-122">Enter **search** followed by a name, email address, or any other field on the unified customer profile that is added to the search and filter index.</span></span>

  <span data-ttu-id="73754-123">Z výsledného profilu zákazníka dostanete kartu s až 15 poľami.</span><span class="sxs-lookup"><span data-stu-id="73754-123">You'll get a card with up to 15 fields from the resulting customer profile.</span></span> <span data-ttu-id="73754-124">Viaceré zhody vrátia zoznam výsledkov, kde si môžete vybrať profil.</span><span class="sxs-lookup"><span data-stu-id="73754-124">Multiple matches return a list of results where you can select a profile.</span></span> <span data-ttu-id="73754-125">Ak chcete vyhľadať presnú zhodu, môžete hľadaný výraz pridať do dvojitých úvodzoviek.</span><span class="sxs-lookup"><span data-stu-id="73754-125">You can add the search term in double quotes to look up an exact match.</span></span>

- <span data-ttu-id="73754-126">Ak vaša organizácia udržiava viac prostredí služby Customer Insights v tej istej organizácii, môžete otvoriť **switchinstance** a vybrať, ku ktorému prostrediu chcete bota pripojiť.</span><span class="sxs-lookup"><span data-stu-id="73754-126">If your organization maintains multiple Customer Insights environments in the same organization, you can enter **switchinstance** to choose which environment you want to connect the bot to.</span></span>

- <span data-ttu-id="73754-127">Zadajte **pomoc**, aby ste videli zoznam dostupných príkazov pre bota.</span><span class="sxs-lookup"><span data-stu-id="73754-127">Enter **help** to see a list of available commands for the bot.</span></span>  
