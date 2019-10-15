---
title: Audit, export nebo odstranění osobních údajů
titleSuffix: Microsoft Intune
description: Přečtěte si, jak auditovat, exportovat nebo odstraňovat osobní údaje.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 05/18/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 96990be0-eb1e-43a4-a0e4-09c7dbdc2bf4
ms.reviewer: kerimh
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 74428abf8141c648b5b81bba3177cc89a3cb01d2
ms.sourcegitcommit: dd6755383ba89824d1cc128698a65fde6bb2de55
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/14/2019
ms.locfileid: "72306820"
---
# <a name="audit-export-or-delete-personal-data-in-intune"></a>Auditování, export nebo odstranění osobních údajů v Intune

Správci Intune můžou pomocí protokolů auditu sledovat aktivity obklopující osobní údaje. Správci mohou také exportovat a odstraňovat osobní údaje.

[!INCLUDE [GDPR-related guidance](../includes/gdpr-intro-sentence.md)]

## <a name="audit-personal-data"></a>Auditovat osobní údaje

Protokoly auditu poskytují správcům tenanta záznam aktivit, které generují změnu v Microsoft Intune. Protokoly auditu jsou k dispozici pro mnoho aktivit správy a obvykle se vytvářejí, aktualizují (upravují), odstraňují a přiřazují akce. Je také možné zkontrolovat vzdálené úlohy, které generují události auditu. Tyto protokoly auditu můžou obsahovat osobní údaje uživatelů, jejichž zařízení jsou zaregistrovaná v Intune.  

Pro účely zabezpečení může Intune uchovávat protokoly auditu pro akce uživatelů a zařízení po dobu jednoho roku. Tyto protokoly se po uplynutí doby uchování po dobu jednoho roku automaticky odstraní.

Protokoly auditu si můžete prohlédnout v tématu [protokoly auditu pro aktivity Intune](../fundamentals/monitor-audit-logs.md). 

Správci nemůžou odstranit protokoly auditu.

