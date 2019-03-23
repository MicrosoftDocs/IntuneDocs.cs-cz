---
title: Zařízení funkcích a nastaveních v Microsoft Intune – Azure | Dokumentace Microsoftu
description: Přehled různých profilů zařízení v Microsoft Intune. Získejte informace o funkce, omezení, e-mailu, Wi-Fi, VPN, vzdělávání, certifikátů, upgradu Windows 10, Bitlockeru a Windows defender, Windows Information Protection, šablony pro správu a vlastní nastavení konfigurace na webu Azure Portal. Používání těchto profilů pro správu a ochranu dat a zařízení ve vaší společnosti.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/12/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; get-started
ms.collection: M365-identity-device-management
ms.openlocfilehash: df8cc8c921b685ba7fa0b957685836d059a677e0
ms.sourcegitcommit: 1069b3b1ed593c94af725300aafd52610c7d8f04
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/22/2019
ms.locfileid: "58394989"
---
# <a name="apply-features-and-settings-on-your-devices-using-device-profiles-in-microsoft-intune"></a>Použít nastavení a funkcí v zařízeních pomocí profilů zařízení v Microsoft Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Microsoft Intune zahrnuje nastavení a funkcí můžete povolit nebo zakázat na různých zařízeních ve vaší organizaci. Tato nastavení a funkce se přidají do "konfiguračních profily". Můžete vytvořit profily pro různá zařízení a různé platformy, včetně iOS, Android a Windows. Potom pomocí Intune můžete použít nebo "přiřazení" profilu k zařízením.

Jako součást řešení správy mobilních zařízení provádět různé úlohy, pomocí těchto konfiguračních profilů. Například:

- Na zařízeních s Windows 10 použijte šablonu profilu blokující ovládacích prvků ActiveX v Internet Exploreru.
- Na zařízení s Iosem a macOS umožnit uživatelům používat tiskárny s Airprintem ve vaší organizaci.
- Povolit nebo zakázat přístup k bluetooth na zařízení.
- Vytvoření profilu Wi-Fi nebo VPN, který dává různým zařízením přístup k vaší podnikové síti.
- Správa aktualizací softwaru, včetně při jejich instalaci.
- Spusťte jako vyhrazených veřejných terminálech, který můžete spustit jednu aplikaci, nebo spouštět aplikace pro řadu zařízení s Androidem.

Tento článek obsahuje přehled různých typů profilů, které lze vytvořit. Povolit nebo zakázat některé funkce na zařízeních, používání těchto profilů.

## <a name="administrative-templates-preview"></a>Šablony pro správu (Preview)

[Šablony pro správu](administrative-templates-windows.md) zahrnují stovky nastavení, která můžete nakonfigurovat pro aplikaci Internet Explorer, OneDrive, vzdálené plochy, Word, Excel a jiných aplikacích.

Tyto šablony správce, kterým poskytuje zjednodušený pohled na nastavení zásad skupiny podobné, ale jsou 100 % založené na cloudu.

Tato funkce podporuje:

- Windows 10 a novější

## <a name="device-features"></a>Funkce zařízení

[Funkce zařízení](device-features-configure.md) ovládají funkce na zařízeních s Iosem a macOS, jako jsou AirPrint, oznámení a zprávy zámek obrazovky.

Tato funkce podporuje:

- iOS 
- macOS

## <a name="device-restrictions"></a>Omezení zařízení

[Omezení zařízení](device-restrictions-configure.md) řídí zabezpečení, hardware, sdílení dat a další nastavení na zařízeních. Můžete například vytvořit profil omezení zařízení, který uživatelům zařízení s iOSem zakazuje použít fotoaparát v zařízení. 

Tato funkce podporuje:

- Android
- Android enterprise
- iOS
- macOS
- Windows 10 a novější
- Windows 10 Team

## <a name="delivery-optimization"></a>Optimalizace doručení

[Optimalizace doručení](delivery-optimization-windows.md) poskytuje lepší prostředí pro doručování aktualizací softwaru. Tato nastavení jsou nahrazení **aktualizace softwaru** > **aktualizační kanál Windows 10** nastavení.

Pomocí těchto nastavení můžete řídit, jak se aktualizace softwaru se stáhnou do zařízení ve vaší organizaci. Například můžete umožnit uživatelům získat vlastní aktualizace nebo aktualizace pomocí cloudových služeb, která optimalizace doručování v profilu zařízení.

Tato funkce podporuje:

- Windows 10 a novější

## <a name="endpoint-protection"></a>Ochrana koncového bodu

