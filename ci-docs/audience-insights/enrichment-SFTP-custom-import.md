---
title: Obohatenie pomocou vlastného importu protokolu SFTP
description: Všeobecné informácie o obohatení pomocou vlastného importu protokolu SFTP.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: a2d450635c19432bdd88db74b61c17febdeb568d
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: sk-SK
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896300"
---
# <a name="enrich-customer-profiles-with-custom-data-preview"></a><span data-ttu-id="dff93-103">Obohatenie profilov zákazníkov o vlastné údaje (ukážka)</span><span class="sxs-lookup"><span data-stu-id="dff93-103">Enrich customer profiles with custom data (preview)</span></span>

<span data-ttu-id="dff93-104">Vlastný import protokolu SFTP (Secure File Transfer Protocol) vám umožňuje importovať údaje, ktoré nemusia prechádzať procesom zjednotenia údajov.</span><span class="sxs-lookup"><span data-stu-id="dff93-104">Secure File Transfer Protocol (SFTP) custom import enables you to import data that does not have to go through the process of data unification.</span></span> <span data-ttu-id="dff93-105">Ide o flexibilný, bezpečný a ľahký spôsob, ako prenášať vaše údaje.</span><span class="sxs-lookup"><span data-stu-id="dff93-105">It's a flexible, secure, and easy way to bring in your data.</span></span> <span data-ttu-id="dff93-106">Vlastný import SFTP je možné použiť v kombinácii s [exportom protokolu SFTP](export-sftp.md), ktorý vám umožňuje exportovať údaje profilu zákazníka, ktoré sú potrebné na obohatenie.</span><span class="sxs-lookup"><span data-stu-id="dff93-106">SFTP custom import can be used in combination with [SFTP export](export-sftp.md) that lets you export the customer profile data that is needed for enrichment.</span></span> <span data-ttu-id="dff93-107">Údaje potom môžu byť spracované, obohatené a vlastný import protokolu SFTP je možné použiť na prenos obohatených údajov späť do funkcie prehľadov cieľových skupín v službe Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="dff93-107">The data can then be processed, enriched, and SFTP custom import can be used to bring the enriched data back to the audience insights capability of Dynamics 365 Customer Insights.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="dff93-108">Predpoklady</span><span class="sxs-lookup"><span data-stu-id="dff93-108">Prerequisites</span></span>

<span data-ttu-id="dff93-109">Ak chcete nakonfigurovať vlastný import protokolu SFTP, musíte splniť nasledujúce predpoklady:</span><span class="sxs-lookup"><span data-stu-id="dff93-109">To configure SFTP custom import, the following prerequisites must be met:</span></span>

