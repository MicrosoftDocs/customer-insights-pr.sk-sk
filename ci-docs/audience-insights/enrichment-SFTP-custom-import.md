---
title: Obohatenie pomocou vlastného importu protokolu SFTP
description: Všeobecné informácie o obohatení pomocou vlastného importu protokolu SFTP.
ms.date: 11/18/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jdahl
ms.author: mhart
manager: shellyha
ms.openlocfilehash: f25dcc08d96d36507e47af0d7b184003ae095819
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269625"
---
# <a name="enrich-customer-profiles-with-custom-data-preview"></a><span data-ttu-id="bfe7d-103">Obohatenie profilov zákazníkov o vlastné údaje (ukážka)</span><span class="sxs-lookup"><span data-stu-id="bfe7d-103">Enrich customer profiles with custom data (preview)</span></span>

<span data-ttu-id="bfe7d-104">Vlastný import protokolu SFTP (Secure File Transfer Protocol) vám umožňuje importovať údaje, ktoré nemusia prechádzať procesom zjednotenia údajov.</span><span class="sxs-lookup"><span data-stu-id="bfe7d-104">Secure File Transfer Protocol(SFTP) custom import enables you to import data that doesn't have to go through the process of data unification.</span></span> <span data-ttu-id="bfe7d-105">Ide o flexibilný, bezpečný a ľahký spôsob, ako prenášať vaše údaje.</span><span class="sxs-lookup"><span data-stu-id="bfe7d-105">It's a flexible, secure, and easy way to bring in your data.</span></span> <span data-ttu-id="bfe7d-106">Vlastný import SFTP je možné použiť v kombinácii s [exportom protokolu SFTP](export-sftp.md), ktorý vám umožňuje exportovať údaje profilu zákazníka, ktoré sú potrebné na obohatenie.</span><span class="sxs-lookup"><span data-stu-id="bfe7d-106">SFTP custom import can be used in combination with [SFTP export](export-sftp.md) that lets you export the customer profile data that is needed for enrichment.</span></span> <span data-ttu-id="bfe7d-107">Údaje potom môžu byť spracované, obohatené a vlastný import protokolu SFTP je možné použiť na prenos obohatených údajov späť do funkcie prehľadov cieľových skupín v službe Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="bfe7d-107">The data can then be processed, enriched, and SFTP custom import can be used to bring the enriched data back to the audience insights capability of Dynamics 365 Customer Insights.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="bfe7d-108">Predpoklady</span><span class="sxs-lookup"><span data-stu-id="bfe7d-108">Prerequisites</span></span>

<span data-ttu-id="bfe7d-109">Ak chcete nakonfigurovať vlastný import protokolu SFTP, musíte splniť nasledujúce predpoklady:</span><span class="sxs-lookup"><span data-stu-id="bfe7d-109">To configure SFTP custom import, the following prerequisites must be met:</span></span>

