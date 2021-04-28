---
title: Konektor LiveRamp
description: Zistite ako nakonfigurovať pripojenie a realizovať exportovanie do LiveRamp.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 987457966fe1fc034d9e3cd2a1ce33902c7a84f4
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760346"
---
# <a name="export-segments-to-liverampreg-preview"></a><span data-ttu-id="0d1c5-103">Export segmentov do LiveRamp&reg; (ukážka)</span><span class="sxs-lookup"><span data-stu-id="0d1c5-103">Export segments to LiveRamp&reg; (preview)</span></span>

<span data-ttu-id="0d1c5-104">Aktivujte svoje údaje v službe LiveRamp a spojte sa s viac ako 500 platformami v digitálnych, sociálnych a televíznych zariadeniach.</span><span class="sxs-lookup"><span data-stu-id="0d1c5-104">Activate your data in LiveRamp to connect with over 500 platforms across digital, social, and TVs.</span></span> <span data-ttu-id="0d1c5-105">Spolupracujte s vašimi údajmi v riešení LiveRamp na zacielení, potlačení a prispôsobení reklamných kampaní.</span><span class="sxs-lookup"><span data-stu-id="0d1c5-105">Work with your data in LiveRamp to target, suppress, and personalize ad campaigns.</span></span>

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="0d1c5-106">Predpoklad na pripojenie</span><span class="sxs-lookup"><span data-stu-id="0d1c5-106">Prerequisites for a connection</span></span>

