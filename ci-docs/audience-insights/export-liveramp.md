---
title: Konektor LiveRamp
description: Naučte sa, ako exportovať údaje do riešenia LiveRamp.
ms.date: 12/02/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 6ef4388b0e8ba8bc5866807765d8a872d41c9c14
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597576"
---
# <a name="liverampreg-connector-preview"></a><span data-ttu-id="f10dd-103">Konektor LiveRamp&reg; (ukážka)</span><span class="sxs-lookup"><span data-stu-id="f10dd-103">LiveRamp&reg; connector (preview)</span></span>

<span data-ttu-id="f10dd-104">Aktivujte svoje údaje v riešení LiveRamp a spojte sa s viac ako 500 platformami naprieč digitálnymi, sociálnymi a televíznymi ekosystémami.</span><span class="sxs-lookup"><span data-stu-id="f10dd-104">Activate your data in LiveRamp to connect with over 500 platforms across digital, social, and TV ecosystems.</span></span> <span data-ttu-id="f10dd-105">Spolupracujte s vašimi údajmi v riešení LiveRamp na zacielení, potlačení a prispôsobení reklamných kampaní.</span><span class="sxs-lookup"><span data-stu-id="f10dd-105">Work with your data in LiveRamp to target, suppress, and personalize ad campaigns.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="f10dd-106">Predpoklady</span><span class="sxs-lookup"><span data-stu-id="f10dd-106">Prerequisites</span></span>

