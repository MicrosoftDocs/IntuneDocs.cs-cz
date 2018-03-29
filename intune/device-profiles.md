---
title: Profily zařízení v Microsoft Intune – Azure | Microsoft Docs
description: Přehled různých profilů zařízení Microsoft Intune, včetně funkcí, omezení, e-mailu, Wi-Fi, VPN, vzdělávání, certifikátů, upgradu Windows 10, BitLockeru a Windows Defenderu, Windows Information Protection a nastavení konfigurace vlastních zařízení na portálu Azure Portal Tento profil použijte ke správě a ochraně dat a zařízení ve vaší společnosti.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/22/2018
ms.topic: get-started-article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.reviewer: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: e92a10f51fb403c802c1c6d3ea79ccf49a1e93fb
ms.sourcegitcommit: a22309174e617e59ab0cdd0a55abde38711a5f35
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/23/2018
---
# <a name="what-are-microsoft-intune-device-profiles"></a>Co jsou profily zařízení v Microsoft Intune?

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Microsoft Intune zahrnuje nastavení a funkce, které můžete povolit nebo zakázat na různých zařízeních v rámci vaší organizace. Tato nastavení a funkce se spravují pomocí profilů. Například: 

- Profil Wi-Fi, který dává různým zařízením přístup k vaší podnikové síti Wi-Fi
- Profil VPN, který poskytuje různým zařízením přístup k serveru VPN ve vaší podnikové síti

Toto téma obsahuje přehled různých profilů, které můžete vytvořit pro zařízení. Tyto profily umožňují povolit nebo zakázat některé funkce na zařízeních.

