---
title: "Použití datového skladu Intune | Dokumentace Microsoftu"
description: "Datový sklad Intune můžete používat k vytváření sestav poskytujících přehled o podnikovém mobilním prostředí."
keywords: "Datový sklad Intune"
author: Erikre
ms.author: erikre
manager: angrobe
ms.date: 10/18/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 57019B11-DF9B-4D8A-95FE-254C75398DDE
ms.reviewer: aanavath
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 910d279b57c885040d2ad092e460d3e7ca71090e
ms.sourcegitcommit: d44c32aad3e84f6c0b296bdb010981d3a818befb
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/16/2018
---
# <a name="use-the-intune-data-warehouse"></a>Použití datového skladu Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Datový sklad Intune můžete používat k vytváření sestav poskytujících přehled o podnikovém mobilním prostředí. Některé z těchto sestav například obsahují:
-   Trend uživatelů registrujících se v Intune, který vám umožní optimalizovat nákupy licencí
-   Rozpis verzí aplikací a operačních systémů, abyste mohli kontrolovat stav mobilních zařízení
-   Trendy registrace a dodržování předpisů zařízeními, abyste mohli plynule zavést aktualizace zásad

Datový sklad poskytuje přístup k více informacím týkajícím se vašeho mobilního prostředí než web Azure Portal. Datový sklad Intune vám umožňuje přistupovat k:

  -  Historickým datům Intune
  -  Datům aktualizovaným na denní bázi
  -  Datovému modelu používajícímu standard OData

> [!Note]
> Pokud spolu s nástrojem System Center Configuration Manager a Microsoft Intune používáte hybridní správu mobilních zařízení (MDM), můžete chtít načíst data z SCCM. Datový sklad Intune obsahuje jenom data Intune. Pro vlastní sestavy můžete využít řídicí panel Power BI SCCM. Další informace najdete v článku [Představujeme šablonu řešení Power BI pro System Center Configuration Manager]( https://powerbi.microsoft.com/blog/sccm-solution-template) a [Vytvoření sestavy a řídicího panelu Power BI](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/analytics/create-powerbi-report-dashboard).


> [!Important]  
> Nejnovější funkce datového skladu můžete vyzkoušet pomocí beta verze. Pokud chcete použít beta verzi, musí adresa URL obsahovat parametr dotazu `api-version=beta`. Beta verze nabízí funkce dřív, než budou všeobecně dostupné jako podporované služby. S tím, jak Intune přidává nové funkce, se může měnit chování a kontrakty dat beta verze. Jakýkoli vlastní kód nebo nástroje pro vytváření sestav závislé na beta verzi můžou přestat v probíhajících aktualizacích fungovat.

**Další kroky**

- Získejte odkaz a použijte Power BI k získání přehledu. Pokyny najdete v tématu [Připojení k datovému skladu Intune pomocí Power BI](reports-proc-get-a-link-powerbi.md).
- S odkazem vytvořte vlastní sestavu pomocí Power BI. Pokyny najdete v článku [Vytvoření sestavy z datového kanálu OData pomocí Power BI](reports-proc-create-with-odata.md).
- Další informace o rozhraní API datového skladu Intune, datovém modelu a relacích mezi entitami<!-- , and an example of creating a custom client to retrieve data,--> najdete v tématu [Rozhraní API datového skladu Intune](reports-nav-intune-data-warehouse.md).