- <span data-ttu-id="bfe7d-110">Máte používateľské poverenia (používateľské meno a heslo) pre umiestnenie protokolu SFTP, odkiaľ sa budú importovať údaje.</span><span class="sxs-lookup"><span data-stu-id="bfe7d-110">You have user credentials (user name and password) for the SFTP location where the data that is going to be imported from.</span></span>
- <span data-ttu-id="bfe7d-111">Máte adresu URL a číslo portu (zvyčajne 22) hostiteľa protokolu STFP.</span><span class="sxs-lookup"><span data-stu-id="bfe7d-111">You have the URL and port number (usually 22) for the STFP host.</span></span>
- <span data-ttu-id="bfe7d-112">Máte názov súboru a umiestnenie súboru, ktorý sa má importovať, na hostiteľovi protokolu SFTP.</span><span class="sxs-lookup"><span data-stu-id="bfe7d-112">You have the filename and location of the file to be imported on the SFTP host.</span></span>
- <span data-ttu-id="bfe7d-113">Existuje súbor *model.json*, ktorý určuje schému pre údaje, ktoré sa majú importovať.</span><span class="sxs-lookup"><span data-stu-id="bfe7d-113">There's a *model.json* file that specifies the schema for the data that are to be imported.</span></span> <span data-ttu-id="bfe7d-114">Tento súbor musí byť v rovnakom adresári ako súbor, ktorý sa má importovať.</span><span class="sxs-lookup"><span data-stu-id="bfe7d-114">This file must be in the same directory as the file to import.</span></span>
- <span data-ttu-id="bfe7d-115">Máte povolenie roly [Správca](permissions.md#administrator).</span><span class="sxs-lookup"><span data-stu-id="bfe7d-115">You have [Administrator](permissions.md#administrator) permission.</span></span>

## <a name="configuration"></a><span data-ttu-id="bfe7d-116">Konfigurácia</span><span class="sxs-lookup"><span data-stu-id="bfe7d-116">Configuration</span></span>

1. <span data-ttu-id="bfe7d-117">Prejdite na **Údaje** > **Obohatenie** a vyberte kartu **Objavovať**.</span><span class="sxs-lookup"><span data-stu-id="bfe7d-117">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="bfe7d-118">Na **dlažici vlastného importu protokolu SFTP** vyberte položku **Obohatiť moje údaje**.</span><span class="sxs-lookup"><span data-stu-id="bfe7d-118">On the **SFTP custom import tile**, select **Enrich my data**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="bfe7d-119">![Dlaždica vlastného importu protokolu SFTP](media/SFTP_Custom_Import_tile.png "Dlaždica vlastného importu protokolu SFTP")</span><span class="sxs-lookup"><span data-stu-id="bfe7d-119">![SFTP Custom Import tile](media/SFTP_Custom_Import_tile.png "SFTP Custom Import tile")</span></span>

1. <span data-ttu-id="bfe7d-120">Vyberte položku **Začíname** a zadajte poverenia a adresu servera SFTP.</span><span class="sxs-lookup"><span data-stu-id="bfe7d-120">Select **Get started** and provide the credentials and the address for the SFTP server.</span></span> <span data-ttu-id="bfe7d-121">Napríklad zadajte sftp://mysftpserver.com:22.</span><span class="sxs-lookup"><span data-stu-id="bfe7d-121">For example, sftp://mysftpserver.com:22.</span></span>

1. <span data-ttu-id="bfe7d-122">Zadajte názov súboru, ktorý obsahuje údaje, a postup k súboru na serveri SFTP, ak sa nenachádza v koreňovom priečinku.</span><span class="sxs-lookup"><span data-stu-id="bfe7d-122">Enter the name of the file that contains the data and path to the file on the SFTP server if it's not in the root folder.</span></span>

1. <span data-ttu-id="bfe7d-123">Všetky vstupy potvrďte výberom položky **Pripojiť k vlastnému importu**.</span><span class="sxs-lookup"><span data-stu-id="bfe7d-123">Confirm all inputs by selecting **Connect to Custom Import**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="bfe7d-124">![Rozbaľovacia ponuka konfigurácie vlastného importu protokolu SFTP](media/SFTP_Custom_Import_Configuration_flyout.png "Rozbaľovacia ponuka konfigurácie vlastného importu protokolu SFTP")</span><span class="sxs-lookup"><span data-stu-id="bfe7d-124">![SFTP Custom Import Configuration flyout](media/SFTP_Custom_Import_Configuration_flyout.png "SFTP Custom Import Configuration flyout")</span></span>

## <a name="defining-field-mappings"></a><span data-ttu-id="bfe7d-125">Definovanie mapovania polí</span><span class="sxs-lookup"><span data-stu-id="bfe7d-125">Defining field mappings</span></span> 

<span data-ttu-id="bfe7d-126">Adresár, ktorý obsahuje súbor, ktorý sa má importovať na server SFTP, musí obsahovať aj súbor *model.json*.</span><span class="sxs-lookup"><span data-stu-id="bfe7d-126">The directory that contains the file to be imported on the SFTP server must also contain a *model.json* file.</span></span> <span data-ttu-id="bfe7d-127">Tento súbor definuje schému, ktorá sa má použiť na importovanie údajov.</span><span class="sxs-lookup"><span data-stu-id="bfe7d-127">This file defines the schema to use for importing the data.</span></span> <span data-ttu-id="bfe7d-128">Schéma musí používať [Common Data Model](https://docs.microsoft.com/common-data-model/) na určenie mapovania polí.</span><span class="sxs-lookup"><span data-stu-id="bfe7d-128">The schema has to use [the Common Data Model](https://docs.microsoft.com/common-data-model/) to specify the field mapping.</span></span> <span data-ttu-id="bfe7d-129">Jednoduchá ukážka súboru model.json vyzerá takto:</span><span class="sxs-lookup"><span data-stu-id="bfe7d-129">A simple example of a model.json file looks like this:</span></span>

```
{
    "name": "EnrichmentFromMicrosoft",
    "description": "Model containing data enrichment",
    "entities": [
        {
            "name": "CustomImport",
            "attributes": [
                {
                    "name": "CustomerId",
                    "friendlyName": "Client id",
                    "dataType": "string"
                },
                {
                    "name": "PreferredCity",
                    "friendlyName": "Preferred City for vacation",
                    "dataType": "string"
                },
                {
                    "name": "PreferredTransportation",
                    "friendlyName": "Preferred transportation",
                    "dataType": "string"
                }
            ],
            "annotations": [
                {
                    "name": "c360:PrimaryKey",
                    "value": "CustomerId"
                }
            ]
        }
    ],
    "modifiedTime": "2020-01-02T12:00:00+08:00",
    "annotations": [
        {
            "name": "testAnnotation",
            "value": "testValue"
        }
    ]
}
```

## <a name="enrichment-results"></a><span data-ttu-id="bfe7d-130">Výsledky obohatenia</span><span class="sxs-lookup"><span data-stu-id="bfe7d-130">Enrichment results</span></span>

<span data-ttu-id="bfe7d-131">Proces obohatenia spustíte výberom položky **Spustiť** z panela príkazov.</span><span class="sxs-lookup"><span data-stu-id="bfe7d-131">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="bfe7d-132">Môžete tiež nechať systém, aby obohatenie spustil automaticky ako súčasť a [plánovaného obnovenia](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="bfe7d-132">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="bfe7d-133">Čas spracovania bude závisieť od množstva údajov, ktoré sa majú importovať, a od pripojenia k serveru SFTP.</span><span class="sxs-lookup"><span data-stu-id="bfe7d-133">The processing time will depend on the size of the data to be imported and the connection to the SFTP server.</span></span>

<span data-ttu-id="bfe7d-134">Po dokončení procesu obohacovania môžete svoje novo importované údaje o vlastnom obohacovaní skontrolovať v sekcii **Moje obohatenia**.</span><span class="sxs-lookup"><span data-stu-id="bfe7d-134">After the enrichment process completes, you can review your newly imported custom enrichment data under **My enrichments**.</span></span> <span data-ttu-id="bfe7d-135">Ďalej nájdete čas poslednej aktualizácie a počet obohatených profilov.</span><span class="sxs-lookup"><span data-stu-id="bfe7d-135">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="bfe7d-136">Môžete získať podrobné zobrazenie každého obohateného profilu výberom **Zobraziť obohatené údaje**.</span><span class="sxs-lookup"><span data-stu-id="bfe7d-136">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="bfe7d-137">Ďalšie kroky</span><span class="sxs-lookup"><span data-stu-id="bfe7d-137">Next steps</span></span>

<span data-ttu-id="bfe7d-138">Stavajte na svojich obohatených údajoch o zákazníkoch.</span><span class="sxs-lookup"><span data-stu-id="bfe7d-138">Build on top of your enriched customer data.</span></span> <span data-ttu-id="bfe7d-139">Vytváraním [segmentov](segments.md), [mier](measures.md) a [exportovaním údajov](export-destinations.md) môžete zákazníkom pripravovať prispôsobené prostredia.</span><span class="sxs-lookup"><span data-stu-id="bfe7d-139">Create [segments](segments.md), [measures](measures.md), and [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>




[!INCLUDE[footer-include](../includes/footer-banner.md)]