---
title: Export údajov služby Customer Insights do hostiteľov protokolu SFTP
description: Prečítajte si, ako nakonfigurovať pripojenie k hostiteľovi SFTP.
ms.date: 06/05/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: c2529744d7a26a06324b79cad6a8001d75903545
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643522"
---
# <a name="connector-for-sftp-preview"></a><span data-ttu-id="4b4f9-103">Konektor pre SFTP (ukážka)</span><span class="sxs-lookup"><span data-stu-id="4b4f9-103">Connector for SFTP (preview)</span></span>

<span data-ttu-id="4b4f9-104">Používajte svoje zákaznícke údaje v aplikáciách tretích strán tak, že ich bezpečne exportujete do hostiteľa protokolu SFTP (Secure File Transfer Protocol).</span><span class="sxs-lookup"><span data-stu-id="4b4f9-104">Use your customer data in third-party applications by exporting them to a Secure File Transfer Protocol(SFTP) host.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="4b4f9-105">Predpoklady</span><span class="sxs-lookup"><span data-stu-id="4b4f9-105">Prerequisites</span></span>

- <span data-ttu-id="4b4f9-106">Dostupnosť hostiteľa SFTP a zodpovedajúce poverenia.</span><span class="sxs-lookup"><span data-stu-id="4b4f9-106">Availability of a SFTP host and corresponding credentials.</span></span>

## <a name="connect-to-sftp"></a><span data-ttu-id="4b4f9-107">Pripojenie k SFTP</span><span class="sxs-lookup"><span data-stu-id="4b4f9-107">Connect to SFTP</span></span>

1. <span data-ttu-id="4b4f9-108">Prejdite do ponuky **Správca** > **Ciele exportu**.</span><span class="sxs-lookup"><span data-stu-id="4b4f9-108">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="4b4f9-109">Pod **SFTP** vyberte **Nastavenie**.</span><span class="sxs-lookup"><span data-stu-id="4b4f9-109">Under **SFTP**, select **Set up**.</span></span>

1. <span data-ttu-id="4b4f9-110">Do poľa **Zobrazovaný názov** zadajte rozpoznateľný názov cieľa.</span><span class="sxs-lookup"><span data-stu-id="4b4f9-110">Give your destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="4b4f9-111">Uveďte **Používateľské meno**, **Heslo** a **Meno hostiteľa** pre váš účet SFTP.</span><span class="sxs-lookup"><span data-stu-id="4b4f9-111">Provide a **Username**, **Password** and **Hostname** for your SFTP account.</span></span> <span data-ttu-id="4b4f9-112">Príklad: Ak je koreňovým priečinkom vášho servera SFTP /root/folder a chcete exportovať údaje do /root/folder/ci_export_destination_folder, hostiteľom by mal byť sftp://<server_address>/ci_export_destination_folder".</span><span class="sxs-lookup"><span data-stu-id="4b4f9-112">Example: If your SFTP server's root folder is /root/folder, and you would like the data to be exported to /root/folder/ci_export_destination_folder, the the host should be sftp://<server_address>/ci_export_destination_folder".</span></span>

1. <span data-ttu-id="4b4f9-113">Na otestovanie pripojenia vyberte **Overiť**.</span><span class="sxs-lookup"><span data-stu-id="4b4f9-113">Select **Verify** to test the connection.</span></span>

1. <span data-ttu-id="4b4f9-114">Po úspešnom overení vyberte, či chcete exportovať údaje **skomprimované** alebo **dekomprimované** a vyberte **oddeľovač poľa** pre exportované súbory.</span><span class="sxs-lookup"><span data-stu-id="4b4f9-114">After successful verification, choose if you want to export your data **Zipped** or **Unzipped**, and select the **field delimiter** for the exported files.</span></span>

1. <span data-ttu-id="4b4f9-115">Vyberte **Súhlasím** na potvrdenie **Ochrany osobných údajov a dodržiavanie súladu s nariadeniami**.</span><span class="sxs-lookup"><span data-stu-id="4b4f9-115">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="4b4f9-116">Vyberte **Ďalej** a začnite konfigurovať export.</span><span class="sxs-lookup"><span data-stu-id="4b4f9-116">Select **Next** to start configuring the export.</span></span>

## <a name="configure-the-connection"></a><span data-ttu-id="4b4f9-117">Konfigurácia pripojenia</span><span class="sxs-lookup"><span data-stu-id="4b4f9-117">Configure the connection</span></span>

1. <span data-ttu-id="4b4f9-118">Vyberte **atribúty zákazníka**, ktoré chcete exportovať.</span><span class="sxs-lookup"><span data-stu-id="4b4f9-118">Select the **customer attributes** you want to export.</span></span> <span data-ttu-id="4b4f9-119">Môžete exportovať jeden alebo viac atribútov.</span><span class="sxs-lookup"><span data-stu-id="4b4f9-119">You can export one or multiple attributes.</span></span>

1. <span data-ttu-id="4b4f9-120">Vyberte **Ďalej**.</span><span class="sxs-lookup"><span data-stu-id="4b4f9-120">Select **Next**.</span></span>

1. <span data-ttu-id="4b4f9-121">Vyberte segmenty, ktoré chcete exportovať.</span><span class="sxs-lookup"><span data-stu-id="4b4f9-121">Select the segments you want to export.</span></span>

1. <span data-ttu-id="4b4f9-122">Vyberte položku **Uložiť**.</span><span class="sxs-lookup"><span data-stu-id="4b4f9-122">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="4b4f9-123">Export údajov</span><span class="sxs-lookup"><span data-stu-id="4b4f9-123">Export the data</span></span>

<span data-ttu-id="4b4f9-124">Môžete [exportovať údaje na vyžiadanie](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="4b4f9-124">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="4b4f9-125">Export sa spustí aj pri každej [plánovanej obnove](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="4b4f9-125">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="4b4f9-126">Ochrana osobných údajov a dodržiavanie súladu s nariadeniami</span><span class="sxs-lookup"><span data-stu-id="4b4f9-126">Data privacy and compliance</span></span>

<span data-ttu-id="4b4f9-127">Keď povolíte prenos údajov spoločnosti SFTP v službe Dynamics 365 Customer Insights, povoľujete tým prenos údajov mimo hranice súladu so službou Dynamics 365 Customer Insights vrátane potenciálne citlivých údajov, ako sú napríklad osobné údaje.</span><span class="sxs-lookup"><span data-stu-id="4b4f9-127">When you enable Dynamics 365 Customer Insights to transmit data via SFTP, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="4b4f9-128">Spoločnosť Microsoft prenesie tieto údaje na váš pokyn, ale vy ste zodpovední za zabezpečenie toho, aby cieľ exportu plnil všetky prípadné povinnosti týkajúce sa ochrany vašich osobných údajov alebo zabezpečenia.</span><span class="sxs-lookup"><span data-stu-id="4b4f9-128">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that the export destination meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="4b4f9-129">Ďalšie informácie nájdete vo [vyhlásení o ochrane súkromia spoločnosti Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="4b4f9-129">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="4b4f9-130">Váš správca služby Dynamics 365 Customer Insights môže túto funkciu kedykoľvek prestať používať odstránením tohto cieľového umiestnenia exportu.</span><span class="sxs-lookup"><span data-stu-id="4b4f9-130">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
