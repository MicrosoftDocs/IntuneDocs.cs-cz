---
title: Vytvoření sestavy z datového kanálu OData pomocí Power BI
titlesuffix: Microsoft Intune
description: Vytvořte vizualizaci mapy stromové struktury pomocí Power BI Desktopu s interaktivním filtrem z rozhraní API datového skladu Intune.
keywords: Datový sklad Intune
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 05/15/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: A2C8A336-29D3-47DF-BB4A-62748339391D
ms.reviewer: aanavath
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 12725f567cf84d1d7e9110da747470984bc28c01
ms.sourcegitcommit: 34e96e57af6b861ecdfea085acf3c44cff1f3d43
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/17/2018
ms.locfileid: "34224847"
---
# <a name="create-a-report-from-the-odata-feed-with-power-bi"></a>Vytvoření sestavy z datového kanálu OData pomocí Power BI

V tomto článku se dozvíte, jak vytvořit vizualizaci mapy stromové struktury pomocí Power BI Desktopu s interaktivním filtrem. Váš finanční ředitel může třeba chtít vědět, jak se na celkovém rozdělení zařízení podílejí zařízení ve vlastnictví společnosti a osobní zařízení. Mapa stromové struktury poskytuje podrobný přehled celkového počtu typů zařízení. Můžete zkontrolovat počet zařízení s iOSem, Androidem a Windows, která jsou ve vlastnictví společnosti nebo v osobním vlastnictví.

### <a name="overview-of-creating-the-chart"></a>Přehled vytvoření grafu

Graf vytvoříte takto:
1. Pokud ještě nemáte Power BI Desktop, nainstalujte ho.
2. Připojte se k datovému modelu datového skladu Intune a načtěte aktuální data modelu.
3. Vytvořte nebo spravujte relace datového modelu.
4. Vytvořte graf s daty z tabulky **zařízení**.
5. Vytvořte interaktivní filtr.
6. Zobrazte hotový graf.

### <a name="a-note-about-tables-and-entities"></a>Poznámka k tabulkám a entitám

V Power BI pracujete s tabulkami. Tabulka obsahuje datová pole. Každé datové pole má datový typ. Pole může obsahovat jenom data datového typu. Datové typy jsou čísla, text, kalendářní data a tak dále. Tabulky v Power BI se při načtení modelu vyplní posledními historickými daty z vašeho tenanta. I když se konkrétní data časem mění, struktura tabulky se nezmění, dokud se základní datový model neaktualizuje.

Používání pojmů _entita_ a _tabulka_ může být matoucí. Datový model je přístupný prostřednictvím datového kanálu OData. Kontejnery, které se v Power BI nazývají tabulky, se v prostředí OData nazývají entity. Oba tyto pojmy označují stejnou věc, která obsahuje vaše data.

## <a name="install-power-bi-desktop"></a>Instalace Power BI Desktopu