- <span data-ttu-id="0d1c5-107">Na používanie tohto konektora potrebujete predplatné LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="0d1c5-107">You need a LiveRamp subscription to use this connector.</span></span>
- <span data-ttu-id="0d1c5-108">Ak chcete získať predplatné, [kontaktujte LiveRamp](https://liveramp.com/contact/) priamo.</span><span class="sxs-lookup"><span data-stu-id="0d1c5-108">To get a subscription, [contact LiveRamp](https://liveramp.com/contact/) directly.</span></span> <span data-ttu-id="0d1c5-109">[Získajte viac informácií o zaradení riešenia LiveRamp](https://liveramp.com/our-platform/data-onboarding/).</span><span class="sxs-lookup"><span data-stu-id="0d1c5-109">[Learn more about LiveRamp Onboarding](https://liveramp.com/our-platform/data-onboarding/).</span></span>

## <a name="set-up-connection-to-liveramp"></a><span data-ttu-id="0d1c5-110">Nastavenie pripojenia k LiveRamp</span><span class="sxs-lookup"><span data-stu-id="0d1c5-110">Set up connection to LiveRamp</span></span>

1. <span data-ttu-id="0d1c5-111">Prejdite do časti **Správca** > **Pripojenia**.</span><span class="sxs-lookup"><span data-stu-id="0d1c5-111">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="0d1c5-112">Stlačte možnosť **Pridať pripojenie** a stlačením možnosti **LiveRamp** nakonfigurujte pripojenie.</span><span class="sxs-lookup"><span data-stu-id="0d1c5-112">Select **Add connection** and choose **LiveRamp** to configure the connection.</span></span>

1. <span data-ttu-id="0d1c5-113">Do poľa **Zobrazovaný názov** zadajte rozpoznateľný názov pripojenia.</span><span class="sxs-lookup"><span data-stu-id="0d1c5-113">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="0d1c5-114">Zobrazovaný názov a typ spojenia, ktoré popisuje toto spojenie.</span><span class="sxs-lookup"><span data-stu-id="0d1c5-114">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="0d1c5-115">Odporúčame zvoliť názov, ktorý vysvetľuje účel a cieľ tohto spojenia.</span><span class="sxs-lookup"><span data-stu-id="0d1c5-115">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="0d1c5-116">Vyberte používateľov, ktorí môžu používať toto pripojenie.</span><span class="sxs-lookup"><span data-stu-id="0d1c5-116">Choose who can use this connection.</span></span> <span data-ttu-id="0d1c5-117">Ak neurobíte nič, predvolená hodnota bude Správcovia.</span><span class="sxs-lookup"><span data-stu-id="0d1c5-117">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="0d1c5-118">Viac informácií nájdete v časti [Umožnite prispievateľom použiť pripojenie na export](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="0d1c5-118">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="0d1c5-119">Zadajte **používateľské meno** a **heslo** pre vaše konto LiveRamp Secure FTP (SFTP).</span><span class="sxs-lookup"><span data-stu-id="0d1c5-119">Provide a **Username** and **Password** for your LiveRamp Secure FTP (SFTP) account.</span></span>
<span data-ttu-id="0d1c5-120">Tieto poverenia sa môžu líšiť od vašich poverení pre LiveRamp Onboarding.</span><span class="sxs-lookup"><span data-stu-id="0d1c5-120">These credentials may be different from your LiveRamp Onboarding credentials.</span></span>

1. <span data-ttu-id="0d1c5-121">Vyberte **Overiť** na testovanie pripojenia k riešeniu LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="0d1c5-121">Select **Verify** to test the connection to LiveRamp.</span></span>

1. <span data-ttu-id="0d1c5-122">Po úspešnom overení poskytnite svoj súhlas pre **Ochranu osobných údajov a dodržiavanie súladu s nariadeniami** výberom začiarkavacieho políčka **Súhlasím**.</span><span class="sxs-lookup"><span data-stu-id="0d1c5-122">After successful verification, provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span>

1. <span data-ttu-id="0d1c5-123">Stlačte možnosť **Uložiť** a dokončite pripojenie.</span><span class="sxs-lookup"><span data-stu-id="0d1c5-123">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="0d1c5-124">Nakonfigurujte export</span><span class="sxs-lookup"><span data-stu-id="0d1c5-124">Configure an export</span></span>

<span data-ttu-id="0d1c5-125">Tento export môžete nakonfigurovať, ak máte prístup k pripojeniu tohto typu.</span><span class="sxs-lookup"><span data-stu-id="0d1c5-125">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="0d1c5-126">Viac informácií nájdete na stránke [Na konfiguráciu exportu sú potrebné povolenia](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="0d1c5-126">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="0d1c5-127">Prejdite na **Údaje** > **Exporty**.</span><span class="sxs-lookup"><span data-stu-id="0d1c5-127">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="0d1c5-128">Na vytvorenie nového exportu stlačte možnosť **Pridať cieľ**.</span><span class="sxs-lookup"><span data-stu-id="0d1c5-128">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="0d1c5-129">V poli **Pripojenie na export** vyberte pripojenie v časti LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="0d1c5-129">In the **Connection for export** field, choose a connection from the LiveRamp section.</span></span> <span data-ttu-id="0d1c5-130">Ak nevidíte názov tejto sekcie, nemáte k dispozícii žiadne spojenia tohto typu.</span><span class="sxs-lookup"><span data-stu-id="0d1c5-130">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="0d1c5-131">V poli **Vyberte identifikátor kľúča** vyberte **E-mail**, **Meno a adresu** alebo **Telefón** na odoslanie do riešenia LiveRamp na rozlíšenie identity.</span><span class="sxs-lookup"><span data-stu-id="0d1c5-131">In the **Choose your key identifier** field, select **Email**,  **Name and address**, or **Phone** to send to LiveRamp for identity resolution.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="0d1c5-132">![Konektor LiveRamp s priradením atribútov](media/export-liveramp-segments.png "Konektor LiveRamp s priradením atribútov")</span><span class="sxs-lookup"><span data-stu-id="0d1c5-132">![LiveRamp connector with attribute mapping](media/export-liveramp-segments.png "LiveRamp connector with attribute mapping")</span></span>

1. <span data-ttu-id="0d1c5-133">Priraďte zodpovedajúce atribúty z vašej zjednotenej entity zákazníka na vybratý identifikátor kľúča.</span><span class="sxs-lookup"><span data-stu-id="0d1c5-133">Map the corresponding attributes from your unified customer entity for the selected key identifier.</span></span>

1. <span data-ttu-id="0d1c5-134">Vyberte **Pridať atribút** na mapovanie ďalších atribútov na odoslanie do LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="0d1c5-134">Select **Add attribute** to map more attributes to send to LiveRamp.</span></span>

   > [!TIP]
   > <span data-ttu-id="0d1c5-135">Poslaním ďalších atribútov kľúčového identifikátora do riešenia LiveRamp pravdepodobne získate vyššiu mieru zhody.</span><span class="sxs-lookup"><span data-stu-id="0d1c5-135">Sending more key identifier attributes to LiveRamp is likely to get you a higher match rate.</span></span>

1. <span data-ttu-id="0d1c5-136">Vyberte segmenty, ktoré chcete exportovať do LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="0d1c5-136">Select the segments you want to export to LiveRamp.</span></span>

1. <span data-ttu-id="0d1c5-137">Vyberte položku **Uložiť**.</span><span class="sxs-lookup"><span data-stu-id="0d1c5-137">Select **Save**.</span></span>

<span data-ttu-id="0d1c5-138">Uloženie exportu nespustí export okamžite.</span><span class="sxs-lookup"><span data-stu-id="0d1c5-138">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="0d1c5-139">Export prebieha s každým [plánovaným obnovením](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="0d1c5-139">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="0d1c5-140">Môžete tiež [exportovať údaje na požiadanie](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="0d1c5-140">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="0d1c5-141">Ochrana osobných údajov a dodržiavanie súladu s nariadeniami</span><span class="sxs-lookup"><span data-stu-id="0d1c5-141">Data privacy and compliance</span></span>

<span data-ttu-id="0d1c5-142">Keď povolíte prenos údajov spoločnosti Liveramp v službe Dynamics 365 Customer Insights, povoľujete tým prenos údajov mimo hranice súladu so službou Dynamics 365 Customer Insights vrátane potenciálne citlivých údajov, ako sú napríklad osobné údaje.</span><span class="sxs-lookup"><span data-stu-id="0d1c5-142">When you enable Dynamics 365 Customer Insights to transmit data to Liveramp, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="0d1c5-143">Spoločnosť Microsoft prenesie tieto údaje na váš pokyn, ale vy ste zodpovední za zabezpečenie toho, aby spoločnosť Liveramp plnila všetky prípadné povinnosti týkajúce sa ochrany vašich osobných údajov alebo zabezpečenia.</span><span class="sxs-lookup"><span data-stu-id="0d1c5-143">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Liveramp meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="0d1c5-144">Ďalšie informácie nájdete vo [vyhlásení o ochrane súkromia spoločnosti Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="0d1c5-144">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="0d1c5-145">Váš správca služby Dynamics 365 Customer Insights môže túto funkciu kedykoľvek prestať používať odstránením tohto cieľového umiestnenia exportu.</span><span class="sxs-lookup"><span data-stu-id="0d1c5-145">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
