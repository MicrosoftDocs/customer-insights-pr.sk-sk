---
title: Export údajov služby Customer Insights do DotDigital
description: Zistite ako nakonfigurovať pripojenie a realizovať exportovanie do DotDigital.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 235bcdfa4a7c4c1a382778bd4f66c1a9f5b7beb1
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 03/31/2021
ms.locfileid: "5759978"
---
# <a name="export-segment-lists-to-dotdigital-preview"></a><span data-ttu-id="fb13b-103">Exportovanie zoznamov segmentov do DotDigital (ukážka)</span><span class="sxs-lookup"><span data-stu-id="fb13b-103">Export segment lists to DotDigital (preview)</span></span>

<span data-ttu-id="fb13b-104">Exportujte segmenty zjednotených profilov zákazníkov do adresárov DotDigital a použite ich na kampane, e-mailový marketing a na vytváranie segmentov zákazníkov cez DotDigital.</span><span class="sxs-lookup"><span data-stu-id="fb13b-104">Export segments of unified customer profiles to DotDigital address books and use them for campaigns, email marketing, and to build customer segments with DotDigital.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="fb13b-105">Predpoklad na pripojenie</span><span class="sxs-lookup"><span data-stu-id="fb13b-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="fb13b-106">Máte [účet DotDigital](https://dotdigital.com/) a zodpovedajúce poverenia správcu.</span><span class="sxs-lookup"><span data-stu-id="fb13b-106">You have a [DotDigital account](https://dotdigital.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="fb13b-107">V DotDigital a zodpovedajúcich ID existujú adresáre.</span><span class="sxs-lookup"><span data-stu-id="fb13b-107">There are existing address books in DotDigital and the corresponding IDs.</span></span> <span data-ttu-id="fb13b-108">ID nájdete v adrese URL, keď vyberiete a otvoríte adresár.</span><span class="sxs-lookup"><span data-stu-id="fb13b-108">The ID can be found in the URL when you select and open an address book.</span></span> <span data-ttu-id="fb13b-109">Ďalšie informácie nájdete v [adresároch DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span><span class="sxs-lookup"><span data-stu-id="fb13b-109">For more information, see [DotDigital address books](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span></span>
-   <span data-ttu-id="fb13b-110">Máte [konfigurované segmenty](segments.md) v prehľadoch cieľových skupín.</span><span class="sxs-lookup"><span data-stu-id="fb13b-110">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="fb13b-111">Zjednotené profily zákazníkov v exportovaných segmentoch obsahujú pole predstavujúce e-mailovú adresu.</span><span class="sxs-lookup"><span data-stu-id="fb13b-111">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="fb13b-112">Známe obmedzenia</span><span class="sxs-lookup"><span data-stu-id="fb13b-112">Known limitations</span></span>

- <span data-ttu-id="fb13b-113">Až 1 milión profilov na export do DotDigital.</span><span class="sxs-lookup"><span data-stu-id="fb13b-113">Up to 1 million profiles per export to DotDigital.</span></span>
- <span data-ttu-id="fb13b-114">Export do DotDigital je obmedzený na segmenty.</span><span class="sxs-lookup"><span data-stu-id="fb13b-114">Exporting to DotDigital is limited to segments.</span></span>
- <span data-ttu-id="fb13b-115">Export segmentov s celkovým počtom 1 miliónov profilov môže trvať až 3 hodiny z dôvodu obmedzení na strane poskytovateľa.</span><span class="sxs-lookup"><span data-stu-id="fb13b-115">Exporting segments with a total of 1 million profiles can take up to 3 hours because of limitations on the provider side.</span></span> 
- <span data-ttu-id="fb13b-116">Počet profilov, ktoré môžete exportovať do DotDigital, závisí a je obmedzený vašou zmluvou so spoločnosťou DotDigital.</span><span class="sxs-lookup"><span data-stu-id="fb13b-116">The number of profiles that you can export to DotDigital is dependent and limited on your contract with DotDigital.</span></span>

