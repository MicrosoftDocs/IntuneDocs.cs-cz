---
title: "Co jsou profily zařízení v Microsoft Intune?"
titleSuffix: Intune Azure preview
description: "Intune Azure Preview: Poznejte profily zařízení Intune a zjistěte, jak vám pomůžou se správou a ochranou zařízení ve firmě."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/15/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: 153cce3809e24303b8f88a833e2fc7bdd9428a4a
ms.openlocfilehash: eb48265e4655117976c9847b1f5bee712f0c2e3c
ms.lasthandoff: 02/18/2017


---

# <a name="what-are-microsoft-intune-device-profiles"></a>Co jsou profily zařízení v Microsoft Intune?

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Úloha **Konfigurovat zařízení** v Microsoft Intune slouží ke správě nastavení a funkcí na všech zařízeních, která spravujete. Tuto úlohu použijete nejčastěji k vytvoření profilů zařízení, které umožňují spravovat a řídit celou řadu různých funkcí na zařízeních, která spravujete.

Když tuto úlohu otevřete, uvidíte následující možnosti:

- **Přehled** – na této stránce se zobrazuje stav a sestavy, které vám pomůžou monitorovat konfigurace zařízení přiřazené uživatelům a zařízením.
- **Spravovat profily** – sem přejdete, když budete vytvářet profily konfigurace zařízení. Dole najdete seznam všech typů profilů, které můžete vytvořit.
- **Nastavit certifikační autoritu** – tento pracovní postup vás provede kroky potřebnými ke konfiguraci certifikátů. To budete muset udělat, pokud chcete pracovat s profily certifikátů Intune.

## <a name="getting-started"></a>Začínáme

Pracovní postup při vytváření profilů zařízení je pro všechny profily podobný. Pokud potřebujete informace o vytváření profilů, přečtěte si článek [Jak vytvořit profily konfigurace zařízení Microsoft Intune](/intune-azure/configure-devices/how-to-create-device-profiles). Pak si přečtěte konkrétní informace o vytvoření nastavení pro jednotlivé typy profilů.

U zařízení můžete spravovat následující funkce:

## <a name="device-restrictions"></a>Omezení zařízení
Pomocí omezení zařízení můžete ovládat širokou škálu nastavení a funkcí v různých kategoriích včetně nastavení zabezpečení, prohlížeče, hardwaru a sdílení dat. Můžete například vytvořit profil omezení zařízení, který uživatelům zařízení s iOSem zabraňuje v přístupu k fotoaparátu.
Další informace najdete v článku [Jak u zařízení nakonfigurovat nastavení omezení](how-to-configure-device-restrictions.md). Podporované platformy: Android, iOS, macOS, Windows 10 a Windows 10 Team.

## <a name="email"></a>E-mail
E-mailové profily vám umožní na spravovaných zařízeních vytvořit, nasadit a monitorovat nastavení e-mailů Exchange ActiveSync. Nasazením těchto nastavení zajistíte konzistenci, omezíte volání podpory a dáte uživatelům přístup k firemnímu e-mailu na jejich osobních zařízeních, aniž musí něco nastavovat.
Další informace najdete v článku [Jak nakonfigurovat nastavení e-mailu](how-to-configure-email-settings.md). Podporované platformy: Android, iOS, Windows Phone 8.1 a Windows 10.

## <a name="wi-fi"></a>Wi-Fi
Profily Wi-Fi vám umožní nasadit nastavení bezdrátové sítě uživatelům a zařízením ve vaší organizaci. Při nasazení profilu Wi-Fi budou mít uživatelé přístup k vaší podnikové síti, aniž by ji museli konfigurovat sami.
Další informace najdete v článku [Jak nakonfigurovat nastavení Wi-Fi](how-to-configure-wi-fi-settings.md). Podporované platformy: Android, iOS, macOS a Windows 8.1 (jen import).

## <a name="vpn"></a>Síť VPN
Virtuální privátní sítě (VPN) umožňují uživatelům zabezpečený vzdálený přístup k firemní síti. Zařízení používají profil připojení VPN k navázání připojení se serverem VPN. Pomocí profilů sítě VPN můžete uživatelům a zařízením v organizaci nasadit nastavení sítě VPN, aby se mohli snadno a bezpečně připojit k síti.
Další informace najdete v článku [Jak nakonfigurovat nastavení sítě VPN](how-to-configure-vpn-settings.md).
Podporované platformy: Android, iOS, macOS, Windows Phone 8.1, Windows 8.1 a Windows 10.

## <a name="certificates"></a>Certifikáty
Tento typ profilu umožňuje nakonfigurovat důvěryhodné certifikáty a certifikáty SCEP a PKCS, které lze přiřadit k zařízením a použít k ověření profilů Wi-Fi, sítě VPN a e-mailu.
Další informace najdete v článku [Jak nakonfigurovat certifikáty](how-to-configure-certificates.md). Podporované platformy: Android, iOS, Windows Phone 8.1, Windows 8.1 a Windows 10.

## <a name="edition-upgrade"></a>Upgrade edice
Tento typ profilu umožňuje automaticky upgradovat zařízení s určitými verzemi Windows 10 na novější edici. Další informace najdete v článku [Jak nakonfigurovat upgrady edic Windows 10](how-to-configure-windows-10-edition-upgrade.md). Podporované platformy: jen Windows 10.

## <a name="windows-information-protection"></a>Windows Information Protection
Služba Windows Information Protection pomáhá chránit před únikem dat, aniž by jinak zasahovala do činnosti zaměstnanců. Pomáhá také chránit podnikové aplikace a data před náhodnými úniky dat na zařízeních ve vlastnictví společnosti a osobních zařízeních, která si uživatelé přinesou do práce, a nevyžaduje přitom žádné změny prostředí nebo ostatních aplikací.
Další informace najdete v článku [Jak nakonfigurovat službu Windows Information Protection](how-to-configure-windows-information-protection.md). Podporované platformy: jen Windows 10.

## <a name="custom"></a>Vlastní
Pomocí vlastních nastavení můžete k zařízení přiřadit nastavení, která nejsou předdefinovaná v Intune. Například u zařízení s Androidem můžete určit hodnoty OMA-URI, které slouží ke konfiguraci zařízení. U zařízení s iOSem můžete naimportovat konfigurační soubor, který jste vytvořili v nástroji Apple Configurator.
Další informace najdete v článku [Jak nakonfigurovat vlastní nastavení](how-to-configure-custom-settings.md). Podporované platformy: Android, iOS, macOS a Windows Phone 8.1.

