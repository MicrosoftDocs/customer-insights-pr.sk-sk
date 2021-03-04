---
title: Inštalácia a konfigurácia doplnku Karta zákazníka
description: Inštalácia a konfigurácia doplnku Karta zákazníka pre Dynamics 365 Customer Insights.
ms.date: 01/20/2021
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: a6d5b49380ed129cf147698a16f5f3f597bf7fbc
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268063"
---
# <a name="customer-card-add-in-preview"></a><span data-ttu-id="fdf22-103">Doplnok Karta zákazníka (ukážka)</span><span class="sxs-lookup"><span data-stu-id="fdf22-103">Customer Card Add-in (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="fdf22-104">Získajte kompletný prehľad o svojich zákazníkoch priamo v aplikáciách Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="fdf22-104">Get a 360-degree view of your customers directly in Dynamics 365 apps.</span></span> <span data-ttu-id="fdf22-105">Pomocou doplnku Karta zákazníka si môžete prezerať demografické údaje, štatistiky a časové harmonogramy aktivít.</span><span class="sxs-lookup"><span data-stu-id="fdf22-105">View demographics, insights, and activity timelines with the Customer Card Add-in.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="fdf22-106">Predpoklady</span><span class="sxs-lookup"><span data-stu-id="fdf22-106">Prerequisites</span></span>