## <a name="set-up-connection-to-dotdigital"></a><span data-ttu-id="fb13b-117">Nastavenie pripojenia k DotDigital</span><span class="sxs-lookup"><span data-stu-id="fb13b-117">Set up connection to DotDigital</span></span>

1. <span data-ttu-id="fb13b-118">Prejdite do časti **Správca** > **Pripojenia**.</span><span class="sxs-lookup"><span data-stu-id="fb13b-118">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="fb13b-119">Stlačte možnosť **Pridať pripojenie** a stlačením možnosti **DotDigital** nakonfigurujte pripojenie.</span><span class="sxs-lookup"><span data-stu-id="fb13b-119">Select **Add connection** and choose **DotDigital** to configure the connection.</span></span>

1. <span data-ttu-id="fb13b-120">Do poľa **Zobrazovaný názov** zadajte rozpoznateľný názov pripojenia.</span><span class="sxs-lookup"><span data-stu-id="fb13b-120">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="fb13b-121">Zobrazovaný názov a typ spojenia, ktoré popisuje toto spojenie.</span><span class="sxs-lookup"><span data-stu-id="fb13b-121">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="fb13b-122">Odporúčame zvoliť názov, ktorý vysvetľuje účel a cieľ tohto spojenia.</span><span class="sxs-lookup"><span data-stu-id="fb13b-122">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="fb13b-123">Vyberte používateľov, ktorí môžu používať toto pripojenie.</span><span class="sxs-lookup"><span data-stu-id="fb13b-123">Choose who can use this connection.</span></span> <span data-ttu-id="fb13b-124">Ak neurobíte nič, predvolená hodnota bude Správcovia.</span><span class="sxs-lookup"><span data-stu-id="fb13b-124">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="fb13b-125">Viac informácií nájdete v časti [Umožnite prispievateľom použiť pripojenie na export](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="fb13b-125">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="fb13b-126">Zadajte **používateľské meno a heslo pre DotDigital**.</span><span class="sxs-lookup"><span data-stu-id="fb13b-126">Enter your **DotDigital username and password**.</span></span>

1. <span data-ttu-id="fb13b-127">Zadajte **[ID adresára DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**.</span><span class="sxs-lookup"><span data-stu-id="fb13b-127">Enter your **[DotDigital address book ID](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**.</span></span>

1. <span data-ttu-id="fb13b-128">Vyberte **Súhlasím** na potvrdenie **Ochrany osobných údajov a dodržiavanie súladu s nariadeniami**.</span><span class="sxs-lookup"><span data-stu-id="fb13b-128">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="fb13b-129">Vyberte položku **Pripojiť** na inicializáciu pripojenia k DotDigital.</span><span class="sxs-lookup"><span data-stu-id="fb13b-129">Select **Connect** to initialize the connection to DotDigital.</span></span>

1. <span data-ttu-id="fb13b-130">Vyberte položku **Pridať samého seba ako používateľa exportu** a uveďte svoje poverenia pre Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="fb13b-130">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="fb13b-131">Stlačte možnosť **Uložiť** a dokončite pripojenie.</span><span class="sxs-lookup"><span data-stu-id="fb13b-131">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="fb13b-132">Nakonfigurujte export</span><span class="sxs-lookup"><span data-stu-id="fb13b-132">Configure an export</span></span>

<span data-ttu-id="fb13b-133">Tento export môžete nakonfigurovať, ak máte prístup k pripojeniu tohto typu.</span><span class="sxs-lookup"><span data-stu-id="fb13b-133">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="fb13b-134">Viac informácií nájdete na stránke [Na konfiguráciu exportu sú potrebné povolenia](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="fb13b-134">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="fb13b-135">Prejdite na **Údaje** > **Exporty**.</span><span class="sxs-lookup"><span data-stu-id="fb13b-135">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="fb13b-136">Na vytvorenie nového exportu stlačte možnosť **Pridať cieľ**.</span><span class="sxs-lookup"><span data-stu-id="fb13b-136">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="fb13b-137">V poli **Pripojenie na export** vyberte pripojenie v časti DotDigital.</span><span class="sxs-lookup"><span data-stu-id="fb13b-137">In the **Connection for export** field, choose a connection from the DotDigital section.</span></span> <span data-ttu-id="fb13b-138">Ak nevidíte názov tejto sekcie, nemáte k dispozícii žiadne spojenia tohto typu.</span><span class="sxs-lookup"><span data-stu-id="fb13b-138">If you don't see this section name, there are no connections of this type available to you.</span></span>


1. <span data-ttu-id="fb13b-139">V sekcii **Párovanie údajov** v poli **E-mail** do svojho zjednoteného profilu zákazníka vyberte pole, ktoré predstavuje e-mailovú adresu zákazníka.</span><span class="sxs-lookup"><span data-stu-id="fb13b-139">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="fb13b-140">Rovnaký postup zopakujte pri ďalších voliteľných poliach, ako je **Krstné meno**, **Priezvisko**, **Celé meno**, **Rod** a **PSČ**.</span><span class="sxs-lookup"><span data-stu-id="fb13b-140">Repeat the same steps for other optional fields such as **First name**, **Last name**, **Full name**, **Gender**, and **Post code**.</span></span>

1. <span data-ttu-id="fb13b-141">Vyberte segmenty, ktoré chcete exportovať.</span><span class="sxs-lookup"><span data-stu-id="fb13b-141">Select the segments you want to export.</span></span> <span data-ttu-id="fb13b-142">Do DotDigital môžete exportovať spolu až 1 milión zákazníckych profilov.</span><span class="sxs-lookup"><span data-stu-id="fb13b-142">You can export up to 1 million customer profiles in total to DotDigital.</span></span>

1. <span data-ttu-id="fb13b-143">Vyberte položku **Uložiť**.</span><span class="sxs-lookup"><span data-stu-id="fb13b-143">Select **Save**.</span></span>

<span data-ttu-id="fb13b-144">Uloženie exportu nespustí export okamžite.</span><span class="sxs-lookup"><span data-stu-id="fb13b-144">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="fb13b-145">Export prebieha s každým [plánovaným obnovením](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="fb13b-145">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="fb13b-146">Môžete tiež [exportovať údaje na požiadanie](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="fb13b-146">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 
 
<span data-ttu-id="fb13b-147">V DotDigital teraz nájdete svoje segmenty v [adresároch DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span><span class="sxs-lookup"><span data-stu-id="fb13b-147">In DotDigital, you can now find your segments in [DotDigital address books](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span></span>


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="fb13b-148">Ochrana osobných údajov a dodržiavanie súladu s nariadeniami</span><span class="sxs-lookup"><span data-stu-id="fb13b-148">Data privacy and compliance</span></span>

<span data-ttu-id="fb13b-149">Keď povolíte prenos údajov spoločnosti DotDigital v službe Dynamics 365 Customer Insights, povoľujete tým prenos údajov mimo hranice súladu so službou Dynamics 365 Customer Insights vrátane potenciálne citlivých údajov, ako sú napríklad osobné údaje.</span><span class="sxs-lookup"><span data-stu-id="fb13b-149">When you enable Dynamics 365 Customer Insights to transmit data to DotDigital, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="fb13b-150">Spoločnosť Microsoft prenesie tieto údaje na váš pokyn, ale vy ste zodpovední za zabezpečenie toho, aby spoločnosť DotDigital plnila všetky prípadné povinnosti týkajúce sa ochrany vašich osobných údajov alebo zabezpečenia.</span><span class="sxs-lookup"><span data-stu-id="fb13b-150">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that DotDigital meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="fb13b-151">Ďalšie informácie nájdete vo [vyhlásení o ochrane súkromia spoločnosti Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="fb13b-151">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="fb13b-152">Váš správca služby Dynamics 365 Customer Insights môže túto funkciu kedykoľvek prestať používať odstránením tohto cieľového umiestnenia exportu.</span><span class="sxs-lookup"><span data-stu-id="fb13b-152">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
