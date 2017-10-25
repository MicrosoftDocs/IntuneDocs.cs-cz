---
title: "Hromadný zápis pro Windows 10"
titlesuffix: Azure portal
description: "Vytvoření balíčku hromadné registrace pro Microsoft Intune"
keywords: 
author: NathBarn
ms.author: NathBarn
manager: angrobe
ms.date: 10/23/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1f39c02a-8d8a-4911-b4e1-e8d014dbce95
ms.reviewer: damionw
ms.custom: intune-azure
ms.openlocfilehash: 372cc50fb4ac36ec875d84a71f3d3437917a2d1a
ms.sourcegitcommit: 93c8c7e5abe433e35d88cb3b8d3d1e7216d7fe9b
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/24/2017
---
# <a name="bulk-enrollment-for-windows-devices"></a>Hromadná registrace pro zařízení s Windows

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Jako správce můžete k Azure Active Directory a Intune připojit větší počet zařízení s Windows. Hromadnou registraci zařízení pro vašeho tenanta Azure AD zahájíte vytvořením zřizovacího balíčku pomocí aplikace Windows Configuration Designer (WCD). Při aplikování zřizovacího balíčku na zařízení ve vlastnictví firmy se tato zařízení připojí k vašemu tenantovi Azure AD a zaregistrují v systému správy pomocí Intune. Po aplikování balíčku se uživatelé Azure AD můžou přihlašovat.

Uživatelé Azure AD jsou na těchto zařízeních standardními uživateli a obdrží přiřazené zásady Intune a požadované aplikace. Samoobslužné scénáře a scénáře s Portálem společnosti v současnosti nejsou podporované.

## <a name="prerequisites-for-windows-devices-bulk-enrollment"></a>Předpoklady pro hromadnou registraci zařízení s Windows

Hromadná registrace pro zařízení s Windows vyžaduje:

- Zařízení se systémem Windows 10 Creators Update nebo novějším
- [Automatická registrace Windows](https://docs.microsoft.com/intune-classic/deploy-use/set-up-windows-device-management-with-microsoft-intune#enable-windows-10-automatic-enrollment)

## <a name="create-a-provisioning-package"></a>Vytvoření zřizovacího balíčku

1. Stáhněte si [Windows Configuration Designer (WCD)](https://www.microsoft.com/store/apps/9nblggh4tx22) z Microsoft Storu.
![Snímek obrazovky se snímky obrazovky a popisem aplikace Windows Configuration Designer ve Storu](media/bulk-enroll-store.png)

2. Otevřete aplikaci **Windows Configuration Designer** a vyberte **Provision desktop devices** (Zřídit počítačová zařízení).
![Snímek obrazovky s výběrem možnosti Provision desktop devices ve Windows Configuration Designeru](media/bulk-enroll-select.png)

3. Otevře se okno **New project** (Nový projekt), kde zadáte:
  - **Name** (Název) – název vašeho projektu
  - **Project folder** (Složka projektu) – kam se projekt uloží
  - **Description** (Popis) – volitelný popis projektu ![Snímek obrazovky se zadáním názvu, složky projektu a popisu v aplikaci Windows Configuration Designer](media/bulk-enroll-name.png)

4.  Zadejte jedinečný název pro zařízení. Názvy můžou obsahovat sériové číslo (%%SERIAL%%) nebo náhodnou sadu znaků. Volitelně můžete také zadat kód Product Key, pokud provádíte upgrade edice Windows, nakonfigurovat zařízení pro sdílené používání a odebrat předinstalovaný software.
![Snímek obrazovky se zadáním názvu, složky projektu a popisu v aplikaci Windows Configuration Designer](media/bulk-enroll-device.png)

5.  Volitelně můžete nakonfigurovat síť Wi-Fi, ke které se zařízení připojí při prvním spuštění.  Pokud ji nenakonfigurujete, musí být zařízení při prvním spuštění připojené k drátové síti.
![Snímek obrazovky s povolením Wi-Fi včetně SSID sítě a typu sítě v aplikaci Windows Configuration Designer](media/bulk-enroll-network.png)

6.  Vyberte **Enroll in Azure AD** (Zaregistrovat v Azure AD), zadejte datum **Bulk Token Expiry** (Vypršení platnosti hromadného tokenu) a pak vyberte **Get Bulk Token** (Získat hromadný token).
![Snímek obrazovky se zadáním názvu, složky projektu a popisu v aplikaci Windows Configuration Designer](media/bulk-enroll-account.png)

7. Zadejte přihlašovací údaje k Azure AD, abyste získali hromadný token.
![Snímek obrazovky se zadáním názvu, složky projektu a popisu v aplikaci Windows Configuration Designer](media/bulk-enroll-cred.png)

8.  Když se **Bulk Token** (Hromadný token) úspěšně načte, klikněte na **Next** (Další).

9. Volitelně můžete **Add applications** (Přidat aplikace) a **Add certificates** (Přidat certifikáty). Tyto aplikace a certifikáty se zřídí v zařízení.

10. Volitelně můžete zřizovací balíček ochránit heslem.  Klikněte na **Vytvořit**.
![Snímek obrazovky se zadáním názvu, složky projektu a popisu v aplikaci Windows Configuration Designer](media/bulk-enroll-create.png)

## <a name="provision-devices"></a>Zřízení zařízení

1. Najděte zřizovací balíček v umístění, které jste zadali v **Project folder** (Složka projektu) v aplikaci.

2. Zvolte, jakým způsobem zřizovací balíček do zařízení aplikujete.  Zřizovací balíček se dá do zařízení aplikovat jedním z těchto způsobů:
 - Zřizovací balíček umístěte na USB flash disk, připojte USB flash disk k zařízení, které chcete hromadně zaregistrovat, a aplikujte balíček během počáteční instalace.
 - Zřizovací balíček umístěte do síťové složky a aplikujte na zařízení, které chcete po počáteční instalaci hromadně zaregistrovat.

 Podrobné pokyny k aplikování zřizovacího balíčku najdete v článku o [aplikování zřizovacího balíčku](https://technet.microsoft.com/itpro/windows/configure/provisioning-apply-package).

3. Po aplikování balíčku se zařízení za 1 minutu automaticky restartuje.
 ![Snímek obrazovky se zadáním názvu, složky projektu a popisu v aplikaci Windows Configuration Designer](media/bulk-enroll-add.png)

4. Po restartu se zařízení připojí k Azure Active Directory a zaregistruje v Microsoft Intune.

## <a name="troubleshooting-windows-bulk-enrollment"></a>Řešení potíží s hromadnou registrací zařízení s Windows

### <a name="provisioning-issues"></a>Problémy se zřizováním
Zřizování se má používat na nových zařízeních s Windows. Selhání zřizování může vyžadovat tovární resetování zařízení nebo obnovení zařízení ze spouštěcí image. Tyto příklady popisují některé důvody pro selhání zřizování:

- Zřizovací balíček snažící se připojit k doméně Active Directory nebo tenantovi Azure Active Directory, který nevytváří místní účet, může způsobit, že bude zařízení nedostupné, pokud proces připojení k doméně selže kvůli chybějícímu připojení k síti.
- Skripty spouštěné zřizovacím balíčkem se spouštějí v kontextu systému a dokáží provádět libovolné změny v systému souborů a konfiguracích zařízení. Škodlivý nebo chybný skript by mohl zařízení uvést do stavu, který jde obnovit jenom pomocí obnovení z image nebo továrního resetování zařízení.

### <a name="problems-with-bulk-enrollment-and-company-portal"></a>Problémy s hromadnou registrací a Portálem společnosti
Pokud se uživatel pokouší prostřednictvím Portálu společnosti zaregistrovat zařízení, které už bylo dříve hromadně zaregistrováno, obdrží upozornění, že u jeho zařízení jsou potřeba další kroky – buď nastavení, nebo registrace. Zařízení je zaregistrované, ale aplikace nebo webová stránka Portálu společnosti registraci nerozpoznala.

### <a name="bulk-enrollment-with-wi-fi"></a>Hromadná registrace přes Wi-Fi 

U hromadně registrovaných zařízení není možné použít certifikáty cílené na konkrétní uživatele ani provést nasazení přes Wi-Fi. Ke správě těchto připojení budete muset použít [certifikáty na úrovni zařízení](certificates-configure.md). 

### <a name="conditional-access"></a>podmíněný přístup
Podmíněný přístup není k dispozici u zařízení Windows zaregistrovaných pomocí hromadné registrace.