[Nastavení služby Ochrana koncového bodu pro Windows 10](endpoint-protection-windows-10.md) konfiguruje nastavení pro BitLocker a Windows Defender pro zařízení s Windows 10.

Informace o zařazení rozšířené ochrany před internetovými útoky v programu Windows Defender pomocí Microsoft Intune najdete v článku o [konfiguraci koncových bodů pomocí nástrojů pro správu mobilních zařízení (MDM)](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/configure-endpoints-mdm-windows-defender-advanced-threat-protection).

Tato funkce podporuje:

- Windows 10 a novější

## <a name="identity-protection"></a>Ochrana identit

[Ochrana identit](identity-protection-configure.md) řídí prostředí Windows Hello pro firmy na zařízeních s Windows 10 a Windows 10 Mobile. Konfigurací těchto nastavení můžete zpřístupnit Windows Hello pro firmy uživatelům a zařízením a specifikovat požadavky na PIN kódy a gesta zařízení.  

Tato funkce podporuje:  

- Windows 10 a novější
- Windows Holographic for Business  

## <a name="kiosk"></a>Kiosk

[Nastavení celoobrazovkového](kiosk-settings.md) profilu konfiguruje zařízení běžela jedna aplikace nebo spustit velký počet aplikací. Na svém veřejném terminálu si můžete přizpůsobit i další funkce, například úvodní nabídku a webový prohlížeč.

Tato funkce podporuje:

- Windows 10 a novější