- <span data-ttu-id="fdf22-107">Aplikácia Dynamics 365 (napríklad Centrum predaja alebo Centrum služieb pre zákazníkov), verzia 9.0 a novšia, s povoleným Zjednoteným rozhraním.</span><span class="sxs-lookup"><span data-stu-id="fdf22-107">Dynamics 365 app (such as Sales Hub or Customer Service Hub), version 9.0 and later with Unified Interface enabled.</span></span>
- <span data-ttu-id="fdf22-108">Profily zákazníkov [prijaté z aplikácie Dynamics 365 pomocou služby Common Data Service](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="fdf22-108">Customer profiles [ingested from the Dynamics 365 app using Common Data Service](connect-power-query.md).</span></span>
- <span data-ttu-id="fdf22-109">Používatelia doplnku Karta zákazníka musia byť [pridaní ako používatelia](permissions.md) v prehľadoch cieľových skupín.</span><span class="sxs-lookup"><span data-stu-id="fdf22-109">Users of the Customer Card Add-in need to be [added as users](permissions.md) in audience insights.</span></span>
- <span data-ttu-id="fdf22-110">[Konfigurované možnosti vyhľadávania a filtrovania](search-filter-index.md).</span><span class="sxs-lookup"><span data-stu-id="fdf22-110">[Configured search and filter capabilities](search-filter-index.md).</span></span>
- <span data-ttu-id="fdf22-111">Demografický ovládací prvok: Demografické polia (ako napríklad vek alebo pohlavie) sú k dispozícii v zjednotenom profile zákazníka.</span><span class="sxs-lookup"><span data-stu-id="fdf22-111">Demographic control: Demographic fields(such as age or gender) are available in the unified customer profile.</span></span>
- <span data-ttu-id="fdf22-112">Kontrola obohatenia: Vyžaduje sa aktívne [obohatenie](enrichment-hub.md) aplikované na profily zákazníkov.</span><span class="sxs-lookup"><span data-stu-id="fdf22-112">Enrichment control: Requires active [enrichments](enrichment-hub.md) applied to customer profiles.</span></span>
- <span data-ttu-id="fdf22-113">Inteligenčný ovládací prvok: Vyžaduje údaje generované pomocou strojového učenia platformy Azure ([predpovede](predictions.md) alebo [vlastné modely](custom-models.md))</span><span class="sxs-lookup"><span data-stu-id="fdf22-113">Intelligence control: Requires data generated using Azure Machine Learning ([Predictions](predictions.md) or [Custom Models](custom-models.md))</span></span>
- <span data-ttu-id="fdf22-114">Merací ovládací prvok: Vyžadujú sa [nakonfigurované miery](measures.md).</span><span class="sxs-lookup"><span data-stu-id="fdf22-114">Measure control: Requires [configured measures](measures.md).</span></span>
- <span data-ttu-id="fdf22-115">Ovládací prvok časovej osi: Vyžadujú sa [nakonfigurované aktivity](activities.md).</span><span class="sxs-lookup"><span data-stu-id="fdf22-115">Timeline control: Requires [configured activities](activities.md).</span></span>

## <a name="install-the-customer-card-add-in"></a><span data-ttu-id="fdf22-116">Inštalácia doplnku Karta zákazníka</span><span class="sxs-lookup"><span data-stu-id="fdf22-116">Install the Customer Card Add-in</span></span>

<span data-ttu-id="fdf22-117">Doplnok ku karte zákazníka je riešením pre aplikácie na zapojenie zákazníkov do Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="fdf22-117">The Customer Card Add-in is a solution for customer engagement apps in Dynamics 365.</span></span> <span data-ttu-id="fdf22-118">Ak chcete nainštalovať riešenie, prejdite do AppSource a vyhľadajte **Karta zákazníka Dynamics**.</span><span class="sxs-lookup"><span data-stu-id="fdf22-118">To install the solution, go to AppSource and search for **Dynamics Customer Card**.</span></span> <span data-ttu-id="fdf22-119">Vyberte [Doplnok Karta zákazníka v AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) a vyberte **Získať teraz**.</span><span class="sxs-lookup"><span data-stu-id="fdf22-119">Select the [Customer Card Add-in on AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) and select **Get It Now**.</span></span>

<span data-ttu-id="fdf22-120">Možno sa budete musieť prihlásiť so svojimi prihlasovacími údajmi, aby mohla aplikácia Dynamics 365 nainštalovať riešenie.</span><span class="sxs-lookup"><span data-stu-id="fdf22-120">You may need to sign in with your admin credentials for the Dynamics 365 app to install the solution.</span></span>

<span data-ttu-id="fdf22-121">Môže to trvať nejaký čas, kým sa riešenie nainštaluje do vášho prostredia.</span><span class="sxs-lookup"><span data-stu-id="fdf22-121">It can take some time for the solution to be installed to your environment.</span></span>

## <a name="configure-the-customer-card-add-in"></a><span data-ttu-id="fdf22-122">Konfigurácia doplnku Karta zákazníka</span><span class="sxs-lookup"><span data-stu-id="fdf22-122">Configure the Customer Card Add-in</span></span>

1. <span data-ttu-id="fdf22-123">Ako správca prejdite do časti **Nastavenia** v Dynamics 365 a vyberte položku **Riešenia**.</span><span class="sxs-lookup"><span data-stu-id="fdf22-123">As an admin, go to the **Settings** section in Dynamics 365 and select **Solutions**.</span></span>

1. <span data-ttu-id="fdf22-124">Vyberte odkaz **Zobrazovaný názov** pre riešenie **Doplnok Karta zákazníka Dynamics 365 Customer Insights (ukážka)**.</span><span class="sxs-lookup"><span data-stu-id="fdf22-124">Select the **Display Name** link for the **Dynamics 365 Customer Insights Customer Card Add-in (Preview)** solution.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="fdf22-125">![Výber zobrazovaného názvu](media/select-display-name.png "Výber zobrazovaného názvu")</span><span class="sxs-lookup"><span data-stu-id="fdf22-125">![Select display name](media/select-display-name.png "Select display name")</span></span>

1. <span data-ttu-id="fdf22-126">Vyberte **Prihlásiť sa** a zadajte prihlasovacie údaje pre účet správcu, ktorý používate na konfiguráciu Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="fdf22-126">Select **Sign in** and enter the credentials for the admin account you use to configure Customer Insights.</span></span>

   > [!NOTE]
   > <span data-ttu-id="fdf22-127">Skontrolujte, či blokovanie automaticky otváraných okien v prehľadávači neblokuje overovacie okno, keď vyberiete tlačidlo **Prihlásiť sa**.</span><span class="sxs-lookup"><span data-stu-id="fdf22-127">Check that the browser pop-up blocker does not block the authentication window when you select the **Sign in** button.</span></span>

1. <span data-ttu-id="fdf22-128">Vyberte prostredie, z ktorého chcete načítať údaje.</span><span class="sxs-lookup"><span data-stu-id="fdf22-128">Select the environment you want to fetch data from.</span></span>

1. <span data-ttu-id="fdf22-129">Definujte, ktoré pole sa má namapovať k záznamom v aplikácii Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="fdf22-129">Define which the field mapping to records in the Dynamics 365 app.</span></span>
   - <span data-ttu-id="fdf22-130">Na mapovanie ku kontaktu vyberte pole v entite Zákazník, ktoré sa zhoduje s ID entity vášho kontaktu.</span><span class="sxs-lookup"><span data-stu-id="fdf22-130">To map with a contact, select the field in the Customer entity that matches the ID of your contact entity.</span></span>
   - <span data-ttu-id="fdf22-131">Na mapovanie k obchodnému vzťahu vyberte pole v entite Zákazník, ktoré sa zhoduje s ID entity vášho obchodného vzťahu.</span><span class="sxs-lookup"><span data-stu-id="fdf22-131">To map with an account, select the field in the Customer entity that matches the ID of your account entity.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="fdf22-132">![Pole ID kontaktu](media/contact-id-field.png "Pole ID kontaktu")</span><span class="sxs-lookup"><span data-stu-id="fdf22-132">![Contact ID field](media/contact-id-field.png "Contact ID field")</span></span>

1. <span data-ttu-id="fdf22-133">Stlačením možnosti **Uložiť konfiguráciu** uložte nastavenia.</span><span class="sxs-lookup"><span data-stu-id="fdf22-133">Select **Save configuration** to save the settings.</span></span>

1. <span data-ttu-id="fdf22-134">Ďalej musíte v Dynamics 365 prideliť roly zabezpečenia, aby si používatelia mohli prispôsobiť a vidieť Kartu zákazníka.</span><span class="sxs-lookup"><span data-stu-id="fdf22-134">Next, you need to assign security roles in Dynamics 365 so users can customize and see the customer card.</span></span> <span data-ttu-id="fdf22-135">V aplikácii Dynamics 365 prejdite do časti **Nastavenie** > **Zabezpečenie** > **Používatelia**.</span><span class="sxs-lookup"><span data-stu-id="fdf22-135">In Dynamics 365, go to **Settings** > **Security** > **Users**.</span></span> <span data-ttu-id="fdf22-136">Vyberte používateľov, ktorých chcete upraviť, a vyberte **Spravovať roly**.</span><span class="sxs-lookup"><span data-stu-id="fdf22-136">Select the users to edit user roles and select **Manage roles**.</span></span>

1. <span data-ttu-id="fdf22-137">Priraďte rolu **Prispôsobovač karty služby Customer Insights** používateľom, ktorí prispôsobia obsah zobrazený na karte pre celú organizáciu.</span><span class="sxs-lookup"><span data-stu-id="fdf22-137">Assign the **Customer Insights Card Customizer** role to users who will customize the content shown on the card for the whole organization.</span></span>

## <a name="add-customer-card-controls-to-forms"></a><span data-ttu-id="fdf22-138">Pridanie ovládacích prvkov Zákazníckej karty do formulárov</span><span class="sxs-lookup"><span data-stu-id="fdf22-138">Add Customer Card controls to forms</span></span>
  
1. <span data-ttu-id="fdf22-139">Ak chcete pridať ovládacie prvky Karty zákazníka do svojho formulára Kontakt, prejdite na stránku **Nastavenia** > **Prispôsobenia** v Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="fdf22-139">To add the Customer Card controls to your Contact form, go to the **Settings** > **Customizations** in Dynamics 365.</span></span>

1. <span data-ttu-id="fdf22-140">Stlačte možnosť **Prispôsobenie systému**.</span><span class="sxs-lookup"><span data-stu-id="fdf22-140">Select **Customize the System**.</span></span>

1. <span data-ttu-id="fdf22-141">Vyhľadajte entitu **Kontakt**, rozbaľte ju a potom vyberte položku **Formuláre**.</span><span class="sxs-lookup"><span data-stu-id="fdf22-141">Browse to the **Contact** entity, expand it and select **Forms**.</span></span>

1. <span data-ttu-id="fdf22-142">Vyberte formulár kontaktu, do ktorého chcete pridať ovládacie prvky Karty zákazníka.</span><span class="sxs-lookup"><span data-stu-id="fdf22-142">Select the contact form to which you want to add the Customer Card controls.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="fdf22-143">![Výber formulára kontaktu](media/contact-active-forms.png "Výber formulára kontaktu")</span><span class="sxs-lookup"><span data-stu-id="fdf22-143">![Select Contact form](media/contact-active-forms.png "Select Contact form")</span></span>

1. <span data-ttu-id="fdf22-144">Ak chcete pridať ovládací prvok, v editore formulárov presuňte ľubovoľné pole z **Prieskumníka polí** na miesto, kde sa má zobraziť ovládací prvok.</span><span class="sxs-lookup"><span data-stu-id="fdf22-144">To add a control, in the form editor, drag any field from the **Field Explorer** to where you want the control to appear.</span></span>

1. <span data-ttu-id="fdf22-145">Vyberte pole vo formulári, ktoré ste práve pridali, a potom položku **Zmeniť vlastnosti**.</span><span class="sxs-lookup"><span data-stu-id="fdf22-145">Select the field on the form that you just added, and select **Change Properties**.</span></span>

1. <span data-ttu-id="fdf22-146">Prejdite na kartu **Ovládacie prvky** a vyberte položku **Pridať ovládací prvok**.</span><span class="sxs-lookup"><span data-stu-id="fdf22-146">Go to the **Controls** tab and select **Add Control**.</span></span> <span data-ttu-id="fdf22-147">Vyberte jeden z dostupných vlastných ovládacích prvkov a potom položku **Pridať**.</span><span class="sxs-lookup"><span data-stu-id="fdf22-147">Choose one of the available custom controls and select **Add**.</span></span>

1. <span data-ttu-id="fdf22-148">V dialógovom okne **Vlastnosti poľa** zrušte začiarknutie políčka **Zobraziť menovku vo formulári**.</span><span class="sxs-lookup"><span data-stu-id="fdf22-148">In the **Field Properties** dialog, clear the **Display label on the form** check box.</span></span>

1. <span data-ttu-id="fdf22-149">Vyberte možnosť **Web** pre ovládací prvok.</span><span class="sxs-lookup"><span data-stu-id="fdf22-149">Select the **Web** option for the control.</span></span> <span data-ttu-id="fdf22-150">Pre kontrolu obohatenia vyberte typ obohatenia, ktorý chcete zobraziť, nakonfigurovaním poľa **enrichmentType**.</span><span class="sxs-lookup"><span data-stu-id="fdf22-150">For the Enrichment control, select which enrichment type you want to display by configuring the **enrichmentType** field.</span></span> <span data-ttu-id="fdf22-151">Pre každý typ obohatenia pridajte samostatnú kontrolu obohatenia.</span><span class="sxs-lookup"><span data-stu-id="fdf22-151">Add a separate enrichment control for each enrichment type.</span></span>

1. <span data-ttu-id="fdf22-152">Výberom **Uložiť** a **Publikovať** zverejnite aktualizovaný kontaktný formulár.</span><span class="sxs-lookup"><span data-stu-id="fdf22-152">Select **Save** and **Publish** to publish the updated contact form.</span></span>

1. <span data-ttu-id="fdf22-153">Prejdite na publikovaný kontaktný formulár.</span><span class="sxs-lookup"><span data-stu-id="fdf22-153">Go to the published contact form.</span></span> <span data-ttu-id="fdf22-154">Uvidíte novo pridaný ovládací prvok.</span><span class="sxs-lookup"><span data-stu-id="fdf22-154">You'll see the newly added control.</span></span> <span data-ttu-id="fdf22-155">Možno sa budete musieť prihlásiť pri prvom použití.</span><span class="sxs-lookup"><span data-stu-id="fdf22-155">You might need to sign in the first time you use it.</span></span>

1. <span data-ttu-id="fdf22-156">Ak chcete prispôsobiť, čo chcete zobraziť vo vlastnom ovládacom prvku, vyberte tlačidlo Upraviť v pravom hornom rohu.</span><span class="sxs-lookup"><span data-stu-id="fdf22-156">To customize what you want to show on the custom control, select the edit button in the upper-right corner.</span></span>

## <a name="upgrade-customer-card-add-in"></a><span data-ttu-id="fdf22-157">Aktualizácia doplnku Karta zákazníka</span><span class="sxs-lookup"><span data-stu-id="fdf22-157">Upgrade Customer Card Add-in</span></span>
<span data-ttu-id="fdf22-158">Doplnok Karta zákazníka sa neaktualizuje automaticky.</span><span class="sxs-lookup"><span data-stu-id="fdf22-158">The Customer Card Add-in doesn't upgrade automatically.</span></span> <span data-ttu-id="fdf22-159">Pri inovácii na najnovšiu verziu postupujte podľa tohto postupu v aplikácii Dynamics 365, ktorá má nainštalovaný doplnok.</span><span class="sxs-lookup"><span data-stu-id="fdf22-159">To upgrade to the latest version, follow this procedure in the Dynamics 365 app that has the Add-in installed.</span></span>

1. <span data-ttu-id="fdf22-160">V aplikácii Dynamics 365 prejdite na **Nastavenia** > **Prispôsobenie** a vyberte **Riešenia**.</span><span class="sxs-lookup"><span data-stu-id="fdf22-160">In the Dynamics 365 app, go to **Settings** > **Customization** and select **Solutions**.</span></span>

1. <span data-ttu-id="fdf22-161">V tabuľke doplnkov hľadajte **CustomerInsightsCustomerCard** a vyberte riadok.</span><span class="sxs-lookup"><span data-stu-id="fdf22-161">In the table of add-ins look for **CustomerInsightsCustomerCard** and select the row.</span></span>

1. <span data-ttu-id="fdf22-162">Vyberte **Aplikovať inováciu riešenia** v lište akcií.</span><span class="sxs-lookup"><span data-stu-id="fdf22-162">Select the **Apply Solution Upgrade** in the action bar.</span></span>

   :::image type="content" source="media/customer-card-add-in-upgrade.png" alt-text="Inovujte riešenie v oblasti Prispôsobenie aplikácií Dynamics 365":::

1. <span data-ttu-id="fdf22-164">Po spustení procesu inovácie sa vám bude zobrazovať indikátor načítania, kým sa aktualizácia nedokončí.</span><span class="sxs-lookup"><span data-stu-id="fdf22-164">After starting the upgrade process, you'll see a loading indicator until the upgrade completes.</span></span> <span data-ttu-id="fdf22-165">Ak nie je k dispozícii novšia verzia, pri inovácii sa zobrazí chybové hlásenie.</span><span class="sxs-lookup"><span data-stu-id="fdf22-165">If there's no newer version, the upgrade will show an error message.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]