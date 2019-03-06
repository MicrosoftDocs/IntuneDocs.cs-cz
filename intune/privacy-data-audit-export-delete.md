---
title: Audit, export a odstranění osobních dat
description: Naučte se auditovat, exportovat a odstraňovat osobní data.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 05/18/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 96990be0-eb1e-43a4-a0e4-09c7dbdc2bf4
ms.reviewer: angerobe
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 2e4924b83caba0047f326f38cd7bce36b3fd38c4
ms.sourcegitcommit: 430b290474b11f9df87785b01edc178e6bae2049
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/05/2019
ms.locfileid: "57393568"
---
# <a name="audit-export-or-delete-personal-data-in-intune"></a>Audit, export a odstranění osobních dat v Intune

Správci Intune mohou v protokolech auditu sledovat aktivity spojené s osobními daty. Správci také mohou osobní data exportovat a odstraňovat.

[!INCLUDE [GDPR-related guidance](./includes/gdpr-intro-sentence.md)]

## <a name="audit-personal-data"></a>Audit osobních dat

Správci tenantů najdou v protokolech auditu zaznamenané aktivity, které v Microsoft Intune generují změnu. Protokoly auditu jsou k dispozici pro různé aktivity týkající se správy. Většinou jde o tyto akce: vytváření, aktualizace (úpravy), odstranění nebo přiřazení. Správci mohou kontrolovat také vzdálené úlohy, které generují auditované události. Protokoly auditu mohou obsahovat osobní data o uživatelích zařízení zaregistrovaných v Intune.  

Z bezpečnostních důvodů smí Intune udržovat protokoly auditu o akcích uživatelů a zařízení jenom za jeden rok. Po uplynutí ročního archivačního období budou tyto protokoly automaticky odstraněny.

Pokud chcete kontrolovat protokoly auditu, přečtěte si článek [Protokoly auditu pro aktivity v Intune](monitor-audit-logs.md). 

Správci nemohou protokoly auditu odstraňovat.

Auditované události se uchovávají jeden rok. Správci tenanta si mohou vyžádat protokoly auditu vyplněním [formuláře žádosti o podporu](https://privacy.microsoft.com/en-US/privacy-questions?).

## <a name="export-personal-data"></a>Export osobních dat

Správci mohou osobní data koncových uživatelů exportovat, včetně účtů, dat o službách a souvisejících protokolů, aby vyhověli požadavkům spojeným s právy subjektů, kterých se data týkají. Vy a vaše organizace rozhodnete, jestli subjektu, kterého se data týkají, poskytnete kopii osobních dat, nebo máte oprávněné obchodní důvody, proč poskytnutí dat odmítnout. Pokud se rozhodnete poskytnout kopii osobních dat, můžete subjektu poskytnout kopii skutečného dokumentu, upravenou verzi nebo snímek obrazovky s částí informací, které považujete za vhodné ke sdílení.

K exportu osobních dat uživatele můžete použít: 
- Okno správy mobilních zařízení v Intune, ze kterého můžete exportovat seznam zařízení. Data o zařízeních také můžete přímo kopírovat.
- [Skript Export-IntuneData.ps1](https://aka.ms/intunedataexport).

## <a name="delete-end-user-personal-data"></a>Odstranění osobních dat koncového uživatele

Existují tři způsoby, jak odebrat osobní data spravovaná v Intune:
- Odstranění uživatele z Azure Active Directory
- Resetování zařízení do továrního nastavení
- Samostatné odebrání uživatelem

### <a name="delete-a-user-from-intune"></a>Odstranění uživatele z Intune

Pokud chce správce z Intune odstranit osobní data koncového uživatele, musí [ho odstranit z Azure Active Directory (AAD)](https://docs.microsoft.com/azure/active-directory/add-users-azure-active-directory.md#delete-users-from-azure-ad). Po trvalém odstranění uživatele z AAD obdrží Intune signál o odstranění z AAD. Na jeho základě začne ze služby Intune automaticky mazat všechna osobní data uživatele. Informace o uživateli budou ze služby Intune odstraněny do 30 dnů od jeho odebrání.

### <a name="reset-device-to-factory-settings"></a>Resetování zařízení do továrního nastavení
Když zařízení resetujete do továrního nastavení, obnoví se všechna firemní i osobní data a nastavení do původního továrního nastavení. To je užitečné, když chcete zařízení předat dalšímu zaměstnanci. Do 30 dnů od odebrání uživatele budou ze služby Intune odstraněny uživatelské soubory, aplikace instalované uživatelem a veškeré nastavení, které není výchozí.

### <a name="user-self-removal-from-intune-management"></a>Samostatné odebrání uživatele ze správy v Intune
Uživatelé mohou odebrat osobní zařízení se systémem [Android, Apple nebo Windows](https://docs.microsoft.com/intune-user-help/unenroll-your-device-from-intune-android.md) ze správy v Intune i bez pomoci správce.   

### <a name="retire"></a>Vyřazení
Když zařízení **vyřadíte**, Intune odebere poskytnutá data, jako jsou firemní aplikace, data o aplikacích spravovaných v Intune, nastavení zásad a e-mailové profily zřízené prostřednictvím Intune. Při této akci zůstanou v zařízení osobní data uživatele.

### <a name="delete-a-tenant-from-microsoft-intune"></a>Odstranění tenanta z Microsoft Intune

Pokud zákazník, který používá tenanta Intune, zruší svůj účet Intune, odstraní se všechna data tenanta do 180 dnů od zavření účtu Intune zákazníkem. Pokud má tenant AAD přidružené jiné podnikové předplatné Microsoftu (třeba Azure nebo Ofice 365), odstraní se jenom data zákazníka Intune. Tenant AAD se zachová, aby ho mohla využívat jiná předplatná. Pokud má tenant AAD přidružené jenom předplatné účtu Intune, bude odstraněn tenant, všechny prostředky i zákazníkova data.

### <a name="delete-a-user-in-a-hybrid-mobile-device-management-mdm-environment"></a>Odstranění uživatele v hybridním prostředí správy mobilních zařízení (MDM)
Pokud máte hybridní prostředí MDM (tzn. že služba Intune je integrovaná do Configuration Manageru), musíte provést následující akce (v uvedeném pořadí), abyste uživatele zcela odstranili a úplně je odebrali z místních služeb Active Directory, Configuration Manager a Intune.

1. Odstraňte uživatele z místní služby Active Directory (AD). Tím zastavíte synchronizaci uživatele s Azure AD a také zjišťování uživatele Configuration Managerem. 
2. Pokud chcete odebrat uživatele a s ním spojená data z Configuration Manageru, odstraňte ho z konzoly Configuration Manageru. V konzole přejděte na **Prostředky a kompatibilita** > **Uživatelé**. Pravým tlačítkem klikněte na uživatele, kterého chcete odstranit, a klikněte na **Odstranit**.
3. Když [uživatele odstraníte z AAD](https://docs.microsoft.com/azure/active-directory/add-users-azure-active-directory.md#delete-users-from-azure-ad), odeberete uživatele a data, která se ho týkají, současně z Azure Active Directory i z Intune. Po trvalém odstranění uživatele z AAD obdrží Intune signál o odstranění z AAD. Na jeho základě začne ze služby Intune automaticky mazat všechna osobní data uživatele. Informace o uživateli budou ze služby Intune odstraněny do 30 dnů od jeho odebrání.

## <a name="next-steps"></a>Další postup

Přečtete si, jak [auditovat, exportovat nebo odstranit](privacy-data-audit-export-delete.md) osobní data evidovaná v Intune.
