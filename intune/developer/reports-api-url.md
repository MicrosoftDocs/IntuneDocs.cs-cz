---
title: Koncový bod rozhraní API datového skladu Intune
titleSuffix: Microsoft Intune
description: Toto referenční téma popisuje Microsoft Intune strukturu adres URL rozhraní API datového skladu. Jsou k dispozici příklady filtru.
keywords: Datový sklad Intune
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 10/03/2019
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: A7A174EC-109D-4BB8-B460-F53AA2D033E6
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: f73e80fed5de74bc074e26502270467b7d846e5c
ms.sourcegitcommit: 223d64a72ec85fe222f5bb10639da729368e6d57
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/04/2019
ms.locfileid: "71940150"
---
# <a name="intune-data-warehouse-api-endpoint"></a>Koncový bod rozhraní API datového skladu Intune

Rozhraní API datového skladu Intune můžete použít s účtem, který má konkrétní řízení přístupu na základě rolí a přihlašovací údaje Azure AD. Potom budete mít k Azure AD autorizaci klienta REST pomocí OAuth 2,0. A nakonec budete tvořit smysluplnou adresu URL pro volání prostředku datového skladu.

[!INCLUDE [reports-credential-reqs](../includes/reports-credential-reqs.md)]

## <a name="authorization"></a>Autorizace

Azure Active Directory (Azure AD) používá OAuth 2,0 k autorizaci přístupu k webovým aplikacím a webovým rozhraním API v tenantovi Azure AD. Tato příručka je nezávislá na jazyce a popisuje, jak odesílat a přijímat zprávy HTTP bez použití Open Source knihoven. Tok autorizačního kódu OAuth 2,0 je popsaný v [části 4,1](https://tools.ietf.org/html/rfc6749#section-4.1) specifikace OAuth 2,0.

Další informace najdete v tématu [autorizace přístupu k webovým aplikacím pomocí OAuth 2,0 a Azure Active Directory](https://docs.microsoft.com/azure/active-directory/develop/active-directory-protocols-oauth-code).

## <a name="api-url-structure"></a>Struktura adresy URL rozhraní API

Koncové body rozhraní API datového skladu čtou entity pro každou sadu. Rozhraní API podporuje příkaz **Get** http a podmnožinu možností dotazu.

Adresa URL pro Intune používá následující formát:  
`https://fef.{location}.manage.microsoft.com/ReportingService/DataWarehouseFEService/{entity-collection}?api-version={api-version}`

> [!NOTE]
> V předchozí adrese URL nahraďte `{location}`, `{entity-collection}` a `{api-version}` na základě podrobností uvedených v následující tabulce.

Adresa URL obsahuje následující prvky:

| Prvek | Příklad | Popis |
|-------------------|------------|--------------------------------------------------------------------------------------------------------------------|
| umístění | msua06 | Základní adresu URL najdete tak, že v Azure Portal zobrazíte okno rozhraní API datového skladu. |
| kolekce entit | devicePropertyHistories | Název kolekce entit OData Další informace o kolekcích a entitách v datovém modelu najdete v tématu [datový model](reports-ref-data-model.md). |
| verze API-Version | Testování | Verze je verze rozhraní API, pro kterou má být přístup. Další informace najdete v tématu [Version](reports-api-url.md#api-version-information). |
| maxhistorydays | čl | Volitelné Maximální počet dní, po které se má načítat historie. Tento parametr lze zadat do jakékoli kolekce, ale uplatní se pouze pro kolekce, které zahrnují `dateKey` jako součást své klíčové vlastnosti. Další informace najdete v tématu [filtry rozsahu DateKey](reports-api-url.md#datekey-range-filters) . |

## <a name="api-version-information"></a>Informace o verzi rozhraní API

Teď můžete použít verzi v datovém skladu Intune v 1.0 nastavením parametru dotazu @ no__t-0. Aktualizace kolekcí v datovém skladu jsou v podstatě doplňkové a neruší stávající scénáře.

Nejnovější funkce datového skladu můžete vyzkoušet pomocí beta verze. Chcete-li použít beta verzi, musí adresa URL obsahovat parametr dotazu @ no__t-0. Beta verze nabízí funkce dřív, než jsou všeobecně dostupné jako podporovaná služba. Jelikož Intune přidává nové funkce, může beta verze změnit chování a kontrakty dat. Jakékoli vlastní kódy nebo nástroje pro vytváření sestav závislé na beta verzi se můžou porušit průběžnými aktualizacemi.

## <a name="odata-query-options"></a>Možnosti dotazu OData

Aktuální verze podporuje tyto parametry dotazu OData: `$filter`, `$select`, `$skip,` a `$top`. V `$filter` může být podporován pouze `DateKey` nebo `RowLastModifiedDateTimeUTC`, pokud jsou sloupce použity a další vlastnosti budou aktivovat chybný požadavek.

## <a name="datekey-range-filters"></a>Filtry rozsahu DateKey

filtry rozsahu `DateKey` se dají použít k omezení množství dat, která se mají stáhnout pro některé kolekce, a to jako vlastnost klíče `dateKey`. Filtr `DateKey` se dá použít k optimalizaci výkonu služby tím, že poskytuje následující parametr dotazu `$filter`:

1. `DateKey` samostatně v `$filter`, podporující operátory `lt/le/eq/ge/gt` a spojit se s operátorem Logic `and`, kde lze namapovat na datum zahájení nebo koncové datum.
2. `maxhistorydays` se dodává jako možnost vlastního dotazu.<br>

## <a name="filter-examples"></a>Příklady filtru

> [!NOTE]
> Příklady filtru předpokládají, že dnes je 2/21/2019.

|                             Filtrovací                             |           Optimalizace výkonu           |                                          Popis                                          |
|:--------------------------------------------------------------:|:--------------------------------------------:|:---------------------------------------------------------------------------------------------:|
|    `maxhistorydays=7`                                            |    Do bloku                                      |    Vrátí data s `DateKey` mezi 20180214 a 20180221.                                     |
|    `$filter=DateKey eq 20180214`                                 |    Do bloku                                      |    Vrátí data s `DateKey` rovnající se 20180214.                                                    |
|    `$filter=DateKey ge 20180214 and DateKey lt 20180221`         |    Do bloku                                      |    Vrátí data s `DateKey` mezi 20180214 a 20180220.                                     |
|    `maxhistorydays=7&$filter=DateKey eq 20180214`                |    Do bloku                                      |    Vrátí data s `DateKey` rovnající se 20180214. `maxhistorydays` se ignoruje.                            |
|    `$filter=RowLastModifiedDateTimeUTC ge 2018-02-21T23:18:51.3277273Z`                                |    Do bloku                                       |    Vrátí data s `RowLastModifiedDateTimeUTC` je větší nebo rovna `2018-02-21T23:18:51.3277273Z`.                             |
