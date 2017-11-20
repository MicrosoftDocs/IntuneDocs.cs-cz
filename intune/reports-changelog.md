---
title: "Protokol změn v datovém skladu Intune | Microsoft Docs"
description: "Seznam změn v rozhraní API datového skladu Intune"
keywords: "Datový sklad Intune"
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 10/19/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: E85DBB2D-67BB-4E10-82D6-E43046B9C43C
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 6d675a36cd5ea4c11d755174bf2b0bbc5d4b18ec
ms.sourcegitcommit: 5279a0bb8c5aef79aa57aa247ad95888ffe5a12b
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/08/2017
---
# <a name="change-log-for-the-intune-data-warehouse-api"></a>Protokol změn pro rozhraní API datového skladu Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Udržujte si přehled o aktualizacích datového skladu Intune.

## <a name="1710"></a>1710
_Vydáno v listopadu 2017_

### <a name="user-entity-contains-latest-user-data-in-data-warehouse-data-model----1544273---"></a>Entita uživatele obsahuje nejnovější uživatelská data v datovém modelu datového skladu<!-- 1544273 -->

První verze datového modelu datového skladu Intune obsahovala jenom poslední historická data Intune. Při vytváření sestav nebylo možné zachytit aktuální stav uživatele. V této aktualizaci se [**entita uživatele**](reports-ref-user.md) naplní nejnovějšími uživatelskými daty.

### <a name="new-entities-in-the-in-data-warehouse-data-model----1479526--------"></a>Nové entity v datovém modelu datového skladu <!-- 1479526 --><!-- -->

 - Přidali jsme entitu [**UserDeviceAssociation**](reports-ref-user-device.md). **UserDeviceAssociation** obsahuje přidružení zařízení uživatelů ve vaší organizaci.
 - Přidali jsme entitu [**IntuneManagementExtension**](reports-ref-intunemanagementextension.md). **IntuneManagementExtension** obsahuje entity pro mobilní zařízení, které sledují informace, jako je verze a stav instalace.

## <a name="next-steps"></a>Další kroky
 - Zjistěte, [jaké novinky každý týden přináší Intune](whats-new.md). Můžete také získat informace o nadcházejících změnách, důležitá oznámení o službě a informace o minulých vydaných verzích. 
 - Přečtěte si [Blog Microsoft Intune](http://go.microsoft.com/fwlink/?LinkID=273882).