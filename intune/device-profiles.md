---
title: "Co jsou profily zařízení v Microsoft Intune?"
titleSuffix: Intune on Azure
description: "Poznejte profily zařízení Intune a zjistěte, jak vám pomůžou se správou a ochranou zařízení ve firmě."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 08/23/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 95ce3b6a307a71431b9717abdc3980f15a916a18
ms.sourcegitcommit: 4dc5bed94cc965a54eacac2d87fb2d49c9300c3a
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/25/2017
---
# <a name="what-are-microsoft-intune-device-profiles"></a>Co jsou profily zařízení v Microsoft Intune?

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Úloha **Konfigurace zařízení** ve službě Microsoft Intune slouží ke správě nastavení a funkcí na všech zařízeních, která spravujete. Tuto úlohu použijete nejčastěji k vytvoření profilů zařízení, které umožňují spravovat a řídit na zařízeních celou řadu různých funkcí.

Když tuto úlohu otevřete, uvidíte následující možnosti:

- **Přehled** – na této stránce se zobrazuje stav a sestavy, které vám pomůžou monitorovat konfigurace zařízení přiřazené uživatelům a zařízením.
- **Spravovat profily** – sem přejdete, když budete vytvářet profily konfigurace zařízení. Dále v tomto tématu najdete seznam všech typů profilů, které můžete vytvořit.
- **Nastavit certifikační autoritu** – tento pracovní postup vás provede kroky potřebnými ke konfiguraci profilů certifikátů Intune.

## <a name="getting-started"></a>Začínáme

Pracovní postup při vytváření profilů zařízení je pro všechny profily podobný. Další informace najdete v článku [Vytváření profilů konfigurace zařízení v Microsoft Intune](device-profile-create.md). Pak si přečtěte konkrétní informace o vytvoření nastavení pro jednotlivé typy profilů.

U zařízení můžete spravovat následující funkce:

## <a name="device-features"></a>Funkce zařízení

Funkcemi zařízení můžete ovládat funkce na zařízeních s iOSem a macOS, jako jsou AirPrint, oznámení a konfigurace sdílených zařízení.
Další informace najdete v tématu [Postup konfigurace nastavení funkce zařízení](device-features-configure.md). Podporované platformy: iOS a macOS.

## <a name="device-restrictions"></a>Omezení zařízení
Pomocí omezení zařízení můžete regulovat řadu nastavení na vámi spravovaných zařízeních v různých kategoriích včetně nastavení zabezpečení, hardwaru a sdílení dat. Můžete například vytvořit profil omezení zařízení, který uživatelům zařízení s iOSem zabraňuje v přístupu k fotoaparátu.
Další informace najdete v článku [Konfigurace nastavení omezení zařízení](device-restrictions-configure.md). Podporované platformy: Android, iOS, macOS, Windows 10 a Windows 10 Team.

## <a name="email"></a>E-mailu
E-mailové profily vám umožní na spravovaných zařízeních vytvořit, přiřadit a monitorovat nastavení e-mailů Exchange ActiveSync. E-mailové profily přispívají ke konzistentnosti, omezují volání na podporu a dávají uživatelům přístup k firemnímu e-mailu na jejich osobních zařízeních bez toho, aby museli něco nastavovat.
Další informace najdete v článku [Jak nakonfigurovat nastavení e-mailu](email-settings-configure.md). Podporované platformy: Android, iOS, Windows Phone 8.1 a Windows 10.

## <a name="wi-fi"></a>Wi-Fi
Profily Wi-Fi umožňují přiřadit nastavení bezdrátové sítě uživatelům a zařízením ve vaší organizaci. Po přiřazení profilu Wi-Fi získají uživatelé přístup k vaší podnikové síti, aniž by ji museli konfigurovat sami.
Další informace najdete v článku [Jak nakonfigurovat nastavení Wi-Fi](wi-fi-settings-configure.md). Podporované platformy: Android, iOS, macOS a Windows 8.1 (jen import).

## <a name="vpn"></a>Síť VPN
Virtuální privátní sítě (VPN) umožňují uživatelům zabezpečený vzdálený přístup k firemní síti. Zařízení používají profil připojení VPN k navázání připojení se serverem VPN. Přiřazením profilů sítě VPN uživatelům a zařízením v organizaci jim umožníte snadné a bezpečné připojení k síti.
Další informace najdete v článku [Jak nakonfigurovat nastavení sítě VPN](vpn-settings-configure.md).
Podporované platformy: Android, iOS, macOS, Windows Phone 8.1, Windows 8.1 a Windows 10.

## <a name="education"></a>Vzdělávání
Umožňuje vám nakonfigurovat možnosti pro aplikaci Windows Zkuste si test. Když tyto možnosti nakonfigurujete, žádnou jinou aplikaci nepůjde na zařízení spustit, dokud nebude test dokončen.
Další informace najdete v článku [Konfigurace nastavení vzdělávání](education-settings-configure.md).

## <a name="certificates"></a>Certifikáty
Tento typ profilu umožňuje nakonfigurovat důvěryhodné certifikáty a certifikáty SCEP a PKCS, které lze přiřadit k zařízením a použít k ověření profilů Wi-Fi, sítě VPN a e-mailu.
Další informace najdete v článku [Konfigurace certifikátů](certificates-configure.md). Podporované platformy: Android, iOS, Windows Phone 8.1, Windows 8.1 a Windows 10.

## <a name="edition-upgrade"></a>Upgrade edice
Tento typ profilu vám umožní automaticky upgradovat zařízení s některými verzemi Windows 10 na novější edici.
Další informace najdete v článku [Konfigurace nastavení upgradu edice Windows 10](edition-upgrade-configure-windows-10.md). Podporované platformy: jen Windows 10.

## <a name="endpoint-protection"></a>Ochrana koncového bodu
Tento typ profilu vám umožní nakonfigurovat nastavení BitLockeru a Windows Defenderu pro zařízení s Windows 10.
Další informace najdete v tématu o [nastavení ochrany koncového bodu pro Windows 10 a novější](endpoint-protection-windows-10.md). Podporované platformy: jen Windows 10.

## <a name="windows-information-protection"></a>Windows Information Protection
Služba Windows Information Protection pomáhá chránit před únikem dat, aniž by jinak zasahovala do činnosti zaměstnanců. Pomáhá také chránit podnikové aplikace a data před náhodnými úniky dat na zařízeních ve vlastnictví společnosti a osobních zařízeních, která si uživatelé přinesou do práce, a nevyžaduje přitom žádné změny prostředí nebo ostatních aplikací.
Další informace najdete v článku [Jak nakonfigurovat službu Windows Information Protection](windows-information-protection-configure.md). Podporované platformy: jen Windows 10.

## <a name="custom"></a>Vlastní
Pomocí vlastních nastavení můžete k zařízení přiřadit nastavení, která nejsou předdefinovaná v Intune. Například u zařízení s Androidem můžete určit hodnoty OMA-URI, které slouží ke konfiguraci zařízení. U zařízení s iOSem můžete naimportovat konfigurační soubor, který jste vytvořili v nástroji Apple Configurator.
Další informace najdete v článku [Konfigurace vlastního nastavení](custom-settings-configure.md). Podporované platformy: Android, iOS, macOS a Windows Phone 8.1.

## <a name="next-steps"></a>Další kroky
Zvolte jeden z typů profilů na seznamu a začněte s konfigurací zařízení.
