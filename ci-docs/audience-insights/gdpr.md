---
title: Žiadosti dotknutých osôb (DSR) podľa GDPR | Dokumentácia spoločnosti Microsoft
description: Odpovedajte na žiadosti dotknutých osôb pre funkciu prehľadov cieľových skupín v službe Dynamics 365 Customer Insights.
ms.date: 05/14/2020
ms.reviewer: wimohabb
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: ed9aa09fba938606611c6ce86c2b250c5e19c606
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268705"
---
# <a name="data-subject-rights-dsr-requests-under-gdpr"></a><span data-ttu-id="a3c53-103">Žiadosti o práva dotknutých osôb (DSR) podľa GDPR</span><span class="sxs-lookup"><span data-stu-id="a3c53-103">Data Subject Rights (DSR) requests under GDPR</span></span>

## <a name="responding-to-gdpr-data-subject-delete-requests-for-dynamics-365-customer-insights-audience-insights-capability"></a><span data-ttu-id="a3c53-104">Odpovede na žiadosti dotknutých osôb o odstránenie podľa nariadenia GRPR pre funkciu prehľadov cieľových skupín v službe Dynamics 365 Customer Insights</span><span class="sxs-lookup"><span data-stu-id="a3c53-104">Responding to GDPR data subject delete requests for Dynamics 365 Customer Insights audience insights capability</span></span>

<span data-ttu-id="a3c53-105">„Právo na vymazanie“ odstránením osobných údajov z údajov o zákazníkoch organizácie je kľúčovou ochranou podľa všeobecného nariadenia o ochrane údajov (GDPR).</span><span class="sxs-lookup"><span data-stu-id="a3c53-105">The “right to erasure” by the removal of personal data from an organization’s customer data is a key protection in the General Data Protection Regulation (GDPR).</span></span> <span data-ttu-id="a3c53-106">Odstránenie osobných údajov zahŕňa odstránenie všetkých osobných údajov a protokolov generovaných systémom, okrem informácií z denníkov auditu.</span><span class="sxs-lookup"><span data-stu-id="a3c53-106">Removing personal data includes removing all personal data and system-generated logs, except audit log information.</span></span>

### <a name="manage-data-subject-delete-requests"></a><span data-ttu-id="a3c53-107">Správa požiadaviek na odstránenie dotknutej osoby</span><span class="sxs-lookup"><span data-stu-id="a3c53-107">Manage data subject delete requests</span></span>

<span data-ttu-id="a3c53-108">Prehľady cieľových skupín ponúkajú nasledujúce integrované rozhranie na vymazanie osobných údajov pre konkrétneho zákazníka alebo používateľa:</span><span class="sxs-lookup"><span data-stu-id="a3c53-108">Audience insights offers the following in-product experiences to delete personal data for a specific customer or user:</span></span>

- <span data-ttu-id="a3c53-109">**Spravovať žiadosti o vymazanie údajov zákazníkov**: Údaje zákazníkov v Customer Insights sa získavajú z pôvodných zdrojov údajov, ktoré nepochádzajú z Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="a3c53-109">**Manage delete requests for customer data**: Customer data in Customer Insights is ingested from original data sources external to Customer Insights.</span></span> <span data-ttu-id="a3c53-110">Všetky žiadosti o vymazanie GDPR musia byť vykonané v pôvodnom zdroji údajov.</span><span class="sxs-lookup"><span data-stu-id="a3c53-110">All GDPR delete requests must be performed in the original data source.</span></span>
- <span data-ttu-id="a3c53-111">**Spravovanie žiadostí o vymazanie používateľských údajov v Customer Insights**: Údaje pre používateľov vytvára služba Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="a3c53-111">**Manage delete requests for Customer Insights user data**: Data for users is created by Customer Insights.</span></span> <span data-ttu-id="a3c53-112">Všetky žiadosti o vymazanie GDPR sa musia vykonať v Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="a3c53-112">All GDPR delete requests must be performed in Customer Insights.</span></span>

#### <a name="manage-delete-requests-for-customer-data"></a><span data-ttu-id="a3c53-113">Spravovanie žiadostí o vymazanie údajov o zákazníkoch</span><span class="sxs-lookup"><span data-stu-id="a3c53-113">Manage delete requests for customer data</span></span>

<span data-ttu-id="a3c53-114">Správca Customer Insights môže podľa týchto krokov odstrániť zákaznícke údaje, ktoré boli odstránené v zdroji údajov:</span><span class="sxs-lookup"><span data-stu-id="a3c53-114">A Customer Insights admin can follow these steps to remove customer data that was deleted in the data source:</span></span>