Nainstalujte si nejnovější verzi aplikace Power BI Desktop. Power BI Desktop si můžete stáhnout z webu: [PowerBI.microsoft.com](https://powerbi.microsoft.com/desktop)

## <a name="connect-to-the-odata-feed-for-the-intune-data-warehouse-for-your-tenant"></a>Připojení k datovému kanálu OData pro datový sklad Intune pro vašeho tenanta

> [!Note]  
> Potřebujete oprávnění k **Sestavám** v Intune. Další informace najdete v sekci [Autorizace](reports-api-url.md).

1. Přihlaste se k [portálu Azure Portal](https://portal.azure.com).
2. Zvolte **Všechny služby** > **Intune**. Intune se nachází v části **Monitorování a správa**.
3. Otevřete podokno **Datový sklad Intune**.
4. Zkopírujte adresu URL vlastního kanálu. Příklad: `https://fef.tenant.manage.microsoft.com/ReportingService/DataWarehouseFEService?api-version=beta`
5. Otevřete Power BI Desktop.
6. Zvolte **Načíst data** > **Datový kanál Odata**.
7. Do pole pro adresu URL v okně **Datový kanál OData** vložte adresu URL vlastního kanálu.
8. Vyberte **Základní**.

    ![Datový kanál OData](media/reports-create-01-odatafeed.png)

9. Vyberte **OK**.
10. Vyberte **Účet organizace** a pak se přihlaste pomocí přihlašovacích údajů Intune.

    ![Přihlašovací údaje pro účet organizace](media/reports-create-02-org-account.png)

11. Vyberte **Připojit**. Otevře se Navigátor se seznamem tabulek v datovém skladu Intune.

    ![Navigátor](media/reports-create-02-loadentities.png)

12. Vyberte **zařízení** a tabulky **ownerTypes**.  Vyberte **Načíst**. Power BI načte data do modelu.

## <a name="create-a-relationship"></a>Vytvoření relace

Můžete importovat víc tabulek k analýze nejen dat v jedné tabulce, ale souvisejících dat mezi tabulkami.  PowerBI má funkci zvanou **automatické rozpoznávání**, která se pokusí relace najít a vytvořit za vás. Tabulky v datovém skladu jsou vytvořené tak, aby funkci automatického rozpoznání v PowerBI podporovaly. I když ale PowerBI relace automaticky nenajde, stále je spravujete.

![Správa relací](media/reports-create-03-managerelationships.png)

1. Vyberte **Spravovat relace**.
2. Pokud PowerBI ještě relace nerozpoznal, vyberte **Automatické rozpoznávání**.

Relace se zobrazí ve sloupci Z do sloupce Do. V tomto příkladu datové pole **ownerTypeKey** v tabulce **zařízení** odkazuje na datové pole **ownerTypeKey** v okně **ownerTypes**. Pomocí relace vyhledejte prostý název kódu typu zařízení v tabulce **zařízení**.

## <a name="create-a-treemap-visualization"></a>Vytvoření vizualizace mapy stromové struktury

Graf mapy stromové struktury zobrazuje hierarchická data jako pole uvnitř polí. Každá větev hierarchie je pole, které obsahuje menší pole zobrazující nižší větve. Pomocí Power BI Desktopu můžete vytvořit mapu stromové struktury vašich dat Intune.

![Vizualizace > mapa stromové struktury](media/reports-create-03-treemap.png)

1. Zvolte typ grafu. Vyberte **Mapa stromové struktury**.
2. V datovém modelu najděte tabulku **zařízení**.
3. Rozbalte **tabulku zařízení** a na panelu **Pole** vyberte datové pole **výrobce**.
4. Přetáhněte datové pole **výrobce** do grafu Mapa stromové struktury na plátně pro sestavy.
5. Přetáhněte datové pole **deviceKey** z tabulky **zařízení** do sekce **Hodnoty** v podokně **Vizualizace** a pusťte ho v poli označeném **Sem přetáhněte datové pole**.  

Teď máte vizuál, který znázorňuje rozdělení výrobců zařízení v rámci vaší organizace.

![Mapa stromové struktury s daty](media/reports-create-06-treemapwdata.png)

## <a name="add-a-filter"></a>Přidání filtru

Do mapy stromové struktury můžete přidat filtr, který vám pomocí vaší aplikace umožní zodpovědět další otázky.


1. Pokud chcete přidat filtr, vyberte plátno pro sestavy a pak vyberte **ikonu Průřez** (![Mapa stromové struktury s daty](media/reports-create-slicer.png)) v části **Vizualizace**.
2. Najděte tabulku **ownerTypes** a přetáhněte datové pole **ownerTypeName** do části **Filtry** na panelu **Vizualizace**.  

   V tabulce zařízení je datové pole s názvem **OwnerTypeKey**, které obsahuje kód, jestli je zařízení ve vlastnictví společnosti, nebo osobní. Protože v tomto filtru chcete zobrazit popisné názvy, najděte tabulku **ownerTypes** a přetáhněte **ownerTypeName**. Tento příklad ukazuje, jak datový model podporuje relace mezi tabulkami.

![Mapa stromové struktury s filtrem](media/reports-create-08_ownertype.png)

Teď máte interaktivní filtr, pomocí kterého můžete přepínat mezi zařízeními ve vlastnictví společnosti a v osobním vlastnictví. Pomocí tohoto filtru uvidíte, jak se jejich rozdělení mění.

1. Výběrem možnosti **Společnost** zobrazíte rozdělení zařízení ve vlastnictví společnosti.
2. Výběrem možnosti **Osobní** zobrazíte zařízení v osobním vlastnictví.

## <a name="next-steps"></a>Další kroky

 - Další informace o [vytváření a správě relací](https://powerbi.microsoft.com/documentation/powerbi-desktop-create-and-manage-relationships/) v Power BI Desktopu najdete v dokumentaci k Power BI.
 - Přečtěte si článek [Datový model datového skladu Intune](https://docs.microsoft.com/intune/reports-ref-data-model).
