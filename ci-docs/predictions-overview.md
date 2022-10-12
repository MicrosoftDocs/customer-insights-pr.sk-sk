---
title: Prehľad predikcií
description: Scenáre predikcie a možnosti, ktoré pokrýva aplikácia Dynamics 365 Customer Insights.
ms.date: 09/29/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: overview
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: f8c61d7530126890d26ce482a27a0f97a39e836c
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: sk-SK
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610209"
---
# <a name="predictions-overview"></a>Prehľad predikcií

Dynamics 365 Customer Insights prichádza s rôznymi možnosťami, ktoré využívajú AI a strojové učenie na predikciu údajov.

## <a name="out-of-box-models"></a>Pripravené modely

Najjednoduchší spôsob, ako začať s predikovaním údajov, sú preddefinované modely, ktoré sa často označujú ako vopred pripravené modely. Vyžadujú iba určité údaje a štruktúru na rýchle získanie štatistík. K dispozícii sú nasledujúce modely:

# <a name="individual-consumers-b-to-c"></a>[Jednotliví spotrebitelia (firma a spotrebiteľ)](#tab/b2c)

- [Hodnota životnosti zákazníka](predict-customer-lifetime-value.md): Predikuje potenciálne príjmy zákazníka počas celej interakcie s podnikom.
- [Odporúčanie produktu](predict-product-recommendation.md): Navrhuje množiny prediktívnych odporúčaní produktov na základe nákupného správania a zákazníkov s podobnými nákupnými vzormi.
- [Odchod predplatiteľov](predict-subscription-churn.md): Predikuje, či hrozí odchod zákazníka, pretože už nebude používať predplatené produkty alebo služby vašej spoločnosti.
- [Transakčný únik](predict-transactional-churn.md) : Predpovedá, či si individuálny zákazník už nebude kupovať vaše produkty alebo služby v určitom časovom rámci.
- [Analýza sentimentu](sentiment-analysis.md) : Analyzuje pocity spätnej väzby od zákazníkov a identifikuje obchodné aspekty, ktoré sa často spomínajú.

# <a name="business-accounts-b-to-b"></a>[Firemné obchodné vzťahy (firma a firma)](#tab/b2b)

- [Transakčný únik](predict-transactional-churn.md) : Predpovedá, či zákaznícky účet už nebude kupovať vaše produkty alebo služby v určitom časovom rámci.

---

> [!TIP]
> Odporúčame vám pravidelne obnovovať predvolené modely s aktualizovanými údajmi, aby ste zaistili, že budú presne informovať o vašom firemnom použití. Údaje sa obnovujú ad-hoc, keď systém prijíma nové alebo aktualizované zdroje údajov. Modely však v tomto prípade len prehodnotia a budú naďalej využívať existujúce tréningové dáta.
>
> Nakonfigurujte an **Aktualizovať plán** nastavením plánu preškolenia modelu počas konfigurácie. Model sa preškolí a prehodnotí podľa tohto rozvrhu, ktorý môžete kedykoľvek zmeniť.

## <a name="azure-machine-learning-integration"></a>Integrácia strojového učenia platformy Azure

Ak organizácia už používa scenáre strojového učenia založené na experimentoch strojového učenia Azure, funkcia vlastných modelov v Customer Insights pomôže tieto body spojiť. Vytvorte pracovné postupy, ktoré vám pomôžu vybrať údaje, z ktorých chcete generovať štatistiky, a výsledky namapovať do svojich zjednotených profilov zákazníkov. Viac informácií nájdete v časti [Vlastné modely strojového učenia](custom-models.md).

## <a name="manage-existing-predictions"></a>Spravujte existujúce predpovede

Choďte na **Inteligencia** > **Predpovede** stránku. Na **Moje predpovede** zobrazte predpovede, ktoré ste vytvorili, ich typ predikcia, názov výstupnej entity, stav, kedy bol predikcia naposledy upravený a kedy boli údaje naposledy obnovené. Zoznam predpovedí môžete zoradiť podľa ľubovoľného stĺpca.

Ak chcete zobraziť dostupné akcie, vyberte predikcia.

:::image type="content" source="media/predictions.png" alt-text="Moja stránka predpovedí.":::

- **Upraviť** predikcia na zmenu jeho vlastností.
- [**Obnoviť**](#refresh-a-prediction) predikcia na zahrnutie najnovších údajov.
- **vyhliadka** podrobnosti predikcia.
- [**Správa o použiteľnosti vstupných údajov**](#view-the-input-data-usability-report) na zobrazenie chýb, upozornení a odporúčaní.
- **Odstrániť** predikcia.

### <a name="refresh-a-prediction"></a>Obnovenie predikcie

Predpovede môžu byť obnovené podľa automatického plánu alebo manuálne na požiadanie. Ak chcete manuálne obnoviť všetky predpovede, vyberte **Obnoviť všetko**. Ak chcete manuálne obnoviť predikcia, vyberte ho a vyberte **Obnoviť**. Komu [naplánovať automatické obnovenie](schedule-refresh.md), ísť do **Admin** > **Systém** > **Rozvrh**.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

### <a name="view-the-input-data-usability-report"></a>Prezeranie zostavy použiteľnosti vstupných údajov

Zostava o použiteľnosti vstupných údajov poskytuje konsolidovaný prehľad o chybách a varovaniach, ktoré môžu generovať vaše vopred pripravené predikcie. Poskytuje tiež odporúčania, ako zlepšiť výkon modelu.

Zostava je k dispozícii po dokončení tréningového procesu modelu. Je vytvorený pre každý model zvlášť, bez ohľadu na to, či absolvoval školenie úspešne alebo nie.

Na **Moje predpovede** vyberte kartu predikcia a vyberte si **Správa o použiteľnosti vstupných údajov**. Alebo v predikcia zobrazení podrobností vyberte **Správa o použiteľnosti vstupných údajov**.

:::image type="content" source="media/input-data-usability-report.png" alt-text="Príklad správy o použiteľnosti vstupných údajov, ktorá zobrazuje tabuľku s chybami, varovaniami a odporúčaniami.":::

Správa obsahuje:

- **Názov:** Popisný názov chyby, varovania alebo odporúčania.
- **krok:** Fáza modelu, vlak alebo skóre, na ktoré sa informácie vzťahujú.
- **Štát:** Závažnosť informácie (chyba, varovanie, odporúčanie).
- **Názov stĺpca:** Stĺpec v entite, ktorú je potrebné upraviť, aby sa zlepšil výkon modelu.
- **Názov entity:** Názov entity, ktorú je potrebné upraviť, aby sa zlepšil výkon modelu.
- **Podrobnosti:** Podrobnosti o chybe, varovaní alebo odporúčaní.

[!INCLUDE [footer-include](includes/footer-banner.md)]
