---
title: Doplnok Customer Card pre aplikácie Dynamics 365
description: Pomocou tohto doplnku zobrazujte údaje z prehľadov cieľovej skupiny v aplikáciách Dynamics 365.
ms.date: 05/18/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 88492943ddbf9ae30c64d92b261433b74f34f682
ms.sourcegitcommit: d74430270f1b754322287c4f045d7febdae35be2
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 05/18/2021
ms.locfileid: "6059607"
---
# <a name="customer-card-add-in-preview"></a><span data-ttu-id="66ffc-103">Doplnok Karta zákazníka (ukážka)</span><span class="sxs-lookup"><span data-stu-id="66ffc-103">Customer Card Add-in (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="66ffc-104">Získajte kompletný prehľad o svojich zákazníkoch priamo v aplikáciách Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="66ffc-104">Get a 360-degree view of your customers directly in Dynamics 365 apps.</span></span> <span data-ttu-id="66ffc-105">S doplnkom Customer Card nainštalovaným v podporovanej aplikácii Dynamics 365 si môžete zvoliť zobrazenie demografických údajov, štatistík a časových osí aktivít.</span><span class="sxs-lookup"><span data-stu-id="66ffc-105">With the Customer Card Add-in installed in a supported Dynamics 365 app you can choose to display demographics, insights, and activity timelines.</span></span> <span data-ttu-id="66ffc-106">Doplnok načíta údaje z Customer Insights bez ovplyvnenia údajov v pripojenej aplikácii Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="66ffc-106">The add-in will retrieve data from Customer Insights without affecting the data in the connected Dynamics 365 app.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="66ffc-107">Predpoklady</span><span class="sxs-lookup"><span data-stu-id="66ffc-107">Prerequisites</span></span>

