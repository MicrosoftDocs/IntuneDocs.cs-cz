---
title: Metody registrace v Intune pro zařízení s Windows
titleSuffix: Microsoft Intune
description: Přečtěte si různé způsoby, jak můžete zaregistrovat zařízení s Windows v Intune
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 04/02/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.suite: ems
search.appverid: MET150
ms.custom: ''
ms.collection: ''
ms.openlocfilehash: 55e758c8a7eddc1a5500464754448d26680ec772
ms.sourcegitcommit: cc5d757018d05fc03ac9ea3d30f563df9bfd61ed
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/10/2019
ms.locfileid: "66819578"
---
# <a name="intune-enrollment-methods-for-windows-devices"></a>Metody registrace v Intune pro zařízení s Windows

Ke správě zařízení v Intune, musí zařízení nejdřív zaregistrovat ve službě Intune. Jak v osobním vlastnictví a podnikových zařízení, která mohou být zaregistrovaná ke správě Intune. 

Existují dva způsoby, jak získat zařízení zaregistrovaná v Intune:
- Uživatelé můžou sami zaregistrovat své počítače s Windows 
- Správci mohou nakonfigurovat zásady, které vynutit automatické registrace bez jakékoli zapojení uživatelů

## <a name="user-self-enrollment-in-intune"></a>Samoobslužný zápis v Intune

Uživatelé můžou sami zaregistrovat svoje zařízení s Windows pomocí některé z těchto metod:

- [Přineste si vlastní zařízení (BYOD)](https://docs.microsoft.com/intune-user-help/enroll-windows-10-device): Uživatelé zaregistrovat svoje zařízení v osobním vlastnictví volbou pro připojení **pracovní a školní** účet z **nastavení** zařízení. Tento postup:
    - Zaregistruje zařízení s Azure Active Directory a získat přístup k firemním prostředkům, jako je e-mail.
    - Zaregistruje zařízení v Intune jako osobní vlastnictví zařízení (BYOD).
Pokud správce nakonfiguroval automatický zápis (k dispozici s předplatnými Azure AD premium), má uživatel jenom jednou zadejte svoje přihlašovací údaje. V opačném případě budete mít k registraci samostatně prostřednictvím pouze registrace MDM a zadejte znovu své přihlašovací údaje.  
- **Pouze registrace MDM** umožňuje uživatelům registrovat existující pracovní skupiny služby Active Directory, nebo počítač do Intune připojený k Azure Active directory. Uživatelé můžou zaregistrovat z nastavení na existující počítač s Windows. Tato metoda není doporučeno, protože to není registrace zařízení do služby Azure Active Directory. Zabrání také použití funkce, jako je podmíněný přístup.
- [Připojení k Azure Active Directory (Azure AD)](https://docs.microsoft.com/azure/active-directory/user-help/user-help-join-device-on-network) – připojí zařízení se službou Azure Active Directory a umožňuje uživatelům přihlášení k Windows pomocí svých přihlašovacích údajů Azure AD. Pokud po povolení automatické registrace zařízení automaticky zaregistruje v Intune. Výhodou automatický zápis je jedním krokem procesu pro daného uživatele. V opačném případě budete mít k registraci samostatně prostřednictvím pouze registrace MDM a zadejte znovu své přihlašovací údaje. Uživatelé můžou zaregistrovat tímto způsobem během počáteční prvního Windows nebo z nastavení. Zařízení je označená jako firemní vlastněné zařízení v Intune.
- [AutoPilot](enrollment-autopilot.md) – automatizuje připojení ke službě Azure AD a zaregistruje do Intune nová zařízení vlastněných společností. Tato metoda zjednodušuje práci out-of-box a eliminuje nutnost použití vlastních imagí operačního systému na zařízeních. Když správci Intune použít ke správě zařízení Autopilot, můžou spravovat zásady, profily, aplikace a další po jejich registraci.  Existují dva typy nasazení Autopilot: [Vlastní nasazení režimu](https://docs.microsoft.com/windows/deployment/windows-autopilot/self-deploying) (pro veřejné terminály, digitálních materiálů nebo sdílená zařízení) a [uživatelského režimu řízené](https://docs.microsoft.com/windows/deployment/windows-autopilot/user-driven) (pro tradiční uživatele). 

## <a name="administrator-based-enrollment-in-intune"></a>Na základě správce registrace v Intune

Správci můžou nastavit následující metody registrace, které nevyžadují žádný zásah uživatele:

- [Hybridní připojení k Azure AD](https://docs.microsoft.com/windows/client-management/mdm/enroll-a-windows-10-device-automatically-using-group-policy) umožňuje správcům nakonfigurovat zásady skupiny služby Active Directory o automatickou registraci zařízení, která jsou připojená k hybridní Azure AD. 
- [Společná Správa nástroje Configuration Manager](https://docs.microsoft.com/sccm/comanage/overview) umožňuje správcům zaregistrovat svá zařízení existující spravované Configuration Manageru do Intune, abyste získali duální výhody Intune a Configuration Managerem. 
- [Správce registrace zařízení](device-enrollment-manager-enroll.md) (zařízení DEM) je speciální účet. Účty správce registrace zařízení mají oprávnění, která umožní oprávněným uživatelům registrovat a spravovat více zařízení vlastněných společností. Tyto typy zařízení se hodí například pro aplikace POS a jednoúčelové aplikace, ale nehodí se pro uživatele, kteří potřebují přístup k e-mailu nebo k prostředkům společnosti. Tato metoda nepovoluje použití funkce, jako je podmíněný přístup. 
- [Hromadná registrace](windows-bulk-enroll.md) umožňuje autorizovaným uživatelům k Azure Active Directory a Intune připojit velký počet nových zařízení vlastněných společností. Vytvořte zřizovací balíček s aplikací Windows Configuration designeru (WCD). Potom přes port USB média během počáteční prvního Windows prostředí nebo z existujících Windows PC, nainstalovat zřizovací balíček automaticky registrovat zařízení do Intune. Tato metoda nepovoluje použití podmíněného přístupu. 

## <a name="next-steps"></a>Další postup

[Další možnosti metody zápisu Windows](enrollment-method-capab.md)
