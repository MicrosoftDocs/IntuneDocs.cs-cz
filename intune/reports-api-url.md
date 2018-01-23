---
title: "Koncový bod rozhraní API datového skladu Intune | Dokumentace Microsoftu"
description: "Referenční téma popisuje strukturu adresy URL rozhraní API."
keywords: "Datový sklad Intune"
author: Erikre
ms.author: erikre
manager: angrobe
ms.date: 07/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: A7A174EC-109D-4BB8-B460-F53AA2D033E6
ms.reviewer: aanavath
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 4ca309a0317686a44a495a758ab52c079bc858af
ms.sourcegitcommit: d44c32aad3e84f6c0b296bdb010981d3a818befb
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/16/2018
---
# <a name="intune-data-warehouse-api-endpoint"></a>Koncový bod rozhraní API datového skladu Intune

Rozhraní API datového skladu Intune můžete použít s účtem s řízením přístupu na základě konkrétních rolí a přihlašovacími údaji služby Azure AD. Následně pak provedete autorizaci klienta REST s Azure AD pomocí standardu OAuth 2.0. Nakonec vytvoříte smysluplnou adresu URL pro volání prostředku datového skladu.

[!INCLUDE[reports-credential-reqs](./includes/reports-credential-reqs.md)]

## <a name="authorization"></a>Autorizace

Azure Active Directory (Azure AD) používá standard OAuth 2.0 za účelem umožnění autorizace přístupu k webovým aplikacím a webovým rozhraním API v tenantovi Azure AD. Tato příručka je nezávislá na jazyce a popisuje, jak posílat a přijímat zprávy HTTP bez použití našich knihoven open-source. Tok autorizačního kódu OAuth 2.0 je popsán v [části 4.1](https://tools.ietf.org/html/rfc6749#section-4.1) specifikace standardu OAuth 2.0.

Další informace najdete v tématu [Autorizace přístupu k webovým aplikacím pomocí OAuth 2.0 a Azure Active Directory](https://docs.microsoft.com/azure/active-directory/develop/active-directory-protocols-oauth-code).

## <a name="api-url-structure"></a>Struktura adresy URL rozhraní API

Koncové body rozhraní API datového skladu čtou entity jednotlivých sad. Rozhraní API podporuje příkaz HTTP **GET** a podmnožinu možností dotazu.

Adresa URL pro Intune používá následující formát:  
https://fef.{***umístění***}.manage.microsoft.com/ReportingService/DataWarehouseFEService/{***kolekce-entit***}?api-version={***verze-api***}

Adresa URL obsahuje následující prvky:

| Prvek | Příklad | Popis |
|-------------------|------------|--------------------------------------------------------------------------------------------------------------------|
| location | msua06 | Základní adresu URL můžete najít zobrazením okna rozhraní API datového skladu na webu Azure Portal. |
| kolekce-entit | kalendářní data | Název kolekce entit OData Další informace o kolekcích a entitách v datovém modelu najdete v tématu [Datový model](reports-ref-data-model.md). |
| verze-api | beta | Verze je verzí rozhraní API, ke kterému přistupujete. Další informace najdete v tématu [Verze](#API-version-information). |


## <a name="api-version-information"></a>Informace o verzi rozhraní API

Aktuální verze rozhraní API je: `beta`. 

## <a name="odata-query-options"></a>Možnosti dotazu OData

Aktuální verze podporuje tyto parametry dotazu OData: `$filter, $orderby, $select, $skip,` a `$top`.