K dispozici i jako omezení zařízení pro nastavení celoobrazovkového [Android](device-restrictions-android.md#kiosk), [Androidu Enterprise](device-restrictions-android-for-work.md#dedicated-device-settings), a [ios](device-restrictions-ios.md#kiosk-supervised-only).

## <a name="email"></a>Email

[Nastavení e-mailu](email-settings-configure.md) vytvoří, přiřadí a sleduje nastavení e-mailu protokolu Exchange ActiveSync na zařízeních. E-mailové profily pomoc s konzistencí, omezíte volání podpory a umožní koncovým uživatelům přístup k firemnímu e-mailu na jejich osobních zařízení bez nutnosti něco nastavovat jejich část. 

Tato funkce podporuje: 

- Android
- Android Enterprise
- iOS
- Windows Phone 8.1
- Windows 10 a novější

## <a name="vpn"></a>Síť VPN

[Nastavení VPN](vpn-settings-configure.md) přiřadí uživatelům a zařízením v organizaci profily sítě VPN, aby se mohli snadno a bezpečně připojit k síti. 

Virtuální privátní sítě (VPN) umožňují uživatelům zabezpečený vzdálený přístup k firemní síti. Zařízení používají profil připojení VPN k navázání připojení se serverem VPN. 

Tato funkce podporuje: 

- Android
- Android Enterprise
- iOS
- macOS
- Windows Phone 8.1
- Windows 8.1
- Windows 10 a novější

## <a name="wi-fi"></a>Wi-Fi

[Nastavení Wi-Fi](wi-fi-settings-configure.md) přiřadí uživatelům a zařízením nastavení bezdrátové sítě. Po přiřazení profilu Wi-Fi získají uživatelé přístup k vaší podnikové síti, aniž by ji museli konfigurovat sami. 

Tato funkce podporuje: 

- Android
- Android Enterprise
- iOS
- macOS
- Windows 8.1 (pouze import)
- Windows 10 a novější

## <a name="esim-cellular---public-preview"></a>Mobilní profily eSIM ve verzi Public Preview

[mobilní profily karty eSIM](esim-device-configuration.md) umožňuje správcům nakonfigurovat mobilní datové tarify pro vaše spravovaná zařízení pro přístup k Internetu a data. Po získání aktivační kódy od mobilního operátora, použijte k importu těchto aktivační kódy a zařaďte do zařízení s podporou karty eSIM Intune.

Tato funkce podporuje:
- Windows 10 Fall Creators Update a novější

## <a name="education"></a>Vzdělávání

[Nastavení vzdělávání – Windows 10](education-settings-configure.md) konfiguruje možnosti pro [aplikaci Windows Zkuste si test](https://education.microsoft.com/gettrained/win10takeatest). Když tyto možnosti nakonfigurujete, žádnou jinou aplikaci nepůjde na zařízení spustit, dokud nebude test dokončen.

[Nastavení vzdělávání – iOS](education-settings-configure-ios-shared.md) používá aplikaci Classroom pro systém iOS, která umožňuje vést výuku a ovládat zařízení studentů v učebně. Zařízení iPad můžete nakonfigurovat tak, že mnoho studentů můžou sdílet jedno zařízení.

## <a name="edition-upgrade"></a>Upgrade edice

[Upgrady edice Windows 10](edition-upgrade-configure-windows-10.md) automaticky upgradují zařízení s některými verzemi Windows 10 na novější edici.

Tato funkce podporuje: 
- Windows 10 a novější

## <a name="update-policies"></a>Zásady aktualizací

[Zásady aktualizací pro iOS](software-updates-ios.md) ukazují, jak vytvořit a přiřadit zásady pro iOS k instalaci aktualizací softwaru na zařízení s iOSem. Můžete také zkontrolovat stav instalace.

Aktualizace zásad na zařízeních s Windows, naleznete v tématu [optimalizace doručení](delivery-optimization-windows.md). 

Tato funkce podporuje:
- iOS

## <a name="certificates"></a>Certifikáty

[Certifikáty](certificates-configure.md) nakonfigurovat důvěryhodné SCEP a PKCS certifikáty, které jsou přiřazeny k zařízení. Tyto certifikáty ověřování Wi-Fi, VPN a e-mailové profily.

Tato funkce podporuje: 

- Android
- Android Enterprise
- iOS
- Windows Phone 8.1
- Windows 8.1
- Windows 10 a novější

## <a name="windows-information-protection-profile"></a>Profil Windows Information Protection

[Služba Windows Information Protection](windows-information-protection-configure.md) pomáhá chránit před únikem dat, aniž by zasahovala do možností zaměstnanců. Pomáhá také chránit podnikové aplikace a data před náhodnými úniky dat na firemních zařízeních a osobních zařízeních, která zaměstnanci používají v práci. Pomocí Windows Information Protection nevyžaduje změny prostředí nebo jiných aplikací.

Tato funkce podporuje:

- Windows 10 a novější

## <a name="shared-multi-user-device"></a>Sdílené zařízení s více uživateli

[Windows 10](shared-user-device-settings-windows.md) a [Windows Holographic for Business](shared-user-device-settings-windows-holographic.md) zahrnuje nastavení pro správu zařízení s více uživateli, označované také jako sdílená zařízení nebo sdílené počítače. Když se uživatel přihlásí k zařízení, zvolíte-li uživatel může změnit možnosti Přejít do režimu spánku nebo uložit soubory v zařízení. Například pro úsporu místa, můžete vytvořit profil, který odstraní neaktivní přihlašovacích údajů ze zařízení s Windows, HoloLens.

Tato nastavení sdílených více uživateli zařízení umožňují správcům řídit některé funkce zařízení a spravovat tyto sdílené zařízení přes Intune.

Tato funkce podporuje:

- Windows 10 a novější
- Windows Holographic for Business

## <a name="zebra-mobility-extensions-mx"></a>Zebra Mobility Extensions (MX)

[Zebra Mobility rozšíření (MX)](android-zebra-mx-overview.md) správcům umožňuje použití a správa Zebra zařízení v Intune. Vytváření profilů StageNow s nastavením a pak pomocí Intune můžete přiřadit a tyto profily nasadit do zařízení Zebra. [StageNow běžné problémy a protokolování](android-zebra-mx-logs-troubleshoot.md) je skvělý prostředek pro řešení potíží s profily a podívejte se na některé potenciální problémy při použití StageNow.

Tato funkce podporuje:

- Android

## <a name="custom-profile"></a>Profil Vlastní

[Vlastní nastavení](custom-settings-configure.md) umožňují správcům přiřadit nastavení zařízení, která nejsou součástí Intune. Na zařízeních s Androidem můžete zadat hodnoty OMA-URI. U zařízení s iOSem můžete naimportovat konfigurační soubor, který jste vytvořili v nástroji Apple Configurator.

Tato funkce podporuje:

- Android
- Android Enterprise
- iOS
- macOS
- Windows Phone 8.1

## <a name="manage-and-troubleshoot"></a>Správa a řešení problémů

[Při správě profilů](device-profile-monitor.md) můžete zjistit stav zařízení a přiřazené profily. Také pomoci vyřešit konflikty tím, že zobrazíte nastavení, které způsobují konflikt a profily, které obsahují tato nastavení. [Běžné problémy a řešení](device-profile-troubleshoot.md) pomáhá správcům práci pomocí profilů. Popisuje, co se stane po odstranění profilu, co způsobí, že oznámení k odeslání do zařízení a další.

## <a name="next-steps"></a>Další postup

Zvolte vaši platformu a začít pracovat.
