---
title: "Použití datového skladu Intune | Dokumentace Microsoftu"
description: "Datový sklad Intune můžete používat k vytváření sestav poskytujících přehled o podnikovém mobilním prostředí."
keywords: "Datový sklad Intune"
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 07/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 57019B11-DF9B-4D8A-95FE-254C75398DDE
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: db6661dd92b890d711f655a60eb883b417a30d8a
ms.sourcegitcommit: addf6a40caa22c22adfd2e2eff7d666cd1877e3c
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/04/2017
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

> [!Important]  
> Nejnovější funkce datového skladu můžete vyzkoušet pomocí beta verze. Pokud chcete použít beta verzi, musí adresa URL obsahovat parametr dotazu `api-version=beta`. Beta verze nabízí funkce dřív, než budou všeobecně dostupné jako podporované služby. S tím, jak Intune přidává nové funkce, se může měnit chování a kontrakty dat beta verze. Jakýkoli vlastní kód nebo nástroje pro vytváření sestav závislé na beta verzi můžou přestat v probíhajících aktualizacích fungovat. <!-- If you experience problems with the beta service, follow [link to feedback process]() to report the issue or provide feedback.-->

**Další kroky**

- Získejte odkaz a použijte Power BI k získání přehledu. Pokyny najdete v tématu [Připojení k datovému skladu Intune pomocí Power BI](reports-proc-get-a-link-powerbi.md).
- Další informace o rozhraní API datového skladu Intune, datovém modelu a relacích mezi entitami<!-- , and an example of creating a custom client to retrieve data,--> najdete v tématu [Rozhraní API datového skladu Intune](reports-nav-intune-date-warehouse.md).