1. <span data-ttu-id="a3c53-115">Prihlásiť sa do Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="a3c53-115">Sign in to Dynamics 365 Customer Insights.</span></span>
2. <span data-ttu-id="a3c53-116">V prehľadoch cieľových skupín prejdite na **Údaje** > **Zdroje údajov**</span><span class="sxs-lookup"><span data-stu-id="a3c53-116">In audience insights, go to **Data** > **Data sources**</span></span>
3. <span data-ttu-id="a3c53-117">Pre každý zdroj údajov v zozname, ktorý obsahuje odstránené údaje o zákazníkoch:</span><span class="sxs-lookup"><span data-stu-id="a3c53-117">For each data source in the list that contains deleted customer data:</span></span>
   1. <span data-ttu-id="a3c53-118">Vyberte (...) a potom možnosť **Obnoviť**.</span><span class="sxs-lookup"><span data-stu-id="a3c53-118">Select (...) and then select **Refresh**.</span></span>
   2. <span data-ttu-id="a3c53-119">Skontrolujte stav zdroja údajov v časti **Stav**.</span><span class="sxs-lookup"><span data-stu-id="a3c53-119">Check the status of the data source under **Status**.</span></span> <span data-ttu-id="a3c53-120">Začiarknutie znamená, že obnovenie bolo úspešné.</span><span class="sxs-lookup"><span data-stu-id="a3c53-120">A check mark means the refresh was successful.</span></span> <span data-ttu-id="a3c53-121">Výstražný trojuholník znamená, že sa niečo pokazilo.</span><span class="sxs-lookup"><span data-stu-id="a3c53-121">A warning triangle means something went wrong.</span></span> <span data-ttu-id="a3c53-122">Ak sa zobrazí výstražný trojuholník, kontaktujte D365CI@microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="a3c53-122">If a warning triangle is displayed, contact D365CI@microsoft.com.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="a3c53-123">![Spravovanie žiadostí o vymazanie údajov o zákazníkoch podľa GDPR](media/gdpr-data-sources.png "Spravovanie žiadostí o vymazanie údajov o zákazníkoch podľa GDPR")</span><span class="sxs-lookup"><span data-stu-id="a3c53-123">![Handling GDPR delete requests for customer data](media/gdpr-data-sources.png "Handling GDPR delete requests for customer data")</span></span>

#### <a name="manage-delete-requests-for-user-data"></a><span data-ttu-id="a3c53-124">Spravovanie žiadostí o vymazanie údajov o používateľoch</span><span class="sxs-lookup"><span data-stu-id="a3c53-124">Manage delete requests for user data</span></span>

<span data-ttu-id="a3c53-125">Správca Customer Insights môže podľa týchto krokov odstrániť používateľské údaje Customer Insights:</span><span class="sxs-lookup"><span data-stu-id="a3c53-125">A Customer Insights admin can follow these steps to delete Customer Insights user data:</span></span>

1. <span data-ttu-id="a3c53-126">Prihlásiť sa do Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="a3c53-126">Sign in to Dynamics 365 Customer Insights.</span></span>
2. <span data-ttu-id="a3c53-127">V prehľadoch cieľových skupín prejdite na **Správa** > **Povolenia**.</span><span class="sxs-lookup"><span data-stu-id="a3c53-127">In audience insights, go to **Admin** > **Permissions**.</span></span>
3. <span data-ttu-id="a3c53-128">Začiarknite políčka používateľa, ktorého chcete odstrániť.</span><span class="sxs-lookup"><span data-stu-id="a3c53-128">Select the check box for the user you want to delete.</span></span>
4. <span data-ttu-id="a3c53-129">Vyberte možnosť **Odstrániť**.</span><span class="sxs-lookup"><span data-stu-id="a3c53-129">Select **Remove**.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="a3c53-130">![Vybavovanie žiadostí o vymazanie údajov o používateľoch podľa nariadenia GDPR](media/gdpr-permissions.png "Vybavovanie žiadostí o vymazanie údajov o používateľoch podľa nariadenia GDPR")</span><span class="sxs-lookup"><span data-stu-id="a3c53-130">![Handling GDPR delete requests foruser data](media/gdpr-permissions.png "Handling GDPR delete requests for user data")</span></span>

## <a name="responding-to-gdpr-data-subject-export-requests"></a><span data-ttu-id="a3c53-131">Odpovedanie na žiadosti o export dotknutých osôb pre podľa nariadenia GDPR</span><span class="sxs-lookup"><span data-stu-id="a3c53-131">Responding to GDPR data subject export requests</span></span>