Tyto události auditu se uchovávají po dobu jednoho roku. Správci klientů mohou požádat o protokoly auditu pomocí [tohoto formuláře žádosti o podporu](https://privacy.microsoft.com/en-US/privacy-questions?).

## <a name="export-personal-data"></a>Export osobních údajů

Správci mohou exportovat osobní údaje o koncových uživatelích, včetně účtů, dat služeb a přidružených protokolů, aby byly v souladu s požadavky na práva subjektu dat. Je to pro vás a vaši organizaci, abyste se rozhodli, jestli chcete subjektu údajů poskytnout kopii osobních údajů, nebo jestli máte oprávněný podnikový důvod k jeho odmítnutí. Pokud se rozhodnete ho poskytnout, můžete jim poskytnout kopii vlastního dokumentu, vhodně neredigovánou verzi nebo snímek obrazovky s částmi, které jste považovali za vhodné ke sdílení.

Pokud chcete exportovat osobní údaje uživatele, můžete použít: 
- okno zařízení MDM Intune pro export seznamu zařízení. Data zařízení také můžete kopírovat přímo.
- [skript export-IntuneData. ps1](https://aka.ms/intunedataexport).

## <a name="delete-end-user-personal-data"></a>Odstranit osobní data koncového uživatele

Existují tři způsoby, jak ze správy Intune odebrat osobní data:
- Odstranit uživatele z Azure Active Directory
- Resetovat tovární nastavení zařízení
- Samoobslužné odebrání uživatele

### <a name="delete-a-user-from-intune"></a>Odstranění uživatele z Intune

Pokud chcete z Intune odstranit osobní údaje koncového uživatele, správce musí [uživatele odstranit z Azure Active Directory (AAD)](https://docs.microsoft.com/azure/active-directory/fundamentals/add-users-azure-active-directory#delete-a-user). Když se uživatel z AAD odstraní (nevratný), obdrží Intune signál odstranit z AAD a pak automaticky zahájí mazání všech osobních údajů tohoto uživatele ze služby Intune. Informace o uživateli budou odstraněny ze služby Intune do 30 dnů od akce odebrání.

### <a name="reset-device-to-factory-settings"></a>Resetovat zařízení do továrního nastavení
Obnovení továrního nastavení obnoví ze všech firemních a osobních údajů a nastavení původní tovární nastavení. To je užitečné pro poskytování zařízení dalšímu zaměstnanci. Uživatelské soubory, aplikace nainstalované uživatelem a jiné než výchozí nastavení se odeberou a tato data se ze služby Intune odstraní do 30 dnů od akce odebrání.

### <a name="user-self-removal-from-intune-management"></a>Samoobslužné odebrání uživatele ze správy Intune
Uživatelé můžou svoje zařízení [s Androidem, Apple nebo Windows](https://docs.microsoft.com/intune-user-help/unenroll-your-device-from-intune-android) odebrat ze správy Intune bez pomoci správce.   

### <a name="retire"></a>Vyřazení
Akce **vyřazení** odebere vytvořená data Intune, jako jsou aplikace společnosti, data o aplikacích, které spravuje Intune, nastavení zásad a e-mailové profily zřízené prostřednictvím Intune. Tato akce opustí osobní údaje uživatele v zařízení.

### <a name="delete-a-tenant-from-microsoft-intune"></a>Odstranění tenanta z Microsoft Intune

Pokud zákazník tenanta Intune zruší svůj účet Intune, všechna data tenanta se odstraní během 180 dnů od uzavření účtu Intune od zákazníka. Pokud je tenant AAD přidružený k jiným předplatným Microsoft Enterprise (Azure, Office 365), odstraní se jenom zákaznická data Intune. Prostředek tenanta AAD se uchovává pro použití v ostatních předplatných. Pokud je účet Intune jediným předplatným přidruženým k tenantovi AAD, tenant se odstraní a odstraní se taky všechny prostředky a zákaznická data.

### <a name="delete-a-user-in-a-hybrid-mobile-device-management-mdm-environment"></a>Odstranění uživatele v hybridním prostředí pro správu mobilních zařízení (MDM)
Pokud máte hybridní prostředí MDM (Intune je integrované s Configuration Manager), musíte provést následující akce (v uvedeném pořadí) k úplnému odstranění uživatele a jejich úplnému odebrání z místní služby Active Directory, Configuration Manager a Intune.

1. Odstraňte uživatele z místní služby Active Directory (AD). Tím se zastaví synchronizace uživatele se službou Azure AD a zjistí se taky Configuration Manager zjišťování. 
2. Odstraněním uživatele z konzoly Configuration Manager odeberete uživatele a přidružená data z Configuration Manager. V konzole nástroje přejděte na prostředky **assety a dodržování předpisů** > **Uživatelé**, klikněte pravým tlačítkem na uživatele, který chcete odstranit, a klikněte na **Odstranit**.
3. [Odstraňte uživatele z AAD](https://docs.microsoft.com/azure/active-directory/fundamentals/add-users-azure-active-directory#delete-a-user), který odebere uživatele a přidružená data z Azure Active Directory i Intune současně. Když se uživatel z AAD odstraní (nevratný), obdrží Intune signál odstranit z AAD a pak automaticky zahájí mazání všech osobních údajů tohoto uživatele ze služby Intune. Informace o uživateli budou odstraněny ze služby Intune do 30 dnů od akce odebrání.

> [!Important]
>Připojování nových zákazníků hybridních MDM se už nepoužívá. Další informace najdete v příspěvku na blogu o [přesunu z hybridní správy mobilních zařízení do Intune v Azure](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Move-from-Hybrid-Mobile-Device-Management-to-Intune-on-Azure/ba-p/280150) .

## <a name="next-steps"></a>Další kroky

Zjistěte, jak v Intune [Auditovat, exportovat nebo odstraňovat](privacy-data-audit-export-delete.md) osobní údaje.