- <span data-ttu-id="f10dd-107">Na používanie tohto konektora potrebujete predplatné LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="f10dd-107">You need a LiveRamp subscription to use this connector.</span></span>
- <span data-ttu-id="f10dd-108">Ak chcete získať predplatné, [kontaktujte LiveRamp](https://liveramp.com/contact/) priamo.</span><span class="sxs-lookup"><span data-stu-id="f10dd-108">To get a subscription, [contact LiveRamp](https://liveramp.com/contact/) directly.</span></span> <span data-ttu-id="f10dd-109">[Získajte viac informácií o zaradení riešenia LiveRamp](https://liveramp.com/our-platform/data-onboarding/).</span><span class="sxs-lookup"><span data-stu-id="f10dd-109">[Learn more about LiveRamp Onboarding](https://liveramp.com/our-platform/data-onboarding/).</span></span>

## <a name="connect-to-liveramp"></a><span data-ttu-id="f10dd-110">Pripojenie k riešeniu LiveRamp</span><span class="sxs-lookup"><span data-stu-id="f10dd-110">Connect to LiveRamp</span></span>

1. <span data-ttu-id="f10dd-111">V prehľadoch cieľových skupín prejdite na **Správca** > **Ciele exportu**.</span><span class="sxs-lookup"><span data-stu-id="f10dd-111">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="f10dd-112">Na dlaždici **LiveRamp** vyberte položku **Nastaviť**.</span><span class="sxs-lookup"><span data-stu-id="f10dd-112">In the **LiveRamp** tile, select **Set up**.</span></span>

1. <span data-ttu-id="f10dd-113">Do poľa **Zobrazovaný názov** zadajte rozpoznateľný názov cieľa.</span><span class="sxs-lookup"><span data-stu-id="f10dd-113">Give your destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="f10dd-114">Zadajte **používateľské meno** a **heslo** pre vaše konto LiveRamp Secure FTP (SFTP).</span><span class="sxs-lookup"><span data-stu-id="f10dd-114">Provide a **Username** and **Password** for your LiveRamp Secure FTP (SFTP) account.</span></span>
<span data-ttu-id="f10dd-115">Tieto poverenia sa môžu líšiť od vašich poverení pre LiveRamp Onboarding.</span><span class="sxs-lookup"><span data-stu-id="f10dd-115">These credentials may be different from your LiveRamp Onboarding credentials.</span></span>

1. <span data-ttu-id="f10dd-116">Vyberte **Overiť** na testovanie pripojenia k riešeniu LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="f10dd-116">Select **Verify** to test the connection to LiveRamp.</span></span>

1. <span data-ttu-id="f10dd-117">Po úspešnom overení poskytnite svoj súhlas pre **Ochranu osobných údajov a dodržiavanie súladu s nariadeniami** výberom začiarkavacieho políčka **Súhlasím**.</span><span class="sxs-lookup"><span data-stu-id="f10dd-117">After successful verification, provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span>

1. <span data-ttu-id="f10dd-118">Vyberte **Ďalej** na nastavenie konektora LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="f10dd-118">Select **Next** to set up the LiveRamp connector.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="f10dd-119">Nakonfigurujte konektor</span><span class="sxs-lookup"><span data-stu-id="f10dd-119">Configure the connector</span></span>

1. <span data-ttu-id="f10dd-120">V poli **Vyberte identifikátor kľúča** vyberte **E-mail**, **Meno a adresu** alebo **Telefón** na odoslanie do riešenia LiveRamp na rozlíšenie identity.</span><span class="sxs-lookup"><span data-stu-id="f10dd-120">In the **Choose your key identifier** field, select **Email**,  **Name and address**, or **Phone** to send to LiveRamp for identity resolution.</span></span>

1. <span data-ttu-id="f10dd-121">Priraďte zodpovedajúce atribúty z vašej zjednotenej entity zákazníka na vybratý identifikátor kľúča.</span><span class="sxs-lookup"><span data-stu-id="f10dd-121">Map the corresponding attributes from your unified customer entity for the selected key identifier.</span></span>

1. <span data-ttu-id="f10dd-122">Vyberte **Pridať atribút** na priradenie ďalších atribútov na odoslanie do LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="f10dd-122">Select **Add attribute** to map additional attributes to send to LiveRamp.</span></span>

   > [!TIP]
   > <span data-ttu-id="f10dd-123">Poslaním ďalších atribútov kľúčového identifikátora do riešenia LiveRamp pravdepodobne získate vyššiu mieru zhody.</span><span class="sxs-lookup"><span data-stu-id="f10dd-123">Sending more key identifier attributes to LiveRamp is likely to get you a higher match rate.</span></span>

1. <span data-ttu-id="f10dd-124">Vyberte segmenty, ktoré chcete exportovať do LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="f10dd-124">Select the segments you want to export to LiveRamp.</span></span>

1. <span data-ttu-id="f10dd-125">Vyberte položku **Uložiť**.</span><span class="sxs-lookup"><span data-stu-id="f10dd-125">Select **Save**.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="f10dd-126">![Konektor LiveRamp s priradením atribútov](media/export-liveramp-segments.png "Konektor LiveRamp s priradením atribútov")</span><span class="sxs-lookup"><span data-stu-id="f10dd-126">![LiveRamp connector with attribute mapping](media/export-liveramp-segments.png "LiveRamp connector with attribute mapping")</span></span>

## <a name="export-the-data"></a><span data-ttu-id="f10dd-127">Export údajov</span><span class="sxs-lookup"><span data-stu-id="f10dd-127">Export the data</span></span>

<span data-ttu-id="f10dd-128">Export sa začne čoskoro, ak budú splnené všetky predpoklady na export.</span><span class="sxs-lookup"><span data-stu-id="f10dd-128">The export will start shortly if all prerequisites for export have been completed.</span></span> <span data-ttu-id="f10dd-129">Export sa spustí aj pri každej [plánovanej obnove](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="f10dd-129">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>
<span data-ttu-id="f10dd-130">Po úspešnom dokončení exportu sa môžete prihlásiť do riešenia LiveRamp Onboarding a aktivovať a distribuovať svoje údaje.</span><span class="sxs-lookup"><span data-stu-id="f10dd-130">Once the export is successfully completed, you can sign in to LiveRamp Onboarding to activate and distribute your data.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="f10dd-131">Ochrana osobných údajov a dodržiavanie súladu s nariadeniami</span><span class="sxs-lookup"><span data-stu-id="f10dd-131">Data privacy and compliance</span></span>

<span data-ttu-id="f10dd-132">Keď povolíte prenos údajov spoločnosti Liveramp v službe Dynamics 365 Customer Insights, povoľujete tým prenos údajov mimo hranice súladu so službou Dynamics 365 Customer Insights vrátane potenciálne citlivých údajov, ako sú napríklad osobné údaje.</span><span class="sxs-lookup"><span data-stu-id="f10dd-132">When you enable Dynamics 365 Customer Insights to transmit data to Liveramp, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="f10dd-133">Spoločnosť Microsoft prenesie tieto údaje na váš pokyn, ale vy ste zodpovední za zabezpečenie toho, aby spoločnosť Liveramp plnila všetky prípadné povinnosti týkajúce sa ochrany vašich osobných údajov alebo zabezpečenia.</span><span class="sxs-lookup"><span data-stu-id="f10dd-133">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Liveramp meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="f10dd-134">Ďalšie informácie nájdete vo [vyhlásení o ochrane súkromia spoločnosti Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="f10dd-134">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="f10dd-135">Váš správca služby Dynamics 365 Customer Insights môže túto funkciu kedykoľvek prestať používať odstránením tohto cieľového umiestnenia exportu.</span><span class="sxs-lookup"><span data-stu-id="f10dd-135">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]