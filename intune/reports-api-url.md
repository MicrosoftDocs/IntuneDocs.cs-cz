---
title: Koncový bod rozhraní API datového skladu Intune
titlesuffix: Microsoft Intune
description: Referenční téma popisuje strukturu adresy URL rozhraní API datového skladu Intune.
keywords: Datový sklad Intune
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 10/09/2018
ms.topic: reference
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: A7A174EC-109D-4BB8-B460-F53AA2D033E6
ms.reviewer: aanavath
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: c6709d68ce4bf847be3eb5cd5ae427db6d11aba8
ms.sourcegitcommit: 11bd3dbbc9dd762df7c6d20143f2171799712547
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/10/2018
ms.locfileid: "48903586"
---
# <a name="intune-data-warehouse-api-endpoint"></a>Koncový bod rozhraní API datového skladu Intune

Rozhraní API datového skladu Intune můžete použít s účtem s řízením přístupu na základě konkrétních rolí a přihlašovacími údaji služby Azure AD. Následně pak provedete autorizaci klienta REST s Azure AD pomocí standardu OAuth 2.0. Nakonec vytvoříte smysluplnou adresu URL pro volání prostředku datového skladu.

[!INCLUDE [reports-credential-reqs](./includes/reports-credential-reqs.md)]

## <a name="authorization"></a>Autorizace

Azure Active Directory (Azure AD) používá standard OAuth 2.0 za účelem umožnění autorizace přístupu k webovým aplikacím a webovým rozhraním API v tenantovi Azure AD. Tato příručka je nezávislá na jazyce a popisuje, jak posílat a přijímat zprávy HTTP bez použití knihoven open-source. Tok autorizačního kódu OAuth 2.0 je popsán v [části 4.1](https://tools.ietf.org/html/rfc6749#section-4.1) specifikace standardu OAuth 2.0.

Další informace najdete v tématu [Autorizace přístupu k webovým aplikacím pomocí OAuth 2.0 a Azure Active Directory](https://docs.microsoft.com/azure/active-directory/develop/active-directory-protocols-oauth-code).

## <a name="api-url-structure"></a>Struktura adresy URL rozhraní API

Koncové body rozhraní API datového skladu čtou entity jednotlivých sad. Rozhraní API podporuje příkaz HTTP **GET** a podmnožinu možností dotazu.

Adresa URL pro Intune používá následující formát:  
`https://fef.{location}.manage.microsoft.com/ReportingService/DataWarehouseFEService/{entity-collection}?api-version={api-version}`

> [!NOTE]
> Ve výše uvedené adrese URL nahraďte `{location}`, `{entity-collection}` a `{api-version}` podle informací v tabulce níže.

Adresa URL obsahuje následující prvky:

| Prvek | Příklad | Popis |
|-------------------|------------|--------------------------------------------------------------------------------------------------------------------|
| location | msua06 | Základní adresu URL můžete najít zobrazením okna rozhraní API datového skladu na webu Azure Portal. |
| kolekce-entit | kalendářní data | Název kolekce entit OData Další informace o kolekcích a entitách v datovém modelu najdete v tématu [Datový model](reports-ref-data-model.md). |
| verze-api | beta | Verze je verzí rozhraní API, ke kterému přistupujete. Další informace najdete v tématu [Verze](#API-version-information). |
| maxhistorydays | 7 | (Volitelné) Maximální počet dní, pro které se načte historie. Tento parametr lze zadat pro jakoukoli kolekci, ale bude mít účinek jenom u kolekcí, jejichž klíčová vlastnost zahrnuje `dateKey`. Další informace najdete v části [Filtry rozsahu DateKey](reports-api-url.md#datekey-range-filters). |

## <a name="api-version-information"></a>Informace o verzi rozhraní API

Aktuální verze rozhraní API je: `beta`. 

## <a name="odata-query-options"></a>Možnosti dotazu OData

Aktuální verze podporuje tyto parametry dotazu OData: `$filter, $orderby, $select, $skip,` a `$top`.

## <a name="datekey-range-filters"></a>Filtry rozsahu DateKey

Filtry rozsahu `DateKey` se dají použít k omezení množství dat ke stažení u některých kolekcí s klíčovou vlastností `dateKey`. Filtr `DateKey` lze použít k optimalizaci výkonu služby tak, že se zadá následující parametr dotazu `$filter`:

1.  Samotný prvek `DateKey` v dotazu `$filter`, který podporuje operátory `lt/le/eq/ge/gt` a ke kterému se dá přidat logický operátor `and`, který umožňuje mapování na počáteční nebo koncové datum.
2.  `maxhistorydays` se zadá jako vlastní parametr dotazu.<br>

## <a name="filter-examples"></a>Příklady filtrů

> [!NOTE]
> V příkladech filtrů se předpokládá, že dnešní datum je 21. 2. 2018.

|                             Filtr                             |           Optimalizace výkonu           |                                          Popis                                          |
|:--------------------------------------------------------------:|:--------------------------------------------:|:---------------------------------------------------------------------------------------------:|
|    `maxhistorydays=7`                                            |    Všechny                                      |    Vrátí data s hodnotou `DateKey` mezi 20180214 a 20180221.                                     |
|    `$filter=DateKey eq 20180214`                                 |    Všechny                                      |    Vrátí data s hodnotou `DateKey` rovnající se 20180214.                                                    |
|    `$filter=DateKey ge 20180214 and DateKey lt 20180221`         |    Všechny                                      |    Vrátí data s hodnotou `DateKey` mezi 20180214 a 20180220.                                     |
|    `maxhistorydays=7&$filter=Id gt 1`                            |    Částečná, Id gt 1 se neoptimalizuje    |    Vrátí data s hodnotou `DateKey` mezi 20180214 a 20180221 a Id větší než 1.             |
|    `maxhistorydays=7&$filter=DateKey eq 20180214`                |    Všechny                                      |    Vrátí data s hodnotou `DateKey` rovnající se 20180214. `maxhistorydays` se ignoruje.                            |
|    `$filter=DateKey eq 20180214 and Id gt 1`                     |    Žádné                                      |    Nepovažuje se za filtr rozsahu `DateKey`, takže k žádnému zvýšení výkonu nedojde.                              |
|    `$filter=DateKey ne 20180214`                                 |    Žádné                                      |    Nepovažuje se za filtr rozsahu `DateKey`, takže k žádnému zvýšení výkonu nedojde.                              |
|    `maxhistorydays=7&$filter=DateKey eq 20180214 and Id gt 1`    |    Žádné                                      |    Nepovažuje se za filtr rozsahu `DateKey`, takže k žádnému zvýšení výkonu nedojde. `maxhistorydays` se ignoruje.    |