- <span data-ttu-id="66ffc-108">Doplnok funguje iba s aplikáciami Dynamics 365 riadenými modelmi, ako sú napríklad Sales alebo Customer Service, verzia 9.0 a novšia.</span><span class="sxs-lookup"><span data-stu-id="66ffc-108">The add-in only works with Dynamics 365 model-driven apps, such as Sales or Customer Service, version 9.0 and later.</span></span>
- <span data-ttu-id="66ffc-109">Aby sa vaše údaje Dynamics 365 mohli namapovať do profilov cieľovej skupiny, musia byť [prijaté z aplikácie Dynamics 365 pomocou konektora Common Data Service](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="66ffc-109">For your Dynamics 365 data to map to the audience insights customer profiles they need to be [ingested from the Dynamics 365 app using the Common Data Service connector](connect-power-query.md).</span></span>
- <span data-ttu-id="66ffc-110">Všetci používatelia Dynamics 365 doplnku Customer Card musia byť [pridaní ako používatelia](permissions.md) v prehľade cieľových skupín, aby mohli vidieť údaje.</span><span class="sxs-lookup"><span data-stu-id="66ffc-110">All Dynamics 365 users of the Customer Card Add-in must be [added as users](permissions.md) in audience insights to see the data.</span></span>
- <span data-ttu-id="66ffc-111">[Konfigurované možnosti vyhľadávania a filtrovania](search-filter-index.md) v prehľadoch cieľovej skupiny sú nevyhnutné na fungovanie vyhľadávania údajov.</span><span class="sxs-lookup"><span data-stu-id="66ffc-111">[Configured search and filter capabilities](search-filter-index.md) in audience insights are required for lookup of data to work.</span></span>
- <span data-ttu-id="66ffc-112">Každá kontrola doplnku sa spolieha na konkrétne údaje vo prehľadoch cieľovej skupiny:</span><span class="sxs-lookup"><span data-stu-id="66ffc-112">Each add-in control relies on specific data in audience insights:</span></span>
  - <span data-ttu-id="66ffc-113">Merací ovládací prvok: Vyžadujú sa [nakonfigurované miery](measures.md).</span><span class="sxs-lookup"><span data-stu-id="66ffc-113">Measure control: Requires [configured measures](measures.md).</span></span>
  - <span data-ttu-id="66ffc-114">Inteligentná kontrola: Vyžaduje údaje generované pomocou [predikcií](predictions.md) alebo [vlastných modelov](custom-models.md).</span><span class="sxs-lookup"><span data-stu-id="66ffc-114">Intelligence control: Requires data generated using [predictions](predictions.md) or [custom models](custom-models.md).</span></span>
  - <span data-ttu-id="66ffc-115">Demografický ovládací prvok: Demografické polia (ako napríklad vek alebo pohlavie) sú k dispozícii v zjednotenom profile zákazníka.</span><span class="sxs-lookup"><span data-stu-id="66ffc-115">Demographic control: Demographic fields(such as age or gender) are available in the unified customer profile.</span></span>
  - <span data-ttu-id="66ffc-116">Kontrola obohatenia: Vyžaduje sa aktívne [obohatenie](enrichment-hub.md) aplikované na profily zákazníkov.</span><span class="sxs-lookup"><span data-stu-id="66ffc-116">Enrichment control: Requires active [enrichments](enrichment-hub.md) applied to customer profiles.</span></span>
  - <span data-ttu-id="66ffc-117">Ovládací prvok časovej osi: Vyžadujú sa [nakonfigurované aktivity](activities.md).</span><span class="sxs-lookup"><span data-stu-id="66ffc-117">Timeline control: Requires [configured activities](activities.md).</span></span>

## <a name="install-the-customer-card-add-in"></a><span data-ttu-id="66ffc-118">Inštalácia doplnku Karta zákazníka</span><span class="sxs-lookup"><span data-stu-id="66ffc-118">Install the Customer Card Add-in</span></span>

<span data-ttu-id="66ffc-119">Doplnok ku karte zákazníka je riešením pre aplikácie na zapojenie zákazníkov do Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="66ffc-119">The Customer Card Add-in is a solution for customer engagement apps in Dynamics 365.</span></span> <span data-ttu-id="66ffc-120">Ak chcete nainštalovať riešenie, prejdite do AppSource a vyhľadajte **Karta zákazníka Dynamics**.</span><span class="sxs-lookup"><span data-stu-id="66ffc-120">To install the solution, go to AppSource and search for **Dynamics Customer Card**.</span></span> <span data-ttu-id="66ffc-121">Vyberte [Doplnok Karta zákazníka v AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) a vyberte **Získať teraz**.</span><span class="sxs-lookup"><span data-stu-id="66ffc-121">Select the [Customer Card Add-in on AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) and select **Get It Now**.</span></span>

<span data-ttu-id="66ffc-122">Možno sa budete musieť prihlásiť so svojimi prihlasovacími údajmi, aby mohla aplikácia Dynamics 365 nainštalovať riešenie.</span><span class="sxs-lookup"><span data-stu-id="66ffc-122">You may need to sign in with your admin credentials for the Dynamics 365 app to install the solution.</span></span>

<span data-ttu-id="66ffc-123">Môže to trvať nejaký čas, kým sa riešenie nainštaluje do vášho prostredia.</span><span class="sxs-lookup"><span data-stu-id="66ffc-123">It can take some time for the solution to be installed to your environment.</span></span>

## <a name="configure-the-customer-card-add-in"></a><span data-ttu-id="66ffc-124">Konfigurácia doplnku Karta zákazníka</span><span class="sxs-lookup"><span data-stu-id="66ffc-124">Configure the Customer Card Add-in</span></span>

1. <span data-ttu-id="66ffc-125">Ako správca prejdite do časti **Nastavenia** v Dynamics 365 a vyberte položku **Riešenia**.</span><span class="sxs-lookup"><span data-stu-id="66ffc-125">As an admin, go to the **Settings** section in Dynamics 365 and select **Solutions**.</span></span>

1. <span data-ttu-id="66ffc-126">Vyberte odkaz **Zobrazovaný názov** pre riešenie **Doplnok Karta zákazníka Dynamics 365 Customer Insights (ukážka)**.</span><span class="sxs-lookup"><span data-stu-id="66ffc-126">Select the **Display Name** link for the **Dynamics 365 Customer Insights Customer Card Add-in (Preview)** solution.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="66ffc-127">![Výber zobrazovaného názvu](media/select-display-name.png "Výber zobrazovaného názvu")</span><span class="sxs-lookup"><span data-stu-id="66ffc-127">![Select display name](media/select-display-name.png "Select display name")</span></span>

1. <span data-ttu-id="66ffc-128">Vyberte **Prihlásiť sa** a zadajte prihlasovacie údaje pre účet správcu, ktorý používate na konfiguráciu Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="66ffc-128">Select **Sign in** and enter the credentials for the admin account you use to configure Customer Insights.</span></span>

   > [!NOTE]
   > <span data-ttu-id="66ffc-129">Skontrolujte, či blokovanie automaticky otváraných okien v prehľadávači neblokuje overovacie okno, keď vyberiete tlačidlo **Prihlásiť sa**.</span><span class="sxs-lookup"><span data-stu-id="66ffc-129">Check that the browser pop-up blocker does not block the authentication window when you select the **Sign in** button.</span></span>

1. <span data-ttu-id="66ffc-130">Vyberte prostredie Customer Insights, z ktorého chcete načítať údaje.</span><span class="sxs-lookup"><span data-stu-id="66ffc-130">Select the Customer Insights environment you want to fetch data from.</span></span>

1. <span data-ttu-id="66ffc-131">Definujte mapovanie poľa na záznamy v aplikácii Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="66ffc-131">Define the field mapping to records in the Dynamics 365 app.</span></span> <span data-ttu-id="66ffc-132">V závislosti od vašich údajov v Customer Insights môžete mapovať nasledujúce možnosti:</span><span class="sxs-lookup"><span data-stu-id="66ffc-132">Depending on your data in Customer Insights you can choose to map the following options:</span></span>
   - <span data-ttu-id="66ffc-133">Na mapovanie ku kontaktu vyberte pole v entite Zákazník, ktoré sa zhoduje s ID entity vášho kontaktu.</span><span class="sxs-lookup"><span data-stu-id="66ffc-133">To map with a contact, select the field in the Customer entity that matches the ID of your contact entity.</span></span>
   - <span data-ttu-id="66ffc-134">Na mapovanie k obchodnému vzťahu vyberte pole v entite Zákazník, ktoré sa zhoduje s ID entity vášho obchodného vzťahu.</span><span class="sxs-lookup"><span data-stu-id="66ffc-134">To map with an account, select the field in the Customer entity that matches the ID of your account entity.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="66ffc-135">![Pole ID kontaktu](media/contact-id-field.png "Pole ID kontaktu")</span><span class="sxs-lookup"><span data-stu-id="66ffc-135">![Contact ID field](media/contact-id-field.png "Contact ID field")</span></span>

1. <span data-ttu-id="66ffc-136">Stlačením možnosti **Uložiť konfiguráciu** uložte nastavenia.</span><span class="sxs-lookup"><span data-stu-id="66ffc-136">Select **Save configuration** to save the settings.</span></span>

1. <span data-ttu-id="66ffc-137">Ďalej musíte v Dynamics 365 prideliť roly zabezpečenia, aby si používatelia mohli prispôsobiť a vidieť Kartu zákazníka.</span><span class="sxs-lookup"><span data-stu-id="66ffc-137">Next, you need to assign security roles in Dynamics 365 so users can customize and see the customer card.</span></span> <span data-ttu-id="66ffc-138">V aplikácii Dynamics 365 prejdite do časti **Nastavenie** > **Zabezpečenie** > **Používatelia**.</span><span class="sxs-lookup"><span data-stu-id="66ffc-138">In Dynamics 365, go to **Settings** > **Security** > **Users**.</span></span> <span data-ttu-id="66ffc-139">Vyberte používateľov, ktorých chcete upraviť, a vyberte **Spravovať roly**.</span><span class="sxs-lookup"><span data-stu-id="66ffc-139">Select the users to edit user roles and select **Manage roles**.</span></span>

1. <span data-ttu-id="66ffc-140">Priraďte rolu **Prispôsobovač karty služby Customer Insights** používateľom, ktorí prispôsobia obsah zobrazený na karte pre celú organizáciu.</span><span class="sxs-lookup"><span data-stu-id="66ffc-140">Assign the **Customer Insights Card Customizer** role to users who will customize the content shown on the card for the whole organization.</span></span>

## <a name="add-customer-card-controls-to-forms"></a><span data-ttu-id="66ffc-141">Pridanie ovládacích prvkov Zákazníckej karty do formulárov</span><span class="sxs-lookup"><span data-stu-id="66ffc-141">Add Customer Card controls to forms</span></span>
  
1. <span data-ttu-id="66ffc-142">Ak chcete pridať ovládacie prvky Karty zákazníka do svojho formulára Kontakt, prejdite na stránku **Nastavenia** > **Prispôsobenia** v Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="66ffc-142">To add the Customer Card controls to your Contact form, go to the **Settings** > **Customizations** in Dynamics 365.</span></span>

1. <span data-ttu-id="66ffc-143">Stlačte možnosť **Prispôsobenie systému**.</span><span class="sxs-lookup"><span data-stu-id="66ffc-143">Select **Customize the System**.</span></span>

1. <span data-ttu-id="66ffc-144">Vyhľadajte entitu **Kontakt**, rozbaľte ju a potom vyberte položku **Formuláre**.</span><span class="sxs-lookup"><span data-stu-id="66ffc-144">Browse to the **Contact** entity, expand it and select **Forms**.</span></span>

1. <span data-ttu-id="66ffc-145">Vyberte formulár kontaktu, do ktorého chcete pridať ovládacie prvky Karty zákazníka.</span><span class="sxs-lookup"><span data-stu-id="66ffc-145">Select the contact form to which you want to add the Customer Card controls.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="66ffc-146">![Výber formulára kontaktu](media/contact-active-forms.png "Výber formulára kontaktu")</span><span class="sxs-lookup"><span data-stu-id="66ffc-146">![Select Contact form](media/contact-active-forms.png "Select Contact form")</span></span>

1. <span data-ttu-id="66ffc-147">Ak chcete pridať ovládací prvok, v editore formulárov presuňte ľubovoľné pole z **Prieskumníka polí** na miesto, kde sa má zobraziť ovládací prvok.</span><span class="sxs-lookup"><span data-stu-id="66ffc-147">To add a control, in the form editor, drag any field from the **Field Explorer** to where you want the control to appear.</span></span>

1. <span data-ttu-id="66ffc-148">Vyberte pole vo formulári, ktoré ste práve pridali, a potom položku **Zmeniť vlastnosti**.</span><span class="sxs-lookup"><span data-stu-id="66ffc-148">Select the field on the form that you just added, and select **Change Properties**.</span></span>

1. <span data-ttu-id="66ffc-149">Prejdite na kartu **Ovládacie prvky** a vyberte položku **Pridať ovládací prvok**.</span><span class="sxs-lookup"><span data-stu-id="66ffc-149">Go to the **Controls** tab and select **Add Control**.</span></span> <span data-ttu-id="66ffc-150">Vyberte jeden z dostupných vlastných ovládacích prvkov a potom položku **Pridať**.</span><span class="sxs-lookup"><span data-stu-id="66ffc-150">Choose one of the available custom controls and select **Add**.</span></span>

1. <span data-ttu-id="66ffc-151">V dialógovom okne **Vlastnosti poľa** zrušte začiarknutie políčka **Zobraziť menovku vo formulári**.</span><span class="sxs-lookup"><span data-stu-id="66ffc-151">In the **Field Properties** dialog, clear the **Display label on the form** check box.</span></span>

1. <span data-ttu-id="66ffc-152">Vyberte možnosť **Web** pre ovládací prvok.</span><span class="sxs-lookup"><span data-stu-id="66ffc-152">Select the **Web** option for the control.</span></span> <span data-ttu-id="66ffc-153">Pre kontrolu obohatenia vyberte typ obohatenia, ktorý chcete zobraziť, nakonfigurovaním poľa **enrichmentType**.</span><span class="sxs-lookup"><span data-stu-id="66ffc-153">For the Enrichment control, select which enrichment type you want to display by configuring the **enrichmentType** field.</span></span> <span data-ttu-id="66ffc-154">Pre každý typ obohatenia pridajte samostatnú kontrolu obohatenia.</span><span class="sxs-lookup"><span data-stu-id="66ffc-154">Add a separate enrichment control for each enrichment type.</span></span>

1. <span data-ttu-id="66ffc-155">Výberom **Uložiť** a **Publikovať** zverejnite aktualizovaný kontaktný formulár.</span><span class="sxs-lookup"><span data-stu-id="66ffc-155">Select **Save** and **Publish** to publish the updated contact form.</span></span>

1. <span data-ttu-id="66ffc-156">Prejdite na publikovaný kontaktný formulár.</span><span class="sxs-lookup"><span data-stu-id="66ffc-156">Go to the published contact form.</span></span> <span data-ttu-id="66ffc-157">Uvidíte novo pridaný ovládací prvok.</span><span class="sxs-lookup"><span data-stu-id="66ffc-157">You'll see the newly added control.</span></span> <span data-ttu-id="66ffc-158">Možno sa budete musieť prihlásiť pri prvom použití.</span><span class="sxs-lookup"><span data-stu-id="66ffc-158">You might need to sign in the first time you use it.</span></span>

1. <span data-ttu-id="66ffc-159">Ak chcete prispôsobiť, čo chcete zobraziť vo vlastnom ovládacom prvku, vyberte tlačidlo Upraviť v pravom hornom rohu.</span><span class="sxs-lookup"><span data-stu-id="66ffc-159">To customize what you want to show on the custom control, select the edit button in the upper-right corner.</span></span>

## <a name="upgrade-customer-card-add-in"></a><span data-ttu-id="66ffc-160">Aktualizácia doplnku Karta zákazníka</span><span class="sxs-lookup"><span data-stu-id="66ffc-160">Upgrade Customer Card Add-in</span></span>
<span data-ttu-id="66ffc-161">Doplnok Karta zákazníka sa neaktualizuje automaticky.</span><span class="sxs-lookup"><span data-stu-id="66ffc-161">The Customer Card Add-in doesn't upgrade automatically.</span></span> <span data-ttu-id="66ffc-162">Pri inovácii na najnovšiu verziu postupujte podľa tohto postupu v aplikácii Dynamics 365, ktorá má nainštalovaný doplnok.</span><span class="sxs-lookup"><span data-stu-id="66ffc-162">To upgrade to the latest version, follow this procedure in the Dynamics 365 app that has the Add-in installed.</span></span>

1. <span data-ttu-id="66ffc-163">V aplikácii Dynamics 365 prejdite na **Nastavenia** > **Prispôsobenie** a vyberte **Riešenia**.</span><span class="sxs-lookup"><span data-stu-id="66ffc-163">In the Dynamics 365 app, go to **Settings** > **Customization** and select **Solutions**.</span></span>

1. <span data-ttu-id="66ffc-164">V tabuľke doplnkov hľadajte **CustomerInsightsCustomerCard** a vyberte riadok.</span><span class="sxs-lookup"><span data-stu-id="66ffc-164">In the table of add-ins look for **CustomerInsightsCustomerCard** and select the row.</span></span>

1. <span data-ttu-id="66ffc-165">Vyberte **Aplikovať inováciu riešenia** v lište akcií.</span><span class="sxs-lookup"><span data-stu-id="66ffc-165">Select the **Apply Solution Upgrade** in the action bar.</span></span>

   :::image type="content" source="media/customer-card-add-in-upgrade.png" alt-text="Inovujte riešenie v oblasti Prispôsobenie aplikácií Dynamics 365":::

1. <span data-ttu-id="66ffc-167">Po spustení procesu inovácie sa vám bude zobrazovať indikátor načítania, kým sa aktualizácia nedokončí.</span><span class="sxs-lookup"><span data-stu-id="66ffc-167">After starting the upgrade process, you'll see a loading indicator until the upgrade completes.</span></span> <span data-ttu-id="66ffc-168">Ak nie je k dispozícii novšia verzia, pri inovácii sa zobrazí chybové hlásenie.</span><span class="sxs-lookup"><span data-stu-id="66ffc-168">If there's no newer version, the upgrade will show an error message.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