## <a name="before-you-begin"></a>Před zahájením
Pokud chcete zobrazit dostupné funkce, otevřete [Azure Portal](https://portal.azure.com) a spusťte prostředek Intune. 

**Konfigurace zařízení** zahrnuje následující možnosti:

- **Přehled**: Zobrazí stav profilů a další podrobnosti o profilech, které jste přiřadili uživatelům a zařízením.
- **Správa**: Umožňuje vytvořit profily zařízení a nahrát vlastní [powershellové skripty](intune-management-extension.md) ke spuštění v rámci profilu.
- **Monitorování**: Umožňuje zkontrolovat stav profilu, jestli se jedná o úspěch nebo chybu, a také zobrazit protokoly vašich profilů.
- **Instalační program**: Umožňuje přidat k profilu certifikační autoritu (SCEP nebo PFX) nebo povolit službu TEM (Telecom Expense Management).

## <a name="create-the-profile"></a>Vytvoření profilu

[Vytvoření profilů zařízení](device-profile-create.md) obsahuje podrobné informace k vytvoření profilu. 

## <a name="device-features-profile"></a>Profil Funkce zařízení

[Funkce zařízení](device-features-configure.md) ovládají funkce na zařízeních s iOSem a macOS, jako jsou třeba AirPrint, oznámení a konfigurace sdílených zařízení.

Tato funkce podporuje:  
- iOS 
- macOS

## <a name="device-restrictions-profile"></a>Profil Omezení zařízení
[Omezení zařízení](device-restrictions-configure.md) řídí zabezpečení, hardware, sdílení dat a další nastavení na zařízeních. Můžete například vytvořit profil omezení zařízení, který uživatelům zařízení s iOSem zakazuje použít fotoaparát v zařízení. 

Tato funkce podporuje: 

- Android
- iOS
- macOS
- Windows 10
- Windows 10 Team

## <a name="email-profile"></a>e-mailový profil
Profil [Nastavení e-mailu](email-settings-configure.md) vytvoří, přiřadí a sleduje nastavení e-mailu Exchange ActiveSync na zařízeních. E-mailové profily pomáhají zajistit konzistentnost, omezují volání na podporu a dávají uživatelům přístup k firemnímu e-mailu na jejich osobních zařízeních bez toho, aby museli něco nastavovat. 

Tato funkce podporuje: 

- Android
- iOS
- Windows Phone 8.1
- Windows 10

## <a name="wi-fi-profile"></a>Wi-Fi profil
[Nastavení Wi-Fi](wi-fi-settings-configure.md) přiřadí uživatelům a zařízením nastavení bezdrátové sítě. Po přiřazení profilu Wi-Fi získají uživatelé přístup k vaší podnikové síti, aniž by ji museli konfigurovat sami. 

Tato funkce podporuje: 

- Android
- iOS
- macOS
- Windows 8.1 (pouze import)

## <a name="vpn-profile"></a>Profil VPN
[Nastavení VPN](vpn-settings-configure.md) přiřadí uživatelům a zařízením v organizaci profily sítě VPN, aby se mohli snadno a bezpečně připojit k síti. 

Virtuální privátní sítě (VPN) umožňují uživatelům zabezpečený vzdálený přístup k firemní síti. Zařízení používají profil připojení VPN k navázání připojení se serverem VPN. 

Tato funkce podporuje: 

- Android
- iOS
- macOS
- Windows Phone 8.1
- Windows 8.1
- Windows 10

## <a name="education-profile"></a>Profil Vzdělávání
[Nastavení Vzdělávání](education-settings-configure.md) konfiguruje možnosti pro [aplikaci Windows Zkuste si test](https://education.microsoft.com/gettrained/win10takeatest). Když tyto možnosti nakonfigurujete, žádnou jinou aplikaci nepůjde na zařízení spustit, dokud nebude test dokončen.

## <a name="certificates-profile"></a>Profil Certifikáty
[Certifikáty](certificates-configure.md) umožňují nakonfigurovat důvěryhodné certifikáty a certifikáty SCEP a PKCS, které je možné přiřadit k zařízením a použít k ověření profilů Wi-Fi, sítě VPN a e-mailu.

Tato funkce podporuje: 

- Android
- iOS
- Windows Phone 8.1
- Windows 8.1
- Windows 10

## <a name="edition-upgrade-profile"></a>Profil Upgrade edice
[Upgrady edice Windows 10](edition-upgrade-configure-windows-10.md) automaticky upgradují zařízení s některými verzemi Windows 10 na novější edici.

Tato funkce podporuje: jenom Windows 10

## <a name="endpoint-protection-profile"></a>Profil Ochrana koncového bodu
[Nastavení služby Ochrana koncového bodu pro Windows 10](endpoint-protection-windows-10.md) konfiguruje nastavení pro BitLocker a Windows Defender pro zařízení s Windows 10.

Informace o zařazení rozšířené ochrany před internetovými útoky v programu Windows Defender pomocí Microsoft Intune najdete v článku o [konfiguraci koncových bodů pomocí nástrojů pro správu mobilních zařízení (MDM)](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/configure-endpoints-mdm-windows-defender-advanced-threat-protection).

Tato funkce podporuje: jenom Windows 10

## <a name="windows-information-protection-profile"></a>Profil Windows Information Protection
[Služba Windows Information Protection](windows-information-protection-configure.md) pomáhá chránit před únikem dat, aniž by zasahovala do možností zaměstnanců. Pomáhá také chránit podnikové aplikace a data před náhodnými úniky dat na zařízeních ve vlastnictví společnosti a osobních zařízeních, která zaměstnanci používají v práci. Probíhá to bez nutnosti provádět změny prostředí nebo ostatních aplikací.

Tato funkce podporuje: jenom Windows 10

## <a name="custom-profile"></a>Profil Vlastní
[Vlastní nastavení](custom-settings-configure.md) zahrnuje možnost přiřadit k zařízení nastavení, která nejsou předdefinovaná v Intune. Například na zařízení s Androidem, můžete zadat hodnoty OMA-URI. U zařízení s iOSem můžete naimportovat konfigurační soubor, který jste vytvořili v nástroji Apple Configurator. 

Tato funkce podporuje:

- Android
- iOS
- macOS
- Windows Phone 8.1