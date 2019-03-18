---
title: Protokol změn v datovém skladu Intune
titlesuffix: Microsoft Intune
description: Toto téma obsahuje seznam změn pro rozhraní API datového skladu Microsoft Intune.
keywords: Datový sklad Intune
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 02/22/2019
ms.topic: reference
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: E85DBB2D-67BB-4E10-82D6-E43046B9C43C
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: 20c9c1bf5eea12407cba2e00288a039b74fcaca7
ms.sourcegitcommit: 25e6aa3bfce58ce8d9f8c054bc338cc3dff4a78b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/14/2019
ms.locfileid: "57565634"
---
# <a name="change-log-for-the-intune-data-warehouse-api"></a>Protokol změn pro rozhraní API datového skladu Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Udržujte si přehled o aktualizacích datového skladu Intune.

## <a name="1902"></a>1902 
_Vydáno. února 2019_

### <a name="power-bi-compliance-app"></a>Dodržování předpisů aplikace Power BI 

Přístup k datovému skladu Intune pomocí Power BI Online [dodržování předpisů v Intune (datový sklad)](https://app.powerbi.com/groups/me/getapps/services/Intune_dw_compliance) aplikace. V této aplikaci Power BI můžete nyní přístup k a sdílet předem vytvořených sestav bez nastavení a aniž byste museli opustit ve webovém prohlížeči. 

> [!NOTE]
> Existují dva další filtry, které můžete použít pro aplikaci dodržování předpisů v Intune.

#### <a name="add-additional-filters-to-the-intune-compliance-app"></a>Přidat další filtry aplikace dodržování předpisů v Intune
1. Otevřít [dodržování předpisů v Intune (datový sklad)](https://app.powerbi.com/groups/me/getapps/services/Intune_dw_compliance) browers vaší webové aplikace.
2. Klikněte na tlačítko **nekompatibilní zařízení** a vyberte **nekompatibilní** v **complianceStatus** filtru. 
3. Klikněte na **Neznámá zařízení** a vyberte **zatím není k dispozici** v **complianceStatus** filtru. 

## <a name="1812"></a>1812 
_Vydáno prosince 2018_

### <a name="enrollment-activities-collection-released-to-v10"></a>Kolekce aktivit registrace všeobecně dostupné verze 1.0 

Kolekce aktivity zápisu je teď dostupná v v1.0. Tuto kolekci můžete použít k pochopení svazku selhání registrace a trendy ve vašem prostředí. Další informace najdete v tématu [enrollmentActivities](intune-data-warehouse-collections.md#enrollmentactivities), [enrollmentEventStatuses](intune-data-warehouse-collections.md#enrollmenteventstatuses), [enrollmentFailureCategories](intune-data-warehouse-collections.md#enrollmentfailurecategories), a [ enrollmentFailureReasons](intune-data-warehouse-collections.md#enrollmentfailurereasons).

## <a name="1808"></a>1808
_Vydáno v srpnu 2018_

### <a name="v10-collections"></a>Kolekce v1.0  

Nastavením parametru dotazu `api-version=v1.0` můžete teď používat verzi datového skladu Intune v1.0. Aktualizace kolekcí v datovém skladu mají aditivní povahu a nijak nenarušují existující scénáře.

### <a name="enrollment-activities-collection-released-to-beta"></a>Kolekce aktivit registrace všeobecně dostupné verze Beta

Nová kolekce `Enrollment Activities` se vydala ve verzi beta. Můžete ji použít k pochopení průběhu registrace tím, že se zaměříte na nejběžnější chyby. 


## <a name="1805"></a>1805
_Vydáno v květnu 2018_

### <a name="correction-to-device-count-in-devices-collection"></a>Oprava počtu zařízení v kolekci **Zařízení** 

Opravili jsme kolekci **Zařízení**, čímž se může snížit celkový počet zařízení vyfiltrovaných podle atributu `isDeleted`. Toto snížení je výsledkem opravy a není to chyba. Další informace o kolekci **Zařízení** najdete v části [Referenční informace pro entity zařízení](reports-ref-devices.md). 


## <a name="1801"></a>1801
_Vydáno v lednu 2018_

### <a name="intune-data-warehouse-application-only-authentication----1867540---"></a>Ověřování v Intune Data Warehouse pouze na úrovni aplikace <!-- 1867540 -->

Můžete nastavit aplikaci pomocí Azure Active Directory (Azure AD) a ověřit ji přes Intune Data Warehouse. Další informace najdete v tématu [Ověřování v datovém skladu Intune pouze na úrovni aplikace](data-warehouse-app-only-auth.md).

### <a name="azure-ad-and-intune-credential-requirements----2077525---"></a>Požadavky na přihlašovací údaje pro Azure AD a Intune <!-- 2077525 -->

- Při přístupu k datovému skladu Intune (včetně rozhraní API) se už nevyžaduje přiřazení licence Intune uživateli.
- Název role Intune **Sestavy** se změnil na **Datový sklad Intune**. 

    Další informace najdete v tématu [Požadavky na přihlašovací údaje pro Azure AD a Intune](reports-api-url.md#azure-ad-and-intune-credential-requirements).

### <a name="odata-query-options----2077711---"></a>Možnosti dotazu OData <!-- 2077711 -->

Jako parametr dotazu OData můžete použít <code>$select</code>. Aktuální verze podporuje tyto parametry dotazu OData: <code>$filter</code>, <code>$orderby</code>, <code>$select</code>, <code>$skip</code> a <code>$top</code>. Další informace najdete v tématu [Možnosti dotazu OData](reports-api-url.md#odata-query-options).

### <a name="new-entities-in-the-in-data-warehouse-data-model----2077804---"></a>Nové entity v v datovém modelu datového skladu <!-- 2077804 -->

 - Byla přidána entita [**MobileAppDeviceuserInstallStatus**](reports-ref-application.md#mobileappdeviceuserinstallstatus). **MobileAppDeviceUserInstallStatus** představuje stav instalace mobilní aplikace pro dané zařízení a uživatele.
 - Byla přidána entita [**MobileAppInstallState**](reports-ref-application.md#mobileappinstallstate). Entita **MobileAppInstallState** představuje stav instalace mobilní aplikace po jejím přiřazení do skupiny obsahující zařízení, uživatele, nebo obě tyto možnosti. 

## <a name="1710"></a>1710
_Vydáno v listopadu 2017_

### <a name="a-new-entity-collection-named-current-user-is-limited-to-currently-active-user-data----1544273---"></a>Nová kolekce entit z názvem aktuální uživatel je omezená na data aktuálně aktivních uživatelů <!-- 1544273 -->

Kolekce entit **Uživatelé** obsahuje všechny uživatele Azure Active Directory (Azure AD), kteří mají v podniku přiřazené licence. Tyto záznamy zahrnují stavy uživatelů za dobu shromažďování dat i v případě odebrání uživatele. Uživatel například může být přidaný do Intune a potom v průběhu posledního měsíce dojde k jeho odebrání. Přestože tento uživatel není v době vytvoření sestavy přítomen, existují data o uživateli a stavu. Můžete vytvořit sestavu, která ukazuje trvání historické přítomnosti uživatele ve vašich datech.

Naproti tomu nová kolekce entit **Aktuální uživatel** obsahuje pouze uživatele, kteří nebyli odebráni. Kolekce entit **Aktuální uživatel** obsahuje pouze aktuálně aktivní uživatele. Informace o kolekci entit **Aktuální uživatel** najdete v části [Referenční informace o entitě aktuálního uživatele](reports-ref-current-user.md).

## <a name="1709"></a>1709
_Vydáno: říjen 2017_

### <a name="user-device-association-entity-collection-added-to-intune-data-warehouse-data-model----1187917---"></a>Uživatel zařízení přidána kolekce entit přidružení do datového modelu datového skladu Intune <!-- 1187917 -->

Pomocí informací o přidružení uživatelů a zařízení, které přidružují kolekce entit uživatelů a zařízení, teď můžete vytvářet sestavy a vizualizace dat. Tento datový model lze zpřístupnit přes soubor Power BI (PBIX) načtený ze stránky Datový sklad v Intune, přes koncový bod OData nebo vývojem vlastního klienta. Další informace najdete v tématu [Přidružení zařízení uživatele](reports-ref-user-device.md).

### <a name="new-entities-in-the-in-data-warehouse-data-model----1479526--------"></a>Nové entity v v datovém modelu datového skladu <!-- 1479526 --><!-- -->

 - Přidali jsme entitu [**UserDeviceAssociation**](reports-ref-user-device.md). **UserDeviceAssociation** obsahuje přidružení zařízení uživatelů ve vaší organizaci. Pomocí informací o přidružení uživatelů a zařízení, které přidružují kolekce entit uživatelů a zařízení, teď můžete vytvářet sestavy a vizualizace dat.  
 - Přidali jsme entitu [**IntuneManagementExtension**](reports-ref-intunemanagementextension.md). **IntuneManagementExtension** obsahuje entity pro mobilní zařízení, které sledují informace, jako je verze a stav instalace.

## <a name="next-steps"></a>Další postup
 - Zjistěte, [jaké novinky každý týden přináší Intune](whats-new.md). Můžete také získat informace o nadcházejících změnách, důležitá oznámení o službě a informace o minulých vydaných verzích.
 - Přečtěte si [Blog Microsoft Intune](https://go.microsoft.com/fwlink/?LinkID=273882).
