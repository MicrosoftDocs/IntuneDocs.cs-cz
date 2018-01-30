---
title: "Protokol změn v datovém skladu Intune | Microsoft Docs"
description: "Seznam změn v rozhraní API datového skladu Intune"
keywords: "Datový sklad Intune"
author: erikre
ms.author: erikre
manager: dougeby
ms.date: 12/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: E85DBB2D-67BB-4E10-82D6-E43046B9C43C
ms.reviewer: aanavath
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 306cceb704c1153b5691181d576561d9c93a36d3
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2018
---
# <a name="change-log-for-the-intune-data-warehouse-api"></a>Protokol změn pro rozhraní API datového skladu Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Udržujte si přehled o aktualizacích datového skladu Intune.

## <a name="1710"></a>1710
_Vydáno v listopadu 2017_

### <a name="a-new-entity-collection-named-current-user-is-limited-to-currently-active-user-data----1544273---"></a>Nová kolekce entit z názvem Aktuální uživatel se omezuje na data aktuálně aktivních uživatelů <!-- 1544273 -->

Kolekce entit **Uživatelé** obsahuje všechny uživatele Azure Active Directory (Azure AD), kteří mají v podniku přiřazené licence. Tyto záznamy zahrnují stavy uživatelů za dobu shromažďování dat i v případě odebrání uživatele. Uživatel například může být přidaný do Intune a potom v průběhu posledního měsíce dojde k jeho odebrání. Přestože tento uživatel není v době vytvoření sestavy přítomen, existují data o uživateli a stavu. Můžete vytvořit sestavu, která ukazuje trvání historické přítomnosti uživatele ve vašich datech.

Naproti tomu nová kolekce entit **Aktuální uživatel** obsahuje pouze uživatele, kteří nebyli odebráni. Kolekce entit **Aktuální uživatel** obsahuje pouze aktuálně aktivní uživatele. Informace o kolekci entit **Aktuální uživatel** najdete v části [Referenční informace o entitě aktuálního uživatele](reports-ref-current-user.md).

## <a name="1709"></a>1709
_Vydáno: říjen 2017_

### <a name="user-device-association-entity-collection-added-to-intune-data-warehouse-data-model----1187917---"></a>Do datového modelu datového skladu Intune byla přidána kolekce entit přidružení uživatelů a zařízení <!-- 1187917 -->

Pomocí informací o přidružení uživatelů a zařízení, které přidružují kolekce entit uživatelů a zařízení, teď můžete vytvářet sestavy a vizualizace dat. Tento datový model lze zpřístupnit přes soubor Power BI (PBIX) načtený ze stránky Datový sklad v Intune, přes koncový bod OData nebo vývojem vlastního klienta. Další informace najdete v tématu [Přidružení zařízení uživatele](reports-ref-user-device.md).

### <a name="new-entities-in-the-in-data-warehouse-data-model----1479526--------"></a>Nové entity v datovém modelu datového skladu <!-- 1479526 --><!-- -->

 - Přidali jsme entitu [**UserDeviceAssociation**](reports-ref-user-device.md). **UserDeviceAssociation** obsahuje přidružení zařízení uživatelů ve vaší organizaci. Pomocí informací o přidružení uživatelů a zařízení, které přidružují kolekce entit uživatelů a zařízení, teď můžete vytvářet sestavy a vizualizace dat.  
 - Přidali jsme entitu [**IntuneManagementExtension**](reports-ref-intunemanagementextension.md). **IntuneManagementExtension** obsahuje entity pro mobilní zařízení, které sledují informace, jako je verze a stav instalace.

## <a name="next-steps"></a>Další kroky
 - Zjistěte, [jaké novinky každý týden přináší Intune](whats-new.md). Můžete také získat informace o nadcházejících změnách, důležitá oznámení o službě a informace o minulých vydaných verzích.
 - Přečtěte si [Blog Microsoft Intune](http://go.microsoft.com/fwlink/?LinkID=273882).
