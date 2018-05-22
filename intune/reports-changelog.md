---
title: Protokol změn v datovém skladu Intune
titlesuffix: Microsoft Intune
description: Seznam změn v rozhraní API datového skladu Intune
keywords: Datový sklad Intune
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 05/15/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: E85DBB2D-67BB-4E10-82D6-E43046B9C43C
ms.reviewer: aanavath
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: dd9fb36bb1b8c5e66d104f530690c5d236ea25e4
ms.sourcegitcommit: 34e96e57af6b861ecdfea085acf3c44cff1f3d43
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/17/2018
---
# <a name="change-log-for-the-intune-data-warehouse-api"></a>Protokol změn pro rozhraní API datového skladu Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Udržujte si přehled o aktualizacích datového skladu Intune.

## <a name="1805"></a>1805
_Vydáno v květnu 2018_

### <a name="correction-to-device-count-in-devices-collection"></a>Oprava počtu zařízení v kolekci **Zařízení** 

Opravili jsme kolekci **Zařízení**, čímž se může snížit celkový počet zařízení vyfiltrovaných podle atributu `isDeleted`. Toto snížení je výsledkem opravy a není to chyba. Další informace o kolekci **Zařízení** najdete v části [Referenční informace pro entity zařízení](reports-ref-devices.md). 


## <a name="1801"></a>1801
_Vydáno v lednu 2018_

### <a name="intune-data-warehouse-application-only-authentication----1867540---"></a>Ověřování v datovém skladu Intune pouze na úrovni aplikace <!-- 1867540 -->

Můžete nastavit aplikaci pomocí Azure Active Directory (Azure AD) a ověřit ji přes Intune Data Warehouse. Další informace najdete v tématu [Ověřování v datovém skladu Intune pouze na úrovni aplikace](data-warehouse-app-only-auth.md).

### <a name="azure-ad-and-intune-credential-requirements----2077525---"></a>Požadavky na přihlašovací údaje pro Azure AD a Intune <!-- 2077525 -->

- Při přístupu k datovému skladu Intune (včetně rozhraní API) se už nevyžaduje přiřazení licence Intune uživateli.
- Název role Intune **Sestavy** se změnil na **Datový sklad Intune**. 

    Další informace najdete v tématu [Požadavky na přihlašovací údaje pro Azure AD a Intune](reports-api-url.md#azure-ad-and-intune-credential-requirements).

### <a name="odata-query-options----2077711---"></a>Možnosti dotazu OData <!-- 2077711 -->

Jako parametr dotazu OData můžete použít <code>$select</code>. Aktuální verze podporuje tyto parametry dotazu OData: <code>$filter</code>, <code>$orderby</code>, <code>$select</code>, <code>$skip</code> a <code>$top</code>. Další informace najdete v tématu [Možnosti dotazu OData](reports-api-url.md#odata-query-options).

### <a name="new-entities-in-the-in-data-warehouse-data-model----2077804---"></a>Nové entity v datovém modelu datového skladu <!-- 2077804 -->

 - Byla přidána entita [**MobileAppDeviceuserInstallStatus**](reports-ref-application.md#mobileappdeviceuserinstallstatus). **MobileAppDeviceUserInstallStatus** představuje stav instalace mobilní aplikace pro dané zařízení a uživatele.
 - Byla přidána entita [**MobileAppInstallState**](reports-ref-application.md#mobileappinstallstate). Entita **MobileAppInstallState** představuje stav instalace mobilní aplikace po jejím přiřazení do skupiny obsahující zařízení, uživatele, nebo obě tyto možnosti. 

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