- <span data-ttu-id="dff93-110">Máte názov súboru a umiestnenie (cestu) súboru, ktorý sa má importovať na hostiteľa SFTP.</span><span class="sxs-lookup"><span data-stu-id="dff93-110">You have the filename and location (path) of the file to be imported on the SFTP host.</span></span>
- <span data-ttu-id="dff93-111">Existuje súbor *model.json*, ktorý špecifikuje [schému spoločného dátového modelu](/common-data-model/) na import údajov.</span><span class="sxs-lookup"><span data-stu-id="dff93-111">There is a *model.json* file that specifies [the Common Data Model schema](/common-data-model/) for the data to be imported.</span></span> <span data-ttu-id="dff93-112">Tento súbor musí byť v rovnakom adresári ako súbor, ktorý sa má importovať.</span><span class="sxs-lookup"><span data-stu-id="dff93-112">This file must be in the same directory as the file to import.</span></span>
- <span data-ttu-id="dff93-113">Pripojenie SFTP už nakonfiguroval správca *alebo* máte povolenia [správcu](permissions.md#administrator).</span><span class="sxs-lookup"><span data-stu-id="dff93-113">An SFTP connection has already been configured by an administrator *or* you have [administrator](permissions.md#administrator) permissions.</span></span> <span data-ttu-id="dff93-114">Budete potrebovať prihlasovacie údaje používateľa, adresu URL a číslo portu pre umiestnenie SFTP, z ktorého chcete importovať údaje.</span><span class="sxs-lookup"><span data-stu-id="dff93-114">You'll need the user credentials, URL, and port number for the SFTP location where you want to import data from.</span></span>


## <a name="configure-the-import"></a><span data-ttu-id="dff93-115">Konfigurácia importu</span><span class="sxs-lookup"><span data-stu-id="dff93-115">Configure the import</span></span>

1. <span data-ttu-id="dff93-116">Prejdite na **Údaje** > **Obohatenie** a vyberte kartu **Objavovať**.</span><span class="sxs-lookup"><span data-stu-id="dff93-116">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="dff93-117">V **dlaždici vlastného importu SFTP** stlačte možnosť **Obohatiť moje údaje** a potom stlačte možnosť **Začíname**.</span><span class="sxs-lookup"><span data-stu-id="dff93-117">On the **SFTP custom import tile**, select **Enrich my data** and then select **Get started**.</span></span>

   :::image type="content" source="media/SFTP_Custom_Import_tile.png" alt-text="Dlaždica vlastného importu.":::

1. <span data-ttu-id="dff93-119">V rozbaľovacej ponuke stlačte možnosť [pripojenie](connections.md).</span><span class="sxs-lookup"><span data-stu-id="dff93-119">Select a [connection](connections.md) from the drop-down.</span></span> <span data-ttu-id="dff93-120">Ak nie je k dispozícii pripojenie, kontaktujte správcu.</span><span class="sxs-lookup"><span data-stu-id="dff93-120">Contact an administrator if no connection is available.</span></span> <span data-ttu-id="dff93-121">Ak ste správca, pripojenie môžete vytvoriť výberom možnosti **Pridať pripojenie** a v rozbaľovacej ponuke stlačte možnosť **Vlastný import SFTP**.</span><span class="sxs-lookup"><span data-stu-id="dff93-121">If you are an administrator, you can create a connection by selecting **Add connection** and choosing **SFTP Custom Import** from the drop-down.</span></span>

1. <span data-ttu-id="dff93-122">Vyberte **Pripojiť sa k vlastnému importu** na potvrdenie zvoleného spojenia.</span><span class="sxs-lookup"><span data-stu-id="dff93-122">Select **Connect to Custom Import** to confirm the selected connection.</span></span>

1.  <span data-ttu-id="dff93-123">Stlačte možnosť **Ďalej** a vstúpte do časti **Názov súboru** a **Cesta** s údajmi, ktoré chcete importovať.</span><span class="sxs-lookup"><span data-stu-id="dff93-123">Select **Next** and enter the **Filename** and **Path** of the data file that you want to import.</span></span>

    :::image type="content" source="media/enrichment-SFTP-path-and-filename.png" alt-text="Snímka obrazovky pri zadávaní umiestnenia údajov.":::

1. <span data-ttu-id="dff93-125">Stlačte možnosť **Ďalej** a uveďte názov obohatenia a názov výstupnej entity.</span><span class="sxs-lookup"><span data-stu-id="dff93-125">Select **Next** and provide a name for the enrichment and a name for the output entity.</span></span> 

1. <span data-ttu-id="dff93-126">Stlačte možnosť **Uložiť obohatenie** po preskúmaní vašich možností.</span><span class="sxs-lookup"><span data-stu-id="dff93-126">Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="configure-the-connection-for-sftp-custom-import"></a><span data-ttu-id="dff93-127">Nakonfigurujte pripojenie pre vlastný import SFTP</span><span class="sxs-lookup"><span data-stu-id="dff93-127">Configure the connection for SFTP Custom Import</span></span> 

<span data-ttu-id="dff93-128">Na konfiguráciu pripojení musíte byť administrátor.</span><span class="sxs-lookup"><span data-stu-id="dff93-128">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="dff93-129">Stlačte možnosť **Pridať pripojenie** pri konfigurácii obohatenia *alebo* prejdite na **Správca** > **Pripojenia** a vyberte **Nastaviť** na dlaždici Vlastný import.</span><span class="sxs-lookup"><span data-stu-id="dff93-129">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the Custom Import tile.</span></span>

1. <span data-ttu-id="dff93-130">Zadajte názov pripojenia do boxu **Zobrazovaný názov**.</span><span class="sxs-lookup"><span data-stu-id="dff93-130">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="dff93-131">Zadajte platné používateľské meno, heslo a adresu URL hostiteľa servera STFP, na ktorom sa nachádzajú importované údaje.</span><span class="sxs-lookup"><span data-stu-id="dff93-131">Enter valid user name, password, and host URL for the STFP server the data to be imported resides on.</span></span>

1. <span data-ttu-id="dff93-132">Skontrolujte a poskytnite svoj súhlas pre **Ochranu osobných údajov a dodržiavanie súladu s nariadeniami** výberom začiarkavacieho políčka **Súhlasím**.</span><span class="sxs-lookup"><span data-stu-id="dff93-132">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span>

1. <span data-ttu-id="dff93-133">Stlačte **Overiť** na overenie konfigurácie.</span><span class="sxs-lookup"><span data-stu-id="dff93-133">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="dff93-134">Po dokončení overenia je možné pripojenie uložiť kliknutím na možnosť **Uložiť**.</span><span class="sxs-lookup"><span data-stu-id="dff93-134">Once the verification has completed, the connection can be saved by clicking **Save**.</span></span>

> [!div class="mx-imgBorder"]
   > <span data-ttu-id="dff93-135">![Konfiguračná stránka pripojenia Experian](media/enrichment-SFTP-connection.png "Konfiguračná stránka pripojenia Experian")</span><span class="sxs-lookup"><span data-stu-id="dff93-135">![Experian connection configuration page](media/enrichment-SFTP-connection.png "Experian connection configuration page")</span></span>


## <a name="defining-field-mappings"></a><span data-ttu-id="dff93-136">Definovanie mapovania polí</span><span class="sxs-lookup"><span data-stu-id="dff93-136">Defining field mappings</span></span> 

<span data-ttu-id="dff93-137">Adresár, ktorý obsahuje súbor, ktorý sa má importovať na server SFTP, musí obsahovať aj súbor *model.json*.</span><span class="sxs-lookup"><span data-stu-id="dff93-137">The directory that contains the file to be imported on the SFTP server must also contain a *model.json* file.</span></span> <span data-ttu-id="dff93-138">Tento súbor definuje schému, ktorá sa má použiť na importovanie údajov.</span><span class="sxs-lookup"><span data-stu-id="dff93-138">This file defines the schema to use for importing the data.</span></span> <span data-ttu-id="dff93-139">Schéma musí používať [Common Data Model](/common-data-model/) na určenie mapovania polí.</span><span class="sxs-lookup"><span data-stu-id="dff93-139">The schema has to use [the Common Data Model](/common-data-model/) to specify the field mapping.</span></span> <span data-ttu-id="dff93-140">Jednoduchá ukážka súboru model.json vyzerá takto:</span><span class="sxs-lookup"><span data-stu-id="dff93-140">A simple example of a model.json file looks like this:</span></span>

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

## <a name="enrichment-results"></a><span data-ttu-id="dff93-141">Výsledky obohatenia</span><span class="sxs-lookup"><span data-stu-id="dff93-141">Enrichment results</span></span>

<span data-ttu-id="dff93-142">Proces obohatenia spustíte výberom položky **Spustiť** z panela príkazov.</span><span class="sxs-lookup"><span data-stu-id="dff93-142">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="dff93-143">Môžete tiež nechať systém, aby obohatenie spustil automaticky ako súčasť a [plánovaného obnovenia](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="dff93-143">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="dff93-144">Čas spracovania bude závisieť od množstva údajov, ktoré sa majú importovať, a od pripojenia k serveru SFTP.</span><span class="sxs-lookup"><span data-stu-id="dff93-144">The processing time will depend on the size of the data to be imported and the connection to the SFTP server.</span></span>

<span data-ttu-id="dff93-145">Po dokončení procesu obohacovania môžete svoje novo importované údaje o vlastnom obohacovaní skontrolovať v sekcii **Moje obohatenia**.</span><span class="sxs-lookup"><span data-stu-id="dff93-145">After the enrichment process completes, you can review your newly imported custom enrichment data under **My enrichments**.</span></span> <span data-ttu-id="dff93-146">Ďalej nájdete čas poslednej aktualizácie a počet obohatených profilov.</span><span class="sxs-lookup"><span data-stu-id="dff93-146">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="dff93-147">Môžete získať podrobné zobrazenie každého obohateného profilu výberom **Zobraziť obohatené údaje**.</span><span class="sxs-lookup"><span data-stu-id="dff93-147">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="dff93-148">Ďalšie kroky</span><span class="sxs-lookup"><span data-stu-id="dff93-148">Next steps</span></span>

<span data-ttu-id="dff93-149">Stavajte na svojich obohatených údajoch o zákazníkoch.</span><span class="sxs-lookup"><span data-stu-id="dff93-149">Build on top of your enriched customer data.</span></span> <span data-ttu-id="dff93-150">Vytváraním [segmentov](segments.md), [mier](measures.md) a [exportovaním údajov](export-destinations.md) môžete zákazníkom pripravovať prispôsobené prostredia.</span><span class="sxs-lookup"><span data-stu-id="dff93-150">Create [segments](segments.md), [measures](measures.md), and [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