<span data-ttu-id="a3c53-132">Ako súčasť nášho záväzku voči partnerovi s vami na vašej ceste k všeobecnému nariadeniu o ochrane údajov (GDPR) sme vyvinuli dokumentáciu, ktorá vám pomôže pripraviť sa.</span><span class="sxs-lookup"><span data-stu-id="a3c53-132">As part of our commitment to partner with you on your journey to the General Data Protection Regulation (GDPR), we’ve developed documentation to help you prepare.</span></span> <span data-ttu-id="a3c53-133">Táto dokumentácia popisuje kroky, ktoré dnes môžete podniknúť na podporu súladu s GDPR pri používaní prehľadov cieľových skupín.</span><span class="sxs-lookup"><span data-stu-id="a3c53-133">This documentation describes steps you can take today to support GDPR compliance when using audience insights.</span></span>

### <a name="manage-export-and-view-requests"></a><span data-ttu-id="a3c53-134">Spravovanie žiadostí o export a zobrazenie</span><span class="sxs-lookup"><span data-stu-id="a3c53-134">Manage export and view requests</span></span>

<span data-ttu-id="a3c53-135">Právo na prenosnosť údajov umožňuje dotknutým osobám požiadať o kópiu svojich osobných údajov v elektronickom formáte („štruktúrovaný, bežne používaný, strojovo čitateľný a interoperabilný formát“), ktorý sa môže preniesť inému prevádzkovateľovi údajov.</span><span class="sxs-lookup"><span data-stu-id="a3c53-135">The right of data portability allows data subjects to request a copy of their personal data in an electronic format (a “structured, commonly used, machine readable, and interoperable format”) that can be transmitted to another data controller.</span></span>

#### <a name="export-customer-data-tenant-admin"></a><span data-ttu-id="a3c53-136">Export údajov o zákazníkoch (správca nájomníka)</span><span class="sxs-lookup"><span data-stu-id="a3c53-136">Export customer data (tenant admin)</span></span>

<span data-ttu-id="a3c53-137">Správca nájomníka môže exportovať údaje podľa týchto krokov:</span><span class="sxs-lookup"><span data-stu-id="a3c53-137">A tenant administrator can follow these steps to export data:</span></span>

1. <span data-ttu-id="a3c53-138">Pošlite e-mail na D365CI@microsoft.com, v ktorom je uvedená e-mailová adresa požadovaného zákazníka.</span><span class="sxs-lookup"><span data-stu-id="a3c53-138">Send an email to D365CI@microsoft.com specifying the customer’s email address in the request.</span></span> <span data-ttu-id="a3c53-139">Tím služby Customer Insights pošle e-mail na zaregistrovanú e-mailovú adresu správcu nájomníka a požiada o potvrdenie exportu údajov.</span><span class="sxs-lookup"><span data-stu-id="a3c53-139">The Customer Insights team will send an email to the registered tenant admin email address, asking for confirmation to export data.</span></span>
2. <span data-ttu-id="a3c53-140">Potvrďte potvrdenie na exportovanie údajov pre požadovaného zákazníka.</span><span class="sxs-lookup"><span data-stu-id="a3c53-140">Acknowledge the confirmation to export the data for the requested customer.</span></span>
3. <span data-ttu-id="a3c53-141">Exportované údaje dostanete prostredníctvom e-mailovej adresy správcu nájomníka.</span><span class="sxs-lookup"><span data-stu-id="a3c53-141">Receive the exported data through the tenant admin email address.</span></span>

#### <a name="export-user-data-tenant-admin"></a><span data-ttu-id="a3c53-142">Export údajov o používateľoch (správca nájomníka)</span><span class="sxs-lookup"><span data-stu-id="a3c53-142">Export user data (tenant admin)</span></span>

1. <span data-ttu-id="a3c53-143">Pošlite e-mail na D365CI@microsoft.com, v ktorom je uvedená e-mailová adresa požadovaného používateľa.</span><span class="sxs-lookup"><span data-stu-id="a3c53-143">Send an email to D365CI@microsoft.com specifying the user’s email address in the request.</span></span> <span data-ttu-id="a3c53-144">Tím služby Customer Insights pošle e-mail na zaregistrovanú e-mailovú adresu správcu nájomníka a požiada o potvrdenie exportu údajov.</span><span class="sxs-lookup"><span data-stu-id="a3c53-144">The Customer Insights team will send an email to the registered tenant admin email address, asking for confirmation to export data.</span></span>
2. <span data-ttu-id="a3c53-145">Potvrďte potvrdenie na exportovanie údajov pre požadovaného používateľa.</span><span class="sxs-lookup"><span data-stu-id="a3c53-145">Acknowledge the confirmation to export the data for the requested user.</span></span>
3. <span data-ttu-id="a3c53-146">Exportované údaje dostanete prostredníctvom e-mailovej adresy správcu nájomníka.</span><span class="sxs-lookup"><span data-stu-id="a3c53-146">Receive the exported data through the tenant admin email address.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]